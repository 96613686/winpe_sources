# CFontPreview::_FindPfb(ushort const *,ushort *,unsigned __int64)

- ea: `0x180024c30`
- end: `0x180024d84`
- name: `?_FindPfb@CFontPreview@@AEAAJPEBGPEAG_K@Z`
- size: `340`
- prototype: `__int64 __fastcall(CFontPreview *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180024b98`

## callees

- `0x180006624`
- `0x180006668`
- `0x180024c30`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180024cc8`
- `SHLWAPI!PathFindFileNameW` at `0x180024cc8`
- `SHLWAPI!PathAppendW` at `0x180024d18`
- `SHLWAPI!PathAppendW` at `0x180024d18`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180024cd6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180024d06`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180024cd6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180024d06`
- `SHLWAPI!PathFileExistsW` at `0x180024cb2`
- `SHLWAPI!PathFileExistsW` at `0x180024d39`
- `SHLWAPI!PathFileExistsW` at `0x180024cb2`
- `SHLWAPI!PathFileExistsW` at `0x180024d39`
- `SHLWAPI!PathRenameExtensionW` at `0x180024ca7`
- `SHLWAPI!PathRenameExtensionW` at `0x180024d2e`
- `SHLWAPI!PathRenameExtensionW` at `0x180024ca7`
- `SHLWAPI!PathRenameExtensionW` at `0x180024d2e`

## pseudocode

```c
__int64 __fastcall CFontPreview::_FindPfb(CFontPreview *this, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v5; // ebx
  const WCHAR *FileNameW; // rdi
  unsigned int v7; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-E0h] BYREF

  memset_0(pszPath, 0, 0x208u);
  *a3 = 0;
  v5 = StringCchCopyW(pszPath, 0x104u, a2);
  if ( v5 >= 0 )
  {
    PathRenameExtensionW(pszPath, L".PFB");
    if ( PathFileExistsW(pszPath) )
    {
      if ( !v5 )
        return (unsigned int)StringCchCopyW(a3, 0x104u, pszPath);
    }
    else
    {
      v5 = -2147467259;
      FileNameW = PathFindFileNameW(a2);
      if ( PathRemoveFileSpecW(pszPath) )
      {
        if ( !pszPath[0] )
        {
          v7 = StringCchPrintfW(pszPath, 0x104u, L"..\\%s", FileNameW);
          if ( v7 )
            return v7;
          goto LABEL_9;
        }
        if ( PathRemoveFileSpecW(pszPath) && PathAppendW(pszPath, FileNameW) )
        {
LABEL_9:
          PathRenameExtensionW(pszPath, L".PFB");
          if ( !PathFileExistsW(pszPath) )
            return (unsigned int)v5;
          return (unsigned int)StringCchCopyW(a3, 0x104u, pszPath);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024c30  mov     [rsp-8+arg_0], rbx
0x180024c35  mov     [rsp-8+arg_18], rsi
0x180024c3a  push    rbp
0x180024c3b  push    rdi
0x180024c3c  push    r14
0x180024c3e  lea     rbp, [rsp-140h]
0x180024c46  sub     rsp, 240h
0x180024c4d  mov     rax, cs:__security_cookie
0x180024c54  xor     rax, rsp
0x180024c57  mov     [rbp+150h+var_20], rax
0x180024c5e  mov     rsi, r8
0x180024c61  lea     rcx, [rsp+250h+pszPath]; void *
0x180024c66  mov     rdi, rdx
0x180024c69  mov     r8d, 208h; Size
0x180024c6f  xor     edx, edx; Val
0x180024c71  call    memset_0
0x180024c76  xor     eax, eax
0x180024c78  lea     rcx, [rsp+250h+pszPath]; unsigned __int16 *
0x180024c7d  mov     r14d, 104h
0x180024c83  mov     [rsi], ax
0x180024c86  mov     edx, r14d; unsigned __int64
0x180024c89  mov     r8, rdi; unsigned __int16 *
0x180024c8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024c91  mov     ebx, eax
0x180024c93  test    eax, eax
0x180024c95  js      loc_180024D5B
0x180024c9b  lea     rdx, pszExt; ".PFB"
0x180024ca2  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024ca7  call    cs:__imp_PathRenameExtensionW
0x180024cad  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024cb2  call    cs:__imp_PathFileExistsW
0x180024cb8  test    eax, eax
0x180024cba  jnz     loc_180024D45
0x180024cc0  mov     rcx, rdi; pszPath
0x180024cc3  mov     ebx, 80004005h
0x180024cc8  call    cs:__imp_PathFindFileNameW
0x180024cce  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024cd3  mov     rdi, rax
0x180024cd6  call    cs:__imp_PathRemoveFileSpecW
0x180024cdc  test    eax, eax
0x180024cde  jz      short loc_180024D5B
0x180024ce0  xor     ecx, ecx
0x180024ce2  cmp     cx, [rsp+250h+pszPath]
0x180024ce7  lea     rcx, [rsp+250h+pszPath]; unsigned __int16 *
0x180024cec  jnz     short loc_180024D06
0x180024cee  mov     r9, rdi
0x180024cf1  lea     r8, aS_0; "..\\%s"
0x180024cf8  mov     edx, r14d; unsigned __int64
0x180024cfb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024d00  test    eax, eax
0x180024d02  jz      short loc_180024D22
0x180024d04  jmp     short loc_180024D59
0x180024d06  call    cs:__imp_PathRemoveFileSpecW
0x180024d0c  test    eax, eax
0x180024d0e  jz      short loc_180024D5B
0x180024d10  mov     rdx, rdi; pszMore
0x180024d13  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024d18  call    cs:__imp_PathAppendW
0x180024d1e  test    eax, eax
0x180024d20  jz      short loc_180024D5B
0x180024d22  lea     rdx, pszExt; ".PFB"
0x180024d29  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024d2e  call    cs:__imp_PathRenameExtensionW
0x180024d34  lea     rcx, [rsp+250h+pszPath]; pszPath
0x180024d39  call    cs:__imp_PathFileExistsW
0x180024d3f  test    eax, eax
0x180024d41  jnz     short loc_180024D49
0x180024d43  jmp     short loc_180024D5B
0x180024d45  test    ebx, ebx
0x180024d47  jnz     short loc_180024D5B
0x180024d49  lea     r8, [rsp+250h+pszPath]; unsigned __int16 *
0x180024d4e  mov     rdx, r14; unsigned __int64
0x180024d51  mov     rcx, rsi; unsigned __int16 *
0x180024d54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024d59  mov     ebx, eax
0x180024d5b  mov     eax, ebx
0x180024d5d  mov     rcx, [rbp+150h+var_20]
0x180024d64  xor     rcx, rsp; StackCookie
0x180024d67  call    __security_check_cookie
0x180024d6c  lea     r11, [rsp+250h+var_10]
0x180024d74  mov     rbx, [r11+20h]
0x180024d78  mov     rsi, [r11+38h]
0x180024d7c  mov     rsp, r11
0x180024d7f  pop     r14
0x180024d81  pop     rdi
0x180024d82  pop     rbp
0x180024d83  retn
```
