# GetHash(uchar const *,ulong,uint,uchar * *,ulong *)

- ea: `0x18006dea4`
- end: `0x18006e143`
- name: `?GetHash@@YAJPEBEKIPEAPEAEPEAK@Z`
- size: `671`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, DWORD dwDataLen@<edx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005e0b4`
- `0x18006dbb8`
- `0x1800893dc`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012cf0`
- `0x1800307c4`
- `0x18003334c`
- `0x18006dea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006e04e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006e0b2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006e04e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18006e0b2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18006e0fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18006e0fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18006dfee`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18006dfee`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18006df9e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18006df9e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18006e10c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18006e10c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18006e01a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18006e01a`

## string_xrefs

- `0x18006e004`: `CryptCreateHash`

## pseudocode

```c

```
