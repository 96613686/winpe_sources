# CngRsa32Compat_MD5Update

- ea: `0x140004cd0`
- end: `0x140004cf9`
- name: `CngRsa32Compat_MD5Update`
- size: `41`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a4ec`
- `0x14000ec00`
- `0x14000eef8`
- `0x14000f340`
- `0x14002de70`
- `0x14002dfb0`
- `0x14002e050`

## callees

- `0x140004cd0`

## import_xrefs

- `cng!BCryptHashData` at `0x140004cda`
- `cng!BCryptHashData` at `0x140004cda`

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
0x140004cd0  sub     rsp, 28h
0x140004cd4  mov     rcx, [rcx]; hHash
0x140004cd7  xor     r9d, r9d; dwFlags
0x140004cda  call    cs:__imp_BCryptHashData
0x140004ce1  nop     dword ptr [rax+rax+00h]
0x140004ce6  test    eax, eax
0x140004ce8  js      short loc_140004CF0
0x140004cea  add     rsp, 28h
0x140004cee  retn
0x140004cf0  mov     ecx, 7
0x140004cf5  int     29h; Win8: RtlFailFast(ecx)
0x140004cf7  jmp     short loc_140004CEA
```
