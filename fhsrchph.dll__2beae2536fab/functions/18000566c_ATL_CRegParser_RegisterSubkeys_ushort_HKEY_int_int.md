# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000566c`
- end: `0x180005e03`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800052f8`
- `0x18000566c`

## callees

- `0x18000278c`
- `0x1800027b4`
- `0x1800037ac`
- `0x180003eb8`
- `0x180004ba0`
- `0x1800051a8`
- `0x18000566c`
- `0x180006074`
- `0x18000ab60`
- `0x18000ac20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005b4a`
- `msvcrt!wcsncpy_s` at `0x180005b4a`
- `ADVAPI32!RegDeleteValueW` at `0x1800058cf`
- `ADVAPI32!RegDeleteValueW` at `0x1800058cf`
- `ADVAPI32!RegCreateKeyExW` at `0x180005a07`
- `ADVAPI32!RegCreateKeyExW` at `0x180005a07`
- `ADVAPI32!RegOpenKeyExW` at `0x1800058b2`
- `ADVAPI32!RegOpenKeyExW` at `0x180005960`
- `ADVAPI32!RegOpenKeyExW` at `0x1800059a9`
- `ADVAPI32!RegOpenKeyExW` at `0x180005af8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800058b2`
- `ADVAPI32!RegOpenKeyExW` at `0x180005960`
- `ADVAPI32!RegOpenKeyExW` at `0x1800059a9`
- `ADVAPI32!RegOpenKeyExW` at `0x180005af8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005c76`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005d0c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005c76`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005d0c`
- `ADVAPI32!RegCloseKey` at `0x1800058e8`
- `ADVAPI32!RegCloseKey` at `0x180005974`
- `ADVAPI32!RegCloseKey` at `0x1800059bd`
- `ADVAPI32!RegCloseKey` at `0x180005a1f`
- `ADVAPI32!RegCloseKey` at `0x180005b13`
- `ADVAPI32!RegCloseKey` at `0x180005d2a`
- `ADVAPI32!RegCloseKey` at `0x180005d84`
- `ADVAPI32!RegCloseKey` at `0x180005dc0`
- `ADVAPI32!RegCloseKey` at `0x180005dd0`
- `ADVAPI32!RegCloseKey` at `0x1800058e8`
- `ADVAPI32!RegCloseKey` at `0x180005974`
- `ADVAPI32!RegCloseKey` at `0x1800059bd`
- `ADVAPI32!RegCloseKey` at `0x180005a1f`
- `ADVAPI32!RegCloseKey` at `0x180005b13`
- `ADVAPI32!RegCloseKey` at `0x180005d2a`
- `ADVAPI32!RegCloseKey` at `0x180005d84`
- `ADVAPI32!RegCloseKey` at `0x180005dc0`
- `ADVAPI32!RegCloseKey` at `0x180005dd0`
- `KERNEL32!lstrcmpiW` at `0x1800056e9`
- `KERNEL32!lstrcmpiW` at `0x1800056fc`
- `KERNEL32!lstrcmpiW` at `0x18000577a`
- `KERNEL32!lstrcmpiW` at `0x1800057e3`
- `KERNEL32!lstrcmpiW` at `0x180005811`
- `KERNEL32!lstrcmpiW` at `0x180005c99`
- `KERNEL32!lstrcmpiW` at `0x1800056e9`
- `KERNEL32!lstrcmpiW` at `0x1800056fc`
- `KERNEL32!lstrcmpiW` at `0x18000577a`
- `KERNEL32!lstrcmpiW` at `0x1800057e3`
- `KERNEL32!lstrcmpiW` at `0x180005811`
- `KERNEL32!lstrcmpiW` at `0x180005c99`
- `USER32!CharNextW` at `0x18000574e`
- `USER32!CharNextW` at `0x180005919`
- `USER32!CharNextW` at `0x18000574e`
- `USER32!CharNextW` at `0x180005919`

## string_xrefs

- `0x1800056f2`: `ForceRemove`
- `0x1800057d9`: `NoRemove`
- `0x1800056df`: `Delete`

## pseudocode

```c
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
0x18000566c  push    rbp
0x18000566e  push    rbx
0x18000566f  push    rsi
0x180005670  push    rdi
0x180005671  push    r12
0x180005673  push    r13
0x180005675  push    r14
0x180005677  push    r15
0x180005679  lea     rbp, [rsp-21D8h]
0x180005681  mov     eax, 22D8h
0x180005686  call    _alloca_probe
0x18000568b  sub     rsp, rax
0x18000568e  mov     rax, cs:__security_cookie
0x180005695  xor     rax, rsp
0x180005698  mov     [rbp+2210h+var_50], rax
0x18000569f  mov     r12d, r9d
0x1800056a2  mov     [rsp+2310h+var_22A8], r9d
0x1800056a7  mov     r15, r8
0x1800056aa  mov     [rsp+2310h+var_22A0], r8
0x1800056af  mov     rsi, rdx
0x1800056b2  mov     r13, rcx
0x1800056b5  xor     eax, eax
0x1800056b7  mov     ebx, eax
0x1800056b9  mov     [rbp+2210h+var_2290], rax
0x1800056bd  mov     [rbp+2210h+var_2288], rax
0x1800056c1  mov     [rbp+2210h+var_2280], rax
0x1800056c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800056ca  mov     edi, eax
0x1800056cc  test    eax, eax
0x1800056ce  jns     short loc_1800056D5
0x1800056d0  jmp     loc_180005D8C
0x1800056d5  cmp     word ptr [rsi], 7Dh ; '}'
0x1800056d9  jz      loc_180005D7C
0x1800056df  lea     rdx, String2; "Delete"
0x1800056e6  mov     rcx, rsi; lpString1
0x1800056e9  call    cs:__imp_lstrcmpiW
0x1800056ef  mov     r14d, eax
0x1800056f2  lea     rdx, aForceremove; "ForceRemove"
0x1800056f9  mov     rcx, rsi; lpString1
0x1800056fc  call    cs:__imp_lstrcmpiW
0x180005702  xor     edi, edi
0x180005704  test    eax, eax
0x180005706  jz      short loc_180005711
0x180005708  test    r14d, r14d
0x18000570b  jnz     loc_1800057D3
0x180005711  mov     rdx, rsi; unsigned __int16 *
0x180005714  mov     rcx, r13; this
0x180005717  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000571c  mov     edi, eax
0x18000571e  test    eax, eax
0x180005720  js      loc_180005D7C
0x180005726  xor     edi, edi
0x180005728  test    r12d, r12d
0x18000572b  jz      loc_1800057D3
0x180005731  mov     [rbp+2210h+var_2278], rdi
0x180005735  mov     [rbp+2210h+var_2270], rdi
0x180005739  mov     [rbp+2210h+var_2268], rdi
0x18000573d  movzx   eax, word ptr [rsi]
0x180005740  test    ax, ax
0x180005743  jz      short loc_18000576A
0x180005745  mov     rcx, rsi; lpsz
0x180005748  cmp     ax, 5Ch ; '\'
0x18000574c  jz      short loc_180005761
0x18000574e  call    cs:__imp_CharNextW
0x180005754  mov     rcx, rax
0x180005757  movzx   eax, word ptr [rax]
0x18000575a  test    ax, ax
0x18000575d  jnz     short loc_180005748
0x18000575f  jmp     short loc_18000576A
0x180005761  test    rcx, rcx
0x180005764  jnz     loc_180005DC8
0x18000576a  mov     edx, edi
0x18000576c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180005773  mov     rdx, [rax+rdx*8]; lpString2
0x180005777  mov     rcx, rsi; lpString1
0x18000577a  call    cs:__imp_lstrcmpiW
0x180005780  test    eax, eax
0x180005782  jz      short loc_18000579B
0x180005784  inc     edi
0x180005786  cmp     edi, 0Ch
0x180005789  jl      short loc_18000576A
0x18000578b  mov     [rbp+2210h+var_2278], r15
0x18000578f  mov     rdx, rsi; unsigned __int16 *
0x180005792  lea     rcx, [rbp+2210h+var_2278]; this
0x180005796  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000579b  xor     edi, edi
0x18000579d  test    r14d, r14d
0x1800057a0  jnz     short loc_1800057D3
0x1800057a2  mov     rdx, rsi; unsigned __int16 *
0x1800057a5  mov     rcx, r13; this
0x1800057a8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800057ad  mov     edi, eax
0x1800057af  test    eax, eax
0x1800057b1  js      loc_180005D7C
0x1800057b7  mov     rdx, rsi; unsigned __int16 *
0x1800057ba  mov     rcx, r13; this
0x1800057bd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800057c2  mov     edi, eax
0x1800057c4  xor     ecx, ecx
0x1800057c6  test    eax, eax
0x1800057c8  js      loc_180005D7C
0x1800057ce  jmp     loc_180005A7A
0x1800057d3  mov     r12d, 1
0x1800057d9  lea     rdx, aNoremove; "NoRemove"
0x1800057e0  mov     rcx, rsi; lpString1
0x1800057e3  call    cs:__imp_lstrcmpiW
0x1800057e9  test    eax, eax
0x1800057eb  jnz     short loc_180005807
0x1800057ed  mov     r12d, edi
0x1800057f0  mov     rdx, rsi; unsigned __int16 *
0x1800057f3  mov     rcx, r13; this
0x1800057f6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800057fb  mov     edi, eax
0x1800057fd  test    eax, eax
0x1800057ff  js      loc_180005D7C
0x180005805  xor     edi, edi
0x180005807  lea     rdx, aVal; "Val"
0x18000580e  mov     rcx, rsi; lpString1
0x180005811  call    cs:__imp_lstrcmpiW
0x180005817  test    eax, eax
0x180005819  jnz     loc_180005908
0x18000581f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005826  mov     rcx, r13; this
0x180005829  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000582e  mov     edi, eax
0x180005830  test    eax, eax
0x180005832  js      loc_180005D7C
0x180005838  mov     rdx, rsi; unsigned __int16 *
0x18000583b  mov     rcx, r13; this
0x18000583e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005843  mov     edi, eax
0x180005845  test    eax, eax
0x180005847  js      loc_180005D7C
0x18000584d  cmp     word ptr [rsi], 3Dh ; '='
0x180005851  jnz     loc_180005DC8
0x180005857  xor     edi, edi
0x180005859  cmp     [rsp+2310h+var_22A8], edi
0x18000585d  jz      short loc_180005888
0x18000585f  mov     [rbp+2210h+var_2270], rdi
0x180005863  mov     [rbp+2210h+var_2268], rdi
0x180005867  mov     [rbp+2210h+var_2278], r15
0x18000586b  mov     r9, rsi; unsigned __int16 *
0x18000586e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005875  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005879  mov     rcx, r13; this
0x18000587c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005881  mov     edi, eax
0x180005883  jmp     loc_180005A6B
0x180005888  cmp     [rbp+2210h+arg_20], edi
0x18000588e  jnz     short loc_1800058EE
0x180005890  test    r12d, r12d
0x180005893  jz      short loc_1800058EE
0x180005895  mov     [rsp+2310h+hKey], rdi
0x18000589a  lea     rax, [rsp+2310h+hKey]
0x18000589f  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800058a4  mov     r9d, 20006h; samDesired
0x1800058aa  xor     r8d, r8d; ulOptions
0x1800058ad  xor     edx, edx; lpSubKey
0x1800058af  mov     rcx, r15; hKey
0x1800058b2  call    cs:__imp_RegOpenKeyExW
0x1800058b8  test    eax, eax
0x1800058ba  jnz     loc_180005D73
0x1800058c0  mov     r14, [rsp+2310h+hKey]
0x1800058c5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800058cc  mov     rcx, r14; hKey
0x1800058cf  call    cs:__imp_RegDeleteValueW
0x1800058d5  test    eax, 0FFFFFFFDh
0x1800058da  jnz     loc_180005DAF
0x1800058e0  test    r14, r14
0x1800058e3  jz      short loc_1800058EE
0x1800058e5  mov     rcx, r14; hKey
0x1800058e8  call    cs:__imp_RegCloseKey
0x1800058ee  mov     rdx, rsi; unsigned __int16 *
0x1800058f1  mov     rcx, r13; this
0x1800058f4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800058f9  mov     edi, eax
0x1800058fb  test    eax, eax
0x1800058fd  js      loc_180005D7C
0x180005903  jmp     loc_180005C15
0x180005908  movzx   eax, word ptr [rsi]
0x18000590b  test    ax, ax
0x18000590e  jz      short loc_180005935
0x180005910  mov     rcx, rsi; lpsz
0x180005913  cmp     ax, 5Ch ; '\'
0x180005917  jz      short loc_18000592C
0x180005919  call    cs:__imp_CharNextW
0x18000591f  mov     rcx, rax
0x180005922  movzx   eax, word ptr [rax]
0x180005925  test    ax, ax
0x180005928  jnz     short loc_180005913
0x18000592a  jmp     short loc_180005935
0x18000592c  test    rcx, rcx
0x18000592f  jnz     loc_180005DC8
0x180005935  cmp     [rsp+2310h+var_22A8], edi
0x180005939  jz      loc_180005ACE
0x18000593f  mov     [rsp+2310h+hKey], rdi
0x180005944  lea     rax, [rsp+2310h+hKey]
0x180005949  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000594e  mov     r14d, 2001Fh
0x180005954  mov     r9d, r14d; samDesired
0x180005957  xor     r8d, r8d; ulOptions
0x18000595a  mov     rdx, rsi; lpSubKey
0x18000595d  mov     rcx, r15; hKey
0x180005960  call    cs:__imp_RegOpenKeyExW
0x180005966  test    eax, eax
0x180005968  jnz     short loc_18000598B
0x18000596a  mov     eax, edi
0x18000596c  test    rbx, rbx
0x18000596f  jz      short loc_18000597A
0x180005971  mov     rcx, rbx; hKey
0x180005974  call    cs:__imp_RegCloseKey
0x18000597a  mov     rbx, [rsp+2310h+hKey]
0x18000597f  mov     [rbp+2210h+var_2290], rbx
0x180005983  test    eax, eax
0x180005985  jz      loc_180005A36
0x18000598b  mov     [rsp+2310h+hKey], rdi
0x180005990  lea     rax, [rsp+2310h+hKey]
0x180005995  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000599a  mov     r9d, 20019h; samDesired
0x1800059a0  xor     r8d, r8d; ulOptions
0x1800059a3  mov     rdx, rsi; lpSubKey
0x1800059a6  mov     rcx, r15; hKey
0x1800059a9  call    cs:__imp_RegOpenKeyExW
0x1800059af  test    eax, eax
0x1800059b1  jnz     short loc_1800059D0
0x1800059b3  mov     eax, edi
0x1800059b5  test    rbx, rbx
0x1800059b8  jz      short loc_1800059C3
0x1800059ba  mov     rcx, rbx; hKey
0x1800059bd  call    cs:__imp_RegCloseKey
0x1800059c3  mov     rbx, [rsp+2310h+hKey]
0x1800059c8  mov     [rbp+2210h+var_2290], rbx
0x1800059cc  test    eax, eax
0x1800059ce  jz      short loc_180005A36
0x1800059d0  mov     dword ptr [rsp+2310h+hKey], edi
0x1800059d4  mov     [rsp+2310h+var_2298], rdi
0x1800059d9  lea     rax, [rsp+2310h+hKey]
0x1800059de  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800059e3  lea     rax, [rsp+2310h+var_2298]
0x1800059e8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800059ed  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800059f2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800059f7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800059fb  xor     r9d, r9d; lpClass
0x1800059fe  xor     r8d, r8d; Reserved
0x180005a01  mov     rdx, rsi; lpSubKey
0x180005a04  mov     rcx, r15; hKey
0x180005a07  call    cs:__imp_RegCreateKeyExW
0x180005a0d  test    eax, eax
0x180005a0f  jnz     loc_180005D73
0x180005a15  mov     eax, edi
0x180005a17  test    rbx, rbx
0x180005a1a  jz      short loc_180005A25
0x180005a1c  mov     rcx, rbx; hKey
0x180005a1f  call    cs:__imp_RegCloseKey
0x180005a25  mov     rbx, [rsp+2310h+var_2298]
0x180005a2a  mov     [rbp+2210h+var_2290], rbx
0x180005a2e  test    eax, eax
0x180005a30  jnz     loc_180005D73
0x180005a36  mov     rdx, rsi; unsigned __int16 *
0x180005a39  mov     rcx, r13; this
0x180005a3c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a41  mov     edi, eax
0x180005a43  xor     ecx, ecx
0x180005a45  test    eax, eax
0x180005a47  js      loc_180005D7C
0x180005a4d  cmp     word ptr [rsi], 3Dh ; '='
0x180005a51  jnz     short loc_180005A75
0x180005a53  mov     r9, rsi; unsigned __int16 *
0x180005a56  xor     r8d, r8d; unsigned __int16 *
0x180005a59  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180005a5d  mov     rcx, r13; this
0x180005a60  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005a65  mov     edi, eax
0x180005a67  mov     rbx, [rbp+2210h+var_2290]
0x180005a6b  test    eax, eax
0x180005a6d  js      loc_180005D7C
0x180005a73  xor     ecx, ecx
0x180005a75  mov     r12d, [rsp+2310h+var_22A8]
0x180005a7a  cmp     word ptr [rsi], 7Bh ; '{'
0x180005a7e  jnz     loc_180005C15
0x180005a84  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a88  inc     rax
0x180005a8b  cmp     [rsi+rax*2], cx
0x180005a8f  jnz     short loc_180005A88
0x180005a91  cmp     rax, 1
0x180005a95  jnz     loc_180005C15
0x180005a9b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180005aa3  mov     r9d, r12d; int
0x180005aa6  mov     r8, rbx; HKEY
0x180005aa9  mov     rdx, rsi; unsigned __int16 *
0x180005aac  mov     rcx, r13; this
0x180005aaf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005ab4  mov     edi, eax
0x180005ab6  test    eax, eax
0x180005ab8  js      loc_180005D7C
0x180005abe  mov     rdx, rsi; unsigned __int16 *
0x180005ac1  mov     rcx, r13; this
0x180005ac4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005ac9  jmp     loc_1800058F9
  ... truncated ...
```
