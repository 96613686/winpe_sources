# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000521c`
- end: `0x1800059b3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004ea8`
- `0x18000521c`

## callees

- `0x180001f90`
- `0x18000366c`
- `0x180003e98`
- `0x180003eb0`
- `0x1800043d8`
- `0x1800047e0`
- `0x180004d58`
- `0x18000521c`
- `0x180005b98`
- `0x180012350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800056fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800056fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800054c9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800054c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005559`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005559`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800055b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800055b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005826`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800058bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005826`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800058bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000547f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000547f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000556d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005980`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000556d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005980`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005299`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800052ac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000532a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005393`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800053c1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005849`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005299`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800052ac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000532a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005393`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800053c1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005849`

## string_xrefs

- `0x1800052a2`: `ForceRemove`
- `0x180005389`: `NoRemove`
- `0x18000528f`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
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
  int v17; // eax
  LSTATUS v18; // eax
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
  int v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  unsigned int v32; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  HKEY v35; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v37[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
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
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v38, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
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
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v37, 0, a2);
        Token = v17;
        v9 = (HKEY)v37[0];
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
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
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
    v29 = _o_wcsncpy_s(String1, 260, a2, -1);
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
    Token = ATL::CRegParser::SkipAssignment(this, a2);
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
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v28);
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
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, String1);
                v9 = (HKEY)v37[0];
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
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v38, String1);
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
    v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v38, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v21 = ATL::CRegParser::SkipAssignment(this, a2);
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
0x18000521c  push    rbp
0x18000521e  push    rbx
0x18000521f  push    rsi
0x180005220  push    rdi
0x180005221  push    r12
0x180005223  push    r13
0x180005225  push    r14
0x180005227  push    r15
0x180005229  lea     rbp, [rsp-21D8h]
0x180005231  mov     eax, 22D8h
0x180005236  call    _alloca_probe
0x18000523b  sub     rsp, rax
0x18000523e  mov     rax, cs:__security_cookie
0x180005245  xor     rax, rsp
0x180005248  mov     [rbp+2210h+var_50], rax
0x18000524f  mov     r12d, r9d
0x180005252  mov     [rsp+2310h+var_22A8], r9d
0x180005257  mov     r15, r8
0x18000525a  mov     [rsp+2310h+var_22A0], r8
0x18000525f  mov     rsi, rdx
0x180005262  mov     r13, rcx
0x180005265  xor     eax, eax
0x180005267  mov     ebx, eax
0x180005269  mov     [rbp+2210h+var_2290], rax
0x18000526d  mov     [rbp+2210h+var_2288], rax
0x180005271  mov     [rbp+2210h+var_2280], rax
0x180005275  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000527a  mov     edi, eax
0x18000527c  test    eax, eax
0x18000527e  jns     short loc_180005285
0x180005280  jmp     loc_18000593C
0x180005285  cmp     word ptr [rsi], 7Dh ; '}'
0x180005289  jz      loc_18000592C
0x18000528f  lea     rdx, String2; "Delete"
0x180005296  mov     rcx, rsi; lpString1
0x180005299  call    cs:__imp_lstrcmpiW
0x18000529f  mov     r14d, eax
0x1800052a2  lea     rdx, aForceremove; "ForceRemove"
0x1800052a9  mov     rcx, rsi; lpString1
0x1800052ac  call    cs:__imp_lstrcmpiW
0x1800052b2  xor     edi, edi
0x1800052b4  test    eax, eax
0x1800052b6  jz      short loc_1800052C1
0x1800052b8  test    r14d, r14d
0x1800052bb  jnz     loc_180005383
0x1800052c1  mov     rdx, rsi; unsigned __int16 *
0x1800052c4  mov     rcx, r13; this
0x1800052c7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052cc  mov     edi, eax
0x1800052ce  test    eax, eax
0x1800052d0  js      loc_18000592C
0x1800052d6  xor     edi, edi
0x1800052d8  test    r12d, r12d
0x1800052db  jz      loc_180005383
0x1800052e1  mov     [rbp+2210h+var_2278], rdi
0x1800052e5  mov     [rbp+2210h+var_2270], rdi
0x1800052e9  mov     [rbp+2210h+var_2268], rdi
0x1800052ed  movzx   eax, word ptr [rsi]
0x1800052f0  test    ax, ax
0x1800052f3  jz      short loc_18000531A
0x1800052f5  mov     rcx, rsi; lpsz
0x1800052f8  cmp     ax, 5Ch ; '\'
0x1800052fc  jz      short loc_180005311
0x1800052fe  call    cs:__imp_CharNextW
0x180005304  mov     rcx, rax
0x180005307  movzx   eax, word ptr [rax]
0x18000530a  test    ax, ax
0x18000530d  jnz     short loc_1800052F8
0x18000530f  jmp     short loc_18000531A
0x180005311  test    rcx, rcx
0x180005314  jnz     loc_180005978
0x18000531a  mov     edx, edi
0x18000531c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180005323  mov     rdx, [rax+rdx*8]; lpString2
0x180005327  mov     rcx, rsi; lpString1
0x18000532a  call    cs:__imp_lstrcmpiW
0x180005330  test    eax, eax
0x180005332  jz      short loc_18000534B
0x180005334  inc     edi
0x180005336  cmp     edi, 0Ch
0x180005339  jl      short loc_18000531A
0x18000533b  mov     [rbp+2210h+var_2278], r15
0x18000533f  mov     rdx, rsi; unsigned __int16 *
0x180005342  lea     rcx, [rbp+2210h+var_2278]; this
0x180005346  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000534b  xor     edi, edi
0x18000534d  test    r14d, r14d
0x180005350  jnz     short loc_180005383
0x180005352  mov     rdx, rsi; unsigned __int16 *
0x180005355  mov     rcx, r13; this
0x180005358  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000535d  mov     edi, eax
0x18000535f  test    eax, eax
0x180005361  js      loc_18000592C
0x180005367  mov     rdx, rsi; unsigned __int16 *
0x18000536a  mov     rcx, r13; this
0x18000536d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005372  mov     edi, eax
0x180005374  xor     ecx, ecx
0x180005376  test    eax, eax
0x180005378  js      loc_18000592C
0x18000537e  jmp     loc_18000562A
0x180005383  mov     r12d, 1
0x180005389  lea     rdx, aNoremove; "NoRemove"
0x180005390  mov     rcx, rsi; lpString1
0x180005393  call    cs:__imp_lstrcmpiW
0x180005399  test    eax, eax
0x18000539b  jnz     short loc_1800053B7
0x18000539d  mov     r12d, edi
0x1800053a0  mov     rdx, rsi; unsigned __int16 *
0x1800053a3  mov     rcx, r13; this
0x1800053a6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800053ab  mov     edi, eax
0x1800053ad  test    eax, eax
0x1800053af  js      loc_18000592C
0x1800053b5  xor     edi, edi
0x1800053b7  lea     rdx, aVal; "Val"
0x1800053be  mov     rcx, rsi; lpString1
0x1800053c1  call    cs:__imp_lstrcmpiW
0x1800053c7  test    eax, eax
0x1800053c9  jnz     loc_1800054B8
0x1800053cf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800053d6  mov     rcx, r13; this
0x1800053d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800053de  mov     edi, eax
0x1800053e0  test    eax, eax
0x1800053e2  js      loc_18000592C
0x1800053e8  mov     rdx, rsi; unsigned __int16 *
0x1800053eb  mov     rcx, r13; this
0x1800053ee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800053f3  mov     edi, eax
0x1800053f5  test    eax, eax
0x1800053f7  js      loc_18000592C
0x1800053fd  cmp     word ptr [rsi], 3Dh ; '='
0x180005401  jnz     loc_180005978
0x180005407  xor     edi, edi
0x180005409  cmp     [rsp+2310h+var_22A8], edi
0x18000540d  jz      short loc_180005438
0x18000540f  mov     [rbp+2210h+var_2270], rdi
0x180005413  mov     [rbp+2210h+var_2268], rdi
0x180005417  mov     [rbp+2210h+var_2278], r15
0x18000541b  mov     r9, rsi; unsigned __int16 *
0x18000541e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005425  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005429  mov     rcx, r13; this
0x18000542c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005431  mov     edi, eax
0x180005433  jmp     loc_18000561B
0x180005438  cmp     [rbp+2210h+arg_20], edi
0x18000543e  jnz     short loc_18000549E
0x180005440  test    r12d, r12d
0x180005443  jz      short loc_18000549E
0x180005445  mov     [rsp+2310h+hKey], rdi
0x18000544a  lea     rax, [rsp+2310h+hKey]
0x18000544f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005454  mov     r9d, 20006h; samDesired
0x18000545a  xor     r8d, r8d; ulOptions
0x18000545d  xor     edx, edx; lpSubKey
0x18000545f  mov     rcx, r15; hKey
0x180005462  call    cs:__imp_RegOpenKeyExW
0x180005468  test    eax, eax
0x18000546a  jnz     loc_180005923
0x180005470  mov     r14, [rsp+2310h+hKey]
0x180005475  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000547c  mov     rcx, r14; hKey
0x18000547f  call    cs:__imp_RegDeleteValueW
0x180005485  test    eax, 0FFFFFFFDh
0x18000548a  jnz     loc_18000595F
0x180005490  test    r14, r14
0x180005493  jz      short loc_18000549E
0x180005495  mov     rcx, r14; hKey
0x180005498  call    cs:__imp_RegCloseKey
0x18000549e  mov     rdx, rsi; unsigned __int16 *
0x1800054a1  mov     rcx, r13; this
0x1800054a4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800054a9  mov     edi, eax
0x1800054ab  test    eax, eax
0x1800054ad  js      loc_18000592C
0x1800054b3  jmp     loc_1800057C5
0x1800054b8  movzx   eax, word ptr [rsi]
0x1800054bb  test    ax, ax
0x1800054be  jz      short loc_1800054E5
0x1800054c0  mov     rcx, rsi; lpsz
0x1800054c3  cmp     ax, 5Ch ; '\'
0x1800054c7  jz      short loc_1800054DC
0x1800054c9  call    cs:__imp_CharNextW
0x1800054cf  mov     rcx, rax
0x1800054d2  movzx   eax, word ptr [rax]
0x1800054d5  test    ax, ax
0x1800054d8  jnz     short loc_1800054C3
0x1800054da  jmp     short loc_1800054E5
0x1800054dc  test    rcx, rcx
0x1800054df  jnz     loc_180005978
0x1800054e5  cmp     [rsp+2310h+var_22A8], edi
0x1800054e9  jz      loc_18000567E
0x1800054ef  mov     [rsp+2310h+hKey], rdi
0x1800054f4  lea     rax, [rsp+2310h+hKey]
0x1800054f9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800054fe  mov     r14d, 2001Fh
0x180005504  mov     r9d, r14d; samDesired
0x180005507  xor     r8d, r8d; ulOptions
0x18000550a  mov     rdx, rsi; lpSubKey
0x18000550d  mov     rcx, r15; hKey
0x180005510  call    cs:__imp_RegOpenKeyExW
0x180005516  test    eax, eax
0x180005518  jnz     short loc_18000553B
0x18000551a  mov     eax, edi
0x18000551c  test    rbx, rbx
0x18000551f  jz      short loc_18000552A
0x180005521  mov     rcx, rbx; hKey
0x180005524  call    cs:__imp_RegCloseKey
0x18000552a  mov     rbx, [rsp+2310h+hKey]
0x18000552f  mov     [rbp+2210h+var_2290], rbx
0x180005533  test    eax, eax
0x180005535  jz      loc_1800055E6
0x18000553b  mov     [rsp+2310h+hKey], rdi
0x180005540  lea     rax, [rsp+2310h+hKey]
0x180005545  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000554a  mov     r9d, 20019h; samDesired
0x180005550  xor     r8d, r8d; ulOptions
0x180005553  mov     rdx, rsi; lpSubKey
0x180005556  mov     rcx, r15; hKey
0x180005559  call    cs:__imp_RegOpenKeyExW
0x18000555f  test    eax, eax
0x180005561  jnz     short loc_180005580
0x180005563  mov     eax, edi
0x180005565  test    rbx, rbx
0x180005568  jz      short loc_180005573
0x18000556a  mov     rcx, rbx; hKey
0x18000556d  call    cs:__imp_RegCloseKey
0x180005573  mov     rbx, [rsp+2310h+hKey]
0x180005578  mov     [rbp+2210h+var_2290], rbx
0x18000557c  test    eax, eax
0x18000557e  jz      short loc_1800055E6
0x180005580  mov     dword ptr [rsp+2310h+hKey], edi
0x180005584  mov     [rsp+2310h+var_2298], rdi
0x180005589  lea     rax, [rsp+2310h+hKey]
0x18000558e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180005593  lea     rax, [rsp+2310h+var_2298]
0x180005598  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000559d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800055a2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800055a7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800055ab  xor     r9d, r9d; lpClass
0x1800055ae  xor     r8d, r8d; Reserved
0x1800055b1  mov     rdx, rsi; lpSubKey
0x1800055b4  mov     rcx, r15; hKey
0x1800055b7  call    cs:__imp_RegCreateKeyExW
0x1800055bd  test    eax, eax
0x1800055bf  jnz     loc_180005923
0x1800055c5  mov     eax, edi
0x1800055c7  test    rbx, rbx
0x1800055ca  jz      short loc_1800055D5
0x1800055cc  mov     rcx, rbx; hKey
0x1800055cf  call    cs:__imp_RegCloseKey
0x1800055d5  mov     rbx, [rsp+2310h+var_2298]
0x1800055da  mov     [rbp+2210h+var_2290], rbx
0x1800055de  test    eax, eax
0x1800055e0  jnz     loc_180005923
0x1800055e6  mov     rdx, rsi; unsigned __int16 *
0x1800055e9  mov     rcx, r13; this
0x1800055ec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800055f1  mov     edi, eax
0x1800055f3  xor     ecx, ecx
0x1800055f5  test    eax, eax
0x1800055f7  js      loc_18000592C
0x1800055fd  cmp     word ptr [rsi], 3Dh ; '='
0x180005601  jnz     short loc_180005625
0x180005603  mov     r9, rsi; unsigned __int16 *
0x180005606  xor     r8d, r8d; unsigned __int16 *
0x180005609  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000560d  mov     rcx, r13; this
0x180005610  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005615  mov     edi, eax
0x180005617  mov     rbx, [rbp+2210h+var_2290]
0x18000561b  test    eax, eax
0x18000561d  js      loc_18000592C
0x180005623  xor     ecx, ecx
0x180005625  mov     r12d, [rsp+2310h+var_22A8]
0x18000562a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000562e  jnz     loc_1800057C5
0x180005634  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005638  inc     rax
0x18000563b  cmp     [rsi+rax*2], cx
0x18000563f  jnz     short loc_180005638
0x180005641  cmp     rax, 1
0x180005645  jnz     loc_1800057C5
0x18000564b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180005653  mov     r9d, r12d; int
0x180005656  mov     r8, rbx; HKEY
0x180005659  mov     rdx, rsi; unsigned __int16 *
0x18000565c  mov     rcx, r13; this
0x18000565f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005664  mov     edi, eax
0x180005666  test    eax, eax
0x180005668  js      loc_18000592C
0x18000566e  mov     rdx, rsi; unsigned __int16 *
0x180005671  mov     rcx, r13; this
0x180005674  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005679  jmp     loc_1800054A9
  ... truncated ...
```
