# DllMain

- ea: `0x1800110dc`
- end: `0x1800111fd`
- name: `DllMain`
- size: `289`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180005218`

## callees

- `0x180006158`
- `0x18000f0dc`
- `0x1800110dc`
- `0x180033dec`
- `0x180084204`
- `0x180084284`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011110`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011179`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180011161`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180011161`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x18001119d`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x18001119d`

## string_xrefs

- `0x1800111b5`: `onecore\base\appmodel\execmodel\desktopappx\libjitv\thread_state.cpp`

## pseudocode

```c

```
