# DllMain

- ea: `0x18005b9f8`
- end: `0x18005bb32`
- name: `DllMain`
- size: `314`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18007fa14`

## callees

- `0x180030ee0`
- `0x1800511b0`
- `0x180051814`
- `0x180055978`
- `0x180055fc0`
- `0x18005b9f8`
- `0x18006beec`
- `0x18006c6c8`
- `0x18006eea0`
- `0x18006f6ac`
- `0x180070bf0`
- `0x1800754e0`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x18005babf`
- `GDI32!LpkpInitializeEditControl` at `0x18005ba4a`
- `GDI32!LpkpInitializeEditControl` at `0x18005ba4a`
- `GDI32!gCookie` at `0x18005ba2b`
- `win32u!NtGdiInit2` at `0x18005ba1f`
- `win32u!NtGdiInit2` at `0x18005ba1f`

## pseudocode

```c

```
