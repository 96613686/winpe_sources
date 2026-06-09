# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000460c`
- end: `0x180004da3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004298`
- `0x18000460c`

## callees

- `0x18000296c`
- `0x18000309c`
- `0x1800030b4`
- `0x1800038e8`
- `0x180003b30`
- `0x180004148`
- `0x18000460c`
- `0x180004f84`
- `0x180009a00`
- `0x180009ac0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004aea`
- `msvcrt!wcsncpy_s` at `0x180004aea`
- `ADVAPI32!RegCloseKey` at `0x180004888`
- `ADVAPI32!RegCloseKey` at `0x180004914`
- `ADVAPI32!RegCloseKey` at `0x18000495d`
- `ADVAPI32!RegCloseKey` at `0x1800049bf`
- `ADVAPI32!RegCloseKey` at `0x180004ab3`
- `ADVAPI32!RegCloseKey` at `0x180004cca`
- `ADVAPI32!RegCloseKey` at `0x180004d24`
- `ADVAPI32!RegCloseKey` at `0x180004d60`
- `ADVAPI32!RegCloseKey` at `0x180004d70`
- `ADVAPI32!RegCloseKey` at `0x180004888`
- `ADVAPI32!RegCloseKey` at `0x180004914`
- `ADVAPI32!RegCloseKey` at `0x18000495d`
- `ADVAPI32!RegCloseKey` at `0x1800049bf`
- `ADVAPI32!RegCloseKey` at `0x180004ab3`
- `ADVAPI32!RegCloseKey` at `0x180004cca`
- `ADVAPI32!RegCloseKey` at `0x180004d24`
- `ADVAPI32!RegCloseKey` at `0x180004d60`
- `ADVAPI32!RegCloseKey` at `0x180004d70`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004c16`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004cac`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004c16`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004cac`
- `ADVAPI32!RegCreateKeyExW` at `0x1800049a7`
- `ADVAPI32!RegCreateKeyExW` at `0x1800049a7`
- `ADVAPI32!RegOpenKeyExW` at `0x180004852`
- `ADVAPI32!RegOpenKeyExW` at `0x180004900`
- `ADVAPI32!RegOpenKeyExW` at `0x180004949`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a98`
- `ADVAPI32!RegOpenKeyExW` at `0x180004852`
- `ADVAPI32!RegOpenKeyExW` at `0x180004900`
- `ADVAPI32!RegOpenKeyExW` at `0x180004949`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a98`
- `ADVAPI32!RegDeleteValueW` at `0x18000486f`
- `ADVAPI32!RegDeleteValueW` at `0x18000486f`
- `KERNEL32!lstrcmpiW` at `0x180004689`
- `KERNEL32!lstrcmpiW` at `0x18000469c`
- `KERNEL32!lstrcmpiW` at `0x18000471a`
- `KERNEL32!lstrcmpiW` at `0x180004783`
- `KERNEL32!lstrcmpiW` at `0x1800047b1`
- `KERNEL32!lstrcmpiW` at `0x180004c39`
- `KERNEL32!lstrcmpiW` at `0x180004689`
- `KERNEL32!lstrcmpiW` at `0x18000469c`
- `KERNEL32!lstrcmpiW` at `0x18000471a`
- `KERNEL32!lstrcmpiW` at `0x180004783`
- `KERNEL32!lstrcmpiW` at `0x1800047b1`
- `KERNEL32!lstrcmpiW` at `0x180004c39`
- `USER32!CharNextW` at `0x1800046ee`
- `USER32!CharNextW` at `0x1800048b9`
- `USER32!CharNextW` at `0x1800046ee`
- `USER32!CharNextW` at `0x1800048b9`

## string_xrefs

