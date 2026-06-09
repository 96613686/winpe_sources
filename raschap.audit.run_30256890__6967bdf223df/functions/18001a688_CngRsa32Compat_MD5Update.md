# CngRsa32Compat_MD5Update

- ea: `0x18001a688`
- end: `0x18001a6a8`
- name: `CngRsa32Compat_MD5Update`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008cf0`

## callees

- `0x18001a688`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001a692`
- `bcrypt!BCryptHashData` at `0x18001a692`

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
0x18001a688  sub     rsp, 28h
0x18001a68c  mov     rcx, [rcx]; hHash
0x18001a68f  xor     r9d, r9d; dwFlags
0x18001a692  call    cs:__imp_BCryptHashData
0x18001a698  test    eax, eax
0x18001a69a  jns     short loc_18001A6A3
0x18001a69c  mov     ecx, 7
0x18001a6a1  int     29h; Win8: RtlFailFast(ecx)
0x18001a6a3  add     rsp, 28h
0x18001a6a7  retn
```
