# CryptDllFormatAttr

- ea: `0x1800d6840`
- end: `0x1800d6dc0`
- name: `CryptDllFormatAttr`
- size: `1408`
- prototype: `__int64 __usercall@<rax>(DWORD dwCertEncodingType@<ecx>, PCNZCH lpString1, BYTE *pbEncoded, DWORD cbEncoded, void *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008720`
- `0x180009da0`
- `0x180021920`
- `0x1800777bc`
- `0x1800d6840`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6d17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6d63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6d17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6da4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d6da4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d693d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d69a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d6adf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d6b51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d693d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d69a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d6adf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d6b51`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800d6c2c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800d6c2c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d6b2c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d6b8b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d6b2c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d6b8b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800d6a4b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800d6a4b`

## pseudocode

```c

```
