# Dart Documentation
Flutter is an open-source UI software development toolkit created by Google. It's used to build natively compiled applications for mobile, web, and desktop from a single codebase. The key feature of Flutter is its ability to create beautiful and expressive user interfaces with a flexible and efficient framework.
<br><br>
Now, Dart is the programming language that Flutter uses. It's also developed by Google and is designed for building web, server, and mobile applications. Dart is known for its fast performance and strong support for modern development workflows. In the context of Flutter, Dart is used to write the code for your app, defining its logic and behavior.

## Resources
- Flutter Official Documentation : [link](https://docs.flutter.dev/)
- Dart and Flutter Packages: [link](https://pub.dev/)
- Dart Pad : [link](https://dartpad.dev/)

# Flutter Sample Projects
## Counter App
```
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: MyCounterApp(),
    );
  }
}

class MyCounterApp extends StatefulWidget {
  @override
  _MyCounterAppState createState() => _MyCounterAppState();
}

class _MyCounterAppState extends State<MyCounterApp> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  void _decrementCounter() {
    setState(() {
      _counter--;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Counter App'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const Text(
              'Counter Value:',
              style: TextStyle(fontSize: 20),
            ),
            Text(
              '$_counter',
              style: const TextStyle(fontSize: 40, fontWeight: FontWeight.bold),
            ),
            const SizedBox(height: 20),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: _incrementCounter,
                  child: const Icon(Icons.add),
                ),
                const SizedBox(width: 20),
                ElevatedButton(
                  onPressed: _decrementCounter,
                  child: const Icon(Icons.remove),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}
```
## Color Changer App
```
import 'package:flutter/material.dart';

void main() {
  runApp(
    const MaterialApp(
      home: HomeScreen(),
    ),
  );
}

class HomeScreen extends StatefulWidget {
  const HomeScreen({super.key});

  @override
  State<HomeScreen> createState() => _HomeScreenState();
}

class _HomeScreenState extends State<HomeScreen> {
  bool _isRed = true;

  void _changeColor() {
    setState(() {
      _isRed = !_isRed;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Color Change App'),
      ),
      body: Center(
        child: GestureDetector(
          onTap: _changeColor,
          child: Container(
            width: 200,
            height: 200,
            color: _isRed ? Colors.red : Colors.green,
            child: const Center(
              child: Text(
                'Tap to Change Color',
                style: TextStyle(color: Colors.white),
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

