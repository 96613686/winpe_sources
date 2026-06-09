# CngRsa32Compat_MD5Init

- ea: `0x1800039a0`
- end: `0x1800039d7`
- name: `CngRsa32Compat_MD5Init`
- size: `55`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003950`
- `0x180006710`
- `0x180006850`
- `0x180006b18`
- `0x18000750c`

## callees

- `0x1800039a0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800039c1`
- `bcrypt!BCryptCreateHash` at `0x1800039c1`

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
0x1800039a0  sub     rsp, 48h
0x1800039a4  xor     eax, eax
0x1800039a6  mov     rdx, rcx; phHash
0x1800039a9  mov     [rsp+48h+dwFlags], eax; dwFlags
0x1800039ad  xor     r9d, r9d; cbHashObject
0x1800039b0  mov     [rsp+48h+cbSecret], eax; cbSecret
0x1800039b4  xor     r8d, r8d; pbHashObject
0x1800039b7  mov     ecx, 21h ; '!'; hAlgorithm
0x1800039bc  mov     [rsp+48h+pbSecret], rax; pbSecret
0x1800039c1  call    cs:__imp_BCryptCreateHash
0x1800039c7  test    eax, eax
0x1800039c9  jns     short loc_1800039D2
0x1800039cb  mov     ecx, 7
0x1800039d0  int     29h; Win8: RtlFailFast(ecx)
0x1800039d2  add     rsp, 48h
0x1800039d6  retn
```
