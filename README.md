# Mini AI Studio (Safari PWA prototype)

A ChatGPT-inspired, local-first chat and project workspace intended for iPhone Safari.

## What is included
- Responsive chat interface, sidebar, conversation history
- Five real model IDs in a selector
- On-device inference attempt through Transformers.js / ONNX Runtime Web
- Local chat and project-note storage
- Text/code file attachments and basic ZIP project export
- PWA manifest and app-shell service worker

## Important limitations
This is a prototype, not a guarantee that every model will run on every iPhone/Safari version. Mobile Safari can terminate heavy tasks or run out of memory. Model files may be large. The model runtime is loaded from a CDN, and model files are downloaded from model hosting on first use, so setup requires internet. Generation is configured to use a browser runtime (`wasm`) rather than a hosted inference API. This does not make the app itself fully offline on first visit. The PWA shell can be cached, but reliable model caching depends on browser storage policies.

The five listed model repositories should be verified for current ONNX/quantized artifacts and Transformers.js compatibility before treating all five as supported. If one fails, the UI reports the error rather than faking a response. This prototype does not yet implement robust long-term memory retrieval, full IDE features, syntax highlighting, or ZIP import.

## Run / install
A PWA requires HTTPS or localhost; opening `index.html` directly from Files will not work reliably.
1. Host the folder on an HTTPS static host (for example, a static site host you control).
2. Open the HTTPS URL in Safari.
3. Use Share -> Add to Home Screen.
4. Load one model at a time; start with the smallest.
5. Keep Safari open while model files download and while testing.

No API key is included. No cloud inference endpoint is configured. External CDN/model hosting is used only to fetch app libraries and model files.
