# Os componentes de terceiros

O instalador do vTranscript leva componentes de outras pessoas e empresas, cada um com a licença dele. Os termos do
vTranscript (o arquivo [LICENSE](LICENSE)) não mudam essas licenças.

Esta lista é a da versão 0.5.0. Ela saiu dos metadados dos pacotes: o `cargo` para o núcleo em Rust, o `pnpm` para a
interface e os `dist-info` para o motor em Python. Nas licenças, `OR` quer dizer "à escolha de quem usa", e `AND`,
"as duas valem".

- **Onde estão os textos completos:**
  - os dos pacotes do motor e o do Python vão no próprio app instalado: em
    `%LOCALAPPDATA%\vTranscript\motor\LICENSE.txt` e nas pastas
    `%LOCALAPPDATA%\vTranscript\motor\site-packages\<pacote>.dist-info\`;
  - os outros, na página de cada pacote: no [crates.io](https://crates.io) e no [npm](https://www.npmjs.com).

## O que vai junto com o motor

- **O Python 3.14 embutido**, da Python Software Foundation: a licença PSF-2.0.
- **O runtime do Visual C++** (`vcruntime140.dll`, `vcruntime140_1.dll`, `msvcp140.dll` e `msvcp140_1.dll`), da
  Microsoft: ele vai como código redistribuível, nos termos do Visual Studio.
- **As bibliotecas do FFmpeg** (`motor\site-packages\av.libs\av*.dll`), que o PyAV traz: a LGPL 3.0 ou mais nova.
  - Você pode trocá-las por outra versão compatível.
  - O código delas está no [ffmpeg.org](https://ffmpeg.org), e a receita do build, no
    [pyav-ffmpeg](https://github.com/PyAV-Org/pyav-ffmpeg).
- **O PortAudio**, que o PyAudioWPatch traz: a licença MIT.
- **O modelo de voz CAM++** (`motor\modelos\speaker_campplus.onnx`), do
  [3D-Speaker](https://github.com/modelscope/3D-Speaker): a Apache 2.0.

### Os pacotes Python do motor (29)

**BSD-3-Clause** (8): av 19.0.2, click 8.5.0, fsspec 2026.9.0, httpcore 1.0.9, httpcore2 2.16.0, httpx2 2.16.0, idna 3.20, protobuf 7.36.2.

**MIT** (8): anyio 4.16.0, ctranslate2 4.8.5, faster-whisper 1.2.1, filelock 4.2.9, h11 0.16.0, onnxruntime 1.31.1, PyYAML 6.0.3, truststore 0.10.5.

**Apache-2.0** (6): flatbuffers 25.12.19, hf-xet 1.8.0, huggingface_hub 2.4.0, PyAudioWPatch 0.2.12.8, sherpa_onnx 1.13.4, tokenizers 0.23.3.

**BSD** (2): colorama 0.4.6, httpx 0.28.1.

**Apache-2.0 OR BSD-2-Clause** (1): packaging 26.3.

**BSD-3-Clause AND 0BSD AND MIT AND Zlib AND CC0-1.0** (1): numpy 2.5.1.

**MPL-2.0** (1): certifi 2026.10.23.

**MPL-2.0 AND MIT** (1): tqdm 4.70.1.

**PSF-2.0** (1): typing_extensions 4.16.0.

## O núcleo em Rust (250 crates)

**MIT OR Apache-2.0** (167): allocator-api2 0.2.21, anyhow 1.0.104, base64 0.22.1, base64 0.23.1, bit-set 0.8.0, bit-vec 0.8.0, bitflags 2.13.2, block-buffer 0.10.4, bumpalo 3.20.3, camino 1.2.6, cargo-platform 0.1.9, cfg-if 1.0.5, chrono 0.4.45, cookie 0.18.2, core_detect 1.0.0, cpufeatures 0.2.17, crc 3.4.0, crc-catalog 2.5.0, crc32fast 1.5.4, crossbeam-channel 0.5.17, crossbeam-queue 0.3.14, crossbeam-utils 0.8.23, crypto-common 0.1.7, ctor 1.0.13, deranged 0.5.9, digest 0.10.7, dirs 7.0.0, dirs-sys 0.5.0, dtoa 1.0.11, dyn-clone 1.0.20, either 1.19.0, equivalent 1.0.3, erased-serde 0.4.11, event-listener 5.4.2, fastrand 2.5.0, fdeflate 0.3.7, flate2 1.1.10, flume 0.11.1, fnv 1.0.7, form_urlencoded 1.2.2, futures-channel 0.3.34, futures-core 0.3.34, futures-executor 0.3.34, futures-intrusive 0.5.0, futures-io 0.3.34, futures-sink 0.3.34, futures-task 0.3.34, futures-util 0.3.34, getrandom 0.3.4, getrandom 0.4.3, glob 0.3.4, global-hotkey 0.8.0, hashbrown 0.12.3, hashbrown 0.15.5, hashbrown 0.17.1, hashlink 0.10.0, heck 0.5.0, hex 0.4.3, html5ever 0.39.0, http 1.5.0, ident_case 1.0.1, idna 1.1.0, idna_adapter 1.2.2, indexmap 1.9.3, indexmap 2.14.2, itoa 1.0.18, json-patch 4.2.0, jsonptr 0.7.1, keyboard-types 0.7.0, keyboard-types 0.8.3, keyring 3.6.3, libc 0.2.191, lock_api 0.4.14, log 0.4.35, markup5ever 0.39.0, mime 0.3.17, muda 0.20.0, num-conv 0.2.2, num-traits 0.2.19, once_cell 1.21.4, parking 2.2.1, parking_lot 0.12.5, parking_lot_core 0.9.12, percent-encoding 2.3.2, pin-project-lite 0.2.17, png 0.18.1, powerfmt 0.2.1, proc-macro2 1.0.107, quote 1.0.47, regex 1.13.1, regex-automata 0.4.18, regex-syntax 0.8.11, rustc-hash 2.1.3, scopeguard 1.2.0, semver 1.0.28, serde 1.0.229, serde_core 1.0.229, serde_derive_internals 0.29.1, serde_json 1.0.154, serde_spanned 1.1.2, serde_urlencoded 0.7.1, serde_with 3.24.0, serde-untagged 0.1.9, serialize-to-javascript 0.1.2, servo_arc 0.4.3, sha2 0.10.9, simdutf8 0.1.5, siphasher 1.0.4, smallvec 1.16.4, socket2 0.6.5, softbuffer 0.4.8, sqlx 0.8.6, sqlx-core 0.8.6, sqlx-macros-core 0.8.6, sqlx-sqlite 0.8.6, stable_deref_trait 1.2.1, string_cache 0.9.0, syn 2.0.119, syn 3.0.9, tauri 2.12.5, tauri-codegen 2.7.4, tauri-plugin-dialog 2.8.4, tauri-plugin-fs 2.7.1, tauri-plugin-global-shortcut 2.4.1, tauri-plugin-single-instance 2.5.5, tauri-runtime 2.12.2, tauri-runtime-wry 2.12.3, tauri-utils 2.10.2, tendril 0.5.1, thiserror 2.0.21, time 0.3.55, time-core 0.1.9, toml 1.2.0+spec-1.1.0, toml_datetime 1.1.2+spec-1.1.0, toml_parser 1.1.5+spec-1.1.0, toml_writer 1.2.0+spec-1.1.0, tray-icon 0.25.1, typed-path 0.12.4, typeid 1.0.3, typenum 1.20.1, unicode-segmentation 1.13.3, url 2.5.8, utf_types 1.0.0, utf8_iter 1.1.0, uuid 1.29.0, web_atoms 0.2.6, web-time 1.1.0, window-vibrancy 0.8.1, windows 0.62.2, windows_x86_64_msvc 0.52.6, windows_x86_64_msvc 0.53.1, windows-collections 0.3.2, windows-core 0.62.2, windows-future 0.3.2, windows-link 0.2.1, windows-numerics 0.3.1, windows-result 0.4.1, windows-strings 0.5.1, windows-sys 0.59.0, windows-sys 0.60.2, windows-sys 0.61.2, windows-targets 0.52.6, windows-targets 0.53.5, windows-threading 0.2.1, windows-version 0.1.7, wry 0.57.1, zeroize 1.9.1.

**MIT** (40): atoi 2.0.0, bytes 1.12.1, cargo_metadata 0.19.2, cfb 0.14.0, darling 0.24.1, darling_core 0.24.1, derive_more 2.1.1, docx-rs 0.4.22, dom_query 0.28.0, dotenvy 0.15.7, generic-array 0.14.7, ico 0.6.0, infer 0.22.0, libsqlite3-sys 0.30.1, mio 1.2.4, new_debug_unreachable 1.0.6, phf 0.13.1, phf_generator 0.13.1, phf_shared 0.13.1, plist 1.10.3, precomputed-hash 0.1.1, quick-xml 0.41.0, quick-xml 0.42.0, rfd 0.17.2, schemars 0.8.22, simd-adler32 0.3.10, slab 0.4.12, spin 0.9.9, strsim 0.11.1, synstructure 0.14.0, tokio 1.54.1, tokio-stream 0.1.19, tracing 0.1.44, tracing-core 0.1.36, urlpattern 0.6.0, webview2-com 0.39.1, webview2-com-sys 0.39.1, winnow 1.0.5, zip 8.6.0, zmij 1.0.23.

**Unicode-3.0** (15): icu_collections 2.4.0, icu_locale_core 2.4.0, icu_normalizer 2.4.0, icu_normalizer_data 2.4.0, icu_properties 2.4.0, icu_properties_data 2.4.0, icu_provider 2.4.0, litemap 0.8.3, potential_utf 0.1.6, tinystr 0.8.5, writeable 0.6.4, yoke 0.8.4, zerofrom 0.1.8, zerotrie 0.2.5, zerovec 0.11.9.

**Unlicense OR MIT** (6): aho-corasick 1.1.5, byteorder 1.5.0, memchr 2.8.3, same-file 1.0.6, walkdir 2.5.0, winapi-util 0.1.11.

**MPL-2.0** (4): cssparser 0.37.0, dtoa-short 0.3.5, option-ext 0.2.0, selectors 0.38.0.

**Zlib** (3): foldhash 0.1.5, foldhash 0.2.0, zlib-rs 0.6.8.

**Apache-2.0** (2): tao 0.37.2, zopfli 0.8.4.

**BSD-3-Clause** (2): alloc-no-stdlib 3.0.0, alloc-stdlib 0.3.0.

**MIT OR Zlib OR Apache-2.0** (2): miniz_oxide 0.8.9, miniz_oxide 0.9.1.

**(Apache-2.0 OR MIT) AND BSD-3-Clause** (1): encoding_rs 0.8.44.

**(MIT OR Apache-2.0) AND Unicode-3.0** (1): unicode-ident 1.0.27.

**0BSD OR MIT OR Apache-2.0** (1): adler2 2.0.1.

**Apache-2.0 AND MIT** (1): dpi 0.1.2.

**Apache-2.0 OR BSL-1.0** (1): ryu 1.0.23.

**BSD-3-Clause AND MIT** (1): brotli 9.1.1.

**BSD-3-Clause OR MIT** (1): brotli-decompressor 6.2.0.

**CC0-1.0 OR MIT-0 OR Apache-2.0** (1): dunce 1.0.5.

**MIT OR Apache-2.0 OR Zlib** (1): raw-window-handle 0.6.2.

## A interface (61 pacotes)

**MIT** (59): @floating-ui/core 1.8.0, @floating-ui/dom 1.8.0, @floating-ui/utils 0.2.12, @phosphor-icons/react 2.1.10, @tiptap/core 3.32.0, @tiptap/extension-blockquote 3.32.0, @tiptap/extension-bold 3.32.0, @tiptap/extension-bubble-menu 3.32.0, @tiptap/extension-bullet-list 3.32.0, @tiptap/extension-code 3.32.0, @tiptap/extension-code-block 3.32.0, @tiptap/extension-document 3.32.0, @tiptap/extension-dropcursor 3.32.0, @tiptap/extension-floating-menu 3.32.0, @tiptap/extension-gapcursor 3.32.0, @tiptap/extension-hard-break 3.32.0, @tiptap/extension-heading 3.32.0, @tiptap/extension-horizontal-rule 3.32.0, @tiptap/extension-italic 3.32.0, @tiptap/extension-link 3.32.0, @tiptap/extension-list 3.32.0, @tiptap/extension-list-item 3.32.0, @tiptap/extension-list-keymap 3.32.0, @tiptap/extension-ordered-list 3.32.0, @tiptap/extension-paragraph 3.32.0, @tiptap/extension-strike 3.32.0, @tiptap/extension-text 3.32.0, @tiptap/extension-underline 3.32.0, @tiptap/extensions 3.32.0, @tiptap/pm 3.32.0, @tiptap/react 3.32.0, @tiptap/starter-kit 3.32.0, @types/react 19.3.0, @types/react-dom 19.3.0, @types/use-sync-external-store 0.0.6, csstype 3.2.3, fast-equals 5.4.5, linkifyjs 4.4.0, orderedmap 2.1.1, prosemirror-changeset 2.4.6, prosemirror-commands 1.7.2, prosemirror-dropcursor 1.8.4, prosemirror-gapcursor 1.4.1, prosemirror-history 1.5.1, prosemirror-inputrules 1.5.1, prosemirror-keymap 1.2.3, prosemirror-model 1.25.12, prosemirror-schema-list 1.6.0, prosemirror-state 1.4.4, prosemirror-tables 1.8.5, prosemirror-transform 1.12.5, prosemirror-view 1.42.9, react 19.3.1, react-dom 19.3.1, rope-sequence 1.3.4, scheduler 0.28.0, use-sync-external-store 1.7.0, w3c-keyname 2.2.8, zustand 5.0.16.

**MIT OR Apache-2.0** (1): @tauri-apps/api 2.12.4.

**OFL-1.1** (1): @fontsource-variable/source-serif-4 5.3.1.

A fonte é a [Source Serif 4](https://github.com/adobe-fonts/source-serif), da Adobe, sob a SIL Open Font License 1.1. Os
ícones são do [Phosphor](https://phosphoricons.com), sob a MIT.

## O que não vai no instalador

O app baixa estes das fontes originais, só quando você escolhe:

- **os modelos do Whisper**, da OpenAI, sob a MIT, nas conversões do faster-whisper, no Hugging Face;
- **o pacote da GPU** (o cuBLAS e o cuDNN), da NVIDIA, sob a licença da NVIDIA, a partir das rodas dela no PyPI.

O WebView2, que mostra a interface, é um componente do Windows. Ele não vai no instalador: no Windows 10, o instalador o
baixa, se faltar.
