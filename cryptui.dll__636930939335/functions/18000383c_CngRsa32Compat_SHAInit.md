# CngRsa32Compat_SHAInit

- ea: `0x18000383c`
- end: `0x18000387c`
- name: `CngRsa32Compat_SHAInit`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003600`
- `0x1800038ac`
- `0x1800052f0`

## callees

- `0x18000383c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180003866`
- `bcrypt!BCryptCreateHash` at `0x180003866`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAInit(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x18000383c  sub     rsp, 48h
0x180003840  xor     r9d, r9d; cbHashObject
0x180003843  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18000384b  mov     rdx, rcx; phHash
0x18000384e  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180003856  xor     r8d, r8d; pbHashObject
0x180003859  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180003862  lea     ecx, [r9+31h]; hAlgorithm
0x180003866  call    cs:__imp_BCryptCreateHash
0x18000386c  test    eax, eax
0x18000386e  jns     short loc_180003877
0x180003870  mov     ecx, 7
0x180003875  int     29h; Win8: RtlFailFast(ecx)
0x180003877  add     rsp, 48h
0x18000387b  retn
```
