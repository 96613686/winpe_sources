# CngRsa32Compat_SHA256Init

- ea: `0x14000f728`
- end: `0x14000f76f`
- name: `CngRsa32Compat_SHA256Init`
- size: `71`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f4b0`
- `0x14002f510`

## callees

- `0x14000f728`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14000f752`
- `cng!BCryptCreateHash` at `0x14000f752`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA256Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x14000f728  sub     rsp, 48h
0x14000f72c  xor     r9d, r9d; cbHashObject
0x14000f72f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000f737  mov     rdx, rcx; phHash
0x14000f73a  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14000f742  xor     r8d, r8d; pbHashObject
0x14000f745  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000f74e  lea     ecx, [r9+41h]; hAlgorithm
0x14000f752  call    cs:__imp_BCryptCreateHash
0x14000f759  nop     dword ptr [rax+rax+00h]
0x14000f75e  test    eax, eax
0x14000f760  jns     short loc_14000F769
0x14000f762  mov     ecx, 7
0x14000f767  int     29h; Win8: RtlFailFast(ecx)
0x14000f769  add     rsp, 48h
0x14000f76d  retn
```
