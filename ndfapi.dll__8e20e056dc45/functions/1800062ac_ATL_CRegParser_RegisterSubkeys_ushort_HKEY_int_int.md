# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800062ac`
- end: `0x180006a43`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180005f38`
- `0x1800062ac`

## callees

- `0x1800046ec`
- `0x180004e1c`
- `0x180005688`
- `0x1800057a4`
- `0x180005944`
- `0x180005de8`
- `0x1800062ac`
- `0x180006a5c`
- `0x18001f690`
- `0x18001f750`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000678a`
- `msvcrt!wcsncpy_s` at `0x18000678a`
- `ADVAPI32!RegDeleteValueW` at `0x18000650f`
- `ADVAPI32!RegDeleteValueW` at `0x18000650f`
- `ADVAPI32!RegCreateKeyExW` at `0x180006647`
- `ADVAPI32!RegCreateKeyExW` at `0x180006647`
- `ADVAPI32!RegOpenKeyExW` at `0x1800064f2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065a0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065e9`
- `ADVAPI32!RegOpenKeyExW` at `0x180006738`
- `ADVAPI32!RegOpenKeyExW` at `0x1800064f2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065a0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065e9`
- `ADVAPI32!RegOpenKeyExW` at `0x180006738`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800068b6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000694c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800068b6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000694c`
- `ADVAPI32!RegCloseKey` at `0x180006528`
- `ADVAPI32!RegCloseKey` at `0x1800065b4`
- `ADVAPI32!RegCloseKey` at `0x1800065fd`
- `ADVAPI32!RegCloseKey` at `0x18000665f`
- `ADVAPI32!RegCloseKey` at `0x180006753`
- `ADVAPI32!RegCloseKey` at `0x18000696a`
- `ADVAPI32!RegCloseKey` at `0x1800069c4`
- `ADVAPI32!RegCloseKey` at `0x180006a00`
- `ADVAPI32!RegCloseKey` at `0x180006a10`
- `ADVAPI32!RegCloseKey` at `0x180006528`
- `ADVAPI32!RegCloseKey` at `0x1800065b4`
- `ADVAPI32!RegCloseKey` at `0x1800065fd`
- `ADVAPI32!RegCloseKey` at `0x18000665f`
- `ADVAPI32!RegCloseKey` at `0x180006753`
- `ADVAPI32!RegCloseKey` at `0x18000696a`
- `ADVAPI32!RegCloseKey` at `0x1800069c4`
- `ADVAPI32!RegCloseKey` at `0x180006a00`
- `ADVAPI32!RegCloseKey` at `0x180006a10`
- `KERNEL32!lstrcmpiW` at `0x180006329`
- `KERNEL32!lstrcmpiW` at `0x18000633c`
- `KERNEL32!lstrcmpiW` at `0x1800063ba`
- `KERNEL32!lstrcmpiW` at `0x180006423`
- `KERNEL32!lstrcmpiW` at `0x180006451`
- `KERNEL32!lstrcmpiW` at `0x1800068d9`
- `KERNEL32!lstrcmpiW` at `0x180006329`
- `KERNEL32!lstrcmpiW` at `0x18000633c`
- `KERNEL32!lstrcmpiW` at `0x1800063ba`
- `KERNEL32!lstrcmpiW` at `0x180006423`
- `KERNEL32!lstrcmpiW` at `0x180006451`
- `KERNEL32!lstrcmpiW` at `0x1800068d9`
- `USER32!CharNextW` at `0x18000638e`
- `USER32!CharNextW` at `0x180006559`
- `USER32!CharNextW` at `0x18000638e`
- `USER32!CharNextW` at `0x180006559`

## string_xrefs

- `0x180006332`: `ForceRemove`
- `0x180006419`: `NoRemove`
- `0x18000631f`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
{
  int v5; // r12d
  HKEY v6; // r15
  HKEY v9; // rbx
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // r12d
  HRESULT v17; // eax
  DWORD v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // r14d
  int v28; // r15d
  errno_t v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  unsigned int v32; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  HKEY v35; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v37[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v34 = a4;
  v6 = a3;
  v35 = a3;
  v9 = 0;
  memset(v37, 0, sizeof(v37));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    goto LABEL_111;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      v13 = 0;
      if ( v5 )
      {
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v14 = *a2;
        if ( !*a2 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_117;
          }
          v15 = CharNextW(v15);
          v14 = *v15;
        }
        while ( *v15 );
LABEL_13:
        while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
        {
          if ( ++v13 >= 12 )
          {
            v38 = v6;
            ATL::CRegKey::RecurseDeleteKey(&v38, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          goto LABEL_61;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
    }
    if ( !lstrcmpiW(a2, L"Val") )
      break;
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextW(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_43;
      }
      if ( v23 )
        goto LABEL_117;
    }
LABEL_43:
    if ( v34 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v24 = 0;
      if ( v9 )
        v24 = RegCloseKey(v9);
      v9 = hKey;
      v37[0] = hKey;
      if ( v24 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v25 = 0;
        if ( v9 )
          v25 = RegCloseKey(v9);
        v9 = hKey;
        v37[0] = hKey;
        if ( v25 )
        {
LABEL_127:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_109;
          v18 = 0;
          if ( v9 )
            v18 = RegCloseKey(v9);
          v9 = phkResult;
          v37[0] = phkResult;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, v37, 0, a2);
        Token = v17;
        v9 = v37[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v34;
LABEL_61:
      if ( *a2 != 123 )
        goto LABEL_93;
      v26 = -1;
      do
        ++v26;
      while ( a2[v26] );
      if ( v26 != 1 )
        goto LABEL_93;
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v21 = ATL::CRegParser::NextToken(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_111;
      goto LABEL_93;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = phkResult;
        v37[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v29 )
    {
      if ( v29 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v29 == 22 || v29 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v29 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v6 = v35;
        goto LABEL_93;
      }
      v32 = v27;
LABEL_110:
      Token = ATL::AtlHresultFromWin32(v32);
      goto LABEL_111;
    }
    v31 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey(v37, Destination);
                v9 = v37[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v31) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v18 = RegCloseKey(v9);
      v9 = 0;
      v37[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v32 = v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v31 )
      goto LABEL_92;
    v39 = 0;
    v40 = 0;
    v6 = v35;
    v38 = v35;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v38, Destination);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v34;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_111;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_111;
  if ( *a2 != 61 )
  {
LABEL_117:
    if ( v9 )
      RegCloseKey(v9);
    return 2147614729LL;
  }
  if ( v34 )
  {
    v39 = 0;
    v40 = 0;
    v38 = v6;
    v17 = ATL::CRegParser::AddValue(this, &v38, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
    goto LABEL_35;
  }
  hKey = 0;
  v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v19 = hKey;
  v20 = RegDeleteValueW(hKey, ValueName);
  if ( (v20 & 0xFFFFFFFD) == 0 )
  {
    if ( v19 )
      RegCloseKey(v19);
    goto LABEL_34;
  }
  Token = ATL::AtlHresultFromWin32(v20);
  if ( v19 )
    RegCloseKey(v19);
LABEL_111:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x1800062ac  push    rbp
0x1800062ae  push    rbx
0x1800062af  push    rsi
0x1800062b0  push    rdi
0x1800062b1  push    r12
0x1800062b3  push    r13
0x1800062b5  push    r14
0x1800062b7  push    r15
0x1800062b9  lea     rbp, [rsp-21D8h]
0x1800062c1  mov     eax, 22D8h
0x1800062c6  call    _alloca_probe
0x1800062cb  sub     rsp, rax
0x1800062ce  mov     rax, cs:__security_cookie
0x1800062d5  xor     rax, rsp
0x1800062d8  mov     [rbp+2210h+var_50], rax
0x1800062df  mov     r12d, r9d
0x1800062e2  mov     [rsp+2310h+var_22A8], r9d
0x1800062e7  mov     r15, r8
0x1800062ea  mov     [rsp+2310h+var_22A0], r8
0x1800062ef  mov     rsi, rdx
0x1800062f2  mov     r13, rcx
0x1800062f5  xor     eax, eax
0x1800062f7  mov     ebx, eax
0x1800062f9  mov     [rbp+2210h+var_2290], rax
0x1800062fd  mov     [rbp+2210h+var_2288], rax
0x180006301  mov     [rbp+2210h+var_2280], rax
0x180006305  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000630a  mov     edi, eax
0x18000630c  test    eax, eax
0x18000630e  jns     short loc_180006315
0x180006310  jmp     loc_1800069CC
0x180006315  cmp     word ptr [rsi], 7Dh ; '}'
0x180006319  jz      loc_1800069BC
0x18000631f  lea     rdx, String2; "Delete"
0x180006326  mov     rcx, rsi; lpString1
0x180006329  call    cs:__imp_lstrcmpiW
0x18000632f  mov     r14d, eax
0x180006332  lea     rdx, aForceremove; "ForceRemove"
0x180006339  mov     rcx, rsi; lpString1
0x18000633c  call    cs:__imp_lstrcmpiW
0x180006342  xor     edi, edi
0x180006344  test    eax, eax
0x180006346  jz      short loc_180006351
0x180006348  test    r14d, r14d
0x18000634b  jnz     loc_180006413
0x180006351  mov     rdx, rsi; unsigned __int16 *
0x180006354  mov     rcx, r13; this
0x180006357  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000635c  mov     edi, eax
0x18000635e  test    eax, eax
0x180006360  js      loc_1800069BC
0x180006366  xor     edi, edi
0x180006368  test    r12d, r12d
0x18000636b  jz      loc_180006413
0x180006371  mov     [rbp+2210h+var_2278], rdi
0x180006375  mov     [rbp+2210h+var_2270], rdi
0x180006379  mov     [rbp+2210h+var_2268], rdi
0x18000637d  movzx   eax, word ptr [rsi]
0x180006380  test    ax, ax
0x180006383  jz      short loc_1800063AA
0x180006385  mov     rcx, rsi; lpsz
0x180006388  cmp     ax, 5Ch ; '\'
0x18000638c  jz      short loc_1800063A1
0x18000638e  call    cs:__imp_CharNextW
0x180006394  mov     rcx, rax
0x180006397  movzx   eax, word ptr [rax]
0x18000639a  test    ax, ax
0x18000639d  jnz     short loc_180006388
0x18000639f  jmp     short loc_1800063AA
0x1800063a1  test    rcx, rcx
0x1800063a4  jnz     loc_180006A08
0x1800063aa  mov     edx, edi
0x1800063ac  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800063b3  mov     rdx, [rax+rdx*8]; lpString2
0x1800063b7  mov     rcx, rsi; lpString1
0x1800063ba  call    cs:__imp_lstrcmpiW
0x1800063c0  test    eax, eax
0x1800063c2  jz      short loc_1800063DB
0x1800063c4  inc     edi
0x1800063c6  cmp     edi, 0Ch
0x1800063c9  jl      short loc_1800063AA
0x1800063cb  mov     [rbp+2210h+var_2278], r15
0x1800063cf  mov     rdx, rsi; unsigned __int16 *
0x1800063d2  lea     rcx, [rbp+2210h+var_2278]; this
0x1800063d6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800063db  xor     edi, edi
0x1800063dd  test    r14d, r14d
0x1800063e0  jnz     short loc_180006413
0x1800063e2  mov     rdx, rsi; unsigned __int16 *
0x1800063e5  mov     rcx, r13; this
0x1800063e8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800063ed  mov     edi, eax
0x1800063ef  test    eax, eax
0x1800063f1  js      loc_1800069BC
0x1800063f7  mov     rdx, rsi; unsigned __int16 *
0x1800063fa  mov     rcx, r13; this
0x1800063fd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006402  mov     edi, eax
0x180006404  xor     ecx, ecx
0x180006406  test    eax, eax
0x180006408  js      loc_1800069BC
0x18000640e  jmp     loc_1800066BA
0x180006413  mov     r12d, 1
0x180006419  lea     rdx, aNoremove; "NoRemove"
0x180006420  mov     rcx, rsi; lpString1
0x180006423  call    cs:__imp_lstrcmpiW
0x180006429  test    eax, eax
0x18000642b  jnz     short loc_180006447
0x18000642d  mov     r12d, edi
0x180006430  mov     rdx, rsi; unsigned __int16 *
0x180006433  mov     rcx, r13; this
0x180006436  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000643b  mov     edi, eax
0x18000643d  test    eax, eax
0x18000643f  js      loc_1800069BC
0x180006445  xor     edi, edi
0x180006447  lea     rdx, aVal; "Val"
0x18000644e  mov     rcx, rsi; lpString1
0x180006451  call    cs:__imp_lstrcmpiW
0x180006457  test    eax, eax
0x180006459  jnz     loc_180006548
0x18000645f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006466  mov     rcx, r13; this
0x180006469  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000646e  mov     edi, eax
0x180006470  test    eax, eax
0x180006472  js      loc_1800069BC
0x180006478  mov     rdx, rsi; unsigned __int16 *
0x18000647b  mov     rcx, r13; this
0x18000647e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006483  mov     edi, eax
0x180006485  test    eax, eax
0x180006487  js      loc_1800069BC
0x18000648d  cmp     word ptr [rsi], 3Dh ; '='
0x180006491  jnz     loc_180006A08
0x180006497  xor     edi, edi
0x180006499  cmp     [rsp+2310h+var_22A8], edi
0x18000649d  jz      short loc_1800064C8
0x18000649f  mov     [rbp+2210h+var_2270], rdi
0x1800064a3  mov     [rbp+2210h+var_2268], rdi
0x1800064a7  mov     [rbp+2210h+var_2278], r15
0x1800064ab  mov     r9, rsi; unsigned __int16 *
0x1800064ae  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800064b5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1800064b9  mov     rcx, r13; this
0x1800064bc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800064c1  mov     edi, eax
0x1800064c3  jmp     loc_1800066AB
0x1800064c8  cmp     [rbp+2210h+arg_20], edi
0x1800064ce  jnz     short loc_18000652E
0x1800064d0  test    r12d, r12d
0x1800064d3  jz      short loc_18000652E
0x1800064d5  mov     [rsp+2310h+hKey], rdi
0x1800064da  lea     rax, [rsp+2310h+hKey]
0x1800064df  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800064e4  mov     r9d, 20006h; samDesired
0x1800064ea  xor     r8d, r8d; ulOptions
0x1800064ed  xor     edx, edx; lpSubKey
0x1800064ef  mov     rcx, r15; hKey
0x1800064f2  call    cs:__imp_RegOpenKeyExW
0x1800064f8  test    eax, eax
0x1800064fa  jnz     loc_1800069B3
0x180006500  mov     r14, [rsp+2310h+hKey]
0x180006505  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000650c  mov     rcx, r14; hKey
0x18000650f  call    cs:__imp_RegDeleteValueW
0x180006515  test    eax, 0FFFFFFFDh
0x18000651a  jnz     loc_1800069EF
0x180006520  test    r14, r14
0x180006523  jz      short loc_18000652E
0x180006525  mov     rcx, r14; hKey
0x180006528  call    cs:__imp_RegCloseKey
0x18000652e  mov     rdx, rsi; unsigned __int16 *
0x180006531  mov     rcx, r13; this
0x180006534  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006539  mov     edi, eax
0x18000653b  test    eax, eax
0x18000653d  js      loc_1800069BC
0x180006543  jmp     loc_180006855
0x180006548  movzx   eax, word ptr [rsi]
0x18000654b  test    ax, ax
0x18000654e  jz      short loc_180006575
0x180006550  mov     rcx, rsi; lpsz
0x180006553  cmp     ax, 5Ch ; '\'
0x180006557  jz      short loc_18000656C
0x180006559  call    cs:__imp_CharNextW
0x18000655f  mov     rcx, rax
0x180006562  movzx   eax, word ptr [rax]
0x180006565  test    ax, ax
0x180006568  jnz     short loc_180006553
0x18000656a  jmp     short loc_180006575
0x18000656c  test    rcx, rcx
0x18000656f  jnz     loc_180006A08
0x180006575  cmp     [rsp+2310h+var_22A8], edi
0x180006579  jz      loc_18000670E
0x18000657f  mov     [rsp+2310h+hKey], rdi
0x180006584  lea     rax, [rsp+2310h+hKey]
0x180006589  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000658e  mov     r14d, 2001Fh
0x180006594  mov     r9d, r14d; samDesired
0x180006597  xor     r8d, r8d; ulOptions
0x18000659a  mov     rdx, rsi; lpSubKey
0x18000659d  mov     rcx, r15; hKey
0x1800065a0  call    cs:__imp_RegOpenKeyExW
0x1800065a6  test    eax, eax
0x1800065a8  jnz     short loc_1800065CB
0x1800065aa  mov     eax, edi
0x1800065ac  test    rbx, rbx
0x1800065af  jz      short loc_1800065BA
0x1800065b1  mov     rcx, rbx; hKey
0x1800065b4  call    cs:__imp_RegCloseKey
0x1800065ba  mov     rbx, [rsp+2310h+hKey]
0x1800065bf  mov     [rbp+2210h+var_2290], rbx
0x1800065c3  test    eax, eax
0x1800065c5  jz      loc_180006676
0x1800065cb  mov     [rsp+2310h+hKey], rdi
0x1800065d0  lea     rax, [rsp+2310h+hKey]
0x1800065d5  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800065da  mov     r9d, 20019h; samDesired
0x1800065e0  xor     r8d, r8d; ulOptions
0x1800065e3  mov     rdx, rsi; lpSubKey
0x1800065e6  mov     rcx, r15; hKey
0x1800065e9  call    cs:__imp_RegOpenKeyExW
0x1800065ef  test    eax, eax
0x1800065f1  jnz     short loc_180006610
0x1800065f3  mov     eax, edi
0x1800065f5  test    rbx, rbx
0x1800065f8  jz      short loc_180006603
0x1800065fa  mov     rcx, rbx; hKey
0x1800065fd  call    cs:__imp_RegCloseKey
0x180006603  mov     rbx, [rsp+2310h+hKey]
0x180006608  mov     [rbp+2210h+var_2290], rbx
0x18000660c  test    eax, eax
0x18000660e  jz      short loc_180006676
0x180006610  mov     dword ptr [rsp+2310h+hKey], edi
0x180006614  mov     [rsp+2310h+var_2298], rdi
0x180006619  lea     rax, [rsp+2310h+hKey]
0x18000661e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180006623  lea     rax, [rsp+2310h+var_2298]
0x180006628  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000662d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180006632  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180006637  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000663b  xor     r9d, r9d; lpClass
0x18000663e  xor     r8d, r8d; Reserved
0x180006641  mov     rdx, rsi; lpSubKey
0x180006644  mov     rcx, r15; hKey
0x180006647  call    cs:__imp_RegCreateKeyExW
0x18000664d  test    eax, eax
0x18000664f  jnz     loc_1800069B3
0x180006655  mov     eax, edi
0x180006657  test    rbx, rbx
0x18000665a  jz      short loc_180006665
0x18000665c  mov     rcx, rbx; hKey
0x18000665f  call    cs:__imp_RegCloseKey
0x180006665  mov     rbx, [rsp+2310h+var_2298]
0x18000666a  mov     [rbp+2210h+var_2290], rbx
0x18000666e  test    eax, eax
0x180006670  jnz     loc_1800069B3
0x180006676  mov     rdx, rsi; unsigned __int16 *
0x180006679  mov     rcx, r13; this
0x18000667c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006681  mov     edi, eax
0x180006683  xor     ecx, ecx
0x180006685  test    eax, eax
0x180006687  js      loc_1800069BC
0x18000668d  cmp     word ptr [rsi], 3Dh ; '='
0x180006691  jnz     short loc_1800066B5
0x180006693  mov     r9, rsi; unsigned __int16 *
0x180006696  xor     r8d, r8d; unsigned __int16 *
0x180006699  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000669d  mov     rcx, r13; this
0x1800066a0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800066a5  mov     edi, eax
0x1800066a7  mov     rbx, [rbp+2210h+var_2290]
0x1800066ab  test    eax, eax
0x1800066ad  js      loc_1800069BC
0x1800066b3  xor     ecx, ecx
0x1800066b5  mov     r12d, [rsp+2310h+var_22A8]
0x1800066ba  cmp     word ptr [rsi], 7Bh ; '{'
0x1800066be  jnz     loc_180006855
0x1800066c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800066c8  inc     rax
0x1800066cb  cmp     [rsi+rax*2], cx
0x1800066cf  jnz     short loc_1800066C8
0x1800066d1  cmp     rax, 1
0x1800066d5  jnz     loc_180006855
0x1800066db  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x1800066e3  mov     r9d, r12d; int
0x1800066e6  mov     r8, rbx; HKEY
0x1800066e9  mov     rdx, rsi; unsigned __int16 *
0x1800066ec  mov     rcx, r13; this
0x1800066ef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800066f4  mov     edi, eax
0x1800066f6  test    eax, eax
0x1800066f8  js      loc_1800069BC
0x1800066fe  mov     rdx, rsi; unsigned __int16 *
0x180006701  mov     rcx, r13; this
0x180006704  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006709  jmp     loc_180006539
  ... truncated ...
```
