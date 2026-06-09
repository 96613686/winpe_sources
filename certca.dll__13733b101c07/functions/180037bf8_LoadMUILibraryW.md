# LoadMUILibraryW

- ea: `0x180037bf8`
- end: `0x18003806b`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800051f0`
- `0x18000ef48`

## callees

- `0x18000a320`
- `0x180037510`
- `0x180037590`
- `0x1800376a4`
- `0x1800377cc`
- `0x180037840`
- `0x1800379b8`
- `0x180037bf8`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037eca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038011`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038040`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037eca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038011`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038040`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180037cdb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180037cdb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037c52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003802f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037c52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003802f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180037c95`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180037c95`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180037db9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180037db9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180037cfb`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180037cfb`

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
  dword_1800C5188 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800C5188 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1800C5188 & 0x20) != 0 )
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
    if ( (dword_1800C5188 & 4) != 0 )
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
    else if ( (dword_1800C5188 & 3) != 0 )
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
0x180037bf8  push    rbp
0x180037bfa  push    rbx
0x180037bfb  push    rsi
0x180037bfc  push    rdi
0x180037bfd  push    r12
0x180037bff  push    r13
0x180037c01  push    r14
0x180037c03  push    r15
0x180037c05  lea     rbp, [rsp-378h]
0x180037c0d  sub     rsp, 478h
0x180037c14  mov     rax, cs:__security_cookie
0x180037c1b  xor     rax, rsp
0x180037c1e  mov     [rbp+3B0h+var_50], rax
0x180037c25  xor     r13d, r13d
0x180037c28  mov     r12, rcx
0x180037c2b  mov     [rsp+4B0h+FilePart], r13
0x180037c30  test    rcx, rcx
0x180037c33  jz      loc_180038046
0x180037c39  call    GetOSType
0x180037c3e  mov     cs:dword_1800C5188, eax
0x180037c44  xor     edx, edx; hFile
0x180037c46  and     eax, 20h
0x180037c49  mov     rcx, r12; lpLibFileName
0x180037c4c  or      eax, 2
0x180037c4f  mov     r8d, eax; dwFlags
0x180037c52  call    cs:__imp_LoadLibraryExW
0x180037c58  mov     rdi, rax
0x180037c5b  test    rax, rax
0x180037c5e  jz      loc_180038046
0x180037c64  test    byte ptr cs:dword_1800C5188, 20h
0x180037c6b  jnz     loc_180038048
0x180037c71  lea     rax, [rsp+4B0h+FilePart]
0x180037c76  mov     r9d, 104h; nBufferLength
0x180037c7c  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x180037c81  xor     r8d, r8d; lpExtension
0x180037c84  lea     rax, [rbp+3B0h+Buffer]
0x180037c8b  mov     rdx, r12; lpFileName
0x180037c8e  xor     ecx, ecx; lpPath
0x180037c90  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180037c95  call    cs:__imp_SearchPathW
0x180037c9b  test    eax, eax
0x180037c9d  jz      loc_18003803D
0x180037ca3  mov     rcx, [rsp+4B0h+FilePart]
0x180037ca8  test    rcx, rcx
0x180037cab  jnz     short loc_180037CBE
0x180037cad  lea     rax, [rbp+3B0h+Buffer]
0x180037cb4  mov     esi, r13d
0x180037cb7  mov     [rsp+4B0h+FilePart], rax
0x180037cbc  jmp     short loc_180037CCA
0x180037cbe  lea     rsi, [rbp+3B0h+Buffer]
0x180037cc5  mov     [rcx-2], r13w
0x180037cca  xor     r9d, r9d; wLanguage
0x180037ccd  lea     rdx, Type; "MUI"
0x180037cd4  mov     rcx, rdi; hModule
0x180037cd7  lea     r8d, [r9+1]; lpName
0x180037cdb  call    cs:__imp_FindResourceExW
0x180037ce1  test    rax, rax
0x180037ce4  jz      loc_180037EBD
0x180037cea  mov     eax, cs:dword_1800C5188
0x180037cf0  test    al, 4
0x180037cf2  jz      loc_180037F1A
0x180037cf8  mov     rbx, r13
0x180037cfb  call    cs:__imp_GetUserDefaultUILanguage
0x180037d01  mov     r15d, 404h
0x180037d07  movzx   r14d, ax
0x180037d0b  cmp     ax, r15w
0x180037d0f  jnz     short loc_180037D1A
0x180037d11  call    GetCHTLangauge
0x180037d16  movzx   r14d, ax
0x180037d1a  lea     r9, [rbp+3B0h+var_3C0]
0x180037d1e  movzx   ecx, r14w
0x180037d22  lea     r8, [rbp+3B0h+var_310]
0x180037d29  lea     rdx, [rsp+4B0h+var_470]
0x180037d2e  call    LookupLangID
0x180037d33  test    eax, eax
0x180037d35  jz      loc_180038005
0x180037d3b  mov     r9, [rsp+4B0h+FilePart]
0x180037d40  lea     r8, [rsp+4B0h+var_470]
0x180037d45  mov     rdx, rsi
0x180037d48  mov     rcx, rdi
0x180037d4b  call    LoadMUIFile
0x180037d50  mov     rbx, rax
0x180037d53  test    rax, rax
0x180037d56  jnz     loc_18003800E
0x180037d5c  mov     r9, [rsp+4B0h+FilePart]
0x180037d61  lea     r8, [rbp+3B0h+var_310]
0x180037d68  mov     rdx, rsi
0x180037d6b  mov     rcx, rdi
0x180037d6e  call    LoadMUIFile
0x180037d73  mov     rbx, rax
0x180037d76  test    rax, rax
0x180037d79  jnz     loc_18003800E
0x180037d7f  cmp     [rbp+3B0h+var_3C0], r13w
0x180037d84  jz      short loc_180037DA6
0x180037d86  mov     r9, [rsp+4B0h+FilePart]
0x180037d8b  lea     r8, [rbp+3B0h+var_3C0]
0x180037d8f  mov     rdx, rsi
0x180037d92  mov     rcx, rdi
0x180037d95  call    LoadMUIFile
0x180037d9a  mov     rbx, rax
0x180037d9d  test    rax, rax
0x180037da0  jnz     loc_18003800E
0x180037da6  mov     eax, 0C04h
0x180037dab  cmp     r14w, ax
0x180037daf  jnz     short loc_180037DB9
0x180037db1  mov     r14d, r15d
0x180037db4  jmp     loc_180037D1A
0x180037db9  call    cs:__imp_GetSystemDefaultUILanguage
0x180037dbf  movzx   r15d, ax
0x180037dc3  cmp     ax, r14w
0x180037dc7  jz      loc_180037E58
0x180037dcd  lea     r9, [rbp+3B0h+var_3C0]
0x180037dd1  movzx   ecx, ax
0x180037dd4  lea     r8, [rbp+3B0h+var_310]
0x180037ddb  lea     rdx, [rsp+4B0h+var_470]
0x180037de0  call    LookupLangID
0x180037de5  test    eax, eax
0x180037de7  jz      loc_180037EBD
0x180037ded  mov     r9, [rsp+4B0h+FilePart]
0x180037df2  lea     r8, [rsp+4B0h+var_470]
0x180037df7  mov     rdx, rsi
0x180037dfa  mov     rcx, rdi
0x180037dfd  call    LoadMUIFile
0x180037e02  mov     rbx, rax
0x180037e05  test    rax, rax
0x180037e08  jnz     loc_18003800E
0x180037e0e  mov     r9, [rsp+4B0h+FilePart]
0x180037e13  lea     r8, [rbp+3B0h+var_310]
0x180037e1a  mov     rdx, rsi
0x180037e1d  mov     rcx, rdi
0x180037e20  call    LoadMUIFile
0x180037e25  mov     rbx, rax
0x180037e28  test    rax, rax
0x180037e2b  jnz     loc_18003800E
0x180037e31  cmp     [rbp+3B0h+var_3C0], r13w
0x180037e36  jz      short loc_180037E58
0x180037e38  mov     r9, [rsp+4B0h+FilePart]
0x180037e3d  lea     r8, [rbp+3B0h+var_3C0]
0x180037e41  mov     rdx, rsi
0x180037e44  mov     rcx, rdi
0x180037e47  call    LoadMUIFile
0x180037e4c  mov     rbx, rax
0x180037e4f  test    rax, rax
0x180037e52  jnz     loc_18003800E
0x180037e58  mov     ecx, 409h
0x180037e5d  cmp     cx, r14w
0x180037e61  jz      short loc_180037E9E
0x180037e63  cmp     cx, r15w
0x180037e67  jz      short loc_180037E9E
0x180037e69  xor     r9d, r9d
0x180037e6c  lea     r8, [rbp+3B0h+var_310]
0x180037e73  lea     rdx, [rsp+4B0h+var_470]
0x180037e78  call    LookupLangID
0x180037e7d  mov     r9, [rsp+4B0h+FilePart]
0x180037e82  lea     r8, [rsp+4B0h+var_470]
0x180037e87  mov     rdx, rsi
0x180037e8a  mov     rcx, rdi
0x180037e8d  call    LoadMUIFile
0x180037e92  mov     rbx, rax
0x180037e95  test    rax, rax
0x180037e98  jnz     loc_18003800E
0x180037e9e  mov     r9, [rsp+4B0h+FilePart]
0x180037ea3  xor     r8d, r8d
0x180037ea6  mov     rdx, rsi
0x180037ea9  mov     rcx, rdi
0x180037eac  call    LoadMUIFile
0x180037eb1  mov     rbx, rax
0x180037eb4  test    rax, rax
0x180037eb7  jnz     loc_18003800E
0x180037ebd  test    dil, 1
0x180037ec1  jz      loc_180038038
0x180037ec7  mov     rcx, rdi; hLibModule
0x180037eca  call    cs:__imp_FreeLibrary
0x180037ed0  call    GetOSType
0x180037ed5  test    al, 38h
0x180037ed7  jz      loc_18003801C
0x180037edd  mov     rax, [rsp+4B0h+FilePart]
0x180037ee2  lea     r8, aSS; "%s\\%s"
0x180037ee9  mov     r9, rsi
0x180037eec  mov     [rsp+4B0h+lpBuffer], rax
0x180037ef1  mov     edx, 104h; unsigned __int64
0x180037ef6  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180037efd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037f02  xor     r8d, r8d
0x180037f05  lea     rcx, [rbp+3B0h+Buffer]
0x180037f0c  lea     edx, [r8+1]
0x180037f10  call    MapMUIFile
0x180037f15  jmp     loc_180038035
0x180037f1a  test    al, 3
0x180037f1c  jz      short loc_180037EBD
0x180037f1e  call    GetInstallLanguage
0x180037f23  lea     r9, [rbp+3B0h+var_3C0]
0x180037f27  movzx   ecx, ax
0x180037f2a  lea     r8, [rbp+3B0h+var_310]
0x180037f31  movzx   r14d, ax
0x180037f35  lea     rdx, [rsp+4B0h+var_470]
0x180037f3a  call    LookupLangID
0x180037f3f  test    eax, eax
0x180037f41  jz      loc_180037EBD
0x180037f47  mov     r9, [rsp+4B0h+FilePart]
0x180037f4c  lea     r8, [rsp+4B0h+var_470]
0x180037f51  mov     rdx, rsi
0x180037f54  mov     rcx, rdi
0x180037f57  call    LoadMUIFile
0x180037f5c  mov     rbx, rax
0x180037f5f  test    rax, rax
0x180037f62  jnz     loc_18003800E
0x180037f68  mov     r9, [rsp+4B0h+FilePart]
0x180037f6d  lea     r8, [rbp+3B0h+var_310]
0x180037f74  mov     rdx, rsi
0x180037f77  mov     rcx, rdi
0x180037f7a  call    LoadMUIFile
0x180037f7f  mov     rbx, rax
0x180037f82  test    rax, rax
0x180037f85  jnz     loc_18003800E
0x180037f8b  cmp     [rbp+3B0h+var_3C0], r13w
0x180037f90  jz      short loc_180037FAE
0x180037f92  mov     r9, [rsp+4B0h+FilePart]
0x180037f97  lea     r8, [rbp+3B0h+var_3C0]
0x180037f9b  mov     rdx, rsi
0x180037f9e  mov     rcx, rdi
0x180037fa1  call    LoadMUIFile
0x180037fa6  mov     rbx, rax
0x180037fa9  test    rax, rax
0x180037fac  jnz     short loc_18003800E
0x180037fae  mov     ecx, 409h
0x180037fb3  cmp     cx, r14w
0x180037fb7  jz      short loc_180037FEA
0x180037fb9  xor     r9d, r9d
0x180037fbc  lea     r8, [rbp+3B0h+var_310]
0x180037fc3  lea     rdx, [rsp+4B0h+var_470]
0x180037fc8  call    LookupLangID
0x180037fcd  mov     r9, [rsp+4B0h+FilePart]
0x180037fd2  lea     r8, [rsp+4B0h+var_470]
0x180037fd7  mov     rdx, rsi
0x180037fda  mov     rcx, rdi
0x180037fdd  call    LoadMUIFile
0x180037fe2  mov     rbx, rax
0x180037fe5  test    rax, rax
0x180037fe8  jnz     short loc_18003800E
0x180037fea  mov     r9, [rsp+4B0h+FilePart]
0x180037fef  xor     r8d, r8d
0x180037ff2  mov     rdx, rsi
0x180037ff5  mov     rcx, rdi
0x180037ff8  call    LoadMUIFile
0x180037ffd  mov     rbx, rax
0x180038000  test    rax, rax
0x180038003  jnz     short loc_18003800E
0x180038005  test    rbx, rbx
0x180038008  jz      loc_180037EBD
0x18003800e  mov     rcx, rdi; hLibModule
0x180038011  call    cs:__imp_FreeLibrary
0x180038017  mov     rax, rbx
0x18003801a  jmp     short loc_180038048
0x18003801c  call    GetOSType
0x180038021  test    al, 26h
0x180038023  mov     r8d, r13d
0x180038026  mov     rcx, r12; lpLibFileName
0x180038029  setnz   r8b; dwFlags
0x18003802d  xor     edx, edx; hFile
0x18003802f  call    cs:__imp_LoadLibraryExW
0x180038035  mov     rdi, rax
0x180038038  mov     rax, rdi
0x18003803b  jmp     short loc_180038048
0x18003803d  mov     rcx, rdi; hLibModule
0x180038040  call    cs:__imp_FreeLibrary
0x180038046  xor     eax, eax
0x180038048  mov     rcx, [rbp+3B0h+var_50]
0x18003804f  xor     rcx, rsp; StackCookie
0x180038052  call    __security_check_cookie
0x180038057  add     rsp, 478h
0x18003805e  pop     r15
0x180038060  pop     r14
0x180038062  pop     r13
0x180038064  pop     r12
0x180038066  pop     rdi
0x180038067  pop     rsi
0x180038068  pop     rbx
0x180038069  pop     rbp
0x18003806a  retn
```
