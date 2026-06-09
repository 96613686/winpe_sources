# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004ef8`
- end: `0x18000572c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2100`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004b4c`
- `0x180004ef8`

## callees

- `0x1800030ec`
- `0x180003864`
- `0x18000418c`
- `0x1800042e0`
- `0x1800044c4`
- `0x1800049dc`
- `0x180004ef8`
- `0x18000574c`
- `0x18000df10`
- `0x18000dfd0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005442`
- `msvcrt!wcsncpy_s` at `0x180005442`
- `KERNEL32!lstrcmpiW` at `0x180004f75`
- `KERNEL32!lstrcmpiW` at `0x180004f8e`
- `KERNEL32!lstrcmpiW` at `0x180005018`
- `KERNEL32!lstrcmpiW` at `0x180005087`
- `KERNEL32!lstrcmpiW` at `0x1800050bb`
- `KERNEL32!lstrcmpiW` at `0x18000559d`
- `KERNEL32!lstrcmpiW` at `0x180004f75`
- `KERNEL32!lstrcmpiW` at `0x180004f8e`
- `KERNEL32!lstrcmpiW` at `0x180005018`
- `KERNEL32!lstrcmpiW` at `0x180005087`
- `KERNEL32!lstrcmpiW` at `0x1800050bb`
- `KERNEL32!lstrcmpiW` at `0x18000559d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005574`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005616`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005574`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005616`
- `ADVAPI32!RegOpenKeyExW` at `0x180005162`
- `ADVAPI32!RegOpenKeyExW` at `0x180005228`
- `ADVAPI32!RegOpenKeyExW` at `0x18000527d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800053e4`
- `ADVAPI32!RegOpenKeyExW` at `0x180005162`
- `ADVAPI32!RegOpenKeyExW` at `0x180005228`
- `ADVAPI32!RegOpenKeyExW` at `0x18000527d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800053e4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800052e7`
- `ADVAPI32!RegCreateKeyExW` at `0x1800052e7`
- `ADVAPI32!RegCloseKey` at `0x1800051a4`
- `ADVAPI32!RegCloseKey` at `0x180005242`
- `ADVAPI32!RegCloseKey` at `0x180005297`
- `ADVAPI32!RegCloseKey` at `0x180005305`
- `ADVAPI32!RegCloseKey` at `0x180005405`
- `ADVAPI32!RegCloseKey` at `0x18000563a`
- `ADVAPI32!RegCloseKey` at `0x18000569a`
- `ADVAPI32!RegCloseKey` at `0x1800056dd`
- `ADVAPI32!RegCloseKey` at `0x1800056f3`
- `ADVAPI32!RegCloseKey` at `0x1800051a4`
- `ADVAPI32!RegCloseKey` at `0x180005242`
- `ADVAPI32!RegCloseKey` at `0x180005297`
- `ADVAPI32!RegCloseKey` at `0x180005305`
- `ADVAPI32!RegCloseKey` at `0x180005405`
- `ADVAPI32!RegCloseKey` at `0x18000563a`
- `ADVAPI32!RegCloseKey` at `0x18000569a`
- `ADVAPI32!RegCloseKey` at `0x1800056dd`
- `ADVAPI32!RegCloseKey` at `0x1800056f3`
- `ADVAPI32!RegDeleteValueW` at `0x180005185`
- `ADVAPI32!RegDeleteValueW` at `0x180005185`
- `USER32!CharNextW` at `0x180004fe6`
- `USER32!CharNextW` at `0x1800051db`
- `USER32!CharNextW` at `0x180004fe6`
- `USER32!CharNextW` at `0x1800051db`

## string_xrefs

