# PeapEapInfoReadSZ(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180002420`
- end: `0x1800024fa`
- name: `?PeapEapInfoReadSZ@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `218`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003240`

## callees

- `0x180002420`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000247a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000247a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000245f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800024b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000245f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800024b2`

## pseudocode

```c

```
