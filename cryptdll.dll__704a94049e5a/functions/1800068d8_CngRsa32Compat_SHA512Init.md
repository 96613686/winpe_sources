# CngRsa32Compat_SHA512Init

- ea: `0x1800068d8`
- end: `0x180006918`
- name: `CngRsa32Compat_SHA512Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800069a0`
- `0x1800069f0`

## callees

- `0x1800068d8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180006902`
- `bcrypt!BCryptCreateHash` at `0x180006902`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA512Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x61, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x1800068d8  sub     rsp, 48h
0x1800068dc  xor     r9d, r9d; cbHashObject
0x1800068df  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800068e7  mov     rdx, rcx; phHash
0x1800068ea  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1800068f2  xor     r8d, r8d; pbHashObject
0x1800068f5  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1800068fe  lea     ecx, [r9+61h]; hAlgorithm
0x180006902  call    cs:__imp_BCryptCreateHash
0x180006908  test    eax, eax
0x18000690a  jns     short loc_180006913
0x18000690c  mov     ecx, 7
0x180006911  int     29h; Win8: RtlFailFast(ecx)
0x180006913  add     rsp, 48h
0x180006917  retn
```
