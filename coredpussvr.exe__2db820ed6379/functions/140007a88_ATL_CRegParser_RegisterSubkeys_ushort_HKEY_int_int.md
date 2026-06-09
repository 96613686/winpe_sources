# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140007a88`
- end: `0x1400082bc`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2100`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1400076dc`
- `0x140007a88`

## callees

- `0x140001500`
- `0x1400061bc`
- `0x140006928`
- `0x140006940`
- `0x140006d28`
- `0x140006f40`
- `0x14000756c`
- `0x140007a88`
- `0x14000836c`
- `0x140009030`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140007fd2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140007fd2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007b76`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007d6b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007b76`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007d6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007e77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007e77`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008104`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400081a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140008104`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400081a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400081ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000822a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000826d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008283`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400081ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000822a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000826d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008283`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140007d15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140007d15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007db8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007e0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007f74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007db8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007e0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007f74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007b05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007b1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007ba8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007c17`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007c4b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000812d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007b05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007b1e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007ba8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007c17`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140007c4b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000812d`

## string_xrefs

- `0x140007b14`: `ForceRemove`
- `0x140007c0d`: `NoRemove`
- `0x140007afb`: `Delete`

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
  int v29; // eax
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
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
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
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, String1);
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
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v38, String1);
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
0x140007a88  push    rbp
0x140007a8a  push    rbx
0x140007a8b  push    rsi
0x140007a8c  push    rdi
0x140007a8d  push    r12
0x140007a8f  push    r13
0x140007a91  push    r14
0x140007a93  push    r15
0x140007a95  lea     rbp, [rsp-21D8h]
0x140007a9d  mov     eax, 22D8h
0x140007aa2  call    _alloca_probe
0x140007aa7  sub     rsp, rax
0x140007aaa  mov     rax, cs:__security_cookie
0x140007ab1  xor     rax, rsp
0x140007ab4  mov     [rbp+2210h+var_50], rax
0x140007abb  mov     r12d, r9d
0x140007abe  mov     [rsp+2310h+var_22A8], r9d
0x140007ac3  mov     r15, r8
0x140007ac6  mov     [rsp+2310h+var_22A0], r8
0x140007acb  mov     rsi, rdx
0x140007ace  mov     r13, rcx
0x140007ad1  xor     eax, eax
0x140007ad3  mov     ebx, eax
0x140007ad5  mov     [rbp+2210h+var_2290], rax
0x140007ad9  mov     [rbp+2210h+var_2288], rax
0x140007add  mov     [rbp+2210h+var_2280], rax
0x140007ae1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007ae6  mov     edi, eax
0x140007ae8  test    eax, eax
0x140007aea  jns     short loc_140007AF1
0x140007aec  jmp     loc_140008238
0x140007af1  cmp     word ptr [rsi], 7Dh ; '}'
0x140007af5  jz      loc_140008222
0x140007afb  lea     rdx, String2; "Delete"
0x140007b02  mov     rcx, rsi; lpString1
0x140007b05  call    cs:__imp_lstrcmpiW
0x140007b0c  nop     dword ptr [rax+rax+00h]
0x140007b11  mov     r14d, eax
0x140007b14  lea     rdx, aForceremove; "ForceRemove"
0x140007b1b  mov     rcx, rsi; lpString1
0x140007b1e  call    cs:__imp_lstrcmpiW
0x140007b25  nop     dword ptr [rax+rax+00h]
0x140007b2a  xor     edi, edi
0x140007b2c  test    eax, eax
0x140007b2e  jz      short loc_140007B39
0x140007b30  test    r14d, r14d
0x140007b33  jnz     loc_140007C07
0x140007b39  mov     rdx, rsi; unsigned __int16 *
0x140007b3c  mov     rcx, r13; this
0x140007b3f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007b44  mov     edi, eax
0x140007b46  test    eax, eax
0x140007b48  js      loc_140008222
0x140007b4e  xor     edi, edi
0x140007b50  test    r12d, r12d
0x140007b53  jz      loc_140007C07
0x140007b59  mov     [rbp+2210h+var_2278], rdi
0x140007b5d  mov     [rbp+2210h+var_2270], rdi
0x140007b61  mov     [rbp+2210h+var_2268], rdi
0x140007b65  movzx   eax, word ptr [rsi]
0x140007b68  test    ax, ax
0x140007b6b  jz      short loc_140007B98
0x140007b6d  mov     rcx, rsi; lpsz
0x140007b70  cmp     ax, 5Ch ; '\'
0x140007b74  jz      short loc_140007B8F
0x140007b76  call    cs:__imp_CharNextW
0x140007b7d  nop     dword ptr [rax+rax+00h]
0x140007b82  mov     rcx, rax
0x140007b85  movzx   eax, word ptr [rax]
0x140007b88  test    ax, ax
0x140007b8b  jnz     short loc_140007B70
0x140007b8d  jmp     short loc_140007B98
0x140007b8f  test    rcx, rcx
0x140007b92  jnz     loc_14000827B
0x140007b98  mov     edx, edi
0x140007b9a  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x140007ba1  mov     rdx, [rax+rdx*8]; lpString2
0x140007ba5  mov     rcx, rsi; lpString1
0x140007ba8  call    cs:__imp_lstrcmpiW
0x140007baf  nop     dword ptr [rax+rax+00h]
0x140007bb4  test    eax, eax
0x140007bb6  jz      short loc_140007BCF
0x140007bb8  inc     edi
0x140007bba  cmp     edi, 0Ch
0x140007bbd  jl      short loc_140007B98
0x140007bbf  mov     [rbp+2210h+var_2278], r15
0x140007bc3  mov     rdx, rsi; unsigned __int16 *
0x140007bc6  lea     rcx, [rbp+2210h+var_2278]; this
0x140007bca  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140007bcf  xor     edi, edi
0x140007bd1  test    r14d, r14d
0x140007bd4  jnz     short loc_140007C07
0x140007bd6  mov     rdx, rsi; unsigned __int16 *
0x140007bd9  mov     rcx, r13; this
0x140007bdc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007be1  mov     edi, eax
0x140007be3  test    eax, eax
0x140007be5  js      loc_140008222
0x140007beb  mov     rdx, rsi; unsigned __int16 *
0x140007bee  mov     rcx, r13; this
0x140007bf1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140007bf6  mov     edi, eax
0x140007bf8  xor     ecx, ecx
0x140007bfa  test    eax, eax
0x140007bfc  js      loc_140008222
0x140007c02  jmp     loc_140007EF6
0x140007c07  mov     r12d, 1
0x140007c0d  lea     rdx, aNoremove; "NoRemove"
0x140007c14  mov     rcx, rsi; lpString1
0x140007c17  call    cs:__imp_lstrcmpiW
0x140007c1e  nop     dword ptr [rax+rax+00h]
0x140007c23  test    eax, eax
0x140007c25  jnz     short loc_140007C41
0x140007c27  mov     r12d, edi
0x140007c2a  mov     rdx, rsi; unsigned __int16 *
0x140007c2d  mov     rcx, r13; this
0x140007c30  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007c35  mov     edi, eax
0x140007c37  test    eax, eax
0x140007c39  js      loc_140008222
0x140007c3f  xor     edi, edi
0x140007c41  lea     rdx, aVal; "Val"
0x140007c48  mov     rcx, rsi; lpString1
0x140007c4b  call    cs:__imp_lstrcmpiW
0x140007c52  nop     dword ptr [rax+rax+00h]
0x140007c57  test    eax, eax
0x140007c59  jnz     loc_140007D5A
0x140007c5f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x140007c66  mov     rcx, r13; this
0x140007c69  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007c6e  mov     edi, eax
0x140007c70  test    eax, eax
0x140007c72  js      loc_140008222
0x140007c78  mov     rdx, rsi; unsigned __int16 *
0x140007c7b  mov     rcx, r13; this
0x140007c7e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007c83  mov     edi, eax
0x140007c85  test    eax, eax
0x140007c87  js      loc_140008222
0x140007c8d  cmp     word ptr [rsi], 3Dh ; '='
0x140007c91  jnz     loc_14000827B
0x140007c97  xor     edi, edi
0x140007c99  cmp     [rsp+2310h+var_22A8], edi
0x140007c9d  jz      short loc_140007CC8
0x140007c9f  mov     [rbp+2210h+var_2270], rdi
0x140007ca3  mov     [rbp+2210h+var_2268], rdi
0x140007ca7  mov     [rbp+2210h+var_2278], r15
0x140007cab  mov     r9, rsi; unsigned __int16 *
0x140007cae  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x140007cb5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x140007cb9  mov     rcx, r13; this
0x140007cbc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140007cc1  mov     edi, eax
0x140007cc3  jmp     loc_140007EE7
0x140007cc8  cmp     [rbp+2210h+arg_20], edi
0x140007cce  jnz     short loc_140007D40
0x140007cd0  test    r12d, r12d
0x140007cd3  jz      short loc_140007D40
0x140007cd5  mov     [rsp+2310h+hKey], rdi
0x140007cda  lea     rax, [rsp+2310h+hKey]
0x140007cdf  mov     [rsp+2310h+phkResult], rax; phkResult
0x140007ce4  mov     r9d, 20006h; samDesired
0x140007cea  xor     r8d, r8d; ulOptions
0x140007ced  xor     edx, edx; lpSubKey
0x140007cef  mov     rcx, r15; hKey
0x140007cf2  call    cs:__imp_RegOpenKeyExW
0x140007cf9  nop     dword ptr [rax+rax+00h]
0x140007cfe  test    eax, eax
0x140007d00  jnz     loc_140008219
0x140007d06  mov     r14, [rsp+2310h+hKey]
0x140007d0b  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x140007d12  mov     rcx, r14; hKey
0x140007d15  call    cs:__imp_RegDeleteValueW
0x140007d1c  nop     dword ptr [rax+rax+00h]
0x140007d21  test    eax, 0FFFFFFFDh
0x140007d26  jnz     loc_14000825C
0x140007d2c  test    r14, r14
0x140007d2f  jz      short loc_140007D40
0x140007d31  mov     rcx, r14; hKey
0x140007d34  call    cs:__imp_RegCloseKey
0x140007d3b  nop     dword ptr [rax+rax+00h]
0x140007d40  mov     rdx, rsi; unsigned __int16 *
0x140007d43  mov     rcx, r13; this
0x140007d46  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140007d4b  mov     edi, eax
0x140007d4d  test    eax, eax
0x140007d4f  js      loc_140008222
0x140007d55  jmp     loc_1400080A3
0x140007d5a  movzx   eax, word ptr [rsi]
0x140007d5d  test    ax, ax
0x140007d60  jz      short loc_140007D8D
0x140007d62  mov     rcx, rsi; lpsz
0x140007d65  cmp     ax, 5Ch ; '\'
0x140007d69  jz      short loc_140007D84
0x140007d6b  call    cs:__imp_CharNextW
0x140007d72  nop     dword ptr [rax+rax+00h]
0x140007d77  mov     rcx, rax
0x140007d7a  movzx   eax, word ptr [rax]
0x140007d7d  test    ax, ax
0x140007d80  jnz     short loc_140007D65
0x140007d82  jmp     short loc_140007D8D
0x140007d84  test    rcx, rcx
0x140007d87  jnz     loc_14000827B
0x140007d8d  cmp     [rsp+2310h+var_22A8], edi
0x140007d91  jz      loc_140007F4A
0x140007d97  mov     [rsp+2310h+hKey], rdi
0x140007d9c  lea     rax, [rsp+2310h+hKey]
0x140007da1  mov     [rsp+2310h+phkResult], rax; phkResult
0x140007da6  mov     r14d, 2001Fh
0x140007dac  mov     r9d, r14d; samDesired
0x140007daf  xor     r8d, r8d; ulOptions
0x140007db2  mov     rdx, rsi; lpSubKey
0x140007db5  mov     rcx, r15; hKey
0x140007db8  call    cs:__imp_RegOpenKeyExW
0x140007dbf  nop     dword ptr [rax+rax+00h]
0x140007dc4  test    eax, eax
0x140007dc6  jnz     short loc_140007DEF
0x140007dc8  mov     eax, edi
0x140007dca  test    rbx, rbx
0x140007dcd  jz      short loc_140007DDE
0x140007dcf  mov     rcx, rbx; hKey
0x140007dd2  call    cs:__imp_RegCloseKey
0x140007dd9  nop     dword ptr [rax+rax+00h]
0x140007dde  mov     rbx, [rsp+2310h+hKey]
0x140007de3  mov     [rbp+2210h+var_2290], rbx
0x140007de7  test    eax, eax
0x140007de9  jz      loc_140007EB2
0x140007def  mov     [rsp+2310h+hKey], rdi
0x140007df4  lea     rax, [rsp+2310h+hKey]
0x140007df9  mov     [rsp+2310h+phkResult], rax; phkResult
0x140007dfe  mov     r9d, 20019h; samDesired
0x140007e04  xor     r8d, r8d; ulOptions
0x140007e07  mov     rdx, rsi; lpSubKey
0x140007e0a  mov     rcx, r15; hKey
0x140007e0d  call    cs:__imp_RegOpenKeyExW
0x140007e14  nop     dword ptr [rax+rax+00h]
0x140007e19  test    eax, eax
0x140007e1b  jnz     short loc_140007E40
0x140007e1d  mov     eax, edi
0x140007e1f  test    rbx, rbx
0x140007e22  jz      short loc_140007E33
0x140007e24  mov     rcx, rbx; hKey
0x140007e27  call    cs:__imp_RegCloseKey
0x140007e2e  nop     dword ptr [rax+rax+00h]
0x140007e33  mov     rbx, [rsp+2310h+hKey]
0x140007e38  mov     [rbp+2210h+var_2290], rbx
0x140007e3c  test    eax, eax
0x140007e3e  jz      short loc_140007EB2
0x140007e40  mov     dword ptr [rsp+2310h+hKey], edi
0x140007e44  mov     [rsp+2310h+var_2298], rdi
0x140007e49  lea     rax, [rsp+2310h+hKey]
0x140007e4e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x140007e53  lea     rax, [rsp+2310h+var_2298]
0x140007e58  mov     [rsp+2310h+var_22D8], rax; phkResult
0x140007e5d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140007e62  mov     [rsp+2310h+samDesired], r14d; samDesired
0x140007e67  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x140007e6b  xor     r9d, r9d; lpClass
0x140007e6e  xor     r8d, r8d; Reserved
0x140007e71  mov     rdx, rsi; lpSubKey
0x140007e74  mov     rcx, r15; hKey
0x140007e77  call    cs:__imp_RegCreateKeyExW
0x140007e7e  nop     dword ptr [rax+rax+00h]
0x140007e83  test    eax, eax
0x140007e85  jnz     loc_140008219
0x140007e8b  mov     eax, edi
0x140007e8d  test    rbx, rbx
0x140007e90  jz      short loc_140007EA1
0x140007e92  mov     rcx, rbx; hKey
0x140007e95  call    cs:__imp_RegCloseKey
0x140007e9c  nop     dword ptr [rax+rax+00h]
0x140007ea1  mov     rbx, [rsp+2310h+var_2298]
0x140007ea6  mov     [rbp+2210h+var_2290], rbx
0x140007eaa  test    eax, eax
0x140007eac  jnz     loc_140008219
0x140007eb2  mov     rdx, rsi; unsigned __int16 *
0x140007eb5  mov     rcx, r13; this
0x140007eb8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140007ebd  mov     edi, eax
0x140007ebf  xor     ecx, ecx
0x140007ec1  test    eax, eax
0x140007ec3  js      loc_140008222
0x140007ec9  cmp     word ptr [rsi], 3Dh ; '='
0x140007ecd  jnz     short loc_140007EF1
0x140007ecf  mov     r9, rsi; unsigned __int16 *
0x140007ed2  xor     r8d, r8d; unsigned __int16 *
0x140007ed5  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x140007ed9  mov     rcx, r13; this
0x140007edc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140007ee1  mov     edi, eax
0x140007ee3  mov     rbx, [rbp+2210h+var_2290]
0x140007ee7  test    eax, eax
0x140007ee9  js      loc_140008222
0x140007eef  xor     ecx, ecx
0x140007ef1  mov     r12d, [rsp+2310h+var_22A8]
0x140007ef6  cmp     word ptr [rsi], 7Bh ; '{'
0x140007efa  jnz     loc_1400080A3
0x140007f00  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007f04  inc     rax
0x140007f07  cmp     [rsi+rax*2], cx
  ... truncated ...
```
