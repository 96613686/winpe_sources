# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180011384`
- end: `0x180011b1b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180010f18`
- `0x180011384`

## callees

- `0x18000e0bc`
- `0x18000e8f8`
- `0x18000f208`
- `0x18000fd78`
- `0x1800107e0`
- `0x180010dc8`
- `0x180011384`
- `0x180011eb0`
- `0x1800181e0`
- `0x1800182a0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180011862`
- `msvcrt!wcsncpy_s` at `0x180011862`
- `ADVAPI32!RegCloseKey` at `0x180011600`
- `ADVAPI32!RegCloseKey` at `0x18001168c`
- `ADVAPI32!RegCloseKey` at `0x1800116d5`
- `ADVAPI32!RegCloseKey` at `0x180011737`
- `ADVAPI32!RegCloseKey` at `0x18001182b`
- `ADVAPI32!RegCloseKey` at `0x180011a42`
- `ADVAPI32!RegCloseKey` at `0x180011a9c`
- `ADVAPI32!RegCloseKey` at `0x180011ad8`
- `ADVAPI32!RegCloseKey` at `0x180011ae8`
- `ADVAPI32!RegCloseKey` at `0x180011600`
- `ADVAPI32!RegCloseKey` at `0x18001168c`
- `ADVAPI32!RegCloseKey` at `0x1800116d5`
- `ADVAPI32!RegCloseKey` at `0x180011737`
- `ADVAPI32!RegCloseKey` at `0x18001182b`
- `ADVAPI32!RegCloseKey` at `0x180011a42`
- `ADVAPI32!RegCloseKey` at `0x180011a9c`
- `ADVAPI32!RegCloseKey` at `0x180011ad8`
- `ADVAPI32!RegCloseKey` at `0x180011ae8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001198e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011a24`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001198e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011a24`
- `ADVAPI32!RegCreateKeyExW` at `0x18001171f`
- `ADVAPI32!RegCreateKeyExW` at `0x18001171f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800115ca`
- `ADVAPI32!RegOpenKeyExW` at `0x180011678`
- `ADVAPI32!RegOpenKeyExW` at `0x1800116c1`
- `ADVAPI32!RegOpenKeyExW` at `0x180011810`
- `ADVAPI32!RegOpenKeyExW` at `0x1800115ca`
- `ADVAPI32!RegOpenKeyExW` at `0x180011678`
- `ADVAPI32!RegOpenKeyExW` at `0x1800116c1`
- `ADVAPI32!RegOpenKeyExW` at `0x180011810`
- `ADVAPI32!RegDeleteValueW` at `0x1800115e7`
- `ADVAPI32!RegDeleteValueW` at `0x1800115e7`
- `KERNEL32!lstrcmpiW` at `0x180011401`
- `KERNEL32!lstrcmpiW` at `0x180011414`
- `KERNEL32!lstrcmpiW` at `0x180011492`
- `KERNEL32!lstrcmpiW` at `0x1800114fb`
- `KERNEL32!lstrcmpiW` at `0x180011529`
- `KERNEL32!lstrcmpiW` at `0x1800119b1`
- `KERNEL32!lstrcmpiW` at `0x180011401`
- `KERNEL32!lstrcmpiW` at `0x180011414`
- `KERNEL32!lstrcmpiW` at `0x180011492`
- `KERNEL32!lstrcmpiW` at `0x1800114fb`
- `KERNEL32!lstrcmpiW` at `0x180011529`
- `KERNEL32!lstrcmpiW` at `0x1800119b1`
- `USER32!CharNextW` at `0x180011466`
- `USER32!CharNextW` at `0x180011631`
- `USER32!CharNextW` at `0x180011466`
- `USER32!CharNextW` at `0x180011631`

## string_xrefs

- `0x18001140a`: `ForceRemove`
- `0x1800114f1`: `NoRemove`
- `0x1800113f7`: `Delete`

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
0x180011384  push    rbp
0x180011386  push    rbx
0x180011387  push    rsi
0x180011388  push    rdi
0x180011389  push    r12
0x18001138b  push    r13
0x18001138d  push    r14
0x18001138f  push    r15
0x180011391  lea     rbp, [rsp-21D8h]
0x180011399  mov     eax, 22D8h
0x18001139e  call    _alloca_probe
0x1800113a3  sub     rsp, rax
0x1800113a6  mov     rax, cs:__security_cookie
0x1800113ad  xor     rax, rsp
0x1800113b0  mov     [rbp+2210h+var_50], rax
0x1800113b7  mov     r12d, r9d
0x1800113ba  mov     [rsp+2310h+var_22A8], r9d
0x1800113bf  mov     r15, r8
0x1800113c2  mov     [rsp+2310h+var_22A0], r8
0x1800113c7  mov     rsi, rdx
0x1800113ca  mov     r13, rcx
0x1800113cd  xor     eax, eax
0x1800113cf  mov     ebx, eax
0x1800113d1  mov     [rbp+2210h+var_2290], rax
0x1800113d5  mov     [rbp+2210h+var_2288], rax
0x1800113d9  mov     [rbp+2210h+var_2280], rax
0x1800113dd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800113e2  mov     edi, eax
0x1800113e4  test    eax, eax
0x1800113e6  jns     short loc_1800113ED
0x1800113e8  jmp     loc_180011AA4
0x1800113ed  cmp     word ptr [rsi], 7Dh ; '}'
0x1800113f1  jz      loc_180011A94
0x1800113f7  lea     rdx, aDelete; "Delete"
0x1800113fe  mov     rcx, rsi; lpString1
0x180011401  call    cs:__imp_lstrcmpiW
0x180011407  mov     r14d, eax
0x18001140a  lea     rdx, aForceremove; "ForceRemove"
0x180011411  mov     rcx, rsi; lpString1
0x180011414  call    cs:__imp_lstrcmpiW
0x18001141a  xor     edi, edi
0x18001141c  test    eax, eax
0x18001141e  jz      short loc_180011429
0x180011420  test    r14d, r14d
0x180011423  jnz     loc_1800114EB
0x180011429  mov     rdx, rsi; unsigned __int16 *
0x18001142c  mov     rcx, r13; this
0x18001142f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011434  mov     edi, eax
0x180011436  test    eax, eax
0x180011438  js      loc_180011A94
0x18001143e  xor     edi, edi
0x180011440  test    r12d, r12d
0x180011443  jz      loc_1800114EB
0x180011449  mov     [rbp+2210h+var_2278], rdi
0x18001144d  mov     [rbp+2210h+var_2270], rdi
0x180011451  mov     [rbp+2210h+var_2268], rdi
0x180011455  movzx   eax, word ptr [rsi]
0x180011458  test    ax, ax
0x18001145b  jz      short loc_180011482
0x18001145d  mov     rcx, rsi; lpsz
0x180011460  cmp     ax, 5Ch ; '\'
0x180011464  jz      short loc_180011479
0x180011466  call    cs:__imp_CharNextW
0x18001146c  mov     rcx, rax
0x18001146f  movzx   eax, word ptr [rax]
0x180011472  test    ax, ax
0x180011475  jnz     short loc_180011460
0x180011477  jmp     short loc_180011482
0x180011479  test    rcx, rcx
0x18001147c  jnz     loc_180011AE0
0x180011482  mov     edx, edi
0x180011484  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18001148b  mov     rdx, [rax+rdx*8]; lpString2
0x18001148f  mov     rcx, rsi; lpString1
0x180011492  call    cs:__imp_lstrcmpiW
0x180011498  test    eax, eax
0x18001149a  jz      short loc_1800114B3
0x18001149c  inc     edi
0x18001149e  cmp     edi, 0Ch
0x1800114a1  jl      short loc_180011482
0x1800114a3  mov     [rbp+2210h+var_2278], r15
0x1800114a7  mov     rdx, rsi; unsigned __int16 *
0x1800114aa  lea     rcx, [rbp+2210h+var_2278]; this
0x1800114ae  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800114b3  xor     edi, edi
0x1800114b5  test    r14d, r14d
0x1800114b8  jnz     short loc_1800114EB
0x1800114ba  mov     rdx, rsi; unsigned __int16 *
0x1800114bd  mov     rcx, r13; this
0x1800114c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800114c5  mov     edi, eax
0x1800114c7  test    eax, eax
0x1800114c9  js      loc_180011A94
0x1800114cf  mov     rdx, rsi; unsigned __int16 *
0x1800114d2  mov     rcx, r13; this
0x1800114d5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800114da  mov     edi, eax
0x1800114dc  xor     ecx, ecx
0x1800114de  test    eax, eax
0x1800114e0  js      loc_180011A94
0x1800114e6  jmp     loc_180011792
0x1800114eb  mov     r12d, 1
0x1800114f1  lea     rdx, aNoremove; "NoRemove"
0x1800114f8  mov     rcx, rsi; lpString1
0x1800114fb  call    cs:__imp_lstrcmpiW
0x180011501  test    eax, eax
0x180011503  jnz     short loc_18001151F
0x180011505  mov     r12d, edi
0x180011508  mov     rdx, rsi; unsigned __int16 *
0x18001150b  mov     rcx, r13; this
0x18001150e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011513  mov     edi, eax
0x180011515  test    eax, eax
0x180011517  js      loc_180011A94
0x18001151d  xor     edi, edi
0x18001151f  lea     rdx, aVal; "Val"
0x180011526  mov     rcx, rsi; lpString1
0x180011529  call    cs:__imp_lstrcmpiW
0x18001152f  test    eax, eax
0x180011531  jnz     loc_180011620
0x180011537  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18001153e  mov     rcx, r13; this
0x180011541  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011546  mov     edi, eax
0x180011548  test    eax, eax
0x18001154a  js      loc_180011A94
0x180011550  mov     rdx, rsi; unsigned __int16 *
0x180011553  mov     rcx, r13; this
0x180011556  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001155b  mov     edi, eax
0x18001155d  test    eax, eax
0x18001155f  js      loc_180011A94
0x180011565  cmp     word ptr [rsi], 3Dh ; '='
0x180011569  jnz     loc_180011AE0
0x18001156f  xor     edi, edi
0x180011571  cmp     [rsp+2310h+var_22A8], edi
0x180011575  jz      short loc_1800115A0
0x180011577  mov     [rbp+2210h+var_2270], rdi
0x18001157b  mov     [rbp+2210h+var_2268], rdi
0x18001157f  mov     [rbp+2210h+var_2278], r15
0x180011583  mov     r9, rsi; unsigned __int16 *
0x180011586  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18001158d  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180011591  mov     rcx, r13; this
0x180011594  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180011599  mov     edi, eax
0x18001159b  jmp     loc_180011783
0x1800115a0  cmp     [rbp+2210h+arg_20], edi
0x1800115a6  jnz     short loc_180011606
0x1800115a8  test    r12d, r12d
0x1800115ab  jz      short loc_180011606
0x1800115ad  mov     [rsp+2310h+hKey], rdi
0x1800115b2  lea     rax, [rsp+2310h+hKey]
0x1800115b7  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800115bc  mov     r9d, 20006h; samDesired
0x1800115c2  xor     r8d, r8d; ulOptions
0x1800115c5  xor     edx, edx; lpSubKey
0x1800115c7  mov     rcx, r15; hKey
0x1800115ca  call    cs:__imp_RegOpenKeyExW
0x1800115d0  test    eax, eax
0x1800115d2  jnz     loc_180011A8B
0x1800115d8  mov     r14, [rsp+2310h+hKey]
0x1800115dd  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800115e4  mov     rcx, r14; hKey
0x1800115e7  call    cs:__imp_RegDeleteValueW
0x1800115ed  test    eax, 0FFFFFFFDh
0x1800115f2  jnz     loc_180011AC7
0x1800115f8  test    r14, r14
0x1800115fb  jz      short loc_180011606
0x1800115fd  mov     rcx, r14; hKey
0x180011600  call    cs:__imp_RegCloseKey
0x180011606  mov     rdx, rsi; unsigned __int16 *
0x180011609  mov     rcx, r13; this
0x18001160c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180011611  mov     edi, eax
0x180011613  test    eax, eax
0x180011615  js      loc_180011A94
0x18001161b  jmp     loc_18001192D
0x180011620  movzx   eax, word ptr [rsi]
0x180011623  test    ax, ax
0x180011626  jz      short loc_18001164D
0x180011628  mov     rcx, rsi; lpsz
0x18001162b  cmp     ax, 5Ch ; '\'
0x18001162f  jz      short loc_180011644
0x180011631  call    cs:__imp_CharNextW
0x180011637  mov     rcx, rax
0x18001163a  movzx   eax, word ptr [rax]
0x18001163d  test    ax, ax
0x180011640  jnz     short loc_18001162B
0x180011642  jmp     short loc_18001164D
0x180011644  test    rcx, rcx
0x180011647  jnz     loc_180011AE0
0x18001164d  cmp     [rsp+2310h+var_22A8], edi
0x180011651  jz      loc_1800117E6
0x180011657  mov     [rsp+2310h+hKey], rdi
0x18001165c  lea     rax, [rsp+2310h+hKey]
0x180011661  mov     [rsp+2310h+phkResult], rax; phkResult
0x180011666  mov     r14d, 2001Fh
0x18001166c  mov     r9d, r14d; samDesired
0x18001166f  xor     r8d, r8d; ulOptions
0x180011672  mov     rdx, rsi; lpSubKey
0x180011675  mov     rcx, r15; hKey
0x180011678  call    cs:__imp_RegOpenKeyExW
0x18001167e  test    eax, eax
0x180011680  jnz     short loc_1800116A3
0x180011682  mov     eax, edi
0x180011684  test    rbx, rbx
0x180011687  jz      short loc_180011692
0x180011689  mov     rcx, rbx; hKey
0x18001168c  call    cs:__imp_RegCloseKey
0x180011692  mov     rbx, [rsp+2310h+hKey]
0x180011697  mov     [rbp+2210h+var_2290], rbx
0x18001169b  test    eax, eax
0x18001169d  jz      loc_18001174E
0x1800116a3  mov     [rsp+2310h+hKey], rdi
0x1800116a8  lea     rax, [rsp+2310h+hKey]
0x1800116ad  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800116b2  mov     r9d, 20019h; samDesired
0x1800116b8  xor     r8d, r8d; ulOptions
0x1800116bb  mov     rdx, rsi; lpSubKey
0x1800116be  mov     rcx, r15; hKey
0x1800116c1  call    cs:__imp_RegOpenKeyExW
0x1800116c7  test    eax, eax
0x1800116c9  jnz     short loc_1800116E8
0x1800116cb  mov     eax, edi
0x1800116cd  test    rbx, rbx
0x1800116d0  jz      short loc_1800116DB
0x1800116d2  mov     rcx, rbx; hKey
0x1800116d5  call    cs:__imp_RegCloseKey
0x1800116db  mov     rbx, [rsp+2310h+hKey]
0x1800116e0  mov     [rbp+2210h+var_2290], rbx
0x1800116e4  test    eax, eax
0x1800116e6  jz      short loc_18001174E
0x1800116e8  mov     dword ptr [rsp+2310h+hKey], edi
0x1800116ec  mov     [rsp+2310h+var_2298], rdi
0x1800116f1  lea     rax, [rsp+2310h+hKey]
0x1800116f6  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800116fb  lea     rax, [rsp+2310h+var_2298]
0x180011700  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180011705  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001170a  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18001170f  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180011713  xor     r9d, r9d; lpClass
0x180011716  xor     r8d, r8d; Reserved
0x180011719  mov     rdx, rsi; lpSubKey
0x18001171c  mov     rcx, r15; hKey
0x18001171f  call    cs:__imp_RegCreateKeyExW
0x180011725  test    eax, eax
0x180011727  jnz     loc_180011A8B
0x18001172d  mov     eax, edi
0x18001172f  test    rbx, rbx
0x180011732  jz      short loc_18001173D
0x180011734  mov     rcx, rbx; hKey
0x180011737  call    cs:__imp_RegCloseKey
0x18001173d  mov     rbx, [rsp+2310h+var_2298]
0x180011742  mov     [rbp+2210h+var_2290], rbx
0x180011746  test    eax, eax
0x180011748  jnz     loc_180011A8B
0x18001174e  mov     rdx, rsi; unsigned __int16 *
0x180011751  mov     rcx, r13; this
0x180011754  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011759  mov     edi, eax
0x18001175b  xor     ecx, ecx
0x18001175d  test    eax, eax
0x18001175f  js      loc_180011A94
0x180011765  cmp     word ptr [rsi], 3Dh ; '='
0x180011769  jnz     short loc_18001178D
0x18001176b  mov     r9, rsi; unsigned __int16 *
0x18001176e  xor     r8d, r8d; unsigned __int16 *
0x180011771  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180011775  mov     rcx, r13; this
0x180011778  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001177d  mov     edi, eax
0x18001177f  mov     rbx, [rbp+2210h+var_2290]
0x180011783  test    eax, eax
0x180011785  js      loc_180011A94
0x18001178b  xor     ecx, ecx
0x18001178d  mov     r12d, [rsp+2310h+var_22A8]
0x180011792  cmp     word ptr [rsi], 7Bh ; '{'
0x180011796  jnz     loc_18001192D
0x18001179c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800117a0  inc     rax
0x1800117a3  cmp     [rsi+rax*2], cx
0x1800117a7  jnz     short loc_1800117A0
0x1800117a9  cmp     rax, 1
0x1800117ad  jnz     loc_18001192D
0x1800117b3  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x1800117bb  mov     r9d, r12d; int
0x1800117be  mov     r8, rbx; HKEY
0x1800117c1  mov     rdx, rsi; unsigned __int16 *
0x1800117c4  mov     rcx, r13; this
0x1800117c7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800117cc  mov     edi, eax
0x1800117ce  test    eax, eax
0x1800117d0  js      loc_180011A94
0x1800117d6  mov     rdx, rsi; unsigned __int16 *
0x1800117d9  mov     rcx, r13; this
0x1800117dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800117e1  jmp     loc_180011611
  ... truncated ...
```
