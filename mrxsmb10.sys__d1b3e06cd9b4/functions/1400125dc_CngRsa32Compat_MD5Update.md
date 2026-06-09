# CngRsa32Compat_MD5Update

- ea: `0x1400125dc`
- end: `0x140012603`
- name: `CngRsa32Compat_MD5Update`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001260c`
- `0x1400126a4`
- `0x14003ec3c`
- `0x14003edd4`

## callees

- `0x1400125dc`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x1400125e6`
- `ksecdd!BCryptHashData` at `0x1400125e6`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Update(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
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
0x1400125dc  sub     rsp, 28h
0x1400125e0  mov     rcx, [rcx]; hHash
0x1400125e3  xor     r9d, r9d; dwFlags
0x1400125e6  call    cs:__imp_BCryptHashData
0x1400125ed  nop     dword ptr [rax+rax+00h]
0x1400125f2  test    eax, eax
0x1400125f4  jns     short loc_1400125FD
0x1400125f6  mov     ecx, 7
0x1400125fb  int     29h; Win8: RtlFailFast(ecx)
0x1400125fd  add     rsp, 28h
0x140012601  retn
```
