# CngRsa32Compat_MD5Init

- ea: `0x18000fb7c`
- end: `0x18000fbbc`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800028f0`
- `0x180003f00`
- `0x180005bd0`
- `0x180007af0`

## callees

- `0x18000fb7c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000fba6`
- `bcrypt!BCryptCreateHash` at `0x18000fba6`

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
0x18000fb7c  sub     rsp, 48h
0x18000fb80  xor     r9d, r9d; cbHashObject
0x18000fb83  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18000fb8b  mov     rdx, rcx; phHash
0x18000fb8e  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18000fb96  xor     r8d, r8d; pbHashObject
0x18000fb99  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18000fba2  lea     ecx, [r9+21h]; hAlgorithm
0x18000fba6  call    cs:__imp_BCryptCreateHash
0x18000fbac  test    eax, eax
0x18000fbae  jns     short loc_18000FBB7
0x18000fbb0  mov     ecx, 7
0x18000fbb5  int     29h; Win8: RtlFailFast(ecx)
0x18000fbb7  add     rsp, 48h
0x18000fbbb  retn
```
