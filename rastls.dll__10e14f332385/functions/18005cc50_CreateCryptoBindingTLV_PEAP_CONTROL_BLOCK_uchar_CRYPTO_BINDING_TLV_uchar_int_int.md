# CreateCryptoBindingTLV(_PEAP_CONTROL_BLOCK *,uchar *,_CRYPTO_BINDING_TLV *,uchar *,int,int)

- ea: `0x18005cc50`
- end: `0x18005ce66`
- name: `?CreateCryptoBindingTLV@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAEPEAU_CRYPTO_BINDING_TLV@@1HH@Z`
- size: `534`
- prototype: `unsigned int __usercall@<eax>(struct _PEAP_CONTROL_BLOCK *@<rcx>, unsigned __int8 *@<rdx>, struct _CRYPTO_BINDING_TLV *@<r8>, unsigned __int8 *@<r9>, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180008b28`
- `0x18001ac80`
- `0x18002d9e8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180012bd0`
- `0x180013430`
- `0x180035680`
- `0x18003623c`
- `0x18005cc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cd85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cd85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ce3d`
- `eapputil!EapConvertHostToWireFormat16` at `0x18005ccc0`
- `eapputil!EapConvertHostToWireFormat16` at `0x18005ccc0`
- `bcrypt!BCryptGenRandom` at `0x18005ccf1`
- `bcrypt!BCryptGenRandom` at `0x18005ccf1`

## pseudocode

```c

```
