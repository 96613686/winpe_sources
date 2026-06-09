# PathMakeFilenameUnique(ushort *,uint,int)

- ea: `0x180013a38`
- end: `0x180013c17`
- name: `?PathMakeFilenameUnique@@YAJPEAGIH@Z`
- size: `479`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180007ab0`
- `0x1800087d0`

## callees

- `0x180006624`
- `0x180006668`
- `0x180013a38`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `msvcrt!iswxdigit` at `0x180013b17`
- `msvcrt!iswxdigit` at `0x180013b17`
- `SHLWAPI!PathFindFileNameW` at `0x180013ab9`
- `SHLWAPI!PathFindFileNameW` at `0x180013ab9`
- `SHLWAPI!PathRemoveExtensionW` at `0x180013ad9`
- `SHLWAPI!PathRemoveExtensionW` at `0x180013ad9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ab0`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ab0`
- `SHLWAPI!PathFindExtensionW` at `0x180013ae2`
- `SHLWAPI!PathFindExtensionW` at `0x180013ae2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013bc0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013bc0`
- `KERNEL32!lstrlenW` at `0x180013b04`
- `KERNEL32!lstrlenW` at `0x180013b04`

## pseudocode

```c
__int64 __fastcall PathMakeFilenameUnique(unsigned __int16 *a1, __int64 a2, int a3)
{
  const unsigned __int16 *FileNameW; // rax
  const unsigned __int16 *ExtensionW; // rax
  wint_t *i; // rbx
  unsigned __int16 v9[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v10; // [rsp+50h] [rbp-B0h]
  __int64 v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[2]; // [rsp+6Eh] [rbp-92h] BYREF
  WCHAR String[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v14[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszPath[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR FileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(String, 0, 0x208u);
  memset_0(v14, 0, 0x208u);
  StringCchCopyW(pszPath, 0x104u, a1);
  PathRemoveFileSpecW(pszPath);
  FileNameW = PathFindFileNameW(a1);
  if ( FileNameW )
  {
    StringCchCopyW(String, 0x104u, FileNameW);
    PathRemoveExtensionW(String);
    ExtensionW = PathFindExtensionW(a1);
    if ( ExtensionW )
      StringCchCopyW(v14, 0x104u, ExtensionW);
    for ( i = (wint_t *)&v12[2 * lstrlenW(String)]; i > String; --i )
    {
      if ( !iswxdigit(*i) )
      {
        if ( *i == 95 )
          *i = 0;
        break;
      }
    }
  }
  if ( !String[0] )
    return 2147500037LL;
  v11 = 0;
  *(_OWORD *)v9 = 0;
  v10 = 0;
  while ( 1 )
  {
    if ( a3 >= 0 )
      StringCchPrintfW(v9, 0x14u, L"_%X", (unsigned int)a3);
    StringCchPrintfW(FileName, 0x104u, L"%s\\%s%s%s", pszPath, String, v9, v14);
    if ( GetFileAttributesW(FileName) == -1 )
      break;
    if ( (unsigned int)++a3 >= 0xFF )
      return 2147500037LL;
  }
  StringCchCopyW(a1, 0x104u, FileName);
  return 0;
}

```

## disassembly

