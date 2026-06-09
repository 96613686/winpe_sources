# LoadMUILibraryW

- ea: `0x140015be8`
- end: `0x14001606e`
- name: `LoadMUILibraryW`
- size: `1158`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140014880`

## callees

- `0x14000c2ec`
- `0x140015500`
- `0x140015580`
- `0x140015694`
- `0x1400157bc`
- `0x140015830`
- `0x1400159a8`
- `0x140015be8`
- `0x1400161d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140015c49`
- `KERNEL32!LoadLibraryExW` at `0x14001602b`
- `KERNEL32!LoadLibraryExW` at `0x140015c49`
- `KERNEL32!LoadLibraryExW` at `0x14001602b`
- `KERNEL32!FreeLibrary` at `0x140015f78`
- `KERNEL32!FreeLibrary` at `0x14001600d`
- `KERNEL32!FreeLibrary` at `0x14001603c`
- `KERNEL32!FreeLibrary` at `0x140015f78`
- `KERNEL32!FreeLibrary` at `0x14001600d`
- `KERNEL32!FreeLibrary` at `0x14001603c`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140015db9`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140015db9`
- `KERNEL32!SearchPathW` at `0x140015c8c`
- `KERNEL32!SearchPathW` at `0x140015c8c`
- `KERNEL32!FindResourceExW` at `0x140015cd2`
- `KERNEL32!FindResourceExW` at `0x140015cd2`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140015cfb`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140015cfb`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v6; // rdi
  WCHAR *v7; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v11; // r15
  bool v12; // zf
  __int64 InstallLanguage; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_14001EA50 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_14001EA50 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_14001EA50 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v6);
    return 0;
  }
  if ( FilePart )
  {
    v7 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v7 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v6, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( !LangID )
    {
      if ( (dword_14001EA50 & 4) == 0 )
      {
        if ( (dword_14001EA50 & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
            v12 = (_WORD)InstallLanguage == 1033;
LABEL_35:
            if ( !v12 )
            {
              LookupLangID(1033, v21, v23, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
LABEL_37:
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
            if ( MUIFile )
            {
LABEL_45:
              FreeLibrary(v6);
              return MUIFile;
            }
          }
        }
        goto LABEL_38;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
          if ( MUIFile )
            goto LABEL_45;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              goto LABEL_38;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_37;
          v12 = v11 == 1033;
          goto LABEL_35;
        }
        UserDefaultUILanguage = 1028;
      }
      goto LABEL_44;
    }
    if ( (dword_14001EA50 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
LABEL_44:
      if ( MUIFile )
        goto LABEL_45;
    }
  }
LABEL_38:
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType(v15, v14) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v17, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140015be8  mov     [rsp-8+arg_8], rbx
0x140015bed  push    rbp
0x140015bee  push    rsi
0x140015bef  push    rdi
0x140015bf0  push    r12
0x140015bf2  push    r13
0x140015bf4  push    r14
0x140015bf6  push    r15
0x140015bf8  lea     rbp, [rsp-370h]
0x140015c00  sub     rsp, 470h
0x140015c07  mov     rax, cs:__security_cookie
0x140015c0e  xor     rax, rsp
0x140015c11  mov     [rbp+3A0h+var_40], rax
0x140015c18  xor     r13d, r13d
0x140015c1b  movzx   ebx, r8w
0x140015c1f  mov     [rsp+4A0h+FilePart], r13
0x140015c24  mov     r12, rcx
0x140015c27  test    rcx, rcx
0x140015c2a  jz      loc_140016042
0x140015c30  call    GetOSType
0x140015c35  mov     cs:dword_14001EA50, eax
0x140015c3b  xor     edx, edx; hFile
0x140015c3d  and     eax, 20h
0x140015c40  mov     rcx, r12; lpLibFileName
0x140015c43  or      eax, 2
0x140015c46  mov     r8d, eax; dwFlags
0x140015c49  call    cs:__imp_LoadLibraryExW
0x140015c4f  mov     rdi, rax
0x140015c52  test    rax, rax
0x140015c55  jz      loc_140016042
0x140015c5b  test    byte ptr cs:dword_14001EA50, 20h
0x140015c62  jnz     loc_140016044
0x140015c68  lea     rax, [rsp+4A0h+FilePart]
0x140015c6d  mov     r9d, 104h; nBufferLength
0x140015c73  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x140015c78  xor     r8d, r8d; lpExtension
0x140015c7b  lea     rax, [rbp+3A0h+Buffer]
0x140015c82  mov     rdx, r12; lpFileName
0x140015c85  xor     ecx, ecx; lpPath
0x140015c87  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x140015c8c  call    cs:__imp_SearchPathW
0x140015c92  test    eax, eax
0x140015c94  jz      loc_140016039
0x140015c9a  mov     rcx, [rsp+4A0h+FilePart]
0x140015c9f  test    rcx, rcx
0x140015ca2  jnz     short loc_140015CB5
0x140015ca4  lea     rax, [rbp+3A0h+Buffer]
0x140015cab  mov     esi, r13d
0x140015cae  mov     [rsp+4A0h+FilePart], rax
0x140015cb3  jmp     short loc_140015CC1
0x140015cb5  lea     rsi, [rbp+3A0h+Buffer]
0x140015cbc  mov     [rcx-2], r13w
0x140015cc1  xor     r9d, r9d; wLanguage
0x140015cc4  lea     rdx, Type; "MUI"
0x140015ccb  mov     rcx, rdi; hModule
0x140015cce  lea     r8d, [r9+1]; lpName
0x140015cd2  call    cs:__imp_FindResourceExW
0x140015cd8  test    rax, rax
0x140015cdb  jz      loc_140015F6B
0x140015ce1  test    bx, bx
0x140015ce4  jnz     loc_140015FC5
0x140015cea  mov     eax, cs:dword_14001EA50
0x140015cf0  test    al, 4
0x140015cf2  jz      loc_140015E70
0x140015cf8  mov     rbx, r13
0x140015cfb  call    cs:__imp_GetUserDefaultUILanguage
0x140015d01  mov     r15d, 404h
0x140015d07  movzx   r14d, ax
0x140015d0b  cmp     ax, r15w
0x140015d0f  jnz     short loc_140015D1A
0x140015d11  call    GetCHTLangauge
0x140015d16  movzx   r14d, ax
0x140015d1a  lea     r9, [rbp+3A0h+var_3B0]
0x140015d1e  movzx   ecx, r14w
0x140015d22  lea     r8, [rbp+3A0h+var_300]
0x140015d29  lea     rdx, [rsp+4A0h+var_460]
0x140015d2e  call    LookupLangID
0x140015d33  test    eax, eax
0x140015d35  jz      loc_140016001
0x140015d3b  mov     r9, [rsp+4A0h+FilePart]
0x140015d40  lea     r8, [rsp+4A0h+var_460]
0x140015d45  mov     rdx, rsi
0x140015d48  mov     rcx, rdi
0x140015d4b  call    LoadMUIFile
0x140015d50  mov     rbx, rax
0x140015d53  test    rax, rax
0x140015d56  jnz     loc_14001600A
0x140015d5c  mov     r9, [rsp+4A0h+FilePart]
0x140015d61  lea     r8, [rbp+3A0h+var_300]
0x140015d68  mov     rdx, rsi
0x140015d6b  mov     rcx, rdi
0x140015d6e  call    LoadMUIFile
0x140015d73  mov     rbx, rax
0x140015d76  test    rax, rax
0x140015d79  jnz     loc_14001600A
0x140015d7f  cmp     [rbp+3A0h+var_3B0], r13w
0x140015d84  jz      short loc_140015DA6
0x140015d86  mov     r9, [rsp+4A0h+FilePart]
0x140015d8b  lea     r8, [rbp+3A0h+var_3B0]
0x140015d8f  mov     rdx, rsi
0x140015d92  mov     rcx, rdi
0x140015d95  call    LoadMUIFile
0x140015d9a  mov     rbx, rax
0x140015d9d  test    rax, rax
0x140015da0  jnz     loc_14001600A
0x140015da6  mov     eax, 0C04h
0x140015dab  cmp     r14w, ax
0x140015daf  jnz     short loc_140015DB9
0x140015db1  mov     r14d, r15d
0x140015db4  jmp     loc_140015D1A
0x140015db9  call    cs:__imp_GetSystemDefaultUILanguage
0x140015dbf  movzx   r15d, ax
0x140015dc3  cmp     ax, r14w
0x140015dc7  jz      loc_140015E58
0x140015dcd  lea     r9, [rbp+3A0h+var_3B0]
0x140015dd1  movzx   ecx, ax
0x140015dd4  lea     r8, [rbp+3A0h+var_300]
0x140015ddb  lea     rdx, [rsp+4A0h+var_460]
0x140015de0  call    LookupLangID
0x140015de5  test    eax, eax
0x140015de7  jz      loc_140015F6B
0x140015ded  mov     r9, [rsp+4A0h+FilePart]
0x140015df2  lea     r8, [rsp+4A0h+var_460]
0x140015df7  mov     rdx, rsi
0x140015dfa  mov     rcx, rdi
0x140015dfd  call    LoadMUIFile
0x140015e02  mov     rbx, rax
0x140015e05  test    rax, rax
0x140015e08  jnz     loc_14001600A
0x140015e0e  mov     r9, [rsp+4A0h+FilePart]
0x140015e13  lea     r8, [rbp+3A0h+var_300]
0x140015e1a  mov     rdx, rsi
0x140015e1d  mov     rcx, rdi
0x140015e20  call    LoadMUIFile
0x140015e25  mov     rbx, rax
0x140015e28  test    rax, rax
0x140015e2b  jnz     loc_14001600A
0x140015e31  cmp     [rbp+3A0h+var_3B0], r13w
0x140015e36  jz      short loc_140015E58
0x140015e38  mov     r9, [rsp+4A0h+FilePart]
0x140015e3d  lea     r8, [rbp+3A0h+var_3B0]
0x140015e41  mov     rdx, rsi
0x140015e44  mov     rcx, rdi
0x140015e47  call    LoadMUIFile
0x140015e4c  mov     rbx, rax
0x140015e4f  test    rax, rax
0x140015e52  jnz     loc_14001600A
0x140015e58  mov     ecx, 409h
0x140015e5d  cmp     cx, r14w
0x140015e61  jz      loc_140015F4C
0x140015e67  cmp     cx, r15w
0x140015e6b  jmp     loc_140015F15
0x140015e70  test    al, 3
0x140015e72  jz      loc_140015F6B
0x140015e78  call    GetInstallLanguage
0x140015e7d  lea     r9, [rbp+3A0h+var_3B0]
0x140015e81  movzx   ecx, ax
0x140015e84  lea     r8, [rbp+3A0h+var_300]
0x140015e8b  movzx   r14d, ax
0x140015e8f  lea     rdx, [rsp+4A0h+var_460]
0x140015e94  call    LookupLangID
0x140015e99  test    eax, eax
0x140015e9b  jz      loc_140015F6B
0x140015ea1  mov     r9, [rsp+4A0h+FilePart]
0x140015ea6  lea     r8, [rsp+4A0h+var_460]
0x140015eab  mov     rdx, rsi
0x140015eae  mov     rcx, rdi
0x140015eb1  call    LoadMUIFile
0x140015eb6  mov     rbx, rax
0x140015eb9  test    rax, rax
0x140015ebc  jnz     loc_14001600A
0x140015ec2  mov     r9, [rsp+4A0h+FilePart]
0x140015ec7  lea     r8, [rbp+3A0h+var_300]
0x140015ece  mov     rdx, rsi
0x140015ed1  mov     rcx, rdi
0x140015ed4  call    LoadMUIFile
0x140015ed9  mov     rbx, rax
0x140015edc  test    rax, rax
0x140015edf  jnz     loc_14001600A
0x140015ee5  cmp     [rbp+3A0h+var_3B0], r13w
0x140015eea  jz      short loc_140015F0C
0x140015eec  mov     r9, [rsp+4A0h+FilePart]
0x140015ef1  lea     r8, [rbp+3A0h+var_3B0]
0x140015ef5  mov     rdx, rsi
0x140015ef8  mov     rcx, rdi
0x140015efb  call    LoadMUIFile
0x140015f00  mov     rbx, rax
0x140015f03  test    rax, rax
0x140015f06  jnz     loc_14001600A
0x140015f0c  mov     ecx, 409h
0x140015f11  cmp     cx, r14w
0x140015f15  jz      short loc_140015F4C
0x140015f17  xor     r9d, r9d
0x140015f1a  lea     r8, [rbp+3A0h+var_300]
0x140015f21  lea     rdx, [rsp+4A0h+var_460]
0x140015f26  call    LookupLangID
0x140015f2b  mov     r9, [rsp+4A0h+FilePart]
0x140015f30  lea     r8, [rsp+4A0h+var_460]
0x140015f35  mov     rdx, rsi
0x140015f38  mov     rcx, rdi
0x140015f3b  call    LoadMUIFile
0x140015f40  mov     rbx, rax
0x140015f43  test    rax, rax
0x140015f46  jnz     loc_14001600A
0x140015f4c  mov     r9, [rsp+4A0h+FilePart]
0x140015f51  xor     r8d, r8d
0x140015f54  mov     rdx, rsi
0x140015f57  mov     rcx, rdi
0x140015f5a  call    LoadMUIFile
0x140015f5f  mov     rbx, rax
0x140015f62  test    rax, rax
0x140015f65  jnz     loc_14001600A
0x140015f6b  test    dil, 1
0x140015f6f  jz      loc_140016034
0x140015f75  mov     rcx, rdi; hLibModule
0x140015f78  call    cs:__imp_FreeLibrary
0x140015f7e  call    GetOSType
0x140015f83  test    al, 38h
0x140015f85  jz      loc_140016018
0x140015f8b  mov     rax, [rsp+4A0h+FilePart]
0x140015f90  lea     r8, aSS; "%s\\%s"
0x140015f97  mov     r9, rsi
0x140015f9a  mov     [rsp+4A0h+lpBuffer], rax
0x140015f9f  mov     edx, 104h; unsigned __int64
0x140015fa4  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x140015fab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140015fb0  xor     r8d, r8d
0x140015fb3  lea     rcx, [rbp+3A0h+Buffer]
0x140015fba  lea     edx, [r8+1]
0x140015fbe  call    MapMUIFile
0x140015fc3  jmp     short loc_140016031
0x140015fc5  test    byte ptr cs:dword_14001EA50, 7
0x140015fcc  jz      short loc_140015F6B
0x140015fce  xor     r9d, r9d
0x140015fd1  lea     r8, [rbp+3A0h+var_300]
0x140015fd8  lea     rdx, [rsp+4A0h+var_460]
0x140015fdd  movzx   ecx, bx
0x140015fe0  call    LookupLangID
0x140015fe5  test    eax, eax
0x140015fe7  jz      short loc_140015F6B
0x140015fe9  mov     r9, [rsp+4A0h+FilePart]
0x140015fee  lea     r8, [rsp+4A0h+var_460]
0x140015ff3  mov     rdx, rsi
0x140015ff6  mov     rcx, rdi
0x140015ff9  call    LoadMUIFile
0x140015ffe  mov     rbx, rax
0x140016001  test    rbx, rbx
0x140016004  jz      loc_140015F6B
0x14001600a  mov     rcx, rdi; hLibModule
0x14001600d  call    cs:__imp_FreeLibrary
0x140016013  mov     rax, rbx
0x140016016  jmp     short loc_140016044
0x140016018  call    GetOSType
0x14001601d  test    al, 26h
0x14001601f  mov     r8d, r13d
0x140016022  mov     rcx, r12; lpLibFileName
0x140016025  setnz   r8b; dwFlags
0x140016029  xor     edx, edx; hFile
0x14001602b  call    cs:__imp_LoadLibraryExW
0x140016031  mov     rdi, rax
0x140016034  mov     rax, rdi
0x140016037  jmp     short loc_140016044
0x140016039  mov     rcx, rdi; hLibModule
0x14001603c  call    cs:__imp_FreeLibrary
0x140016042  xor     eax, eax
0x140016044  mov     rcx, [rbp+3A0h+var_40]
0x14001604b  xor     rcx, rsp; StackCookie
0x14001604e  call    __security_check_cookie
0x140016053  mov     rbx, [rsp+4A0h+arg_8]
0x14001605b  add     rsp, 470h
0x140016062  pop     r15
0x140016064  pop     r14
0x140016066  pop     r13
0x140016068  pop     r12
0x14001606a  pop     rdi
0x14001606b  pop     rsi
0x14001606c  pop     rbp
0x14001606d  retn
```
