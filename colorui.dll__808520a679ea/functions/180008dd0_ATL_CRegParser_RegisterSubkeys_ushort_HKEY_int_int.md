# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180008dd0`
- end: `0x18000956d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180008a7c`
- `0x180008dd0`

## callees

- `0x180004314`
- `0x180004a78`
- `0x180004a90`
- `0x1800052a0`
- `0x180007038`
- `0x18000892c`
- `0x180008dd0`
- `0x180009e1c`
- `0x180018500`
- `0x180018590`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800092a7`
- `msvcrt!wcsncpy_s` at `0x1800092a7`
- `KERNEL32!lstrcmpiW` at `0x180008e4e`
- `KERNEL32!lstrcmpiW` at `0x180008e61`
- `KERNEL32!lstrcmpiW` at `0x180008edf`
- `KERNEL32!lstrcmpiW` at `0x180008f48`
- `KERNEL32!lstrcmpiW` at `0x180008f76`
- `KERNEL32!lstrcmpiW` at `0x1800093f5`
- `KERNEL32!lstrcmpiW` at `0x180008e4e`
- `KERNEL32!lstrcmpiW` at `0x180008e61`
- `KERNEL32!lstrcmpiW` at `0x180008edf`
- `KERNEL32!lstrcmpiW` at `0x180008f48`
- `KERNEL32!lstrcmpiW` at `0x180008f76`
- `KERNEL32!lstrcmpiW` at `0x1800093f5`
- `USER32!CharNextW` at `0x180008eb3`
- `USER32!CharNextW` at `0x18000907a`
- `USER32!CharNextW` at `0x180008eb3`
- `USER32!CharNextW` at `0x18000907a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800093ce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009467`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800093ce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009467`
- `ADVAPI32!RegCreateKeyExW` at `0x180009168`
- `ADVAPI32!RegCreateKeyExW` at `0x180009168`
- `ADVAPI32!RegOpenKeyExW` at `0x180009013`
- `ADVAPI32!RegOpenKeyExW` at `0x1800090c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000910a`
- `ADVAPI32!RegOpenKeyExW` at `0x180009255`
- `ADVAPI32!RegOpenKeyExW` at `0x180009013`
- `ADVAPI32!RegOpenKeyExW` at `0x1800090c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000910a`
- `ADVAPI32!RegOpenKeyExW` at `0x180009255`
- `ADVAPI32!RegDeleteValueW` at `0x180009030`
- `ADVAPI32!RegDeleteValueW` at `0x180009030`
- `ADVAPI32!RegCloseKey` at `0x180009049`
- `ADVAPI32!RegCloseKey` at `0x1800090d5`
- `ADVAPI32!RegCloseKey` at `0x18000911e`
- `ADVAPI32!RegCloseKey` at `0x180009180`
- `ADVAPI32!RegCloseKey` at `0x180009270`
- `ADVAPI32!RegCloseKey` at `0x180009486`
- `ADVAPI32!RegCloseKey` at `0x1800094e5`
- `ADVAPI32!RegCloseKey` at `0x180009521`
- `ADVAPI32!RegCloseKey` at `0x180009531`
- `ADVAPI32!RegCloseKey` at `0x180009049`
- `ADVAPI32!RegCloseKey` at `0x1800090d5`
- `ADVAPI32!RegCloseKey` at `0x18000911e`
- `ADVAPI32!RegCloseKey` at `0x180009180`
- `ADVAPI32!RegCloseKey` at `0x180009270`
- `ADVAPI32!RegCloseKey` at `0x180009486`
- `ADVAPI32!RegCloseKey` at `0x1800094e5`
- `ADVAPI32!RegCloseKey` at `0x180009521`
- `ADVAPI32!RegCloseKey` at `0x180009531`

## string_xrefs

