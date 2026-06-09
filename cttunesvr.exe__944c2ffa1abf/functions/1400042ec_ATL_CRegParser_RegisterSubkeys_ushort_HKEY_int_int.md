# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1400042ec`
- end: `0x140004a89`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140003f98`
- `0x1400042ec`

## callees

- `0x1400025a4`
- `0x140002bfc`
- `0x140002c14`
- `0x140003018`
- `0x140003910`
- `0x140003e48`
- `0x1400042ec`
- `0x140004e78`
- `0x1400065f0`
- `0x140006680`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140004565`
- `ADVAPI32!RegCloseKey` at `0x1400045f1`
- `ADVAPI32!RegCloseKey` at `0x14000463a`
- `ADVAPI32!RegCloseKey` at `0x14000469c`
- `ADVAPI32!RegCloseKey` at `0x14000478c`
- `ADVAPI32!RegCloseKey` at `0x1400049a2`
- `ADVAPI32!RegCloseKey` at `0x140004a01`
- `ADVAPI32!RegCloseKey` at `0x140004a3d`
- `ADVAPI32!RegCloseKey` at `0x140004a4d`
- `ADVAPI32!RegCloseKey` at `0x140004565`
- `ADVAPI32!RegCloseKey` at `0x1400045f1`
- `ADVAPI32!RegCloseKey` at `0x14000463a`
- `ADVAPI32!RegCloseKey` at `0x14000469c`
- `ADVAPI32!RegCloseKey` at `0x14000478c`
- `ADVAPI32!RegCloseKey` at `0x1400049a2`
- `ADVAPI32!RegCloseKey` at `0x140004a01`
- `ADVAPI32!RegCloseKey` at `0x140004a3d`
- `ADVAPI32!RegCloseKey` at `0x140004a4d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400048ea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140004983`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400048ea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140004983`
- `ADVAPI32!RegOpenKeyExW` at `0x14000452f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400045dd`
- `ADVAPI32!RegOpenKeyExW` at `0x140004626`
- `ADVAPI32!RegOpenKeyExW` at `0x140004771`
- `ADVAPI32!RegOpenKeyExW` at `0x14000452f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400045dd`
- `ADVAPI32!RegOpenKeyExW` at `0x140004626`
- `ADVAPI32!RegOpenKeyExW` at `0x140004771`
- `ADVAPI32!RegCreateKeyExW` at `0x140004684`
- `ADVAPI32!RegCreateKeyExW` at `0x140004684`
- `ADVAPI32!RegDeleteValueW` at `0x14000454c`
- `ADVAPI32!RegDeleteValueW` at `0x14000454c`
- `KERNEL32!lstrcmpiW` at `0x14000436a`
- `KERNEL32!lstrcmpiW` at `0x14000437d`
- `KERNEL32!lstrcmpiW` at `0x1400043fb`
- `KERNEL32!lstrcmpiW` at `0x140004464`
- `KERNEL32!lstrcmpiW` at `0x140004492`
- `KERNEL32!lstrcmpiW` at `0x140004911`
- `KERNEL32!lstrcmpiW` at `0x14000436a`
- `KERNEL32!lstrcmpiW` at `0x14000437d`
- `KERNEL32!lstrcmpiW` at `0x1400043fb`
- `KERNEL32!lstrcmpiW` at `0x140004464`
- `KERNEL32!lstrcmpiW` at `0x140004492`
- `KERNEL32!lstrcmpiW` at `0x140004911`
- `USER32!CharNextW` at `0x1400043cf`
- `USER32!CharNextW` at `0x140004596`
- `USER32!CharNextW` at `0x1400043cf`
- `USER32!CharNextW` at `0x140004596`
- `msvcrt!wcsncpy_s` at `0x1400047c3`
- `msvcrt!wcsncpy_s` at `0x1400047c3`

## string_xrefs

- `0x140004370`: `ForceRemove`
- `0x140004454`: `NoRemove`
- `0x140004360`: `Delete`

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
0x1400042ec  push    rbp
0x1400042ee  push    rbx
0x1400042ef  push    rsi
0x1400042f0  push    rdi
0x1400042f1  push    r12
0x1400042f3  push    r13
0x1400042f5  push    r14
0x1400042f7  push    r15
0x1400042f9  lea     rbp, [rsp-21D8h]
0x140004301  mov     eax, 22D8h
0x140004306  call    _alloca_probe
0x14000430b  sub     rsp, rax
0x14000430e  mov     rax, cs:__security_cookie
0x140004315  xor     rax, rsp
0x140004318  mov     [rbp+2210h+var_50], rax
0x14000431f  xor     r14d, r14d
0x140004322  mov     [rsp+2310h+var_22A8], r9d
0x140004327  mov     ebx, r14d
0x14000432a  mov     [rsp+2310h+var_22A0], r8
0x14000432f  mov     [rbp+2210h+var_2290], rbx
0x140004333  mov     r12d, r9d
0x140004336  mov     r15, r8
0x140004339  mov     [rbp+2210h+var_2288], r14
0x14000433d  mov     rsi, rdx
0x140004340  mov     [rbp+2210h+var_2280], r14
0x140004344  mov     r13, rcx
0x140004347  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000434c  mov     edi, eax
0x14000434e  test    eax, eax
0x140004350  js      loc_140004A09
0x140004356  cmp     word ptr [rsi], 7Dh ; '}'
0x14000435a  jz      loc_140004A07
0x140004360  lea     rdx, String2; "Delete"
0x140004367  mov     rcx, rsi; lpString1
0x14000436a  call    cs:__imp_lstrcmpiW
0x140004370  lea     rdx, aForceremove; "ForceRemove"
0x140004377  mov     rcx, rsi; lpString1
0x14000437a  mov     r14d, eax
0x14000437d  call    cs:__imp_lstrcmpiW
0x140004383  xor     edi, edi
0x140004385  test    eax, eax
0x140004387  jz      short loc_140004392
0x140004389  test    r14d, r14d
0x14000438c  jnz     loc_140004454
0x140004392  mov     rdx, rsi; unsigned __int16 *
0x140004395  mov     rcx, r13; this
0x140004398  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000439d  mov     edi, eax
0x14000439f  test    eax, eax
0x1400043a1  js      loc_1400049F9
0x1400043a7  xor     edi, edi
0x1400043a9  test    r12d, r12d
0x1400043ac  jz      loc_140004454
0x1400043b2  movzx   eax, word ptr [rsi]
0x1400043b5  mov     [rbp+2210h+var_2278], rdi
0x1400043b9  mov     [rbp+2210h+var_2270], rdi
0x1400043bd  mov     [rbp+2210h+var_2268], rdi
0x1400043c1  test    ax, ax
0x1400043c4  jz      short loc_1400043EB
0x1400043c6  mov     rcx, rsi; lpsz
0x1400043c9  cmp     ax, 5Ch ; '\'
0x1400043cd  jz      short loc_1400043E2
0x1400043cf  call    cs:__imp_CharNextW
0x1400043d5  mov     rcx, rax
0x1400043d8  movzx   eax, word ptr [rax]
0x1400043db  test    ax, ax
0x1400043de  jnz     short loc_1400043C9
0x1400043e0  jmp     short loc_1400043EB
0x1400043e2  test    rcx, rcx
0x1400043e5  jnz     loc_140004A45
0x1400043eb  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1400043f2  mov     edx, edi
0x1400043f4  mov     rcx, rsi; lpString1
0x1400043f7  mov     rdx, [rax+rdx*8]; lpString2
0x1400043fb  call    cs:__imp_lstrcmpiW
0x140004401  test    eax, eax
0x140004403  jz      short loc_14000441C
0x140004405  inc     edi
0x140004407  cmp     edi, 0Ch
0x14000440a  jl      short loc_1400043EB
0x14000440c  mov     rdx, rsi; unsigned __int16 *
0x14000440f  mov     [rbp+2210h+var_2278], r15
0x140004413  lea     rcx, [rbp+2210h+var_2278]; this
0x140004417  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000441c  xor     edi, edi
0x14000441e  test    r14d, r14d
0x140004421  jnz     short loc_140004454
0x140004423  mov     rdx, rsi; unsigned __int16 *
0x140004426  mov     rcx, r13; this
0x140004429  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000442e  mov     edi, eax
0x140004430  test    eax, eax
0x140004432  js      loc_1400049F9
0x140004438  mov     rdx, rsi; unsigned __int16 *
0x14000443b  mov     rcx, r13; this
0x14000443e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140004443  xor     edx, edx
0x140004445  mov     edi, eax
0x140004447  test    eax, eax
0x140004449  js      loc_1400049F9
0x14000444f  jmp     loc_1400046F7
0x140004454  lea     rdx, aNoremove; "NoRemove"
0x14000445b  mov     rcx, rsi; lpString1
0x14000445e  mov     r12d, 1
0x140004464  call    cs:__imp_lstrcmpiW
0x14000446a  test    eax, eax
0x14000446c  jnz     short loc_140004488
0x14000446e  mov     rdx, rsi; unsigned __int16 *
0x140004471  mov     rcx, r13; this
0x140004474  mov     r12d, edi
0x140004477  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000447c  mov     edi, eax
0x14000447e  test    eax, eax
0x140004480  js      loc_1400049F9
0x140004486  xor     edi, edi
0x140004488  lea     rdx, aVal; "Val"
0x14000448f  mov     rcx, rsi; lpString1
0x140004492  call    cs:__imp_lstrcmpiW
0x140004498  test    eax, eax
0x14000449a  jnz     loc_140004585
0x1400044a0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1400044a7  mov     rcx, r13; this
0x1400044aa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400044af  mov     edi, eax
0x1400044b1  test    eax, eax
0x1400044b3  js      loc_1400049F9
0x1400044b9  mov     rdx, rsi; unsigned __int16 *
0x1400044bc  mov     rcx, r13; this
0x1400044bf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400044c4  xor     edx, edx; lpSubKey
0x1400044c6  mov     edi, eax
0x1400044c8  test    eax, eax
0x1400044ca  js      loc_1400049F9
0x1400044d0  cmp     word ptr [rsi], 3Dh ; '='
0x1400044d4  jnz     loc_140004A45
0x1400044da  cmp     [rsp+2310h+var_22A8], edx
0x1400044de  jz      short loc_140004507
0x1400044e0  mov     [rbp+2210h+var_2270], rdx
0x1400044e4  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1400044eb  mov     [rbp+2210h+var_2268], rdx
0x1400044ef  mov     r9, rsi; unsigned __int16 *
0x1400044f2  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1400044f6  mov     [rbp+2210h+var_2278], r15
0x1400044fa  mov     rcx, r13; this
0x1400044fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140004502  jmp     loc_1400046E6
0x140004507  cmp     [rbp+2210h+arg_20], edx
0x14000450d  jnz     short loc_14000456B
0x14000450f  test    r12d, r12d
0x140004512  jz      short loc_14000456B
0x140004514  lea     rax, [rsp+2310h+hKey]
0x140004519  mov     [rsp+2310h+hKey], rdx
0x14000451e  mov     r9d, 20006h; samDesired
0x140004524  mov     [rsp+2310h+phkResult], rax; phkResult
0x140004529  xor     r8d, r8d; ulOptions
0x14000452c  mov     rcx, r15; hKey
0x14000452f  call    cs:__imp_RegOpenKeyExW
0x140004535  test    eax, eax
0x140004537  jnz     loc_1400049F0
0x14000453d  mov     r14, [rsp+2310h+hKey]
0x140004542  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x140004549  mov     rcx, r14; hKey
0x14000454c  call    cs:__imp_RegDeleteValueW
0x140004552  test    eax, 0FFFFFFFDh
0x140004557  jnz     loc_140004A2C
0x14000455d  test    r14, r14
0x140004560  jz      short loc_14000456B
0x140004562  mov     rcx, r14; hKey
0x140004565  call    cs:__imp_RegCloseKey
0x14000456b  mov     rdx, rsi; unsigned __int16 *
0x14000456e  mov     rcx, r13; this
0x140004571  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140004576  mov     edi, eax
0x140004578  test    eax, eax
0x14000457a  js      loc_1400049F9
0x140004580  jmp     loc_14000488E
0x140004585  movzx   eax, word ptr [rsi]
0x140004588  test    ax, ax
0x14000458b  jz      short loc_1400045B2
0x14000458d  mov     rcx, rsi; lpsz
0x140004590  cmp     ax, 5Ch ; '\'
0x140004594  jz      short loc_1400045A9
0x140004596  call    cs:__imp_CharNextW
0x14000459c  mov     rcx, rax
0x14000459f  movzx   eax, word ptr [rax]
0x1400045a2  test    ax, ax
0x1400045a5  jnz     short loc_140004590
0x1400045a7  jmp     short loc_1400045B2
0x1400045a9  test    rcx, rcx
0x1400045ac  jnz     loc_140004A45
0x1400045b2  cmp     [rsp+2310h+var_22A8], edi
0x1400045b6  jz      loc_140004747
0x1400045bc  lea     rax, [rsp+2310h+hKey]
0x1400045c1  mov     [rsp+2310h+hKey], rdi
0x1400045c6  mov     r14d, 2001Fh
0x1400045cc  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400045d1  mov     r9d, r14d; samDesired
0x1400045d4  xor     r8d, r8d; ulOptions
0x1400045d7  mov     rdx, rsi; lpSubKey
0x1400045da  mov     rcx, r15; hKey
0x1400045dd  call    cs:__imp_RegOpenKeyExW
0x1400045e3  test    eax, eax
0x1400045e5  jnz     short loc_140004608
0x1400045e7  mov     eax, edi
0x1400045e9  test    rbx, rbx
0x1400045ec  jz      short loc_1400045F7
0x1400045ee  mov     rcx, rbx; hKey
0x1400045f1  call    cs:__imp_RegCloseKey
0x1400045f7  mov     rbx, [rsp+2310h+hKey]
0x1400045fc  mov     [rbp+2210h+var_2290], rbx
0x140004600  test    eax, eax
0x140004602  jz      loc_1400046B3
0x140004608  lea     rax, [rsp+2310h+hKey]
0x14000460d  mov     [rsp+2310h+hKey], rdi
0x140004612  mov     r9d, 20019h; samDesired
0x140004618  mov     [rsp+2310h+phkResult], rax; phkResult
0x14000461d  xor     r8d, r8d; ulOptions
0x140004620  mov     rdx, rsi; lpSubKey
0x140004623  mov     rcx, r15; hKey
0x140004626  call    cs:__imp_RegOpenKeyExW
0x14000462c  test    eax, eax
0x14000462e  jnz     short loc_14000464D
0x140004630  mov     eax, edi
0x140004632  test    rbx, rbx
0x140004635  jz      short loc_140004640
0x140004637  mov     rcx, rbx; hKey
0x14000463a  call    cs:__imp_RegCloseKey
0x140004640  mov     rbx, [rsp+2310h+hKey]
0x140004645  mov     [rbp+2210h+var_2290], rbx
0x140004649  test    eax, eax
0x14000464b  jz      short loc_1400046B3
0x14000464d  lea     rax, [rsp+2310h+hKey]
0x140004652  mov     dword ptr [rsp+2310h+hKey], edi
0x140004656  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x14000465b  xor     r9d, r9d; lpClass
0x14000465e  lea     rax, [rsp+2310h+var_2298]
0x140004663  mov     [rsp+2310h+var_2298], rdi
0x140004668  mov     [rsp+2310h+var_22D8], rax; phkResult
0x14000466d  xor     r8d, r8d; Reserved
0x140004670  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140004675  mov     rdx, rsi; lpSubKey
0x140004678  mov     [rsp+2310h+samDesired], r14d; samDesired
0x14000467d  mov     rcx, r15; hKey
0x140004680  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x140004684  call    cs:__imp_RegCreateKeyExW
0x14000468a  test    eax, eax
0x14000468c  jnz     loc_1400049F0
0x140004692  mov     eax, edi
0x140004694  test    rbx, rbx
0x140004697  jz      short loc_1400046A2
0x140004699  mov     rcx, rbx; hKey
0x14000469c  call    cs:__imp_RegCloseKey
0x1400046a2  mov     rbx, [rsp+2310h+var_2298]
0x1400046a7  mov     [rbp+2210h+var_2290], rbx
0x1400046ab  test    eax, eax
0x1400046ad  jnz     loc_1400049F0
0x1400046b3  mov     rdx, rsi; unsigned __int16 *
0x1400046b6  mov     rcx, r13; this
0x1400046b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400046be  xor     edx, edx
0x1400046c0  mov     edi, eax
0x1400046c2  test    eax, eax
0x1400046c4  js      loc_1400049F9
0x1400046ca  cmp     word ptr [rsi], 3Dh ; '='
0x1400046ce  jnz     short loc_1400046F2
0x1400046d0  mov     r9, rsi; unsigned __int16 *
0x1400046d3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1400046d7  xor     r8d, r8d; unsigned __int16 *
0x1400046da  mov     rcx, r13; this
0x1400046dd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1400046e2  mov     rbx, [rbp+2210h+var_2290]
0x1400046e6  xor     edx, edx
0x1400046e8  mov     edi, eax
0x1400046ea  test    eax, eax
0x1400046ec  js      loc_1400049F9
0x1400046f2  mov     r12d, [rsp+2310h+var_22A8]
0x1400046f7  cmp     word ptr [rsi], 7Bh ; '{'
0x1400046fb  jnz     loc_14000488E
0x140004701  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004705  inc     rax
0x140004708  cmp     [rsi+rax*2], dx
0x14000470c  jnz     short loc_140004705
0x14000470e  cmp     rax, 1
0x140004712  jnz     loc_14000488E
0x140004718  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x14000471c  mov     r9d, r12d; int
0x14000471f  mov     rdx, rsi; unsigned __int16 *
0x140004722  mov     r8, rbx; HKEY
0x140004725  mov     rcx, r13; this
0x140004728  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000472d  mov     edi, eax
0x14000472f  test    eax, eax
0x140004731  js      loc_1400049F9
0x140004737  mov     rdx, rsi; unsigned __int16 *
0x14000473a  mov     rcx, r13; this
0x14000473d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004742  jmp     loc_140004576
0x140004747  mov     edi, [rbp+2210h+arg_20]
0x14000474d  xor     eax, eax
0x14000474f  test    edi, edi
  ... truncated ...
```
