# CngRsa32Compat_SHAUpdate

- ea: `0x18000de00`
- end: `0x18000de22`
- name: `CngRsa32Compat_SHAUpdate`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ab6c`
- `0x18001b3ec`
- `0x18001c570`

## callees

- `0x18000de00`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000de0a`
- `bcrypt!BCryptHashData` at `0x18000de0a`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_SHAUpdate(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
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
0x18000de00  sub     rsp, 28h
0x18000de04  mov     rcx, [rcx]; hHash
0x18000de07  xor     r9d, r9d; dwFlags
0x18000de0a  call    cs:__imp_BCryptHashData
0x18000de10  test    eax, eax
0x18000de12  js      short loc_18000DE19
0x18000de14  add     rsp, 28h
0x18000de18  retn
0x18000de19  mov     ecx, 7
0x18000de1e  int     29h; Win8: RtlFailFast(ecx)
0x18000de20  jmp     short loc_18000DE14
```
