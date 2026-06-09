# CngRsa32Compat_MD5Update

- ea: `0x18000fbc4`
- end: `0x18000fbe4`
- name: `CngRsa32Compat_MD5Update`
- size: `32`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *, UCHAR *, ULONG)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800028f0`
- `0x180003f00`
- `0x180005bd0`
- `0x180007af0`

## callees

- `0x18000fbc4`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000fbce`
- `bcrypt!BCryptHashData` at `0x18000fbce`

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
0x18000fbc4  sub     rsp, 28h
0x18000fbc8  mov     rcx, [rcx]; hHash
0x18000fbcb  xor     r9d, r9d; dwFlags
0x18000fbce  call    cs:__imp_BCryptHashData
0x18000fbd4  test    eax, eax
0x18000fbd6  jns     short loc_18000FBDF
0x18000fbd8  mov     ecx, 7
0x18000fbdd  int     29h; Win8: RtlFailFast(ecx)
0x18000fbdf  add     rsp, 28h
0x18000fbe3  retn
```
