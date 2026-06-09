# LoadMUILibraryW

- ea: `0x18005a1cc`
- end: `0x18005a642`
- name: `LoadMUILibraryW`
- size: `1142`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800685f8`

## callees

- `0x18002568c`
- `0x18005a1cc`
- `0x18005a648`
- `0x18006ed20`
- `0x1800a7f18`
- `0x1800a7f98`
- `0x1800a80a8`
- `0x1800a811c`
- `0x1800a8290`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18005a2c6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18005a2c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a4b5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a5fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a635`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a4b5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a5fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a635`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a21c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a621`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a21c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a621`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18005a2e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18005a2e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18005a3a4`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18005a3a4`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18005a280`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18005a280`

## string_xrefs

- `0x18005a20a`: `propsys.dll`
- `0x18005a268`: `propsys.dll`
- `0x18005a611`: `propsys.dll`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v4; // rdi
  WCHAR *v5; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  dword_1800F1BF8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(L"propsys.dll", 0, dword_1800F1BF8 & 0x20 | 2u);
  v4 = result;
  if ( !result )
    return 0;
  if ( (dword_1800F1BF8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"propsys.dll", 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v4);
    return 0;
  }
  if ( FilePart )
  {
    v5 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v5 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v4, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_1800F1BF8 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
          if ( MUIFile )
            goto LABEL_41;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v9 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
              if ( MUIFile )
                goto LABEL_41;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v9 != 1033 )
          {
            LookupLangID(1033, v20, v22, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart);
          if ( MUIFile )
            goto LABEL_41;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_1800F1BF8 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart)) != 0
          || v21[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v20, v22, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart)) != 0 )
        {
LABEL_41:
          FreeLibrary(v4);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v4 & 1) != 0 )
  {
    FreeLibrary(v4);
    if ( (GetOSType(v11, v10, v12) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v5, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v14, v13, v15);
      return LoadLibraryExW(L"propsys.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18005a1cc  push    rbp
0x18005a1ce  push    rbx
0x18005a1cf  push    rsi
0x18005a1d0  push    rdi
0x18005a1d1  push    r12
0x18005a1d3  push    r14
0x18005a1d5  push    r15
0x18005a1d7  lea     rbp, [rsp-370h]
0x18005a1df  sub     rsp, 470h
0x18005a1e6  mov     rax, cs:__security_cookie
0x18005a1ed  xor     rax, rsp
0x18005a1f0  mov     [rbp+3A0h+var_40], rax
0x18005a1f7  xor     r12d, r12d
0x18005a1fa  mov     [rsp+4A0h+FilePart], r12
0x18005a1ff  call    GetOSType
0x18005a204  mov     cs:dword_1800F1BF8, eax
0x18005a20a  lea     rcx, pszFullModuleName; "propsys.dll"
0x18005a211  and     eax, 20h
0x18005a214  xor     edx, edx; hFile
0x18005a216  or      eax, 2
0x18005a219  mov     r8d, eax; dwFlags
0x18005a21c  call    cs:__imp_LoadLibraryExW
0x18005a222  mov     rdi, rax
0x18005a225  test    rax, rax
0x18005a228  jz      loc_18005A63B
0x18005a22e  test    byte ptr cs:dword_1800F1BF8, 20h
0x18005a235  jz      short loc_18005A258
0x18005a237  mov     rcx, [rbp+3A0h+var_40]
0x18005a23e  xor     rcx, rsp; StackCookie
0x18005a241  call    __security_check_cookie
0x18005a246  add     rsp, 470h
0x18005a24d  pop     r15
0x18005a24f  pop     r14
0x18005a251  pop     r12
0x18005a253  pop     rdi
0x18005a254  pop     rsi
0x18005a255  pop     rbx
0x18005a256  pop     rbp
0x18005a257  retn
0x18005a258  lea     rax, [rsp+4A0h+FilePart]
0x18005a25d  mov     r9d, 104h; nBufferLength
0x18005a263  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x18005a268  lea     rdx, pszFullModuleName; "propsys.dll"
0x18005a26f  lea     rax, [rbp+3A0h+Buffer]
0x18005a276  xor     r8d, r8d; lpExtension
0x18005a279  xor     ecx, ecx; lpPath
0x18005a27b  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x18005a280  call    cs:__imp_SearchPathW
0x18005a286  test    eax, eax
0x18005a288  jz      loc_18005A632
0x18005a28e  mov     rcx, [rsp+4A0h+FilePart]
0x18005a293  test    rcx, rcx
0x18005a296  jnz     short loc_18005A2A9
0x18005a298  lea     rax, [rbp+3A0h+Buffer]
0x18005a29f  mov     rsi, r12
0x18005a2a2  mov     [rsp+4A0h+FilePart], rax
0x18005a2a7  jmp     short loc_18005A2B5
0x18005a2a9  lea     rsi, [rbp+3A0h+Buffer]
0x18005a2b0  mov     [rcx-2], r12w
0x18005a2b5  xor     r9d, r9d; wLanguage
0x18005a2b8  lea     rdx, Type; "MUI"
0x18005a2bf  mov     rcx, rdi; hModule
0x18005a2c2  lea     r8d, [r9+1]; lpName
0x18005a2c6  call    cs:__imp_FindResourceExW
0x18005a2cc  test    rax, rax
0x18005a2cf  jz      loc_18005A4A8
0x18005a2d5  mov     eax, cs:dword_1800F1BF8
0x18005a2db  test    al, 4
0x18005a2dd  jz      loc_18005A505
0x18005a2e3  mov     rbx, r12
0x18005a2e6  call    cs:__imp_GetUserDefaultUILanguage
0x18005a2ec  mov     r15d, 404h
0x18005a2f2  movzx   r14d, ax
0x18005a2f6  cmp     ax, r15w
0x18005a2fa  jnz     short loc_18005A305
0x18005a2fc  call    GetCHTLangauge
0x18005a301  movzx   r14d, ax
0x18005a305  lea     r9, [rbp+3A0h+var_3B0]
0x18005a309  movzx   ecx, r14w
0x18005a30d  lea     r8, [rbp+3A0h+var_300]
0x18005a314  lea     rdx, [rsp+4A0h+var_460]
0x18005a319  call    LookupLangID
0x18005a31e  test    eax, eax
0x18005a320  jz      loc_18005A5F0
0x18005a326  mov     r9, [rsp+4A0h+FilePart]
0x18005a32b  lea     r8, [rsp+4A0h+var_460]
0x18005a330  mov     rdx, rsi
0x18005a333  mov     rcx, rdi
0x18005a336  call    LoadMUIFile
0x18005a33b  mov     rbx, rax
0x18005a33e  test    rax, rax
0x18005a341  jnz     loc_18005A5F9
0x18005a347  mov     r9, [rsp+4A0h+FilePart]
0x18005a34c  lea     r8, [rbp+3A0h+var_300]
0x18005a353  mov     rdx, rsi
0x18005a356  mov     rcx, rdi
0x18005a359  call    LoadMUIFile
0x18005a35e  mov     rbx, rax
0x18005a361  test    rax, rax
0x18005a364  jnz     loc_18005A5F9
0x18005a36a  cmp     [rbp+3A0h+var_3B0], r12w
0x18005a36f  jz      short loc_18005A391
0x18005a371  mov     r9, [rsp+4A0h+FilePart]
0x18005a376  lea     r8, [rbp+3A0h+var_3B0]
0x18005a37a  mov     rdx, rsi
0x18005a37d  mov     rcx, rdi
0x18005a380  call    LoadMUIFile
0x18005a385  mov     rbx, rax
0x18005a388  test    rax, rax
0x18005a38b  jnz     loc_18005A5F9
0x18005a391  mov     eax, 0C04h
0x18005a396  cmp     r14w, ax
0x18005a39a  jnz     short loc_18005A3A4
0x18005a39c  mov     r14d, r15d
0x18005a39f  jmp     loc_18005A305
0x18005a3a4  call    cs:__imp_GetSystemDefaultUILanguage
0x18005a3aa  movzx   r15d, ax
0x18005a3ae  cmp     ax, r14w
0x18005a3b2  jz      loc_18005A443
0x18005a3b8  lea     r9, [rbp+3A0h+var_3B0]
0x18005a3bc  movzx   ecx, ax
0x18005a3bf  lea     r8, [rbp+3A0h+var_300]
0x18005a3c6  lea     rdx, [rsp+4A0h+var_460]
0x18005a3cb  call    LookupLangID
0x18005a3d0  test    eax, eax
0x18005a3d2  jz      loc_18005A4A8
0x18005a3d8  mov     r9, [rsp+4A0h+FilePart]
0x18005a3dd  lea     r8, [rsp+4A0h+var_460]
0x18005a3e2  mov     rdx, rsi
0x18005a3e5  mov     rcx, rdi
0x18005a3e8  call    LoadMUIFile
0x18005a3ed  mov     rbx, rax
0x18005a3f0  test    rax, rax
0x18005a3f3  jnz     loc_18005A5F9
0x18005a3f9  mov     r9, [rsp+4A0h+FilePart]
0x18005a3fe  lea     r8, [rbp+3A0h+var_300]
0x18005a405  mov     rdx, rsi
0x18005a408  mov     rcx, rdi
0x18005a40b  call    LoadMUIFile
0x18005a410  mov     rbx, rax
0x18005a413  test    rax, rax
0x18005a416  jnz     loc_18005A5F9
0x18005a41c  cmp     [rbp+3A0h+var_3B0], r12w
0x18005a421  jz      short loc_18005A443
0x18005a423  mov     r9, [rsp+4A0h+FilePart]
0x18005a428  lea     r8, [rbp+3A0h+var_3B0]
0x18005a42c  mov     rdx, rsi
0x18005a42f  mov     rcx, rdi
0x18005a432  call    LoadMUIFile
0x18005a437  mov     rbx, rax
0x18005a43a  test    rax, rax
0x18005a43d  jnz     loc_18005A5F9
0x18005a443  mov     ecx, 409h
0x18005a448  cmp     cx, r14w
0x18005a44c  jz      short loc_18005A489
0x18005a44e  cmp     cx, r15w
0x18005a452  jz      short loc_18005A489
0x18005a454  xor     r9d, r9d
0x18005a457  lea     r8, [rbp+3A0h+var_300]
0x18005a45e  lea     rdx, [rsp+4A0h+var_460]
0x18005a463  call    LookupLangID
0x18005a468  mov     r9, [rsp+4A0h+FilePart]
0x18005a46d  lea     r8, [rsp+4A0h+var_460]
0x18005a472  mov     rdx, rsi
0x18005a475  mov     rcx, rdi
0x18005a478  call    LoadMUIFile
0x18005a47d  mov     rbx, rax
0x18005a480  test    rax, rax
0x18005a483  jnz     loc_18005A5F9
0x18005a489  mov     r9, [rsp+4A0h+FilePart]
0x18005a48e  xor     r8d, r8d
0x18005a491  mov     rdx, rsi
0x18005a494  mov     rcx, rdi
0x18005a497  call    LoadMUIFile
0x18005a49c  mov     rbx, rax
0x18005a49f  test    rax, rax
0x18005a4a2  jnz     loc_18005A5F9
0x18005a4a8  test    dil, 1
0x18005a4ac  jz      loc_18005A62A
0x18005a4b2  mov     rcx, rdi; hLibModule
0x18005a4b5  call    cs:__imp_FreeLibrary
0x18005a4bb  call    GetOSType
0x18005a4c0  test    al, 38h
0x18005a4c2  jz      loc_18005A60A
0x18005a4c8  mov     rax, [rsp+4A0h+FilePart]
0x18005a4cd  lea     r8, aSS; "%s\\%s"
0x18005a4d4  mov     r9, rsi
0x18005a4d7  mov     [rsp+4A0h+lpBuffer], rax
0x18005a4dc  mov     edx, 104h; unsigned __int64
0x18005a4e1  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x18005a4e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a4ed  xor     r8d, r8d
0x18005a4f0  lea     rcx, [rbp+3A0h+Buffer]
0x18005a4f7  lea     edx, [r8+1]
0x18005a4fb  call    MapMUIFile
0x18005a500  jmp     loc_18005A627
0x18005a505  test    al, 3
0x18005a507  jz      short loc_18005A4A8
0x18005a509  call    GetInstallLanguage
0x18005a50e  lea     r9, [rbp+3A0h+var_3B0]
0x18005a512  movzx   ecx, ax
0x18005a515  lea     r8, [rbp+3A0h+var_300]
0x18005a51c  movzx   r14d, ax
0x18005a520  lea     rdx, [rsp+4A0h+var_460]
0x18005a525  call    LookupLangID
0x18005a52a  test    eax, eax
0x18005a52c  jz      loc_18005A4A8
0x18005a532  mov     r9, [rsp+4A0h+FilePart]
0x18005a537  lea     r8, [rsp+4A0h+var_460]
0x18005a53c  mov     rdx, rsi
0x18005a53f  mov     rcx, rdi
0x18005a542  call    LoadMUIFile
0x18005a547  mov     rbx, rax
0x18005a54a  test    rax, rax
0x18005a54d  jnz     loc_18005A5F9
0x18005a553  mov     r9, [rsp+4A0h+FilePart]
0x18005a558  lea     r8, [rbp+3A0h+var_300]
0x18005a55f  mov     rdx, rsi
0x18005a562  mov     rcx, rdi
0x18005a565  call    LoadMUIFile
0x18005a56a  mov     rbx, rax
0x18005a56d  test    rax, rax
0x18005a570  jnz     loc_18005A5F9
0x18005a576  cmp     [rbp+3A0h+var_3B0], r12w
0x18005a57b  jz      short loc_18005A599
0x18005a57d  mov     r9, [rsp+4A0h+FilePart]
0x18005a582  lea     r8, [rbp+3A0h+var_3B0]
0x18005a586  mov     rdx, rsi
0x18005a589  mov     rcx, rdi
0x18005a58c  call    LoadMUIFile
0x18005a591  mov     rbx, rax
0x18005a594  test    rax, rax
0x18005a597  jnz     short loc_18005A5F9
0x18005a599  mov     ecx, 409h
0x18005a59e  cmp     cx, r14w
0x18005a5a2  jz      short loc_18005A5D5
0x18005a5a4  xor     r9d, r9d
0x18005a5a7  lea     r8, [rbp+3A0h+var_300]
0x18005a5ae  lea     rdx, [rsp+4A0h+var_460]
0x18005a5b3  call    LookupLangID
0x18005a5b8  mov     r9, [rsp+4A0h+FilePart]
0x18005a5bd  lea     r8, [rsp+4A0h+var_460]
0x18005a5c2  mov     rdx, rsi
0x18005a5c5  mov     rcx, rdi
0x18005a5c8  call    LoadMUIFile
0x18005a5cd  mov     rbx, rax
0x18005a5d0  test    rax, rax
0x18005a5d3  jnz     short loc_18005A5F9
0x18005a5d5  mov     r9, [rsp+4A0h+FilePart]
0x18005a5da  xor     r8d, r8d
0x18005a5dd  mov     rdx, rsi
0x18005a5e0  mov     rcx, rdi
0x18005a5e3  call    LoadMUIFile
0x18005a5e8  mov     rbx, rax
0x18005a5eb  test    rax, rax
0x18005a5ee  jnz     short loc_18005A5F9
0x18005a5f0  test    rbx, rbx
0x18005a5f3  jz      loc_18005A4A8
0x18005a5f9  mov     rcx, rdi; hLibModule
0x18005a5fc  call    cs:__imp_FreeLibrary
0x18005a602  mov     rax, rbx
0x18005a605  jmp     loc_18005A237
0x18005a60a  call    GetOSType
0x18005a60f  test    al, 26h
0x18005a611  lea     rcx, pszFullModuleName; "propsys.dll"
0x18005a618  mov     r8d, r12d
0x18005a61b  setnz   r8b; dwFlags
0x18005a61f  xor     edx, edx; hFile
0x18005a621  call    cs:__imp_LoadLibraryExW
0x18005a627  mov     rdi, rax
0x18005a62a  mov     rax, rdi
0x18005a62d  jmp     loc_18005A237
0x18005a632  mov     rcx, rdi; hLibModule
0x18005a635  call    cs:__imp_FreeLibrary
0x18005a63b  xor     eax, eax
0x18005a63d  jmp     loc_18005A237
```