- `0x180008e54`: `ForceRemove`
- `0x180008f38`: `NoRemove`
- `0x180008e44`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
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
  int v32; // r14d
  LSTATUS v33; // eax
  unsigned int v34; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v39[3]; // [rsp+80h] [rbp-80h] BYREF
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
            ATL::CRegKey::RecurseDeleteKey(&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, v6, 0);
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
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, &v40, ValueName, a2);
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
      v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
        v17 = ATL::CRegParser::AddValue((ATL::CRegParser *)this, v39, 0, a2);
        v5 = v39[0];
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
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v5, 0, v28);
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
                ATL::CRegKey::RecurseDeleteKey(v39, Destination);
                v5 = v39[0];
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
0x180008dd0  push    rbp
0x180008dd2  push    rbx
0x180008dd3  push    rsi
0x180008dd4  push    rdi
0x180008dd5  push    r12
0x180008dd7  push    r13
0x180008dd9  push    r14
0x180008ddb  push    r15
0x180008ddd  lea     rbp, [rsp-21D8h]
0x180008de5  mov     eax, 22D8h
0x180008dea  call    _alloca_probe
0x180008def  sub     rsp, rax
0x180008df2  mov     rax, cs:__security_cookie
0x180008df9  xor     rax, rsp
0x180008dfc  mov     [rbp+2210h+var_50], rax
0x180008e03  xor     r14d, r14d
0x180008e06  mov     [rsp+2310h+var_22A8], r9d
0x180008e0b  mov     ebx, r14d
0x180008e0e  mov     [rsp+2310h+var_22A0], r8
0x180008e13  mov     [rbp+2210h+var_2290], rbx
0x180008e17  mov     r12d, r9d
0x180008e1a  mov     r15, r8
0x180008e1d  mov     [rbp+2210h+var_2288], r14
0x180008e21  mov     rsi, rdx
0x180008e24  mov     [rbp+2210h+var_2280], r14
0x180008e28  mov     r13, rcx
0x180008e2b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008e30  mov     edi, eax
0x180008e32  test    eax, eax
0x180008e34  js      loc_1800094ED
0x180008e3a  cmp     word ptr [rsi], 7Dh ; '}'
0x180008e3e  jz      loc_1800094EB
0x180008e44  lea     rdx, String2; "Delete"
0x180008e4b  mov     rcx, rsi; lpString1
0x180008e4e  call    cs:__imp_lstrcmpiW
0x180008e54  lea     rdx, aForceremove; "ForceRemove"
0x180008e5b  mov     rcx, rsi; lpString1
0x180008e5e  mov     r14d, eax
0x180008e61  call    cs:__imp_lstrcmpiW
0x180008e67  xor     edi, edi
0x180008e69  test    eax, eax
0x180008e6b  jz      short loc_180008E76
0x180008e6d  test    r14d, r14d
0x180008e70  jnz     loc_180008F38
0x180008e76  mov     rdx, rsi; unsigned __int16 *
0x180008e79  mov     rcx, r13; this
0x180008e7c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008e81  mov     edi, eax
0x180008e83  test    eax, eax
0x180008e85  js      loc_1800094DD
0x180008e8b  xor     edi, edi
0x180008e8d  test    r12d, r12d
0x180008e90  jz      loc_180008F38
0x180008e96  movzx   eax, word ptr [rsi]
0x180008e99  mov     [rbp+2210h+var_2278], rdi
0x180008e9d  mov     [rbp+2210h+var_2270], rdi
0x180008ea1  mov     [rbp+2210h+var_2268], rdi
0x180008ea5  test    ax, ax
0x180008ea8  jz      short loc_180008ECF
0x180008eaa  mov     rcx, rsi; lpsz
0x180008ead  cmp     ax, 5Ch ; '\'
0x180008eb1  jz      short loc_180008EC6
0x180008eb3  call    cs:__imp_CharNextW
0x180008eb9  mov     rcx, rax
0x180008ebc  movzx   eax, word ptr [rax]
0x180008ebf  test    ax, ax
0x180008ec2  jnz     short loc_180008EAD
0x180008ec4  jmp     short loc_180008ECF
0x180008ec6  test    rcx, rcx
0x180008ec9  jnz     loc_180009529
0x180008ecf  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180008ed6  mov     edx, edi
0x180008ed8  mov     rcx, rsi; lpString1
0x180008edb  mov     rdx, [rax+rdx*8]; lpString2
0x180008edf  call    cs:__imp_lstrcmpiW
0x180008ee5  test    eax, eax
0x180008ee7  jz      short loc_180008F00
0x180008ee9  inc     edi
0x180008eeb  cmp     edi, 0Ch
0x180008eee  jl      short loc_180008ECF
0x180008ef0  mov     rdx, rsi; unsigned __int16 *
0x180008ef3  mov     [rbp+2210h+var_2278], r15
0x180008ef7  lea     rcx, [rbp+2210h+var_2278]; this
0x180008efb  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008f00  xor     edi, edi
0x180008f02  test    r14d, r14d
0x180008f05  jnz     short loc_180008F38
0x180008f07  mov     rdx, rsi; unsigned __int16 *
0x180008f0a  mov     rcx, r13; this
0x180008f0d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f12  mov     edi, eax
0x180008f14  test    eax, eax
0x180008f16  js      loc_1800094DD
0x180008f1c  mov     rdx, rsi; unsigned __int16 *
0x180008f1f  mov     rcx, r13; this
0x180008f22  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008f27  xor     edx, edx
0x180008f29  mov     edi, eax
0x180008f2b  test    eax, eax
0x180008f2d  js      loc_1800094DD
0x180008f33  jmp     loc_1800091DB
0x180008f38  lea     rdx, aNoremove; "NoRemove"
0x180008f3f  mov     rcx, rsi; lpString1
0x180008f42  mov     r12d, 1
0x180008f48  call    cs:__imp_lstrcmpiW
0x180008f4e  test    eax, eax
0x180008f50  jnz     short loc_180008F6C
0x180008f52  mov     rdx, rsi; unsigned __int16 *
0x180008f55  mov     rcx, r13; this
0x180008f58  mov     r12d, edi
0x180008f5b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f60  mov     edi, eax
0x180008f62  test    eax, eax
0x180008f64  js      loc_1800094DD
0x180008f6a  xor     edi, edi
0x180008f6c  lea     rdx, aVal; "Val"
0x180008f73  mov     rcx, rsi; lpString1
0x180008f76  call    cs:__imp_lstrcmpiW
0x180008f7c  test    eax, eax
0x180008f7e  jnz     loc_180009069
0x180008f84  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180008f8b  mov     rcx, r13; this
0x180008f8e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f93  mov     edi, eax
0x180008f95  test    eax, eax
0x180008f97  js      loc_1800094DD
0x180008f9d  mov     rdx, rsi; unsigned __int16 *
0x180008fa0  mov     rcx, r13; this
0x180008fa3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008fa8  xor     edx, edx; lpSubKey
0x180008faa  mov     edi, eax
0x180008fac  test    eax, eax
0x180008fae  js      loc_1800094DD
0x180008fb4  cmp     word ptr [rsi], 3Dh ; '='
0x180008fb8  jnz     loc_180009529
0x180008fbe  cmp     [rsp+2310h+var_22A8], edx
0x180008fc2  jz      short loc_180008FEB
0x180008fc4  mov     [rbp+2210h+var_2270], rdx
0x180008fc8  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180008fcf  mov     [rbp+2210h+var_2268], rdx
0x180008fd3  mov     r9, rsi; unsigned __int16 *
0x180008fd6  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180008fda  mov     [rbp+2210h+var_2278], r15
0x180008fde  mov     rcx, r13; this
0x180008fe1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008fe6  jmp     loc_1800091CA
0x180008feb  cmp     [rbp+2210h+arg_20], edx
0x180008ff1  jnz     short loc_18000904F
0x180008ff3  test    r12d, r12d
0x180008ff6  jz      short loc_18000904F
0x180008ff8  lea     rax, [rsp+2310h+hKey]
0x180008ffd  mov     [rsp+2310h+hKey], rdx
0x180009002  mov     r9d, 20006h; samDesired
0x180009008  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000900d  xor     r8d, r8d; ulOptions
0x180009010  mov     rcx, r15; hKey
0x180009013  call    cs:__imp_RegOpenKeyExW
0x180009019  test    eax, eax
0x18000901b  jnz     loc_1800094D4
0x180009021  mov     r14, [rsp+2310h+hKey]
0x180009026  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000902d  mov     rcx, r14; hKey
0x180009030  call    cs:__imp_RegDeleteValueW
0x180009036  test    eax, 0FFFFFFFDh
0x18000903b  jnz     loc_180009510
0x180009041  test    r14, r14
0x180009044  jz      short loc_18000904F
0x180009046  mov     rcx, r14; hKey
0x180009049  call    cs:__imp_RegCloseKey
0x18000904f  mov     rdx, rsi; unsigned __int16 *
0x180009052  mov     rcx, r13; this
0x180009055  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000905a  mov     edi, eax
0x18000905c  test    eax, eax
0x18000905e  js      loc_1800094DD
0x180009064  jmp     loc_180009372
0x180009069  movzx   eax, word ptr [rsi]
0x18000906c  test    ax, ax
0x18000906f  jz      short loc_180009096
0x180009071  mov     rcx, rsi; lpsz
0x180009074  cmp     ax, 5Ch ; '\'
0x180009078  jz      short loc_18000908D
0x18000907a  call    cs:__imp_CharNextW
0x180009080  mov     rcx, rax
0x180009083  movzx   eax, word ptr [rax]
0x180009086  test    ax, ax
0x180009089  jnz     short loc_180009074
0x18000908b  jmp     short loc_180009096
0x18000908d  test    rcx, rcx
0x180009090  jnz     loc_180009529
0x180009096  cmp     [rsp+2310h+var_22A8], edi
0x18000909a  jz      loc_18000922B
0x1800090a0  lea     rax, [rsp+2310h+hKey]
0x1800090a5  mov     [rsp+2310h+hKey], rdi
0x1800090aa  mov     r14d, 2001Fh
0x1800090b0  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800090b5  mov     r9d, r14d; samDesired
0x1800090b8  xor     r8d, r8d; ulOptions
0x1800090bb  mov     rdx, rsi; lpSubKey
0x1800090be  mov     rcx, r15; hKey
0x1800090c1  call    cs:__imp_RegOpenKeyExW
0x1800090c7  test    eax, eax
0x1800090c9  jnz     short loc_1800090EC
0x1800090cb  mov     eax, edi
0x1800090cd  test    rbx, rbx
0x1800090d0  jz      short loc_1800090DB
0x1800090d2  mov     rcx, rbx; hKey
0x1800090d5  call    cs:__imp_RegCloseKey
0x1800090db  mov     rbx, [rsp+2310h+hKey]
0x1800090e0  mov     [rbp+2210h+var_2290], rbx
0x1800090e4  test    eax, eax
0x1800090e6  jz      loc_180009197
0x1800090ec  lea     rax, [rsp+2310h+hKey]
0x1800090f1  mov     [rsp+2310h+hKey], rdi
0x1800090f6  mov     r9d, 20019h; samDesired
0x1800090fc  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009101  xor     r8d, r8d; ulOptions
0x180009104  mov     rdx, rsi; lpSubKey
0x180009107  mov     rcx, r15; hKey
0x18000910a  call    cs:__imp_RegOpenKeyExW
0x180009110  test    eax, eax
0x180009112  jnz     short loc_180009131
0x180009114  mov     eax, edi
0x180009116  test    rbx, rbx
0x180009119  jz      short loc_180009124
0x18000911b  mov     rcx, rbx; hKey
0x18000911e  call    cs:__imp_RegCloseKey
0x180009124  mov     rbx, [rsp+2310h+hKey]
0x180009129  mov     [rbp+2210h+var_2290], rbx
0x18000912d  test    eax, eax
0x18000912f  jz      short loc_180009197
0x180009131  lea     rax, [rsp+2310h+hKey]
0x180009136  mov     dword ptr [rsp+2310h+hKey], edi
0x18000913a  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000913f  xor     r9d, r9d; lpClass
0x180009142  lea     rax, [rsp+2310h+var_2298]
0x180009147  mov     [rsp+2310h+var_2298], rdi
0x18000914c  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180009151  xor     r8d, r8d; Reserved
0x180009154  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180009159  mov     rdx, rsi; lpSubKey
0x18000915c  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180009161  mov     rcx, r15; hKey
0x180009164  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180009168  call    cs:__imp_RegCreateKeyExW
0x18000916e  test    eax, eax
0x180009170  jnz     loc_1800094D4
0x180009176  mov     eax, edi
0x180009178  test    rbx, rbx
0x18000917b  jz      short loc_180009186
0x18000917d  mov     rcx, rbx; hKey
0x180009180  call    cs:__imp_RegCloseKey
0x180009186  mov     rbx, [rsp+2310h+var_2298]
0x18000918b  mov     [rbp+2210h+var_2290], rbx
0x18000918f  test    eax, eax
0x180009191  jnz     loc_1800094D4
0x180009197  mov     rdx, rsi; unsigned __int16 *
0x18000919a  mov     rcx, r13; this
0x18000919d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091a2  xor     edx, edx
0x1800091a4  mov     edi, eax
0x1800091a6  test    eax, eax
0x1800091a8  js      loc_1800094DD
0x1800091ae  cmp     word ptr [rsi], 3Dh ; '='
0x1800091b2  jnz     short loc_1800091D6
0x1800091b4  mov     r9, rsi; unsigned __int16 *
0x1800091b7  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800091bb  xor     r8d, r8d; unsigned __int16 *
0x1800091be  mov     rcx, r13; this
0x1800091c1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800091c6  mov     rbx, [rbp+2210h+var_2290]
0x1800091ca  xor     edx, edx
0x1800091cc  mov     edi, eax
0x1800091ce  test    eax, eax
0x1800091d0  js      loc_1800094DD
0x1800091d6  mov     r12d, [rsp+2310h+var_22A8]
0x1800091db  cmp     word ptr [rsi], 7Bh ; '{'
0x1800091df  jnz     loc_180009372
0x1800091e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800091e9  inc     rax
0x1800091ec  cmp     [rsi+rax*2], dx
0x1800091f0  jnz     short loc_1800091E9
0x1800091f2  cmp     rax, 1
0x1800091f6  jnz     loc_180009372
0x1800091fc  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x180009200  mov     r9d, r12d; int
0x180009203  mov     rdx, rsi; unsigned __int16 *
0x180009206  mov     r8, rbx; HKEY
0x180009209  mov     rcx, r13; this
0x18000920c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009211  mov     edi, eax
0x180009213  test    eax, eax
0x180009215  js      loc_1800094DD
0x18000921b  mov     rdx, rsi; unsigned __int16 *
0x18000921e  mov     rcx, r13; this
0x180009221  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009226  jmp     loc_18000905A
0x18000922b  mov     edi, [rbp+2210h+arg_20]
0x180009231  xor     eax, eax
0x180009233  test    edi, edi
  ... truncated ...
```
