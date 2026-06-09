# CngRsa32Compat_SHAInit

- ea: `0x180027ae8`
- end: `0x180027b28`
- name: `CngRsa32Compat_SHAInit`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028ce0`

## callees

- `0x180027ae8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180027b12`
- `bcrypt!BCryptCreateHash` at `0x180027b12`

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
0x180027ae8  sub     rsp, 48h
0x180027aec  xor     r9d, r9d; cbHashObject
0x180027aef  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180027af7  mov     rdx, rcx; phHash
0x180027afa  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180027b02  xor     r8d, r8d; pbHashObject
0x180027b05  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180027b0e  lea     ecx, [r9+31h]; hAlgorithm
0x180027b12  call    cs:__imp_BCryptCreateHash
0x180027b18  test    eax, eax
0x180027b1a  jns     short loc_180027B23
0x180027b1c  mov     ecx, 7
0x180027b21  int     29h; Win8: RtlFailFast(ecx)
0x180027b23  add     rsp, 48h
0x180027b27  retn
```
