# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180003a3c`
- end: `0x1800041d9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800036e8`
- `0x180003a3c`

## callees

- `0x180002454`
- `0x180002aac`
- `0x180002ac4`
- `0x180002e78`
- `0x1800030c0`
- `0x180003598`
- `0x180003a3c`
- `0x180004304`
- `0x180018500`
- `0x1800185c0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003f13`
- `msvcrt!wcsncpy_s` at `0x180003f13`
- `USER32!CharNextW` at `0x180003b1f`
- `USER32!CharNextW` at `0x180003ce6`
- `USER32!CharNextW` at `0x180003b1f`
- `USER32!CharNextW` at `0x180003ce6`
- `ADVAPI32!RegCloseKey` at `0x180003cb5`
- `ADVAPI32!RegCloseKey` at `0x180003d41`
- `ADVAPI32!RegCloseKey` at `0x180003d8a`
- `ADVAPI32!RegCloseKey` at `0x180003dec`
- `ADVAPI32!RegCloseKey` at `0x180003edc`
- `ADVAPI32!RegCloseKey` at `0x1800040f2`
- `ADVAPI32!RegCloseKey` at `0x180004151`
- `ADVAPI32!RegCloseKey` at `0x18000418d`
- `ADVAPI32!RegCloseKey` at `0x18000419d`
- `ADVAPI32!RegCloseKey` at `0x180003cb5`
- `ADVAPI32!RegCloseKey` at `0x180003d41`
- `ADVAPI32!RegCloseKey` at `0x180003d8a`
- `ADVAPI32!RegCloseKey` at `0x180003dec`
- `ADVAPI32!RegCloseKey` at `0x180003edc`
- `ADVAPI32!RegCloseKey` at `0x1800040f2`
- `ADVAPI32!RegCloseKey` at `0x180004151`
- `ADVAPI32!RegCloseKey` at `0x18000418d`
- `ADVAPI32!RegCloseKey` at `0x18000419d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000403a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800040d3`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000403a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800040d3`
- `ADVAPI32!RegCreateKeyExW` at `0x180003dd4`
- `ADVAPI32!RegCreateKeyExW` at `0x180003dd4`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c7f`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d2d`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d76`
- `ADVAPI32!RegOpenKeyExW` at `0x180003ec1`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c7f`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d2d`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d76`
- `ADVAPI32!RegOpenKeyExW` at `0x180003ec1`
- `ADVAPI32!RegDeleteValueW` at `0x180003c9c`
- `ADVAPI32!RegDeleteValueW` at `0x180003c9c`
- `KERNEL32!lstrcmpiW` at `0x180003aba`
- `KERNEL32!lstrcmpiW` at `0x180003acd`
- `KERNEL32!lstrcmpiW` at `0x180003b4b`
- `KERNEL32!lstrcmpiW` at `0x180003bb4`
- `KERNEL32!lstrcmpiW` at `0x180003be2`
- `KERNEL32!lstrcmpiW` at `0x180004061`
- `KERNEL32!lstrcmpiW` at `0x180003aba`
- `KERNEL32!lstrcmpiW` at `0x180003acd`
- `KERNEL32!lstrcmpiW` at `0x180003b4b`
- `KERNEL32!lstrcmpiW` at `0x180003bb4`
- `KERNEL32!lstrcmpiW` at `0x180003be2`
- `KERNEL32!lstrcmpiW` at `0x180004061`

## string_xrefs

- `0x180003ac0`: `ForceRemove`
- `0x180003ba4`: `NoRemove`
- `0x180003ab0`: `Delete`

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
0x180003a3c  push    rbp
0x180003a3e  push    rbx
0x180003a3f  push    rsi
0x180003a40  push    rdi
0x180003a41  push    r12
0x180003a43  push    r13
0x180003a45  push    r14
0x180003a47  push    r15
0x180003a49  lea     rbp, [rsp-21D8h]
0x180003a51  mov     eax, 22D8h
0x180003a56  call    _alloca_probe
0x180003a5b  sub     rsp, rax
0x180003a5e  mov     rax, cs:__security_cookie
0x180003a65  xor     rax, rsp
0x180003a68  mov     [rbp+2210h+var_50], rax
0x180003a6f  xor     r14d, r14d
0x180003a72  mov     [rsp+2310h+var_22A8], r9d
0x180003a77  mov     ebx, r14d
0x180003a7a  mov     [rsp+2310h+var_22A0], r8
0x180003a7f  mov     [rbp+2210h+var_2290], rbx
0x180003a83  mov     r12d, r9d
0x180003a86  mov     r15, r8
0x180003a89  mov     [rbp+2210h+var_2288], r14
0x180003a8d  mov     rsi, rdx
0x180003a90  mov     [rbp+2210h+var_2280], r14
0x180003a94  mov     r13, rcx
0x180003a97  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003a9c  mov     edi, eax
0x180003a9e  test    eax, eax
0x180003aa0  js      loc_180004159
0x180003aa6  cmp     word ptr [rsi], 7Dh ; '}'
0x180003aaa  jz      loc_180004157
0x180003ab0  lea     rdx, String2; "Delete"
0x180003ab7  mov     rcx, rsi; lpString1
0x180003aba  call    cs:__imp_lstrcmpiW
0x180003ac0  lea     rdx, aForceremove; "ForceRemove"
0x180003ac7  mov     rcx, rsi; lpString1
0x180003aca  mov     r14d, eax
0x180003acd  call    cs:__imp_lstrcmpiW
0x180003ad3  xor     edi, edi
0x180003ad5  test    eax, eax
0x180003ad7  jz      short loc_180003AE2
0x180003ad9  test    r14d, r14d
0x180003adc  jnz     loc_180003BA4
0x180003ae2  mov     rdx, rsi; unsigned __int16 *
0x180003ae5  mov     rcx, r13; this
0x180003ae8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003aed  mov     edi, eax
0x180003aef  test    eax, eax
0x180003af1  js      loc_180004149
0x180003af7  xor     edi, edi
0x180003af9  test    r12d, r12d
0x180003afc  jz      loc_180003BA4
0x180003b02  movzx   eax, word ptr [rsi]
0x180003b05  mov     [rbp+2210h+var_2278], rdi
0x180003b09  mov     [rbp+2210h+var_2270], rdi
0x180003b0d  mov     [rbp+2210h+var_2268], rdi
0x180003b11  test    ax, ax
0x180003b14  jz      short loc_180003B3B
0x180003b16  mov     rcx, rsi; lpsz
0x180003b19  cmp     ax, 5Ch ; '\'
0x180003b1d  jz      short loc_180003B32
0x180003b1f  call    cs:__imp_CharNextW
0x180003b25  mov     rcx, rax
0x180003b28  movzx   eax, word ptr [rax]
0x180003b2b  test    ax, ax
0x180003b2e  jnz     short loc_180003B19
0x180003b30  jmp     short loc_180003B3B
0x180003b32  test    rcx, rcx
0x180003b35  jnz     loc_180004195
0x180003b3b  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180003b42  mov     edx, edi
0x180003b44  mov     rcx, rsi; lpString1
0x180003b47  mov     rdx, [rax+rdx*8]; lpString2
0x180003b4b  call    cs:__imp_lstrcmpiW
0x180003b51  test    eax, eax
0x180003b53  jz      short loc_180003B6C
0x180003b55  inc     edi
0x180003b57  cmp     edi, 0Ch
0x180003b5a  jl      short loc_180003B3B
0x180003b5c  mov     rdx, rsi; unsigned __int16 *
0x180003b5f  mov     [rbp+2210h+var_2278], r15
0x180003b63  lea     rcx, [rbp+2210h+var_2278]; this
0x180003b67  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003b6c  xor     edi, edi
0x180003b6e  test    r14d, r14d
0x180003b71  jnz     short loc_180003BA4
0x180003b73  mov     rdx, rsi; unsigned __int16 *
0x180003b76  mov     rcx, r13; this
0x180003b79  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003b7e  mov     edi, eax
0x180003b80  test    eax, eax
0x180003b82  js      loc_180004149
0x180003b88  mov     rdx, rsi; unsigned __int16 *
0x180003b8b  mov     rcx, r13; this
0x180003b8e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003b93  xor     edx, edx
0x180003b95  mov     edi, eax
0x180003b97  test    eax, eax
0x180003b99  js      loc_180004149
0x180003b9f  jmp     loc_180003E47
0x180003ba4  lea     rdx, aNoremove; "NoRemove"
0x180003bab  mov     rcx, rsi; lpString1
0x180003bae  mov     r12d, 1
0x180003bb4  call    cs:__imp_lstrcmpiW
0x180003bba  test    eax, eax
0x180003bbc  jnz     short loc_180003BD8
0x180003bbe  mov     rdx, rsi; unsigned __int16 *
0x180003bc1  mov     rcx, r13; this
0x180003bc4  mov     r12d, edi
0x180003bc7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bcc  mov     edi, eax
0x180003bce  test    eax, eax
0x180003bd0  js      loc_180004149
0x180003bd6  xor     edi, edi
0x180003bd8  lea     rdx, aVal; "Val"
0x180003bdf  mov     rcx, rsi; lpString1
0x180003be2  call    cs:__imp_lstrcmpiW
0x180003be8  test    eax, eax
0x180003bea  jnz     loc_180003CD5
0x180003bf0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180003bf7  mov     rcx, r13; this
0x180003bfa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bff  mov     edi, eax
0x180003c01  test    eax, eax
0x180003c03  js      loc_180004149
0x180003c09  mov     rdx, rsi; unsigned __int16 *
0x180003c0c  mov     rcx, r13; this
0x180003c0f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003c14  xor     edx, edx; lpSubKey
0x180003c16  mov     edi, eax
0x180003c18  test    eax, eax
0x180003c1a  js      loc_180004149
0x180003c20  cmp     word ptr [rsi], 3Dh ; '='
0x180003c24  jnz     loc_180004195
0x180003c2a  cmp     [rsp+2310h+var_22A8], edx
0x180003c2e  jz      short loc_180003C57
0x180003c30  mov     [rbp+2210h+var_2270], rdx
0x180003c34  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180003c3b  mov     [rbp+2210h+var_2268], rdx
0x180003c3f  mov     r9, rsi; unsigned __int16 *
0x180003c42  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180003c46  mov     [rbp+2210h+var_2278], r15
0x180003c4a  mov     rcx, r13; this
0x180003c4d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180003c52  jmp     loc_180003E36
0x180003c57  cmp     [rbp+2210h+arg_20], edx
0x180003c5d  jnz     short loc_180003CBB
0x180003c5f  test    r12d, r12d
0x180003c62  jz      short loc_180003CBB
0x180003c64  lea     rax, [rsp+2310h+hKey]
0x180003c69  mov     [rsp+2310h+hKey], rdx
0x180003c6e  mov     r9d, 20006h; samDesired
0x180003c74  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003c79  xor     r8d, r8d; ulOptions
0x180003c7c  mov     rcx, r15; hKey
0x180003c7f  call    cs:__imp_RegOpenKeyExW
0x180003c85  test    eax, eax
0x180003c87  jnz     loc_180004140
0x180003c8d  mov     r14, [rsp+2310h+hKey]
0x180003c92  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180003c99  mov     rcx, r14; hKey
0x180003c9c  call    cs:__imp_RegDeleteValueW
0x180003ca2  test    eax, 0FFFFFFFDh
0x180003ca7  jnz     loc_18000417C
0x180003cad  test    r14, r14
0x180003cb0  jz      short loc_180003CBB
0x180003cb2  mov     rcx, r14; hKey
0x180003cb5  call    cs:__imp_RegCloseKey
0x180003cbb  mov     rdx, rsi; unsigned __int16 *
0x180003cbe  mov     rcx, r13; this
0x180003cc1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003cc6  mov     edi, eax
0x180003cc8  test    eax, eax
0x180003cca  js      loc_180004149
0x180003cd0  jmp     loc_180003FDE
0x180003cd5  movzx   eax, word ptr [rsi]
0x180003cd8  test    ax, ax
0x180003cdb  jz      short loc_180003D02
0x180003cdd  mov     rcx, rsi; lpsz
0x180003ce0  cmp     ax, 5Ch ; '\'
0x180003ce4  jz      short loc_180003CF9
0x180003ce6  call    cs:__imp_CharNextW
0x180003cec  mov     rcx, rax
0x180003cef  movzx   eax, word ptr [rax]
0x180003cf2  test    ax, ax
0x180003cf5  jnz     short loc_180003CE0
0x180003cf7  jmp     short loc_180003D02
0x180003cf9  test    rcx, rcx
0x180003cfc  jnz     loc_180004195
0x180003d02  cmp     [rsp+2310h+var_22A8], edi
0x180003d06  jz      loc_180003E97
0x180003d0c  lea     rax, [rsp+2310h+hKey]
0x180003d11  mov     [rsp+2310h+hKey], rdi
0x180003d16  mov     r14d, 2001Fh
0x180003d1c  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003d21  mov     r9d, r14d; samDesired
0x180003d24  xor     r8d, r8d; ulOptions
0x180003d27  mov     rdx, rsi; lpSubKey
0x180003d2a  mov     rcx, r15; hKey
0x180003d2d  call    cs:__imp_RegOpenKeyExW
0x180003d33  test    eax, eax
0x180003d35  jnz     short loc_180003D58
0x180003d37  mov     eax, edi
0x180003d39  test    rbx, rbx
0x180003d3c  jz      short loc_180003D47
0x180003d3e  mov     rcx, rbx; hKey
0x180003d41  call    cs:__imp_RegCloseKey
0x180003d47  mov     rbx, [rsp+2310h+hKey]
0x180003d4c  mov     [rbp+2210h+var_2290], rbx
0x180003d50  test    eax, eax
0x180003d52  jz      loc_180003E03
0x180003d58  lea     rax, [rsp+2310h+hKey]
0x180003d5d  mov     [rsp+2310h+hKey], rdi
0x180003d62  mov     r9d, 20019h; samDesired
0x180003d68  mov     [rsp+2310h+phkResult], rax; phkResult
0x180003d6d  xor     r8d, r8d; ulOptions
0x180003d70  mov     rdx, rsi; lpSubKey
0x180003d73  mov     rcx, r15; hKey
0x180003d76  call    cs:__imp_RegOpenKeyExW
0x180003d7c  test    eax, eax
0x180003d7e  jnz     short loc_180003D9D
0x180003d80  mov     eax, edi
0x180003d82  test    rbx, rbx
0x180003d85  jz      short loc_180003D90
0x180003d87  mov     rcx, rbx; hKey
0x180003d8a  call    cs:__imp_RegCloseKey
0x180003d90  mov     rbx, [rsp+2310h+hKey]
0x180003d95  mov     [rbp+2210h+var_2290], rbx
0x180003d99  test    eax, eax
0x180003d9b  jz      short loc_180003E03
0x180003d9d  lea     rax, [rsp+2310h+hKey]
0x180003da2  mov     dword ptr [rsp+2310h+hKey], edi
0x180003da6  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180003dab  xor     r9d, r9d; lpClass
0x180003dae  lea     rax, [rsp+2310h+var_2298]
0x180003db3  mov     [rsp+2310h+var_2298], rdi
0x180003db8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180003dbd  xor     r8d, r8d; Reserved
0x180003dc0  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003dc5  mov     rdx, rsi; lpSubKey
0x180003dc8  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180003dcd  mov     rcx, r15; hKey
0x180003dd0  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180003dd4  call    cs:__imp_RegCreateKeyExW
0x180003dda  test    eax, eax
0x180003ddc  jnz     loc_180004140
0x180003de2  mov     eax, edi
0x180003de4  test    rbx, rbx
0x180003de7  jz      short loc_180003DF2
0x180003de9  mov     rcx, rbx; hKey
0x180003dec  call    cs:__imp_RegCloseKey
0x180003df2  mov     rbx, [rsp+2310h+var_2298]
0x180003df7  mov     [rbp+2210h+var_2290], rbx
0x180003dfb  test    eax, eax
0x180003dfd  jnz     loc_180004140
0x180003e03  mov     rdx, rsi; unsigned __int16 *
0x180003e06  mov     rcx, r13; this
0x180003e09  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003e0e  xor     edx, edx
0x180003e10  mov     edi, eax
0x180003e12  test    eax, eax
0x180003e14  js      loc_180004149
0x180003e1a  cmp     word ptr [rsi], 3Dh ; '='
0x180003e1e  jnz     short loc_180003E42
0x180003e20  mov     r9, rsi; unsigned __int16 *
0x180003e23  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180003e27  xor     r8d, r8d; unsigned __int16 *
0x180003e2a  mov     rcx, r13; this
0x180003e2d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180003e32  mov     rbx, [rbp+2210h+var_2290]
0x180003e36  xor     edx, edx
0x180003e38  mov     edi, eax
0x180003e3a  test    eax, eax
0x180003e3c  js      loc_180004149
0x180003e42  mov     r12d, [rsp+2310h+var_22A8]
0x180003e47  cmp     word ptr [rsi], 7Bh ; '{'
0x180003e4b  jnz     loc_180003FDE
0x180003e51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003e55  inc     rax
0x180003e58  cmp     [rsi+rax*2], dx
0x180003e5c  jnz     short loc_180003E55
0x180003e5e  cmp     rax, 1
0x180003e62  jnz     loc_180003FDE
0x180003e68  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x180003e6c  mov     r9d, r12d; int
0x180003e6f  mov     rdx, rsi; unsigned __int16 *
0x180003e72  mov     r8, rbx; HKEY
0x180003e75  mov     rcx, r13; this
0x180003e78  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003e7d  mov     edi, eax
0x180003e7f  test    eax, eax
0x180003e81  js      loc_180004149
0x180003e87  mov     rdx, rsi; unsigned __int16 *
0x180003e8a  mov     rcx, r13; this
0x180003e8d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003e92  jmp     loc_180003CC6
0x180003e97  mov     edi, [rbp+2210h+arg_20]
0x180003e9d  xor     eax, eax
0x180003e9f  test    edi, edi
  ... truncated ...
```
