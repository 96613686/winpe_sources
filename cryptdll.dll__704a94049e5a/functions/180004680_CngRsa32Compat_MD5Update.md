# CngRsa32Compat_MD5Update

- ea: `0x180004680`
- end: `0x1800046a0`
- name: `CngRsa32Compat_MD5Update`
- size: `32`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800047b0`
- `0x180006710`
- `0x180006850`
- `0x180006b18`
- `0x18000750c`

## callees

- `0x180004680`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000468a`
- `bcrypt!BCryptHashData` at `0x18000468a`

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
0x180004680  sub     rsp, 28h
0x180004684  mov     rcx, [rcx]; hHash
0x180004687  xor     r9d, r9d; dwFlags
0x18000468a  call    cs:__imp_BCryptHashData
0x180004690  test    eax, eax
0x180004692  jns     short loc_18000469B
0x180004694  mov     ecx, 7
0x180004699  int     29h; Win8: RtlFailFast(ecx)
0x18000469b  add     rsp, 28h
0x18000469f  retn
```
