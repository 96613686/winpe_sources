# CngRsa32Compat_MD5Update

- ea: `0x18001fae4`
- end: `0x18001fb04`
- name: `CngRsa32Compat_MD5Update`
- size: `32`
- prototype: `NTSTATUS __fastcall(BCRYPT_HASH_HANDLE *, UCHAR *, ULONG)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001c80`
- `0x180002810`
- `0x18000335c`
- `0x180006d40`
- `0x180007a40`

## callees

- `0x18001fae4`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001faee`
- `bcrypt!BCryptHashData` at `0x18001faee`

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
0x18001fae4  sub     rsp, 28h
0x18001fae8  mov     rcx, [rcx]; hHash
0x18001faeb  xor     r9d, r9d; dwFlags
0x18001faee  call    cs:__imp_BCryptHashData
0x18001faf4  test    eax, eax
0x18001faf6  jns     short loc_18001FAFF
0x18001faf8  mov     ecx, 7
0x18001fafd  int     29h; Win8: RtlFailFast(ecx)
0x18001faff  add     rsp, 28h
0x18001fb03  retn
```
