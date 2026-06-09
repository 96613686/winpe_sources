# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000448c`
- end: `0x180004c23`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004118`
- `0x18000448c`

## callees

- `0x180002b3c`
- `0x18000326c`
- `0x18000374c`
- `0x180003874`
- `0x180003b24`
- `0x180003fc8`
- `0x18000448c`
- `0x180004c3c`
- `0x18000fe10`
- `0x18000fed0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000496a`
- `msvcrt!wcsncpy_s` at `0x18000496a`
- `USER32!CharNextW` at `0x18000456e`
- `USER32!CharNextW` at `0x180004739`
- `USER32!CharNextW` at `0x18000456e`
- `USER32!CharNextW` at `0x180004739`
- `ADVAPI32!RegCloseKey` at `0x180004708`
- `ADVAPI32!RegCloseKey` at `0x180004794`
- `ADVAPI32!RegCloseKey` at `0x1800047dd`
- `ADVAPI32!RegCloseKey` at `0x18000483f`
- `ADVAPI32!RegCloseKey` at `0x180004933`
- `ADVAPI32!RegCloseKey` at `0x180004b4a`
- `ADVAPI32!RegCloseKey` at `0x180004ba4`
- `ADVAPI32!RegCloseKey` at `0x180004be0`
- `ADVAPI32!RegCloseKey` at `0x180004bf0`
- `ADVAPI32!RegCloseKey` at `0x180004708`
- `ADVAPI32!RegCloseKey` at `0x180004794`
- `ADVAPI32!RegCloseKey` at `0x1800047dd`
- `ADVAPI32!RegCloseKey` at `0x18000483f`
- `ADVAPI32!RegCloseKey` at `0x180004933`
- `ADVAPI32!RegCloseKey` at `0x180004b4a`
- `ADVAPI32!RegCloseKey` at `0x180004ba4`
- `ADVAPI32!RegCloseKey` at `0x180004be0`
- `ADVAPI32!RegCloseKey` at `0x180004bf0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004a96`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004b2c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004a96`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004b2c`
- `ADVAPI32!RegCreateKeyExW` at `0x180004827`
- `ADVAPI32!RegCreateKeyExW` at `0x180004827`
- `ADVAPI32!RegOpenKeyExW` at `0x1800046d2`
- `ADVAPI32!RegOpenKeyExW` at `0x180004780`
- `ADVAPI32!RegOpenKeyExW` at `0x1800047c9`
- `ADVAPI32!RegOpenKeyExW` at `0x180004918`
- `ADVAPI32!RegOpenKeyExW` at `0x1800046d2`
- `ADVAPI32!RegOpenKeyExW` at `0x180004780`
- `ADVAPI32!RegOpenKeyExW` at `0x1800047c9`
- `ADVAPI32!RegOpenKeyExW` at `0x180004918`
- `ADVAPI32!RegDeleteValueW` at `0x1800046ef`
- `ADVAPI32!RegDeleteValueW` at `0x1800046ef`
- `KERNEL32!lstrcmpiW` at `0x180004509`
- `KERNEL32!lstrcmpiW` at `0x18000451c`
- `KERNEL32!lstrcmpiW` at `0x18000459a`
- `KERNEL32!lstrcmpiW` at `0x180004603`
- `KERNEL32!lstrcmpiW` at `0x180004631`
- `KERNEL32!lstrcmpiW` at `0x180004ab9`
- `KERNEL32!lstrcmpiW` at `0x180004509`
- `KERNEL32!lstrcmpiW` at `0x18000451c`
- `KERNEL32!lstrcmpiW` at `0x18000459a`
- `KERNEL32!lstrcmpiW` at `0x180004603`
- `KERNEL32!lstrcmpiW` at `0x180004631`
- `KERNEL32!lstrcmpiW` at `0x180004ab9`

## string_xrefs

- `0x180004512`: `ForceRemove`
- `0x1800045f9`: `NoRemove`
- `0x1800044ff`: `Delete`

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
0x18000448c  push    rbp
0x18000448e  push    rbx
0x18000448f  push    rsi
0x180004490  push    rdi
0x180004491  push    r12
0x180004493  push    r13
0x180004495  push    r14
0x180004497  push    r15
0x180004499  lea     rbp, [rsp-21D8h]
0x1800044a1  mov     eax, 22D8h
0x1800044a6  call    _alloca_probe
0x1800044ab  sub     rsp, rax
0x1800044ae  mov     rax, cs:__security_cookie
0x1800044b5  xor     rax, rsp
0x1800044b8  mov     [rbp+2210h+var_50], rax
0x1800044bf  mov     r12d, r9d
0x1800044c2  mov     [rsp+2310h+var_22A8], r9d
0x1800044c7  mov     r15, r8
0x1800044ca  mov     [rsp+2310h+var_22A0], r8
0x1800044cf  mov     rsi, rdx
0x1800044d2  mov     r13, rcx
0x1800044d5  xor     eax, eax
0x1800044d7  mov     ebx, eax
0x1800044d9  mov     [rbp+2210h+var_2290], rax
0x1800044dd  mov     [rbp+2210h+var_2288], rax
0x1800044e1  mov     [rbp+2210h+var_2280], rax
0x1800044e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800044ea  mov     edi, eax
0x1800044ec  test    eax, eax
0x1800044ee  jns     short loc_1800044F5
0x1800044f0  jmp     loc_180004BAC
0x1800044f5  cmp     word ptr [rsi], 7Dh ; '}'
0x1800044f9  jz      loc_180004B9C
0x1800044ff  lea     rdx, String2; "Delete"
0x180004506  mov     rcx, rsi; lpString1
0x180004509  call    cs:__imp_lstrcmpiW
0x18000450f  mov     r14d, eax
0x180004512  lea     rdx, aForceremove; "ForceRemove"
0x180004519  mov     rcx, rsi; lpString1
0x18000451c  call    cs:__imp_lstrcmpiW
0x180004522  xor     edi, edi
0x180004524  test    eax, eax
0x180004526  jz      short loc_180004531
0x180004528  test    r14d, r14d
0x18000452b  jnz     loc_1800045F3
0x180004531  mov     rdx, rsi; unsigned __int16 *
0x180004534  mov     rcx, r13; this
0x180004537  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000453c  mov     edi, eax
0x18000453e  test    eax, eax
0x180004540  js      loc_180004B9C
0x180004546  xor     edi, edi
0x180004548  test    r12d, r12d
0x18000454b  jz      loc_1800045F3
0x180004551  mov     [rbp+2210h+var_2278], rdi
0x180004555  mov     [rbp+2210h+var_2270], rdi
0x180004559  mov     [rbp+2210h+var_2268], rdi
0x18000455d  movzx   eax, word ptr [rsi]
0x180004560  test    ax, ax
0x180004563  jz      short loc_18000458A
0x180004565  mov     rcx, rsi; lpsz
0x180004568  cmp     ax, 5Ch ; '\'
0x18000456c  jz      short loc_180004581
0x18000456e  call    cs:__imp_CharNextW
0x180004574  mov     rcx, rax
0x180004577  movzx   eax, word ptr [rax]
0x18000457a  test    ax, ax
0x18000457d  jnz     short loc_180004568
0x18000457f  jmp     short loc_18000458A
0x180004581  test    rcx, rcx
0x180004584  jnz     loc_180004BE8
0x18000458a  mov     edx, edi
0x18000458c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004593  mov     rdx, [rax+rdx*8]; lpString2
0x180004597  mov     rcx, rsi; lpString1
0x18000459a  call    cs:__imp_lstrcmpiW
0x1800045a0  test    eax, eax
0x1800045a2  jz      short loc_1800045BB
0x1800045a4  inc     edi
0x1800045a6  cmp     edi, 0Ch
0x1800045a9  jl      short loc_18000458A
0x1800045ab  mov     [rbp+2210h+var_2278], r15
0x1800045af  mov     rdx, rsi; unsigned __int16 *
0x1800045b2  lea     rcx, [rbp+2210h+var_2278]; this
0x1800045b6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800045bb  xor     edi, edi
0x1800045bd  test    r14d, r14d
0x1800045c0  jnz     short loc_1800045F3
0x1800045c2  mov     rdx, rsi; unsigned __int16 *
0x1800045c5  mov     rcx, r13; this
0x1800045c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800045cd  mov     edi, eax
0x1800045cf  test    eax, eax
0x1800045d1  js      loc_180004B9C
0x1800045d7  mov     rdx, rsi; unsigned __int16 *
0x1800045da  mov     rcx, r13; this
0x1800045dd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800045e2  mov     edi, eax
0x1800045e4  xor     ecx, ecx
0x1800045e6  test    eax, eax
0x1800045e8  js      loc_180004B9C
0x1800045ee  jmp     loc_18000489A
0x1800045f3  mov     r12d, 1
0x1800045f9  lea     rdx, aNoremove; "NoRemove"
0x180004600  mov     rcx, rsi; lpString1
0x180004603  call    cs:__imp_lstrcmpiW
0x180004609  test    eax, eax
0x18000460b  jnz     short loc_180004627
0x18000460d  mov     r12d, edi
0x180004610  mov     rdx, rsi; unsigned __int16 *
0x180004613  mov     rcx, r13; this
0x180004616  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000461b  mov     edi, eax
0x18000461d  test    eax, eax
0x18000461f  js      loc_180004B9C
0x180004625  xor     edi, edi
0x180004627  lea     rdx, aVal; "Val"
0x18000462e  mov     rcx, rsi; lpString1
0x180004631  call    cs:__imp_lstrcmpiW
0x180004637  test    eax, eax
0x180004639  jnz     loc_180004728
0x18000463f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004646  mov     rcx, r13; this
0x180004649  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000464e  mov     edi, eax
0x180004650  test    eax, eax
0x180004652  js      loc_180004B9C
0x180004658  mov     rdx, rsi; unsigned __int16 *
0x18000465b  mov     rcx, r13; this
0x18000465e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004663  mov     edi, eax
0x180004665  test    eax, eax
0x180004667  js      loc_180004B9C
0x18000466d  cmp     word ptr [rsi], 3Dh ; '='
0x180004671  jnz     loc_180004BE8
0x180004677  xor     edi, edi
0x180004679  cmp     [rsp+2310h+var_22A8], edi
0x18000467d  jz      short loc_1800046A8
0x18000467f  mov     [rbp+2210h+var_2270], rdi
0x180004683  mov     [rbp+2210h+var_2268], rdi
0x180004687  mov     [rbp+2210h+var_2278], r15
0x18000468b  mov     r9, rsi; unsigned __int16 *
0x18000468e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180004695  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004699  mov     rcx, r13; this
0x18000469c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800046a1  mov     edi, eax
0x1800046a3  jmp     loc_18000488B
0x1800046a8  cmp     [rbp+2210h+arg_20], edi
0x1800046ae  jnz     short loc_18000470E
0x1800046b0  test    r12d, r12d
0x1800046b3  jz      short loc_18000470E
0x1800046b5  mov     [rsp+2310h+hKey], rdi
0x1800046ba  lea     rax, [rsp+2310h+hKey]
0x1800046bf  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800046c4  mov     r9d, 20006h; samDesired
0x1800046ca  xor     r8d, r8d; ulOptions
0x1800046cd  xor     edx, edx; lpSubKey
0x1800046cf  mov     rcx, r15; hKey
0x1800046d2  call    cs:__imp_RegOpenKeyExW
0x1800046d8  test    eax, eax
0x1800046da  jnz     loc_180004B93
0x1800046e0  mov     r14, [rsp+2310h+hKey]
0x1800046e5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800046ec  mov     rcx, r14; hKey
0x1800046ef  call    cs:__imp_RegDeleteValueW
0x1800046f5  test    eax, 0FFFFFFFDh
0x1800046fa  jnz     loc_180004BCF
0x180004700  test    r14, r14
0x180004703  jz      short loc_18000470E
0x180004705  mov     rcx, r14; hKey
0x180004708  call    cs:__imp_RegCloseKey
0x18000470e  mov     rdx, rsi; unsigned __int16 *
0x180004711  mov     rcx, r13; this
0x180004714  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004719  mov     edi, eax
0x18000471b  test    eax, eax
0x18000471d  js      loc_180004B9C
0x180004723  jmp     loc_180004A35
0x180004728  movzx   eax, word ptr [rsi]
0x18000472b  test    ax, ax
0x18000472e  jz      short loc_180004755
0x180004730  mov     rcx, rsi; lpsz
0x180004733  cmp     ax, 5Ch ; '\'
0x180004737  jz      short loc_18000474C
0x180004739  call    cs:__imp_CharNextW
0x18000473f  mov     rcx, rax
0x180004742  movzx   eax, word ptr [rax]
0x180004745  test    ax, ax
0x180004748  jnz     short loc_180004733
0x18000474a  jmp     short loc_180004755
0x18000474c  test    rcx, rcx
0x18000474f  jnz     loc_180004BE8
0x180004755  cmp     [rsp+2310h+var_22A8], edi
0x180004759  jz      loc_1800048EE
0x18000475f  mov     [rsp+2310h+hKey], rdi
0x180004764  lea     rax, [rsp+2310h+hKey]
0x180004769  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000476e  mov     r14d, 2001Fh
0x180004774  mov     r9d, r14d; samDesired
0x180004777  xor     r8d, r8d; ulOptions
0x18000477a  mov     rdx, rsi; lpSubKey
0x18000477d  mov     rcx, r15; hKey
0x180004780  call    cs:__imp_RegOpenKeyExW
0x180004786  test    eax, eax
0x180004788  jnz     short loc_1800047AB
0x18000478a  mov     eax, edi
0x18000478c  test    rbx, rbx
0x18000478f  jz      short loc_18000479A
0x180004791  mov     rcx, rbx; hKey
0x180004794  call    cs:__imp_RegCloseKey
0x18000479a  mov     rbx, [rsp+2310h+hKey]
0x18000479f  mov     [rbp+2210h+var_2290], rbx
0x1800047a3  test    eax, eax
0x1800047a5  jz      loc_180004856
0x1800047ab  mov     [rsp+2310h+hKey], rdi
0x1800047b0  lea     rax, [rsp+2310h+hKey]
0x1800047b5  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800047ba  mov     r9d, 20019h; samDesired
0x1800047c0  xor     r8d, r8d; ulOptions
0x1800047c3  mov     rdx, rsi; lpSubKey
0x1800047c6  mov     rcx, r15; hKey
0x1800047c9  call    cs:__imp_RegOpenKeyExW
0x1800047cf  test    eax, eax
0x1800047d1  jnz     short loc_1800047F0
0x1800047d3  mov     eax, edi
0x1800047d5  test    rbx, rbx
0x1800047d8  jz      short loc_1800047E3
0x1800047da  mov     rcx, rbx; hKey
0x1800047dd  call    cs:__imp_RegCloseKey
0x1800047e3  mov     rbx, [rsp+2310h+hKey]
0x1800047e8  mov     [rbp+2210h+var_2290], rbx
0x1800047ec  test    eax, eax
0x1800047ee  jz      short loc_180004856
0x1800047f0  mov     dword ptr [rsp+2310h+hKey], edi
0x1800047f4  mov     [rsp+2310h+var_2298], rdi
0x1800047f9  lea     rax, [rsp+2310h+hKey]
0x1800047fe  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180004803  lea     rax, [rsp+2310h+var_2298]
0x180004808  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000480d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004812  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180004817  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000481b  xor     r9d, r9d; lpClass
0x18000481e  xor     r8d, r8d; Reserved
0x180004821  mov     rdx, rsi; lpSubKey
0x180004824  mov     rcx, r15; hKey
0x180004827  call    cs:__imp_RegCreateKeyExW
0x18000482d  test    eax, eax
0x18000482f  jnz     loc_180004B93
0x180004835  mov     eax, edi
0x180004837  test    rbx, rbx
0x18000483a  jz      short loc_180004845
0x18000483c  mov     rcx, rbx; hKey
0x18000483f  call    cs:__imp_RegCloseKey
0x180004845  mov     rbx, [rsp+2310h+var_2298]
0x18000484a  mov     [rbp+2210h+var_2290], rbx
0x18000484e  test    eax, eax
0x180004850  jnz     loc_180004B93
0x180004856  mov     rdx, rsi; unsigned __int16 *
0x180004859  mov     rcx, r13; this
0x18000485c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004861  mov     edi, eax
0x180004863  xor     ecx, ecx
0x180004865  test    eax, eax
0x180004867  js      loc_180004B9C
0x18000486d  cmp     word ptr [rsi], 3Dh ; '='
0x180004871  jnz     short loc_180004895
0x180004873  mov     r9, rsi; unsigned __int16 *
0x180004876  xor     r8d, r8d; unsigned __int16 *
0x180004879  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000487d  mov     rcx, r13; this
0x180004880  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004885  mov     edi, eax
0x180004887  mov     rbx, [rbp+2210h+var_2290]
0x18000488b  test    eax, eax
0x18000488d  js      loc_180004B9C
0x180004893  xor     ecx, ecx
0x180004895  mov     r12d, [rsp+2310h+var_22A8]
0x18000489a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000489e  jnz     loc_180004A35
0x1800048a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800048a8  inc     rax
0x1800048ab  cmp     [rsi+rax*2], cx
0x1800048af  jnz     short loc_1800048A8
0x1800048b1  cmp     rax, 1
0x1800048b5  jnz     loc_180004A35
0x1800048bb  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x1800048c3  mov     r9d, r12d; int
0x1800048c6  mov     r8, rbx; HKEY
0x1800048c9  mov     rdx, rsi; unsigned __int16 *
0x1800048cc  mov     rcx, r13; this
0x1800048cf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800048d4  mov     edi, eax
0x1800048d6  test    eax, eax
0x1800048d8  js      loc_180004B9C
0x1800048de  mov     rdx, rsi; unsigned __int16 *
0x1800048e1  mov     rcx, r13; this
0x1800048e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800048e9  jmp     loc_180004719
  ... truncated ...
```
