# CngRsa32Compat_MD5Init

- ea: `0x18001fa9c`
- end: `0x18001fadc`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001c80`
- `0x180002810`
- `0x18000335c`
- `0x180006d40`
- `0x180007a40`

## callees

- `0x18001fa9c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001fac6`
- `bcrypt!BCryptCreateHash` at `0x18001fac6`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x18001fa9c  sub     rsp, 48h
0x18001faa0  xor     r9d, r9d; cbHashObject
0x18001faa3  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18001faab  mov     rdx, rcx; phHash
0x18001faae  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18001fab6  xor     r8d, r8d; pbHashObject
0x18001fab9  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18001fac2  lea     ecx, [r9+21h]; hAlgorithm
0x18001fac6  call    cs:__imp_BCryptCreateHash
0x18001facc  test    eax, eax
0x18001face  jns     short loc_18001FAD7
0x18001fad0  mov     ecx, 7
0x18001fad5  int     29h; Win8: RtlFailFast(ecx)
0x18001fad7  add     rsp, 48h
0x18001fadb  retn
```
