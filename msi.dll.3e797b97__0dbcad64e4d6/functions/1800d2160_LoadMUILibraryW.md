# LoadMUILibraryW

- ea: `0x1800d2160`
- end: `0x1800d2627`
- name: `LoadMUILibraryW`
- size: `1223`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800d0a50`
- `0x1800d20e8`

## callees

- `0x180010ac0`
- `0x1800d2160`
- `0x18014e064`
- `0x180263f7c`
- `0x180264004`
- `0x180264134`
- `0x1802641a8`
- `0x180264334`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800d2347`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800d2347`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800d2283`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800d2283`
- `KERNEL32!LoadLibraryExW` at `0x1800d21bb`
- `KERNEL32!LoadLibraryExW` at `0x1800d25d6`
- `KERNEL32!LoadLibraryExW` at `0x1800d21bb`
- `KERNEL32!LoadLibraryExW` at `0x1800d25d6`
- `KERNEL32!FreeLibrary` at `0x1800d250c`
- `KERNEL32!FreeLibrary` at `0x1800d25ae`
- `KERNEL32!FreeLibrary` at `0x1800d25ed`
- `KERNEL32!FreeLibrary` at `0x1800d250c`
- `KERNEL32!FreeLibrary` at `0x1800d25ae`
- `KERNEL32!FreeLibrary` at `0x1800d25ed`
- `KERNEL32!FindResourceExW` at `0x1800d2254`
- `KERNEL32!FindResourceExW` at `0x1800d2254`
- `KERNEL32!SearchPathW` at `0x1800d2208`
- `KERNEL32!SearchPathW` at `0x1800d2208`

## string_xrefs

- `0x1800d21a9`: `MsiMsg.dll`
- `0x1800d21f0`: `MsiMsg.dll`
- `0x1800d25c6`: `MsiMsg.dll`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rdi
  WCHAR *v6; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r15
  bool v11; // zf
  __int64 InstallLanguage; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  dword_18031539C = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(L"MsiMsg.dll", 0, dword_18031539C & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_18031539C & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"MsiMsg.dll", 0, 0x104u, Buffer, &FilePart) )
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
    if ( !LangID )
    {
      if ( (dword_18031539C & 4) == 0 )
      {
        if ( (dword_18031539C & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
            v11 = (_WORD)InstallLanguage == 1033;
LABEL_34:
            if ( !v11 )
            {
              LookupLangID(1033, v20, v22, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
LABEL_36:
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
            if ( MUIFile )
            {
LABEL_44:
              FreeLibrary(v5);
              return MUIFile;
            }
          }
        }
        goto LABEL_37;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
        if ( MUIFile )
          goto LABEL_44;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
        if ( MUIFile )
          goto LABEL_44;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
          if ( MUIFile )
            goto LABEL_44;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              goto LABEL_37;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_36;
          v11 = v10 == 1033;
          goto LABEL_34;
        }
        UserDefaultUILanguage = 1028;
      }
      goto LABEL_43;
    }
    if ( (dword_18031539C & 7) != 0 && (unsigned int)LookupLangID(LangID, v20, v22, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
LABEL_43:
      if ( MUIFile )
        goto LABEL_44;
    }
  }
LABEL_37:
  if ( ((unsigned __int8)v5 & 1) != 0 )
  {
    FreeLibrary(v5);
    if ( (GetOSType(v14, v13) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v16, v15);
      return LoadLibraryExW(L"MsiMsg.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800d2160  mov     [rsp-8+arg_0], rbx
0x1800d2165  mov     [rsp-8+arg_8], rsi
0x1800d216a  push    rbp
0x1800d216b  push    rdi
0x1800d216c  push    r12
0x1800d216e  push    r14
0x1800d2170  push    r15
0x1800d2172  lea     rbp, [rsp-370h]
0x1800d217a  sub     rsp, 470h
0x1800d2181  mov     rax, cs:__security_cookie
0x1800d2188  xor     rax, rsp
0x1800d218b  mov     [rbp+390h+var_30], rax
0x1800d2192  xor     r12d, r12d
0x1800d2195  movzx   ebx, r8w
0x1800d2199  mov     [rsp+490h+FilePart], r12
0x1800d219e  call    GetOSType
0x1800d21a3  mov     cs:dword_18031539C, eax
0x1800d21a9  lea     rcx, FileName; "MsiMsg.dll"
0x1800d21b0  and     eax, 20h
0x1800d21b3  xor     edx, edx; hFile
0x1800d21b5  or      eax, 2
0x1800d21b8  mov     r8d, eax; dwFlags
0x1800d21bb  call    cs:__imp_LoadLibraryExW
0x1800d21c2  nop     dword ptr [rax+rax+00h]
0x1800d21c7  mov     rdi, rax
0x1800d21ca  test    rax, rax
0x1800d21cd  jz      loc_1800D25F9
0x1800d21d3  test    byte ptr cs:dword_18031539C, 20h
0x1800d21da  jnz     loc_1800D25FB
0x1800d21e0  lea     rax, [rsp+490h+FilePart]
0x1800d21e5  mov     r9d, 104h; nBufferLength
0x1800d21eb  mov     [rsp+490h+lpFilePart], rax; lpFilePart
0x1800d21f0  lea     rdx, FileName; "MsiMsg.dll"
0x1800d21f7  lea     rax, [rbp+390h+Buffer]
0x1800d21fe  xor     r8d, r8d; lpExtension
0x1800d2201  xor     ecx, ecx; lpPath
0x1800d2203  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x1800d2208  call    cs:__imp_SearchPathW
0x1800d220f  nop     dword ptr [rax+rax+00h]
0x1800d2214  test    eax, eax
0x1800d2216  jz      loc_1800D25EA
0x1800d221c  mov     rcx, [rsp+490h+FilePart]
0x1800d2221  test    rcx, rcx
0x1800d2224  jnz     short loc_1800D2237
0x1800d2226  lea     rax, [rbp+390h+Buffer]
0x1800d222d  mov     esi, r12d
0x1800d2230  mov     [rsp+490h+FilePart], rax
0x1800d2235  jmp     short loc_1800D2243
0x1800d2237  lea     rsi, [rbp+390h+Buffer]
0x1800d223e  mov     [rcx-2], r12w
0x1800d2243  xor     r9d, r9d; wLanguage
0x1800d2246  lea     rdx, Type; "MUI"
0x1800d224d  mov     rcx, rdi; hModule
0x1800d2250  lea     r8d, [r9+1]; lpName
0x1800d2254  call    cs:__imp_FindResourceExW
0x1800d225b  nop     dword ptr [rax+rax+00h]
0x1800d2260  test    rax, rax
0x1800d2263  jz      loc_1800D24FF
0x1800d2269  test    bx, bx
0x1800d226c  jnz     loc_1800D2562
0x1800d2272  mov     eax, cs:dword_18031539C
0x1800d2278  test    al, 4
0x1800d227a  jz      loc_1800D2404
0x1800d2280  mov     rbx, r12
0x1800d2283  call    cs:__imp_GetUserDefaultUILanguage
0x1800d228a  nop     dword ptr [rax+rax+00h]
0x1800d228f  mov     r15d, 404h
0x1800d2295  movzx   r14d, ax
0x1800d2299  cmp     ax, r15w
0x1800d229d  jnz     short loc_1800D22A8
0x1800d229f  call    GetCHTLangauge
0x1800d22a4  movzx   r14d, ax
0x1800d22a8  lea     r9, [rbp+390h+var_3A0]
0x1800d22ac  movzx   ecx, r14w
0x1800d22b0  lea     r8, [rbp+390h+var_2F0]
0x1800d22b7  lea     rdx, [rsp+490h+var_450]
0x1800d22bc  call    LookupLangID
0x1800d22c1  test    eax, eax
0x1800d22c3  jz      loc_1800D25A2
0x1800d22c9  mov     r9, [rsp+490h+FilePart]
0x1800d22ce  lea     r8, [rsp+490h+var_450]
0x1800d22d3  mov     rdx, rsi
0x1800d22d6  mov     rcx, rdi
0x1800d22d9  call    LoadMUIFile
0x1800d22de  mov     rbx, rax
0x1800d22e1  test    rax, rax
0x1800d22e4  jnz     loc_1800D25AB
0x1800d22ea  mov     r9, [rsp+490h+FilePart]
0x1800d22ef  lea     r8, [rbp+390h+var_2F0]
0x1800d22f6  mov     rdx, rsi
0x1800d22f9  mov     rcx, rdi
0x1800d22fc  call    LoadMUIFile
0x1800d2301  mov     rbx, rax
0x1800d2304  test    rax, rax
0x1800d2307  jnz     loc_1800D25AB
0x1800d230d  cmp     [rbp+390h+var_3A0], r12w
0x1800d2312  jz      short loc_1800D2334
0x1800d2314  mov     r9, [rsp+490h+FilePart]
0x1800d2319  lea     r8, [rbp+390h+var_3A0]
0x1800d231d  mov     rdx, rsi
0x1800d2320  mov     rcx, rdi
0x1800d2323  call    LoadMUIFile
0x1800d2328  mov     rbx, rax
0x1800d232b  test    rax, rax
0x1800d232e  jnz     loc_1800D25AB
0x1800d2334  mov     eax, 0C04h
0x1800d2339  cmp     r14w, ax
0x1800d233d  jnz     short loc_1800D2347
0x1800d233f  mov     r14d, r15d
0x1800d2342  jmp     loc_1800D22A8
0x1800d2347  call    cs:__imp_GetSystemDefaultUILanguage
0x1800d234e  nop     dword ptr [rax+rax+00h]
0x1800d2353  movzx   r15d, ax
0x1800d2357  cmp     ax, r14w
0x1800d235b  jz      loc_1800D23EC
0x1800d2361  lea     r9, [rbp+390h+var_3A0]
0x1800d2365  movzx   ecx, ax
0x1800d2368  lea     r8, [rbp+390h+var_2F0]
0x1800d236f  lea     rdx, [rsp+490h+var_450]
0x1800d2374  call    LookupLangID
0x1800d2379  test    eax, eax
0x1800d237b  jz      loc_1800D24FF
0x1800d2381  mov     r9, [rsp+490h+FilePart]
0x1800d2386  lea     r8, [rsp+490h+var_450]
0x1800d238b  mov     rdx, rsi
0x1800d238e  mov     rcx, rdi
0x1800d2391  call    LoadMUIFile
0x1800d2396  mov     rbx, rax
0x1800d2399  test    rax, rax
0x1800d239c  jnz     loc_1800D25AB
0x1800d23a2  mov     r9, [rsp+490h+FilePart]
0x1800d23a7  lea     r8, [rbp+390h+var_2F0]
0x1800d23ae  mov     rdx, rsi
0x1800d23b1  mov     rcx, rdi
0x1800d23b4  call    LoadMUIFile
0x1800d23b9  mov     rbx, rax
0x1800d23bc  test    rax, rax
0x1800d23bf  jnz     loc_1800D25AB
0x1800d23c5  cmp     [rbp+390h+var_3A0], r12w
0x1800d23ca  jz      short loc_1800D23EC
0x1800d23cc  mov     r9, [rsp+490h+FilePart]
0x1800d23d1  lea     r8, [rbp+390h+var_3A0]
0x1800d23d5  mov     rdx, rsi
0x1800d23d8  mov     rcx, rdi
0x1800d23db  call    LoadMUIFile
0x1800d23e0  mov     rbx, rax
0x1800d23e3  test    rax, rax
0x1800d23e6  jnz     loc_1800D25AB
0x1800d23ec  mov     ecx, 409h
0x1800d23f1  cmp     cx, r14w
0x1800d23f5  jz      loc_1800D24E0
0x1800d23fb  cmp     cx, r15w
0x1800d23ff  jmp     loc_1800D24A9
0x1800d2404  test    al, 3
0x1800d2406  jz      loc_1800D24FF
0x1800d240c  call    GetInstallLanguage
0x1800d2411  lea     r9, [rbp+390h+var_3A0]
0x1800d2415  movzx   ecx, ax
0x1800d2418  lea     r8, [rbp+390h+var_2F0]
0x1800d241f  movzx   r14d, ax
0x1800d2423  lea     rdx, [rsp+490h+var_450]
0x1800d2428  call    LookupLangID
0x1800d242d  test    eax, eax
0x1800d242f  jz      loc_1800D24FF
0x1800d2435  mov     r9, [rsp+490h+FilePart]
0x1800d243a  lea     r8, [rsp+490h+var_450]
0x1800d243f  mov     rdx, rsi
0x1800d2442  mov     rcx, rdi
0x1800d2445  call    LoadMUIFile
0x1800d244a  mov     rbx, rax
0x1800d244d  test    rax, rax
0x1800d2450  jnz     loc_1800D25AB
0x1800d2456  mov     r9, [rsp+490h+FilePart]
0x1800d245b  lea     r8, [rbp+390h+var_2F0]
0x1800d2462  mov     rdx, rsi
0x1800d2465  mov     rcx, rdi
0x1800d2468  call    LoadMUIFile
0x1800d246d  mov     rbx, rax
0x1800d2470  test    rax, rax
0x1800d2473  jnz     loc_1800D25AB
0x1800d2479  cmp     [rbp+390h+var_3A0], r12w
0x1800d247e  jz      short loc_1800D24A0
0x1800d2480  mov     r9, [rsp+490h+FilePart]
0x1800d2485  lea     r8, [rbp+390h+var_3A0]
0x1800d2489  mov     rdx, rsi
0x1800d248c  mov     rcx, rdi
0x1800d248f  call    LoadMUIFile
0x1800d2494  mov     rbx, rax
0x1800d2497  test    rax, rax
0x1800d249a  jnz     loc_1800D25AB
0x1800d24a0  mov     ecx, 409h
0x1800d24a5  cmp     cx, r14w
0x1800d24a9  jz      short loc_1800D24E0
0x1800d24ab  xor     r9d, r9d
0x1800d24ae  lea     r8, [rbp+390h+var_2F0]
0x1800d24b5  lea     rdx, [rsp+490h+var_450]
0x1800d24ba  call    LookupLangID
0x1800d24bf  mov     r9, [rsp+490h+FilePart]
0x1800d24c4  lea     r8, [rsp+490h+var_450]
0x1800d24c9  mov     rdx, rsi
0x1800d24cc  mov     rcx, rdi
0x1800d24cf  call    LoadMUIFile
0x1800d24d4  mov     rbx, rax
0x1800d24d7  test    rax, rax
0x1800d24da  jnz     loc_1800D25AB
0x1800d24e0  mov     r9, [rsp+490h+FilePart]
0x1800d24e5  xor     r8d, r8d
0x1800d24e8  mov     rdx, rsi
0x1800d24eb  mov     rcx, rdi
0x1800d24ee  call    LoadMUIFile
0x1800d24f3  mov     rbx, rax
0x1800d24f6  test    rax, rax
0x1800d24f9  jnz     loc_1800D25AB
0x1800d24ff  test    dil, 1
0x1800d2503  jz      loc_1800D25E5
0x1800d2509  mov     rcx, rdi; hLibModule
0x1800d250c  call    cs:__imp_FreeLibrary
0x1800d2513  nop     dword ptr [rax+rax+00h]
0x1800d2518  call    GetOSType
0x1800d251d  test    al, 38h
0x1800d251f  jz      loc_1800D25BF
0x1800d2525  mov     rax, [rsp+490h+FilePart]
0x1800d252a  lea     r8, aSS_0; "%s\\%s"
0x1800d2531  mov     r9, rsi
0x1800d2534  mov     [rsp+490h+lpBuffer], rax
0x1800d2539  mov     edx, 104h; unsigned __int64
0x1800d253e  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x1800d2545  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d254a  xor     r8d, r8d
0x1800d254d  lea     rcx, [rbp+390h+Buffer]
0x1800d2554  lea     edx, [r8+1]
0x1800d2558  call    MapMUIFile
0x1800d255d  jmp     loc_1800D25E2
0x1800d2562  test    byte ptr cs:dword_18031539C, 7
0x1800d2569  jz      short loc_1800D24FF
0x1800d256b  xor     r9d, r9d
0x1800d256e  lea     r8, [rbp+390h+var_2F0]
0x1800d2575  lea     rdx, [rsp+490h+var_450]
0x1800d257a  movzx   ecx, bx
0x1800d257d  call    LookupLangID
0x1800d2582  test    eax, eax
0x1800d2584  jz      loc_1800D24FF
0x1800d258a  mov     r9, [rsp+490h+FilePart]
0x1800d258f  lea     r8, [rsp+490h+var_450]
0x1800d2594  mov     rdx, rsi
0x1800d2597  mov     rcx, rdi
0x1800d259a  call    LoadMUIFile
0x1800d259f  mov     rbx, rax
0x1800d25a2  test    rbx, rbx
0x1800d25a5  jz      loc_1800D24FF
0x1800d25ab  mov     rcx, rdi; hLibModule
0x1800d25ae  call    cs:__imp_FreeLibrary
0x1800d25b5  nop     dword ptr [rax+rax+00h]
0x1800d25ba  mov     rax, rbx
0x1800d25bd  jmp     short loc_1800D25FB
0x1800d25bf  call    GetOSType
0x1800d25c4  test    al, 26h
0x1800d25c6  lea     rcx, FileName; "MsiMsg.dll"
0x1800d25cd  mov     r8d, r12d
0x1800d25d0  setnz   r8b; dwFlags
0x1800d25d4  xor     edx, edx; hFile
0x1800d25d6  call    cs:__imp_LoadLibraryExW
0x1800d25dd  nop     dword ptr [rax+rax+00h]
0x1800d25e2  mov     rdi, rax
0x1800d25e5  mov     rax, rdi
0x1800d25e8  jmp     short loc_1800D25FB
0x1800d25ea  mov     rcx, rdi; hLibModule
0x1800d25ed  call    cs:__imp_FreeLibrary
0x1800d25f4  nop     dword ptr [rax+rax+00h]
0x1800d25f9  xor     eax, eax
0x1800d25fb  mov     rcx, [rbp+390h+var_30]
0x1800d2602  xor     rcx, rsp; StackCookie
0x1800d2605  call    __security_check_cookie
0x1800d260a  lea     r11, [rsp+490h+var_20]
0x1800d2612  mov     rbx, [r11+30h]
0x1800d2616  mov     rsi, [r11+38h]
0x1800d261a  mov     rsp, r11
0x1800d261d  pop     r15
0x1800d261f  pop     r14
0x1800d2621  pop     r12
0x1800d2623  pop     rdi
0x1800d2624  pop     rbp
0x1800d2625  retn
```
