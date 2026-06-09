# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x14000d8cc`
- end: `0x14000e069`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14000d578`
- `0x14000d8cc`

## callees

- `0x140001fa0`
- `0x1400045e4`
- `0x14000c654`
- `0x14000cc6c`
- `0x14000cd84`
- `0x14000cf98`
- `0x14000d428`
- `0x14000d8cc`
- `0x14000e07c`
- `0x14000f6e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000db45`
- `ADVAPI32!RegCloseKey` at `0x14000dbd1`
- `ADVAPI32!RegCloseKey` at `0x14000dc1a`
- `ADVAPI32!RegCloseKey` at `0x14000dc7c`
- `ADVAPI32!RegCloseKey` at `0x14000dd6c`
- `ADVAPI32!RegCloseKey` at `0x14000df82`
- `ADVAPI32!RegCloseKey` at `0x14000dfe1`
- `ADVAPI32!RegCloseKey` at `0x14000e01d`
- `ADVAPI32!RegCloseKey` at `0x14000e02d`
- `ADVAPI32!RegCloseKey` at `0x14000db45`
- `ADVAPI32!RegCloseKey` at `0x14000dbd1`
- `ADVAPI32!RegCloseKey` at `0x14000dc1a`
- `ADVAPI32!RegCloseKey` at `0x14000dc7c`
- `ADVAPI32!RegCloseKey` at `0x14000dd6c`
- `ADVAPI32!RegCloseKey` at `0x14000df82`
- `ADVAPI32!RegCloseKey` at `0x14000dfe1`
- `ADVAPI32!RegCloseKey` at `0x14000e01d`
- `ADVAPI32!RegCloseKey` at `0x14000e02d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000db0f`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dbbd`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dc06`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dd51`
- `ADVAPI32!RegOpenKeyExW` at `0x14000db0f`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dbbd`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dc06`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dd51`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000deca`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000df63`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000deca`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000df63`
- `ADVAPI32!RegCreateKeyExW` at `0x14000dc64`
- `ADVAPI32!RegCreateKeyExW` at `0x14000dc64`
- `ADVAPI32!RegDeleteValueW` at `0x14000db2c`
- `ADVAPI32!RegDeleteValueW` at `0x14000db2c`
- `KERNEL32!lstrcmpiW` at `0x14000d94a`
- `KERNEL32!lstrcmpiW` at `0x14000d95d`
- `KERNEL32!lstrcmpiW` at `0x14000d9db`
- `KERNEL32!lstrcmpiW` at `0x14000da44`
- `KERNEL32!lstrcmpiW` at `0x14000da72`
- `KERNEL32!lstrcmpiW` at `0x14000def1`
- `KERNEL32!lstrcmpiW` at `0x14000d94a`
- `KERNEL32!lstrcmpiW` at `0x14000d95d`
- `KERNEL32!lstrcmpiW` at `0x14000d9db`
- `KERNEL32!lstrcmpiW` at `0x14000da44`
- `KERNEL32!lstrcmpiW` at `0x14000da72`
- `KERNEL32!lstrcmpiW` at `0x14000def1`
- `USER32!CharNextW` at `0x14000d9af`
- `USER32!CharNextW` at `0x14000db76`
- `USER32!CharNextW` at `0x14000d9af`
- `USER32!CharNextW` at `0x14000db76`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000dda3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000dda3`

## string_xrefs

