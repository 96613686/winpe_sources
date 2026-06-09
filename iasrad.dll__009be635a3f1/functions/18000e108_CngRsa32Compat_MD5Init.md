# CngRsa32Compat_MD5Init

- ea: `0x18000e108`
- end: `0x18000e148`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df80`
- `0x18001fcb0`
- `0x180020128`

## callees

- `0x18000e108`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000e132`
- `bcrypt!BCryptCreateHash` at `0x18000e132`

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
0x18000e108  sub     rsp, 48h
0x18000e10c  xor     r9d, r9d; cbHashObject
0x18000e10f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18000e117  mov     rdx, rcx; phHash
0x18000e11a  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18000e122  xor     r8d, r8d; pbHashObject
0x18000e125  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18000e12e  lea     ecx, [r9+21h]; hAlgorithm
0x18000e132  call    cs:__imp_BCryptCreateHash
0x18000e138  test    eax, eax
0x18000e13a  jns     short loc_18000E143
0x18000e13c  mov     ecx, 7
0x18000e141  int     29h; Win8: RtlFailFast(ecx)
0x18000e143  add     rsp, 48h
0x18000e147  retn
```
