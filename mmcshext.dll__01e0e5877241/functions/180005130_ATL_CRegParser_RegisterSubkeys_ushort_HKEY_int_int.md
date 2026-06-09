# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180005130`
- end: `0x180005a8c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2396`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180004d3c`
- `0x180005130`

## callees

- `0x180002fe8`
- `0x180004008`
- `0x180004598`
- `0x180004be8`
- `0x180005130`
- `0x180006074`
- `0x180006510`
- `0x18000a5b0`

## import_xrefs

- `msvcrt!malloc` at `0x1800055ec`
- `msvcrt!malloc` at `0x1800056df`
- `msvcrt!malloc` at `0x1800055ec`
- `msvcrt!malloc` at `0x1800056df`
- `msvcrt!free` at `0x180005727`
- `msvcrt!free` at `0x180005732`
- `msvcrt!free` at `0x180005952`
- `msvcrt!free` at `0x18000596a`
- `msvcrt!free` at `0x1800059bb`
- `msvcrt!free` at `0x1800059e2`
- `msvcrt!free` at `0x180005a06`
- `msvcrt!free` at `0x180005a2a`
- `msvcrt!free` at `0x180005a44`
- `msvcrt!free` at `0x180005a5c`
- `msvcrt!free` at `0x180005727`
- `msvcrt!free` at `0x180005732`
- `msvcrt!free` at `0x180005952`
- `msvcrt!free` at `0x18000596a`
- `msvcrt!free` at `0x1800059bb`
- `msvcrt!free` at `0x1800059e2`
- `msvcrt!free` at `0x180005a06`
- `msvcrt!free` at `0x180005a2a`
- `msvcrt!free` at `0x180005a44`
- `msvcrt!free` at `0x180005a5c`
- `USER32!CharNextW` at `0x18000521c`
- `USER32!CharNextW` at `0x1800053e3`
- `USER32!CharNextW` at `0x18000521c`
- `USER32!CharNextW` at `0x1800053e3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800053a0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800053a0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180005713`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180005713`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005670`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800056bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005815`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005670`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800056bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005815`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005385`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005428`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005472`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000558f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005385`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005428`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005472`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000558f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000592f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000598f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000592f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000598f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800054d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800054d1`
- `KERNEL32!lstrcpynW` at `0x180005627`
- `KERNEL32!lstrcpynW` at `0x180005627`
- `KERNEL32!lstrcmpiW` at `0x1800051b6`
- `KERNEL32!lstrcmpiW` at `0x1800051c9`
- `KERNEL32!lstrcmpiW` at `0x180005248`
- `KERNEL32!lstrcmpiW` at `0x1800052a5`
- `KERNEL32!lstrcmpiW` at `0x1800052d3`
- `KERNEL32!lstrcmpiW` at `0x18000551c`
- `KERNEL32!lstrcmpiW` at `0x180005836`
- `KERNEL32!lstrcmpiW` at `0x1800051b6`
- `KERNEL32!lstrcmpiW` at `0x1800051c9`
- `KERNEL32!lstrcmpiW` at `0x180005248`
- `KERNEL32!lstrcmpiW` at `0x1800052a5`
- `KERNEL32!lstrcmpiW` at `0x1800052d3`
- `KERNEL32!lstrcmpiW` at `0x18000551c`
- `KERNEL32!lstrcmpiW` at `0x180005836`

## string_xrefs

- `0x1800051bf`: `ForceRemove`
- `0x18000529b`: `NoRemove`
- `0x1800051ac`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  _QWORD *v7; // rbx
  HKEY v8; // rsi
  __int64 result; // rax
  signed int Token; // edi
  int v11; // r13d
  int v12; // r15d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // eax
  unsigned __int64 v17; // rdx
  LSTATUS v18; // eax
  HKEY v19; // r15
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  HKEY v24; // rdi
  bool v25; // r15
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  WCHAR *v30; // r15
  void *v31; // rsp
  _QWORD *v32; // rax
  _WORD *v33; // rdi
  __int64 v34; // rdi
  LSTATUS v35; // eax
  __int64 v36; // rax
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  char v45; // [rsp+40h] [rbp-210h] BYREF
  DWORD dwDisposition; // [rsp+250h] [rbp+0h] BYREF
  HKEY phkResult; // [rsp+258h] [rbp+8h] BYREF
  int v48; // [rsp+260h] [rbp+10h]
  HKEY hKey; // [rsp+268h] [rbp+18h]
  int v50; // [rsp+270h] [rbp+20h]
  LPWSTR lpString1; // [rsp+278h] [rbp+28h]
  HKEY v52; // [rsp+280h] [rbp+30h] BYREF
  __int64 v53; // [rsp+288h] [rbp+38h]
  __int64 v54; // [rsp+290h] [rbp+40h]
  int v55; // [rsp+298h] [rbp+48h]
  _QWORD v56[3]; // [rsp+2A0h] [rbp+50h] BYREF
  _QWORD *v57; // [rsp+2B8h] [rbp+68h]
  WCHAR ValueName[264]; // [rsp+2C0h] [rbp+70h] BYREF

  v48 = a4;
  hKey = a3;
  v7 = 0;
  v57 = 0;
  v8 = 0;
  memset(v56, 0, sizeof(v56));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  lpString1 = 0;
  v50 = 1;
  v11 = a5;
  v55 = a5;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( *a2 == 125 )
        goto LABEL_117;
      v12 = lstrcmpiW(a2, L"Delete");
      if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
        v13 = 0;
        if ( v48 )
        {
          v52 = 0;
          v53 = 0;
          v54 = 0;
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
              if ( v8 )
                RegCloseKey(v8);
              while ( v7 )
              {
                v37 = v7;
                v7 = (_QWORD *)*v7;
                free(v37);
              }
              return 2147614729LL;
            }
            v15 = CharNextW(v15);
            v14 = *v15;
          }
          while ( *v15 );
LABEL_13:
          while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
          {
            if ( ++v13 >= 2 )
            {
              v52 = hKey;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v52, a2);
              break;
            }
          }
          if ( !v12 )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              goto LABEL_117;
            v16 = ATL::CRegParser::SkipAssignment(this, a2);
            Token = v16;
            goto LABEL_107;
          }
        }
      }
      if ( !lstrcmpiW(a2, L"NoRemove") )
      {
        v50 = 0;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
      }
      if ( lstrcmpiW(a2, L"Val") )
        break;
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_117;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      if ( *a2 != 61 )
      {
        if ( v8 )
          RegCloseKey(v8);
        while ( v7 )
        {
          v39 = v7;
          v7 = (_QWORD *)*v7;
          free(v39);
        }
        return 2147614729LL;
      }
      if ( v48 )
      {
        v53 = 0;
        v54 = 0;
        v52 = hKey;
        Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v52, ValueName, a2, 0);
        if ( Token < 0 )
        {
          if ( v8 )
            RegCloseKey(v8);
          while ( v7 )
          {
            v38 = v7;
            v7 = (_QWORD *)*v7;
            free(v38);
          }
          return (unsigned int)Token;
        }
LABEL_108:
        if ( v48 )
        {
          if ( *a2 == 123 )
          {
            v36 = -1;
            do
              ++v36;
            while ( a2[v36] );
            if ( v36 == 1 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, a2, v8, v48, 0);
              if ( Token < 0 )
                goto LABEL_117;
              goto LABEL_114;
            }
          }
        }
      }
      else
      {
        if ( !v11 )
        {
          phkResult = 0;
          v18 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &phkResult);
          Token = v18;
          if ( v18 )
          {
            if ( v18 > 0 )
              Token = (unsigned __int16)v18 | 0x80070000;
          }
          else
          {
            v19 = phkResult;
            v20 = RegDeleteValueW(phkResult, ValueName);
            Token = v20;
            if ( (v20 & 0xFFFFFFFD) == 0 )
            {
              if ( v19 )
                RegCloseKey(v19);
              goto LABEL_35;
            }
            if ( v20 > 0 )
              Token = (unsigned __int16)v20 | 0x80070000;
            if ( v19 )
              RegCloseKey(v19);
          }
LABEL_117:
          if ( v8 )
            RegCloseKey(v8);
          while ( v7 )
          {
            v44 = v7;
            v7 = (_QWORD *)*v7;
            free(v44);
          }
          return (unsigned int)Token;
        }
LABEL_35:
        v21 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_115:
        Token = v21;
        if ( v21 < 0 )
          goto LABEL_117;
      }
    }
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextW(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_42;
      }
      if ( v23 )
      {
        if ( v8 )
          RegCloseKey(v8);
        while ( v7 )
        {
          v40 = v7;
          v7 = (_QWORD *)*v7;
          free(v40);
        }
        return 2147614729LL;
      }
    }
LABEL_42:
    if ( v48 )
    {
      phkResult = 0;
      v24 = hKey;
      v25 = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, &phkResult) )
        goto LABEL_169;
      v26 = 0;
      if ( v8 )
        v26 = RegCloseKey(v8);
      v8 = phkResult;
      v56[0] = phkResult;
      if ( v26 )
      {
LABEL_169:
        phkResult = 0;
        if ( RegOpenKeyExW(v24, a2, 0, 0x20019u, &phkResult) )
          goto LABEL_170;
        v27 = 0;
        if ( v8 )
          v27 = RegCloseKey(v8);
        v8 = phkResult;
        v56[0] = phkResult;
        if ( v27 )
        {
LABEL_170:
          dwDisposition = 0;
          phkResult = 0;
          if ( RegCreateKeyExW(v24, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
            goto LABEL_148;
          v28 = 0;
          if ( v8 )
            v28 = RegCloseKey(v8);
          v8 = phkResult;
          v56[0] = phkResult;
          if ( v28 )
          {
LABEL_148:
            if ( v8 )
              RegCloseKey(v8);
            while ( v7 )
            {
              v41 = v7;
              v7 = (_QWORD *)*v7;
              free(v41);
            }
            return 2147614729LL;
          }
        }
      }
      if ( ((*a2 - 76) & 0xFFDF) == 0 )
        v25 = lstrcmpiW(a2, L"LocalServer32") == 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      if ( *a2 != 61 )
        goto LABEL_108;
      v16 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v56, 0, a2, v25);
      goto LABEL_106;
    }
    if ( !v11 )
    {
      phkResult = 0;
      if ( RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult) )
        goto LABEL_65;
      v29 = 0;
      if ( v8 )
        v29 = RegCloseKey(v8);
      v8 = phkResult;
      v56[0] = phkResult;
      if ( v29 )
LABEL_65:
        v11 = 1;
    }
    v30 = lpString1;
    if ( !lpString1 )
      break;
LABEL_74:
    lstrcpynW(v30, a2, 260);
    if ( !v11 )
    {
      dwDisposition = 0;
      if ( RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) < 0 || !dwDisposition )
      {
        dwDisposition = 0;
        if ( RegQueryInfoKeyW(v8, 0, 0, 0, 0, 0, 0, &dwDisposition, 0, 0, 0, 0) )
          goto LABEL_100;
        if ( dwDisposition == 1 )
        {
          LODWORD(phkResult) = 4096;
          v33 = malloc(0x2000u);
          if ( !v33 )
            goto LABEL_100;
          if ( RegEnumValueW(v8, 0, v33, (LPDWORD)&phkResult, 0, 0, 0, 0) || !*v33 )
          {
            free(v33);
            goto LABEL_100;
          }
          free(v33);
        }
        else if ( !dwDisposition )
        {
          goto LABEL_100;
        }
      }
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_117;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_117;
    if ( *a2 == 123 )
    {
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v8, 0, v11);
      if ( Token < 0 )
        goto LABEL_117;
      if ( !v11 )
      {
LABEL_94:
        dwDisposition = 0;
        if ( RegQueryInfoKeyW(v8, 0, 0, 0, &dwDisposition, 0, 0, 0, 0, 0, 0, 0) >= 0 && dwDisposition )
        {
          v34 = 0;
          while ( lstrcmpiW(v30, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v34]) )
          {
            v34 = (unsigned int)(v34 + 1);
            if ( (int)v34 >= 2 )
            {
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v56, v30);
              v8 = (HKEY)v56[0];
              break;
            }
          }
LABEL_114:
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_115;
        }
LABEL_100:
        if ( v8 )
        {
          v35 = RegCloseKey(v8);
          v8 = 0;
          v56[0] = 0;
          if ( v35 )
          {
            while ( v7 )
            {
              v43 = v7;
              v7 = (_QWORD *)*v7;
              free(v43);
            }
            return 2147614729LL;
          }
        }
        if ( v50 )
        {
          v53 = 0;
          v54 = 0;
          v52 = hKey;
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v52, v30);
        }
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_117;
        v16 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_106:
        Token = v16;
LABEL_107:
        if ( v16 < 0 )
          goto LABEL_117;
        goto LABEL_108;
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      Token = ATL::CRegParser::SkipAssignment(this, a2);
      if ( Token < 0 )
        goto LABEL_117;
      v11 = v55;
    }
    else if ( !v11 )
    {
      goto LABEL_94;
    }
  }
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
  {
    v31 = alloca(528);
    v30 = (WCHAR *)&v45;
  }
  else
  {
    v32 = malloc(0x218u);
    if ( !v32 )
    {
      v30 = 0;
      lpString1 = 0;
      goto LABEL_73;
    }
    *v32 = v7;
    v7 = v32;
    v57 = v32;
    v30 = (WCHAR *)(v32 + 2);
  }
  lpString1 = v30;
LABEL_73:
  if ( v30 )
    goto LABEL_74;
  if ( v8 )
    RegCloseKey(v8);
  while ( v7 )
  {
    v42 = v7;
    v7 = (_QWORD *)*v7;
    free(v42);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180005130  push    rbp
0x180005132  push    rbx
0x180005133  push    rsi
0x180005134  push    rdi
0x180005135  push    r12
0x180005137  push    r13
0x180005139  push    r14
0x18000513b  push    r15
0x18000513d  sub     rsp, 2F8h
0x180005144  lea     rbp, [rsp+60h]
0x180005149  mov     rax, cs:__security_cookie
0x180005150  xor     rax, rbp
0x180005153  mov     [rbp+2D0h+var_50], rax
0x18000515a  mov     [rbp+2D0h+var_2C0], r9d
0x18000515e  mov     [rbp+2D0h+hKey], r8
0x180005162  mov     r14, rdx
0x180005165  mov     r12, rcx
0x180005168  xor     r13d, r13d
0x18000516b  mov     ebx, r13d
0x18000516e  mov     [rbp+2D0h+var_268], rbx
0x180005172  mov     esi, r13d
0x180005175  mov     [rbp+2D0h+var_280], r13
0x180005179  mov     [rbp+2D0h+var_278], r13
0x18000517d  mov     [rbp+2D0h+var_270], r13
0x180005181  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005186  mov     edi, eax
0x180005188  test    eax, eax
0x18000518a  jns     short loc_180005191
0x18000518c  jmp     loc_180005A69
0x180005191  mov     [rbp+2D0h+lpString1], r13
0x180005195  mov     [rbp+2D0h+var_2B0], 1
0x18000519c  mov     r13d, [rbp+2D0h+arg_20]
0x1800051a3  mov     [rbp+2D0h+var_288], r13d
0x1800051a7  jmp     loc_18000591C
0x1800051ac  lea     rdx, aDelete; "Delete"
0x1800051b3  mov     rcx, r14; lpString1
0x1800051b6  call    cs:__imp_lstrcmpiW
0x1800051bc  mov     r15d, eax
0x1800051bf  lea     rdx, aForceremove; "ForceRemove"
0x1800051c6  mov     rcx, r14; lpString1
0x1800051c9  call    cs:__imp_lstrcmpiW
0x1800051cf  xor     edi, edi
0x1800051d1  test    eax, eax
0x1800051d3  jz      short loc_1800051DE
0x1800051d5  test    r15d, r15d
0x1800051d8  jnz     loc_18000529B
0x1800051de  mov     rdx, r14; unsigned __int16 *
0x1800051e1  mov     rcx, r12; this
0x1800051e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800051e9  mov     edi, eax
0x1800051eb  test    eax, eax
0x1800051ed  js      loc_180005927
0x1800051f3  xor     edi, edi
0x1800051f5  cmp     [rbp+2D0h+var_2C0], edi
0x1800051f8  jz      loc_18000529B
0x1800051fe  mov     [rbp+2D0h+var_2A0], rdi
0x180005202  mov     [rbp+2D0h+var_298], rdi
0x180005206  mov     [rbp+2D0h+var_290], rdi
0x18000520a  movzx   eax, word ptr [r14]
0x18000520e  test    ax, ax
0x180005211  jz      short loc_180005238
0x180005213  mov     rcx, r14; lpsz
0x180005216  cmp     ax, 5Ch ; '\'
0x18000521a  jz      short loc_18000522F
0x18000521c  call    cs:__imp_CharNextW
0x180005222  mov     rcx, rax
0x180005225  movzx   eax, word ptr [rax]
0x180005228  test    ax, ax
0x18000522b  jnz     short loc_180005216
0x18000522d  jmp     short loc_180005238
0x18000522f  test    rcx, rcx
0x180005232  jnz     loc_18000593B
0x180005238  mov     edx, edi
0x18000523a  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x180005241  mov     rdx, [rax+rdx*8]; lpString2
0x180005245  mov     rcx, r14; lpString1
0x180005248  call    cs:__imp_lstrcmpiW
0x18000524e  test    eax, eax
0x180005250  jz      short loc_18000526D
0x180005252  inc     edi
0x180005254  cmp     edi, 2
0x180005257  jl      short loc_180005238
0x180005259  mov     rax, [rbp+2D0h+hKey]
0x18000525d  mov     [rbp+2D0h+var_2A0], rax
0x180005261  mov     rdx, r14; unsigned __int16 *
0x180005264  lea     rcx, [rbp+2D0h+var_2A0]; this
0x180005268  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000526d  xor     edi, edi
0x18000526f  test    r15d, r15d
0x180005272  jnz     short loc_18000529B
0x180005274  mov     rdx, r14; unsigned __int16 *
0x180005277  mov     rcx, r12; this
0x18000527a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000527f  mov     edi, eax
0x180005281  test    eax, eax
0x180005283  js      loc_180005962
0x180005289  mov     rdx, r14; unsigned __int16 *
0x18000528c  mov     rcx, r12; this
0x18000528f  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005294  mov     edi, eax
0x180005296  jmp     loc_1800058C8
0x18000529b  lea     rdx, aNoremove; "NoRemove"
0x1800052a2  mov     rcx, r14; lpString1
0x1800052a5  call    cs:__imp_lstrcmpiW
0x1800052ab  test    eax, eax
0x1800052ad  jnz     short loc_1800052C9
0x1800052af  mov     [rbp+2D0h+var_2B0], edi
0x1800052b2  mov     rdx, r14; unsigned __int16 *
0x1800052b5  mov     rcx, r12; this
0x1800052b8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052bd  mov     edi, eax
0x1800052bf  test    eax, eax
0x1800052c1  js      loc_180005927
0x1800052c7  xor     edi, edi
0x1800052c9  lea     rdx, aVal; "Val"
0x1800052d0  mov     rcx, r14; lpString1
0x1800052d3  call    cs:__imp_lstrcmpiW
0x1800052d9  test    eax, eax
0x1800052db  jnz     loc_1800053D1
0x1800052e1  lea     rdx, [rbp+2D0h+ValueName]; unsigned __int16 *
0x1800052e5  mov     rcx, r12; this
0x1800052e8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052ed  mov     edi, eax
0x1800052ef  test    eax, eax
0x1800052f1  js      loc_180005927
0x1800052f7  mov     rdx, r14; unsigned __int16 *
0x1800052fa  mov     rcx, r12; this
0x1800052fd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005302  mov     edi, eax
0x180005304  test    eax, eax
0x180005306  js      loc_180005927
0x18000530c  cmp     word ptr [r14], 3Dh ; '='
0x180005311  jnz     loc_1800059A4
0x180005317  xor     edi, edi
0x180005319  cmp     [rbp+2D0h+var_2C0], edi
0x18000531c  jz      short loc_180005364
0x18000531e  mov     [rbp+2D0h+var_298], rdi
0x180005322  mov     [rbp+2D0h+var_290], rdi
0x180005326  mov     rax, [rbp+2D0h+hKey]
0x18000532a  mov     [rbp+2D0h+var_2A0], rax
0x18000532e  mov     byte ptr [rsp+330h+phkResult], dil; bool
0x180005333  mov     r9, r14; unsigned __int16 *
0x180005336  lea     r8, [rbp+2D0h+ValueName]; unsigned __int16 *
0x18000533a  lea     rdx, [rbp+2D0h+var_2A0]; struct ATL::CRegKey *
0x18000533e  mov     rcx, r12; this
0x180005341  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180005346  mov     edi, eax
0x180005348  test    eax, eax
0x18000534a  jns     loc_1800058CC
0x180005350  test    rsi, rsi
0x180005353  jz      short loc_18000535F
0x180005355  mov     rcx, rsi; hKey
0x180005358  call    cs:__imp_RegCloseKey
0x18000535e  nop
0x18000535f  jmp     loc_180005970
0x180005364  test    r13d, r13d
0x180005367  jnz     short loc_1800053C1
0x180005369  mov     [rbp+2D0h+var_2C8], rdi
0x18000536d  lea     rax, [rbp+2D0h+var_2C8]
0x180005371  mov     [rsp+330h+phkResult], rax; phkResult
0x180005376  mov     r9d, 20006h; samDesired
0x18000537c  xor     r8d, r8d; ulOptions
0x18000537f  xor     edx, edx; lpSubKey
0x180005381  mov     rcx, [rbp+2D0h+hKey]; hKey
0x180005385  call    cs:__imp_RegOpenKeyExW
0x18000538b  mov     edi, eax
0x18000538d  test    eax, eax
0x18000538f  jnz     loc_180005997
0x180005395  mov     r15, [rbp+2D0h+var_2C8]
0x180005399  lea     rdx, [rbp+2D0h+ValueName]; lpValueName
0x18000539d  mov     rcx, r15; hKey
0x1800053a0  call    cs:__imp_RegDeleteValueW
0x1800053a6  mov     edi, eax
0x1800053a8  test    eax, 0FFFFFFFDh
0x1800053ad  jnz     loc_18000597A
0x1800053b3  test    r15, r15
0x1800053b6  jz      short loc_1800053C1
0x1800053b8  mov     rcx, r15; hKey
0x1800053bb  call    cs:__imp_RegCloseKey
0x1800053c1  mov     rdx, r14; unsigned __int16 *
0x1800053c4  mov     rcx, r12; this
0x1800053c7  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800053cc  jmp     loc_180005916
0x1800053d1  movzx   eax, word ptr [r14]
0x1800053d5  test    ax, ax
0x1800053d8  jz      short loc_1800053FF
0x1800053da  mov     rcx, r14; lpsz
0x1800053dd  cmp     ax, 5Ch ; '\'
0x1800053e1  jz      short loc_1800053F6
0x1800053e3  call    cs:__imp_CharNextW
0x1800053e9  mov     rcx, rax
0x1800053ec  movzx   eax, word ptr [rax]
0x1800053ef  test    ax, ax
0x1800053f2  jnz     short loc_1800053DD
0x1800053f4  jmp     short loc_1800053FF
0x1800053f6  test    rcx, rcx
0x1800053f9  jnz     loc_1800059CB
0x1800053ff  cmp     [rbp+2D0h+var_2C0], edi
0x180005402  jz      loc_18000556D
0x180005408  mov     [rbp+2D0h+var_2C8], rdi
0x18000540c  lea     rax, [rbp+2D0h+var_2C8]
0x180005410  mov     [rsp+330h+phkResult], rax; phkResult
0x180005415  mov     r9d, 0F003Fh; samDesired
0x18000541b  xor     r8d, r8d; ulOptions
0x18000541e  mov     rdx, r14; lpSubKey
0x180005421  mov     rdi, [rbp+2D0h+hKey]
0x180005425  mov     rcx, rdi; hKey
0x180005428  call    cs:__imp_RegOpenKeyExW
0x18000542e  xor     r15d, r15d
0x180005431  test    eax, eax
0x180005433  jnz     short loc_180005456
0x180005435  mov     eax, r15d
0x180005438  test    rsi, rsi
0x18000543b  jz      short loc_180005446
0x18000543d  mov     rcx, rsi; hKey
0x180005440  call    cs:__imp_RegCloseKey
0x180005446  mov     rsi, [rbp+2D0h+var_2C8]
0x18000544a  mov     [rbp+2D0h+var_280], rsi
0x18000544e  test    eax, eax
0x180005450  jz      loc_180005500
0x180005456  mov     [rbp+2D0h+var_2C8], r15
0x18000545a  lea     rax, [rbp+2D0h+var_2C8]
0x18000545e  mov     [rsp+330h+phkResult], rax; phkResult
0x180005463  mov     r9d, 20019h; samDesired
0x180005469  xor     r8d, r8d; ulOptions
0x18000546c  mov     rdx, r14; lpSubKey
0x18000546f  mov     rcx, rdi; hKey
0x180005472  call    cs:__imp_RegOpenKeyExW
0x180005478  test    eax, eax
0x18000547a  jnz     short loc_180005499
0x18000547c  mov     eax, r15d
0x18000547f  test    rsi, rsi
0x180005482  jz      short loc_18000548D
0x180005484  mov     rcx, rsi; hKey
0x180005487  call    cs:__imp_RegCloseKey
0x18000548d  mov     rsi, [rbp+2D0h+var_2C8]
0x180005491  mov     [rbp+2D0h+var_280], rsi
0x180005495  test    eax, eax
0x180005497  jz      short loc_180005500
0x180005499  mov     [rbp+2D0h+dwDisposition], r15d
0x18000549d  mov     [rbp+2D0h+var_2C8], r15
0x1800054a1  lea     rax, [rbp+2D0h+dwDisposition]
0x1800054a5  mov     [rsp+330h+lpdwDisposition], rax; lpdwDisposition
0x1800054aa  lea     rax, [rbp+2D0h+var_2C8]
0x1800054ae  mov     [rsp+330h+var_2F8], rax; phkResult
0x1800054b3  mov     [rsp+330h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800054b8  mov     [rsp+330h+samDesired], 2001Fh; samDesired
0x1800054c0  mov     dword ptr [rsp+330h+phkResult], r15d; dwOptions
0x1800054c5  xor     r9d, r9d; lpClass
0x1800054c8  xor     r8d, r8d; Reserved
0x1800054cb  mov     rdx, r14; lpSubKey
0x1800054ce  mov     rcx, rdi; hKey
0x1800054d1  call    cs:__imp_RegCreateKeyExW
0x1800054d7  test    eax, eax
0x1800054d9  jnz     loc_1800059EF
0x1800054df  mov     eax, r15d
0x1800054e2  test    rsi, rsi
0x1800054e5  jz      short loc_1800054F0
0x1800054e7  mov     rcx, rsi; hKey
0x1800054ea  call    cs:__imp_RegCloseKey
0x1800054f0  mov     rsi, [rbp+2D0h+var_2C8]
0x1800054f4  mov     [rbp+2D0h+var_280], rsi
0x1800054f8  test    eax, eax
0x1800054fa  jnz     loc_1800059EF
0x180005500  movzx   eax, word ptr [r14]
0x180005504  sub     ax, 4Ch ; 'L'
0x180005508  mov     ecx, 0FFDFh
0x18000550d  test    cx, ax
0x180005510  jnz     short loc_180005531
0x180005512  lea     rdx, aLocalserver32; "LocalServer32"
0x180005519  mov     rcx, r14; lpString1
0x18000551c  call    cs:__imp_lstrcmpiW
0x180005522  movzx   r15d, r15b
0x180005526  test    eax, eax
0x180005528  mov     eax, 1
0x18000552d  cmovz   r15d, eax
0x180005531  mov     rdx, r14; unsigned __int16 *
0x180005534  mov     rcx, r12; this
0x180005537  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000553c  mov     edi, eax
0x18000553e  test    eax, eax
0x180005540  js      loc_180005927
0x180005546  cmp     word ptr [r14], 3Dh ; '='
0x18000554b  jnz     loc_1800058CC
0x180005551  mov     byte ptr [rsp+330h+phkResult], r15b; bool
0x180005556  mov     r9, r14; unsigned __int16 *
0x180005559  xor     r8d, r8d; unsigned __int16 *
0x18000555c  lea     rdx, [rbp+2D0h+var_280]; struct ATL::CRegKey *
0x180005560  mov     rcx, r12; this
0x180005563  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180005568  jmp     loc_1800058C6
0x18000556d  test    r13d, r13d
0x180005570  jnz     short loc_1800055BB
0x180005572  mov     [rbp+2D0h+var_2C8], rdi
0x180005576  lea     rax, [rbp+2D0h+var_2C8]
0x18000557a  mov     [rsp+330h+phkResult], rax; phkResult
0x18000557f  mov     r9d, 20019h; samDesired
0x180005585  xor     r8d, r8d; ulOptions
0x180005588  mov     rdx, r14; lpSubKey
0x18000558b  mov     rcx, [rbp+2D0h+hKey]; hKey
  ... truncated ...
```
