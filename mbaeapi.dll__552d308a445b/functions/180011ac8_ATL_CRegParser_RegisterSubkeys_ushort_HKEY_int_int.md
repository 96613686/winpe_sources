# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180011ac8`
- end: `0x18001225f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180011758`
- `0x180011ac8`

## callees

- `0x1800024e0`
- `0x18000dcf0`
- `0x18000e3e0`
- `0x18000ec4c`
- `0x18000faf8`
- `0x180010b7c`
- `0x180011608`
- `0x180011ac8`
- `0x180012c08`
- `0x1800588d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011fa6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011fa6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011baa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011baa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011dbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011dbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001221c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001221c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800120d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012168`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800120d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012168`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011e63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011e63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011d2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011d2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011b45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011b58`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011bd6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011c3f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011c6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800120f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011b45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011b58`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011bd6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011c3f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011c6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800120f5`

## string_xrefs

- `0x180011b4e`: `ForceRemove`
- `0x180011c35`: `NoRemove`
- `0x180011b3b`: `Delete`

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
  HRESULT v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // edx
  HKEY v20; // r14
  unsigned int v21; // eax
  unsigned int v22; // edx
  int v23; // eax
  WCHAR v24; // ax
  const WCHAR *v25; // rcx
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  __int64 v28; // rax
  unsigned int v29; // r14d
  int v30; // r15d
  int v31; // eax
  __int64 v32; // rax
  int v33; // r14d
  winrt::impl *v34; // rcx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v36 = a4;
  v6 = a3;
  v37 = a3;
  v9 = 0;
  memset(v39, 0, sizeof(v39));
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
        v40 = 0;
        v41 = 0;
        v42 = 0;
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
            v40 = v6;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
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
    v24 = *a2;
    if ( *a2 )
    {
      v25 = a2;
      while ( v24 != 92 )
      {
        v25 = CharNextW(v25);
        v24 = *v25;
        if ( !*v25 )
          goto LABEL_43;
      }
      if ( v25 )
        goto LABEL_117;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v26 = 0;
      if ( v9 )
        v26 = RegCloseKey(v9);
      v9 = hKey;
      v39[0] = hKey;
      if ( v26 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = hKey;
        v39[0] = hKey;
        if ( v27 )
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
          v39[0] = phkResult;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue((LPCWSTR *)this, v39, 0, a2);
        Token = v17;
        v9 = v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v36;
LABEL_61:
      if ( *a2 != 123 )
        goto LABEL_93;
      v28 = -1;
      do
        ++v28;
      while ( a2[v28] );
      if ( v28 != 1 )
        goto LABEL_93;
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v23 = ATL::CRegParser::NextToken(this, a2);
LABEL_35:
      Token = v23;
      if ( v23 < 0 )
        goto LABEL_111;
      goto LABEL_93;
    }
    if ( a5 )
    {
      v29 = 2;
    }
    else
    {
      phkResult = 0;
      v29 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v29 )
      {
        v29 = 0;
        if ( v9 )
          v29 = RegCloseKey(v9);
        v9 = phkResult;
        v39[0] = phkResult;
      }
    }
    v30 = 1;
    if ( !v29 )
      v30 = a5;
    v31 = _o_wcsncpy_s(String1, 260, a2);
    if ( v31 )
    {
      if ( v31 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v31 == 22 || v31 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v31 != 80 )
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
      v32 = -1;
      do
        ++v32;
      while ( a2[v32] );
      if ( v32 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v30);
        if ( Token < 0 && !v30 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v29 == 2 )
      goto LABEL_92;
    if ( v29 )
    {
      if ( a5 )
      {
LABEL_92:
        v6 = v37;
        goto LABEL_93;
      }
      v34 = (winrt::impl *)v29;
LABEL_110:
      Token = winrt::impl::hresult_from_win32(v34, v19);
      goto LABEL_111;
    }
    v33 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v33]) )
          {
            if ( ++v33 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, String1);
                v9 = v39[0];
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
      LOBYTE(v33) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v18 = RegCloseKey(v9);
      v9 = 0;
      v39[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v34 = (winrt::impl *)v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v33 )
      goto LABEL_92;
    v41 = 0;
    v42 = 0;
    v6 = v37;
    v40 = v37;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, String1);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v36;
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
  if ( v36 )
  {
    v41 = 0;
    v42 = 0;
    v40 = v6;
    v17 = ATL::CRegParser::AddValue((LPCWSTR *)this, &v40, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v23 = ATL::CRegParser::SkipAssignment(this, a2);
    goto LABEL_35;
  }
  hKey = 0;
  v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v20 = hKey;
  v21 = RegDeleteValueW(hKey, ValueName);
  if ( (v21 & 0xFFFFFFFD) == 0 )
  {
    if ( v20 )
      RegCloseKey(v20);
    goto LABEL_34;
  }
  Token = winrt::impl::hresult_from_win32((winrt::impl *)v21, v22);
  if ( v20 )
    RegCloseKey(v20);
LABEL_111:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180011ac8  push    rbp
0x180011aca  push    rbx
0x180011acb  push    rsi
0x180011acc  push    rdi
0x180011acd  push    r12
0x180011acf  push    r13
0x180011ad1  push    r14
0x180011ad3  push    r15
0x180011ad5  lea     rbp, [rsp-21D8h]
0x180011add  mov     eax, 22D8h
0x180011ae2  call    _alloca_probe
0x180011ae7  sub     rsp, rax
0x180011aea  mov     rax, cs:__security_cookie
0x180011af1  xor     rax, rsp
0x180011af4  mov     [rbp+2210h+var_50], rax
0x180011afb  mov     r12d, r9d
0x180011afe  mov     [rsp+2310h+var_22A8], r9d
0x180011b03  mov     r15, r8
0x180011b06  mov     [rsp+2310h+var_22A0], r8
0x180011b0b  mov     rsi, rdx
0x180011b0e  mov     r13, rcx
0x180011b11  xor     eax, eax
0x180011b13  mov     ebx, eax
0x180011b15  mov     [rbp+2210h+var_2290], rax
0x180011b19  mov     [rbp+2210h+var_2288], rax
0x180011b1d  mov     [rbp+2210h+var_2280], rax
0x180011b21  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011b26  mov     edi, eax
0x180011b28  test    eax, eax
0x180011b2a  jns     short loc_180011B31
0x180011b2c  jmp     loc_1800121E8
0x180011b31  cmp     word ptr [rsi], 7Dh ; '}'
0x180011b35  jz      loc_1800121D8
0x180011b3b  lea     rdx, String2; "Delete"
0x180011b42  mov     rcx, rsi; lpString1
0x180011b45  call    cs:__imp_lstrcmpiW
0x180011b4b  mov     r14d, eax
0x180011b4e  lea     rdx, aForceremove; "ForceRemove"
0x180011b55  mov     rcx, rsi; lpString1
0x180011b58  call    cs:__imp_lstrcmpiW
0x180011b5e  xor     edi, edi
0x180011b60  test    eax, eax
0x180011b62  jz      short loc_180011B6D
0x180011b64  test    r14d, r14d
0x180011b67  jnz     loc_180011C2F
0x180011b6d  mov     rdx, rsi; unsigned __int16 *
0x180011b70  mov     rcx, r13; this
0x180011b73  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011b78  mov     edi, eax
0x180011b7a  test    eax, eax
0x180011b7c  js      loc_1800121D8
0x180011b82  xor     edi, edi
0x180011b84  test    r12d, r12d
0x180011b87  jz      loc_180011C2F
0x180011b8d  mov     [rbp+2210h+var_2278], rdi
0x180011b91  mov     [rbp+2210h+var_2270], rdi
0x180011b95  mov     [rbp+2210h+var_2268], rdi
0x180011b99  movzx   eax, word ptr [rsi]
0x180011b9c  test    ax, ax
0x180011b9f  jz      short loc_180011BC6
0x180011ba1  mov     rcx, rsi; lpsz
0x180011ba4  cmp     ax, 5Ch ; '\'
0x180011ba8  jz      short loc_180011BBD
0x180011baa  call    cs:__imp_CharNextW
0x180011bb0  mov     rcx, rax
0x180011bb3  movzx   eax, word ptr [rax]
0x180011bb6  test    ax, ax
0x180011bb9  jnz     short loc_180011BA4
0x180011bbb  jmp     short loc_180011BC6
0x180011bbd  test    rcx, rcx
0x180011bc0  jnz     loc_180012224
0x180011bc6  mov     edx, edi
0x180011bc8  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180011bcf  mov     rdx, [rax+rdx*8]; lpString2
0x180011bd3  mov     rcx, rsi; lpString1
0x180011bd6  call    cs:__imp_lstrcmpiW
0x180011bdc  test    eax, eax
0x180011bde  jz      short loc_180011BF7
0x180011be0  inc     edi
0x180011be2  cmp     edi, 0Ch
0x180011be5  jl      short loc_180011BC6
0x180011be7  mov     [rbp+2210h+var_2278], r15
0x180011beb  mov     rdx, rsi; unsigned __int16 *
0x180011bee  lea     rcx, [rbp+2210h+var_2278]; this
0x180011bf2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180011bf7  xor     edi, edi
0x180011bf9  test    r14d, r14d
0x180011bfc  jnz     short loc_180011C2F
0x180011bfe  mov     rdx, rsi; unsigned __int16 *
0x180011c01  mov     rcx, r13; this
0x180011c04  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011c09  mov     edi, eax
0x180011c0b  test    eax, eax
0x180011c0d  js      loc_1800121D8
0x180011c13  mov     rdx, rsi; unsigned __int16 *
0x180011c16  mov     rcx, r13; this
0x180011c19  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180011c1e  mov     edi, eax
0x180011c20  xor     ecx, ecx
0x180011c22  test    eax, eax
0x180011c24  js      loc_1800121D8
0x180011c2a  jmp     loc_180011ED6
0x180011c2f  mov     r12d, 1
0x180011c35  lea     rdx, aNoremove; "NoRemove"
0x180011c3c  mov     rcx, rsi; lpString1
0x180011c3f  call    cs:__imp_lstrcmpiW
0x180011c45  test    eax, eax
0x180011c47  jnz     short loc_180011C63
0x180011c49  mov     r12d, edi
0x180011c4c  mov     rdx, rsi; unsigned __int16 *
0x180011c4f  mov     rcx, r13; this
0x180011c52  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011c57  mov     edi, eax
0x180011c59  test    eax, eax
0x180011c5b  js      loc_1800121D8
0x180011c61  xor     edi, edi
0x180011c63  lea     rdx, aVal; "Val"
0x180011c6a  mov     rcx, rsi; lpString1
0x180011c6d  call    cs:__imp_lstrcmpiW
0x180011c73  test    eax, eax
0x180011c75  jnz     loc_180011D64
0x180011c7b  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180011c82  mov     rcx, r13; this
0x180011c85  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011c8a  mov     edi, eax
0x180011c8c  test    eax, eax
0x180011c8e  js      loc_1800121D8
0x180011c94  mov     rdx, rsi; unsigned __int16 *
0x180011c97  mov     rcx, r13; this
0x180011c9a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011c9f  mov     edi, eax
0x180011ca1  test    eax, eax
0x180011ca3  js      loc_1800121D8
0x180011ca9  cmp     word ptr [rsi], 3Dh ; '='
0x180011cad  jnz     loc_180012224
0x180011cb3  xor     edi, edi
0x180011cb5  cmp     [rsp+2310h+var_22A8], edi
0x180011cb9  jz      short loc_180011CE4
0x180011cbb  mov     [rbp+2210h+var_2270], rdi
0x180011cbf  mov     [rbp+2210h+var_2268], rdi
0x180011cc3  mov     [rbp+2210h+var_2278], r15
0x180011cc7  mov     r9, rsi; unsigned __int16 *
0x180011cca  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180011cd1  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180011cd5  mov     rcx, r13; this
0x180011cd8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180011cdd  mov     edi, eax
0x180011cdf  jmp     loc_180011EC7
0x180011ce4  cmp     [rbp+2210h+arg_20], edi
0x180011cea  jnz     short loc_180011D4A
0x180011cec  test    r12d, r12d
0x180011cef  jz      short loc_180011D4A
0x180011cf1  mov     [rsp+2310h+hKey], rdi
0x180011cf6  lea     rax, [rsp+2310h+hKey]
0x180011cfb  mov     [rsp+2310h+phkResult], rax; phkResult
0x180011d00  mov     r9d, 20006h; samDesired
0x180011d06  xor     r8d, r8d; ulOptions
0x180011d09  xor     edx, edx; lpSubKey
0x180011d0b  mov     rcx, r15; hKey
0x180011d0e  call    cs:__imp_RegOpenKeyExW
0x180011d14  test    eax, eax
0x180011d16  jnz     loc_1800121CF
0x180011d1c  mov     r14, [rsp+2310h+hKey]
0x180011d21  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180011d28  mov     rcx, r14; hKey
0x180011d2b  call    cs:__imp_RegDeleteValueW
0x180011d31  test    eax, 0FFFFFFFDh
0x180011d36  jnz     loc_18001220B
0x180011d3c  test    r14, r14
0x180011d3f  jz      short loc_180011D4A
0x180011d41  mov     rcx, r14; hKey
0x180011d44  call    cs:__imp_RegCloseKey
0x180011d4a  mov     rdx, rsi; unsigned __int16 *
0x180011d4d  mov     rcx, r13; this
0x180011d50  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180011d55  mov     edi, eax
0x180011d57  test    eax, eax
0x180011d59  js      loc_1800121D8
0x180011d5f  jmp     loc_180012071
0x180011d64  movzx   eax, word ptr [rsi]
0x180011d67  test    ax, ax
0x180011d6a  jz      short loc_180011D91
0x180011d6c  mov     rcx, rsi; lpsz
0x180011d6f  cmp     ax, 5Ch ; '\'
0x180011d73  jz      short loc_180011D88
0x180011d75  call    cs:__imp_CharNextW
0x180011d7b  mov     rcx, rax
0x180011d7e  movzx   eax, word ptr [rax]
0x180011d81  test    ax, ax
0x180011d84  jnz     short loc_180011D6F
0x180011d86  jmp     short loc_180011D91
0x180011d88  test    rcx, rcx
0x180011d8b  jnz     loc_180012224
0x180011d91  cmp     [rsp+2310h+var_22A8], edi
0x180011d95  jz      loc_180011F2A
0x180011d9b  mov     [rsp+2310h+hKey], rdi
0x180011da0  lea     rax, [rsp+2310h+hKey]
0x180011da5  mov     [rsp+2310h+phkResult], rax; phkResult
0x180011daa  mov     r14d, 2001Fh
0x180011db0  mov     r9d, r14d; samDesired
0x180011db3  xor     r8d, r8d; ulOptions
0x180011db6  mov     rdx, rsi; lpSubKey
0x180011db9  mov     rcx, r15; hKey
0x180011dbc  call    cs:__imp_RegOpenKeyExW
0x180011dc2  test    eax, eax
0x180011dc4  jnz     short loc_180011DE7
0x180011dc6  mov     eax, edi
0x180011dc8  test    rbx, rbx
0x180011dcb  jz      short loc_180011DD6
0x180011dcd  mov     rcx, rbx; hKey
0x180011dd0  call    cs:__imp_RegCloseKey
0x180011dd6  mov     rbx, [rsp+2310h+hKey]
0x180011ddb  mov     [rbp+2210h+var_2290], rbx
0x180011ddf  test    eax, eax
0x180011de1  jz      loc_180011E92
0x180011de7  mov     [rsp+2310h+hKey], rdi
0x180011dec  lea     rax, [rsp+2310h+hKey]
0x180011df1  mov     [rsp+2310h+phkResult], rax; phkResult
0x180011df6  mov     r9d, 20019h; samDesired
0x180011dfc  xor     r8d, r8d; ulOptions
0x180011dff  mov     rdx, rsi; lpSubKey
0x180011e02  mov     rcx, r15; hKey
0x180011e05  call    cs:__imp_RegOpenKeyExW
0x180011e0b  test    eax, eax
0x180011e0d  jnz     short loc_180011E2C
0x180011e0f  mov     eax, edi
0x180011e11  test    rbx, rbx
0x180011e14  jz      short loc_180011E1F
0x180011e16  mov     rcx, rbx; hKey
0x180011e19  call    cs:__imp_RegCloseKey
0x180011e1f  mov     rbx, [rsp+2310h+hKey]
0x180011e24  mov     [rbp+2210h+var_2290], rbx
0x180011e28  test    eax, eax
0x180011e2a  jz      short loc_180011E92
0x180011e2c  mov     dword ptr [rsp+2310h+hKey], edi
0x180011e30  mov     [rsp+2310h+var_2298], rdi
0x180011e35  lea     rax, [rsp+2310h+hKey]
0x180011e3a  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180011e3f  lea     rax, [rsp+2310h+var_2298]
0x180011e44  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180011e49  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180011e4e  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180011e53  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180011e57  xor     r9d, r9d; lpClass
0x180011e5a  xor     r8d, r8d; Reserved
0x180011e5d  mov     rdx, rsi; lpSubKey
0x180011e60  mov     rcx, r15; hKey
0x180011e63  call    cs:__imp_RegCreateKeyExW
0x180011e69  test    eax, eax
0x180011e6b  jnz     loc_1800121CF
0x180011e71  mov     eax, edi
0x180011e73  test    rbx, rbx
0x180011e76  jz      short loc_180011E81
0x180011e78  mov     rcx, rbx; hKey
0x180011e7b  call    cs:__imp_RegCloseKey
0x180011e81  mov     rbx, [rsp+2310h+var_2298]
0x180011e86  mov     [rbp+2210h+var_2290], rbx
0x180011e8a  test    eax, eax
0x180011e8c  jnz     loc_1800121CF
0x180011e92  mov     rdx, rsi; unsigned __int16 *
0x180011e95  mov     rcx, r13; this
0x180011e98  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011e9d  mov     edi, eax
0x180011e9f  xor     ecx, ecx
0x180011ea1  test    eax, eax
0x180011ea3  js      loc_1800121D8
0x180011ea9  cmp     word ptr [rsi], 3Dh ; '='
0x180011ead  jnz     short loc_180011ED1
0x180011eaf  mov     r9, rsi; unsigned __int16 *
0x180011eb2  xor     r8d, r8d; unsigned __int16 *
0x180011eb5  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180011eb9  mov     rcx, r13; this
0x180011ebc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180011ec1  mov     edi, eax
0x180011ec3  mov     rbx, [rbp+2210h+var_2290]
0x180011ec7  test    eax, eax
0x180011ec9  js      loc_1800121D8
0x180011ecf  xor     ecx, ecx
0x180011ed1  mov     r12d, [rsp+2310h+var_22A8]
0x180011ed6  cmp     word ptr [rsi], 7Bh ; '{'
0x180011eda  jnz     loc_180012071
0x180011ee0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011ee4  inc     rax
0x180011ee7  cmp     [rsi+rax*2], cx
0x180011eeb  jnz     short loc_180011EE4
0x180011eed  cmp     rax, 1
0x180011ef1  jnz     loc_180012071
0x180011ef7  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180011eff  mov     r9d, r12d; int
0x180011f02  mov     r8, rbx; HKEY
0x180011f05  mov     rdx, rsi; unsigned __int16 *
0x180011f08  mov     rcx, r13; this
0x180011f0b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180011f10  mov     edi, eax
0x180011f12  test    eax, eax
0x180011f14  js      loc_1800121D8
0x180011f1a  mov     rdx, rsi; unsigned __int16 *
0x180011f1d  mov     rcx, r13; this
0x180011f20  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011f25  jmp     loc_180011D55
  ... truncated ...
```
