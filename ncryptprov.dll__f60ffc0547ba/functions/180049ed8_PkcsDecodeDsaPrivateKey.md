# _PkcsDecodeDsaPrivateKey

- ea: `0x180049ed8`
- end: `0x18004a31d`
- name: `_PkcsDecodeDsaPrivateKey`
- size: `1093`
- prototype: `__int64 __usercall@<rax>(BYTE *pbEncoded@<rcx>, DWORD cbEncoded@<edx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004acf8`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001652c`
- `0x180038970`
- `0x1800398b0`
- `0x180049ed8`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fc8`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049f56`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049fb8`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049f56`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049fb8`

## string_xrefs

- `0x18004a269`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c

```
