# CngRsa32Compat_MD5Init

- ea: `0x140004bb0`
- end: `0x140004bf0`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a4ec`
- `0x14000eb80`
- `0x14000eef8`
- `0x14000f340`
- `0x14002de70`
- `0x14002dfb0`

## callees

- `0x140004bb0`

## import_xrefs

- `cng!BCryptCreateHash` at `0x140004bd1`
- `cng!BCryptCreateHash` at `0x140004bd1`

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
0x140004bb0  sub     rsp, 48h
0x140004bb4  xor     eax, eax
0x140004bb6  mov     rdx, rcx; phHash
0x140004bb9  mov     [rsp+48h+dwFlags], eax; dwFlags
0x140004bbd  xor     r9d, r9d; cbHashObject
0x140004bc0  mov     [rsp+48h+cbSecret], eax; cbSecret
0x140004bc4  xor     r8d, r8d; pbHashObject
0x140004bc7  mov     ecx, 21h ; '!'; hAlgorithm
0x140004bcc  mov     [rsp+48h+pbSecret], rax; pbSecret
0x140004bd1  call    cs:__imp_BCryptCreateHash
0x140004bd8  nop     dword ptr [rax+rax+00h]
0x140004bdd  test    eax, eax
0x140004bdf  js      short loc_140004BE7
0x140004be1  add     rsp, 48h
0x140004be5  retn
0x140004be7  mov     ecx, 7
0x140004bec  int     29h; Win8: RtlFailFast(ecx)
0x140004bee  jmp     short loc_140004BE1
```
