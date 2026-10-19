# Web Wrapper Regression Checks

These checks cover the HTML/CSS wrapper around the precompiled Unity WebGL build. They do not verify in-game physics or gameplay because the Unity C# source project is not included in this repository.

## Manual smoke test
- [ ] Open `index.html` from a local static HTTP server or the deployed site (do not use `file://`).
- [ ] Verify the Unity loader, JSON config, data, framework, and WASM files return HTTP 200.
- [ ] Verify the game starts without console errors in a current desktop browser with WebGL enabled.
- [ ] Verify the fullscreen control enters fullscreen and gracefully reports an initialization issue if the Unity instance has not loaded.
- [ ] Verify the Android download link resolves to `Android File/flappybird.apk` and downloads the committed APK.
- [ ] Verify the canvas fits without horizontal overflow at 320px, 375px, 768px, and 1440px viewport widths.
- [ ] Verify the wrapper remains usable in portrait and landscape orientation.
- [ ] Disable WebGL or block the loader and verify a visible, accessible load-error message appears.
- [ ] Keyboard-tab through the page and confirm the fullscreen control has an accessible name and visible focus indicator.

## Static checks
- [ ] Confirm `index.html` includes a viewport meta tag and no inline fixed canvas dimensions.
- [ ] Confirm the APK link path matches the tracked file path (URL-encoded spaces are acceptable).
- [ ] Confirm mobile and landscape responsive CSS rules exist.
- [ ] Confirm the load-error alert is hidden until an initialization/load error occurs.
