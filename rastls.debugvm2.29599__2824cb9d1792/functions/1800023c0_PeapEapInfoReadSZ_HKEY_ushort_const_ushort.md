# PeapEapInfoReadSZ(HKEY__ *,ushort const *,ushort * *)

- ea: `0x1800023c0`
- end: `0x180002481`
- name: `?PeapEapInfoReadSZ@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `193`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800030d0`

## callees

- `0x1800023c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002414`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002468`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002468`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800023ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002446`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800023ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002446`

## pseudocode

```c

```
