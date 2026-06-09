# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140015bdc`
- end: `0x140016410`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2100`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140015830`
- `0x140015bdc`

## callees

- `0x1400044f8`
- `0x14000d3e0`
- `0x14000e520`
- `0x1400100a4`
- `0x140011b60`
- `0x1400154e0`
- `0x140015bdc`
- `0x1400178cc`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140015e88`
- `ADVAPI32!RegCloseKey` at `0x140015f26`
- `ADVAPI32!RegCloseKey` at `0x140015f7b`
- `ADVAPI32!RegCloseKey` at `0x140015fe9`
- `ADVAPI32!RegCloseKey` at `0x1400160e9`
- `ADVAPI32!RegCloseKey` at `0x14001631e`
- `ADVAPI32!RegCloseKey` at `0x14001637e`
- `ADVAPI32!RegCloseKey` at `0x1400163c1`
- `ADVAPI32!RegCloseKey` at `0x1400163d7`
- `ADVAPI32!RegCloseKey` at `0x140015e88`
- `ADVAPI32!RegCloseKey` at `0x140015f26`
- `ADVAPI32!RegCloseKey` at `0x140015f7b`
- `ADVAPI32!RegCloseKey` at `0x140015fe9`
- `ADVAPI32!RegCloseKey` at `0x1400160e9`
- `ADVAPI32!RegCloseKey` at `0x14001631e`
- `ADVAPI32!RegCloseKey` at `0x14001637e`
- `ADVAPI32!RegCloseKey` at `0x1400163c1`
- `ADVAPI32!RegCloseKey` at `0x1400163d7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140016258`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400162fa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140016258`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400162fa`
- `ADVAPI32!RegOpenKeyExW` at `0x140015e46`
- `ADVAPI32!RegOpenKeyExW` at `0x140015f0c`
- `ADVAPI32!RegOpenKeyExW` at `0x140015f61`
- `ADVAPI32!RegOpenKeyExW` at `0x1400160c8`
- `ADVAPI32!RegOpenKeyExW` at `0x140015e46`
- `ADVAPI32!RegOpenKeyExW` at `0x140015f0c`
- `ADVAPI32!RegOpenKeyExW` at `0x140015f61`
- `ADVAPI32!RegOpenKeyExW` at `0x1400160c8`
- `ADVAPI32!RegCreateKeyExW` at `0x140015fcb`
- `ADVAPI32!RegCreateKeyExW` at `0x140015fcb`
- `ADVAPI32!RegDeleteValueW` at `0x140015e69`
- `ADVAPI32!RegDeleteValueW` at `0x140015e69`
- `KERNEL32!lstrcmpiW` at `0x140015c59`
- `KERNEL32!lstrcmpiW` at `0x140015c72`
- `KERNEL32!lstrcmpiW` at `0x140015cfc`
- `KERNEL32!lstrcmpiW` at `0x140015d6b`
- `KERNEL32!lstrcmpiW` at `0x140015d9f`
- `KERNEL32!lstrcmpiW` at `0x140016281`
- `KERNEL32!lstrcmpiW` at `0x140015c59`
- `KERNEL32!lstrcmpiW` at `0x140015c72`
- `KERNEL32!lstrcmpiW` at `0x140015cfc`
- `KERNEL32!lstrcmpiW` at `0x140015d6b`
- `KERNEL32!lstrcmpiW` at `0x140015d9f`
- `KERNEL32!lstrcmpiW` at `0x140016281`
- `USER32!CharNextW` at `0x140015cca`
- `USER32!CharNextW` at `0x140015ebf`
- `USER32!CharNextW` at `0x140015cca`
- `USER32!CharNextW` at `0x140015ebf`
- `msvcrt!wcsncpy_s` at `0x140016126`
- `msvcrt!wcsncpy_s` at `0x140016126`

## string_xrefs

- `0x140015c68`: `ForceRemove`
- `0x140015d61`: `NoRemove`
- `0x140015c4f`: `Delete`

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
0x140015bdc  push    rbp
0x140015bde  push    rbx
0x140015bdf  push    rsi
0x140015be0  push    rdi
0x140015be1  push    r12
0x140015be3  push    r13
0x140015be5  push    r14
0x140015be7  push    r15
0x140015be9  lea     rbp, [rsp-21D8h]
0x140015bf1  mov     eax, 22D8h
0x140015bf6  call    _alloca_probe
0x140015bfb  sub     rsp, rax
0x140015bfe  mov     rax, cs:__security_cookie
0x140015c05  xor     rax, rsp
0x140015c08  mov     [rbp+2210h+var_50], rax
0x140015c0f  mov     r12d, r9d
0x140015c12  mov     [rsp+2310h+var_22A8], r9d
0x140015c17  mov     r15, r8
0x140015c1a  mov     [rsp+2310h+var_22A0], r8
0x140015c1f  mov     rsi, rdx
0x140015c22  mov     r13, rcx
0x140015c25  xor     eax, eax
0x140015c27  mov     ebx, eax
0x140015c29  mov     [rbp+2210h+var_2290], rax
0x140015c2d  mov     [rbp+2210h+var_2288], rax
0x140015c31  mov     [rbp+2210h+var_2280], rax
0x140015c35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015c3a  mov     edi, eax
0x140015c3c  test    eax, eax
0x140015c3e  jns     short loc_140015C45
0x140015c40  jmp     loc_14001638C
0x140015c45  cmp     word ptr [rsi], 7Dh ; '}'
0x140015c49  jz      loc_140016376
0x140015c4f  lea     rdx, aDelete; "Delete"
0x140015c56  mov     rcx, rsi; lpString1
0x140015c59  call    cs:__imp_lstrcmpiW
0x140015c60  nop     dword ptr [rax+rax+00h]
0x140015c65  mov     r14d, eax
0x140015c68  lea     rdx, aForceremove; "ForceRemove"
0x140015c6f  mov     rcx, rsi; lpString1
0x140015c72  call    cs:__imp_lstrcmpiW
0x140015c79  nop     dword ptr [rax+rax+00h]
0x140015c7e  xor     edi, edi
0x140015c80  test    eax, eax
0x140015c82  jz      short loc_140015C8D
0x140015c84  test    r14d, r14d
0x140015c87  jnz     loc_140015D5B
0x140015c8d  mov     rdx, rsi; unsigned __int16 *
0x140015c90  mov     rcx, r13; this
0x140015c93  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015c98  mov     edi, eax
0x140015c9a  test    eax, eax
0x140015c9c  js      loc_140016376
0x140015ca2  xor     edi, edi
0x140015ca4  test    r12d, r12d
0x140015ca7  jz      loc_140015D5B
0x140015cad  mov     [rbp+2210h+var_2278], rdi
0x140015cb1  mov     [rbp+2210h+var_2270], rdi
0x140015cb5  mov     [rbp+2210h+var_2268], rdi
0x140015cb9  movzx   eax, word ptr [rsi]
0x140015cbc  test    ax, ax
0x140015cbf  jz      short loc_140015CEC
0x140015cc1  mov     rcx, rsi; lpsz
0x140015cc4  cmp     ax, 5Ch ; '\'
0x140015cc8  jz      short loc_140015CE3
0x140015cca  call    cs:__imp_CharNextW
0x140015cd1  nop     dword ptr [rax+rax+00h]
0x140015cd6  mov     rcx, rax
0x140015cd9  movzx   eax, word ptr [rax]
0x140015cdc  test    ax, ax
0x140015cdf  jnz     short loc_140015CC4
0x140015ce1  jmp     short loc_140015CEC
0x140015ce3  test    rcx, rcx
0x140015ce6  jnz     loc_1400163CF
0x140015cec  mov     edx, edi
0x140015cee  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x140015cf5  mov     rdx, [rax+rdx*8]; lpString2
0x140015cf9  mov     rcx, rsi; lpString1
0x140015cfc  call    cs:__imp_lstrcmpiW
0x140015d03  nop     dword ptr [rax+rax+00h]
0x140015d08  test    eax, eax
0x140015d0a  jz      short loc_140015D23
0x140015d0c  inc     edi
0x140015d0e  cmp     edi, 0Ch
0x140015d11  jl      short loc_140015CEC
0x140015d13  mov     [rbp+2210h+var_2278], r15
0x140015d17  mov     rdx, rsi; unsigned __int16 *
0x140015d1a  lea     rcx, [rbp+2210h+var_2278]; this
0x140015d1e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140015d23  xor     edi, edi
0x140015d25  test    r14d, r14d
0x140015d28  jnz     short loc_140015D5B
0x140015d2a  mov     rdx, rsi; unsigned __int16 *
0x140015d2d  mov     rcx, r13; this
0x140015d30  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015d35  mov     edi, eax
0x140015d37  test    eax, eax
0x140015d39  js      loc_140016376
0x140015d3f  mov     rdx, rsi; unsigned __int16 *
0x140015d42  mov     rcx, r13; this
0x140015d45  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140015d4a  mov     edi, eax
0x140015d4c  xor     ecx, ecx
0x140015d4e  test    eax, eax
0x140015d50  js      loc_140016376
0x140015d56  jmp     loc_14001604A
0x140015d5b  mov     r12d, 1
0x140015d61  lea     rdx, aNoremove; "NoRemove"
0x140015d68  mov     rcx, rsi; lpString1
0x140015d6b  call    cs:__imp_lstrcmpiW
0x140015d72  nop     dword ptr [rax+rax+00h]
0x140015d77  test    eax, eax
0x140015d79  jnz     short loc_140015D95
0x140015d7b  mov     r12d, edi
0x140015d7e  mov     rdx, rsi; unsigned __int16 *
0x140015d81  mov     rcx, r13; this
0x140015d84  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015d89  mov     edi, eax
0x140015d8b  test    eax, eax
0x140015d8d  js      loc_140016376
0x140015d93  xor     edi, edi
0x140015d95  lea     rdx, aVal; "Val"
0x140015d9c  mov     rcx, rsi; lpString1
0x140015d9f  call    cs:__imp_lstrcmpiW
0x140015da6  nop     dword ptr [rax+rax+00h]
0x140015dab  test    eax, eax
0x140015dad  jnz     loc_140015EAE
0x140015db3  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x140015dba  mov     rcx, r13; this
0x140015dbd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015dc2  mov     edi, eax
0x140015dc4  test    eax, eax
0x140015dc6  js      loc_140016376
0x140015dcc  mov     rdx, rsi; unsigned __int16 *
0x140015dcf  mov     rcx, r13; this
0x140015dd2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140015dd7  mov     edi, eax
0x140015dd9  test    eax, eax
0x140015ddb  js      loc_140016376
0x140015de1  cmp     word ptr [rsi], 3Dh ; '='
0x140015de5  jnz     loc_1400163CF
0x140015deb  xor     edi, edi
0x140015ded  cmp     [rsp+2310h+var_22A8], edi
0x140015df1  jz      short loc_140015E1C
0x140015df3  mov     [rbp+2210h+var_2270], rdi
0x140015df7  mov     [rbp+2210h+var_2268], rdi
0x140015dfb  mov     [rbp+2210h+var_2278], r15
0x140015dff  mov     r9, rsi; unsigned __int16 *
0x140015e02  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x140015e09  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x140015e0d  mov     rcx, r13; this
0x140015e10  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140015e15  mov     edi, eax
0x140015e17  jmp     loc_14001603B
0x140015e1c  cmp     [rbp+2210h+arg_20], edi
0x140015e22  jnz     short loc_140015E94
0x140015e24  test    r12d, r12d
0x140015e27  jz      short loc_140015E94
0x140015e29  mov     [rsp+2310h+hKey], rdi
0x140015e2e  lea     rax, [rsp+2310h+hKey]
0x140015e33  mov     [rsp+2310h+phkResult], rax; phkResult
0x140015e38  mov     r9d, 20006h; samDesired
0x140015e3e  xor     r8d, r8d; ulOptions
0x140015e41  xor     edx, edx; lpSubKey
0x140015e43  mov     rcx, r15; hKey
0x140015e46  call    cs:__imp_RegOpenKeyExW
0x140015e4d  nop     dword ptr [rax+rax+00h]
0x140015e52  test    eax, eax
0x140015e54  jnz     loc_14001636D
0x140015e5a  mov     r14, [rsp+2310h+hKey]
0x140015e5f  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x140015e66  mov     rcx, r14; hKey
0x140015e69  call    cs:__imp_RegDeleteValueW
0x140015e70  nop     dword ptr [rax+rax+00h]
0x140015e75  test    eax, 0FFFFFFFDh
0x140015e7a  jnz     loc_1400163B0
0x140015e80  test    r14, r14
0x140015e83  jz      short loc_140015E94
0x140015e85  mov     rcx, r14; hKey
0x140015e88  call    cs:__imp_RegCloseKey
0x140015e8f  nop     dword ptr [rax+rax+00h]
0x140015e94  mov     rdx, rsi; unsigned __int16 *
0x140015e97  mov     rcx, r13; this
0x140015e9a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140015e9f  mov     edi, eax
0x140015ea1  test    eax, eax
0x140015ea3  js      loc_140016376
0x140015ea9  jmp     loc_1400161F7
0x140015eae  movzx   eax, word ptr [rsi]
0x140015eb1  test    ax, ax
0x140015eb4  jz      short loc_140015EE1
0x140015eb6  mov     rcx, rsi; lpsz
0x140015eb9  cmp     ax, 5Ch ; '\'
0x140015ebd  jz      short loc_140015ED8
0x140015ebf  call    cs:__imp_CharNextW
0x140015ec6  nop     dword ptr [rax+rax+00h]
0x140015ecb  mov     rcx, rax
0x140015ece  movzx   eax, word ptr [rax]
0x140015ed1  test    ax, ax
0x140015ed4  jnz     short loc_140015EB9
0x140015ed6  jmp     short loc_140015EE1
0x140015ed8  test    rcx, rcx
0x140015edb  jnz     loc_1400163CF
0x140015ee1  cmp     [rsp+2310h+var_22A8], edi
0x140015ee5  jz      loc_14001609E
0x140015eeb  mov     [rsp+2310h+hKey], rdi
0x140015ef0  lea     rax, [rsp+2310h+hKey]
0x140015ef5  mov     [rsp+2310h+phkResult], rax; phkResult
0x140015efa  mov     r14d, 2001Fh
0x140015f00  mov     r9d, r14d; samDesired
0x140015f03  xor     r8d, r8d; ulOptions
0x140015f06  mov     rdx, rsi; lpSubKey
0x140015f09  mov     rcx, r15; hKey
0x140015f0c  call    cs:__imp_RegOpenKeyExW
0x140015f13  nop     dword ptr [rax+rax+00h]
0x140015f18  test    eax, eax
0x140015f1a  jnz     short loc_140015F43
0x140015f1c  mov     eax, edi
0x140015f1e  test    rbx, rbx
0x140015f21  jz      short loc_140015F32
0x140015f23  mov     rcx, rbx; hKey
0x140015f26  call    cs:__imp_RegCloseKey
0x140015f2d  nop     dword ptr [rax+rax+00h]
0x140015f32  mov     rbx, [rsp+2310h+hKey]
0x140015f37  mov     [rbp+2210h+var_2290], rbx
0x140015f3b  test    eax, eax
0x140015f3d  jz      loc_140016006
0x140015f43  mov     [rsp+2310h+hKey], rdi
0x140015f48  lea     rax, [rsp+2310h+hKey]
0x140015f4d  mov     [rsp+2310h+phkResult], rax; phkResult
0x140015f52  mov     r9d, 20019h; samDesired
0x140015f58  xor     r8d, r8d; ulOptions
0x140015f5b  mov     rdx, rsi; lpSubKey
0x140015f5e  mov     rcx, r15; hKey
0x140015f61  call    cs:__imp_RegOpenKeyExW
0x140015f68  nop     dword ptr [rax+rax+00h]
0x140015f6d  test    eax, eax
0x140015f6f  jnz     short loc_140015F94
0x140015f71  mov     eax, edi
0x140015f73  test    rbx, rbx
0x140015f76  jz      short loc_140015F87
0x140015f78  mov     rcx, rbx; hKey
0x140015f7b  call    cs:__imp_RegCloseKey
0x140015f82  nop     dword ptr [rax+rax+00h]
0x140015f87  mov     rbx, [rsp+2310h+hKey]
0x140015f8c  mov     [rbp+2210h+var_2290], rbx
0x140015f90  test    eax, eax
0x140015f92  jz      short loc_140016006
0x140015f94  mov     dword ptr [rsp+2310h+hKey], edi
0x140015f98  mov     [rsp+2310h+var_2298], rdi
0x140015f9d  lea     rax, [rsp+2310h+hKey]
0x140015fa2  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x140015fa7  lea     rax, [rsp+2310h+var_2298]
0x140015fac  mov     [rsp+2310h+var_22D8], rax; phkResult
0x140015fb1  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140015fb6  mov     [rsp+2310h+samDesired], r14d; samDesired
0x140015fbb  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x140015fbf  xor     r9d, r9d; lpClass
0x140015fc2  xor     r8d, r8d; Reserved
0x140015fc5  mov     rdx, rsi; lpSubKey
0x140015fc8  mov     rcx, r15; hKey
0x140015fcb  call    cs:__imp_RegCreateKeyExW
0x140015fd2  nop     dword ptr [rax+rax+00h]
0x140015fd7  test    eax, eax
0x140015fd9  jnz     loc_14001636D
0x140015fdf  mov     eax, edi
0x140015fe1  test    rbx, rbx
0x140015fe4  jz      short loc_140015FF5
0x140015fe6  mov     rcx, rbx; hKey
0x140015fe9  call    cs:__imp_RegCloseKey
0x140015ff0  nop     dword ptr [rax+rax+00h]
0x140015ff5  mov     rbx, [rsp+2310h+var_2298]
0x140015ffa  mov     [rbp+2210h+var_2290], rbx
0x140015ffe  test    eax, eax
0x140016000  jnz     loc_14001636D
0x140016006  mov     rdx, rsi; unsigned __int16 *
0x140016009  mov     rcx, r13; this
0x14001600c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016011  mov     edi, eax
0x140016013  xor     ecx, ecx
0x140016015  test    eax, eax
0x140016017  js      loc_140016376
0x14001601d  cmp     word ptr [rsi], 3Dh ; '='
0x140016021  jnz     short loc_140016045
0x140016023  mov     r9, rsi; unsigned __int16 *
0x140016026  xor     r8d, r8d; unsigned __int16 *
0x140016029  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x14001602d  mov     rcx, r13; this
0x140016030  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140016035  mov     edi, eax
0x140016037  mov     rbx, [rbp+2210h+var_2290]
0x14001603b  test    eax, eax
0x14001603d  js      loc_140016376
0x140016043  xor     ecx, ecx
0x140016045  mov     r12d, [rsp+2310h+var_22A8]
0x14001604a  cmp     word ptr [rsi], 7Bh ; '{'
0x14001604e  jnz     loc_1400161F7
0x140016054  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016058  inc     rax
0x14001605b  cmp     [rsi+rax*2], cx
  ... truncated ...
```
