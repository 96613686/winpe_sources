# CngRsa32Compat_SHA256Update

- ea: `0x14000ec20`
- end: `0x14000ec47`
- name: `CngRsa32Compat_SHA256Update`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002e1d0`

## callees

- `0x14000ec20`

## import_xrefs

- `cng!BCryptHashData` at `0x14000ec2a`
- `cng!BCryptHashData` at `0x14000ec2a`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHA256Update(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
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
0x14000ec20  sub     rsp, 28h
0x14000ec24  mov     rcx, [rcx]; hHash
0x14000ec27  xor     r9d, r9d; dwFlags
0x14000ec2a  call    cs:__imp_BCryptHashData
0x14000ec31  nop     dword ptr [rax+rax+00h]
0x14000ec36  test    eax, eax
0x14000ec38  jns     short loc_14000EC41
0x14000ec3a  mov     ecx, 7
0x14000ec3f  int     29h; Win8: RtlFailFast(ecx)
0x14000ec41  add     rsp, 28h
0x14000ec45  retn
```
