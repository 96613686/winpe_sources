# LoadMUILibraryW

- ea: `0x180038d50`
- end: `0x1800391c3`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c590`

## callees

- `0x18000ba10`
- `0x18003866c`
- `0x1800386ec`
- `0x1800387fc`
- `0x180038924`
- `0x180038998`
- `0x180038b10`
- `0x180038d50`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038daa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039187`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038daa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039187`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180038e33`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180038e33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039022`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039169`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039198`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039022`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039169`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039198`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180038ded`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180038ded`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180038f11`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180038f11`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180038e53`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180038e53`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rdi
  WCHAR *v6; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_18006B2D8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_18006B2D8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_18006B2D8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v5);
    return 0;
  }
  if ( FilePart )
  {
    v6 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v6 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v5, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_18006B2D8 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
          if ( MUIFile )
            goto LABEL_42;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_42;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
            if ( MUIFile )
              goto LABEL_42;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
              if ( MUIFile )
                goto LABEL_42;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v10 != 1033 )
          {
            LookupLangID(1033, v21, v23, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_42;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
          if ( MUIFile )
            goto LABEL_42;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_18006B2D8 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart)) != 0
          || v22[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v21, v23, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart)) != 0 )
        {
LABEL_42:
          FreeLibrary(v5);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v5 & 1) != 0 )
  {
    FreeLibrary(v5);
    if ( (GetOSType(v12, v11, v13) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v15, v14, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180038d50  push    rbp
0x180038d52  push    rbx
0x180038d53  push    rsi
0x180038d54  push    rdi
0x180038d55  push    r12
0x180038d57  push    r13
0x180038d59  push    r14
0x180038d5b  push    r15
0x180038d5d  lea     rbp, [rsp-378h]
0x180038d65  sub     rsp, 478h
0x180038d6c  mov     rax, cs:__security_cookie
0x180038d73  xor     rax, rsp
0x180038d76  mov     [rbp+3B0h+var_50], rax
0x180038d7d  xor     r13d, r13d
0x180038d80  mov     r12, rcx
0x180038d83  mov     [rsp+4B0h+FilePart], r13
0x180038d88  test    rcx, rcx
0x180038d8b  jz      loc_18003919E
0x180038d91  call    GetOSType
0x180038d96  mov     cs:dword_18006B2D8, eax
0x180038d9c  xor     edx, edx; hFile
0x180038d9e  and     eax, 20h
0x180038da1  mov     rcx, r12; lpLibFileName
0x180038da4  or      eax, 2
0x180038da7  mov     r8d, eax; dwFlags
0x180038daa  call    cs:__imp_LoadLibraryExW
0x180038db0  mov     rdi, rax
0x180038db3  test    rax, rax
0x180038db6  jz      loc_18003919E
0x180038dbc  test    byte ptr cs:dword_18006B2D8, 20h
0x180038dc3  jnz     loc_1800391A0
0x180038dc9  lea     rax, [rsp+4B0h+FilePart]
0x180038dce  mov     r9d, 104h; nBufferLength
0x180038dd4  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x180038dd9  xor     r8d, r8d; lpExtension
0x180038ddc  lea     rax, [rbp+3B0h+Buffer]
0x180038de3  mov     rdx, r12; lpFileName
0x180038de6  xor     ecx, ecx; lpPath
0x180038de8  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180038ded  call    cs:__imp_SearchPathW
0x180038df3  test    eax, eax
0x180038df5  jz      loc_180039195
0x180038dfb  mov     rcx, [rsp+4B0h+FilePart]
0x180038e00  test    rcx, rcx
0x180038e03  jnz     short loc_180038E16
0x180038e05  lea     rax, [rbp+3B0h+Buffer]
0x180038e0c  mov     esi, r13d
0x180038e0f  mov     [rsp+4B0h+FilePart], rax
0x180038e14  jmp     short loc_180038E22
0x180038e16  lea     rsi, [rbp+3B0h+Buffer]
0x180038e1d  mov     [rcx-2], r13w
0x180038e22  xor     r9d, r9d; wLanguage
0x180038e25  lea     rdx, Type; "MUI"
0x180038e2c  mov     rcx, rdi; hModule
0x180038e2f  lea     r8d, [r9+1]; lpName
0x180038e33  call    cs:__imp_FindResourceExW
0x180038e39  test    rax, rax
0x180038e3c  jz      loc_180039015
0x180038e42  mov     eax, cs:dword_18006B2D8
0x180038e48  test    al, 4
0x180038e4a  jz      loc_180039072
0x180038e50  mov     rbx, r13
0x180038e53  call    cs:__imp_GetUserDefaultUILanguage
0x180038e59  mov     r15d, 404h
0x180038e5f  movzx   r14d, ax
0x180038e63  cmp     ax, r15w
0x180038e67  jnz     short loc_180038E72
0x180038e69  call    GetCHTLangauge
0x180038e6e  movzx   r14d, ax
0x180038e72  lea     r9, [rbp+3B0h+var_3C0]
0x180038e76  movzx   ecx, r14w
0x180038e7a  lea     r8, [rbp+3B0h+var_310]
0x180038e81  lea     rdx, [rsp+4B0h+var_470]
0x180038e86  call    LookupLangID
0x180038e8b  test    eax, eax
0x180038e8d  jz      loc_18003915D
0x180038e93  mov     r9, [rsp+4B0h+FilePart]
0x180038e98  lea     r8, [rsp+4B0h+var_470]
0x180038e9d  mov     rdx, rsi
0x180038ea0  mov     rcx, rdi
0x180038ea3  call    LoadMUIFile
0x180038ea8  mov     rbx, rax
0x180038eab  test    rax, rax
0x180038eae  jnz     loc_180039166
0x180038eb4  mov     r9, [rsp+4B0h+FilePart]
0x180038eb9  lea     r8, [rbp+3B0h+var_310]
0x180038ec0  mov     rdx, rsi
0x180038ec3  mov     rcx, rdi
0x180038ec6  call    LoadMUIFile
0x180038ecb  mov     rbx, rax
0x180038ece  test    rax, rax
0x180038ed1  jnz     loc_180039166
0x180038ed7  cmp     [rbp+3B0h+var_3C0], r13w
0x180038edc  jz      short loc_180038EFE
0x180038ede  mov     r9, [rsp+4B0h+FilePart]
0x180038ee3  lea     r8, [rbp+3B0h+var_3C0]
0x180038ee7  mov     rdx, rsi
0x180038eea  mov     rcx, rdi
0x180038eed  call    LoadMUIFile
0x180038ef2  mov     rbx, rax
0x180038ef5  test    rax, rax
0x180038ef8  jnz     loc_180039166
0x180038efe  mov     eax, 0C04h
0x180038f03  cmp     r14w, ax
0x180038f07  jnz     short loc_180038F11
0x180038f09  mov     r14d, r15d
0x180038f0c  jmp     loc_180038E72
0x180038f11  call    cs:__imp_GetSystemDefaultUILanguage
0x180038f17  movzx   r15d, ax
0x180038f1b  cmp     ax, r14w
0x180038f1f  jz      loc_180038FB0
0x180038f25  lea     r9, [rbp+3B0h+var_3C0]
0x180038f29  movzx   ecx, ax
0x180038f2c  lea     r8, [rbp+3B0h+var_310]
0x180038f33  lea     rdx, [rsp+4B0h+var_470]
0x180038f38  call    LookupLangID
0x180038f3d  test    eax, eax
0x180038f3f  jz      loc_180039015
0x180038f45  mov     r9, [rsp+4B0h+FilePart]
0x180038f4a  lea     r8, [rsp+4B0h+var_470]
0x180038f4f  mov     rdx, rsi
0x180038f52  mov     rcx, rdi
0x180038f55  call    LoadMUIFile
0x180038f5a  mov     rbx, rax
0x180038f5d  test    rax, rax
0x180038f60  jnz     loc_180039166
0x180038f66  mov     r9, [rsp+4B0h+FilePart]
0x180038f6b  lea     r8, [rbp+3B0h+var_310]
0x180038f72  mov     rdx, rsi
0x180038f75  mov     rcx, rdi
0x180038f78  call    LoadMUIFile
0x180038f7d  mov     rbx, rax
0x180038f80  test    rax, rax
0x180038f83  jnz     loc_180039166
0x180038f89  cmp     [rbp+3B0h+var_3C0], r13w
0x180038f8e  jz      short loc_180038FB0
0x180038f90  mov     r9, [rsp+4B0h+FilePart]
0x180038f95  lea     r8, [rbp+3B0h+var_3C0]
0x180038f99  mov     rdx, rsi
0x180038f9c  mov     rcx, rdi
0x180038f9f  call    LoadMUIFile
0x180038fa4  mov     rbx, rax
0x180038fa7  test    rax, rax
0x180038faa  jnz     loc_180039166
0x180038fb0  mov     ecx, 409h
0x180038fb5  cmp     cx, r14w
0x180038fb9  jz      short loc_180038FF6
0x180038fbb  cmp     cx, r15w
0x180038fbf  jz      short loc_180038FF6
0x180038fc1  xor     r9d, r9d
0x180038fc4  lea     r8, [rbp+3B0h+var_310]
0x180038fcb  lea     rdx, [rsp+4B0h+var_470]
0x180038fd0  call    LookupLangID
0x180038fd5  mov     r9, [rsp+4B0h+FilePart]
0x180038fda  lea     r8, [rsp+4B0h+var_470]
0x180038fdf  mov     rdx, rsi
0x180038fe2  mov     rcx, rdi
0x180038fe5  call    LoadMUIFile
0x180038fea  mov     rbx, rax
0x180038fed  test    rax, rax
0x180038ff0  jnz     loc_180039166
0x180038ff6  mov     r9, [rsp+4B0h+FilePart]
0x180038ffb  xor     r8d, r8d
0x180038ffe  mov     rdx, rsi
0x180039001  mov     rcx, rdi
0x180039004  call    LoadMUIFile
0x180039009  mov     rbx, rax
0x18003900c  test    rax, rax
0x18003900f  jnz     loc_180039166
0x180039015  test    dil, 1
0x180039019  jz      loc_180039190
0x18003901f  mov     rcx, rdi; hLibModule
0x180039022  call    cs:__imp_FreeLibrary
0x180039028  call    GetOSType
0x18003902d  test    al, 38h
0x18003902f  jz      loc_180039174
0x180039035  mov     rax, [rsp+4B0h+FilePart]
0x18003903a  lea     r8, aSS; "%s\\%s"
0x180039041  mov     r9, rsi
0x180039044  mov     [rsp+4B0h+lpBuffer], rax
0x180039049  mov     edx, 104h; unsigned __int64
0x18003904e  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180039055  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003905a  xor     r8d, r8d
0x18003905d  lea     rcx, [rbp+3B0h+Buffer]
0x180039064  lea     edx, [r8+1]
0x180039068  call    MapMUIFile
0x18003906d  jmp     loc_18003918D
0x180039072  test    al, 3
0x180039074  jz      short loc_180039015
0x180039076  call    GetInstallLanguage
0x18003907b  lea     r9, [rbp+3B0h+var_3C0]
0x18003907f  movzx   ecx, ax
0x180039082  lea     r8, [rbp+3B0h+var_310]
0x180039089  movzx   r14d, ax
0x18003908d  lea     rdx, [rsp+4B0h+var_470]
0x180039092  call    LookupLangID
0x180039097  test    eax, eax
0x180039099  jz      loc_180039015
0x18003909f  mov     r9, [rsp+4B0h+FilePart]
0x1800390a4  lea     r8, [rsp+4B0h+var_470]
0x1800390a9  mov     rdx, rsi
0x1800390ac  mov     rcx, rdi
0x1800390af  call    LoadMUIFile
0x1800390b4  mov     rbx, rax
0x1800390b7  test    rax, rax
0x1800390ba  jnz     loc_180039166
0x1800390c0  mov     r9, [rsp+4B0h+FilePart]
0x1800390c5  lea     r8, [rbp+3B0h+var_310]
0x1800390cc  mov     rdx, rsi
0x1800390cf  mov     rcx, rdi
0x1800390d2  call    LoadMUIFile
0x1800390d7  mov     rbx, rax
0x1800390da  test    rax, rax
0x1800390dd  jnz     loc_180039166
0x1800390e3  cmp     [rbp+3B0h+var_3C0], r13w
0x1800390e8  jz      short loc_180039106
0x1800390ea  mov     r9, [rsp+4B0h+FilePart]
0x1800390ef  lea     r8, [rbp+3B0h+var_3C0]
0x1800390f3  mov     rdx, rsi
0x1800390f6  mov     rcx, rdi
0x1800390f9  call    LoadMUIFile
0x1800390fe  mov     rbx, rax
0x180039101  test    rax, rax
0x180039104  jnz     short loc_180039166
0x180039106  mov     ecx, 409h
0x18003910b  cmp     cx, r14w
0x18003910f  jz      short loc_180039142
0x180039111  xor     r9d, r9d
0x180039114  lea     r8, [rbp+3B0h+var_310]
0x18003911b  lea     rdx, [rsp+4B0h+var_470]
0x180039120  call    LookupLangID
0x180039125  mov     r9, [rsp+4B0h+FilePart]
0x18003912a  lea     r8, [rsp+4B0h+var_470]
0x18003912f  mov     rdx, rsi
0x180039132  mov     rcx, rdi
0x180039135  call    LoadMUIFile
0x18003913a  mov     rbx, rax
0x18003913d  test    rax, rax
0x180039140  jnz     short loc_180039166
0x180039142  mov     r9, [rsp+4B0h+FilePart]
0x180039147  xor     r8d, r8d
0x18003914a  mov     rdx, rsi
0x18003914d  mov     rcx, rdi
0x180039150  call    LoadMUIFile
0x180039155  mov     rbx, rax
0x180039158  test    rax, rax
0x18003915b  jnz     short loc_180039166
0x18003915d  test    rbx, rbx
0x180039160  jz      loc_180039015
0x180039166  mov     rcx, rdi; hLibModule
0x180039169  call    cs:__imp_FreeLibrary
0x18003916f  mov     rax, rbx
0x180039172  jmp     short loc_1800391A0
0x180039174  call    GetOSType
0x180039179  test    al, 26h
0x18003917b  mov     r8d, r13d
0x18003917e  mov     rcx, r12; lpLibFileName
0x180039181  setnz   r8b; dwFlags
0x180039185  xor     edx, edx; hFile
0x180039187  call    cs:__imp_LoadLibraryExW
0x18003918d  mov     rdi, rax
0x180039190  mov     rax, rdi
0x180039193  jmp     short loc_1800391A0
0x180039195  mov     rcx, rdi; hLibModule
0x180039198  call    cs:__imp_FreeLibrary
0x18003919e  xor     eax, eax
0x1800391a0  mov     rcx, [rbp+3B0h+var_50]
0x1800391a7  xor     rcx, rsp; StackCookie
0x1800391aa  call    __security_check_cookie
0x1800391af  add     rsp, 478h
0x1800391b6  pop     r15
0x1800391b8  pop     r14
0x1800391ba  pop     r13
0x1800391bc  pop     r12
0x1800391be  pop     rdi
0x1800391bf  pop     rsi
0x1800391c0  pop     rbx
0x1800391c1  pop     rbp
0x1800391c2  retn
```
