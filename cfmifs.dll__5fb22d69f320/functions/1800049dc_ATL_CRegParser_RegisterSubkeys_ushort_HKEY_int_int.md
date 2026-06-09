# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800049dc`
- end: `0x180005179`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004688`
- `0x1800049dc`

## callees

- `0x180002d44`
- `0x1800034a8`
- `0x18000397c`
- `0x180003d68`
- `0x180004060`
- `0x180004538`
- `0x1800049dc`
- `0x1800052b4`
- `0x180006030`
- `0x1800060c0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004eb3`
- `msvcrt!wcsncpy_s` at `0x180004eb3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004d74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004d74`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004c3c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004c3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ccd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004d16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ccd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004d16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005073`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005073`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000512d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000513d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000512d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000513d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004abf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c86`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004abf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004c86`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a5a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004aeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005001`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a5a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004a6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004aeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005001`

## string_xrefs

- `0x180004a60`: `ForceRemove`
- `0x180004b44`: `NoRemove`
- `0x180004a50`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v5; // rbx
  int v6; // r12d
  HKEY v7; // r15
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
  int v32; // r14d
  LSTATUS v33; // eax
  unsigned int v34; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v36 = a4;
  v5 = 0;
  v37 = a3;
  memset(v39, 0, sizeof(v39));
  v6 = a4;
  v7 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        if ( !v14 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_118;
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
            v40 = v7;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_93;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_93;
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_35;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_112;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 != 61 )
        break;
      if ( v36 )
      {
        v41 = 0;
        v42 = 0;
        v40 = v7;
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_112;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_110;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
          goto LABEL_112;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
    }
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
        break;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_128;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v39[0] = hKey;
      if ( v24 )
      {
LABEL_128:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_129;
        v25 = 0;
        if ( v5 )
          v25 = RegCloseKey(v5);
        v5 = hKey;
        v39[0] = hKey;
        if ( v25 )
        {
LABEL_129:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_110;
          v18 = 0;
          if ( v5 )
            v18 = RegCloseKey(v5);
          v5 = phkResult;
          v39[0] = phkResult;
          if ( v18 )
          {
LABEL_110:
            v34 = v18;
            goto LABEL_111;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v39, 0, a2);
        v5 = (HKEY)v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v36;
      goto LABEL_61;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v7, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v39[0] = phkResult;
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
      goto LABEL_112;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_112;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_112;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v7 = v37;
        goto LABEL_93;
      }
      v34 = v27;
LABEL_111:
      Token = ATL::AtlHresultFromWin32(v34);
LABEL_112:
      if ( v5 )
        RegCloseKey(v5);
      return (unsigned int)Token;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v31 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, Destination);
                v5 = (HKEY)v39[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v32 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v33 = RegCloseKey(v5);
      v39[0] = 0;
      v5 = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v36;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x1800049dc  push    rbp
0x1800049de  push    rbx
0x1800049df  push    rsi
0x1800049e0  push    rdi
0x1800049e1  push    r12
0x1800049e3  push    r13
0x1800049e5  push    r14
0x1800049e7  push    r15
0x1800049e9  lea     rbp, [rsp-21D8h]
0x1800049f1  mov     eax, 22D8h
0x1800049f6  call    _alloca_probe
0x1800049fb  sub     rsp, rax
0x1800049fe  mov     rax, cs:__security_cookie
0x180004a05  xor     rax, rsp
0x180004a08  mov     [rbp+2210h+var_50], rax
0x180004a0f  xor     r14d, r14d
0x180004a12  mov     [rsp+2310h+var_22A8], r9d
0x180004a17  mov     ebx, r14d
0x180004a1a  mov     [rsp+2310h+var_22A0], r8
0x180004a1f  mov     [rbp+2210h+var_2290], rbx
0x180004a23  mov     r12d, r9d
0x180004a26  mov     r15, r8
0x180004a29  mov     [rbp+2210h+var_2288], r14
0x180004a2d  mov     rsi, rdx
0x180004a30  mov     [rbp+2210h+var_2280], r14
0x180004a34  mov     r13, rcx
0x180004a37  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a3c  mov     edi, eax
0x180004a3e  test    eax, eax
0x180004a40  js      loc_1800050F9
0x180004a46  cmp     word ptr [rsi], 7Dh ; '}'
0x180004a4a  jz      loc_1800050F7
0x180004a50  lea     rdx, String2; "Delete"
0x180004a57  mov     rcx, rsi; lpString1
0x180004a5a  call    cs:__imp_lstrcmpiW
0x180004a60  lea     rdx, aForceremove; "ForceRemove"
0x180004a67  mov     rcx, rsi; lpString1
0x180004a6a  mov     r14d, eax
0x180004a6d  call    cs:__imp_lstrcmpiW
0x180004a73  xor     edi, edi
0x180004a75  test    eax, eax
0x180004a77  jz      short loc_180004A82
0x180004a79  test    r14d, r14d
0x180004a7c  jnz     loc_180004B44
0x180004a82  mov     rdx, rsi; unsigned __int16 *
0x180004a85  mov     rcx, r13; this
0x180004a88  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a8d  mov     edi, eax
0x180004a8f  test    eax, eax
0x180004a91  js      loc_1800050E9
0x180004a97  xor     edi, edi
0x180004a99  test    r12d, r12d
0x180004a9c  jz      loc_180004B44
0x180004aa2  movzx   eax, word ptr [rsi]
0x180004aa5  mov     [rbp+2210h+var_2278], rdi
0x180004aa9  mov     [rbp+2210h+var_2270], rdi
0x180004aad  mov     [rbp+2210h+var_2268], rdi
0x180004ab1  test    ax, ax
0x180004ab4  jz      short loc_180004ADB
0x180004ab6  mov     rcx, rsi; lpsz
0x180004ab9  cmp     ax, 5Ch ; '\'
0x180004abd  jz      short loc_180004AD2
0x180004abf  call    cs:__imp_CharNextW
0x180004ac5  mov     rcx, rax
0x180004ac8  movzx   eax, word ptr [rax]
0x180004acb  test    ax, ax
0x180004ace  jnz     short loc_180004AB9
0x180004ad0  jmp     short loc_180004ADB
0x180004ad2  test    rcx, rcx
0x180004ad5  jnz     loc_180005135
0x180004adb  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004ae2  mov     edx, edi
0x180004ae4  mov     rcx, rsi; lpString1
0x180004ae7  mov     rdx, [rax+rdx*8]; lpString2
0x180004aeb  call    cs:__imp_lstrcmpiW
0x180004af1  test    eax, eax
0x180004af3  jz      short loc_180004B0C
0x180004af5  inc     edi
0x180004af7  cmp     edi, 0Ch
0x180004afa  jl      short loc_180004ADB
0x180004afc  mov     rdx, rsi; unsigned __int16 *
0x180004aff  mov     [rbp+2210h+var_2278], r15
0x180004b03  lea     rcx, [rbp+2210h+var_2278]; this
0x180004b07  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b0c  xor     edi, edi
0x180004b0e  test    r14d, r14d
0x180004b11  jnz     short loc_180004B44
0x180004b13  mov     rdx, rsi; unsigned __int16 *
0x180004b16  mov     rcx, r13; this
0x180004b19  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b1e  mov     edi, eax
0x180004b20  test    eax, eax
0x180004b22  js      loc_1800050E9
0x180004b28  mov     rdx, rsi; unsigned __int16 *
0x180004b2b  mov     rcx, r13; this
0x180004b2e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004b33  xor     edx, edx
0x180004b35  mov     edi, eax
0x180004b37  test    eax, eax
0x180004b39  js      loc_1800050E9
0x180004b3f  jmp     loc_180004DE7
0x180004b44  lea     rdx, aNoremove; "NoRemove"
0x180004b4b  mov     rcx, rsi; lpString1
0x180004b4e  mov     r12d, 1
0x180004b54  call    cs:__imp_lstrcmpiW
0x180004b5a  test    eax, eax
0x180004b5c  jnz     short loc_180004B78
0x180004b5e  mov     rdx, rsi; unsigned __int16 *
0x180004b61  mov     rcx, r13; this
0x180004b64  mov     r12d, edi
0x180004b67  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b6c  mov     edi, eax
0x180004b6e  test    eax, eax
0x180004b70  js      loc_1800050E9
0x180004b76  xor     edi, edi
0x180004b78  lea     rdx, aVal; "Val"
0x180004b7f  mov     rcx, rsi; lpString1
0x180004b82  call    cs:__imp_lstrcmpiW
0x180004b88  test    eax, eax
0x180004b8a  jnz     loc_180004C75
0x180004b90  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004b97  mov     rcx, r13; this
0x180004b9a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004b9f  mov     edi, eax
0x180004ba1  test    eax, eax
0x180004ba3  js      loc_1800050E9
0x180004ba9  mov     rdx, rsi; unsigned __int16 *
0x180004bac  mov     rcx, r13; this
0x180004baf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004bb4  xor     edx, edx; lpSubKey
0x180004bb6  mov     edi, eax
0x180004bb8  test    eax, eax
0x180004bba  js      loc_1800050E9
0x180004bc0  cmp     word ptr [rsi], 3Dh ; '='
0x180004bc4  jnz     loc_180005135
0x180004bca  cmp     [rsp+2310h+var_22A8], edx
0x180004bce  jz      short loc_180004BF7
0x180004bd0  mov     [rbp+2210h+var_2270], rdx
0x180004bd4  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004bdb  mov     [rbp+2210h+var_2268], rdx
0x180004bdf  mov     r9, rsi; unsigned __int16 *
0x180004be2  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004be6  mov     [rbp+2210h+var_2278], r15
0x180004bea  mov     rcx, r13; this
0x180004bed  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004bf2  jmp     loc_180004DD6
0x180004bf7  cmp     [rbp+2210h+arg_20], edx
0x180004bfd  jnz     short loc_180004C5B
0x180004bff  test    r12d, r12d
0x180004c02  jz      short loc_180004C5B
0x180004c04  lea     rax, [rsp+2310h+hKey]
0x180004c09  mov     [rsp+2310h+hKey], rdx
0x180004c0e  mov     r9d, 20006h; samDesired
0x180004c14  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004c19  xor     r8d, r8d; ulOptions
0x180004c1c  mov     rcx, r15; hKey
0x180004c1f  call    cs:__imp_RegOpenKeyExW
0x180004c25  test    eax, eax
0x180004c27  jnz     loc_1800050E0
0x180004c2d  mov     r14, [rsp+2310h+hKey]
0x180004c32  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180004c39  mov     rcx, r14; hKey
0x180004c3c  call    cs:__imp_RegDeleteValueW
0x180004c42  test    eax, 0FFFFFFFDh
0x180004c47  jnz     loc_18000511C
0x180004c4d  test    r14, r14
0x180004c50  jz      short loc_180004C5B
0x180004c52  mov     rcx, r14; hKey
0x180004c55  call    cs:__imp_RegCloseKey
0x180004c5b  mov     rdx, rsi; unsigned __int16 *
0x180004c5e  mov     rcx, r13; this
0x180004c61  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004c66  mov     edi, eax
0x180004c68  test    eax, eax
0x180004c6a  js      loc_1800050E9
0x180004c70  jmp     loc_180004F7E
0x180004c75  movzx   eax, word ptr [rsi]
0x180004c78  test    ax, ax
0x180004c7b  jz      short loc_180004CA2
0x180004c7d  mov     rcx, rsi; lpsz
0x180004c80  cmp     ax, 5Ch ; '\'
0x180004c84  jz      short loc_180004C99
0x180004c86  call    cs:__imp_CharNextW
0x180004c8c  mov     rcx, rax
0x180004c8f  movzx   eax, word ptr [rax]
0x180004c92  test    ax, ax
0x180004c95  jnz     short loc_180004C80
0x180004c97  jmp     short loc_180004CA2
0x180004c99  test    rcx, rcx
0x180004c9c  jnz     loc_180005135
0x180004ca2  cmp     [rsp+2310h+var_22A8], edi
0x180004ca6  jz      loc_180004E37
0x180004cac  lea     rax, [rsp+2310h+hKey]
0x180004cb1  mov     [rsp+2310h+hKey], rdi
0x180004cb6  mov     r14d, 2001Fh
0x180004cbc  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004cc1  mov     r9d, r14d; samDesired
0x180004cc4  xor     r8d, r8d; ulOptions
0x180004cc7  mov     rdx, rsi; lpSubKey
0x180004cca  mov     rcx, r15; hKey
0x180004ccd  call    cs:__imp_RegOpenKeyExW
0x180004cd3  test    eax, eax
0x180004cd5  jnz     short loc_180004CF8
0x180004cd7  mov     eax, edi
0x180004cd9  test    rbx, rbx
0x180004cdc  jz      short loc_180004CE7
0x180004cde  mov     rcx, rbx; hKey
0x180004ce1  call    cs:__imp_RegCloseKey
0x180004ce7  mov     rbx, [rsp+2310h+hKey]
0x180004cec  mov     [rbp+2210h+var_2290], rbx
0x180004cf0  test    eax, eax
0x180004cf2  jz      loc_180004DA3
0x180004cf8  lea     rax, [rsp+2310h+hKey]
0x180004cfd  mov     [rsp+2310h+hKey], rdi
0x180004d02  mov     r9d, 20019h; samDesired
0x180004d08  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004d0d  xor     r8d, r8d; ulOptions
0x180004d10  mov     rdx, rsi; lpSubKey
0x180004d13  mov     rcx, r15; hKey
0x180004d16  call    cs:__imp_RegOpenKeyExW
0x180004d1c  test    eax, eax
0x180004d1e  jnz     short loc_180004D3D
0x180004d20  mov     eax, edi
0x180004d22  test    rbx, rbx
0x180004d25  jz      short loc_180004D30
0x180004d27  mov     rcx, rbx; hKey
0x180004d2a  call    cs:__imp_RegCloseKey
0x180004d30  mov     rbx, [rsp+2310h+hKey]
0x180004d35  mov     [rbp+2210h+var_2290], rbx
0x180004d39  test    eax, eax
0x180004d3b  jz      short loc_180004DA3
0x180004d3d  lea     rax, [rsp+2310h+hKey]
0x180004d42  mov     dword ptr [rsp+2310h+hKey], edi
0x180004d46  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004d4b  xor     r9d, r9d; lpClass
0x180004d4e  lea     rax, [rsp+2310h+var_2298]
0x180004d53  mov     [rsp+2310h+var_2298], rdi
0x180004d58  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180004d5d  xor     r8d, r8d; Reserved
0x180004d60  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004d65  mov     rdx, rsi; lpSubKey
0x180004d68  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180004d6d  mov     rcx, r15; hKey
0x180004d70  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180004d74  call    cs:__imp_RegCreateKeyExW
0x180004d7a  test    eax, eax
0x180004d7c  jnz     loc_1800050E0
0x180004d82  mov     eax, edi
0x180004d84  test    rbx, rbx
0x180004d87  jz      short loc_180004D92
0x180004d89  mov     rcx, rbx; hKey
0x180004d8c  call    cs:__imp_RegCloseKey
0x180004d92  mov     rbx, [rsp+2310h+var_2298]
0x180004d97  mov     [rbp+2210h+var_2290], rbx
0x180004d9b  test    eax, eax
0x180004d9d  jnz     loc_1800050E0
0x180004da3  mov     rdx, rsi; unsigned __int16 *
0x180004da6  mov     rcx, r13; this
0x180004da9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004dae  xor     edx, edx
0x180004db0  mov     edi, eax
0x180004db2  test    eax, eax
0x180004db4  js      loc_1800050E9
0x180004dba  cmp     word ptr [rsi], 3Dh ; '='
0x180004dbe  jnz     short loc_180004DE2
0x180004dc0  mov     r9, rsi; unsigned __int16 *
0x180004dc3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180004dc7  xor     r8d, r8d; unsigned __int16 *
0x180004dca  mov     rcx, r13; this
0x180004dcd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004dd2  mov     rbx, [rbp+2210h+var_2290]
0x180004dd6  xor     edx, edx
0x180004dd8  mov     edi, eax
0x180004dda  test    eax, eax
0x180004ddc  js      loc_1800050E9
0x180004de2  mov     r12d, [rsp+2310h+var_22A8]
0x180004de7  cmp     word ptr [rsi], 7Bh ; '{'
0x180004deb  jnz     loc_180004F7E
0x180004df1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004df5  inc     rax
0x180004df8  cmp     [rsi+rax*2], dx
0x180004dfc  jnz     short loc_180004DF5
0x180004dfe  cmp     rax, 1
0x180004e02  jnz     loc_180004F7E
0x180004e08  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x180004e0c  mov     r9d, r12d; int
0x180004e0f  mov     rdx, rsi; unsigned __int16 *
0x180004e12  mov     r8, rbx; HKEY
0x180004e15  mov     rcx, r13; this
0x180004e18  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004e1d  mov     edi, eax
0x180004e1f  test    eax, eax
0x180004e21  js      loc_1800050E9
0x180004e27  mov     rdx, rsi; unsigned __int16 *
0x180004e2a  mov     rcx, r13; this
0x180004e2d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004e32  jmp     loc_180004C66
0x180004e37  mov     edi, [rbp+2210h+arg_20]
0x180004e3d  xor     eax, eax
0x180004e3f  test    edi, edi
  ... truncated ...
```
