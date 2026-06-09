# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180009108`
- end: `0x18000993c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2100`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180008d5c`
- `0x180009108`

## callees

- `0x18000615c`
- `0x1800068d4`
- `0x1800068ec`
- `0x180006f3c`
- `0x180008514`
- `0x180008b8c`
- `0x180009108`
- `0x180009ba0`
- `0x1800136b0`
- `0x180013770`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180009652`
- `msvcrt!wcsncpy_s` at `0x180009652`
- `KERNEL32!lstrcmpiW` at `0x180009185`
- `KERNEL32!lstrcmpiW` at `0x18000919e`
- `KERNEL32!lstrcmpiW` at `0x180009228`
- `KERNEL32!lstrcmpiW` at `0x180009297`
- `KERNEL32!lstrcmpiW` at `0x1800092cb`
- `KERNEL32!lstrcmpiW` at `0x1800097ad`
- `KERNEL32!lstrcmpiW` at `0x180009185`
- `KERNEL32!lstrcmpiW` at `0x18000919e`
- `KERNEL32!lstrcmpiW` at `0x180009228`
- `KERNEL32!lstrcmpiW` at `0x180009297`
- `KERNEL32!lstrcmpiW` at `0x1800092cb`
- `KERNEL32!lstrcmpiW` at `0x1800097ad`
- `USER32!CharNextW` at `0x1800091f6`
- `USER32!CharNextW` at `0x1800093eb`
- `USER32!CharNextW` at `0x1800091f6`
- `USER32!CharNextW` at `0x1800093eb`
- `ADVAPI32!RegCreateKeyExW` at `0x1800094f7`
- `ADVAPI32!RegCreateKeyExW` at `0x1800094f7`
- `ADVAPI32!RegCloseKey` at `0x1800093b4`
- `ADVAPI32!RegCloseKey` at `0x180009452`
- `ADVAPI32!RegCloseKey` at `0x1800094a7`
- `ADVAPI32!RegCloseKey` at `0x180009515`
- `ADVAPI32!RegCloseKey` at `0x180009615`
- `ADVAPI32!RegCloseKey` at `0x18000984a`
- `ADVAPI32!RegCloseKey` at `0x1800098aa`
- `ADVAPI32!RegCloseKey` at `0x1800098ed`
- `ADVAPI32!RegCloseKey` at `0x180009903`
- `ADVAPI32!RegCloseKey` at `0x1800093b4`
- `ADVAPI32!RegCloseKey` at `0x180009452`
- `ADVAPI32!RegCloseKey` at `0x1800094a7`
- `ADVAPI32!RegCloseKey` at `0x180009515`
- `ADVAPI32!RegCloseKey` at `0x180009615`
- `ADVAPI32!RegCloseKey` at `0x18000984a`
- `ADVAPI32!RegCloseKey` at `0x1800098aa`
- `ADVAPI32!RegCloseKey` at `0x1800098ed`
- `ADVAPI32!RegCloseKey` at `0x180009903`
- `ADVAPI32!RegDeleteValueW` at `0x180009395`
- `ADVAPI32!RegDeleteValueW` at `0x180009395`
- `ADVAPI32!RegOpenKeyExW` at `0x180009372`
- `ADVAPI32!RegOpenKeyExW` at `0x180009438`
- `ADVAPI32!RegOpenKeyExW` at `0x18000948d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800095f4`
- `ADVAPI32!RegOpenKeyExW` at `0x180009372`
- `ADVAPI32!RegOpenKeyExW` at `0x180009438`
- `ADVAPI32!RegOpenKeyExW` at `0x18000948d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800095f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009784`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009826`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009784`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009826`

## string_xrefs

- `0x180009194`: `ForceRemove`
- `0x18000928d`: `NoRemove`
- `0x18000917b`: `Delete`

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
0x180009108  push    rbp
0x18000910a  push    rbx
0x18000910b  push    rsi
0x18000910c  push    rdi
0x18000910d  push    r12
0x18000910f  push    r13
0x180009111  push    r14
0x180009113  push    r15
0x180009115  lea     rbp, [rsp-21D8h]
0x18000911d  mov     eax, 22D8h
0x180009122  call    _alloca_probe
0x180009127  sub     rsp, rax
0x18000912a  mov     rax, cs:__security_cookie
0x180009131  xor     rax, rsp
0x180009134  mov     [rbp+2210h+var_50], rax
0x18000913b  mov     r12d, r9d
0x18000913e  mov     [rsp+2310h+var_22A8], r9d
0x180009143  mov     r15, r8
0x180009146  mov     [rsp+2310h+var_22A0], r8
0x18000914b  mov     rsi, rdx
0x18000914e  mov     r13, rcx
0x180009151  xor     eax, eax
0x180009153  mov     ebx, eax
0x180009155  mov     [rbp+2210h+var_2290], rax
0x180009159  mov     [rbp+2210h+var_2288], rax
0x18000915d  mov     [rbp+2210h+var_2280], rax
0x180009161  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009166  mov     edi, eax
0x180009168  test    eax, eax
0x18000916a  jns     short loc_180009171
0x18000916c  jmp     loc_1800098B8
0x180009171  cmp     word ptr [rsi], 7Dh ; '}'
0x180009175  jz      loc_1800098A2
0x18000917b  lea     rdx, String2; "Delete"
0x180009182  mov     rcx, rsi; lpString1
0x180009185  call    cs:__imp_lstrcmpiW
0x18000918c  nop     dword ptr [rax+rax+00h]
0x180009191  mov     r14d, eax
0x180009194  lea     rdx, aForceremove; "ForceRemove"
0x18000919b  mov     rcx, rsi; lpString1
0x18000919e  call    cs:__imp_lstrcmpiW
0x1800091a5  nop     dword ptr [rax+rax+00h]
0x1800091aa  xor     edi, edi
0x1800091ac  test    eax, eax
0x1800091ae  jz      short loc_1800091B9
0x1800091b0  test    r14d, r14d
0x1800091b3  jnz     loc_180009287
0x1800091b9  mov     rdx, rsi; unsigned __int16 *
0x1800091bc  mov     rcx, r13; this
0x1800091bf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091c4  mov     edi, eax
0x1800091c6  test    eax, eax
0x1800091c8  js      loc_1800098A2
0x1800091ce  xor     edi, edi
0x1800091d0  test    r12d, r12d
0x1800091d3  jz      loc_180009287
0x1800091d9  mov     [rbp+2210h+var_2278], rdi
0x1800091dd  mov     [rbp+2210h+var_2270], rdi
0x1800091e1  mov     [rbp+2210h+var_2268], rdi
0x1800091e5  movzx   eax, word ptr [rsi]
0x1800091e8  test    ax, ax
0x1800091eb  jz      short loc_180009218
0x1800091ed  mov     rcx, rsi; lpsz
0x1800091f0  cmp     ax, 5Ch ; '\'
0x1800091f4  jz      short loc_18000920F
0x1800091f6  call    cs:__imp_CharNextW
0x1800091fd  nop     dword ptr [rax+rax+00h]
0x180009202  mov     rcx, rax
0x180009205  movzx   eax, word ptr [rax]
0x180009208  test    ax, ax
0x18000920b  jnz     short loc_1800091F0
0x18000920d  jmp     short loc_180009218
0x18000920f  test    rcx, rcx
0x180009212  jnz     loc_1800098FB
0x180009218  mov     edx, edi
0x18000921a  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180009221  mov     rdx, [rax+rdx*8]; lpString2
0x180009225  mov     rcx, rsi; lpString1
0x180009228  call    cs:__imp_lstrcmpiW
0x18000922f  nop     dword ptr [rax+rax+00h]
0x180009234  test    eax, eax
0x180009236  jz      short loc_18000924F
0x180009238  inc     edi
0x18000923a  cmp     edi, 0Ch
0x18000923d  jl      short loc_180009218
0x18000923f  mov     [rbp+2210h+var_2278], r15
0x180009243  mov     rdx, rsi; unsigned __int16 *
0x180009246  lea     rcx, [rbp+2210h+var_2278]; this
0x18000924a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000924f  xor     edi, edi
0x180009251  test    r14d, r14d
0x180009254  jnz     short loc_180009287
0x180009256  mov     rdx, rsi; unsigned __int16 *
0x180009259  mov     rcx, r13; this
0x18000925c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009261  mov     edi, eax
0x180009263  test    eax, eax
0x180009265  js      loc_1800098A2
0x18000926b  mov     rdx, rsi; unsigned __int16 *
0x18000926e  mov     rcx, r13; this
0x180009271  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009276  mov     edi, eax
0x180009278  xor     ecx, ecx
0x18000927a  test    eax, eax
0x18000927c  js      loc_1800098A2
0x180009282  jmp     loc_180009576
0x180009287  mov     r12d, 1
0x18000928d  lea     rdx, aNoremove; "NoRemove"
0x180009294  mov     rcx, rsi; lpString1
0x180009297  call    cs:__imp_lstrcmpiW
0x18000929e  nop     dword ptr [rax+rax+00h]
0x1800092a3  test    eax, eax
0x1800092a5  jnz     short loc_1800092C1
0x1800092a7  mov     r12d, edi
0x1800092aa  mov     rdx, rsi; unsigned __int16 *
0x1800092ad  mov     rcx, r13; this
0x1800092b0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800092b5  mov     edi, eax
0x1800092b7  test    eax, eax
0x1800092b9  js      loc_1800098A2
0x1800092bf  xor     edi, edi
0x1800092c1  lea     rdx, aVal; "Val"
0x1800092c8  mov     rcx, rsi; lpString1
0x1800092cb  call    cs:__imp_lstrcmpiW
0x1800092d2  nop     dword ptr [rax+rax+00h]
0x1800092d7  test    eax, eax
0x1800092d9  jnz     loc_1800093DA
0x1800092df  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800092e6  mov     rcx, r13; this
0x1800092e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800092ee  mov     edi, eax
0x1800092f0  test    eax, eax
0x1800092f2  js      loc_1800098A2
0x1800092f8  mov     rdx, rsi; unsigned __int16 *
0x1800092fb  mov     rcx, r13; this
0x1800092fe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009303  mov     edi, eax
0x180009305  test    eax, eax
0x180009307  js      loc_1800098A2
0x18000930d  cmp     word ptr [rsi], 3Dh ; '='
0x180009311  jnz     loc_1800098FB
0x180009317  xor     edi, edi
0x180009319  cmp     [rsp+2310h+var_22A8], edi
0x18000931d  jz      short loc_180009348
0x18000931f  mov     [rbp+2210h+var_2270], rdi
0x180009323  mov     [rbp+2210h+var_2268], rdi
0x180009327  mov     [rbp+2210h+var_2278], r15
0x18000932b  mov     r9, rsi; unsigned __int16 *
0x18000932e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180009335  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180009339  mov     rcx, r13; this
0x18000933c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009341  mov     edi, eax
0x180009343  jmp     loc_180009567
0x180009348  cmp     [rbp+2210h+arg_20], edi
0x18000934e  jnz     short loc_1800093C0
0x180009350  test    r12d, r12d
0x180009353  jz      short loc_1800093C0
0x180009355  mov     [rsp+2310h+hKey], rdi
0x18000935a  lea     rax, [rsp+2310h+hKey]
0x18000935f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009364  mov     r9d, 20006h; samDesired
0x18000936a  xor     r8d, r8d; ulOptions
0x18000936d  xor     edx, edx; lpSubKey
0x18000936f  mov     rcx, r15; hKey
0x180009372  call    cs:__imp_RegOpenKeyExW
0x180009379  nop     dword ptr [rax+rax+00h]
0x18000937e  test    eax, eax
0x180009380  jnz     loc_180009899
0x180009386  mov     r14, [rsp+2310h+hKey]
0x18000938b  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180009392  mov     rcx, r14; hKey
0x180009395  call    cs:__imp_RegDeleteValueW
0x18000939c  nop     dword ptr [rax+rax+00h]
0x1800093a1  test    eax, 0FFFFFFFDh
0x1800093a6  jnz     loc_1800098DC
0x1800093ac  test    r14, r14
0x1800093af  jz      short loc_1800093C0
0x1800093b1  mov     rcx, r14; hKey
0x1800093b4  call    cs:__imp_RegCloseKey
0x1800093bb  nop     dword ptr [rax+rax+00h]
0x1800093c0  mov     rdx, rsi; unsigned __int16 *
0x1800093c3  mov     rcx, r13; this
0x1800093c6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800093cb  mov     edi, eax
0x1800093cd  test    eax, eax
0x1800093cf  js      loc_1800098A2
0x1800093d5  jmp     loc_180009723
0x1800093da  movzx   eax, word ptr [rsi]
0x1800093dd  test    ax, ax
0x1800093e0  jz      short loc_18000940D
0x1800093e2  mov     rcx, rsi; lpsz
0x1800093e5  cmp     ax, 5Ch ; '\'
0x1800093e9  jz      short loc_180009404
0x1800093eb  call    cs:__imp_CharNextW
0x1800093f2  nop     dword ptr [rax+rax+00h]
0x1800093f7  mov     rcx, rax
0x1800093fa  movzx   eax, word ptr [rax]
0x1800093fd  test    ax, ax
0x180009400  jnz     short loc_1800093E5
0x180009402  jmp     short loc_18000940D
0x180009404  test    rcx, rcx
0x180009407  jnz     loc_1800098FB
0x18000940d  cmp     [rsp+2310h+var_22A8], edi
0x180009411  jz      loc_1800095CA
0x180009417  mov     [rsp+2310h+hKey], rdi
0x18000941c  lea     rax, [rsp+2310h+hKey]
0x180009421  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009426  mov     r14d, 2001Fh
0x18000942c  mov     r9d, r14d; samDesired
0x18000942f  xor     r8d, r8d; ulOptions
0x180009432  mov     rdx, rsi; lpSubKey
0x180009435  mov     rcx, r15; hKey
0x180009438  call    cs:__imp_RegOpenKeyExW
0x18000943f  nop     dword ptr [rax+rax+00h]
0x180009444  test    eax, eax
0x180009446  jnz     short loc_18000946F
0x180009448  mov     eax, edi
0x18000944a  test    rbx, rbx
0x18000944d  jz      short loc_18000945E
0x18000944f  mov     rcx, rbx; hKey
0x180009452  call    cs:__imp_RegCloseKey
0x180009459  nop     dword ptr [rax+rax+00h]
0x18000945e  mov     rbx, [rsp+2310h+hKey]
0x180009463  mov     [rbp+2210h+var_2290], rbx
0x180009467  test    eax, eax
0x180009469  jz      loc_180009532
0x18000946f  mov     [rsp+2310h+hKey], rdi
0x180009474  lea     rax, [rsp+2310h+hKey]
0x180009479  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000947e  mov     r9d, 20019h; samDesired
0x180009484  xor     r8d, r8d; ulOptions
0x180009487  mov     rdx, rsi; lpSubKey
0x18000948a  mov     rcx, r15; hKey
0x18000948d  call    cs:__imp_RegOpenKeyExW
0x180009494  nop     dword ptr [rax+rax+00h]
0x180009499  test    eax, eax
0x18000949b  jnz     short loc_1800094C0
0x18000949d  mov     eax, edi
0x18000949f  test    rbx, rbx
0x1800094a2  jz      short loc_1800094B3
0x1800094a4  mov     rcx, rbx; hKey
0x1800094a7  call    cs:__imp_RegCloseKey
0x1800094ae  nop     dword ptr [rax+rax+00h]
0x1800094b3  mov     rbx, [rsp+2310h+hKey]
0x1800094b8  mov     [rbp+2210h+var_2290], rbx
0x1800094bc  test    eax, eax
0x1800094be  jz      short loc_180009532
0x1800094c0  mov     dword ptr [rsp+2310h+hKey], edi
0x1800094c4  mov     [rsp+2310h+var_2298], rdi
0x1800094c9  lea     rax, [rsp+2310h+hKey]
0x1800094ce  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800094d3  lea     rax, [rsp+2310h+var_2298]
0x1800094d8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800094dd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800094e2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800094e7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800094eb  xor     r9d, r9d; lpClass
0x1800094ee  xor     r8d, r8d; Reserved
0x1800094f1  mov     rdx, rsi; lpSubKey
0x1800094f4  mov     rcx, r15; hKey
0x1800094f7  call    cs:__imp_RegCreateKeyExW
0x1800094fe  nop     dword ptr [rax+rax+00h]
0x180009503  test    eax, eax
0x180009505  jnz     loc_180009899
0x18000950b  mov     eax, edi
0x18000950d  test    rbx, rbx
0x180009510  jz      short loc_180009521
0x180009512  mov     rcx, rbx; hKey
0x180009515  call    cs:__imp_RegCloseKey
0x18000951c  nop     dword ptr [rax+rax+00h]
0x180009521  mov     rbx, [rsp+2310h+var_2298]
0x180009526  mov     [rbp+2210h+var_2290], rbx
0x18000952a  test    eax, eax
0x18000952c  jnz     loc_180009899
0x180009532  mov     rdx, rsi; unsigned __int16 *
0x180009535  mov     rcx, r13; this
0x180009538  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000953d  mov     edi, eax
0x18000953f  xor     ecx, ecx
0x180009541  test    eax, eax
0x180009543  js      loc_1800098A2
0x180009549  cmp     word ptr [rsi], 3Dh ; '='
0x18000954d  jnz     short loc_180009571
0x18000954f  mov     r9, rsi; unsigned __int16 *
0x180009552  xor     r8d, r8d; unsigned __int16 *
0x180009555  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180009559  mov     rcx, r13; this
0x18000955c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009561  mov     edi, eax
0x180009563  mov     rbx, [rbp+2210h+var_2290]
0x180009567  test    eax, eax
0x180009569  js      loc_1800098A2
0x18000956f  xor     ecx, ecx
0x180009571  mov     r12d, [rsp+2310h+var_22A8]
0x180009576  cmp     word ptr [rsi], 7Bh ; '{'
0x18000957a  jnz     loc_180009723
0x180009580  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009584  inc     rax
0x180009587  cmp     [rsi+rax*2], cx
  ... truncated ...
```