- `0x14000d950`: `ForceRemove`
- `0x14000da34`: `NoRemove`
- `0x14000d940`: `Delete`

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
  int v29; // eax
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
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
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
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, String1);
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
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, String1);
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
0x14000d8cc  push    rbp
0x14000d8ce  push    rbx
0x14000d8cf  push    rsi
0x14000d8d0  push    rdi
0x14000d8d1  push    r12
0x14000d8d3  push    r13
0x14000d8d5  push    r14
0x14000d8d7  push    r15
0x14000d8d9  lea     rbp, [rsp-21D8h]
0x14000d8e1  mov     eax, 22D8h
0x14000d8e6  call    _alloca_probe
0x14000d8eb  sub     rsp, rax
0x14000d8ee  mov     rax, cs:__security_cookie
0x14000d8f5  xor     rax, rsp
0x14000d8f8  mov     [rbp+2210h+var_50], rax
0x14000d8ff  xor     r14d, r14d
0x14000d902  mov     [rsp+2310h+var_22A8], r9d
0x14000d907  mov     ebx, r14d
0x14000d90a  mov     [rsp+2310h+var_22A0], r8
0x14000d90f  mov     [rbp+2210h+var_2290], rbx
0x14000d913  mov     r12d, r9d
0x14000d916  mov     r15, r8
0x14000d919  mov     [rbp+2210h+var_2288], r14
0x14000d91d  mov     rsi, rdx
0x14000d920  mov     [rbp+2210h+var_2280], r14
0x14000d924  mov     r13, rcx
0x14000d927  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d92c  mov     edi, eax
0x14000d92e  test    eax, eax
0x14000d930  js      loc_14000DFE9
0x14000d936  cmp     word ptr [rsi], 7Dh ; '}'
0x14000d93a  jz      loc_14000DFE7
0x14000d940  lea     rdx, String2; "Delete"
0x14000d947  mov     rcx, rsi; lpString1
0x14000d94a  call    cs:__imp_lstrcmpiW
0x14000d950  lea     rdx, aForceremove; "ForceRemove"
0x14000d957  mov     rcx, rsi; lpString1
0x14000d95a  mov     r14d, eax
0x14000d95d  call    cs:__imp_lstrcmpiW
0x14000d963  xor     edi, edi
0x14000d965  test    eax, eax
0x14000d967  jz      short loc_14000D972
0x14000d969  test    r14d, r14d
0x14000d96c  jnz     loc_14000DA34
0x14000d972  mov     rdx, rsi; unsigned __int16 *
0x14000d975  mov     rcx, r13; this
0x14000d978  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d97d  mov     edi, eax
0x14000d97f  test    eax, eax
0x14000d981  js      loc_14000DFD9
0x14000d987  xor     edi, edi
0x14000d989  test    r12d, r12d
0x14000d98c  jz      loc_14000DA34
0x14000d992  movzx   eax, word ptr [rsi]
0x14000d995  mov     [rbp+2210h+var_2278], rdi
0x14000d999  mov     [rbp+2210h+var_2270], rdi
0x14000d99d  mov     [rbp+2210h+var_2268], rdi
0x14000d9a1  test    ax, ax
0x14000d9a4  jz      short loc_14000D9CB
0x14000d9a6  mov     rcx, rsi; lpsz
0x14000d9a9  cmp     ax, 5Ch ; '\'
0x14000d9ad  jz      short loc_14000D9C2
0x14000d9af  call    cs:__imp_CharNextW
0x14000d9b5  mov     rcx, rax
0x14000d9b8  movzx   eax, word ptr [rax]
0x14000d9bb  test    ax, ax
0x14000d9be  jnz     short loc_14000D9A9
0x14000d9c0  jmp     short loc_14000D9CB
0x14000d9c2  test    rcx, rcx
0x14000d9c5  jnz     loc_14000E025
0x14000d9cb  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x14000d9d2  mov     edx, edi
0x14000d9d4  mov     rcx, rsi; lpString1
0x14000d9d7  mov     rdx, [rax+rdx*8]; lpString2
0x14000d9db  call    cs:__imp_lstrcmpiW
0x14000d9e1  test    eax, eax
0x14000d9e3  jz      short loc_14000D9FC
0x14000d9e5  inc     edi
0x14000d9e7  cmp     edi, 0Ch
0x14000d9ea  jl      short loc_14000D9CB
0x14000d9ec  mov     rdx, rsi; unsigned __int16 *
0x14000d9ef  mov     [rbp+2210h+var_2278], r15
0x14000d9f3  lea     rcx, [rbp+2210h+var_2278]; this
0x14000d9f7  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000d9fc  xor     edi, edi
0x14000d9fe  test    r14d, r14d
0x14000da01  jnz     short loc_14000DA34
0x14000da03  mov     rdx, rsi; unsigned __int16 *
0x14000da06  mov     rcx, r13; this
0x14000da09  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000da0e  mov     edi, eax
0x14000da10  test    eax, eax
0x14000da12  js      loc_14000DFD9
0x14000da18  mov     rdx, rsi; unsigned __int16 *
0x14000da1b  mov     rcx, r13; this
0x14000da1e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000da23  xor     edx, edx
0x14000da25  mov     edi, eax
0x14000da27  test    eax, eax
0x14000da29  js      loc_14000DFD9
0x14000da2f  jmp     loc_14000DCD7
0x14000da34  lea     rdx, aNoremove; "NoRemove"
0x14000da3b  mov     rcx, rsi; lpString1
0x14000da3e  mov     r12d, 1
0x14000da44  call    cs:__imp_lstrcmpiW
0x14000da4a  test    eax, eax
0x14000da4c  jnz     short loc_14000DA68
0x14000da4e  mov     rdx, rsi; unsigned __int16 *
0x14000da51  mov     rcx, r13; this
0x14000da54  mov     r12d, edi
0x14000da57  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000da5c  mov     edi, eax
0x14000da5e  test    eax, eax
0x14000da60  js      loc_14000DFD9
0x14000da66  xor     edi, edi
0x14000da68  lea     rdx, aVal; "Val"
0x14000da6f  mov     rcx, rsi; lpString1
0x14000da72  call    cs:__imp_lstrcmpiW
0x14000da78  test    eax, eax
0x14000da7a  jnz     loc_14000DB65
0x14000da80  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x14000da87  mov     rcx, r13; this
0x14000da8a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000da8f  mov     edi, eax
0x14000da91  test    eax, eax
0x14000da93  js      loc_14000DFD9
0x14000da99  mov     rdx, rsi; unsigned __int16 *
0x14000da9c  mov     rcx, r13; this
0x14000da9f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000daa4  xor     edx, edx; lpSubKey
0x14000daa6  mov     edi, eax
0x14000daa8  test    eax, eax
0x14000daaa  js      loc_14000DFD9
0x14000dab0  cmp     word ptr [rsi], 3Dh ; '='
0x14000dab4  jnz     loc_14000E025
0x14000daba  cmp     [rsp+2310h+var_22A8], edx
0x14000dabe  jz      short loc_14000DAE7
0x14000dac0  mov     [rbp+2210h+var_2270], rdx
0x14000dac4  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x14000dacb  mov     [rbp+2210h+var_2268], rdx
0x14000dacf  mov     r9, rsi; unsigned __int16 *
0x14000dad2  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x14000dad6  mov     [rbp+2210h+var_2278], r15
0x14000dada  mov     rcx, r13; this
0x14000dadd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14000dae2  jmp     loc_14000DCC6
0x14000dae7  cmp     [rbp+2210h+arg_20], edx
0x14000daed  jnz     short loc_14000DB4B
0x14000daef  test    r12d, r12d
0x14000daf2  jz      short loc_14000DB4B
0x14000daf4  lea     rax, [rsp+2310h+hKey]
0x14000daf9  mov     [rsp+2310h+hKey], rdx
0x14000dafe  mov     r9d, 20006h; samDesired
0x14000db04  mov     [rsp+2310h+phkResult], rax; phkResult
0x14000db09  xor     r8d, r8d; ulOptions
0x14000db0c  mov     rcx, r15; hKey
0x14000db0f  call    cs:__imp_RegOpenKeyExW
0x14000db15  test    eax, eax
0x14000db17  jnz     loc_14000DFD0
0x14000db1d  mov     r14, [rsp+2310h+hKey]
0x14000db22  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x14000db29  mov     rcx, r14; hKey
0x14000db2c  call    cs:__imp_RegDeleteValueW
0x14000db32  test    eax, 0FFFFFFFDh
0x14000db37  jnz     loc_14000E00C
0x14000db3d  test    r14, r14
0x14000db40  jz      short loc_14000DB4B
0x14000db42  mov     rcx, r14; hKey
0x14000db45  call    cs:__imp_RegCloseKey
0x14000db4b  mov     rdx, rsi; unsigned __int16 *
0x14000db4e  mov     rcx, r13; this
0x14000db51  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000db56  mov     edi, eax
0x14000db58  test    eax, eax
0x14000db5a  js      loc_14000DFD9
0x14000db60  jmp     loc_14000DE6E
0x14000db65  movzx   eax, word ptr [rsi]
0x14000db68  test    ax, ax
0x14000db6b  jz      short loc_14000DB92
0x14000db6d  mov     rcx, rsi; lpsz
0x14000db70  cmp     ax, 5Ch ; '\'
0x14000db74  jz      short loc_14000DB89
0x14000db76  call    cs:__imp_CharNextW
0x14000db7c  mov     rcx, rax
0x14000db7f  movzx   eax, word ptr [rax]
0x14000db82  test    ax, ax
0x14000db85  jnz     short loc_14000DB70
0x14000db87  jmp     short loc_14000DB92
0x14000db89  test    rcx, rcx
0x14000db8c  jnz     loc_14000E025
0x14000db92  cmp     [rsp+2310h+var_22A8], edi
0x14000db96  jz      loc_14000DD27
0x14000db9c  lea     rax, [rsp+2310h+hKey]
0x14000dba1  mov     [rsp+2310h+hKey], rdi
0x14000dba6  mov     r14d, 2001Fh
0x14000dbac  mov     [rsp+2310h+phkResult], rax; phkResult
0x14000dbb1  mov     r9d, r14d; samDesired
0x14000dbb4  xor     r8d, r8d; ulOptions
0x14000dbb7  mov     rdx, rsi; lpSubKey
0x14000dbba  mov     rcx, r15; hKey
0x14000dbbd  call    cs:__imp_RegOpenKeyExW
0x14000dbc3  test    eax, eax
0x14000dbc5  jnz     short loc_14000DBE8
0x14000dbc7  mov     eax, edi
0x14000dbc9  test    rbx, rbx
0x14000dbcc  jz      short loc_14000DBD7
0x14000dbce  mov     rcx, rbx; hKey
0x14000dbd1  call    cs:__imp_RegCloseKey
0x14000dbd7  mov     rbx, [rsp+2310h+hKey]
0x14000dbdc  mov     [rbp+2210h+var_2290], rbx
0x14000dbe0  test    eax, eax
0x14000dbe2  jz      loc_14000DC93
0x14000dbe8  lea     rax, [rsp+2310h+hKey]
0x14000dbed  mov     [rsp+2310h+hKey], rdi
0x14000dbf2  mov     r9d, 20019h; samDesired
0x14000dbf8  mov     [rsp+2310h+phkResult], rax; phkResult
0x14000dbfd  xor     r8d, r8d; ulOptions
0x14000dc00  mov     rdx, rsi; lpSubKey
0x14000dc03  mov     rcx, r15; hKey
0x14000dc06  call    cs:__imp_RegOpenKeyExW
0x14000dc0c  test    eax, eax
0x14000dc0e  jnz     short loc_14000DC2D
0x14000dc10  mov     eax, edi
0x14000dc12  test    rbx, rbx
0x14000dc15  jz      short loc_14000DC20
0x14000dc17  mov     rcx, rbx; hKey
0x14000dc1a  call    cs:__imp_RegCloseKey
0x14000dc20  mov     rbx, [rsp+2310h+hKey]
0x14000dc25  mov     [rbp+2210h+var_2290], rbx
0x14000dc29  test    eax, eax
0x14000dc2b  jz      short loc_14000DC93
0x14000dc2d  lea     rax, [rsp+2310h+hKey]
0x14000dc32  mov     dword ptr [rsp+2310h+hKey], edi
0x14000dc36  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x14000dc3b  xor     r9d, r9d; lpClass
0x14000dc3e  lea     rax, [rsp+2310h+var_2298]
0x14000dc43  mov     [rsp+2310h+var_2298], rdi
0x14000dc48  mov     [rsp+2310h+var_22D8], rax; phkResult
0x14000dc4d  xor     r8d, r8d; Reserved
0x14000dc50  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14000dc55  mov     rdx, rsi; lpSubKey
0x14000dc58  mov     [rsp+2310h+samDesired], r14d; samDesired
0x14000dc5d  mov     rcx, r15; hKey
0x14000dc60  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x14000dc64  call    cs:__imp_RegCreateKeyExW
0x14000dc6a  test    eax, eax
0x14000dc6c  jnz     loc_14000DFD0
0x14000dc72  mov     eax, edi
0x14000dc74  test    rbx, rbx
0x14000dc77  jz      short loc_14000DC82
0x14000dc79  mov     rcx, rbx; hKey
0x14000dc7c  call    cs:__imp_RegCloseKey
0x14000dc82  mov     rbx, [rsp+2310h+var_2298]
0x14000dc87  mov     [rbp+2210h+var_2290], rbx
0x14000dc8b  test    eax, eax
0x14000dc8d  jnz     loc_14000DFD0
0x14000dc93  mov     rdx, rsi; unsigned __int16 *
0x14000dc96  mov     rcx, r13; this
0x14000dc99  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000dc9e  xor     edx, edx
0x14000dca0  mov     edi, eax
0x14000dca2  test    eax, eax
0x14000dca4  js      loc_14000DFD9
0x14000dcaa  cmp     word ptr [rsi], 3Dh ; '='
0x14000dcae  jnz     short loc_14000DCD2
0x14000dcb0  mov     r9, rsi; unsigned __int16 *
0x14000dcb3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x14000dcb7  xor     r8d, r8d; unsigned __int16 *
0x14000dcba  mov     rcx, r13; this
0x14000dcbd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14000dcc2  mov     rbx, [rbp+2210h+var_2290]
0x14000dcc6  xor     edx, edx
0x14000dcc8  mov     edi, eax
0x14000dcca  test    eax, eax
0x14000dccc  js      loc_14000DFD9
0x14000dcd2  mov     r12d, [rsp+2310h+var_22A8]
0x14000dcd7  cmp     word ptr [rsi], 7Bh ; '{'
0x14000dcdb  jnz     loc_14000DE6E
0x14000dce1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000dce5  inc     rax
0x14000dce8  cmp     [rsi+rax*2], dx
0x14000dcec  jnz     short loc_14000DCE5
0x14000dcee  cmp     rax, 1
0x14000dcf2  jnz     loc_14000DE6E
0x14000dcf8  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x14000dcfc  mov     r9d, r12d; int
0x14000dcff  mov     rdx, rsi; unsigned __int16 *
0x14000dd02  mov     r8, rbx; HKEY
0x14000dd05  mov     rcx, r13; this
0x14000dd08  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000dd0d  mov     edi, eax
0x14000dd0f  test    eax, eax
0x14000dd11  js      loc_14000DFD9
0x14000dd17  mov     rdx, rsi; unsigned __int16 *
0x14000dd1a  mov     rcx, r13; this
0x14000dd1d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000dd22  jmp     loc_14000DB56
0x14000dd27  mov     edi, [rbp+2210h+arg_20]
0x14000dd2d  xor     eax, eax
0x14000dd2f  test    edi, edi
  ... truncated ...
```
