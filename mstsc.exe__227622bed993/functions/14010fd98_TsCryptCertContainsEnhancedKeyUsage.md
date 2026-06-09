# TsCryptCertContainsEnhancedKeyUsage

- ea: `0x14010fd98`
- end: `0x14010fe9c`
- name: `TsCryptCertContainsEnhancedKeyUsage`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1401100b8`

## callees

- `0x14010fc0c`
- `0x14010fce0`
- `0x14010fd98`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14010fe81`
- `KERNEL32!LocalFree` at `0x14010fe81`
- `KERNEL32!GetLastError` at `0x14010fe66`
- `KERNEL32!GetLastError` at `0x14010fe66`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14010fe5c`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14010fe5c`
- `CRYPT32!CertFindExtension` at `0x14010fdec`
- `CRYPT32!CertFindExtension` at `0x14010fdec`

## pseudocode

```c

```
