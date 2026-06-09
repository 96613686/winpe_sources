# SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)

- ea: `0x18002572c`
- end: `0x180025879`
- name: `?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z`
- size: `333`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017f60`
- `0x180038d48`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18002572c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800257ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800257ee`

## string_xrefs

- `0x18002574f`: `SxRegReadULONGLONG`

## pseudocode

```c

```
