# DhcpCalculateHash

- ea: `0x18007cbec`
- end: `0x18007ce5f`
- name: `DhcpCalculateHash`
- size: `627`
- prototype: `__int64 __fastcall(DWORD dwDataLen, BYTE *pbData, DWORD *pdwDataLen, LPVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007d354`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18007cbec`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x18007ce04`
- `ADVAPI32!CryptDestroyHash` at `0x18007ce04`
- `ADVAPI32!CryptGetHashParam` at `0x18007ccf5`
- `ADVAPI32!CryptGetHashParam` at `0x18007cd96`
- `ADVAPI32!CryptGetHashParam` at `0x18007ccf5`
- `ADVAPI32!CryptGetHashParam` at `0x18007cd96`
- `ADVAPI32!CryptHashData` at `0x18007cc92`
- `ADVAPI32!CryptHashData` at `0x18007cc92`
- `ADVAPI32!CryptCreateHash` at `0x18007cc31`
- `ADVAPI32!CryptCreateHash` at `0x18007cc31`
- `KERNEL32!HeapAlloc` at `0x18007cd46`
- `KERNEL32!HeapAlloc` at `0x18007cd46`
- `KERNEL32!GetLastError` at `0x18007cc41`
- `KERNEL32!GetLastError` at `0x18007ccb0`
- `KERNEL32!GetLastError` at `0x18007cd05`
- `KERNEL32!GetLastError` at `0x18007cda6`
- `KERNEL32!GetLastError` at `0x18007ce14`
- `KERNEL32!GetLastError` at `0x18007cc41`
- `KERNEL32!GetLastError` at `0x18007ccb0`
- `KERNEL32!GetLastError` at `0x18007cd05`
- `KERNEL32!GetLastError` at `0x18007cda6`
- `KERNEL32!GetLastError` at `0x18007ce14`
- `KERNEL32!HeapFree` at `0x18007cdef`
- `KERNEL32!HeapFree` at `0x18007cdef`

## pseudocode

```c

```
