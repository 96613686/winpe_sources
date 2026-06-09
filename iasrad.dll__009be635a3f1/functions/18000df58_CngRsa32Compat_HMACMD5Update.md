# CngRsa32Compat_HMACMD5Update

- ea: `0x18000df58`
- end: `0x18000df78`
- name: `CngRsa32Compat_HMACMD5Update`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ddd0`
- `0x18000df80`
- `0x18001fcb0`
- `0x180020128`

## callees

- `0x18000df58`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000df62`
- `bcrypt!BCryptHashData` at `0x18000df62`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_HMACMD5Update(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
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
0x18000df58  sub     rsp, 28h
0x18000df5c  mov     rcx, [rcx]; hHash
0x18000df5f  xor     r9d, r9d; dwFlags
0x18000df62  call    cs:__imp_BCryptHashData
0x18000df68  test    eax, eax
0x18000df6a  jns     short loc_18000DF73
0x18000df6c  mov     ecx, 7
0x18000df71  int     29h; Win8: RtlFailFast(ecx)
0x18000df73  add     rsp, 28h
0x18000df77  retn
```
