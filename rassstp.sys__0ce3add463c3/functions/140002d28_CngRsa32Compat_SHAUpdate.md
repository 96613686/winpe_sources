# CngRsa32Compat_SHAUpdate

- ea: `0x140002d28`
- end: `0x140002d4f`
- name: `CngRsa32Compat_SHAUpdate`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400100ac`

## callees

- `0x140002d28`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x140002d32`
- `ksecdd!BCryptHashData` at `0x140002d32`

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
0x140002d28  sub     rsp, 28h
0x140002d2c  mov     rcx, [rcx]; hHash
0x140002d2f  xor     r9d, r9d; dwFlags
0x140002d32  call    cs:__imp_BCryptHashData
0x140002d39  nop     dword ptr [rax+rax+00h]
0x140002d3e  test    eax, eax
0x140002d40  jns     short loc_140002D49
0x140002d42  mov     ecx, 7
0x140002d47  int     29h; Win8: RtlFailFast(ecx)
0x140002d49  add     rsp, 28h
0x140002d4d  retn
```
