# CngRsa32Compat_SHAInit

- ea: `0x180007ff0`
- end: `0x180008030`
- name: `CngRsa32Compat_SHAInit`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008090`
- `0x1800080e0`

## callees

- `0x180007ff0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000801a`
- `bcrypt!BCryptCreateHash` at `0x18000801a`

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
0x180007ff0  sub     rsp, 48h
0x180007ff4  xor     r9d, r9d; cbHashObject
0x180007ff7  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180007fff  mov     rdx, rcx; phHash
0x180008002  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18000800a  xor     r8d, r8d; pbHashObject
0x18000800d  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180008016  lea     ecx, [r9+31h]; hAlgorithm
0x18000801a  call    cs:__imp_BCryptCreateHash
0x180008020  test    eax, eax
0x180008022  jns     short loc_18000802B
0x180008024  mov     ecx, 7
0x180008029  int     29h; Win8: RtlFailFast(ecx)
0x18000802b  add     rsp, 48h
0x18000802f  retn
```
