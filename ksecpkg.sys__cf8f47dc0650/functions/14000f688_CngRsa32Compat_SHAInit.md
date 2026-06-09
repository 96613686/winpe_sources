# CngRsa32Compat_SHAInit

- ea: `0x14000f688`
- end: `0x14000f6cf`
- name: `CngRsa32Compat_SHAInit`
- size: `71`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f230`
- `0x14002f290`

## callees

- `0x14000f688`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14000f6b2`
- `cng!BCryptCreateHash` at `0x14000f6b2`

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
0x14000f688  sub     rsp, 48h
0x14000f68c  xor     r9d, r9d; cbHashObject
0x14000f68f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000f697  mov     rdx, rcx; phHash
0x14000f69a  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14000f6a2  xor     r8d, r8d; pbHashObject
0x14000f6a5  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000f6ae  lea     ecx, [r9+31h]; hAlgorithm
0x14000f6b2  call    cs:__imp_BCryptCreateHash
0x14000f6b9  nop     dword ptr [rax+rax+00h]
0x14000f6be  test    eax, eax
0x14000f6c0  jns     short loc_14000F6C9
0x14000f6c2  mov     ecx, 7
0x14000f6c7  int     29h; Win8: RtlFailFast(ecx)
0x14000f6c9  add     rsp, 48h
0x14000f6cd  retn
```
