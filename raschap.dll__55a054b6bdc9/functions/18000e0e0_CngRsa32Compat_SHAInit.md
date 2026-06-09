# CngRsa32Compat_SHAInit

- ea: `0x18000e0e0`
- end: `0x18000e117`
- name: `CngRsa32Compat_SHAInit`
- size: `55`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ab6c`
- `0x18001b3ec`
- `0x18001c570`

## callees

- `0x18000e0e0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000e101`
- `bcrypt!BCryptCreateHash` at `0x18000e101`

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
0x18000e0e0  sub     rsp, 48h
0x18000e0e4  xor     eax, eax
0x18000e0e6  mov     rdx, rcx; phHash
0x18000e0e9  mov     [rsp+48h+dwFlags], eax; dwFlags
0x18000e0ed  xor     r9d, r9d; cbHashObject
0x18000e0f0  mov     [rsp+48h+cbSecret], eax; cbSecret
0x18000e0f4  xor     r8d, r8d; pbHashObject
0x18000e0f7  mov     ecx, 31h ; '1'; hAlgorithm
0x18000e0fc  mov     [rsp+48h+pbSecret], rax; pbSecret
0x18000e101  call    cs:__imp_BCryptCreateHash
0x18000e107  test    eax, eax
0x18000e109  jns     short loc_18000E112
0x18000e10b  mov     ecx, 7
0x18000e110  int     29h; Win8: RtlFailFast(ecx)
0x18000e112  add     rsp, 48h
0x18000e116  retn
```
