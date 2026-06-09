# LoadMUILibraryW

- ea: `0x180219494`
- end: `0x180219907`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1801aa3b0`

## callees

- `0x180085e04`
- `0x180218db0`
- `0x180218e30`
- `0x180218f44`
- `0x18021906c`
- `0x1802190e0`
- `0x180219254`
- `0x180219494`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1802194ee`
- `KERNEL32!LoadLibraryExW` at `0x1802198cb`
- `KERNEL32!LoadLibraryExW` at `0x1802194ee`
- `KERNEL32!LoadLibraryExW` at `0x1802198cb`
- `KERNEL32!FreeLibrary` at `0x180219766`
- `KERNEL32!FreeLibrary` at `0x1802198ad`
- `KERNEL32!FreeLibrary` at `0x1802198dc`
- `KERNEL32!FreeLibrary` at `0x180219766`
- `KERNEL32!FreeLibrary` at `0x1802198ad`
- `KERNEL32!FreeLibrary` at `0x1802198dc`
- `KERNEL32!SearchPathW` at `0x180219531`
- `KERNEL32!SearchPathW` at `0x180219531`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180219655`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180219655`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180219597`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180219597`
- `KERNEL32!FindResourceExW` at `0x180219577`
- `KERNEL32!FindResourceExW` at `0x180219577`

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
  dword_1808CFA88 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1808CFA88 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1808CFA88 & 0x20) != 0 )
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
    if ( (dword_1808CFA88 & 4) != 0 )
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
    else if ( (dword_1808CFA88 & 3) != 0 )
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
0x180219494  push    rbp
0x180219496  push    rbx
0x180219497  push    rsi
0x180219498  push    rdi
0x180219499  push    r12
0x18021949b  push    r13
0x18021949d  push    r14
0x18021949f  push    r15
0x1802194a1  lea     rbp, [rsp-378h]
0x1802194a9  sub     rsp, 478h
0x1802194b0  mov     rax, cs:__security_cookie
0x1802194b7  xor     rax, rsp
0x1802194ba  mov     [rbp+3B0h+var_50], rax
0x1802194c1  xor     r13d, r13d
0x1802194c4  mov     r12, rcx
0x1802194c7  mov     [rsp+4B0h+FilePart], r13
0x1802194cc  test    rcx, rcx
0x1802194cf  jz      loc_1802198E2
0x1802194d5  call    GetOSType
0x1802194da  mov     cs:dword_1808CFA88, eax
0x1802194e0  xor     edx, edx; hFile
0x1802194e2  and     eax, 20h
0x1802194e5  mov     rcx, r12; lpLibFileName
0x1802194e8  or      eax, 2
0x1802194eb  mov     r8d, eax; dwFlags
0x1802194ee  call    cs:__imp_LoadLibraryExW
0x1802194f4  mov     rdi, rax
0x1802194f7  test    rax, rax
0x1802194fa  jz      loc_1802198E2
0x180219500  test    byte ptr cs:dword_1808CFA88, 20h
0x180219507  jnz     loc_1802198E4
0x18021950d  lea     rax, [rsp+4B0h+FilePart]
0x180219512  mov     r9d, 104h; nBufferLength
0x180219518  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x18021951d  xor     r8d, r8d; lpExtension
0x180219520  lea     rax, [rbp+3B0h+Buffer]
0x180219527  mov     rdx, r12; lpFileName
0x18021952a  xor     ecx, ecx; lpPath
0x18021952c  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180219531  call    cs:__imp_SearchPathW
0x180219537  test    eax, eax
0x180219539  jz      loc_1802198D9
0x18021953f  mov     rcx, [rsp+4B0h+FilePart]
0x180219544  test    rcx, rcx
0x180219547  jnz     short loc_18021955A
0x180219549  lea     rax, [rbp+3B0h+Buffer]
0x180219550  mov     esi, r13d
0x180219553  mov     [rsp+4B0h+FilePart], rax
0x180219558  jmp     short loc_180219566
0x18021955a  lea     rsi, [rbp+3B0h+Buffer]
0x180219561  mov     [rcx-2], r13w
0x180219566  xor     r9d, r9d; wLanguage
0x180219569  lea     rdx, Type; "MUI"
0x180219570  mov     rcx, rdi; hModule
0x180219573  lea     r8d, [r9+1]; lpName
0x180219577  call    cs:__imp_FindResourceExW
0x18021957d  test    rax, rax
0x180219580  jz      loc_180219759
0x180219586  mov     eax, cs:dword_1808CFA88
0x18021958c  test    al, 4
0x18021958e  jz      loc_1802197B6
0x180219594  mov     rbx, r13
0x180219597  call    cs:__imp_GetUserDefaultUILanguage
0x18021959d  mov     r15d, 404h
0x1802195a3  movzx   r14d, ax
0x1802195a7  cmp     ax, r15w
0x1802195ab  jnz     short loc_1802195B6
0x1802195ad  call    GetCHTLangauge
0x1802195b2  movzx   r14d, ax
0x1802195b6  lea     r9, [rbp+3B0h+var_3C0]
0x1802195ba  movzx   ecx, r14w
0x1802195be  lea     r8, [rbp+3B0h+var_310]
0x1802195c5  lea     rdx, [rsp+4B0h+var_470]
0x1802195ca  call    LookupLangID
0x1802195cf  test    eax, eax
0x1802195d1  jz      loc_1802198A1
0x1802195d7  mov     r9, [rsp+4B0h+FilePart]
0x1802195dc  lea     r8, [rsp+4B0h+var_470]
0x1802195e1  mov     rdx, rsi
0x1802195e4  mov     rcx, rdi
0x1802195e7  call    LoadMUIFile
0x1802195ec  mov     rbx, rax
0x1802195ef  test    rax, rax
0x1802195f2  jnz     loc_1802198AA
0x1802195f8  mov     r9, [rsp+4B0h+FilePart]
0x1802195fd  lea     r8, [rbp+3B0h+var_310]
0x180219604  mov     rdx, rsi
0x180219607  mov     rcx, rdi
0x18021960a  call    LoadMUIFile
0x18021960f  mov     rbx, rax
0x180219612  test    rax, rax
0x180219615  jnz     loc_1802198AA
0x18021961b  cmp     [rbp+3B0h+var_3C0], r13w
0x180219620  jz      short loc_180219642
0x180219622  mov     r9, [rsp+4B0h+FilePart]
0x180219627  lea     r8, [rbp+3B0h+var_3C0]
0x18021962b  mov     rdx, rsi
0x18021962e  mov     rcx, rdi
0x180219631  call    LoadMUIFile
0x180219636  mov     rbx, rax
0x180219639  test    rax, rax
0x18021963c  jnz     loc_1802198AA
0x180219642  mov     eax, 0C04h
0x180219647  cmp     r14w, ax
0x18021964b  jnz     short loc_180219655
0x18021964d  mov     r14d, r15d
0x180219650  jmp     loc_1802195B6
0x180219655  call    cs:__imp_GetSystemDefaultUILanguage
0x18021965b  movzx   r15d, ax
0x18021965f  cmp     ax, r14w
0x180219663  jz      loc_1802196F4
0x180219669  lea     r9, [rbp+3B0h+var_3C0]
0x18021966d  movzx   ecx, ax
0x180219670  lea     r8, [rbp+3B0h+var_310]
0x180219677  lea     rdx, [rsp+4B0h+var_470]
0x18021967c  call    LookupLangID
0x180219681  test    eax, eax
0x180219683  jz      loc_180219759
0x180219689  mov     r9, [rsp+4B0h+FilePart]
0x18021968e  lea     r8, [rsp+4B0h+var_470]
0x180219693  mov     rdx, rsi
0x180219696  mov     rcx, rdi
0x180219699  call    LoadMUIFile
0x18021969e  mov     rbx, rax
0x1802196a1  test    rax, rax
0x1802196a4  jnz     loc_1802198AA
0x1802196aa  mov     r9, [rsp+4B0h+FilePart]
0x1802196af  lea     r8, [rbp+3B0h+var_310]
0x1802196b6  mov     rdx, rsi
0x1802196b9  mov     rcx, rdi
0x1802196bc  call    LoadMUIFile
0x1802196c1  mov     rbx, rax
0x1802196c4  test    rax, rax
0x1802196c7  jnz     loc_1802198AA
0x1802196cd  cmp     [rbp+3B0h+var_3C0], r13w
0x1802196d2  jz      short loc_1802196F4
0x1802196d4  mov     r9, [rsp+4B0h+FilePart]
0x1802196d9  lea     r8, [rbp+3B0h+var_3C0]
0x1802196dd  mov     rdx, rsi
0x1802196e0  mov     rcx, rdi
0x1802196e3  call    LoadMUIFile
0x1802196e8  mov     rbx, rax
0x1802196eb  test    rax, rax
0x1802196ee  jnz     loc_1802198AA
0x1802196f4  mov     ecx, 409h
0x1802196f9  cmp     cx, r14w
0x1802196fd  jz      short loc_18021973A
0x1802196ff  cmp     cx, r15w
0x180219703  jz      short loc_18021973A
0x180219705  xor     r9d, r9d
0x180219708  lea     r8, [rbp+3B0h+var_310]
0x18021970f  lea     rdx, [rsp+4B0h+var_470]
0x180219714  call    LookupLangID
0x180219719  mov     r9, [rsp+4B0h+FilePart]
0x18021971e  lea     r8, [rsp+4B0h+var_470]
0x180219723  mov     rdx, rsi
0x180219726  mov     rcx, rdi
0x180219729  call    LoadMUIFile
0x18021972e  mov     rbx, rax
0x180219731  test    rax, rax
0x180219734  jnz     loc_1802198AA
0x18021973a  mov     r9, [rsp+4B0h+FilePart]
0x18021973f  xor     r8d, r8d
0x180219742  mov     rdx, rsi
0x180219745  mov     rcx, rdi
0x180219748  call    LoadMUIFile
0x18021974d  mov     rbx, rax
0x180219750  test    rax, rax
0x180219753  jnz     loc_1802198AA
0x180219759  test    dil, 1
0x18021975d  jz      loc_1802198D4
0x180219763  mov     rcx, rdi; hLibModule
0x180219766  call    cs:__imp_FreeLibrary
0x18021976c  call    GetOSType
0x180219771  test    al, 38h
0x180219773  jz      loc_1802198B8
0x180219779  mov     rax, [rsp+4B0h+FilePart]
0x18021977e  lea     r8, aSS_4; "%s\\%s"
0x180219785  mov     r9, rsi
0x180219788  mov     [rsp+4B0h+lpBuffer], rax
0x18021978d  mov     edx, 104h; unsigned __int64
0x180219792  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180219799  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18021979e  xor     r8d, r8d
0x1802197a1  lea     rcx, [rbp+3B0h+Buffer]
0x1802197a8  lea     edx, [r8+1]
0x1802197ac  call    MapMUIFile
0x1802197b1  jmp     loc_1802198D1
0x1802197b6  test    al, 3
0x1802197b8  jz      short loc_180219759
0x1802197ba  call    GetInstallLanguage
0x1802197bf  lea     r9, [rbp+3B0h+var_3C0]
0x1802197c3  movzx   ecx, ax
0x1802197c6  lea     r8, [rbp+3B0h+var_310]
0x1802197cd  movzx   r14d, ax
0x1802197d1  lea     rdx, [rsp+4B0h+var_470]
0x1802197d6  call    LookupLangID
0x1802197db  test    eax, eax
0x1802197dd  jz      loc_180219759
0x1802197e3  mov     r9, [rsp+4B0h+FilePart]
0x1802197e8  lea     r8, [rsp+4B0h+var_470]
0x1802197ed  mov     rdx, rsi
0x1802197f0  mov     rcx, rdi
0x1802197f3  call    LoadMUIFile
0x1802197f8  mov     rbx, rax
0x1802197fb  test    rax, rax
0x1802197fe  jnz     loc_1802198AA
0x180219804  mov     r9, [rsp+4B0h+FilePart]
0x180219809  lea     r8, [rbp+3B0h+var_310]
0x180219810  mov     rdx, rsi
0x180219813  mov     rcx, rdi
0x180219816  call    LoadMUIFile
0x18021981b  mov     rbx, rax
0x18021981e  test    rax, rax
0x180219821  jnz     loc_1802198AA
0x180219827  cmp     [rbp+3B0h+var_3C0], r13w
0x18021982c  jz      short loc_18021984A
0x18021982e  mov     r9, [rsp+4B0h+FilePart]
0x180219833  lea     r8, [rbp+3B0h+var_3C0]
0x180219837  mov     rdx, rsi
0x18021983a  mov     rcx, rdi
0x18021983d  call    LoadMUIFile
0x180219842  mov     rbx, rax
0x180219845  test    rax, rax
0x180219848  jnz     short loc_1802198AA
0x18021984a  mov     ecx, 409h
0x18021984f  cmp     cx, r14w
0x180219853  jz      short loc_180219886
0x180219855  xor     r9d, r9d
0x180219858  lea     r8, [rbp+3B0h+var_310]
0x18021985f  lea     rdx, [rsp+4B0h+var_470]
0x180219864  call    LookupLangID
0x180219869  mov     r9, [rsp+4B0h+FilePart]
0x18021986e  lea     r8, [rsp+4B0h+var_470]
0x180219873  mov     rdx, rsi
0x180219876  mov     rcx, rdi
0x180219879  call    LoadMUIFile
0x18021987e  mov     rbx, rax
0x180219881  test    rax, rax
0x180219884  jnz     short loc_1802198AA
0x180219886  mov     r9, [rsp+4B0h+FilePart]
0x18021988b  xor     r8d, r8d
0x18021988e  mov     rdx, rsi
0x180219891  mov     rcx, rdi
0x180219894  call    LoadMUIFile
0x180219899  mov     rbx, rax
0x18021989c  test    rax, rax
0x18021989f  jnz     short loc_1802198AA
0x1802198a1  test    rbx, rbx
0x1802198a4  jz      loc_180219759
0x1802198aa  mov     rcx, rdi; hLibModule
0x1802198ad  call    cs:__imp_FreeLibrary
0x1802198b3  mov     rax, rbx
0x1802198b6  jmp     short loc_1802198E4
0x1802198b8  call    GetOSType
0x1802198bd  test    al, 26h
0x1802198bf  mov     r8d, r13d
0x1802198c2  mov     rcx, r12; lpLibFileName
0x1802198c5  setnz   r8b; dwFlags
0x1802198c9  xor     edx, edx; hFile
0x1802198cb  call    cs:__imp_LoadLibraryExW
0x1802198d1  mov     rdi, rax
0x1802198d4  mov     rax, rdi
0x1802198d7  jmp     short loc_1802198E4
0x1802198d9  mov     rcx, rdi; hLibModule
0x1802198dc  call    cs:__imp_FreeLibrary
0x1802198e2  xor     eax, eax
0x1802198e4  mov     rcx, [rbp+3B0h+var_50]
0x1802198eb  xor     rcx, rsp; StackCookie
0x1802198ee  call    __security_check_cookie
0x1802198f3  add     rsp, 478h
0x1802198fa  pop     r15
0x1802198fc  pop     r14
0x1802198fe  pop     r13
0x180219900  pop     r12
0x180219902  pop     rdi
0x180219903  pop     rsi
0x180219904  pop     rbx
0x180219905  pop     rbp
0x180219906  retn
```
