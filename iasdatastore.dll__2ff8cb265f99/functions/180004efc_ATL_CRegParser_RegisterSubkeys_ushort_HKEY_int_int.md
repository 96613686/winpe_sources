# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004efc`
- end: `0x180005693`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004b88`
- `0x180004efc`

## callees

- `0x1800028fc`
- `0x180003138`
- `0x1800039a4`
- `0x1800040c8`
- `0x1800044c0`
- `0x180004a38`
- `0x180004efc`
- `0x180005928`
- `0x18000dd10`
- `0x18000ddd0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800053da`
- `msvcrt!wcsncpy_s` at `0x1800053da`
- `ADVAPI32!RegDeleteValueW` at `0x18000515f`
- `ADVAPI32!RegDeleteValueW` at `0x18000515f`
- `ADVAPI32!RegCreateKeyExW` at `0x180005297`
- `ADVAPI32!RegCreateKeyExW` at `0x180005297`
- `ADVAPI32!RegOpenKeyExW` at `0x180005142`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051f0`
- `ADVAPI32!RegOpenKeyExW` at `0x180005239`
- `ADVAPI32!RegOpenKeyExW` at `0x180005388`
- `ADVAPI32!RegOpenKeyExW` at `0x180005142`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051f0`
- `ADVAPI32!RegOpenKeyExW` at `0x180005239`
- `ADVAPI32!RegOpenKeyExW` at `0x180005388`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005506`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000559c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005506`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000559c`
- `ADVAPI32!RegCloseKey` at `0x180005178`
- `ADVAPI32!RegCloseKey` at `0x180005204`
- `ADVAPI32!RegCloseKey` at `0x18000524d`
- `ADVAPI32!RegCloseKey` at `0x1800052af`
- `ADVAPI32!RegCloseKey` at `0x1800053a3`
- `ADVAPI32!RegCloseKey` at `0x1800055ba`
- `ADVAPI32!RegCloseKey` at `0x180005614`
- `ADVAPI32!RegCloseKey` at `0x180005650`
- `ADVAPI32!RegCloseKey` at `0x180005660`
- `ADVAPI32!RegCloseKey` at `0x180005178`
- `ADVAPI32!RegCloseKey` at `0x180005204`
- `ADVAPI32!RegCloseKey` at `0x18000524d`
- `ADVAPI32!RegCloseKey` at `0x1800052af`
- `ADVAPI32!RegCloseKey` at `0x1800053a3`
- `ADVAPI32!RegCloseKey` at `0x1800055ba`
- `ADVAPI32!RegCloseKey` at `0x180005614`
- `ADVAPI32!RegCloseKey` at `0x180005650`
- `ADVAPI32!RegCloseKey` at `0x180005660`
- `KERNEL32!lstrcmpiW` at `0x180004f79`
- `KERNEL32!lstrcmpiW` at `0x180004f8c`
- `KERNEL32!lstrcmpiW` at `0x18000500a`
- `KERNEL32!lstrcmpiW` at `0x180005073`
- `KERNEL32!lstrcmpiW` at `0x1800050a1`
- `KERNEL32!lstrcmpiW` at `0x180005529`
- `KERNEL32!lstrcmpiW` at `0x180004f79`
- `KERNEL32!lstrcmpiW` at `0x180004f8c`
- `KERNEL32!lstrcmpiW` at `0x18000500a`
- `KERNEL32!lstrcmpiW` at `0x180005073`
- `KERNEL32!lstrcmpiW` at `0x1800050a1`
- `KERNEL32!lstrcmpiW` at `0x180005529`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004fde`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800051a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004fde`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800051a9`

## string_xrefs

- `0x180004f82`: `ForceRemove`
- `0x180005069`: `NoRemove`
- `0x180004f6f`: `Delete`

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
0x180004efc  push    rbp
0x180004efe  push    rbx
0x180004eff  push    rsi
0x180004f00  push    rdi
0x180004f01  push    r12
0x180004f03  push    r13
0x180004f05  push    r14
0x180004f07  push    r15
0x180004f09  lea     rbp, [rsp-21D8h]
0x180004f11  mov     eax, 22D8h
0x180004f16  call    _alloca_probe
0x180004f1b  sub     rsp, rax
0x180004f1e  mov     rax, cs:__security_cookie
0x180004f25  xor     rax, rsp
0x180004f28  mov     [rbp+2210h+var_50], rax
0x180004f2f  mov     r12d, r9d
0x180004f32  mov     [rsp+2310h+var_22A8], r9d
0x180004f37  mov     r15, r8
0x180004f3a  mov     [rsp+2310h+var_22A0], r8
0x180004f3f  mov     rsi, rdx
0x180004f42  mov     r13, rcx
0x180004f45  xor     eax, eax
0x180004f47  mov     ebx, eax
0x180004f49  mov     [rbp+2210h+var_2290], rax
0x180004f4d  mov     [rbp+2210h+var_2288], rax
0x180004f51  mov     [rbp+2210h+var_2280], rax
0x180004f55  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004f5a  mov     edi, eax
0x180004f5c  test    eax, eax
0x180004f5e  jns     short loc_180004F65
0x180004f60  jmp     loc_18000561C
0x180004f65  cmp     word ptr [rsi], 7Dh ; '}'
0x180004f69  jz      loc_18000560C
0x180004f6f  lea     rdx, String2; "Delete"
0x180004f76  mov     rcx, rsi; lpString1
0x180004f79  call    cs:__imp_lstrcmpiW
0x180004f7f  mov     r14d, eax
0x180004f82  lea     rdx, aForceremove; "ForceRemove"
0x180004f89  mov     rcx, rsi; lpString1
0x180004f8c  call    cs:__imp_lstrcmpiW
0x180004f92  xor     edi, edi
0x180004f94  test    eax, eax
0x180004f96  jz      short loc_180004FA1
0x180004f98  test    r14d, r14d
0x180004f9b  jnz     loc_180005063
0x180004fa1  mov     rdx, rsi; unsigned __int16 *
0x180004fa4  mov     rcx, r13; this
0x180004fa7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004fac  mov     edi, eax
0x180004fae  test    eax, eax
0x180004fb0  js      loc_18000560C
0x180004fb6  xor     edi, edi
0x180004fb8  test    r12d, r12d
0x180004fbb  jz      loc_180005063
0x180004fc1  mov     [rbp+2210h+var_2278], rdi
0x180004fc5  mov     [rbp+2210h+var_2270], rdi
0x180004fc9  mov     [rbp+2210h+var_2268], rdi
0x180004fcd  movzx   eax, word ptr [rsi]
0x180004fd0  test    ax, ax
0x180004fd3  jz      short loc_180004FFA
0x180004fd5  mov     rcx, rsi; lpsz
0x180004fd8  cmp     ax, 5Ch ; '\'
0x180004fdc  jz      short loc_180004FF1
0x180004fde  call    cs:__imp_CharNextW
0x180004fe4  mov     rcx, rax
0x180004fe7  movzx   eax, word ptr [rax]
0x180004fea  test    ax, ax
0x180004fed  jnz     short loc_180004FD8
0x180004fef  jmp     short loc_180004FFA
0x180004ff1  test    rcx, rcx
0x180004ff4  jnz     loc_180005658
0x180004ffa  mov     edx, edi
0x180004ffc  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180005003  mov     rdx, [rax+rdx*8]; lpString2
0x180005007  mov     rcx, rsi; lpString1
0x18000500a  call    cs:__imp_lstrcmpiW
0x180005010  test    eax, eax
0x180005012  jz      short loc_18000502B
0x180005014  inc     edi
0x180005016  cmp     edi, 0Ch
0x180005019  jl      short loc_180004FFA
0x18000501b  mov     [rbp+2210h+var_2278], r15
0x18000501f  mov     rdx, rsi; unsigned __int16 *
0x180005022  lea     rcx, [rbp+2210h+var_2278]; this
0x180005026  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000502b  xor     edi, edi
0x18000502d  test    r14d, r14d
0x180005030  jnz     short loc_180005063
0x180005032  mov     rdx, rsi; unsigned __int16 *
0x180005035  mov     rcx, r13; this
0x180005038  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000503d  mov     edi, eax
0x18000503f  test    eax, eax
0x180005041  js      loc_18000560C
0x180005047  mov     rdx, rsi; unsigned __int16 *
0x18000504a  mov     rcx, r13; this
0x18000504d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005052  mov     edi, eax
0x180005054  xor     ecx, ecx
0x180005056  test    eax, eax
0x180005058  js      loc_18000560C
0x18000505e  jmp     loc_18000530A
0x180005063  mov     r12d, 1
0x180005069  lea     rdx, aNoremove; "NoRemove"
0x180005070  mov     rcx, rsi; lpString1
0x180005073  call    cs:__imp_lstrcmpiW
0x180005079  test    eax, eax
0x18000507b  jnz     short loc_180005097
0x18000507d  mov     r12d, edi
0x180005080  mov     rdx, rsi; unsigned __int16 *
0x180005083  mov     rcx, r13; this
0x180005086  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000508b  mov     edi, eax
0x18000508d  test    eax, eax
0x18000508f  js      loc_18000560C
0x180005095  xor     edi, edi
0x180005097  lea     rdx, aVal; "Val"
0x18000509e  mov     rcx, rsi; lpString1
0x1800050a1  call    cs:__imp_lstrcmpiW
0x1800050a7  test    eax, eax
0x1800050a9  jnz     loc_180005198
0x1800050af  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800050b6  mov     rcx, r13; this
0x1800050b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050be  mov     edi, eax
0x1800050c0  test    eax, eax
0x1800050c2  js      loc_18000560C
0x1800050c8  mov     rdx, rsi; unsigned __int16 *
0x1800050cb  mov     rcx, r13; this
0x1800050ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050d3  mov     edi, eax
0x1800050d5  test    eax, eax
0x1800050d7  js      loc_18000560C
0x1800050dd  cmp     word ptr [rsi], 3Dh ; '='
0x1800050e1  jnz     loc_180005658
0x1800050e7  xor     edi, edi
0x1800050e9  cmp     [rsp+2310h+var_22A8], edi
0x1800050ed  jz      short loc_180005118
0x1800050ef  mov     [rbp+2210h+var_2270], rdi
0x1800050f3  mov     [rbp+2210h+var_2268], rdi
0x1800050f7  mov     [rbp+2210h+var_2278], r15
0x1800050fb  mov     r9, rsi; unsigned __int16 *
0x1800050fe  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005105  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005109  mov     rcx, r13; this
0x18000510c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005111  mov     edi, eax
0x180005113  jmp     loc_1800052FB
0x180005118  cmp     [rbp+2210h+arg_20], edi
0x18000511e  jnz     short loc_18000517E
0x180005120  test    r12d, r12d
0x180005123  jz      short loc_18000517E
0x180005125  mov     [rsp+2310h+hKey], rdi
0x18000512a  lea     rax, [rsp+2310h+hKey]
0x18000512f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005134  mov     r9d, 20006h; samDesired
0x18000513a  xor     r8d, r8d; ulOptions
0x18000513d  xor     edx, edx; lpSubKey
0x18000513f  mov     rcx, r15; hKey
0x180005142  call    cs:__imp_RegOpenKeyExW
0x180005148  test    eax, eax
0x18000514a  jnz     loc_180005603
0x180005150  mov     r14, [rsp+2310h+hKey]
0x180005155  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000515c  mov     rcx, r14; hKey
0x18000515f  call    cs:__imp_RegDeleteValueW
0x180005165  test    eax, 0FFFFFFFDh
0x18000516a  jnz     loc_18000563F
0x180005170  test    r14, r14
0x180005173  jz      short loc_18000517E
0x180005175  mov     rcx, r14; hKey
0x180005178  call    cs:__imp_RegCloseKey
0x18000517e  mov     rdx, rsi; unsigned __int16 *
0x180005181  mov     rcx, r13; this
0x180005184  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005189  mov     edi, eax
0x18000518b  test    eax, eax
0x18000518d  js      loc_18000560C
0x180005193  jmp     loc_1800054A5
0x180005198  movzx   eax, word ptr [rsi]
0x18000519b  test    ax, ax
0x18000519e  jz      short loc_1800051C5
0x1800051a0  mov     rcx, rsi; lpsz
0x1800051a3  cmp     ax, 5Ch ; '\'
0x1800051a7  jz      short loc_1800051BC
0x1800051a9  call    cs:__imp_CharNextW
0x1800051af  mov     rcx, rax
0x1800051b2  movzx   eax, word ptr [rax]
0x1800051b5  test    ax, ax
0x1800051b8  jnz     short loc_1800051A3
0x1800051ba  jmp     short loc_1800051C5
0x1800051bc  test    rcx, rcx
0x1800051bf  jnz     loc_180005658
0x1800051c5  cmp     [rsp+2310h+var_22A8], edi
0x1800051c9  jz      loc_18000535E
0x1800051cf  mov     [rsp+2310h+hKey], rdi
0x1800051d4  lea     rax, [rsp+2310h+hKey]
0x1800051d9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800051de  mov     r14d, 2001Fh
0x1800051e4  mov     r9d, r14d; samDesired
0x1800051e7  xor     r8d, r8d; ulOptions
0x1800051ea  mov     rdx, rsi; lpSubKey
0x1800051ed  mov     rcx, r15; hKey
0x1800051f0  call    cs:__imp_RegOpenKeyExW
0x1800051f6  test    eax, eax
0x1800051f8  jnz     short loc_18000521B
0x1800051fa  mov     eax, edi
0x1800051fc  test    rbx, rbx
0x1800051ff  jz      short loc_18000520A
0x180005201  mov     rcx, rbx; hKey
0x180005204  call    cs:__imp_RegCloseKey
0x18000520a  mov     rbx, [rsp+2310h+hKey]
0x18000520f  mov     [rbp+2210h+var_2290], rbx
0x180005213  test    eax, eax
0x180005215  jz      loc_1800052C6
0x18000521b  mov     [rsp+2310h+hKey], rdi
0x180005220  lea     rax, [rsp+2310h+hKey]
0x180005225  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000522a  mov     r9d, 20019h; samDesired
0x180005230  xor     r8d, r8d; ulOptions
0x180005233  mov     rdx, rsi; lpSubKey
0x180005236  mov     rcx, r15; hKey
0x180005239  call    cs:__imp_RegOpenKeyExW
0x18000523f  test    eax, eax
0x180005241  jnz     short loc_180005260
0x180005243  mov     eax, edi
0x180005245  test    rbx, rbx
0x180005248  jz      short loc_180005253
0x18000524a  mov     rcx, rbx; hKey
0x18000524d  call    cs:__imp_RegCloseKey
0x180005253  mov     rbx, [rsp+2310h+hKey]
0x180005258  mov     [rbp+2210h+var_2290], rbx
0x18000525c  test    eax, eax
0x18000525e  jz      short loc_1800052C6
0x180005260  mov     dword ptr [rsp+2310h+hKey], edi
0x180005264  mov     [rsp+2310h+var_2298], rdi
0x180005269  lea     rax, [rsp+2310h+hKey]
0x18000526e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180005273  lea     rax, [rsp+2310h+var_2298]
0x180005278  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000527d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180005282  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180005287  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000528b  xor     r9d, r9d; lpClass
0x18000528e  xor     r8d, r8d; Reserved
0x180005291  mov     rdx, rsi; lpSubKey
0x180005294  mov     rcx, r15; hKey
0x180005297  call    cs:__imp_RegCreateKeyExW
0x18000529d  test    eax, eax
0x18000529f  jnz     loc_180005603
0x1800052a5  mov     eax, edi
0x1800052a7  test    rbx, rbx
0x1800052aa  jz      short loc_1800052B5
0x1800052ac  mov     rcx, rbx; hKey
0x1800052af  call    cs:__imp_RegCloseKey
0x1800052b5  mov     rbx, [rsp+2310h+var_2298]
0x1800052ba  mov     [rbp+2210h+var_2290], rbx
0x1800052be  test    eax, eax
0x1800052c0  jnz     loc_180005603
0x1800052c6  mov     rdx, rsi; unsigned __int16 *
0x1800052c9  mov     rcx, r13; this
0x1800052cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052d1  mov     edi, eax
0x1800052d3  xor     ecx, ecx
0x1800052d5  test    eax, eax
0x1800052d7  js      loc_18000560C
0x1800052dd  cmp     word ptr [rsi], 3Dh ; '='
0x1800052e1  jnz     short loc_180005305
0x1800052e3  mov     r9, rsi; unsigned __int16 *
0x1800052e6  xor     r8d, r8d; unsigned __int16 *
0x1800052e9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800052ed  mov     rcx, r13; this
0x1800052f0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800052f5  mov     edi, eax
0x1800052f7  mov     rbx, [rbp+2210h+var_2290]
0x1800052fb  test    eax, eax
0x1800052fd  js      loc_18000560C
0x180005303  xor     ecx, ecx
0x180005305  mov     r12d, [rsp+2310h+var_22A8]
0x18000530a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000530e  jnz     loc_1800054A5
0x180005314  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005318  inc     rax
0x18000531b  cmp     [rsi+rax*2], cx
0x18000531f  jnz     short loc_180005318
0x180005321  cmp     rax, 1
0x180005325  jnz     loc_1800054A5
0x18000532b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180005333  mov     r9d, r12d; int
0x180005336  mov     r8, rbx; HKEY
0x180005339  mov     rdx, rsi; unsigned __int16 *
0x18000533c  mov     rcx, r13; this
0x18000533f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005344  mov     edi, eax
0x180005346  test    eax, eax
0x180005348  js      loc_18000560C
0x18000534e  mov     rdx, rsi; unsigned __int16 *
0x180005351  mov     rcx, r13; this
0x180005354  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005359  jmp     loc_180005189
  ... truncated ...
```
