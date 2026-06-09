# GetObjectA

- ea: `0x18000e5a0`
- end: `0x18000e8ab`
- name: `GetObjectA`
- size: `779`
- prototype: `int __stdcall(HANDLE h, int c, LPVOID pv)`
- caller_count: `14`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000ee34`
- `0x180011fc0`
- `0x18001da40`
- `0x180020a00`
- `0x1800383fc`
- `0x1800532d4`
- `0x18005421c`
- `0x1800566ac`
- `0x180067ef4`
- `0x18006f4e0`
- `0x18007e9b4`
- `0x18007f2e8`
- `0x180089514`
- `0x18009ac00`

## callees

- `0x18000e5a0`
- `0x18000ea10`
- `0x180040e10`
- `0x18007ac50`
- `0x18007ba24`
- `0x180088950`
- `0x1800a3514`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x18000e77d`
- `GDI32!GdiSetLastError` at `0x18000e89e`
- `GDI32!GdiSetLastError` at `0x18000e77d`
- `GDI32!GdiSetLastError` at `0x18000e89e`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000e740`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000e740`
- `win32u!NtGdiExtGetObjectW` at `0x18000e643`
- `win32u!NtGdiExtGetObjectW` at `0x18000e68e`
- `win32u!NtGdiExtGetObjectW` at `0x18000e643`
- `win32u!NtGdiExtGetObjectW` at `0x18000e68e`

## pseudocode

```c

```
