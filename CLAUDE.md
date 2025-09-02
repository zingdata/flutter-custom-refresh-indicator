# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Flutter package (`custom_refresh_indicator`) that provides highly customizable pull-to-refresh functionality. The package allows developers to create completely custom refresh indicators beyond the standard Material Design refresh indicator.

## Key Architecture

### Core Components

- **`CustomRefreshIndicator`**: Main widget that wraps scrollable content and handles refresh gestures
- **`CustomMaterialIndicator`**: Simpler widget for Material Design-style indicators with customization
- **`IndicatorController`**: Manages state and provides data about the refresh indicator's current status
- **State Management**: Uses Flutter's built-in state management with `StatefulWidget`

### Package Structure

- `lib/src/custom_refresh_indicator.dart`: Main CustomRefreshIndicator widget implementation
- `lib/src/widgets/`: Reusable widgets including CustomMaterialIndicator
- `lib/src/data/`: Data classes for states, edges, sides, triggers, and durations
- `lib/src/physics/`: Custom scroll physics for overscroll behavior
- `lib/src/utils/`: Utility classes for animations and transformations
- `lib/custom_refresh_indicator.dart`: Main export file

### Core Concepts

1. **Indicator States**: idle, dragging, armed, loading, complete, finalizing, canceling
2. **Trigger Edges**: leadingEdge, trailingEdge, bothEdges (supports reversed lists)
3. **Trigger Modes**: onEdge, anywhere (determines when refresh can be triggered)
4. **Indicator Sides**: top, bottom, left, right, none (positioning)

## Common Development Commands

### Code Quality
```bash
# Format code with 120 character line length
dart format . --line-length=120

# Run linter (uses flutter_lints)
flutter analyze

# Run tests
flutter test
```

### Example App
```bash
# Navigate to example directory
cd example

# Run the example app
flutter run

# Build for web (has online demo)
flutter build web
```

## Development Guidelines

### Code Style
- Line length: 120 characters (configured in pubspec.yaml scripts)
- Uses `flutter_lints` package for linting rules
- Follow Flutter/Dart conventions with typed parameters

### Key Implementation Patterns

1. **Builder Pattern**: The main widget uses builder functions for custom indicators
2. **Controller Pattern**: IndicatorController provides state and interaction data
3. **Physics Integration**: Custom scroll physics handle overscroll behavior
4. **Animation Management**: Uses Flutter's animation framework extensively

### Testing
- Tests located in `test/` directory
- Covers core functionality, data classes, and controller behavior
- Run tests with `flutter test`

### Example Implementation Structure
When creating new indicators, follow the pattern in `example/lib/indicators/`:
- Create custom indicator widgets that use `IndicatorController`
- Implement builders that respond to controller state changes
- Handle different indicator states (dragging, armed, loading, etc.)
- Use controller properties like `value`, `state`, `edge`, `side` for animations

## Package Distribution
- Published on pub.dev as `custom_refresh_indicator`
- Version 4.0.1 (check pubspec.yaml for current version)
- Minimum Flutter SDK: 1.16.0
- Minimum Dart SDK: 2.17.0