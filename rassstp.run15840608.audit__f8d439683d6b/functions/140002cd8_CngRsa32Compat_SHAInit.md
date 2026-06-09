# CngRsa32Compat_SHAInit

- ea: `0x140002cd8`
- end: `0x140002d1f`
- name: `CngRsa32Compat_SHAInit`
- size: `71`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400100ac`

## callees

- `0x140002cd8`

## import_xrefs

- `ksecdd!BCryptCreateHash` at `0x140002d02`
- `ksecdd!BCryptCreateHash` at `0x140002d02`

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
0x140002cd8  sub     rsp, 48h
0x140002cdc  xor     r9d, r9d; cbHashObject
0x140002cdf  mov     [rsp+48h+dwFlags], 0; dwFlags
0x140002ce7  mov     rdx, rcx; phHash
0x140002cea  mov     [rsp+48h+cbSecret], 0; cbSecret
0x140002cf2  xor     r8d, r8d; pbHashObject
0x140002cf5  mov     [rsp+48h+pbSecret], 0; pbSecret
0x140002cfe  lea     ecx, [r9+31h]; hAlgorithm
0x140002d02  call    cs:__imp_BCryptCreateHash
0x140002d09  nop     dword ptr [rax+rax+00h]
0x140002d0e  test    eax, eax
0x140002d10  jns     short loc_140002D19
0x140002d12  mov     ecx, 7
0x140002d17  int     29h; Win8: RtlFailFast(ecx)
0x140002d19  add     rsp, 48h
0x140002d1d  retn
```