```asm
0x180013a38  mov     [rsp-8+arg_8], rbx
0x180013a3d  mov     [rsp-8+arg_18], rsi
0x180013a42  push    rbp
0x180013a43  push    rdi
0x180013a44  push    r14
0x180013a46  lea     rbp, [rsp-7C0h]
0x180013a4e  sub     rsp, 8C0h
0x180013a55  mov     rax, cs:__security_cookie
0x180013a5c  xor     rax, rsp
0x180013a5f  mov     [rbp+7D0h+var_20], rax
0x180013a66  mov     edi, r8d
0x180013a69  mov     rsi, rcx
0x180013a6c  mov     ebx, 208h
0x180013a71  lea     rcx, [rsp+8D0h+String]; void *
0x180013a76  mov     r8d, ebx; Size
0x180013a79  xor     edx, edx; Val
0x180013a7b  call    memset_0
0x180013a80  mov     r8d, ebx; Size
0x180013a83  lea     rcx, [rbp+7D0h+var_650]; void *
0x180013a8a  xor     edx, edx; Val
0x180013a8c  call    memset_0
0x180013a91  mov     r14d, 104h
0x180013a97  lea     rcx, [rbp+7D0h+pszPath]; unsigned __int16 *
0x180013a9e  mov     edx, r14d; unsigned __int64
0x180013aa1  mov     r8, rsi; unsigned __int16 *
0x180013aa4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013aa9  lea     rcx, [rbp+7D0h+pszPath]; pszPath
0x180013ab0  call    cs:__imp_PathRemoveFileSpecW
0x180013ab6  mov     rcx, rsi; pszPath
0x180013ab9  call    cs:__imp_PathFindFileNameW
0x180013abf  test    rax, rax
0x180013ac2  jz      short loc_180013B40
0x180013ac4  mov     r8, rax; unsigned __int16 *
0x180013ac7  lea     rcx, [rsp+8D0h+String]; unsigned __int16 *
0x180013acc  mov     edx, r14d; unsigned __int64
0x180013acf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013ad4  lea     rcx, [rsp+8D0h+String]; pszPath
0x180013ad9  call    cs:__imp_PathRemoveExtensionW
0x180013adf  mov     rcx, rsi; pszPath
0x180013ae2  call    cs:__imp_PathFindExtensionW
0x180013ae8  test    rax, rax
0x180013aeb  jz      short loc_180013AFF
0x180013aed  mov     r8, rax; unsigned __int16 *
0x180013af0  lea     rcx, [rbp+7D0h+var_650]; unsigned __int16 *
0x180013af7  mov     edx, r14d; unsigned __int64
0x180013afa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013aff  lea     rcx, [rsp+8D0h+String]; lpString
0x180013b04  call    cs:__imp_lstrlenW
0x180013b0a  movsxd  rcx, eax
0x180013b0d  lea     rbx, [rsp+rcx*2+8D0h+var_862]
0x180013b12  jmp     short loc_180013B25
0x180013b14  movzx   ecx, word ptr [rbx]; C
0x180013b17  call    cs:__imp_iswxdigit
0x180013b1d  test    eax, eax
0x180013b1f  jz      short loc_180013B31
0x180013b21  sub     rbx, 2
0x180013b25  lea     rax, [rsp+8D0h+String]
0x180013b2a  cmp     rbx, rax
0x180013b2d  ja      short loc_180013B14
0x180013b2f  jmp     short loc_180013B40
0x180013b31  mov     eax, 5Fh ; '_'
0x180013b36  cmp     ax, [rbx]
0x180013b39  jnz     short loc_180013B40
0x180013b3b  xor     eax, eax
0x180013b3d  mov     [rbx], ax
0x180013b40  xor     eax, eax
0x180013b42  cmp     ax, [rsp+8D0h+String]
0x180013b47  jz      loc_180013BD5
0x180013b4d  xorps   xmm0, xmm0
0x180013b50  mov     [rsp+8D0h+var_870], rax
0x180013b55  movups  xmmword ptr [rsp+8D0h+var_890], xmm0
0x180013b5a  movups  [rsp+8D0h+var_880], xmm0
0x180013b5f  test    edi, edi
0x180013b61  js      short loc_180013B7C
0x180013b63  mov     r9d, edi
0x180013b66  lea     r8, asc_180037E70; "_%X"
0x180013b6d  mov     edx, 14h; unsigned __int64
0x180013b72  lea     rcx, [rsp+8D0h+var_890]; unsigned __int16 *
0x180013b77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013b7c  lea     rax, [rbp+7D0h+var_650]
0x180013b83  mov     rdx, r14; unsigned __int64
0x180013b86  mov     [rsp+8D0h+var_8A0], rax
0x180013b8b  lea     r9, [rbp+7D0h+pszPath]
0x180013b92  lea     rax, [rsp+8D0h+var_890]
0x180013b97  mov     [rsp+8D0h+var_8A8], rax
0x180013b9c  lea     r8, aSSSS; "%s\\%s%s%s"
0x180013ba3  lea     rax, [rsp+8D0h+String]
0x180013ba8  lea     rcx, [rbp+7D0h+FileName]; unsigned __int16 *
0x180013baf  mov     [rsp+8D0h+var_8B0], rax
0x180013bb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013bb9  lea     rcx, [rbp+7D0h+FileName]; lpFileName
0x180013bc0  call    cs:__imp_GetFileAttributesW
0x180013bc6  cmp     eax, 0FFFFFFFFh
0x180013bc9  jz      short loc_180013C01
0x180013bcb  inc     edi
0x180013bcd  cmp     edi, 0FFh
0x180013bd3  jb      short loc_180013B5F
0x180013bd5  mov     eax, 80004005h
0x180013bda  mov     rcx, [rbp+7D0h+var_20]
0x180013be1  xor     rcx, rsp; StackCookie
0x180013be4  call    __security_check_cookie
0x180013be9  lea     r11, [rsp+8D0h+var_10]
0x180013bf1  mov     rbx, [r11+28h]
0x180013bf5  mov     rsi, [r11+38h]
0x180013bf9  mov     rsp, r11
0x180013bfc  pop     r14
0x180013bfe  pop     rdi
0x180013bff  pop     rbp
0x180013c00  retn
0x180013c01  lea     r8, [rbp+7D0h+FileName]; unsigned __int16 *
0x180013c08  mov     rdx, r14; unsigned __int64
0x180013c0b  mov     rcx, rsi; unsigned __int16 *
0x180013c0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013c13  xor     eax, eax
0x180013c15  jmp     short loc_180013BDA
```
