# CngRsa32Compat_SHA512Init

- ea: `0x14000ec50`
- end: `0x14000ec97`
- name: `CngRsa32Compat_SHA512Init`
- size: `71`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002e110`
- `0x14002e170`

## callees

- `0x14000ec50`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14000ec7a`
- `cng!BCryptCreateHash` at `0x14000ec7a`

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
0x14000ec50  sub     rsp, 48h
0x14000ec54  xor     r9d, r9d; cbHashObject
0x14000ec57  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000ec5f  mov     rdx, rcx; phHash
0x14000ec62  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14000ec6a  xor     r8d, r8d; pbHashObject
0x14000ec6d  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000ec76  lea     ecx, [r9+61h]; hAlgorithm
0x14000ec7a  call    cs:__imp_BCryptCreateHash
0x14000ec81  nop     dword ptr [rax+rax+00h]
0x14000ec86  test    eax, eax
0x14000ec88  jns     short loc_14000EC91
0x14000ec8a  mov     ecx, 7
0x14000ec8f  int     29h; Win8: RtlFailFast(ecx)
0x14000ec91  add     rsp, 48h
0x14000ec95  retn
```
