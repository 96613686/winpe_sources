# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18000efac`
- end: `0x18000f743`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000ec38`
- `0x18000efac`

## callees

- `0x1800024a0`
- `0x18000bd2c`
- `0x18000c41c`
- `0x18000c434`
- `0x18000c790`
- `0x18000e33c`
- `0x18000eae8`
- `0x18000efac`
- `0x18000ff04`
- `0x180015650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f48a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f48a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f08e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f259`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f08e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f35f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f6c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f710`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f2fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f35f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f6c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f710`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f438`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f438`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f5b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f64c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f5b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f64c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f20f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f20f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f347`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f347`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f029`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f03c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f0ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f123`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f151`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f5d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f029`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f03c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f0ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f123`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f151`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f5d9`

## string_xrefs

- `0x18000f032`: `ForceRemove`
- `0x18000f119`: `NoRemove`
- `0x18000f01f`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, wchar_t *a2, HKEY a3, int a4, int a5)
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
  int v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  unsigned int v32; // ecx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  HKEY v36; // [rsp+70h] [rbp-90h]
  HKEY v37; // [rsp+78h] [rbp-88h] BYREF
  HKEY v38[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v35 = a4;
  v6 = a3;
  v36 = a3;
  v9 = 0;
  memset(v38, 0, sizeof(v38));
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
        v39 = 0;
        v40 = 0;
        v41 = 0;
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
            v39 = v6;
            ATL::CRegKey::RecurseDeleteKey(&v39, a2);
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
    if ( v35 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v24 = 0;
      if ( v9 )
        v24 = RegCloseKey(v9);
      v9 = hKey;
      v38[0] = hKey;
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
        v38[0] = hKey;
        if ( v25 )
        {
LABEL_127:
          LODWORD(hKey) = 0;
          v37 = 0;
          v18 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &v37, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_109;
          v18 = 0;
          if ( v9 )
            v18 = RegCloseKey(v9);
          v9 = v37;
          v38[0] = v37;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, v38, 0, a2);
        Token = v17;
        v9 = v38[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v35;
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
      v37 = 0;
      v27 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &v37);
      if ( !v27 )
      {
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = v37;
        v38[0] = v37;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = _o_wcsncpy_s(String1, 260, a2, -1, phkResult);
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
        v6 = v36;
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
                ATL::CRegKey::RecurseDeleteKey(v38, String1);
                v9 = v38[0];
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
      v38[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v32 = v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v31 )
      goto LABEL_92;
    v40 = 0;
    v41 = 0;
    v6 = v36;
    v39 = v36;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v39, String1);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v35;
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
  if ( v35 )
  {
    v40 = 0;
    v41 = 0;
    v39 = v6;
    v17 = ATL::CRegParser::AddValue(this, &v39, ValueName, a2);
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
0x18000efac  push    rbp
0x18000efae  push    rbx
0x18000efaf  push    rsi
0x18000efb0  push    rdi
0x18000efb1  push    r12
0x18000efb3  push    r13
0x18000efb5  push    r14
0x18000efb7  push    r15
0x18000efb9  lea     rbp, [rsp-21D8h]
0x18000efc1  mov     eax, 22D8h
0x18000efc6  call    _alloca_probe
0x18000efcb  sub     rsp, rax
0x18000efce  mov     rax, cs:__security_cookie
0x18000efd5  xor     rax, rsp
0x18000efd8  mov     [rbp+2210h+var_50], rax
0x18000efdf  mov     r12d, r9d
0x18000efe2  mov     [rsp+2310h+var_22A8], r9d
0x18000efe7  mov     r15, r8
0x18000efea  mov     [rsp+2310h+var_22A0], r8
0x18000efef  mov     rsi, rdx
0x18000eff2  mov     r13, rcx
0x18000eff5  xor     eax, eax
0x18000eff7  mov     ebx, eax
0x18000eff9  mov     [rbp+2210h+var_2290], rax
0x18000effd  mov     [rbp+2210h+var_2288], rax
0x18000f001  mov     [rbp+2210h+var_2280], rax
0x18000f005  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f00a  mov     edi, eax
0x18000f00c  test    eax, eax
0x18000f00e  jns     short loc_18000F015
0x18000f010  jmp     loc_18000F6CC
0x18000f015  cmp     word ptr [rsi], 7Dh ; '}'
0x18000f019  jz      loc_18000F6BC
0x18000f01f  lea     rdx, String2; "Delete"
0x18000f026  mov     rcx, rsi; lpString1
0x18000f029  call    cs:__imp_lstrcmpiW
0x18000f02f  mov     r14d, eax
0x18000f032  lea     rdx, aForceremove; "ForceRemove"
0x18000f039  mov     rcx, rsi; lpString1
0x18000f03c  call    cs:__imp_lstrcmpiW
0x18000f042  xor     edi, edi
0x18000f044  test    eax, eax
0x18000f046  jz      short loc_18000F051
0x18000f048  test    r14d, r14d
0x18000f04b  jnz     loc_18000F113
0x18000f051  mov     rdx, rsi; wchar_t *
0x18000f054  mov     rcx, r13; this
0x18000f057  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f05c  mov     edi, eax
0x18000f05e  test    eax, eax
0x18000f060  js      loc_18000F6BC
0x18000f066  xor     edi, edi
0x18000f068  test    r12d, r12d
0x18000f06b  jz      loc_18000F113
0x18000f071  mov     [rbp+2210h+var_2278], rdi
0x18000f075  mov     [rbp+2210h+var_2270], rdi
0x18000f079  mov     [rbp+2210h+var_2268], rdi
0x18000f07d  movzx   eax, word ptr [rsi]
0x18000f080  test    ax, ax
0x18000f083  jz      short loc_18000F0AA
0x18000f085  mov     rcx, rsi; lpsz
0x18000f088  cmp     ax, 5Ch ; '\'
0x18000f08c  jz      short loc_18000F0A1
0x18000f08e  call    cs:__imp_CharNextW
0x18000f094  mov     rcx, rax
0x18000f097  movzx   eax, word ptr [rax]
0x18000f09a  test    ax, ax
0x18000f09d  jnz     short loc_18000F088
0x18000f09f  jmp     short loc_18000F0AA
0x18000f0a1  test    rcx, rcx
0x18000f0a4  jnz     loc_18000F708
0x18000f0aa  mov     edx, edi
0x18000f0ac  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEB_WB; wchar_t const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000f0b3  mov     rdx, [rax+rdx*8]; lpString2
0x18000f0b7  mov     rcx, rsi; lpString1
0x18000f0ba  call    cs:__imp_lstrcmpiW
0x18000f0c0  test    eax, eax
0x18000f0c2  jz      short loc_18000F0DB
0x18000f0c4  inc     edi
0x18000f0c6  cmp     edi, 0Ch
0x18000f0c9  jl      short loc_18000F0AA
0x18000f0cb  mov     [rbp+2210h+var_2278], r15
0x18000f0cf  mov     rdx, rsi; wchar_t *
0x18000f0d2  lea     rcx, [rbp+2210h+var_2278]; this
0x18000f0d6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000f0db  xor     edi, edi
0x18000f0dd  test    r14d, r14d
0x18000f0e0  jnz     short loc_18000F113
0x18000f0e2  mov     rdx, rsi; wchar_t *
0x18000f0e5  mov     rcx, r13; this
0x18000f0e8  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f0ed  mov     edi, eax
0x18000f0ef  test    eax, eax
0x18000f0f1  js      loc_18000F6BC
0x18000f0f7  mov     rdx, rsi; wchar_t *
0x18000f0fa  mov     rcx, r13; this
0x18000f0fd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000f102  mov     edi, eax
0x18000f104  xor     ecx, ecx
0x18000f106  test    eax, eax
0x18000f108  js      loc_18000F6BC
0x18000f10e  jmp     loc_18000F3BA
0x18000f113  mov     r12d, 1
0x18000f119  lea     rdx, aNoremove; "NoRemove"
0x18000f120  mov     rcx, rsi; lpString1
0x18000f123  call    cs:__imp_lstrcmpiW
0x18000f129  test    eax, eax
0x18000f12b  jnz     short loc_18000F147
0x18000f12d  mov     r12d, edi
0x18000f130  mov     rdx, rsi; wchar_t *
0x18000f133  mov     rcx, r13; this
0x18000f136  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f13b  mov     edi, eax
0x18000f13d  test    eax, eax
0x18000f13f  js      loc_18000F6BC
0x18000f145  xor     edi, edi
0x18000f147  lea     rdx, aVal; "Val"
0x18000f14e  mov     rcx, rsi; lpString1
0x18000f151  call    cs:__imp_lstrcmpiW
0x18000f157  test    eax, eax
0x18000f159  jnz     loc_18000F248
0x18000f15f  lea     rdx, [rbp+2210h+ValueName]; wchar_t *
0x18000f166  mov     rcx, r13; this
0x18000f169  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f16e  mov     edi, eax
0x18000f170  test    eax, eax
0x18000f172  js      loc_18000F6BC
0x18000f178  mov     rdx, rsi; wchar_t *
0x18000f17b  mov     rcx, r13; this
0x18000f17e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f183  mov     edi, eax
0x18000f185  test    eax, eax
0x18000f187  js      loc_18000F6BC
0x18000f18d  cmp     word ptr [rsi], 3Dh ; '='
0x18000f191  jnz     loc_18000F708
0x18000f197  xor     edi, edi
0x18000f199  cmp     [rsp+2310h+var_22A8], edi
0x18000f19d  jz      short loc_18000F1C8
0x18000f19f  mov     [rbp+2210h+var_2270], rdi
0x18000f1a3  mov     [rbp+2210h+var_2268], rdi
0x18000f1a7  mov     [rbp+2210h+var_2278], r15
0x18000f1ab  mov     r9, rsi; wchar_t *
0x18000f1ae  lea     r8, [rbp+2210h+ValueName]; wchar_t *
0x18000f1b5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18000f1b9  mov     rcx, r13; this
0x18000f1bc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18000f1c1  mov     edi, eax
0x18000f1c3  jmp     loc_18000F3AB
0x18000f1c8  cmp     [rbp+2210h+arg_20], edi
0x18000f1ce  jnz     short loc_18000F22E
0x18000f1d0  test    r12d, r12d
0x18000f1d3  jz      short loc_18000F22E
0x18000f1d5  mov     [rsp+2310h+hKey], rdi
0x18000f1da  lea     rax, [rsp+2310h+hKey]
0x18000f1df  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000f1e4  mov     r9d, 20006h; samDesired
0x18000f1ea  xor     r8d, r8d; ulOptions
0x18000f1ed  xor     edx, edx; lpSubKey
0x18000f1ef  mov     rcx, r15; hKey
0x18000f1f2  call    cs:__imp_RegOpenKeyExW
0x18000f1f8  test    eax, eax
0x18000f1fa  jnz     loc_18000F6B3
0x18000f200  mov     r14, [rsp+2310h+hKey]
0x18000f205  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000f20c  mov     rcx, r14; hKey
0x18000f20f  call    cs:__imp_RegDeleteValueW
0x18000f215  test    eax, 0FFFFFFFDh
0x18000f21a  jnz     loc_18000F6EF
0x18000f220  test    r14, r14
0x18000f223  jz      short loc_18000F22E
0x18000f225  mov     rcx, r14; hKey
0x18000f228  call    cs:__imp_RegCloseKey
0x18000f22e  mov     rdx, rsi; wchar_t *
0x18000f231  mov     rcx, r13; this
0x18000f234  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000f239  mov     edi, eax
0x18000f23b  test    eax, eax
0x18000f23d  js      loc_18000F6BC
0x18000f243  jmp     loc_18000F555
0x18000f248  movzx   eax, word ptr [rsi]
0x18000f24b  test    ax, ax
0x18000f24e  jz      short loc_18000F275
0x18000f250  mov     rcx, rsi; lpsz
0x18000f253  cmp     ax, 5Ch ; '\'
0x18000f257  jz      short loc_18000F26C
0x18000f259  call    cs:__imp_CharNextW
0x18000f25f  mov     rcx, rax
0x18000f262  movzx   eax, word ptr [rax]
0x18000f265  test    ax, ax
0x18000f268  jnz     short loc_18000F253
0x18000f26a  jmp     short loc_18000F275
0x18000f26c  test    rcx, rcx
0x18000f26f  jnz     loc_18000F708
0x18000f275  cmp     [rsp+2310h+var_22A8], edi
0x18000f279  jz      loc_18000F40E
0x18000f27f  mov     [rsp+2310h+hKey], rdi
0x18000f284  lea     rax, [rsp+2310h+hKey]
0x18000f289  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000f28e  mov     r14d, 2001Fh
0x18000f294  mov     r9d, r14d; samDesired
0x18000f297  xor     r8d, r8d; ulOptions
0x18000f29a  mov     rdx, rsi; lpSubKey
0x18000f29d  mov     rcx, r15; hKey
0x18000f2a0  call    cs:__imp_RegOpenKeyExW
0x18000f2a6  test    eax, eax
0x18000f2a8  jnz     short loc_18000F2CB
0x18000f2aa  mov     eax, edi
0x18000f2ac  test    rbx, rbx
0x18000f2af  jz      short loc_18000F2BA
0x18000f2b1  mov     rcx, rbx; hKey
0x18000f2b4  call    cs:__imp_RegCloseKey
0x18000f2ba  mov     rbx, [rsp+2310h+hKey]
0x18000f2bf  mov     [rbp+2210h+var_2290], rbx
0x18000f2c3  test    eax, eax
0x18000f2c5  jz      loc_18000F376
0x18000f2cb  mov     [rsp+2310h+hKey], rdi
0x18000f2d0  lea     rax, [rsp+2310h+hKey]
0x18000f2d5  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000f2da  mov     r9d, 20019h; samDesired
0x18000f2e0  xor     r8d, r8d; ulOptions
0x18000f2e3  mov     rdx, rsi; lpSubKey
0x18000f2e6  mov     rcx, r15; hKey
0x18000f2e9  call    cs:__imp_RegOpenKeyExW
0x18000f2ef  test    eax, eax
0x18000f2f1  jnz     short loc_18000F310
0x18000f2f3  mov     eax, edi
0x18000f2f5  test    rbx, rbx
0x18000f2f8  jz      short loc_18000F303
0x18000f2fa  mov     rcx, rbx; hKey
0x18000f2fd  call    cs:__imp_RegCloseKey
0x18000f303  mov     rbx, [rsp+2310h+hKey]
0x18000f308  mov     [rbp+2210h+var_2290], rbx
0x18000f30c  test    eax, eax
0x18000f30e  jz      short loc_18000F376
0x18000f310  mov     dword ptr [rsp+2310h+hKey], edi
0x18000f314  mov     [rsp+2310h+var_2298], rdi
0x18000f319  lea     rax, [rsp+2310h+hKey]
0x18000f31e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000f323  lea     rax, [rsp+2310h+var_2298]
0x18000f328  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000f32d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000f332  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000f337  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000f33b  xor     r9d, r9d; lpClass
0x18000f33e  xor     r8d, r8d; Reserved
0x18000f341  mov     rdx, rsi; lpSubKey
0x18000f344  mov     rcx, r15; hKey
0x18000f347  call    cs:__imp_RegCreateKeyExW
0x18000f34d  test    eax, eax
0x18000f34f  jnz     loc_18000F6B3
0x18000f355  mov     eax, edi
0x18000f357  test    rbx, rbx
0x18000f35a  jz      short loc_18000F365
0x18000f35c  mov     rcx, rbx; hKey
0x18000f35f  call    cs:__imp_RegCloseKey
0x18000f365  mov     rbx, [rsp+2310h+var_2298]
0x18000f36a  mov     [rbp+2210h+var_2290], rbx
0x18000f36e  test    eax, eax
0x18000f370  jnz     loc_18000F6B3
0x18000f376  mov     rdx, rsi; wchar_t *
0x18000f379  mov     rcx, r13; this
0x18000f37c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f381  mov     edi, eax
0x18000f383  xor     ecx, ecx
0x18000f385  test    eax, eax
0x18000f387  js      loc_18000F6BC
0x18000f38d  cmp     word ptr [rsi], 3Dh ; '='
0x18000f391  jnz     short loc_18000F3B5
0x18000f393  mov     r9, rsi; wchar_t *
0x18000f396  xor     r8d, r8d; wchar_t *
0x18000f399  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000f39d  mov     rcx, r13; this
0x18000f3a0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18000f3a5  mov     edi, eax
0x18000f3a7  mov     rbx, [rbp+2210h+var_2290]
0x18000f3ab  test    eax, eax
0x18000f3ad  js      loc_18000F6BC
0x18000f3b3  xor     ecx, ecx
0x18000f3b5  mov     r12d, [rsp+2310h+var_22A8]
0x18000f3ba  cmp     word ptr [rsi], 7Bh ; '{'
0x18000f3be  jnz     loc_18000F555
0x18000f3c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f3c8  inc     rax
0x18000f3cb  cmp     [rsi+rax*2], cx
0x18000f3cf  jnz     short loc_18000F3C8
0x18000f3d1  cmp     rax, 1
0x18000f3d5  jnz     loc_18000F555
0x18000f3db  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x18000f3e3  mov     r9d, r12d; int
0x18000f3e6  mov     r8, rbx; HKEY
0x18000f3e9  mov     rdx, rsi; wchar_t *
0x18000f3ec  mov     rcx, r13; this
0x18000f3ef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000f3f4  mov     edi, eax
0x18000f3f6  test    eax, eax
0x18000f3f8  js      loc_18000F6BC
0x18000f3fe  mov     rdx, rsi; wchar_t *
0x18000f401  mov     rcx, r13; this
0x18000f404  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f409  jmp     loc_18000F239
  ... truncated ...
```
