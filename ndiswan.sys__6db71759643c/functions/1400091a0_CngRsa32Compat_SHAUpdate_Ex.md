# CngRsa32Compat_SHAUpdate_Ex

- ea: `0x1400091a0`
- end: `0x1400091c7`
- name: `CngRsa32Compat_SHAUpdate_Ex`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140026360`
- `0x140026464`

## callees

- `0x1400091a0`

## import_xrefs

- `cng!BCryptHashData` at `0x1400091aa`
- `cng!BCryptHashData` at `0x1400091aa`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAUpdate_Ex(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
{
  NTSTATUS result; // eax

  result = BCryptHashData(*a1, a2, a3, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x1400091a0  sub     rsp, 28h
0x1400091a4  mov     rcx, [rcx]; hHash
0x1400091a7  xor     r9d, r9d; dwFlags
0x1400091aa  call    cs:__imp_BCryptHashData
0x1400091b1  nop     dword ptr [rax+rax+00h]
0x1400091b6  test    eax, eax
0x1400091b8  jns     short loc_1400091C1
0x1400091ba  mov     ecx, 7
0x1400091bf  int     29h; Win8: RtlFailFast(ecx)
0x1400091c1  add     rsp, 28h
0x1400091c5  retn
```
