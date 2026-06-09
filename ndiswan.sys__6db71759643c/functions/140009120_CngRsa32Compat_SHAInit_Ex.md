# CngRsa32Compat_SHAInit_Ex

- ea: `0x140009120`
- end: `0x14000916a`
- name: `CngRsa32Compat_SHAInit_Ex`
- size: `74`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026360`
- `0x140026464`
- `0x140033c30`

## callees

- `0x140009120`

## import_xrefs

- `cng!BCryptCreateHash` at `0x14000914d`
- `cng!BCryptCreateHash` at `0x14000914d`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAInit_Ex(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash(ghAlgSHA1, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x140009120  sub     rsp, 48h
0x140009124  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000912c  mov     rdx, rcx; phHash
0x14000912f  mov     rcx, cs:ghAlgSHA1; hAlgorithm
0x140009136  xor     r9d, r9d; cbHashObject
0x140009139  mov     [rsp+48h+cbSecret], 0; cbSecret
0x140009141  xor     r8d, r8d; pbHashObject
0x140009144  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000914d  call    cs:__imp_BCryptCreateHash
0x140009154  nop     dword ptr [rax+rax+00h]
0x140009159  test    eax, eax
0x14000915b  jns     short loc_140009164
0x14000915d  mov     ecx, 7
0x140009162  int     29h; Win8: RtlFailFast(ecx)
0x140009164  add     rsp, 48h
0x140009168  retn
```
