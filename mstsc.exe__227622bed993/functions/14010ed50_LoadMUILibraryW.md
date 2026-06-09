# LoadMUILibraryW

- ea: `0x14010ed50`
- end: `0x14010f1c3`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1400fa518`

## callees

- `0x140008a78`
- `0x14010e670`
- `0x14010e6f0`
- `0x14010e800`
- `0x14010e928`
- `0x14010e99c`
- `0x14010eb10`
- `0x14010ed50`
- `0x140111220`

## import_xrefs

- `KERNEL32!SearchPathW` at `0x14010eded`
- `KERNEL32!SearchPathW` at `0x14010eded`
- `KERNEL32!FindResourceExW` at `0x14010ee33`
- `KERNEL32!FindResourceExW` at `0x14010ee33`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14010ee53`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14010ee53`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x14010ef11`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x14010ef11`
- `KERNEL32!LoadLibraryExW` at `0x14010edaa`
- `KERNEL32!LoadLibraryExW` at `0x14010f187`
- `KERNEL32!LoadLibraryExW` at `0x14010edaa`
- `KERNEL32!LoadLibraryExW` at `0x14010f187`
- `KERNEL32!FreeLibrary` at `0x14010f022`
- `KERNEL32!FreeLibrary` at `0x14010f169`
- `KERNEL32!FreeLibrary` at `0x14010f198`
- `KERNEL32!FreeLibrary` at `0x14010f022`
- `KERNEL32!FreeLibrary` at `0x14010f169`
- `KERNEL32!FreeLibrary` at `0x14010f198`

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
  dword_140152CB8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_140152CB8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_140152CB8 & 0x20) != 0 )
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
    if ( (dword_140152CB8 & 4) != 0 )
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
    else if ( (dword_140152CB8 & 3) != 0 )
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
0x14010ed50  push    rbp
0x14010ed52  push    rbx
0x14010ed53  push    rsi
0x14010ed54  push    rdi
0x14010ed55  push    r12
0x14010ed57  push    r13
0x14010ed59  push    r14
0x14010ed5b  push    r15
0x14010ed5d  lea     rbp, [rsp-378h]
0x14010ed65  sub     rsp, 478h
0x14010ed6c  mov     rax, cs:__security_cookie
0x14010ed73  xor     rax, rsp
0x14010ed76  mov     [rbp+3B0h+var_50], rax
0x14010ed7d  xor     r13d, r13d
0x14010ed80  mov     r12, rcx
0x14010ed83  mov     [rsp+4B0h+FilePart], r13
0x14010ed88  test    rcx, rcx
0x14010ed8b  jz      loc_14010F19E
0x14010ed91  call    GetOSType
0x14010ed96  mov     cs:dword_140152CB8, eax
0x14010ed9c  xor     edx, edx; hFile
0x14010ed9e  and     eax, 20h
0x14010eda1  mov     rcx, r12; lpLibFileName
0x14010eda4  or      eax, 2
0x14010eda7  mov     r8d, eax; dwFlags
0x14010edaa  call    cs:__imp_LoadLibraryExW
0x14010edb0  mov     rdi, rax
0x14010edb3  test    rax, rax
0x14010edb6  jz      loc_14010F19E
0x14010edbc  test    byte ptr cs:dword_140152CB8, 20h
0x14010edc3  jnz     loc_14010F1A0
0x14010edc9  lea     rax, [rsp+4B0h+FilePart]
0x14010edce  mov     r9d, 104h; nBufferLength
0x14010edd4  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x14010edd9  xor     r8d, r8d; lpExtension
0x14010eddc  lea     rax, [rbp+3B0h+Buffer]
0x14010ede3  mov     rdx, r12; lpFileName
0x14010ede6  xor     ecx, ecx; lpPath
0x14010ede8  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x14010eded  call    cs:__imp_SearchPathW
0x14010edf3  test    eax, eax
0x14010edf5  jz      loc_14010F195
0x14010edfb  mov     rcx, [rsp+4B0h+FilePart]
0x14010ee00  test    rcx, rcx
0x14010ee03  jnz     short loc_14010EE16
0x14010ee05  lea     rax, [rbp+3B0h+Buffer]
0x14010ee0c  mov     esi, r13d
0x14010ee0f  mov     [rsp+4B0h+FilePart], rax
0x14010ee14  jmp     short loc_14010EE22
0x14010ee16  lea     rsi, [rbp+3B0h+Buffer]
0x14010ee1d  mov     [rcx-2], r13w
0x14010ee22  xor     r9d, r9d; wLanguage
0x14010ee25  lea     rdx, aMui; "MUI"
0x14010ee2c  mov     rcx, rdi; hModule
0x14010ee2f  lea     r8d, [r9+1]; lpName
0x14010ee33  call    cs:__imp_FindResourceExW
0x14010ee39  test    rax, rax
0x14010ee3c  jz      loc_14010F015
0x14010ee42  mov     eax, cs:dword_140152CB8
0x14010ee48  test    al, 4
0x14010ee4a  jz      loc_14010F072
0x14010ee50  mov     rbx, r13
0x14010ee53  call    cs:__imp_GetUserDefaultUILanguage
0x14010ee59  mov     r15d, 404h
0x14010ee5f  movzx   r14d, ax
0x14010ee63  cmp     ax, r15w
0x14010ee67  jnz     short loc_14010EE72
0x14010ee69  call    GetCHTLangauge
0x14010ee6e  movzx   r14d, ax
0x14010ee72  lea     r9, [rbp+3B0h+var_3C0]
0x14010ee76  movzx   ecx, r14w
0x14010ee7a  lea     r8, [rbp+3B0h+var_310]
0x14010ee81  lea     rdx, [rsp+4B0h+var_470]
0x14010ee86  call    LookupLangID
0x14010ee8b  test    eax, eax
0x14010ee8d  jz      loc_14010F15D
0x14010ee93  mov     r9, [rsp+4B0h+FilePart]
0x14010ee98  lea     r8, [rsp+4B0h+var_470]
0x14010ee9d  mov     rdx, rsi
0x14010eea0  mov     rcx, rdi
0x14010eea3  call    LoadMUIFile
0x14010eea8  mov     rbx, rax
0x14010eeab  test    rax, rax
0x14010eeae  jnz     loc_14010F166
0x14010eeb4  mov     r9, [rsp+4B0h+FilePart]
0x14010eeb9  lea     r8, [rbp+3B0h+var_310]
0x14010eec0  mov     rdx, rsi
0x14010eec3  mov     rcx, rdi
0x14010eec6  call    LoadMUIFile
0x14010eecb  mov     rbx, rax
0x14010eece  test    rax, rax
0x14010eed1  jnz     loc_14010F166
0x14010eed7  cmp     [rbp+3B0h+var_3C0], r13w
0x14010eedc  jz      short loc_14010EEFE
0x14010eede  mov     r9, [rsp+4B0h+FilePart]
0x14010eee3  lea     r8, [rbp+3B0h+var_3C0]
0x14010eee7  mov     rdx, rsi
0x14010eeea  mov     rcx, rdi
0x14010eeed  call    LoadMUIFile
0x14010eef2  mov     rbx, rax
0x14010eef5  test    rax, rax
0x14010eef8  jnz     loc_14010F166
0x14010eefe  mov     eax, 0C04h
0x14010ef03  cmp     r14w, ax
0x14010ef07  jnz     short loc_14010EF11
0x14010ef09  mov     r14d, r15d
0x14010ef0c  jmp     loc_14010EE72
0x14010ef11  call    cs:__imp_GetSystemDefaultUILanguage
0x14010ef17  movzx   r15d, ax
0x14010ef1b  cmp     ax, r14w
0x14010ef1f  jz      loc_14010EFB0
0x14010ef25  lea     r9, [rbp+3B0h+var_3C0]
0x14010ef29  movzx   ecx, ax
0x14010ef2c  lea     r8, [rbp+3B0h+var_310]
0x14010ef33  lea     rdx, [rsp+4B0h+var_470]
0x14010ef38  call    LookupLangID
0x14010ef3d  test    eax, eax
0x14010ef3f  jz      loc_14010F015
0x14010ef45  mov     r9, [rsp+4B0h+FilePart]
0x14010ef4a  lea     r8, [rsp+4B0h+var_470]
0x14010ef4f  mov     rdx, rsi
0x14010ef52  mov     rcx, rdi
0x14010ef55  call    LoadMUIFile
0x14010ef5a  mov     rbx, rax
0x14010ef5d  test    rax, rax
0x14010ef60  jnz     loc_14010F166
0x14010ef66  mov     r9, [rsp+4B0h+FilePart]
0x14010ef6b  lea     r8, [rbp+3B0h+var_310]
0x14010ef72  mov     rdx, rsi
0x14010ef75  mov     rcx, rdi
0x14010ef78  call    LoadMUIFile
0x14010ef7d  mov     rbx, rax
0x14010ef80  test    rax, rax
0x14010ef83  jnz     loc_14010F166
0x14010ef89  cmp     [rbp+3B0h+var_3C0], r13w
0x14010ef8e  jz      short loc_14010EFB0
0x14010ef90  mov     r9, [rsp+4B0h+FilePart]
0x14010ef95  lea     r8, [rbp+3B0h+var_3C0]
0x14010ef99  mov     rdx, rsi
0x14010ef9c  mov     rcx, rdi
0x14010ef9f  call    LoadMUIFile
0x14010efa4  mov     rbx, rax
0x14010efa7  test    rax, rax
0x14010efaa  jnz     loc_14010F166
0x14010efb0  mov     ecx, 409h
0x14010efb5  cmp     cx, r14w
0x14010efb9  jz      short loc_14010EFF6
0x14010efbb  cmp     cx, r15w
0x14010efbf  jz      short loc_14010EFF6
0x14010efc1  xor     r9d, r9d
0x14010efc4  lea     r8, [rbp+3B0h+var_310]
0x14010efcb  lea     rdx, [rsp+4B0h+var_470]
0x14010efd0  call    LookupLangID
0x14010efd5  mov     r9, [rsp+4B0h+FilePart]
0x14010efda  lea     r8, [rsp+4B0h+var_470]
0x14010efdf  mov     rdx, rsi
0x14010efe2  mov     rcx, rdi
0x14010efe5  call    LoadMUIFile
0x14010efea  mov     rbx, rax
0x14010efed  test    rax, rax
0x14010eff0  jnz     loc_14010F166
0x14010eff6  mov     r9, [rsp+4B0h+FilePart]
0x14010effb  xor     r8d, r8d
0x14010effe  mov     rdx, rsi
0x14010f001  mov     rcx, rdi
0x14010f004  call    LoadMUIFile
0x14010f009  mov     rbx, rax
0x14010f00c  test    rax, rax
0x14010f00f  jnz     loc_14010F166
0x14010f015  test    dil, 1
0x14010f019  jz      loc_14010F190
0x14010f01f  mov     rcx, rdi; hLibModule
0x14010f022  call    cs:__imp_FreeLibrary
0x14010f028  call    GetOSType
0x14010f02d  test    al, 38h
0x14010f02f  jz      loc_14010F174
0x14010f035  mov     rax, [rsp+4B0h+FilePart]
0x14010f03a  lea     r8, aSS_0; "%s\\%s"
0x14010f041  mov     r9, rsi
0x14010f044  mov     [rsp+4B0h+lpBuffer], rax
0x14010f049  mov     edx, 104h; unsigned __int64
0x14010f04e  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x14010f055  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010f05a  xor     r8d, r8d
0x14010f05d  lea     rcx, [rbp+3B0h+Buffer]
0x14010f064  lea     edx, [r8+1]
0x14010f068  call    MapMUIFile
0x14010f06d  jmp     loc_14010F18D
0x14010f072  test    al, 3
0x14010f074  jz      short loc_14010F015
0x14010f076  call    GetInstallLanguage
0x14010f07b  lea     r9, [rbp+3B0h+var_3C0]
0x14010f07f  movzx   ecx, ax
0x14010f082  lea     r8, [rbp+3B0h+var_310]
0x14010f089  movzx   r14d, ax
0x14010f08d  lea     rdx, [rsp+4B0h+var_470]
0x14010f092  call    LookupLangID
0x14010f097  test    eax, eax
0x14010f099  jz      loc_14010F015
0x14010f09f  mov     r9, [rsp+4B0h+FilePart]
0x14010f0a4  lea     r8, [rsp+4B0h+var_470]
0x14010f0a9  mov     rdx, rsi
0x14010f0ac  mov     rcx, rdi
0x14010f0af  call    LoadMUIFile
0x14010f0b4  mov     rbx, rax
0x14010f0b7  test    rax, rax
0x14010f0ba  jnz     loc_14010F166
0x14010f0c0  mov     r9, [rsp+4B0h+FilePart]
0x14010f0c5  lea     r8, [rbp+3B0h+var_310]
0x14010f0cc  mov     rdx, rsi
0x14010f0cf  mov     rcx, rdi
0x14010f0d2  call    LoadMUIFile
0x14010f0d7  mov     rbx, rax
0x14010f0da  test    rax, rax
0x14010f0dd  jnz     loc_14010F166
0x14010f0e3  cmp     [rbp+3B0h+var_3C0], r13w
0x14010f0e8  jz      short loc_14010F106
0x14010f0ea  mov     r9, [rsp+4B0h+FilePart]
0x14010f0ef  lea     r8, [rbp+3B0h+var_3C0]
0x14010f0f3  mov     rdx, rsi
0x14010f0f6  mov     rcx, rdi
0x14010f0f9  call    LoadMUIFile
0x14010f0fe  mov     rbx, rax
0x14010f101  test    rax, rax
0x14010f104  jnz     short loc_14010F166
0x14010f106  mov     ecx, 409h
0x14010f10b  cmp     cx, r14w
0x14010f10f  jz      short loc_14010F142
0x14010f111  xor     r9d, r9d
0x14010f114  lea     r8, [rbp+3B0h+var_310]
0x14010f11b  lea     rdx, [rsp+4B0h+var_470]
0x14010f120  call    LookupLangID
0x14010f125  mov     r9, [rsp+4B0h+FilePart]
0x14010f12a  lea     r8, [rsp+4B0h+var_470]
0x14010f12f  mov     rdx, rsi
0x14010f132  mov     rcx, rdi
0x14010f135  call    LoadMUIFile
0x14010f13a  mov     rbx, rax
0x14010f13d  test    rax, rax
0x14010f140  jnz     short loc_14010F166
0x14010f142  mov     r9, [rsp+4B0h+FilePart]
0x14010f147  xor     r8d, r8d
0x14010f14a  mov     rdx, rsi
0x14010f14d  mov     rcx, rdi
0x14010f150  call    LoadMUIFile
0x14010f155  mov     rbx, rax
0x14010f158  test    rax, rax
0x14010f15b  jnz     short loc_14010F166
0x14010f15d  test    rbx, rbx
0x14010f160  jz      loc_14010F015
0x14010f166  mov     rcx, rdi; hLibModule
0x14010f169  call    cs:__imp_FreeLibrary
0x14010f16f  mov     rax, rbx
0x14010f172  jmp     short loc_14010F1A0
0x14010f174  call    GetOSType
0x14010f179  test    al, 26h
0x14010f17b  mov     r8d, r13d
0x14010f17e  mov     rcx, r12; lpLibFileName
0x14010f181  setnz   r8b; dwFlags
0x14010f185  xor     edx, edx; hFile
0x14010f187  call    cs:__imp_LoadLibraryExW
0x14010f18d  mov     rdi, rax
0x14010f190  mov     rax, rdi
0x14010f193  jmp     short loc_14010F1A0
0x14010f195  mov     rcx, rdi; hLibModule
0x14010f198  call    cs:__imp_FreeLibrary
0x14010f19e  xor     eax, eax
0x14010f1a0  mov     rcx, [rbp+3B0h+var_50]
0x14010f1a7  xor     rcx, rsp; StackCookie
0x14010f1aa  call    __security_check_cookie
0x14010f1af  add     rsp, 478h
0x14010f1b6  pop     r15
0x14010f1b8  pop     r14
0x14010f1ba  pop     r13
0x14010f1bc  pop     r12
0x14010f1be  pop     rdi
0x14010f1bf  pop     rsi
0x14010f1c0  pop     rbx
0x14010f1c1  pop     rbp
0x14010f1c2  retn
```
