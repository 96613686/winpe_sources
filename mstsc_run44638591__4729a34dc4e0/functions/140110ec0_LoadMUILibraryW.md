# LoadMUILibraryW

- ea: `0x140110ec0`
- end: `0x140111333`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1400fc688`

## callees

- `0x140008a78`
- `0x1401107e0`
- `0x140110860`
- `0x140110970`
- `0x140110a98`
- `0x140110b0c`
- `0x140110c80`
- `0x140110ec0`
- `0x140113390`

## import_xrefs

- `KERNEL32!SearchPathW` at `0x140110f5d`
- `KERNEL32!SearchPathW` at `0x140110f5d`
- `KERNEL32!FindResourceExW` at `0x140110fa3`
- `KERNEL32!FindResourceExW` at `0x140110fa3`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140110fc3`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140110fc3`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140111081`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140111081`
- `KERNEL32!LoadLibraryExW` at `0x140110f1a`
- `KERNEL32!LoadLibraryExW` at `0x1401112f7`
- `KERNEL32!LoadLibraryExW` at `0x140110f1a`
- `KERNEL32!LoadLibraryExW` at `0x1401112f7`
- `KERNEL32!FreeLibrary` at `0x140111192`
- `KERNEL32!FreeLibrary` at `0x1401112d9`
- `KERNEL32!FreeLibrary` at `0x140111308`
- `KERNEL32!FreeLibrary` at `0x140111192`
- `KERNEL32!FreeLibrary` at `0x1401112d9`
- `KERNEL32!FreeLibrary` at `0x140111308`

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
  dword_140154DF8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_140154DF8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_140154DF8 & 0x20) != 0 )
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
    if ( (dword_140154DF8 & 4) != 0 )
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
    else if ( (dword_140154DF8 & 3) != 0 )
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
      StringCchPrintfW(Buffer, 0x104u, (size_t *)L"%s\\%s", v6, FilePart);
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
0x140110ec0  push    rbp
0x140110ec2  push    rbx
0x140110ec3  push    rsi
0x140110ec4  push    rdi
0x140110ec5  push    r12
0x140110ec7  push    r13
0x140110ec9  push    r14
0x140110ecb  push    r15
0x140110ecd  lea     rbp, [rsp-378h]
0x140110ed5  sub     rsp, 478h
0x140110edc  mov     rax, cs:__security_cookie
0x140110ee3  xor     rax, rsp
0x140110ee6  mov     [rbp+3B0h+var_50], rax
0x140110eed  xor     r13d, r13d
0x140110ef0  mov     r12, rcx
0x140110ef3  mov     [rsp+4B0h+FilePart], r13
0x140110ef8  test    rcx, rcx
0x140110efb  jz      loc_14011130E
0x140110f01  call    GetOSType
0x140110f06  mov     cs:dword_140154DF8, eax
0x140110f0c  xor     edx, edx; hFile
0x140110f0e  and     eax, 20h
0x140110f11  mov     rcx, r12; lpLibFileName
0x140110f14  or      eax, 2
0x140110f17  mov     r8d, eax; dwFlags
0x140110f1a  call    cs:__imp_LoadLibraryExW
0x140110f20  mov     rdi, rax
0x140110f23  test    rax, rax
0x140110f26  jz      loc_14011130E
0x140110f2c  test    byte ptr cs:dword_140154DF8, 20h
0x140110f33  jnz     loc_140111310
0x140110f39  lea     rax, [rsp+4B0h+FilePart]
0x140110f3e  mov     r9d, 104h; nBufferLength
0x140110f44  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x140110f49  xor     r8d, r8d; lpExtension
0x140110f4c  lea     rax, [rbp+3B0h+Buffer]
0x140110f53  mov     rdx, r12; lpFileName
0x140110f56  xor     ecx, ecx; lpPath
0x140110f58  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x140110f5d  call    cs:__imp_SearchPathW
0x140110f63  test    eax, eax
0x140110f65  jz      loc_140111305
0x140110f6b  mov     rcx, [rsp+4B0h+FilePart]
0x140110f70  test    rcx, rcx
0x140110f73  jnz     short loc_140110F86
0x140110f75  lea     rax, [rbp+3B0h+Buffer]
0x140110f7c  mov     esi, r13d
0x140110f7f  mov     [rsp+4B0h+FilePart], rax
0x140110f84  jmp     short loc_140110F92
0x140110f86  lea     rsi, [rbp+3B0h+Buffer]
0x140110f8d  mov     [rcx-2], r13w
0x140110f92  xor     r9d, r9d; wLanguage
0x140110f95  lea     rdx, aMui; "MUI"
0x140110f9c  mov     rcx, rdi; hModule
0x140110f9f  lea     r8d, [r9+1]; lpName
0x140110fa3  call    cs:__imp_FindResourceExW
0x140110fa9  test    rax, rax
0x140110fac  jz      loc_140111185
0x140110fb2  mov     eax, cs:dword_140154DF8
0x140110fb8  test    al, 4
0x140110fba  jz      loc_1401111E2
0x140110fc0  mov     rbx, r13
0x140110fc3  call    cs:__imp_GetUserDefaultUILanguage
0x140110fc9  mov     r15d, 404h
0x140110fcf  movzx   r14d, ax
0x140110fd3  cmp     ax, r15w
0x140110fd7  jnz     short loc_140110FE2
0x140110fd9  call    GetCHTLangauge
0x140110fde  movzx   r14d, ax
0x140110fe2  lea     r9, [rbp+3B0h+var_3C0]
0x140110fe6  movzx   ecx, r14w
0x140110fea  lea     r8, [rbp+3B0h+var_310]
0x140110ff1  lea     rdx, [rsp+4B0h+var_470]
0x140110ff6  call    LookupLangID
0x140110ffb  test    eax, eax
0x140110ffd  jz      loc_1401112CD
0x140111003  mov     r9, [rsp+4B0h+FilePart]
0x140111008  lea     r8, [rsp+4B0h+var_470]
0x14011100d  mov     rdx, rsi
0x140111010  mov     rcx, rdi
0x140111013  call    LoadMUIFile
0x140111018  mov     rbx, rax
0x14011101b  test    rax, rax
0x14011101e  jnz     loc_1401112D6
0x140111024  mov     r9, [rsp+4B0h+FilePart]
0x140111029  lea     r8, [rbp+3B0h+var_310]
0x140111030  mov     rdx, rsi
0x140111033  mov     rcx, rdi
0x140111036  call    LoadMUIFile
0x14011103b  mov     rbx, rax
0x14011103e  test    rax, rax
0x140111041  jnz     loc_1401112D6
0x140111047  cmp     [rbp+3B0h+var_3C0], r13w
0x14011104c  jz      short loc_14011106E
0x14011104e  mov     r9, [rsp+4B0h+FilePart]
0x140111053  lea     r8, [rbp+3B0h+var_3C0]
0x140111057  mov     rdx, rsi
0x14011105a  mov     rcx, rdi
0x14011105d  call    LoadMUIFile
0x140111062  mov     rbx, rax
0x140111065  test    rax, rax
0x140111068  jnz     loc_1401112D6
0x14011106e  mov     eax, 0C04h
0x140111073  cmp     r14w, ax
0x140111077  jnz     short loc_140111081
0x140111079  mov     r14d, r15d
0x14011107c  jmp     loc_140110FE2
0x140111081  call    cs:__imp_GetSystemDefaultUILanguage
0x140111087  movzx   r15d, ax
0x14011108b  cmp     ax, r14w
0x14011108f  jz      loc_140111120
0x140111095  lea     r9, [rbp+3B0h+var_3C0]
0x140111099  movzx   ecx, ax
0x14011109c  lea     r8, [rbp+3B0h+var_310]
0x1401110a3  lea     rdx, [rsp+4B0h+var_470]
0x1401110a8  call    LookupLangID
0x1401110ad  test    eax, eax
0x1401110af  jz      loc_140111185
0x1401110b5  mov     r9, [rsp+4B0h+FilePart]
0x1401110ba  lea     r8, [rsp+4B0h+var_470]
0x1401110bf  mov     rdx, rsi
0x1401110c2  mov     rcx, rdi
0x1401110c5  call    LoadMUIFile
0x1401110ca  mov     rbx, rax
0x1401110cd  test    rax, rax
0x1401110d0  jnz     loc_1401112D6
0x1401110d6  mov     r9, [rsp+4B0h+FilePart]
0x1401110db  lea     r8, [rbp+3B0h+var_310]
0x1401110e2  mov     rdx, rsi
0x1401110e5  mov     rcx, rdi
0x1401110e8  call    LoadMUIFile
0x1401110ed  mov     rbx, rax
0x1401110f0  test    rax, rax
0x1401110f3  jnz     loc_1401112D6
0x1401110f9  cmp     [rbp+3B0h+var_3C0], r13w
0x1401110fe  jz      short loc_140111120
0x140111100  mov     r9, [rsp+4B0h+FilePart]
0x140111105  lea     r8, [rbp+3B0h+var_3C0]
0x140111109  mov     rdx, rsi
0x14011110c  mov     rcx, rdi
0x14011110f  call    LoadMUIFile
0x140111114  mov     rbx, rax
0x140111117  test    rax, rax
0x14011111a  jnz     loc_1401112D6
0x140111120  mov     ecx, 409h
0x140111125  cmp     cx, r14w
0x140111129  jz      short loc_140111166
0x14011112b  cmp     cx, r15w
0x14011112f  jz      short loc_140111166
0x140111131  xor     r9d, r9d
0x140111134  lea     r8, [rbp+3B0h+var_310]
0x14011113b  lea     rdx, [rsp+4B0h+var_470]
0x140111140  call    LookupLangID
0x140111145  mov     r9, [rsp+4B0h+FilePart]
0x14011114a  lea     r8, [rsp+4B0h+var_470]
0x14011114f  mov     rdx, rsi
0x140111152  mov     rcx, rdi
0x140111155  call    LoadMUIFile
0x14011115a  mov     rbx, rax
0x14011115d  test    rax, rax
0x140111160  jnz     loc_1401112D6
0x140111166  mov     r9, [rsp+4B0h+FilePart]
0x14011116b  xor     r8d, r8d
0x14011116e  mov     rdx, rsi
0x140111171  mov     rcx, rdi
0x140111174  call    LoadMUIFile
0x140111179  mov     rbx, rax
0x14011117c  test    rax, rax
0x14011117f  jnz     loc_1401112D6
0x140111185  test    dil, 1
0x140111189  jz      loc_140111300
0x14011118f  mov     rcx, rdi; hLibModule
0x140111192  call    cs:__imp_FreeLibrary
0x140111198  call    GetOSType
0x14011119d  test    al, 38h
0x14011119f  jz      loc_1401112E4
0x1401111a5  mov     rax, [rsp+4B0h+FilePart]
0x1401111aa  lea     r8, aSS_0; "%s\\%s"
0x1401111b1  mov     r9, rsi
0x1401111b4  mov     [rsp+4B0h+lpBuffer], rax
0x1401111b9  mov     edx, 104h; unsigned __int64
0x1401111be  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x1401111c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401111ca  xor     r8d, r8d
0x1401111cd  lea     rcx, [rbp+3B0h+Buffer]
0x1401111d4  lea     edx, [r8+1]
0x1401111d8  call    MapMUIFile
0x1401111dd  jmp     loc_1401112FD
0x1401111e2  test    al, 3
0x1401111e4  jz      short loc_140111185
0x1401111e6  call    GetInstallLanguage
0x1401111eb  lea     r9, [rbp+3B0h+var_3C0]
0x1401111ef  movzx   ecx, ax
0x1401111f2  lea     r8, [rbp+3B0h+var_310]
0x1401111f9  movzx   r14d, ax
0x1401111fd  lea     rdx, [rsp+4B0h+var_470]
0x140111202  call    LookupLangID
0x140111207  test    eax, eax
0x140111209  jz      loc_140111185
0x14011120f  mov     r9, [rsp+4B0h+FilePart]
0x140111214  lea     r8, [rsp+4B0h+var_470]
0x140111219  mov     rdx, rsi
0x14011121c  mov     rcx, rdi
0x14011121f  call    LoadMUIFile
0x140111224  mov     rbx, rax
0x140111227  test    rax, rax
0x14011122a  jnz     loc_1401112D6
0x140111230  mov     r9, [rsp+4B0h+FilePart]
0x140111235  lea     r8, [rbp+3B0h+var_310]
0x14011123c  mov     rdx, rsi
0x14011123f  mov     rcx, rdi
0x140111242  call    LoadMUIFile
0x140111247  mov     rbx, rax
0x14011124a  test    rax, rax
0x14011124d  jnz     loc_1401112D6
0x140111253  cmp     [rbp+3B0h+var_3C0], r13w
0x140111258  jz      short loc_140111276
0x14011125a  mov     r9, [rsp+4B0h+FilePart]
0x14011125f  lea     r8, [rbp+3B0h+var_3C0]
0x140111263  mov     rdx, rsi
0x140111266  mov     rcx, rdi
0x140111269  call    LoadMUIFile
0x14011126e  mov     rbx, rax
0x140111271  test    rax, rax
0x140111274  jnz     short loc_1401112D6
0x140111276  mov     ecx, 409h
0x14011127b  cmp     cx, r14w
0x14011127f  jz      short loc_1401112B2
0x140111281  xor     r9d, r9d
0x140111284  lea     r8, [rbp+3B0h+var_310]
0x14011128b  lea     rdx, [rsp+4B0h+var_470]
0x140111290  call    LookupLangID
0x140111295  mov     r9, [rsp+4B0h+FilePart]
0x14011129a  lea     r8, [rsp+4B0h+var_470]
0x14011129f  mov     rdx, rsi
0x1401112a2  mov     rcx, rdi
0x1401112a5  call    LoadMUIFile
0x1401112aa  mov     rbx, rax
0x1401112ad  test    rax, rax
0x1401112b0  jnz     short loc_1401112D6
0x1401112b2  mov     r9, [rsp+4B0h+FilePart]
0x1401112b7  xor     r8d, r8d
0x1401112ba  mov     rdx, rsi
0x1401112bd  mov     rcx, rdi
0x1401112c0  call    LoadMUIFile
0x1401112c5  mov     rbx, rax
0x1401112c8  test    rax, rax
0x1401112cb  jnz     short loc_1401112D6
0x1401112cd  test    rbx, rbx
0x1401112d0  jz      loc_140111185
0x1401112d6  mov     rcx, rdi; hLibModule
0x1401112d9  call    cs:__imp_FreeLibrary
0x1401112df  mov     rax, rbx
0x1401112e2  jmp     short loc_140111310
0x1401112e4  call    GetOSType
0x1401112e9  test    al, 26h
0x1401112eb  mov     r8d, r13d
0x1401112ee  mov     rcx, r12; lpLibFileName
0x1401112f1  setnz   r8b; dwFlags
0x1401112f5  xor     edx, edx; hFile
0x1401112f7  call    cs:__imp_LoadLibraryExW
0x1401112fd  mov     rdi, rax
0x140111300  mov     rax, rdi
0x140111303  jmp     short loc_140111310
0x140111305  mov     rcx, rdi; hLibModule
0x140111308  call    cs:__imp_FreeLibrary
0x14011130e  xor     eax, eax
0x140111310  mov     rcx, [rbp+3B0h+var_50]
0x140111317  xor     rcx, rsp; StackCookie
0x14011131a  call    __security_check_cookie
0x14011131f  add     rsp, 478h
0x140111326  pop     r15
0x140111328  pop     r14
0x14011132a  pop     r13
0x14011132c  pop     r12
0x14011132e  pop     rdi
0x14011132f  pop     rsi
0x140111330  pop     rbx
0x140111331  pop     rbp
0x140111332  retn
```
