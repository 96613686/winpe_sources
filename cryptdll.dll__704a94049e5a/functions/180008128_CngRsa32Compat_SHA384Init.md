# CngRsa32Compat_SHA384Init

- ea: `0x180008128`
- end: `0x180008168`
- name: `CngRsa32Compat_SHA384Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800081c0`
- `0x180008210`

## callees

- `0x180008128`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180008152`
- `bcrypt!BCryptCreateHash` at `0x180008152`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA384Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x51, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180008128  sub     rsp, 48h
0x18000812c  xor     r9d, r9d; cbHashObject
0x18000812f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180008137  mov     rdx, rcx; phHash
0x18000813a  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180008142  xor     r8d, r8d; pbHashObject
0x180008145  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18000814e  lea     ecx, [r9+51h]; hAlgorithm
0x180008152  call    cs:__imp_BCryptCreateHash
0x180008158  test    eax, eax
0x18000815a  jns     short loc_180008163
0x18000815c  mov     ecx, 7
0x180008161  int     29h; Win8: RtlFailFast(ecx)
0x180008163  add     rsp, 48h
0x180008167  retn
```
