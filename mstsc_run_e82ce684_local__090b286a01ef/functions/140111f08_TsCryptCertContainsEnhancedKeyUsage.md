# TsCryptCertContainsEnhancedKeyUsage

- ea: `0x140111f08`
- end: `0x14011200c`
- name: `TsCryptCertContainsEnhancedKeyUsage`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140112228`

## callees

- `0x140111d7c`
- `0x140111e50`
- `0x140111f08`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140111ff1`
- `KERNEL32!LocalFree` at `0x140111ff1`
- `KERNEL32!GetLastError` at `0x140111fd6`
- `KERNEL32!GetLastError` at `0x140111fd6`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x140111fcc`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x140111fcc`
- `CRYPT32!CertFindExtension` at `0x140111f5c`
- `CRYPT32!CertFindExtension` at `0x140111f5c`

## pseudocode

```c

```
