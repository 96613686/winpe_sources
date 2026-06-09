# DhcpCreateAndLookupSid

- ea: `0x1800021c0`
- end: `0x18000231d`
- name: `DhcpCreateAndLookupSid`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180002324`

## callees

- `0x1800021c0`
- `0x18008ed64`
- `0x18008ef1c`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x180002203`
- `ADVAPI32!LookupAccountNameW` at `0x180002290`
- `ADVAPI32!LookupAccountNameW` at `0x180002203`
- `ADVAPI32!LookupAccountNameW` at `0x180002290`
- `KERNEL32!GetLastError` at `0x18000221a`
- `KERNEL32!GetLastError` at `0x1800022a0`
- `KERNEL32!GetLastError` at `0x18000221a`
- `KERNEL32!GetLastError` at `0x1800022a0`

## pseudocode

```c

```
