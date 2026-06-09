# CngRsa32Compat_SHA256Init

- ea: `0x180008258`
- end: `0x180008298`
- name: `CngRsa32Compat_SHA256Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800082f0`
- `0x180008340`

## callees

- `0x180008258`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180008282`
- `bcrypt!BCryptCreateHash` at `0x180008282`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA256Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180008258  sub     rsp, 48h
0x18000825c  xor     r9d, r9d; cbHashObject
0x18000825f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180008267  mov     rdx, rcx; phHash
0x18000826a  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180008272  xor     r8d, r8d; pbHashObject
0x180008275  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18000827e  lea     ecx, [r9+41h]; hAlgorithm
0x180008282  call    cs:__imp_BCryptCreateHash
0x180008288  test    eax, eax
0x18000828a  jns     short loc_180008293
0x18000828c  mov     ecx, 7
0x180008291  int     29h; Win8: RtlFailFast(ecx)
0x180008293  add     rsp, 48h
0x180008297  retn
```
