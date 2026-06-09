# CngRsa32Compat_HMACMD5Init

- ea: `0x18000df0c`
- end: `0x18000df50`
- name: `CngRsa32Compat_HMACMD5Init`
- size: `68`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash, PUCHAR pbSecret)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ddd0`
- `0x18001fcb0`
- `0x180020128`

## callees

- `0x18000df0c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000df3a`
- `bcrypt!BCryptCreateHash` at `0x18000df3a`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_HMACMD5Init(BCRYPT_HASH_HANDLE *phHash, PUCHAR pbSecret, ULONG cbSecret)
{
  NTSTATUS result; // eax

  if ( cbSecret >= 0x40 )
    cbSecret = 64;
  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, phHash, 0, 0, pbSecret, cbSecret, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x18000df0c  sub     rsp, 48h
0x18000df10  mov     eax, 40h ; '@'
0x18000df15  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18000df1d  cmp     r8d, eax
0x18000df20  cmovnb  r8d, eax
0x18000df24  xor     r9d, r9d; cbHashObject
0x18000df27  mov     [rsp+48h+cbSecret], r8d; cbSecret
0x18000df2c  xor     r8d, r8d; pbHashObject
0x18000df2f  mov     [rsp+48h+pbSecret], rdx; pbSecret
0x18000df34  mov     rdx, rcx; phHash
0x18000df37  lea     ecx, [rax+51h]; hAlgorithm
0x18000df3a  call    cs:__imp_BCryptCreateHash
0x18000df40  test    eax, eax
0x18000df42  jns     short loc_18000DF4B
0x18000df44  mov     ecx, 7
0x18000df49  int     29h; Win8: RtlFailFast(ecx)
0x18000df4b  add     rsp, 48h
0x18000df4f  retn
```
