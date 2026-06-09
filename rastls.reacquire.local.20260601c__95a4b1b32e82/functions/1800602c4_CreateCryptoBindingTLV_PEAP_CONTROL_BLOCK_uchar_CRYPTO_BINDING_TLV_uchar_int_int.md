# CreateCryptoBindingTLV(_PEAP_CONTROL_BLOCK *,uchar *,_CRYPTO_BINDING_TLV *,uchar *,int,int)

- ea: `0x1800602c4`
- end: `0x1800604f9`
- name: `?CreateCryptoBindingTLV@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEPEAU_CRYPTO_BINDING_TLV@@1HH@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct _PEAP_CONTROL_BLOCK *, unsigned __int8 *, struct _CRYPTO_BINDING_TLV *, unsigned __int8 *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180009418`
- `0x18001c61c`
- `0x180030090`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180013eb0`
- `0x180014770`
- `0x180038270`
- `0x180038e4c`
- `0x1800602c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060419`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060405`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800604c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800604c9`
- `eapputil!EapConvertHostToWireFormat16` at `0x180060334`
- `eapputil!EapConvertHostToWireFormat16` at `0x180060334`
- `bcrypt!BCryptGenRandom` at `0x18006036b`
- `bcrypt!BCryptGenRandom` at `0x18006036b`

## pseudocode

```c

```
