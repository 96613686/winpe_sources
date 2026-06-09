# RegReadBinary

- ea: `0x1800d8d80`
- end: `0x1800d8f49`
- name: `RegReadBinary`
- size: `457`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCSTR lpValue@<rdx>, LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800d34e4`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800d8d80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800d8dfb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800d8ec5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800d8dfb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800d8ec5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d8e50`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d8e50`

## pseudocode

```c

```
