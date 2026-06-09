# privateRegReadValue

- ea: `0x180038ea0`
- end: `0x1800391d2`
- name: `privateRegReadValue`
- size: `818`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038a70`
- `0x180038cf8`
- `0x18007e1f0`

## callees

- `0x180029d80`
- `0x18002b050`
- `0x180038ea0`
- `0x1800391d8`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dc9e0`
- `0x1800ddf54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038efc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038fe4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038efc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038fe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003919e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003919e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038f90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038f90`

## pseudocode

```c

```
