# PlaliReadRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort * *,ulong *)

- ea: `0x1801317fc`
- end: `0x180131a2a`
- name: `?PlaliReadRegistryStringValue@@YAJPEAUHKEY__@@PEBGKPEAPEAGPEAK@Z`
- size: `558`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned int@<r8d>, unsigned __int16 **@<r9>, unsigned int *)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18012e11c`
- `0x18012e4e0`
- `0x18012edd0`
- `0x18012f050`
- `0x18012f3c8`
- `0x18012f4b0`
- `0x18012fdec`
- `0x180130b28`
- `0x180131a30`

## callees

- `0x180015f98`
- `0x18012f320`
- `0x1801317fc`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131867`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801319a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131867`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801319a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801318f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801318f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180131a0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801318e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180131a0f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1801318b0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1801318b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180131a1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180131a1d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1801318d4`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1801318d4`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180131960`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180131960`

## pseudocode

```c

```
