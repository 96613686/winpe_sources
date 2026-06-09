# SxRegReadBinary(HKEY__ *,ushort const *,uchar *,ulong,int)

- ea: `0x18002d538`
- end: `0x18002d665`
- name: `?SxRegReadBinary@@YAJPEAUHKEY__@@PEBGPEAEKH@Z`
- size: `301`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, LPBYTE lpData@<r8>, unsigned int@<r9d>, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017f60`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18002d538`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d5dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d5dc`

## string_xrefs

- `0x18002d557`: `SxRegReadBinary`

## pseudocode

```c

```
