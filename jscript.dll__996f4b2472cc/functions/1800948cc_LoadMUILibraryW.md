# LoadMUILibraryW

- ea: `0x1800948cc`
- end: `0x180094d8d`
- name: `LoadMUILibraryW`
- size: `1217`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180088504`

## callees

- `0x180043d14`
- `0x180094164`
- `0x1800941ec`
- `0x180094314`
- `0x180094448`
- `0x1800944bc`
- `0x180094644`
- `0x1800948cc`
- `0x1800966e0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18009492d`
- `KERNEL32!LoadLibraryExW` at `0x180094d3d`
- `KERNEL32!LoadLibraryExW` at `0x18009492d`
- `KERNEL32!LoadLibraryExW` at `0x180094d3d`
- `KERNEL32!FreeLibrary` at `0x180094c7a`
- `KERNEL32!FreeLibrary` at `0x180094d19`
- `KERNEL32!FreeLibrary` at `0x180094d54`
- `KERNEL32!FreeLibrary` at `0x180094c7a`
- `KERNEL32!FreeLibrary` at `0x180094d19`
- `KERNEL32!FreeLibrary` at `0x180094d54`
- `KERNEL32!SearchPathW` at `0x180094976`
- `KERNEL32!SearchPathW` at `0x180094976`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180094ab5`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180094ab5`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800949f1`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800949f1`
- `KERNEL32!FindResourceExW` at `0x1800949c2`
- `KERNEL32!FindResourceExW` at `0x1800949c2`

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
  dword_1800B9138 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800B9138 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_1800B9138 & 0x20) != 0 )
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
      if ( (dword_1800B9138 & 4) == 0 )
      {
        if ( (dword_1800B9138 & 3) != 0 )
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
    if ( (dword_1800B9138 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
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
0x1800948cc  mov     [rsp-8+arg_8], rbx
0x1800948d1  push    rbp
0x1800948d2  push    rsi
0x1800948d3  push    rdi
0x1800948d4  push    r12
0x1800948d6  push    r13
0x1800948d8  push    r14
0x1800948da  push    r15
0x1800948dc  lea     rbp, [rsp-370h]
0x1800948e4  sub     rsp, 470h
0x1800948eb  mov     rax, cs:__security_cookie
0x1800948f2  xor     rax, rsp
0x1800948f5  mov     [rbp+3A0h+var_40], rax
0x1800948fc  xor     r13d, r13d
0x1800948ff  movzx   ebx, r8w
0x180094903  mov     [rsp+4A0h+FilePart], r13
0x180094908  mov     r12, rcx
0x18009490b  test    rcx, rcx
0x18009490e  jz      loc_180094D60
0x180094914  call    GetOSType
0x180094919  mov     cs:dword_1800B9138, eax
0x18009491f  xor     edx, edx; hFile
0x180094921  and     eax, 20h
0x180094924  mov     rcx, r12; lpLibFileName
0x180094927  or      eax, 2
0x18009492a  mov     r8d, eax; dwFlags
0x18009492d  call    cs:__imp_LoadLibraryExW
0x180094934  nop     dword ptr [rax+rax+00h]
0x180094939  mov     rdi, rax
0x18009493c  test    rax, rax
0x18009493f  jz      loc_180094D60
0x180094945  test    byte ptr cs:dword_1800B9138, 20h
0x18009494c  jnz     loc_180094D62
0x180094952  lea     rax, [rsp+4A0h+FilePart]
0x180094957  mov     r9d, 104h; nBufferLength
0x18009495d  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180094962  xor     r8d, r8d; lpExtension
0x180094965  lea     rax, [rbp+3A0h+Buffer]
0x18009496c  mov     rdx, r12; lpFileName
0x18009496f  xor     ecx, ecx; lpPath
0x180094971  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180094976  call    cs:__imp_SearchPathW
0x18009497d  nop     dword ptr [rax+rax+00h]
0x180094982  test    eax, eax
0x180094984  jz      loc_180094D51
0x18009498a  mov     rcx, [rsp+4A0h+FilePart]
0x18009498f  test    rcx, rcx
0x180094992  jnz     short loc_1800949A5
0x180094994  lea     rax, [rbp+3A0h+Buffer]
0x18009499b  mov     esi, r13d
0x18009499e  mov     [rsp+4A0h+FilePart], rax
0x1800949a3  jmp     short loc_1800949B1
0x1800949a5  lea     rsi, [rbp+3A0h+Buffer]
0x1800949ac  mov     [rcx-2], r13w
0x1800949b1  xor     r9d, r9d; wLanguage
0x1800949b4  lea     rdx, Type; "MUI"
0x1800949bb  mov     rcx, rdi; hModule
0x1800949be  lea     r8d, [r9+1]; lpName
0x1800949c2  call    cs:__imp_FindResourceExW
0x1800949c9  nop     dword ptr [rax+rax+00h]
0x1800949ce  test    rax, rax
0x1800949d1  jz      loc_180094C6D
0x1800949d7  test    bx, bx
0x1800949da  jnz     loc_180094CCD
0x1800949e0  mov     eax, cs:dword_1800B9138
0x1800949e6  test    al, 4
0x1800949e8  jz      loc_180094B72
0x1800949ee  mov     rbx, r13
0x1800949f1  call    cs:__imp_GetUserDefaultUILanguage
0x1800949f8  nop     dword ptr [rax+rax+00h]
0x1800949fd  mov     r15d, 404h
0x180094a03  movzx   r14d, ax
0x180094a07  cmp     ax, r15w
0x180094a0b  jnz     short loc_180094A16
0x180094a0d  call    GetCHTLangauge
0x180094a12  movzx   r14d, ax
0x180094a16  lea     r9, [rbp+3A0h+var_3B0]
0x180094a1a  movzx   ecx, r14w
0x180094a1e  lea     r8, [rbp+3A0h+var_300]
0x180094a25  lea     rdx, [rsp+4A0h+var_460]
0x180094a2a  call    LookupLangID
0x180094a2f  test    eax, eax
0x180094a31  jz      loc_180094D0D
0x180094a37  mov     r9, [rsp+4A0h+FilePart]
0x180094a3c  lea     r8, [rsp+4A0h+var_460]
0x180094a41  mov     rdx, rsi
0x180094a44  mov     rcx, rdi
0x180094a47  call    LoadMUIFile
0x180094a4c  mov     rbx, rax
0x180094a4f  test    rax, rax
0x180094a52  jnz     loc_180094D16
0x180094a58  mov     r9, [rsp+4A0h+FilePart]
0x180094a5d  lea     r8, [rbp+3A0h+var_300]
0x180094a64  mov     rdx, rsi
0x180094a67  mov     rcx, rdi
0x180094a6a  call    LoadMUIFile
0x180094a6f  mov     rbx, rax
0x180094a72  test    rax, rax
0x180094a75  jnz     loc_180094D16
0x180094a7b  cmp     [rbp+3A0h+var_3B0], r13w
0x180094a80  jz      short loc_180094AA2
0x180094a82  mov     r9, [rsp+4A0h+FilePart]
0x180094a87  lea     r8, [rbp+3A0h+var_3B0]
0x180094a8b  mov     rdx, rsi
0x180094a8e  mov     rcx, rdi
0x180094a91  call    LoadMUIFile
0x180094a96  mov     rbx, rax
0x180094a99  test    rax, rax
0x180094a9c  jnz     loc_180094D16
0x180094aa2  mov     eax, 0C04h
0x180094aa7  cmp     r14w, ax
0x180094aab  jnz     short loc_180094AB5
0x180094aad  mov     r14d, r15d
0x180094ab0  jmp     loc_180094A16
0x180094ab5  call    cs:__imp_GetSystemDefaultUILanguage
0x180094abc  nop     dword ptr [rax+rax+00h]
0x180094ac1  movzx   r15d, ax
0x180094ac5  cmp     ax, r14w
0x180094ac9  jz      loc_180094B5A
0x180094acf  lea     r9, [rbp+3A0h+var_3B0]
0x180094ad3  movzx   ecx, ax
0x180094ad6  lea     r8, [rbp+3A0h+var_300]
0x180094add  lea     rdx, [rsp+4A0h+var_460]
0x180094ae2  call    LookupLangID
0x180094ae7  test    eax, eax
0x180094ae9  jz      loc_180094C6D
0x180094aef  mov     r9, [rsp+4A0h+FilePart]
0x180094af4  lea     r8, [rsp+4A0h+var_460]
0x180094af9  mov     rdx, rsi
0x180094afc  mov     rcx, rdi
0x180094aff  call    LoadMUIFile
0x180094b04  mov     rbx, rax
0x180094b07  test    rax, rax
0x180094b0a  jnz     loc_180094D16
0x180094b10  mov     r9, [rsp+4A0h+FilePart]
0x180094b15  lea     r8, [rbp+3A0h+var_300]
0x180094b1c  mov     rdx, rsi
0x180094b1f  mov     rcx, rdi
0x180094b22  call    LoadMUIFile
0x180094b27  mov     rbx, rax
0x180094b2a  test    rax, rax
0x180094b2d  jnz     loc_180094D16
0x180094b33  cmp     [rbp+3A0h+var_3B0], r13w
0x180094b38  jz      short loc_180094B5A
0x180094b3a  mov     r9, [rsp+4A0h+FilePart]
0x180094b3f  lea     r8, [rbp+3A0h+var_3B0]
0x180094b43  mov     rdx, rsi
0x180094b46  mov     rcx, rdi
0x180094b49  call    LoadMUIFile
0x180094b4e  mov     rbx, rax
0x180094b51  test    rax, rax
0x180094b54  jnz     loc_180094D16
0x180094b5a  mov     ecx, 409h
0x180094b5f  cmp     cx, r14w
0x180094b63  jz      loc_180094C4E
0x180094b69  cmp     cx, r15w
0x180094b6d  jmp     loc_180094C17
0x180094b72  test    al, 3
0x180094b74  jz      loc_180094C6D
0x180094b7a  call    GetInstallLanguage
0x180094b7f  lea     r9, [rbp+3A0h+var_3B0]
0x180094b83  movzx   ecx, ax
0x180094b86  lea     r8, [rbp+3A0h+var_300]
0x180094b8d  movzx   r14d, ax
0x180094b91  lea     rdx, [rsp+4A0h+var_460]
0x180094b96  call    LookupLangID
0x180094b9b  test    eax, eax
0x180094b9d  jz      loc_180094C6D
0x180094ba3  mov     r9, [rsp+4A0h+FilePart]
0x180094ba8  lea     r8, [rsp+4A0h+var_460]
0x180094bad  mov     rdx, rsi
0x180094bb0  mov     rcx, rdi
0x180094bb3  call    LoadMUIFile
0x180094bb8  mov     rbx, rax
0x180094bbb  test    rax, rax
0x180094bbe  jnz     loc_180094D16
0x180094bc4  mov     r9, [rsp+4A0h+FilePart]
0x180094bc9  lea     r8, [rbp+3A0h+var_300]
0x180094bd0  mov     rdx, rsi
0x180094bd3  mov     rcx, rdi
0x180094bd6  call    LoadMUIFile
0x180094bdb  mov     rbx, rax
0x180094bde  test    rax, rax
0x180094be1  jnz     loc_180094D16
0x180094be7  cmp     [rbp+3A0h+var_3B0], r13w
0x180094bec  jz      short loc_180094C0E
0x180094bee  mov     r9, [rsp+4A0h+FilePart]
0x180094bf3  lea     r8, [rbp+3A0h+var_3B0]
0x180094bf7  mov     rdx, rsi
0x180094bfa  mov     rcx, rdi
0x180094bfd  call    LoadMUIFile
0x180094c02  mov     rbx, rax
0x180094c05  test    rax, rax
0x180094c08  jnz     loc_180094D16
0x180094c0e  mov     ecx, 409h
0x180094c13  cmp     cx, r14w
0x180094c17  jz      short loc_180094C4E
0x180094c19  xor     r9d, r9d
0x180094c1c  lea     r8, [rbp+3A0h+var_300]
0x180094c23  lea     rdx, [rsp+4A0h+var_460]
0x180094c28  call    LookupLangID
0x180094c2d  mov     r9, [rsp+4A0h+FilePart]
0x180094c32  lea     r8, [rsp+4A0h+var_460]
0x180094c37  mov     rdx, rsi
0x180094c3a  mov     rcx, rdi
0x180094c3d  call    LoadMUIFile
0x180094c42  mov     rbx, rax
0x180094c45  test    rax, rax
0x180094c48  jnz     loc_180094D16
0x180094c4e  mov     r9, [rsp+4A0h+FilePart]
0x180094c53  xor     r8d, r8d
0x180094c56  mov     rdx, rsi
0x180094c59  mov     rcx, rdi
0x180094c5c  call    LoadMUIFile
0x180094c61  mov     rbx, rax
0x180094c64  test    rax, rax
0x180094c67  jnz     loc_180094D16
0x180094c6d  test    dil, 1
0x180094c71  jz      loc_180094D4C
0x180094c77  mov     rcx, rdi; hLibModule
0x180094c7a  call    cs:__imp_FreeLibrary
0x180094c81  nop     dword ptr [rax+rax+00h]
0x180094c86  call    GetOSType
0x180094c8b  test    al, 38h
0x180094c8d  jz      loc_180094D2A
0x180094c93  mov     rax, [rsp+4A0h+FilePart]
0x180094c98  lea     r8, aSS; "%s\\%s"
0x180094c9f  mov     r9, rsi
0x180094ca2  mov     [rsp+4A0h+lpBuffer], rax
0x180094ca7  mov     edx, 104h; unsigned __int64
0x180094cac  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180094cb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180094cb8  xor     r8d, r8d
0x180094cbb  lea     rcx, [rbp+3A0h+Buffer]
0x180094cc2  lea     edx, [r8+1]
0x180094cc6  call    MapMUIFile
0x180094ccb  jmp     short loc_180094D49
0x180094ccd  test    byte ptr cs:dword_1800B9138, 7
0x180094cd4  jz      short loc_180094C6D
0x180094cd6  xor     r9d, r9d
0x180094cd9  lea     r8, [rbp+3A0h+var_300]
0x180094ce0  lea     rdx, [rsp+4A0h+var_460]
0x180094ce5  movzx   ecx, bx
0x180094ce8  call    LookupLangID
0x180094ced  test    eax, eax
0x180094cef  jz      loc_180094C6D
0x180094cf5  mov     r9, [rsp+4A0h+FilePart]
0x180094cfa  lea     r8, [rsp+4A0h+var_460]
0x180094cff  mov     rdx, rsi
0x180094d02  mov     rcx, rdi
0x180094d05  call    LoadMUIFile
0x180094d0a  mov     rbx, rax
0x180094d0d  test    rbx, rbx
0x180094d10  jz      loc_180094C6D
0x180094d16  mov     rcx, rdi; hLibModule
0x180094d19  call    cs:__imp_FreeLibrary
0x180094d20  nop     dword ptr [rax+rax+00h]
0x180094d25  mov     rax, rbx
0x180094d28  jmp     short loc_180094D62
0x180094d2a  call    GetOSType
0x180094d2f  test    al, 26h
0x180094d31  mov     r8d, r13d
0x180094d34  mov     rcx, r12; lpLibFileName
0x180094d37  setnz   r8b; dwFlags
0x180094d3b  xor     edx, edx; hFile
0x180094d3d  call    cs:__imp_LoadLibraryExW
0x180094d44  nop     dword ptr [rax+rax+00h]
0x180094d49  mov     rdi, rax
0x180094d4c  mov     rax, rdi
0x180094d4f  jmp     short loc_180094D62
0x180094d51  mov     rcx, rdi; hLibModule
0x180094d54  call    cs:__imp_FreeLibrary
0x180094d5b  nop     dword ptr [rax+rax+00h]
0x180094d60  xor     eax, eax
0x180094d62  mov     rcx, [rbp+3A0h+var_40]
0x180094d69  xor     rcx, rsp; StackCookie
0x180094d6c  call    __security_check_cookie
0x180094d71  mov     rbx, [rsp+4A0h+arg_8]
0x180094d79  add     rsp, 470h
0x180094d80  pop     r15
0x180094d82  pop     r14
0x180094d84  pop     r13
0x180094d86  pop     r12
0x180094d88  pop     rdi
0x180094d89  pop     rsi
0x180094d8a  pop     rbp
0x180094d8b  retn
```
