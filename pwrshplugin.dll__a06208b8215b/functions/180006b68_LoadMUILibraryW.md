# LoadMUILibraryW

- ea: `0x180006b68`
- end: `0x180007011`
- name: `LoadMUILibraryW`
- size: `1193`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180002e80`

## callees

- `0x180006418`
- `0x180006520`
- `0x180006648`
- `0x1800066bc`
- `0x180006830`
- `0x18000691c`
- `0x180006b68`
- `0x180009683`
- `0x1800096b0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x180006c47`
- `KERNEL32!FindResourceExW` at `0x180006c47`
- `KERNEL32!LoadLibraryExW` at `0x180006bba`
- `KERNEL32!LoadLibraryExW` at `0x180006fd5`
- `KERNEL32!LoadLibraryExW` at `0x180006bba`
- `KERNEL32!LoadLibraryExW` at `0x180006fd5`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180006c67`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180006c67`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180006d5b`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180006d5b`
- `KERNEL32!SearchPathW` at `0x180006c01`
- `KERNEL32!SearchPathW` at `0x180006c01`
- `KERNEL32!GetLocaleInfoW` at `0x180006c9a`
- `KERNEL32!GetLocaleInfoW` at `0x180006c9a`
- `KERNEL32!FreeLibrary` at `0x180006e6c`
- `KERNEL32!FreeLibrary` at `0x180006fb3`
- `KERNEL32!FreeLibrary` at `0x180006fe6`
- `KERNEL32!FreeLibrary` at `0x180006e6c`
- `KERNEL32!FreeLibrary` at `0x180006fb3`
- `KERNEL32!FreeLibrary` at `0x180006fe6`

## string_xrefs

- `0x180006ba8`: `pwrshplugin.dll`
- `0x180006be9`: `pwrshplugin.dll`
- `0x180006fc5`: `pwrshplugin.dll`

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
  WCHAR LCData[32]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  FilePart = 0;
  dword_180014DB0 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(L"pwrshplugin.dll", 0, dword_180014DB0 & 0x20 | 2u);
  v4 = result;
  if ( !result )
    return 0;
  if ( (dword_180014DB0 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"pwrshplugin.dll", 0, 0x104u, Buffer, &FilePart) )
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
    if ( (dword_180014DB0 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage != 1028 )
        goto LABEL_13;
      UserDefaultUILanguage = 3076;
      if ( !GetLocaleInfoW(0x404u, 8u, LCData, 32) || !wcsncmp_0(LCData, &word_18000E96C, 3u) )
        goto LABEL_13;
      while ( 1 )
      {
        UserDefaultUILanguage = 1028;
LABEL_13:
        if ( !(unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
          break;
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
          if ( MUIFile )
            goto LABEL_42;
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
              goto LABEL_42;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
            if ( MUIFile )
              goto LABEL_42;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
              if ( MUIFile )
                goto LABEL_42;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v9 != 1033 )
          {
            LookupLangID(1033, v20, v22, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_42;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart);
          if ( MUIFile )
            goto LABEL_42;
          break;
        }
      }
    }
    else if ( (dword_180014DB0 & 3) != 0 )
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
LABEL_42:
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
      return MapMUIFile(Buffer, 1, 0);
    }
    else
    {
      OSType = GetOSType(v14, v13, v15);
      return LoadLibraryExW(L"pwrshplugin.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180006b68  push    rbp
0x180006b6a  push    rbx
0x180006b6b  push    rsi
0x180006b6c  push    rdi
0x180006b6d  push    r12
0x180006b6f  push    r13
0x180006b71  push    r14
0x180006b73  push    r15
0x180006b75  lea     rbp, [rsp-3B8h]
0x180006b7d  sub     rsp, 4B8h
0x180006b84  mov     rax, cs:__security_cookie
0x180006b8b  xor     rax, rsp
0x180006b8e  mov     [rbp+3F0h+var_50], rax
0x180006b95  xor     r12d, r12d
0x180006b98  mov     [rsp+4F0h+FilePart], r12
0x180006b9d  call    GetOSType
0x180006ba2  mov     cs:dword_180014DB0, eax
0x180006ba8  lea     rcx, LibFileName; "pwrshplugin.dll"
0x180006baf  and     eax, 20h
0x180006bb2  xor     edx, edx; hFile
0x180006bb4  or      eax, 2
0x180006bb7  mov     r8d, eax; dwFlags
0x180006bba  call    cs:__imp_LoadLibraryExW
0x180006bc0  mov     rdi, rax
0x180006bc3  test    rax, rax
0x180006bc6  jz      loc_180006FEC
0x180006bcc  test    byte ptr cs:dword_180014DB0, 20h
0x180006bd3  jnz     loc_180006FEE
0x180006bd9  lea     rax, [rsp+4F0h+FilePart]
0x180006bde  mov     r9d, 104h; nBufferLength
0x180006be4  mov     [rsp+4F0h+lpFilePart], rax; lpFilePart
0x180006be9  lea     rdx, LibFileName; "pwrshplugin.dll"
0x180006bf0  lea     rax, [rbp+3F0h+Buffer]
0x180006bf7  xor     r8d, r8d; lpExtension
0x180006bfa  xor     ecx, ecx; lpPath
0x180006bfc  mov     [rsp+4F0h+lpBuffer], rax; lpBuffer
0x180006c01  call    cs:__imp_SearchPathW
0x180006c07  test    eax, eax
0x180006c09  jz      loc_180006FE3
0x180006c0f  mov     rcx, [rsp+4F0h+FilePart]
0x180006c14  test    rcx, rcx
0x180006c17  jnz     short loc_180006C2A
0x180006c19  lea     rax, [rbp+3F0h+Buffer]
0x180006c20  mov     esi, r12d
0x180006c23  mov     [rsp+4F0h+FilePart], rax
0x180006c28  jmp     short loc_180006C36
0x180006c2a  lea     rsi, [rbp+3F0h+Buffer]
0x180006c31  mov     [rcx-2], r12w
0x180006c36  xor     r9d, r9d; wLanguage
0x180006c39  lea     rdx, Type; "MUI"
0x180006c40  mov     rcx, rdi; hModule
0x180006c43  lea     r8d, [r9+1]; lpName
0x180006c47  call    cs:__imp_FindResourceExW
0x180006c4d  test    rax, rax
0x180006c50  jz      loc_180006E5F
0x180006c56  mov     eax, cs:dword_180014DB0
0x180006c5c  test    al, 4
0x180006c5e  jz      loc_180006EBC
0x180006c64  mov     rbx, r12
0x180006c67  call    cs:__imp_GetUserDefaultUILanguage
0x180006c6d  mov     r15d, 404h
0x180006c73  mov     r13d, 0C04h
0x180006c79  movzx   r14d, ax
0x180006c7d  cmp     ax, r15w
0x180006c81  jnz     short loc_180006CC5
0x180006c83  mov     r9d, 20h ; ' '; cchData
0x180006c89  lea     r8, [rbp+3F0h+LCData]; lpLCData
0x180006c90  mov     ecx, r15d; Locale
0x180006c93  mov     r14d, r13d
0x180006c96  lea     edx, [r9-18h]; LCType
0x180006c9a  call    cs:__imp_GetLocaleInfoW
0x180006ca0  test    eax, eax
0x180006ca2  jz      short loc_180006CC5
0x180006ca4  mov     r8d, 3; MaxCount
0x180006caa  lea     rdx, word_18000E96C; String2
0x180006cb1  lea     rcx, [rbp+3F0h+LCData]; String1
0x180006cb8  call    wcsncmp_0
0x180006cbd  test    eax, eax
0x180006cbf  jz      short loc_180006CC5
0x180006cc1  movzx   r14d, r15w
0x180006cc5  lea     r9, [rbp+3F0h+var_400]
0x180006cc9  movzx   ecx, r14w
0x180006ccd  lea     r8, [rbp+3F0h+var_350]
0x180006cd4  lea     rdx, [rsp+4F0h+var_4B0]
0x180006cd9  call    LookupLangID
0x180006cde  test    eax, eax
0x180006ce0  jz      loc_180006FA7
0x180006ce6  mov     r9, [rsp+4F0h+FilePart]
0x180006ceb  lea     r8, [rsp+4F0h+var_4B0]
0x180006cf0  mov     rdx, rsi
0x180006cf3  mov     rcx, rdi
0x180006cf6  call    LoadMUIFile
0x180006cfb  mov     rbx, rax
0x180006cfe  test    rax, rax
0x180006d01  jnz     loc_180006FB0
0x180006d07  mov     r9, [rsp+4F0h+FilePart]
0x180006d0c  lea     r8, [rbp+3F0h+var_350]
0x180006d13  mov     rdx, rsi
0x180006d16  mov     rcx, rdi
0x180006d19  call    LoadMUIFile
0x180006d1e  mov     rbx, rax
0x180006d21  test    rax, rax
0x180006d24  jnz     loc_180006FB0
0x180006d2a  cmp     [rbp+3F0h+var_400], r12w
0x180006d2f  jz      short loc_180006D51
0x180006d31  mov     r9, [rsp+4F0h+FilePart]
0x180006d36  lea     r8, [rbp+3F0h+var_400]
0x180006d3a  mov     rdx, rsi
0x180006d3d  mov     rcx, rdi
0x180006d40  call    LoadMUIFile
0x180006d45  mov     rbx, rax
0x180006d48  test    rax, rax
0x180006d4b  jnz     loc_180006FB0
0x180006d51  cmp     r14w, r13w
0x180006d55  jz      loc_180006CC1
0x180006d5b  call    cs:__imp_GetSystemDefaultUILanguage
0x180006d61  movzx   r15d, ax
0x180006d65  cmp     ax, r14w
0x180006d69  jz      loc_180006DFA
0x180006d6f  lea     r9, [rbp+3F0h+var_400]
0x180006d73  movzx   ecx, ax
0x180006d76  lea     r8, [rbp+3F0h+var_350]
0x180006d7d  lea     rdx, [rsp+4F0h+var_4B0]
0x180006d82  call    LookupLangID
0x180006d87  test    eax, eax
0x180006d89  jz      loc_180006E5F
0x180006d8f  mov     r9, [rsp+4F0h+FilePart]
0x180006d94  lea     r8, [rsp+4F0h+var_4B0]
0x180006d99  mov     rdx, rsi
0x180006d9c  mov     rcx, rdi
0x180006d9f  call    LoadMUIFile
0x180006da4  mov     rbx, rax
0x180006da7  test    rax, rax
0x180006daa  jnz     loc_180006FB0
0x180006db0  mov     r9, [rsp+4F0h+FilePart]
0x180006db5  lea     r8, [rbp+3F0h+var_350]
0x180006dbc  mov     rdx, rsi
0x180006dbf  mov     rcx, rdi
0x180006dc2  call    LoadMUIFile
0x180006dc7  mov     rbx, rax
0x180006dca  test    rax, rax
0x180006dcd  jnz     loc_180006FB0
0x180006dd3  cmp     [rbp+3F0h+var_400], r12w
0x180006dd8  jz      short loc_180006DFA
0x180006dda  mov     r9, [rsp+4F0h+FilePart]
0x180006ddf  lea     r8, [rbp+3F0h+var_400]
0x180006de3  mov     rdx, rsi
0x180006de6  mov     rcx, rdi
0x180006de9  call    LoadMUIFile
0x180006dee  mov     rbx, rax
0x180006df1  test    rax, rax
0x180006df4  jnz     loc_180006FB0
0x180006dfa  mov     ecx, 409h
0x180006dff  cmp     cx, r14w
0x180006e03  jz      short loc_180006E40
0x180006e05  cmp     cx, r15w
0x180006e09  jz      short loc_180006E40
0x180006e0b  xor     r9d, r9d
0x180006e0e  lea     r8, [rbp+3F0h+var_350]
0x180006e15  lea     rdx, [rsp+4F0h+var_4B0]
0x180006e1a  call    LookupLangID
0x180006e1f  mov     r9, [rsp+4F0h+FilePart]
0x180006e24  lea     r8, [rsp+4F0h+var_4B0]
0x180006e29  mov     rdx, rsi
0x180006e2c  mov     rcx, rdi
0x180006e2f  call    LoadMUIFile
0x180006e34  mov     rbx, rax
0x180006e37  test    rax, rax
0x180006e3a  jnz     loc_180006FB0
0x180006e40  mov     r9, [rsp+4F0h+FilePart]
0x180006e45  xor     r8d, r8d
0x180006e48  mov     rdx, rsi
0x180006e4b  mov     rcx, rdi
0x180006e4e  call    LoadMUIFile
0x180006e53  mov     rbx, rax
0x180006e56  test    rax, rax
0x180006e59  jnz     loc_180006FB0
0x180006e5f  test    dil, 1
0x180006e63  jz      loc_180006FDE
0x180006e69  mov     rcx, rdi; hLibModule
0x180006e6c  call    cs:__imp_FreeLibrary
0x180006e72  call    GetOSType
0x180006e77  test    al, 38h
0x180006e79  jz      loc_180006FBE
0x180006e7f  mov     rax, [rsp+4F0h+FilePart]
0x180006e84  lea     r8, aSS; "%s\\%s"
0x180006e8b  mov     r9, rsi
0x180006e8e  mov     [rsp+4F0h+lpBuffer], rax
0x180006e93  mov     edx, 104h; unsigned __int64
0x180006e98  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x180006e9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006ea4  xor     r8d, r8d
0x180006ea7  lea     rcx, [rbp+3F0h+Buffer]
0x180006eae  lea     edx, [r8+1]
0x180006eb2  call    MapMUIFile
0x180006eb7  jmp     loc_180006FDB
0x180006ebc  test    al, 3
0x180006ebe  jz      short loc_180006E5F
0x180006ec0  call    GetInstallLanguage
0x180006ec5  lea     r9, [rbp+3F0h+var_400]
0x180006ec9  movzx   ecx, ax
0x180006ecc  lea     r8, [rbp+3F0h+var_350]
0x180006ed3  movzx   r14d, ax
0x180006ed7  lea     rdx, [rsp+4F0h+var_4B0]
0x180006edc  call    LookupLangID
0x180006ee1  test    eax, eax
0x180006ee3  jz      loc_180006E5F
0x180006ee9  mov     r9, [rsp+4F0h+FilePart]
0x180006eee  lea     r8, [rsp+4F0h+var_4B0]
0x180006ef3  mov     rdx, rsi
0x180006ef6  mov     rcx, rdi
0x180006ef9  call    LoadMUIFile
0x180006efe  mov     rbx, rax
0x180006f01  test    rax, rax
0x180006f04  jnz     loc_180006FB0
0x180006f0a  mov     r9, [rsp+4F0h+FilePart]
0x180006f0f  lea     r8, [rbp+3F0h+var_350]
0x180006f16  mov     rdx, rsi
0x180006f19  mov     rcx, rdi
0x180006f1c  call    LoadMUIFile
0x180006f21  mov     rbx, rax
0x180006f24  test    rax, rax
0x180006f27  jnz     loc_180006FB0
0x180006f2d  cmp     [rbp+3F0h+var_400], r12w
0x180006f32  jz      short loc_180006F50
0x180006f34  mov     r9, [rsp+4F0h+FilePart]
0x180006f39  lea     r8, [rbp+3F0h+var_400]
0x180006f3d  mov     rdx, rsi
0x180006f40  mov     rcx, rdi
0x180006f43  call    LoadMUIFile
0x180006f48  mov     rbx, rax
0x180006f4b  test    rax, rax
0x180006f4e  jnz     short loc_180006FB0
0x180006f50  mov     ecx, 409h
0x180006f55  cmp     cx, r14w
0x180006f59  jz      short loc_180006F8C
0x180006f5b  xor     r9d, r9d
0x180006f5e  lea     r8, [rbp+3F0h+var_350]
0x180006f65  lea     rdx, [rsp+4F0h+var_4B0]
0x180006f6a  call    LookupLangID
0x180006f6f  mov     r9, [rsp+4F0h+FilePart]
0x180006f74  lea     r8, [rsp+4F0h+var_4B0]
0x180006f79  mov     rdx, rsi
0x180006f7c  mov     rcx, rdi
0x180006f7f  call    LoadMUIFile
0x180006f84  mov     rbx, rax
0x180006f87  test    rax, rax
0x180006f8a  jnz     short loc_180006FB0
0x180006f8c  mov     r9, [rsp+4F0h+FilePart]
0x180006f91  xor     r8d, r8d
0x180006f94  mov     rdx, rsi
0x180006f97  mov     rcx, rdi
0x180006f9a  call    LoadMUIFile
0x180006f9f  mov     rbx, rax
0x180006fa2  test    rax, rax
0x180006fa5  jnz     short loc_180006FB0
0x180006fa7  test    rbx, rbx
0x180006faa  jz      loc_180006E5F
0x180006fb0  mov     rcx, rdi; hLibModule
0x180006fb3  call    cs:__imp_FreeLibrary
0x180006fb9  mov     rax, rbx
0x180006fbc  jmp     short loc_180006FEE
0x180006fbe  call    GetOSType
0x180006fc3  test    al, 26h
0x180006fc5  lea     rcx, LibFileName; "pwrshplugin.dll"
0x180006fcc  mov     r8d, r12d
0x180006fcf  setnz   r8b; dwFlags
0x180006fd3  xor     edx, edx; hFile
0x180006fd5  call    cs:__imp_LoadLibraryExW
0x180006fdb  mov     rdi, rax
0x180006fde  mov     rax, rdi
0x180006fe1  jmp     short loc_180006FEE
0x180006fe3  mov     rcx, rdi; hLibModule
0x180006fe6  call    cs:__imp_FreeLibrary
0x180006fec  xor     eax, eax
0x180006fee  mov     rcx, [rbp+3F0h+var_50]
0x180006ff5  xor     rcx, rsp; StackCookie
0x180006ff8  call    __security_check_cookie
0x180006ffd  add     rsp, 4B8h
0x180007004  pop     r15
0x180007006  pop     r14
0x180007008  pop     r13
0x18000700a  pop     r12
0x18000700c  pop     rdi
0x18000700d  pop     rsi
0x18000700e  pop     rbx
0x18000700f  pop     rbp
0x180007010  retn
```
