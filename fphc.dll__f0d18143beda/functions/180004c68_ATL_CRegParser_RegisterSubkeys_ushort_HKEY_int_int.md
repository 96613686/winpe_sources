# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004c68`
- end: `0x1800053ff`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800048f8`
- `0x180004c68`

## callees

- `0x1800030ac`
- `0x1800037dc`
- `0x180004048`
- `0x180004164`
- `0x180004304`
- `0x1800047a8`
- `0x180004c68`
- `0x18000541c`
- `0x180011340`
- `0x180011400`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005146`
- `msvcrt!wcsncpy_s` at `0x180005146`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004d4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f15`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004d4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f15`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005272`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005308`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005272`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ee4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000501b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000510f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ee4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000501b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000510f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053cc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004ecb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004ecb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004eae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004fa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800050f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004eae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004fa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800050f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005003`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005003`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004ce5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004cf8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004d76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004ddf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004e0d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005295`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004ce5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004cf8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004d76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004ddf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004e0d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005295`

## string_xrefs

- `0x180004cee`: `ForceRemove`
- `0x180004dd5`: `NoRemove`
- `0x180004cdb`: `Delete`

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
  errno_t v29; // eax
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
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, Destination);
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
0x180004c68  push    rbp
0x180004c6a  push    rbx
0x180004c6b  push    rsi
0x180004c6c  push    rdi
0x180004c6d  push    r12
0x180004c6f  push    r13
0x180004c71  push    r14
0x180004c73  push    r15
0x180004c75  lea     rbp, [rsp-21D8h]
0x180004c7d  mov     eax, 22D8h
0x180004c82  call    _alloca_probe
0x180004c87  sub     rsp, rax
0x180004c8a  mov     rax, cs:__security_cookie
0x180004c91  xor     rax, rsp
0x180004c94  mov     [rbp+2210h+var_50], rax
0x180004c9b  mov     r12d, r9d
0x180004c9e  mov     [rsp+2310h+var_22A8], r9d
0x180004ca3  mov     r15, r8
0x180004ca6  mov     [rsp+2310h+var_22A0], r8
0x180004cab  mov     rsi, rdx
0x180004cae  mov     r13, rcx
0x180004cb1  xor     eax, eax
0x180004cb3  mov     ebx, eax
0x180004cb5  mov     [rbp+2210h+var_2290], rax
0x180004cb9  mov     [rbp+2210h+var_2288], rax
0x180004cbd  mov     [rbp+2210h+var_2280], rax
0x180004cc1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004cc6  mov     edi, eax
0x180004cc8  test    eax, eax
0x180004cca  jns     short loc_180004CD1
0x180004ccc  jmp     loc_180005388
0x180004cd1  cmp     word ptr [rsi], 7Dh ; '}'
0x180004cd5  jz      loc_180005378
0x180004cdb  lea     rdx, String2; "Delete"
0x180004ce2  mov     rcx, rsi; lpString1
0x180004ce5  call    cs:__imp_lstrcmpiW
0x180004ceb  mov     r14d, eax
0x180004cee  lea     rdx, aForceremove; "ForceRemove"
0x180004cf5  mov     rcx, rsi; lpString1
0x180004cf8  call    cs:__imp_lstrcmpiW
0x180004cfe  xor     edi, edi
0x180004d00  test    eax, eax
0x180004d02  jz      short loc_180004D0D
0x180004d04  test    r14d, r14d
0x180004d07  jnz     loc_180004DCF
0x180004d0d  mov     rdx, rsi; unsigned __int16 *
0x180004d10  mov     rcx, r13; this
0x180004d13  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004d18  mov     edi, eax
0x180004d1a  test    eax, eax
0x180004d1c  js      loc_180005378
0x180004d22  xor     edi, edi
0x180004d24  test    r12d, r12d
0x180004d27  jz      loc_180004DCF
0x180004d2d  mov     [rbp+2210h+var_2278], rdi
0x180004d31  mov     [rbp+2210h+var_2270], rdi
0x180004d35  mov     [rbp+2210h+var_2268], rdi
0x180004d39  movzx   eax, word ptr [rsi]
0x180004d3c  test    ax, ax
0x180004d3f  jz      short loc_180004D66
0x180004d41  mov     rcx, rsi; lpsz
0x180004d44  cmp     ax, 5Ch ; '\'
0x180004d48  jz      short loc_180004D5D
0x180004d4a  call    cs:__imp_CharNextW
0x180004d50  mov     rcx, rax
0x180004d53  movzx   eax, word ptr [rax]
0x180004d56  test    ax, ax
0x180004d59  jnz     short loc_180004D44
0x180004d5b  jmp     short loc_180004D66
0x180004d5d  test    rcx, rcx
0x180004d60  jnz     loc_1800053C4
0x180004d66  mov     edx, edi
0x180004d68  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004d6f  mov     rdx, [rax+rdx*8]; lpString2
0x180004d73  mov     rcx, rsi; lpString1
0x180004d76  call    cs:__imp_lstrcmpiW
0x180004d7c  test    eax, eax
0x180004d7e  jz      short loc_180004D97
0x180004d80  inc     edi
0x180004d82  cmp     edi, 0Ch
0x180004d85  jl      short loc_180004D66
0x180004d87  mov     [rbp+2210h+var_2278], r15
0x180004d8b  mov     rdx, rsi; unsigned __int16 *
0x180004d8e  lea     rcx, [rbp+2210h+var_2278]; this
0x180004d92  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004d97  xor     edi, edi
0x180004d99  test    r14d, r14d
0x180004d9c  jnz     short loc_180004DCF
0x180004d9e  mov     rdx, rsi; unsigned __int16 *
0x180004da1  mov     rcx, r13; this
0x180004da4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004da9  mov     edi, eax
0x180004dab  test    eax, eax
0x180004dad  js      loc_180005378
0x180004db3  mov     rdx, rsi; unsigned __int16 *
0x180004db6  mov     rcx, r13; this
0x180004db9  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004dbe  mov     edi, eax
0x180004dc0  xor     ecx, ecx
0x180004dc2  test    eax, eax
0x180004dc4  js      loc_180005378
0x180004dca  jmp     loc_180005076
0x180004dcf  mov     r12d, 1
0x180004dd5  lea     rdx, aNoremove; "NoRemove"
0x180004ddc  mov     rcx, rsi; lpString1
0x180004ddf  call    cs:__imp_lstrcmpiW
0x180004de5  test    eax, eax
0x180004de7  jnz     short loc_180004E03
0x180004de9  mov     r12d, edi
0x180004dec  mov     rdx, rsi; unsigned __int16 *
0x180004def  mov     rcx, r13; this
0x180004df2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004df7  mov     edi, eax
0x180004df9  test    eax, eax
0x180004dfb  js      loc_180005378
0x180004e01  xor     edi, edi
0x180004e03  lea     rdx, aVal; "Val"
0x180004e0a  mov     rcx, rsi; lpString1
0x180004e0d  call    cs:__imp_lstrcmpiW
0x180004e13  test    eax, eax
0x180004e15  jnz     loc_180004F04
0x180004e1b  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004e22  mov     rcx, r13; this
0x180004e25  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004e2a  mov     edi, eax
0x180004e2c  test    eax, eax
0x180004e2e  js      loc_180005378
0x180004e34  mov     rdx, rsi; unsigned __int16 *
0x180004e37  mov     rcx, r13; this
0x180004e3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004e3f  mov     edi, eax
0x180004e41  test    eax, eax
0x180004e43  js      loc_180005378
0x180004e49  cmp     word ptr [rsi], 3Dh ; '='
0x180004e4d  jnz     loc_1800053C4
0x180004e53  xor     edi, edi
0x180004e55  cmp     [rsp+2310h+var_22A8], edi
0x180004e59  jz      short loc_180004E84
0x180004e5b  mov     [rbp+2210h+var_2270], rdi
0x180004e5f  mov     [rbp+2210h+var_2268], rdi
0x180004e63  mov     [rbp+2210h+var_2278], r15
0x180004e67  mov     r9, rsi; unsigned __int16 *
0x180004e6a  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004e71  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004e75  mov     rcx, r13; this
0x180004e78  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004e7d  mov     edi, eax
0x180004e7f  jmp     loc_180005067
0x180004e84  cmp     [rbp+2210h+arg_20], edi
0x180004e8a  jnz     short loc_180004EEA
0x180004e8c  test    r12d, r12d
0x180004e8f  jz      short loc_180004EEA
0x180004e91  mov     [rsp+2310h+hKey], rdi
0x180004e96  lea     rax, [rsp+2310h+hKey]
0x180004e9b  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004ea0  mov     r9d, 20006h; samDesired
0x180004ea6  xor     r8d, r8d; ulOptions
0x180004ea9  xor     edx, edx; lpSubKey
0x180004eab  mov     rcx, r15; hKey
0x180004eae  call    cs:__imp_RegOpenKeyExW
0x180004eb4  test    eax, eax
0x180004eb6  jnz     loc_18000536F
0x180004ebc  mov     r14, [rsp+2310h+hKey]
0x180004ec1  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180004ec8  mov     rcx, r14; hKey
0x180004ecb  call    cs:__imp_RegDeleteValueW
0x180004ed1  test    eax, 0FFFFFFFDh
0x180004ed6  jnz     loc_1800053AB
0x180004edc  test    r14, r14
0x180004edf  jz      short loc_180004EEA
0x180004ee1  mov     rcx, r14; hKey
0x180004ee4  call    cs:__imp_RegCloseKey
0x180004eea  mov     rdx, rsi; unsigned __int16 *
0x180004eed  mov     rcx, r13; this
0x180004ef0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004ef5  mov     edi, eax
0x180004ef7  test    eax, eax
0x180004ef9  js      loc_180005378
0x180004eff  jmp     loc_180005211
0x180004f04  movzx   eax, word ptr [rsi]
0x180004f07  test    ax, ax
0x180004f0a  jz      short loc_180004F31
0x180004f0c  mov     rcx, rsi; lpsz
0x180004f0f  cmp     ax, 5Ch ; '\'
0x180004f13  jz      short loc_180004F28
0x180004f15  call    cs:__imp_CharNextW
0x180004f1b  mov     rcx, rax
0x180004f1e  movzx   eax, word ptr [rax]
0x180004f21  test    ax, ax
0x180004f24  jnz     short loc_180004F0F
0x180004f26  jmp     short loc_180004F31
0x180004f28  test    rcx, rcx
0x180004f2b  jnz     loc_1800053C4
0x180004f31  cmp     [rsp+2310h+var_22A8], edi
0x180004f35  jz      loc_1800050CA
0x180004f3b  mov     [rsp+2310h+hKey], rdi
0x180004f40  lea     rax, [rsp+2310h+hKey]
0x180004f45  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004f4a  mov     r14d, 2001Fh
0x180004f50  mov     r9d, r14d; samDesired
0x180004f53  xor     r8d, r8d; ulOptions
0x180004f56  mov     rdx, rsi; lpSubKey
0x180004f59  mov     rcx, r15; hKey
0x180004f5c  call    cs:__imp_RegOpenKeyExW
0x180004f62  test    eax, eax
0x180004f64  jnz     short loc_180004F87
0x180004f66  mov     eax, edi
0x180004f68  test    rbx, rbx
0x180004f6b  jz      short loc_180004F76
0x180004f6d  mov     rcx, rbx; hKey
0x180004f70  call    cs:__imp_RegCloseKey
0x180004f76  mov     rbx, [rsp+2310h+hKey]
0x180004f7b  mov     [rbp+2210h+var_2290], rbx
0x180004f7f  test    eax, eax
0x180004f81  jz      loc_180005032
0x180004f87  mov     [rsp+2310h+hKey], rdi
0x180004f8c  lea     rax, [rsp+2310h+hKey]
0x180004f91  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004f96  mov     r9d, 20019h; samDesired
0x180004f9c  xor     r8d, r8d; ulOptions
0x180004f9f  mov     rdx, rsi; lpSubKey
0x180004fa2  mov     rcx, r15; hKey
0x180004fa5  call    cs:__imp_RegOpenKeyExW
0x180004fab  test    eax, eax
0x180004fad  jnz     short loc_180004FCC
0x180004faf  mov     eax, edi
0x180004fb1  test    rbx, rbx
0x180004fb4  jz      short loc_180004FBF
0x180004fb6  mov     rcx, rbx; hKey
0x180004fb9  call    cs:__imp_RegCloseKey
0x180004fbf  mov     rbx, [rsp+2310h+hKey]
0x180004fc4  mov     [rbp+2210h+var_2290], rbx
0x180004fc8  test    eax, eax
0x180004fca  jz      short loc_180005032
0x180004fcc  mov     dword ptr [rsp+2310h+hKey], edi
0x180004fd0  mov     [rsp+2310h+var_2298], rdi
0x180004fd5  lea     rax, [rsp+2310h+hKey]
0x180004fda  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004fdf  lea     rax, [rsp+2310h+var_2298]
0x180004fe4  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180004fe9  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004fee  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180004ff3  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180004ff7  xor     r9d, r9d; lpClass
0x180004ffa  xor     r8d, r8d; Reserved
0x180004ffd  mov     rdx, rsi; lpSubKey
0x180005000  mov     rcx, r15; hKey
0x180005003  call    cs:__imp_RegCreateKeyExW
0x180005009  test    eax, eax
0x18000500b  jnz     loc_18000536F
0x180005011  mov     eax, edi
0x180005013  test    rbx, rbx
0x180005016  jz      short loc_180005021
0x180005018  mov     rcx, rbx; hKey
0x18000501b  call    cs:__imp_RegCloseKey
0x180005021  mov     rbx, [rsp+2310h+var_2298]
0x180005026  mov     [rbp+2210h+var_2290], rbx
0x18000502a  test    eax, eax
0x18000502c  jnz     loc_18000536F
0x180005032  mov     rdx, rsi; unsigned __int16 *
0x180005035  mov     rcx, r13; this
0x180005038  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000503d  mov     edi, eax
0x18000503f  xor     ecx, ecx
0x180005041  test    eax, eax
0x180005043  js      loc_180005378
0x180005049  cmp     word ptr [rsi], 3Dh ; '='
0x18000504d  jnz     short loc_180005071
0x18000504f  mov     r9, rsi; unsigned __int16 *
0x180005052  xor     r8d, r8d; unsigned __int16 *
0x180005055  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180005059  mov     rcx, r13; this
0x18000505c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005061  mov     edi, eax
0x180005063  mov     rbx, [rbp+2210h+var_2290]
0x180005067  test    eax, eax
0x180005069  js      loc_180005378
0x18000506f  xor     ecx, ecx
0x180005071  mov     r12d, [rsp+2310h+var_22A8]
0x180005076  cmp     word ptr [rsi], 7Bh ; '{'
0x18000507a  jnz     loc_180005211
0x180005080  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005084  inc     rax
0x180005087  cmp     [rsi+rax*2], cx
0x18000508b  jnz     short loc_180005084
0x18000508d  cmp     rax, 1
0x180005091  jnz     loc_180005211
0x180005097  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x18000509f  mov     r9d, r12d; int
0x1800050a2  mov     r8, rbx; HKEY
0x1800050a5  mov     rdx, rsi; unsigned __int16 *
0x1800050a8  mov     rcx, r13; this
0x1800050ab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800050b0  mov     edi, eax
0x1800050b2  test    eax, eax
0x1800050b4  js      loc_180005378
0x1800050ba  mov     rdx, rsi; unsigned __int16 *
0x1800050bd  mov     rcx, r13; this
0x1800050c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050c5  jmp     loc_180004EF5
  ... truncated ...
```
