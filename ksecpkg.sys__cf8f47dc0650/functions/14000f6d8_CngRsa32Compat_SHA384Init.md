# CngRsa32Compat_SHA384Init

- ea: `0x14000f6d8`
- end: `0x14000f71f`
- name: `CngRsa32Compat_SHA384Init`
- size: `71`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f390`
- `0x14002f3f0`

## callees

- `0x14000f6d8`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14000f702`
- `cng!BCryptCreateHash` at `0x14000f702`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA384Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x51, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x14000f6d8  sub     rsp, 48h
0x14000f6dc  xor     r9d, r9d; cbHashObject
0x14000f6df  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000f6e7  mov     rdx, rcx; phHash
0x14000f6ea  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14000f6f2  xor     r8d, r8d; pbHashObject
0x14000f6f5  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000f6fe  lea     ecx, [r9+51h]; hAlgorithm
0x14000f702  call    cs:__imp_BCryptCreateHash
0x14000f709  nop     dword ptr [rax+rax+00h]
0x14000f70e  test    eax, eax
0x14000f710  jns     short loc_14000F719
0x14000f712  mov     ecx, 7
0x14000f717  int     29h; Win8: RtlFailFast(ecx)
0x14000f719  add     rsp, 48h
0x14000f71d  retn
```
