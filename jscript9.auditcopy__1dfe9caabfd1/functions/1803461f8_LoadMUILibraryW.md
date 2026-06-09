# LoadMUILibraryW

- ea: `0x1803461f8`
- end: `0x1803466cd`
- name: `LoadMUILibraryW`
- size: `1237`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18025b294`

## callees

- `0x1801a2a90`
- `0x180345a48`
- `0x180345ad0`
- `0x180345bf8`
- `0x180345d2c`
- `0x180345dc0`
- `0x180345f58`
- `0x1803461f8`
- `0x1803481f0`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x180346331`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180346331`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1803463f5`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1803463f5`
- `KERNEL32!SearchPathW` at `0x1803462b6`
- `KERNEL32!SearchPathW` at `0x1803462b6`
- `KERNEL32!FindResourceExW` at `0x180346302`
- `KERNEL32!FindResourceExW` at `0x180346302`
- `KERNEL32!LoadLibraryExW` at `0x18034626d`
- `KERNEL32!LoadLibraryExW` at `0x18034667d`
- `KERNEL32!LoadLibraryExW` at `0x18034626d`
- `KERNEL32!LoadLibraryExW` at `0x18034667d`
- `KERNEL32!FreeLibrary` at `0x1803465ba`
- `KERNEL32!FreeLibrary` at `0x180346659`
- `KERNEL32!FreeLibrary` at `0x180346694`
- `KERNEL32!FreeLibrary` at `0x1803465ba`
- `KERNEL32!FreeLibrary` at `0x180346659`
- `KERNEL32!FreeLibrary` at `0x180346694`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HINSTANCE v6; // rdi
  WCHAR *v7; // rsi
  HINSTANCE MUIFile; // rbx
  unsigned __int16 UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v11; // r15
  bool v12; // zf
  unsigned __int16 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR v17[88]; // [rsp+48h] [rbp-C0h] BYREF
  _WORD v18[88]; // [rsp+F8h] [rbp-10h] BYREF
  WCHAR v19[88]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+258h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_180443C98 = GetOSType();
  result = LoadLibraryExW(pszFullModuleName, 0, dword_180443C98 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_180443C98 & 0x20) != 0 )
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
      if ( (dword_180443C98 & 4) == 0 )
      {
        if ( (dword_180443C98 & 3) != 0 )
        {
          InstallLanguage = GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v17, v19, v18) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v17, (__int64)FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v19, (__int64)FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v18[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v18, (__int64)FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
            v12 = InstallLanguage == 1033;
LABEL_35:
            if ( !v12 )
            {
              LookupLangID(0x409u, v17, v19, 0);
              MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v17, (__int64)FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
LABEL_37:
            MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, 0, (__int64)FilePart);
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
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v17, v19, v18) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v17, (__int64)FilePart);
        if ( MUIFile )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v19, (__int64)FilePart);
        if ( MUIFile )
          goto LABEL_45;
        if ( v18[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v18, (__int64)FilePart);
          if ( MUIFile )
            goto LABEL_45;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v17, v19, v18) )
              goto LABEL_38;
            MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v17, (__int64)FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v19, (__int64)FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v18[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v18, (__int64)FilePart);
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
    if ( (dword_180443C98 & 7) != 0 && (unsigned int)LookupLangID(LangID, v17, v19, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile((__int64)v6, (__int64)v7, (__int64)v17, (__int64)FilePart);
LABEL_44:
      if ( MUIFile )
        goto LABEL_45;
    }
  }
LABEL_38:
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType() & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return MapMUIFile(Buffer, 1, 0);
    }
    else
    {
      OSType = GetOSType();
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1803461f8  mov     rax, rsp
0x1803461fb  mov     [rax+20h], rbx
0x1803461ff  mov     [rax+18h], r8w
0x180346204  mov     [rax+10h], edx
0x180346207  mov     [rax+8], rcx
0x18034620b  push    rbp
0x18034620c  push    rsi
0x18034620d  push    rdi
0x18034620e  push    r12
0x180346210  push    r13
0x180346212  push    r14
0x180346214  push    r15
0x180346216  lea     rbp, [rax-3A8h]
0x18034621d  sub     rsp, 470h
0x180346224  mov     rax, cs:__security_cookie
0x18034622b  xor     rax, rsp
0x18034622e  mov     [rbp+3A0h+var_40], rax
0x180346235  mov     r12, [rbp+3A0h+lpLibFileName]
0x18034623c  xor     r13d, r13d
0x18034623f  movzx   ebx, [rbp+3A0h+arg_10]
0x180346246  mov     [rsp+4A0h+FilePart], r13
0x18034624b  test    r12, r12
0x18034624e  jz      loc_1803466A0
0x180346254  call    GetOSType
0x180346259  mov     cs:dword_180443C98, eax
0x18034625f  xor     edx, edx; hFile
0x180346261  and     eax, 20h
0x180346264  mov     rcx, r12; lpLibFileName
0x180346267  or      eax, 2
0x18034626a  mov     r8d, eax; dwFlags
0x18034626d  call    cs:__imp_LoadLibraryExW
0x180346274  nop     dword ptr [rax+rax+00h]
0x180346279  mov     rdi, rax
0x18034627c  test    rax, rax
0x18034627f  jz      loc_1803466A0
0x180346285  test    byte ptr cs:dword_180443C98, 20h
0x18034628c  jnz     loc_1803466A2
0x180346292  lea     rax, [rsp+4A0h+FilePart]
0x180346297  mov     r9d, 104h; nBufferLength
0x18034629d  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x1803462a2  xor     r8d, r8d; lpExtension
0x1803462a5  lea     rax, [rbp+3A0h+Buffer]
0x1803462ac  mov     rdx, r12; lpFileName
0x1803462af  xor     ecx, ecx; lpPath
0x1803462b1  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x1803462b6  call    cs:__imp_SearchPathW
0x1803462bd  nop     dword ptr [rax+rax+00h]
0x1803462c2  test    eax, eax
0x1803462c4  jz      loc_180346691
0x1803462ca  mov     rcx, [rsp+4A0h+FilePart]
0x1803462cf  test    rcx, rcx
0x1803462d2  jnz     short loc_1803462E5
0x1803462d4  lea     rax, [rbp+3A0h+Buffer]
0x1803462db  mov     esi, r13d
0x1803462de  mov     [rsp+4A0h+FilePart], rax
0x1803462e3  jmp     short loc_1803462F1
0x1803462e5  lea     rsi, [rbp+3A0h+Buffer]
0x1803462ec  mov     [rcx-2], r13w
0x1803462f1  xor     r9d, r9d; wLanguage
0x1803462f4  lea     rdx, Type; "MUI"
0x1803462fb  mov     rcx, rdi; hModule
0x1803462fe  lea     r8d, [r9+1]; lpName
0x180346302  call    cs:__imp_FindResourceExW
0x180346309  nop     dword ptr [rax+rax+00h]
0x18034630e  test    rax, rax
0x180346311  jz      loc_1803465AD
0x180346317  test    bx, bx
0x18034631a  jnz     loc_18034660D
0x180346320  mov     eax, cs:dword_180443C98
0x180346326  test    al, 4
0x180346328  jz      loc_1803464B2
0x18034632e  mov     rbx, r13
0x180346331  call    cs:__imp_GetUserDefaultUILanguage
0x180346338  nop     dword ptr [rax+rax+00h]
0x18034633d  mov     r15d, 404h
0x180346343  movzx   r14d, ax
0x180346347  cmp     ax, r15w
0x18034634b  jnz     short loc_180346356
0x18034634d  call    GetCHTLangauge
0x180346352  movzx   r14d, ax
0x180346356  lea     r9, [rbp+3A0h+var_3B0]
0x18034635a  movzx   ecx, r14w
0x18034635e  lea     r8, [rbp+3A0h+var_300]
0x180346365  lea     rdx, [rsp+40h]
0x18034636a  call    LookupLangID
0x18034636f  test    eax, eax
0x180346371  jz      loc_18034664D
0x180346377  mov     r9, [rsp+4A0h+FilePart]
0x18034637c  lea     r8, [rsp+40h]
0x180346381  mov     rdx, rsi
0x180346384  mov     rcx, rdi
0x180346387  call    LoadMUIFile
0x18034638c  mov     rbx, rax
0x18034638f  test    rax, rax
0x180346392  jnz     loc_180346656
0x180346398  mov     r9, [rsp+4A0h+FilePart]
0x18034639d  lea     r8, [rbp+3A0h+var_300]
0x1803463a4  mov     rdx, rsi
0x1803463a7  mov     rcx, rdi
0x1803463aa  call    LoadMUIFile
0x1803463af  mov     rbx, rax
0x1803463b2  test    rax, rax
0x1803463b5  jnz     loc_180346656
0x1803463bb  cmp     [rbp+3A0h+var_3B0], r13w
0x1803463c0  jz      short loc_1803463E2
0x1803463c2  mov     r9, [rsp+4A0h+FilePart]
0x1803463c7  lea     r8, [rbp+3A0h+var_3B0]
0x1803463cb  mov     rdx, rsi
0x1803463ce  mov     rcx, rdi
0x1803463d1  call    LoadMUIFile
0x1803463d6  mov     rbx, rax
0x1803463d9  test    rax, rax
0x1803463dc  jnz     loc_180346656
0x1803463e2  mov     eax, 0C04h
0x1803463e7  cmp     r14w, ax
0x1803463eb  jnz     short loc_1803463F5
0x1803463ed  mov     r14d, r15d
0x1803463f0  jmp     loc_180346356
0x1803463f5  call    cs:__imp_GetSystemDefaultUILanguage
0x1803463fc  nop     dword ptr [rax+rax+00h]
0x180346401  movzx   r15d, ax
0x180346405  cmp     ax, r14w
0x180346409  jz      loc_18034649A
0x18034640f  lea     r9, [rbp+3A0h+var_3B0]
0x180346413  movzx   ecx, ax
0x180346416  lea     r8, [rbp+3A0h+var_300]
0x18034641d  lea     rdx, [rsp+40h]
0x180346422  call    LookupLangID
0x180346427  test    eax, eax
0x180346429  jz      loc_1803465AD
0x18034642f  mov     r9, [rsp+4A0h+FilePart]
0x180346434  lea     r8, [rsp+40h]
0x180346439  mov     rdx, rsi
0x18034643c  mov     rcx, rdi
0x18034643f  call    LoadMUIFile
0x180346444  mov     rbx, rax
0x180346447  test    rax, rax
0x18034644a  jnz     loc_180346656
0x180346450  mov     r9, [rsp+4A0h+FilePart]
0x180346455  lea     r8, [rbp+3A0h+var_300]
0x18034645c  mov     rdx, rsi
0x18034645f  mov     rcx, rdi
0x180346462  call    LoadMUIFile
0x180346467  mov     rbx, rax
0x18034646a  test    rax, rax
0x18034646d  jnz     loc_180346656
0x180346473  cmp     [rbp+3A0h+var_3B0], r13w
0x180346478  jz      short loc_18034649A
0x18034647a  mov     r9, [rsp+4A0h+FilePart]
0x18034647f  lea     r8, [rbp+3A0h+var_3B0]
0x180346483  mov     rdx, rsi
0x180346486  mov     rcx, rdi
0x180346489  call    LoadMUIFile
0x18034648e  mov     rbx, rax
0x180346491  test    rax, rax
0x180346494  jnz     loc_180346656
0x18034649a  mov     ecx, 409h
0x18034649f  cmp     cx, r14w
0x1803464a3  jz      loc_18034658E
0x1803464a9  cmp     cx, r15w
0x1803464ad  jmp     loc_180346557
0x1803464b2  test    al, 3
0x1803464b4  jz      loc_1803465AD
0x1803464ba  call    GetInstallLanguage
0x1803464bf  lea     r9, [rbp+3A0h+var_3B0]
0x1803464c3  movzx   ecx, ax
0x1803464c6  lea     r8, [rbp+3A0h+var_300]
0x1803464cd  movzx   r14d, ax
0x1803464d1  lea     rdx, [rsp+40h]
0x1803464d6  call    LookupLangID
0x1803464db  test    eax, eax
0x1803464dd  jz      loc_1803465AD
0x1803464e3  mov     r9, [rsp+4A0h+FilePart]
0x1803464e8  lea     r8, [rsp+40h]
0x1803464ed  mov     rdx, rsi
0x1803464f0  mov     rcx, rdi
0x1803464f3  call    LoadMUIFile
0x1803464f8  mov     rbx, rax
0x1803464fb  test    rax, rax
0x1803464fe  jnz     loc_180346656
0x180346504  mov     r9, [rsp+4A0h+FilePart]
0x180346509  lea     r8, [rbp+3A0h+var_300]
0x180346510  mov     rdx, rsi
0x180346513  mov     rcx, rdi
0x180346516  call    LoadMUIFile
0x18034651b  mov     rbx, rax
0x18034651e  test    rax, rax
0x180346521  jnz     loc_180346656
0x180346527  cmp     [rbp+3A0h+var_3B0], r13w
0x18034652c  jz      short loc_18034654E
0x18034652e  mov     r9, [rsp+4A0h+FilePart]
0x180346533  lea     r8, [rbp+3A0h+var_3B0]
0x180346537  mov     rdx, rsi
0x18034653a  mov     rcx, rdi
0x18034653d  call    LoadMUIFile
0x180346542  mov     rbx, rax
0x180346545  test    rax, rax
0x180346548  jnz     loc_180346656
0x18034654e  mov     ecx, 409h
0x180346553  cmp     cx, r14w
0x180346557  jz      short loc_18034658E
0x180346559  xor     r9d, r9d
0x18034655c  lea     r8, [rbp+3A0h+var_300]
0x180346563  lea     rdx, [rsp+40h]
0x180346568  call    LookupLangID
0x18034656d  mov     r9, [rsp+4A0h+FilePart]
0x180346572  lea     r8, [rsp+40h]
0x180346577  mov     rdx, rsi
0x18034657a  mov     rcx, rdi
0x18034657d  call    LoadMUIFile
0x180346582  mov     rbx, rax
0x180346585  test    rax, rax
0x180346588  jnz     loc_180346656
0x18034658e  mov     r9, [rsp+4A0h+FilePart]
0x180346593  xor     r8d, r8d
0x180346596  mov     rdx, rsi
0x180346599  mov     rcx, rdi
0x18034659c  call    LoadMUIFile
0x1803465a1  mov     rbx, rax
0x1803465a4  test    rax, rax
0x1803465a7  jnz     loc_180346656
0x1803465ad  test    dil, 1
0x1803465b1  jz      loc_18034668C
0x1803465b7  mov     rcx, rdi; hLibModule
0x1803465ba  call    cs:__imp_FreeLibrary
0x1803465c1  nop     dword ptr [rax+rax+00h]
0x1803465c6  call    GetOSType
0x1803465cb  test    al, 38h
0x1803465cd  jz      loc_18034666A
0x1803465d3  mov     rax, [rsp+4A0h+FilePart]
0x1803465d8  lea     r8, aSS_2; "%s\\%s"
0x1803465df  mov     r9, rsi
0x1803465e2  mov     [rsp+4A0h+lpBuffer], rax
0x1803465e7  mov     edx, 104h; unsigned __int64
0x1803465ec  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x1803465f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1803465f8  xor     r8d, r8d
0x1803465fb  lea     rcx, [rbp+3A0h+Buffer]
0x180346602  lea     edx, [r8+1]
0x180346606  call    MapMUIFile
0x18034660b  jmp     short loc_180346689
0x18034660d  test    byte ptr cs:dword_180443C98, 7
0x180346614  jz      short loc_1803465AD
0x180346616  xor     r9d, r9d
0x180346619  lea     r8, [rbp+3A0h+var_300]
0x180346620  lea     rdx, [rsp+40h]
0x180346625  movzx   ecx, bx
0x180346628  call    LookupLangID
0x18034662d  test    eax, eax
0x18034662f  jz      loc_1803465AD
0x180346635  mov     r9, [rsp+4A0h+FilePart]
0x18034663a  lea     r8, [rsp+40h]
0x18034663f  mov     rdx, rsi
0x180346642  mov     rcx, rdi
0x180346645  call    LoadMUIFile
0x18034664a  mov     rbx, rax
0x18034664d  test    rbx, rbx
0x180346650  jz      loc_1803465AD
0x180346656  mov     rcx, rdi; hLibModule
0x180346659  call    cs:__imp_FreeLibrary
0x180346660  nop     dword ptr [rax+rax+00h]
0x180346665  mov     rax, rbx
0x180346668  jmp     short loc_1803466A2
0x18034666a  call    GetOSType
0x18034666f  test    al, 26h
0x180346671  mov     r8d, r13d
0x180346674  mov     rcx, r12; lpLibFileName
0x180346677  setnz   r8b; dwFlags
0x18034667b  xor     edx, edx; hFile
0x18034667d  call    cs:__imp_LoadLibraryExW
0x180346684  nop     dword ptr [rax+rax+00h]
0x180346689  mov     rdi, rax
0x18034668c  mov     rax, rdi
0x18034668f  jmp     short loc_1803466A2
0x180346691  mov     rcx, rdi; hLibModule
0x180346694  call    cs:__imp_FreeLibrary
0x18034669b  nop     dword ptr [rax+rax+00h]
0x1803466a0  xor     eax, eax
0x1803466a2  mov     rcx, [rbp+3A0h+var_40]
0x1803466a9  xor     rcx, rsp; StackCookie
0x1803466ac  call    __security_check_cookie
0x1803466b1  mov     rbx, [rsp+4A0h+arg_18]
0x1803466b9  add     rsp, 470h
0x1803466c0  pop     r15
0x1803466c2  pop     r14
0x1803466c4  pop     r13
0x1803466c6  pop     r12
0x1803466c8  pop     rdi
0x1803466c9  pop     rsi
0x1803466ca  pop     rbp
0x1803466cb  retn
```