- `0x180004f84`: `ForceRemove`
- `0x18000507d`: `NoRemove`
- `0x180004f6b`: `Delete`

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
0x180004ef8  push    rbp
0x180004efa  push    rbx
0x180004efb  push    rsi
0x180004efc  push    rdi
0x180004efd  push    r12
0x180004eff  push    r13
0x180004f01  push    r14
0x180004f03  push    r15
0x180004f05  lea     rbp, [rsp-21D8h]
0x180004f0d  mov     eax, 22D8h
0x180004f12  call    _alloca_probe
0x180004f17  sub     rsp, rax
0x180004f1a  mov     rax, cs:__security_cookie
0x180004f21  xor     rax, rsp
0x180004f24  mov     [rbp+2210h+var_50], rax
0x180004f2b  mov     r12d, r9d
0x180004f2e  mov     [rsp+2310h+var_22A8], r9d
0x180004f33  mov     r15, r8
0x180004f36  mov     [rsp+2310h+var_22A0], r8
0x180004f3b  mov     rsi, rdx
0x180004f3e  mov     r13, rcx
0x180004f41  xor     eax, eax
0x180004f43  mov     ebx, eax
0x180004f45  mov     [rbp+2210h+var_2290], rax
0x180004f49  mov     [rbp+2210h+var_2288], rax
0x180004f4d  mov     [rbp+2210h+var_2280], rax
0x180004f51  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004f56  mov     edi, eax
0x180004f58  test    eax, eax
0x180004f5a  jns     short loc_180004F61
0x180004f5c  jmp     loc_1800056A8
0x180004f61  cmp     word ptr [rsi], 7Dh ; '}'
0x180004f65  jz      loc_180005692
0x180004f6b  lea     rdx, String2; "Delete"
0x180004f72  mov     rcx, rsi; lpString1
0x180004f75  call    cs:__imp_lstrcmpiW
0x180004f7c  nop     dword ptr [rax+rax+00h]
0x180004f81  mov     r14d, eax
0x180004f84  lea     rdx, aForceremove; "ForceRemove"
0x180004f8b  mov     rcx, rsi; lpString1
0x180004f8e  call    cs:__imp_lstrcmpiW
0x180004f95  nop     dword ptr [rax+rax+00h]
0x180004f9a  xor     edi, edi
0x180004f9c  test    eax, eax
0x180004f9e  jz      short loc_180004FA9
0x180004fa0  test    r14d, r14d
0x180004fa3  jnz     loc_180005077
0x180004fa9  mov     rdx, rsi; unsigned __int16 *
0x180004fac  mov     rcx, r13; this
0x180004faf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004fb4  mov     edi, eax
0x180004fb6  test    eax, eax
0x180004fb8  js      loc_180005692
0x180004fbe  xor     edi, edi
0x180004fc0  test    r12d, r12d
0x180004fc3  jz      loc_180005077
0x180004fc9  mov     [rbp+2210h+var_2278], rdi
0x180004fcd  mov     [rbp+2210h+var_2270], rdi
0x180004fd1  mov     [rbp+2210h+var_2268], rdi
0x180004fd5  movzx   eax, word ptr [rsi]
0x180004fd8  test    ax, ax
0x180004fdb  jz      short loc_180005008
0x180004fdd  mov     rcx, rsi; lpsz
0x180004fe0  cmp     ax, 5Ch ; '\'
0x180004fe4  jz      short loc_180004FFF
0x180004fe6  call    cs:__imp_CharNextW
0x180004fed  nop     dword ptr [rax+rax+00h]
0x180004ff2  mov     rcx, rax
0x180004ff5  movzx   eax, word ptr [rax]
0x180004ff8  test    ax, ax
0x180004ffb  jnz     short loc_180004FE0
0x180004ffd  jmp     short loc_180005008
0x180004fff  test    rcx, rcx
0x180005002  jnz     loc_1800056EB
0x180005008  mov     edx, edi
0x18000500a  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180005011  mov     rdx, [rax+rdx*8]; lpString2
0x180005015  mov     rcx, rsi; lpString1
0x180005018  call    cs:__imp_lstrcmpiW
0x18000501f  nop     dword ptr [rax+rax+00h]
0x180005024  test    eax, eax
0x180005026  jz      short loc_18000503F
0x180005028  inc     edi
0x18000502a  cmp     edi, 0Ch
0x18000502d  jl      short loc_180005008
0x18000502f  mov     [rbp+2210h+var_2278], r15
0x180005033  mov     rdx, rsi; unsigned __int16 *
0x180005036  lea     rcx, [rbp+2210h+var_2278]; this
0x18000503a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000503f  xor     edi, edi
0x180005041  test    r14d, r14d
0x180005044  jnz     short loc_180005077
0x180005046  mov     rdx, rsi; unsigned __int16 *
0x180005049  mov     rcx, r13; this
0x18000504c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005051  mov     edi, eax
0x180005053  test    eax, eax
0x180005055  js      loc_180005692
0x18000505b  mov     rdx, rsi; unsigned __int16 *
0x18000505e  mov     rcx, r13; this
0x180005061  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005066  mov     edi, eax
0x180005068  xor     ecx, ecx
0x18000506a  test    eax, eax
0x18000506c  js      loc_180005692
0x180005072  jmp     loc_180005366
0x180005077  mov     r12d, 1
0x18000507d  lea     rdx, aNoremove; "NoRemove"
0x180005084  mov     rcx, rsi; lpString1
0x180005087  call    cs:__imp_lstrcmpiW
0x18000508e  nop     dword ptr [rax+rax+00h]
0x180005093  test    eax, eax
0x180005095  jnz     short loc_1800050B1
0x180005097  mov     r12d, edi
0x18000509a  mov     rdx, rsi; unsigned __int16 *
0x18000509d  mov     rcx, r13; this
0x1800050a0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050a5  mov     edi, eax
0x1800050a7  test    eax, eax
0x1800050a9  js      loc_180005692
0x1800050af  xor     edi, edi
0x1800050b1  lea     rdx, aVal; "Val"
0x1800050b8  mov     rcx, rsi; lpString1
0x1800050bb  call    cs:__imp_lstrcmpiW
0x1800050c2  nop     dword ptr [rax+rax+00h]
0x1800050c7  test    eax, eax
0x1800050c9  jnz     loc_1800051CA
0x1800050cf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800050d6  mov     rcx, r13; this
0x1800050d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050de  mov     edi, eax
0x1800050e0  test    eax, eax
0x1800050e2  js      loc_180005692
0x1800050e8  mov     rdx, rsi; unsigned __int16 *
0x1800050eb  mov     rcx, r13; this
0x1800050ee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050f3  mov     edi, eax
0x1800050f5  test    eax, eax
0x1800050f7  js      loc_180005692
0x1800050fd  cmp     word ptr [rsi], 3Dh ; '='
0x180005101  jnz     loc_1800056EB
0x180005107  xor     edi, edi
0x180005109  cmp     [rsp+2310h+var_22A8], edi
0x18000510d  jz      short loc_180005138
0x18000510f  mov     [rbp+2210h+var_2270], rdi
0x180005113  mov     [rbp+2210h+var_2268], rdi
0x180005117  mov     [rbp+2210h+var_2278], r15
0x18000511b  mov     r9, rsi; unsigned __int16 *
0x18000511e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005125  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005129  mov     rcx, r13; this
0x18000512c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005131  mov     edi, eax
0x180005133  jmp     loc_180005357
0x180005138  cmp     [rbp+2210h+arg_20], edi
0x18000513e  jnz     short loc_1800051B0
0x180005140  test    r12d, r12d
0x180005143  jz      short loc_1800051B0
0x180005145  mov     [rsp+2310h+hKey], rdi
0x18000514a  lea     rax, [rsp+2310h+hKey]
0x18000514f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005154  mov     r9d, 20006h; samDesired
0x18000515a  xor     r8d, r8d; ulOptions
0x18000515d  xor     edx, edx; lpSubKey
0x18000515f  mov     rcx, r15; hKey
0x180005162  call    cs:__imp_RegOpenKeyExW
0x180005169  nop     dword ptr [rax+rax+00h]
0x18000516e  test    eax, eax
0x180005170  jnz     loc_180005689
0x180005176  mov     r14, [rsp+2310h+hKey]
0x18000517b  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180005182  mov     rcx, r14; hKey
0x180005185  call    cs:__imp_RegDeleteValueW
0x18000518c  nop     dword ptr [rax+rax+00h]
0x180005191  test    eax, 0FFFFFFFDh
0x180005196  jnz     loc_1800056CC
0x18000519c  test    r14, r14
0x18000519f  jz      short loc_1800051B0
0x1800051a1  mov     rcx, r14; hKey
0x1800051a4  call    cs:__imp_RegCloseKey
0x1800051ab  nop     dword ptr [rax+rax+00h]
0x1800051b0  mov     rdx, rsi; unsigned __int16 *
0x1800051b3  mov     rcx, r13; this
0x1800051b6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800051bb  mov     edi, eax
0x1800051bd  test    eax, eax
0x1800051bf  js      loc_180005692
0x1800051c5  jmp     loc_180005513
0x1800051ca  movzx   eax, word ptr [rsi]
0x1800051cd  test    ax, ax
0x1800051d0  jz      short loc_1800051FD
0x1800051d2  mov     rcx, rsi; lpsz
0x1800051d5  cmp     ax, 5Ch ; '\'
0x1800051d9  jz      short loc_1800051F4
0x1800051db  call    cs:__imp_CharNextW
0x1800051e2  nop     dword ptr [rax+rax+00h]
0x1800051e7  mov     rcx, rax
0x1800051ea  movzx   eax, word ptr [rax]
0x1800051ed  test    ax, ax
0x1800051f0  jnz     short loc_1800051D5
0x1800051f2  jmp     short loc_1800051FD
0x1800051f4  test    rcx, rcx
0x1800051f7  jnz     loc_1800056EB
0x1800051fd  cmp     [rsp+2310h+var_22A8], edi
0x180005201  jz      loc_1800053BA
0x180005207  mov     [rsp+2310h+hKey], rdi
0x18000520c  lea     rax, [rsp+2310h+hKey]
0x180005211  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005216  mov     r14d, 2001Fh
0x18000521c  mov     r9d, r14d; samDesired
0x18000521f  xor     r8d, r8d; ulOptions
0x180005222  mov     rdx, rsi; lpSubKey
0x180005225  mov     rcx, r15; hKey
0x180005228  call    cs:__imp_RegOpenKeyExW
0x18000522f  nop     dword ptr [rax+rax+00h]
0x180005234  test    eax, eax
0x180005236  jnz     short loc_18000525F
0x180005238  mov     eax, edi
0x18000523a  test    rbx, rbx
0x18000523d  jz      short loc_18000524E
0x18000523f  mov     rcx, rbx; hKey
0x180005242  call    cs:__imp_RegCloseKey
0x180005249  nop     dword ptr [rax+rax+00h]
0x18000524e  mov     rbx, [rsp+2310h+hKey]
0x180005253  mov     [rbp+2210h+var_2290], rbx
0x180005257  test    eax, eax
0x180005259  jz      loc_180005322
0x18000525f  mov     [rsp+2310h+hKey], rdi
0x180005264  lea     rax, [rsp+2310h+hKey]
0x180005269  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000526e  mov     r9d, 20019h; samDesired
0x180005274  xor     r8d, r8d; ulOptions
0x180005277  mov     rdx, rsi; lpSubKey
0x18000527a  mov     rcx, r15; hKey
0x18000527d  call    cs:__imp_RegOpenKeyExW
0x180005284  nop     dword ptr [rax+rax+00h]
0x180005289  test    eax, eax
0x18000528b  jnz     short loc_1800052B0
0x18000528d  mov     eax, edi
0x18000528f  test    rbx, rbx
0x180005292  jz      short loc_1800052A3
0x180005294  mov     rcx, rbx; hKey
0x180005297  call    cs:__imp_RegCloseKey
0x18000529e  nop     dword ptr [rax+rax+00h]
0x1800052a3  mov     rbx, [rsp+2310h+hKey]
0x1800052a8  mov     [rbp+2210h+var_2290], rbx
0x1800052ac  test    eax, eax
0x1800052ae  jz      short loc_180005322
0x1800052b0  mov     dword ptr [rsp+2310h+hKey], edi
0x1800052b4  mov     [rsp+2310h+var_2298], rdi
0x1800052b9  lea     rax, [rsp+2310h+hKey]
0x1800052be  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800052c3  lea     rax, [rsp+2310h+var_2298]
0x1800052c8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800052cd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800052d2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800052d7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800052db  xor     r9d, r9d; lpClass
0x1800052de  xor     r8d, r8d; Reserved
0x1800052e1  mov     rdx, rsi; lpSubKey
0x1800052e4  mov     rcx, r15; hKey
0x1800052e7  call    cs:__imp_RegCreateKeyExW
0x1800052ee  nop     dword ptr [rax+rax+00h]
0x1800052f3  test    eax, eax
0x1800052f5  jnz     loc_180005689
0x1800052fb  mov     eax, edi
0x1800052fd  test    rbx, rbx
0x180005300  jz      short loc_180005311
0x180005302  mov     rcx, rbx; hKey
0x180005305  call    cs:__imp_RegCloseKey
0x18000530c  nop     dword ptr [rax+rax+00h]
0x180005311  mov     rbx, [rsp+2310h+var_2298]
0x180005316  mov     [rbp+2210h+var_2290], rbx
0x18000531a  test    eax, eax
0x18000531c  jnz     loc_180005689
0x180005322  mov     rdx, rsi; unsigned __int16 *
0x180005325  mov     rcx, r13; this
0x180005328  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000532d  mov     edi, eax
0x18000532f  xor     ecx, ecx
0x180005331  test    eax, eax
0x180005333  js      loc_180005692
0x180005339  cmp     word ptr [rsi], 3Dh ; '='
0x18000533d  jnz     short loc_180005361
0x18000533f  mov     r9, rsi; unsigned __int16 *
0x180005342  xor     r8d, r8d; unsigned __int16 *
0x180005345  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180005349  mov     rcx, r13; this
0x18000534c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005351  mov     edi, eax
0x180005353  mov     rbx, [rbp+2210h+var_2290]
0x180005357  test    eax, eax
0x180005359  js      loc_180005692
0x18000535f  xor     ecx, ecx
0x180005361  mov     r12d, [rsp+2310h+var_22A8]
0x180005366  cmp     word ptr [rsi], 7Bh ; '{'
0x18000536a  jnz     loc_180005513
0x180005370  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005374  inc     rax
0x180005377  cmp     [rsi+rax*2], cx
  ... truncated ...
```
