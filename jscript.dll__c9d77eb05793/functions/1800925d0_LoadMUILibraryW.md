# LoadMUILibraryW

- ea: `0x1800925d0`
- end: `0x180092a56`
- name: `LoadMUILibraryW`
- size: `1158`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180086708`

## callees

- `0x180042ad8`
- `0x180091eec`
- `0x180091f6c`
- `0x18009207c`
- `0x1800921a4`
- `0x180092218`
- `0x18009238c`
- `0x1800925d0`
- `0x1800942d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180092631`
- `KERNEL32!LoadLibraryExW` at `0x180092a13`
- `KERNEL32!LoadLibraryExW` at `0x180092631`
- `KERNEL32!LoadLibraryExW` at `0x180092a13`
- `KERNEL32!FreeLibrary` at `0x180092960`
- `KERNEL32!FreeLibrary` at `0x1800929f5`
- `KERNEL32!FreeLibrary` at `0x180092a24`
- `KERNEL32!FreeLibrary` at `0x180092960`
- `KERNEL32!FreeLibrary` at `0x1800929f5`
- `KERNEL32!FreeLibrary` at `0x180092a24`
- `KERNEL32!SearchPathW` at `0x180092674`
- `KERNEL32!SearchPathW` at `0x180092674`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800927a1`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800927a1`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800926e3`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800926e3`
- `KERNEL32!FindResourceExW` at `0x1800926ba`
- `KERNEL32!FindResourceExW` at `0x1800926ba`

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
  dword_1800B7140 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800B7140 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_1800B7140 & 0x20) != 0 )
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
      if ( (dword_1800B7140 & 4) == 0 )
      {
        if ( (dword_1800B7140 & 3) != 0 )
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
    if ( (dword_1800B7140 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
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
0x1800925d0  mov     [rsp-8+arg_8], rbx
0x1800925d5  push    rbp
0x1800925d6  push    rsi
0x1800925d7  push    rdi
0x1800925d8  push    r12
0x1800925da  push    r13
0x1800925dc  push    r14
0x1800925de  push    r15
0x1800925e0  lea     rbp, [rsp-370h]
0x1800925e8  sub     rsp, 470h
0x1800925ef  mov     rax, cs:__security_cookie
0x1800925f6  xor     rax, rsp
0x1800925f9  mov     [rbp+3A0h+var_40], rax
0x180092600  xor     r13d, r13d
0x180092603  movzx   ebx, r8w
0x180092607  mov     [rsp+4A0h+FilePart], r13
0x18009260c  mov     r12, rcx
0x18009260f  test    rcx, rcx
0x180092612  jz      loc_180092A2A
0x180092618  call    GetOSType
0x18009261d  mov     cs:dword_1800B7140, eax
0x180092623  xor     edx, edx; hFile
0x180092625  and     eax, 20h
0x180092628  mov     rcx, r12; lpLibFileName
0x18009262b  or      eax, 2
0x18009262e  mov     r8d, eax; dwFlags
0x180092631  call    cs:__imp_LoadLibraryExW
0x180092637  mov     rdi, rax
0x18009263a  test    rax, rax
0x18009263d  jz      loc_180092A2A
0x180092643  test    byte ptr cs:dword_1800B7140, 20h
0x18009264a  jnz     loc_180092A2C
0x180092650  lea     rax, [rsp+4A0h+FilePart]
0x180092655  mov     r9d, 104h; nBufferLength
0x18009265b  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180092660  xor     r8d, r8d; lpExtension
0x180092663  lea     rax, [rbp+3A0h+Buffer]
0x18009266a  mov     rdx, r12; lpFileName
0x18009266d  xor     ecx, ecx; lpPath
0x18009266f  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180092674  call    cs:__imp_SearchPathW
0x18009267a  test    eax, eax
0x18009267c  jz      loc_180092A21
0x180092682  mov     rcx, [rsp+4A0h+FilePart]
0x180092687  test    rcx, rcx
0x18009268a  jnz     short loc_18009269D
0x18009268c  lea     rax, [rbp+3A0h+Buffer]
0x180092693  mov     esi, r13d
0x180092696  mov     [rsp+4A0h+FilePart], rax
0x18009269b  jmp     short loc_1800926A9
0x18009269d  lea     rsi, [rbp+3A0h+Buffer]
0x1800926a4  mov     [rcx-2], r13w
0x1800926a9  xor     r9d, r9d; wLanguage
0x1800926ac  lea     rdx, Type; "MUI"
0x1800926b3  mov     rcx, rdi; hModule
0x1800926b6  lea     r8d, [r9+1]; lpName
0x1800926ba  call    cs:__imp_FindResourceExW
0x1800926c0  test    rax, rax
0x1800926c3  jz      loc_180092953
0x1800926c9  test    bx, bx
0x1800926cc  jnz     loc_1800929AD
0x1800926d2  mov     eax, cs:dword_1800B7140
0x1800926d8  test    al, 4
0x1800926da  jz      loc_180092858
0x1800926e0  mov     rbx, r13
0x1800926e3  call    cs:__imp_GetUserDefaultUILanguage
0x1800926e9  mov     r15d, 404h
0x1800926ef  movzx   r14d, ax
0x1800926f3  cmp     ax, r15w
0x1800926f7  jnz     short loc_180092702
0x1800926f9  call    GetCHTLangauge
0x1800926fe  movzx   r14d, ax
0x180092702  lea     r9, [rbp+3A0h+var_3B0]
0x180092706  movzx   ecx, r14w
0x18009270a  lea     r8, [rbp+3A0h+var_300]
0x180092711  lea     rdx, [rsp+4A0h+var_460]
0x180092716  call    LookupLangID
0x18009271b  test    eax, eax
0x18009271d  jz      loc_1800929E9
0x180092723  mov     r9, [rsp+4A0h+FilePart]
0x180092728  lea     r8, [rsp+4A0h+var_460]
0x18009272d  mov     rdx, rsi
0x180092730  mov     rcx, rdi
0x180092733  call    LoadMUIFile
0x180092738  mov     rbx, rax
0x18009273b  test    rax, rax
0x18009273e  jnz     loc_1800929F2
0x180092744  mov     r9, [rsp+4A0h+FilePart]
0x180092749  lea     r8, [rbp+3A0h+var_300]
0x180092750  mov     rdx, rsi
0x180092753  mov     rcx, rdi
0x180092756  call    LoadMUIFile
0x18009275b  mov     rbx, rax
0x18009275e  test    rax, rax
0x180092761  jnz     loc_1800929F2
0x180092767  cmp     [rbp+3A0h+var_3B0], r13w
0x18009276c  jz      short loc_18009278E
0x18009276e  mov     r9, [rsp+4A0h+FilePart]
0x180092773  lea     r8, [rbp+3A0h+var_3B0]
0x180092777  mov     rdx, rsi
0x18009277a  mov     rcx, rdi
0x18009277d  call    LoadMUIFile
0x180092782  mov     rbx, rax
0x180092785  test    rax, rax
0x180092788  jnz     loc_1800929F2
0x18009278e  mov     eax, 0C04h
0x180092793  cmp     r14w, ax
0x180092797  jnz     short loc_1800927A1
0x180092799  mov     r14d, r15d
0x18009279c  jmp     loc_180092702
0x1800927a1  call    cs:__imp_GetSystemDefaultUILanguage
0x1800927a7  movzx   r15d, ax
0x1800927ab  cmp     ax, r14w
0x1800927af  jz      loc_180092840
0x1800927b5  lea     r9, [rbp+3A0h+var_3B0]
0x1800927b9  movzx   ecx, ax
0x1800927bc  lea     r8, [rbp+3A0h+var_300]
0x1800927c3  lea     rdx, [rsp+4A0h+var_460]
0x1800927c8  call    LookupLangID
0x1800927cd  test    eax, eax
0x1800927cf  jz      loc_180092953
0x1800927d5  mov     r9, [rsp+4A0h+FilePart]
0x1800927da  lea     r8, [rsp+4A0h+var_460]
0x1800927df  mov     rdx, rsi
0x1800927e2  mov     rcx, rdi
0x1800927e5  call    LoadMUIFile
0x1800927ea  mov     rbx, rax
0x1800927ed  test    rax, rax
0x1800927f0  jnz     loc_1800929F2
0x1800927f6  mov     r9, [rsp+4A0h+FilePart]
0x1800927fb  lea     r8, [rbp+3A0h+var_300]
0x180092802  mov     rdx, rsi
0x180092805  mov     rcx, rdi
0x180092808  call    LoadMUIFile
0x18009280d  mov     rbx, rax
0x180092810  test    rax, rax
0x180092813  jnz     loc_1800929F2
0x180092819  cmp     [rbp+3A0h+var_3B0], r13w
0x18009281e  jz      short loc_180092840
0x180092820  mov     r9, [rsp+4A0h+FilePart]
0x180092825  lea     r8, [rbp+3A0h+var_3B0]
0x180092829  mov     rdx, rsi
0x18009282c  mov     rcx, rdi
0x18009282f  call    LoadMUIFile
0x180092834  mov     rbx, rax
0x180092837  test    rax, rax
0x18009283a  jnz     loc_1800929F2
0x180092840  mov     ecx, 409h
0x180092845  cmp     cx, r14w
0x180092849  jz      loc_180092934
0x18009284f  cmp     cx, r15w
0x180092853  jmp     loc_1800928FD
0x180092858  test    al, 3
0x18009285a  jz      loc_180092953
0x180092860  call    GetInstallLanguage
0x180092865  lea     r9, [rbp+3A0h+var_3B0]
0x180092869  movzx   ecx, ax
0x18009286c  lea     r8, [rbp+3A0h+var_300]
0x180092873  movzx   r14d, ax
0x180092877  lea     rdx, [rsp+4A0h+var_460]
0x18009287c  call    LookupLangID
0x180092881  test    eax, eax
0x180092883  jz      loc_180092953
0x180092889  mov     r9, [rsp+4A0h+FilePart]
0x18009288e  lea     r8, [rsp+4A0h+var_460]
0x180092893  mov     rdx, rsi
0x180092896  mov     rcx, rdi
0x180092899  call    LoadMUIFile
0x18009289e  mov     rbx, rax
0x1800928a1  test    rax, rax
0x1800928a4  jnz     loc_1800929F2
0x1800928aa  mov     r9, [rsp+4A0h+FilePart]
0x1800928af  lea     r8, [rbp+3A0h+var_300]
0x1800928b6  mov     rdx, rsi
0x1800928b9  mov     rcx, rdi
0x1800928bc  call    LoadMUIFile
0x1800928c1  mov     rbx, rax
0x1800928c4  test    rax, rax
0x1800928c7  jnz     loc_1800929F2
0x1800928cd  cmp     [rbp+3A0h+var_3B0], r13w
0x1800928d2  jz      short loc_1800928F4
0x1800928d4  mov     r9, [rsp+4A0h+FilePart]
0x1800928d9  lea     r8, [rbp+3A0h+var_3B0]
0x1800928dd  mov     rdx, rsi
0x1800928e0  mov     rcx, rdi
0x1800928e3  call    LoadMUIFile
0x1800928e8  mov     rbx, rax
0x1800928eb  test    rax, rax
0x1800928ee  jnz     loc_1800929F2
0x1800928f4  mov     ecx, 409h
0x1800928f9  cmp     cx, r14w
0x1800928fd  jz      short loc_180092934
0x1800928ff  xor     r9d, r9d
0x180092902  lea     r8, [rbp+3A0h+var_300]
0x180092909  lea     rdx, [rsp+4A0h+var_460]
0x18009290e  call    LookupLangID
0x180092913  mov     r9, [rsp+4A0h+FilePart]
0x180092918  lea     r8, [rsp+4A0h+var_460]
0x18009291d  mov     rdx, rsi
0x180092920  mov     rcx, rdi
0x180092923  call    LoadMUIFile
0x180092928  mov     rbx, rax
0x18009292b  test    rax, rax
0x18009292e  jnz     loc_1800929F2
0x180092934  mov     r9, [rsp+4A0h+FilePart]
0x180092939  xor     r8d, r8d
0x18009293c  mov     rdx, rsi
0x18009293f  mov     rcx, rdi
0x180092942  call    LoadMUIFile
0x180092947  mov     rbx, rax
0x18009294a  test    rax, rax
0x18009294d  jnz     loc_1800929F2
0x180092953  test    dil, 1
0x180092957  jz      loc_180092A1C
0x18009295d  mov     rcx, rdi; hLibModule
0x180092960  call    cs:__imp_FreeLibrary
0x180092966  call    GetOSType
0x18009296b  test    al, 38h
0x18009296d  jz      loc_180092A00
0x180092973  mov     rax, [rsp+4A0h+FilePart]
0x180092978  lea     r8, aSS; "%s\\%s"
0x18009297f  mov     r9, rsi
0x180092982  mov     [rsp+4A0h+lpBuffer], rax
0x180092987  mov     edx, 104h; unsigned __int64
0x18009298c  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180092993  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092998  xor     r8d, r8d
0x18009299b  lea     rcx, [rbp+3A0h+Buffer]
0x1800929a2  lea     edx, [r8+1]
0x1800929a6  call    MapMUIFile
0x1800929ab  jmp     short loc_180092A19
0x1800929ad  test    byte ptr cs:dword_1800B7140, 7
0x1800929b4  jz      short loc_180092953
0x1800929b6  xor     r9d, r9d
0x1800929b9  lea     r8, [rbp+3A0h+var_300]
0x1800929c0  lea     rdx, [rsp+4A0h+var_460]
0x1800929c5  movzx   ecx, bx
0x1800929c8  call    LookupLangID
0x1800929cd  test    eax, eax
0x1800929cf  jz      short loc_180092953
0x1800929d1  mov     r9, [rsp+4A0h+FilePart]
0x1800929d6  lea     r8, [rsp+4A0h+var_460]
0x1800929db  mov     rdx, rsi
0x1800929de  mov     rcx, rdi
0x1800929e1  call    LoadMUIFile
0x1800929e6  mov     rbx, rax
0x1800929e9  test    rbx, rbx
0x1800929ec  jz      loc_180092953
0x1800929f2  mov     rcx, rdi; hLibModule
0x1800929f5  call    cs:__imp_FreeLibrary
0x1800929fb  mov     rax, rbx
0x1800929fe  jmp     short loc_180092A2C
0x180092a00  call    GetOSType
0x180092a05  test    al, 26h
0x180092a07  mov     r8d, r13d
0x180092a0a  mov     rcx, r12; lpLibFileName
0x180092a0d  setnz   r8b; dwFlags
0x180092a11  xor     edx, edx; hFile
0x180092a13  call    cs:__imp_LoadLibraryExW
0x180092a19  mov     rdi, rax
0x180092a1c  mov     rax, rdi
0x180092a1f  jmp     short loc_180092A2C
0x180092a21  mov     rcx, rdi; hLibModule
0x180092a24  call    cs:__imp_FreeLibrary
0x180092a2a  xor     eax, eax
0x180092a2c  mov     rcx, [rbp+3A0h+var_40]
0x180092a33  xor     rcx, rsp; StackCookie
0x180092a36  call    __security_check_cookie
0x180092a3b  mov     rbx, [rsp+4A0h+arg_8]
0x180092a43  add     rsp, 470h
0x180092a4a  pop     r15
0x180092a4c  pop     r14
0x180092a4e  pop     r13
0x180092a50  pop     r12
0x180092a52  pop     rdi
0x180092a53  pop     rsi
0x180092a54  pop     rbp
0x180092a55  retn
```
