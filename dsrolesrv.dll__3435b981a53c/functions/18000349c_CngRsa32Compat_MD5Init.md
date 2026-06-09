# CngRsa32Compat_MD5Init

- ea: `0x18000349c`
- end: `0x1800034dc`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003cb8`
- `0x180003d84`

## callees

- `0x18000349c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800034c6`
- `bcrypt!BCryptCreateHash` at `0x1800034c6`

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
0x18000349c  sub     rsp, 48h
0x1800034a0  xor     r9d, r9d; cbHashObject
0x1800034a3  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800034ab  mov     rdx, rcx; phHash
0x1800034ae  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1800034b6  xor     r8d, r8d; pbHashObject
0x1800034b9  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1800034c2  lea     ecx, [r9+21h]; hAlgorithm
0x1800034c6  call    cs:__imp_BCryptCreateHash
0x1800034cc  test    eax, eax
0x1800034ce  jns     short loc_1800034D7
0x1800034d0  mov     ecx, 7
0x1800034d5  int     29h; Win8: RtlFailFast(ecx)
0x1800034d7  add     rsp, 48h
0x1800034db  retn
```
