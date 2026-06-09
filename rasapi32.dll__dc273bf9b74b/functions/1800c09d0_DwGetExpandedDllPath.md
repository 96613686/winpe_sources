# DwGetExpandedDllPath

- ea: `0x1800c09d0`
- end: `0x1800c0aa4`
- name: `DwGetExpandedDllPath`
- size: `212`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, WCHAR **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800972f0`
- `0x1800d0300`

## callees

- `0x18004e984`
- `0x1800c09d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c0a67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c0a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0a8a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0a51`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0a80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0a51`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0a80`

## pseudocode

```c

```
