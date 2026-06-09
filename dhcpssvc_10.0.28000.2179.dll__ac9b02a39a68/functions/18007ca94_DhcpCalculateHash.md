# DhcpCalculateHash

- ea: `0x18007ca94`
- end: `0x18007cd0a`
- name: `DhcpCalculateHash`
- size: `630`
- prototype: `__int64 __fastcall(DWORD dwDataLen, BYTE *pbData, DWORD *pdwDataLen)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007d1fc`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18007ca94`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x18007ccaf`
- `ADVAPI32!CryptDestroyHash` at `0x18007ccaf`
- `ADVAPI32!CryptGetHashParam` at `0x18007cb9d`
- `ADVAPI32!CryptGetHashParam` at `0x18007cc3e`
- `ADVAPI32!CryptGetHashParam` at `0x18007cb9d`
- `ADVAPI32!CryptGetHashParam` at `0x18007cc3e`
- `ADVAPI32!CryptHashData` at `0x18007cb3a`
- `ADVAPI32!CryptHashData` at `0x18007cb3a`
- `ADVAPI32!CryptCreateHash` at `0x18007cad9`
- `ADVAPI32!CryptCreateHash` at `0x18007cad9`
- `KERNEL32!HeapAlloc` at `0x18007cbee`
- `KERNEL32!HeapAlloc` at `0x18007cbee`
- `KERNEL32!GetLastError` at `0x18007cae9`
- `KERNEL32!GetLastError` at `0x18007cb58`
- `KERNEL32!GetLastError` at `0x18007cbad`
- `KERNEL32!GetLastError` at `0x18007cc4e`
- `KERNEL32!GetLastError` at `0x18007ccbf`
- `KERNEL32!GetLastError` at `0x18007cae9`
- `KERNEL32!GetLastError` at `0x18007cb58`
- `KERNEL32!GetLastError` at `0x18007cbad`
- `KERNEL32!GetLastError` at `0x18007cc4e`
- `KERNEL32!GetLastError` at `0x18007ccbf`
- `KERNEL32!HeapFree` at `0x18007cc97`
- `KERNEL32!HeapFree` at `0x18007cc97`

## pseudocode

```c

```
