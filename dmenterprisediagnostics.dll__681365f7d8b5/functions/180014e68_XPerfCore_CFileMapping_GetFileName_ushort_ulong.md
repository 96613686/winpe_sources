# XPerfCore::CFileMapping::GetFileName(ushort *,ulong &)

- ea: `0x180014e68`
- end: `0x180014ec5`
- name: `?GetFileName@CFileMapping@XPerfCore@@QEAAKPEAGAEAK@Z`
- size: `93`
- prototype: `unsigned int __fastcall(XPerfCore::CFileMapping *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800129cc`

## callees

- `0x180014e68`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014e8f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014eab`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014e8f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014eab`

## pseudocode

```c
__int64 __fastcall XPerfCore::CFileMapping::GetFileName(void **this, unsigned __int16 *a2, unsigned int *a3)
{
  void *v3; // rcx
  DWORD v6; // r8d
  DWORD FinalPathNameByHandleW; // eax

  v3 = *this;
  if ( v3 == (void *)-1LL )
    return 87;
  if ( a2 && (v6 = *a3) != 0 )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(v3, a2, v6, 0);
    if ( FinalPathNameByHandleW < *a3 )
      return 0;
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(v3, 0, 0, 0);
  }
  *a3 = FinalPathNameByHandleW;
  return 122;
}

```

## disassembly

```asm
0x180014e68  push    rbx
0x180014e6a  sub     rsp, 20h
0x180014e6e  mov     rcx, [rcx]; hFile
0x180014e71  mov     rbx, r8
0x180014e74  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180014e78  jnz     short loc_180014E7F
0x180014e7a  lea     eax, [rcx+58h]
0x180014e7d  jmp     short loc_180014EBE
0x180014e7f  test    rdx, rdx
0x180014e82  jz      short loc_180014EA3
0x180014e84  mov     r8d, [r8]; cchFilePath
0x180014e87  test    r8d, r8d
0x180014e8a  jz      short loc_180014EA3
0x180014e8c  xor     r9d, r9d; dwFlags
0x180014e8f  call    cs:__imp_GetFinalPathNameByHandleW
0x180014e96  nop     dword ptr [rax+rax+00h]
0x180014e9b  cmp     eax, [rbx]
0x180014e9d  jnb     short loc_180014EB7
0x180014e9f  xor     eax, eax
0x180014ea1  jmp     short loc_180014EBE
0x180014ea3  xor     r9d, r9d; dwFlags
0x180014ea6  xor     r8d, r8d; cchFilePath
0x180014ea9  xor     edx, edx; lpszFilePath
0x180014eab  call    cs:__imp_GetFinalPathNameByHandleW
0x180014eb2  nop     dword ptr [rax+rax+00h]
0x180014eb7  mov     [rbx], eax
0x180014eb9  mov     eax, 7Ah ; 'z'
0x180014ebe  add     rsp, 20h
0x180014ec2  pop     rbx
0x180014ec3  retn
```