- `0x180004692`: `ForceRemove`
- `0x180004779`: `NoRemove`
- `0x18000467f`: `Delete`

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
0x18000460c  push    rbp
0x18000460e  push    rbx
0x18000460f  push    rsi
0x180004610  push    rdi
0x180004611  push    r12
0x180004613  push    r13
0x180004615  push    r14
0x180004617  push    r15
0x180004619  lea     rbp, [rsp-21D8h]
0x180004621  mov     eax, 22D8h
0x180004626  call    _alloca_probe
0x18000462b  sub     rsp, rax
0x18000462e  mov     rax, cs:__security_cookie
0x180004635  xor     rax, rsp
0x180004638  mov     [rbp+2210h+var_50], rax
0x18000463f  mov     r12d, r9d
0x180004642  mov     [rsp+2310h+var_22A8], r9d
0x180004647  mov     r15, r8
0x18000464a  mov     [rsp+2310h+var_22A0], r8
0x18000464f  mov     rsi, rdx
0x180004652  mov     r13, rcx
0x180004655  xor     eax, eax
0x180004657  mov     ebx, eax
0x180004659  mov     [rbp+2210h+var_2290], rax
0x18000465d  mov     [rbp+2210h+var_2288], rax
0x180004661  mov     [rbp+2210h+var_2280], rax
0x180004665  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000466a  mov     edi, eax
0x18000466c  test    eax, eax
0x18000466e  jns     short loc_180004675
0x180004670  jmp     loc_180004D2C
0x180004675  cmp     word ptr [rsi], 7Dh ; '}'
0x180004679  jz      loc_180004D1C
0x18000467f  lea     rdx, String2; "Delete"
0x180004686  mov     rcx, rsi; lpString1
0x180004689  call    cs:__imp_lstrcmpiW
0x18000468f  mov     r14d, eax
0x180004692  lea     rdx, aForceremove; "ForceRemove"
0x180004699  mov     rcx, rsi; lpString1
0x18000469c  call    cs:__imp_lstrcmpiW
0x1800046a2  xor     edi, edi
0x1800046a4  test    eax, eax
0x1800046a6  jz      short loc_1800046B1
0x1800046a8  test    r14d, r14d
0x1800046ab  jnz     loc_180004773
0x1800046b1  mov     rdx, rsi; unsigned __int16 *
0x1800046b4  mov     rcx, r13; this
0x1800046b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800046bc  mov     edi, eax
0x1800046be  test    eax, eax
0x1800046c0  js      loc_180004D1C
0x1800046c6  xor     edi, edi
0x1800046c8  test    r12d, r12d
0x1800046cb  jz      loc_180004773
0x1800046d1  mov     [rbp+2210h+var_2278], rdi
0x1800046d5  mov     [rbp+2210h+var_2270], rdi
0x1800046d9  mov     [rbp+2210h+var_2268], rdi
0x1800046dd  movzx   eax, word ptr [rsi]
0x1800046e0  test    ax, ax
0x1800046e3  jz      short loc_18000470A
0x1800046e5  mov     rcx, rsi; lpsz
0x1800046e8  cmp     ax, 5Ch ; '\'
0x1800046ec  jz      short loc_180004701
0x1800046ee  call    cs:__imp_CharNextW
0x1800046f4  mov     rcx, rax
0x1800046f7  movzx   eax, word ptr [rax]
0x1800046fa  test    ax, ax
0x1800046fd  jnz     short loc_1800046E8
0x1800046ff  jmp     short loc_18000470A
0x180004701  test    rcx, rcx
0x180004704  jnz     loc_180004D68
0x18000470a  mov     edx, edi
0x18000470c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004713  mov     rdx, [rax+rdx*8]; lpString2
0x180004717  mov     rcx, rsi; lpString1
0x18000471a  call    cs:__imp_lstrcmpiW
0x180004720  test    eax, eax
0x180004722  jz      short loc_18000473B
0x180004724  inc     edi
0x180004726  cmp     edi, 0Ch
0x180004729  jl      short loc_18000470A
0x18000472b  mov     [rbp+2210h+var_2278], r15
0x18000472f  mov     rdx, rsi; unsigned __int16 *
0x180004732  lea     rcx, [rbp+2210h+var_2278]; this
0x180004736  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000473b  xor     edi, edi
0x18000473d  test    r14d, r14d
0x180004740  jnz     short loc_180004773
0x180004742  mov     rdx, rsi; unsigned __int16 *
0x180004745  mov     rcx, r13; this
0x180004748  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000474d  mov     edi, eax
0x18000474f  test    eax, eax
0x180004751  js      loc_180004D1C
0x180004757  mov     rdx, rsi; unsigned __int16 *
0x18000475a  mov     rcx, r13; this
0x18000475d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004762  mov     edi, eax
0x180004764  xor     ecx, ecx
0x180004766  test    eax, eax
0x180004768  js      loc_180004D1C
0x18000476e  jmp     loc_180004A1A
0x180004773  mov     r12d, 1
0x180004779  lea     rdx, aNoremove; "NoRemove"
0x180004780  mov     rcx, rsi; lpString1
0x180004783  call    cs:__imp_lstrcmpiW
0x180004789  test    eax, eax
0x18000478b  jnz     short loc_1800047A7
0x18000478d  mov     r12d, edi
0x180004790  mov     rdx, rsi; unsigned __int16 *
0x180004793  mov     rcx, r13; this
0x180004796  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000479b  mov     edi, eax
0x18000479d  test    eax, eax
0x18000479f  js      loc_180004D1C
0x1800047a5  xor     edi, edi
0x1800047a7  lea     rdx, aVal; "Val"
0x1800047ae  mov     rcx, rsi; lpString1
0x1800047b1  call    cs:__imp_lstrcmpiW
0x1800047b7  test    eax, eax
0x1800047b9  jnz     loc_1800048A8
0x1800047bf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800047c6  mov     rcx, r13; this
0x1800047c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800047ce  mov     edi, eax
0x1800047d0  test    eax, eax
0x1800047d2  js      loc_180004D1C
0x1800047d8  mov     rdx, rsi; unsigned __int16 *
0x1800047db  mov     rcx, r13; this
0x1800047de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800047e3  mov     edi, eax
0x1800047e5  test    eax, eax
0x1800047e7  js      loc_180004D1C
0x1800047ed  cmp     word ptr [rsi], 3Dh ; '='
0x1800047f1  jnz     loc_180004D68
0x1800047f7  xor     edi, edi
0x1800047f9  cmp     [rsp+2310h+var_22A8], edi
0x1800047fd  jz      short loc_180004828
0x1800047ff  mov     [rbp+2210h+var_2270], rdi
0x180004803  mov     [rbp+2210h+var_2268], rdi
0x180004807  mov     [rbp+2210h+var_2278], r15
0x18000480b  mov     r9, rsi; unsigned __int16 *
0x18000480e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004815  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004819  mov     rcx, r13; this
0x18000481c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004821  mov     edi, eax
0x180004823  jmp     loc_180004A0B
0x180004828  cmp     [rbp+2210h+arg_20], edi
0x18000482e  jnz     short loc_18000488E
0x180004830  test    r12d, r12d
0x180004833  jz      short loc_18000488E
0x180004835  mov     [rsp+2310h+hKey], rdi
0x18000483a  lea     rax, [rsp+2310h+hKey]
0x18000483f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004844  mov     r9d, 20006h; samDesired
0x18000484a  xor     r8d, r8d; ulOptions
0x18000484d  xor     edx, edx; lpSubKey
0x18000484f  mov     rcx, r15; hKey
0x180004852  call    cs:__imp_RegOpenKeyExW
0x180004858  test    eax, eax
0x18000485a  jnz     loc_180004D13
0x180004860  mov     r14, [rsp+2310h+hKey]
0x180004865  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000486c  mov     rcx, r14; hKey
0x18000486f  call    cs:__imp_RegDeleteValueW
0x180004875  test    eax, 0FFFFFFFDh
0x18000487a  jnz     loc_180004D4F
0x180004880  test    r14, r14
0x180004883  jz      short loc_18000488E
0x180004885  mov     rcx, r14; hKey
0x180004888  call    cs:__imp_RegCloseKey
0x18000488e  mov     rdx, rsi; unsigned __int16 *
0x180004891  mov     rcx, r13; this
0x180004894  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004899  mov     edi, eax
0x18000489b  test    eax, eax
0x18000489d  js      loc_180004D1C
0x1800048a3  jmp     loc_180004BB5
0x1800048a8  movzx   eax, word ptr [rsi]
0x1800048ab  test    ax, ax
0x1800048ae  jz      short loc_1800048D5
0x1800048b0  mov     rcx, rsi; lpsz
0x1800048b3  cmp     ax, 5Ch ; '\'
0x1800048b7  jz      short loc_1800048CC
0x1800048b9  call    cs:__imp_CharNextW
0x1800048bf  mov     rcx, rax
0x1800048c2  movzx   eax, word ptr [rax]
0x1800048c5  test    ax, ax
0x1800048c8  jnz     short loc_1800048B3
0x1800048ca  jmp     short loc_1800048D5
0x1800048cc  test    rcx, rcx
0x1800048cf  jnz     loc_180004D68
0x1800048d5  cmp     [rsp+2310h+var_22A8], edi
0x1800048d9  jz      loc_180004A6E
0x1800048df  mov     [rsp+2310h+hKey], rdi
0x1800048e4  lea     rax, [rsp+2310h+hKey]
0x1800048e9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800048ee  mov     r14d, 2001Fh
0x1800048f4  mov     r9d, r14d; samDesired
0x1800048f7  xor     r8d, r8d; ulOptions
0x1800048fa  mov     rdx, rsi; lpSubKey
0x1800048fd  mov     rcx, r15; hKey
0x180004900  call    cs:__imp_RegOpenKeyExW
0x180004906  test    eax, eax
0x180004908  jnz     short loc_18000492B
0x18000490a  mov     eax, edi
0x18000490c  test    rbx, rbx
0x18000490f  jz      short loc_18000491A
0x180004911  mov     rcx, rbx; hKey
0x180004914  call    cs:__imp_RegCloseKey
0x18000491a  mov     rbx, [rsp+2310h+hKey]
0x18000491f  mov     [rbp+2210h+var_2290], rbx
0x180004923  test    eax, eax
0x180004925  jz      loc_1800049D6
0x18000492b  mov     [rsp+2310h+hKey], rdi
0x180004930  lea     rax, [rsp+2310h+hKey]
0x180004935  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000493a  mov     r9d, 20019h; samDesired
0x180004940  xor     r8d, r8d; ulOptions
0x180004943  mov     rdx, rsi; lpSubKey
0x180004946  mov     rcx, r15; hKey
0x180004949  call    cs:__imp_RegOpenKeyExW
0x18000494f  test    eax, eax
0x180004951  jnz     short loc_180004970
0x180004953  mov     eax, edi
0x180004955  test    rbx, rbx
0x180004958  jz      short loc_180004963
0x18000495a  mov     rcx, rbx; hKey
0x18000495d  call    cs:__imp_RegCloseKey
0x180004963  mov     rbx, [rsp+2310h+hKey]
0x180004968  mov     [rbp+2210h+var_2290], rbx
0x18000496c  test    eax, eax
0x18000496e  jz      short loc_1800049D6
0x180004970  mov     dword ptr [rsp+2310h+hKey], edi
0x180004974  mov     [rsp+2310h+var_2298], rdi
0x180004979  lea     rax, [rsp+2310h+hKey]
0x18000497e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004983  lea     rax, [rsp+2310h+var_2298]
0x180004988  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000498d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004992  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180004997  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000499b  xor     r9d, r9d; lpClass
0x18000499e  xor     r8d, r8d; Reserved
0x1800049a1  mov     rdx, rsi; lpSubKey
0x1800049a4  mov     rcx, r15; hKey
0x1800049a7  call    cs:__imp_RegCreateKeyExW
0x1800049ad  test    eax, eax
0x1800049af  jnz     loc_180004D13
0x1800049b5  mov     eax, edi
0x1800049b7  test    rbx, rbx
0x1800049ba  jz      short loc_1800049C5
0x1800049bc  mov     rcx, rbx; hKey
0x1800049bf  call    cs:__imp_RegCloseKey
0x1800049c5  mov     rbx, [rsp+2310h+var_2298]
0x1800049ca  mov     [rbp+2210h+var_2290], rbx
0x1800049ce  test    eax, eax
0x1800049d0  jnz     loc_180004D13
0x1800049d6  mov     rdx, rsi; unsigned __int16 *
0x1800049d9  mov     rcx, r13; this
0x1800049dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800049e1  mov     edi, eax
0x1800049e3  xor     ecx, ecx
0x1800049e5  test    eax, eax
0x1800049e7  js      loc_180004D1C
0x1800049ed  cmp     word ptr [rsi], 3Dh ; '='
0x1800049f1  jnz     short loc_180004A15
0x1800049f3  mov     r9, rsi; unsigned __int16 *
0x1800049f6  xor     r8d, r8d; unsigned __int16 *
0x1800049f9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800049fd  mov     rcx, r13; this
0x180004a00  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004a05  mov     edi, eax
0x180004a07  mov     rbx, [rbp+2210h+var_2290]
0x180004a0b  test    eax, eax
0x180004a0d  js      loc_180004D1C
0x180004a13  xor     ecx, ecx
0x180004a15  mov     r12d, [rsp+2310h+var_22A8]
0x180004a1a  cmp     word ptr [rsi], 7Bh ; '{'
0x180004a1e  jnz     loc_180004BB5
0x180004a24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a28  inc     rax
0x180004a2b  cmp     [rsi+rax*2], cx
0x180004a2f  jnz     short loc_180004A28
0x180004a31  cmp     rax, 1
0x180004a35  jnz     loc_180004BB5
0x180004a3b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180004a43  mov     r9d, r12d; int
0x180004a46  mov     r8, rbx; HKEY
0x180004a49  mov     rdx, rsi; unsigned __int16 *
0x180004a4c  mov     rcx, r13; this
0x180004a4f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004a54  mov     edi, eax
0x180004a56  test    eax, eax
0x180004a58  js      loc_180004D1C
0x180004a5e  mov     rdx, rsi; unsigned __int16 *
0x180004a61  mov     rcx, r13; this
0x180004a64  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a69  jmp     loc_180004899
  ... truncated ...
```
