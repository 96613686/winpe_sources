# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180011038`
- end: `0x180011994`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2396`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180010c3c`
- `0x180011038`

## callees

- `0x18000e3f4`
- `0x1800100a8`
- `0x1800101d0`
- `0x180010ae8`
- `0x180011038`
- `0x180012064`
- `0x1800124b0`
- `0x180012b40`

## import_xrefs

- `msvcrt!free` at `0x18001162f`
- `msvcrt!free` at `0x18001163a`
- `msvcrt!free` at `0x18001185a`
- `msvcrt!free` at `0x180011872`
- `msvcrt!free` at `0x1800118c3`
- `msvcrt!free` at `0x1800118ea`
- `msvcrt!free` at `0x18001190e`
- `msvcrt!free` at `0x180011932`
- `msvcrt!free` at `0x18001194c`
- `msvcrt!free` at `0x180011964`
- `msvcrt!free` at `0x18001162f`
- `msvcrt!free` at `0x18001163a`
- `msvcrt!free` at `0x18001185a`
- `msvcrt!free` at `0x180011872`
- `msvcrt!free` at `0x1800118c3`
- `msvcrt!free` at `0x1800118ea`
- `msvcrt!free` at `0x18001190e`
- `msvcrt!free` at `0x180011932`
- `msvcrt!free` at `0x18001194c`
- `msvcrt!free` at `0x180011964`
- `msvcrt!malloc` at `0x1800114f4`
- `msvcrt!malloc` at `0x1800115e7`
- `msvcrt!malloc` at `0x1800114f4`
- `msvcrt!malloc` at `0x1800115e7`
- `USER32!CharNextW` at `0x180011124`
- `USER32!CharNextW` at `0x1800112eb`
- `USER32!CharNextW` at `0x180011124`
- `USER32!CharNextW` at `0x1800112eb`
- `KERNEL32!lstrcmpiW` at `0x1800110be`
- `KERNEL32!lstrcmpiW` at `0x1800110d1`
- `KERNEL32!lstrcmpiW` at `0x180011150`
- `KERNEL32!lstrcmpiW` at `0x1800111ad`
- `KERNEL32!lstrcmpiW` at `0x1800111db`
- `KERNEL32!lstrcmpiW` at `0x180011424`
- `KERNEL32!lstrcmpiW` at `0x18001173e`
- `KERNEL32!lstrcmpiW` at `0x1800110be`
- `KERNEL32!lstrcmpiW` at `0x1800110d1`
- `KERNEL32!lstrcmpiW` at `0x180011150`
- `KERNEL32!lstrcmpiW` at `0x1800111ad`
- `KERNEL32!lstrcmpiW` at `0x1800111db`
- `KERNEL32!lstrcmpiW` at `0x180011424`
- `KERNEL32!lstrcmpiW` at `0x18001173e`
- `KERNEL32!lstrcpynW` at `0x18001152f`
- `KERNEL32!lstrcpynW` at `0x18001152f`
- `ADVAPI32!RegEnumValueW` at `0x18001161b`
- `ADVAPI32!RegEnumValueW` at `0x18001161b`
- `ADVAPI32!RegCloseKey` at `0x180011260`
- `ADVAPI32!RegCloseKey` at `0x1800112c3`
- `ADVAPI32!RegCloseKey` at `0x180011348`
- `ADVAPI32!RegCloseKey` at `0x18001138f`
- `ADVAPI32!RegCloseKey` at `0x1800113f2`
- `ADVAPI32!RegCloseKey` at `0x1800114ab`
- `ADVAPI32!RegCloseKey` at `0x18001177b`
- `ADVAPI32!RegCloseKey` at `0x180011837`
- `ADVAPI32!RegCloseKey` at `0x18001184b`
- `ADVAPI32!RegCloseKey` at `0x180011897`
- `ADVAPI32!RegCloseKey` at `0x1800118b4`
- `ADVAPI32!RegCloseKey` at `0x1800118db`
- `ADVAPI32!RegCloseKey` at `0x1800118ff`
- `ADVAPI32!RegCloseKey` at `0x180011923`
- `ADVAPI32!RegCloseKey` at `0x180011260`
- `ADVAPI32!RegCloseKey` at `0x1800112c3`
- `ADVAPI32!RegCloseKey` at `0x180011348`
- `ADVAPI32!RegCloseKey` at `0x18001138f`
- `ADVAPI32!RegCloseKey` at `0x1800113f2`
- `ADVAPI32!RegCloseKey` at `0x1800114ab`
- `ADVAPI32!RegCloseKey` at `0x18001177b`
- `ADVAPI32!RegCloseKey` at `0x180011837`
- `ADVAPI32!RegCloseKey` at `0x18001184b`
- `ADVAPI32!RegCloseKey` at `0x180011897`
- `ADVAPI32!RegCloseKey` at `0x1800118b4`
- `ADVAPI32!RegCloseKey` at `0x1800118db`
- `ADVAPI32!RegCloseKey` at `0x1800118ff`
- `ADVAPI32!RegCloseKey` at `0x180011923`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011578`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800115c5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001171d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011578`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800115c5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001171d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800113d9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800113d9`
- `ADVAPI32!RegOpenKeyExW` at `0x18001128d`
- `ADVAPI32!RegOpenKeyExW` at `0x180011330`
- `ADVAPI32!RegOpenKeyExW` at `0x18001137a`
- `ADVAPI32!RegOpenKeyExW` at `0x180011497`
- `ADVAPI32!RegOpenKeyExW` at `0x18001128d`
- `ADVAPI32!RegOpenKeyExW` at `0x180011330`
- `ADVAPI32!RegOpenKeyExW` at `0x18001137a`
- `ADVAPI32!RegOpenKeyExW` at `0x180011497`
- `ADVAPI32!RegDeleteValueW` at `0x1800112a8`
- `ADVAPI32!RegDeleteValueW` at `0x1800112a8`

## string_xrefs

- `0x1800110c7`: `ForceRemove`
- `0x1800111a3`: `NoRemove`
- `0x1800110b4`: `Delete`

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
0x180011038  push    rbp
0x18001103a  push    rbx
0x18001103b  push    rsi
0x18001103c  push    rdi
0x18001103d  push    r12
0x18001103f  push    r13
0x180011041  push    r14
0x180011043  push    r15
0x180011045  sub     rsp, 2F8h
0x18001104c  lea     rbp, [rsp+60h]
0x180011051  mov     rax, cs:__security_cookie
0x180011058  xor     rax, rbp
0x18001105b  mov     [rbp+2D0h+var_50], rax
0x180011062  mov     [rbp+2D0h+var_2C0], r9d
0x180011066  mov     [rbp+2D0h+hKey], r8
0x18001106a  mov     r14, rdx
0x18001106d  mov     r12, rcx
0x180011070  xor     r13d, r13d
0x180011073  mov     ebx, r13d
0x180011076  mov     [rbp+2D0h+var_268], rbx
0x18001107a  mov     esi, r13d
0x18001107d  mov     [rbp+2D0h+var_280], r13
0x180011081  mov     [rbp+2D0h+var_278], r13
0x180011085  mov     [rbp+2D0h+var_270], r13
0x180011089  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001108e  mov     edi, eax
0x180011090  test    eax, eax
0x180011092  jns     short loc_180011099
0x180011094  jmp     loc_180011971
0x180011099  mov     [rbp+2D0h+lpString1], r13
0x18001109d  mov     [rbp+2D0h+var_2B0], 1
0x1800110a4  mov     r13d, [rbp+2D0h+arg_20]
0x1800110ab  mov     [rbp+2D0h+var_288], r13d
0x1800110af  jmp     loc_180011824
0x1800110b4  lea     rdx, aDelete; "Delete"
0x1800110bb  mov     rcx, r14; lpString1
0x1800110be  call    cs:__imp_lstrcmpiW
0x1800110c4  mov     r15d, eax
0x1800110c7  lea     rdx, aForceremove; "ForceRemove"
0x1800110ce  mov     rcx, r14; lpString1
0x1800110d1  call    cs:__imp_lstrcmpiW
0x1800110d7  xor     edi, edi
0x1800110d9  test    eax, eax
0x1800110db  jz      short loc_1800110E6
0x1800110dd  test    r15d, r15d
0x1800110e0  jnz     loc_1800111A3
0x1800110e6  mov     rdx, r14; unsigned __int16 *
0x1800110e9  mov     rcx, r12; this
0x1800110ec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800110f1  mov     edi, eax
0x1800110f3  test    eax, eax
0x1800110f5  js      loc_18001182F
0x1800110fb  xor     edi, edi
0x1800110fd  cmp     [rbp+2D0h+var_2C0], edi
0x180011100  jz      loc_1800111A3
0x180011106  mov     [rbp+2D0h+var_2A0], rdi
0x18001110a  mov     [rbp+2D0h+var_298], rdi
0x18001110e  mov     [rbp+2D0h+var_290], rdi
0x180011112  movzx   eax, word ptr [r14]
0x180011116  test    ax, ax
0x180011119  jz      short loc_180011140
0x18001111b  mov     rcx, r14; lpsz
0x18001111e  cmp     ax, 5Ch ; '\'
0x180011122  jz      short loc_180011137
0x180011124  call    cs:__imp_CharNextW
0x18001112a  mov     rcx, rax
0x18001112d  movzx   eax, word ptr [rax]
0x180011130  test    ax, ax
0x180011133  jnz     short loc_18001111E
0x180011135  jmp     short loc_180011140
0x180011137  test    rcx, rcx
0x18001113a  jnz     loc_180011843
0x180011140  mov     edx, edi
0x180011142  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x180011149  mov     rdx, [rax+rdx*8]; lpString2
0x18001114d  mov     rcx, r14; lpString1
0x180011150  call    cs:__imp_lstrcmpiW
0x180011156  test    eax, eax
0x180011158  jz      short loc_180011175
0x18001115a  inc     edi
0x18001115c  cmp     edi, 2
0x18001115f  jl      short loc_180011140
0x180011161  mov     rax, [rbp+2D0h+hKey]
0x180011165  mov     [rbp+2D0h+var_2A0], rax
0x180011169  mov     rdx, r14; unsigned __int16 *
0x18001116c  lea     rcx, [rbp+2D0h+var_2A0]; this
0x180011170  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180011175  xor     edi, edi
0x180011177  test    r15d, r15d
0x18001117a  jnz     short loc_1800111A3
0x18001117c  mov     rdx, r14; unsigned __int16 *
0x18001117f  mov     rcx, r12; this
0x180011182  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011187  mov     edi, eax
0x180011189  test    eax, eax
0x18001118b  js      loc_18001186A
0x180011191  mov     rdx, r14; unsigned __int16 *
0x180011194  mov     rcx, r12; this
0x180011197  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001119c  mov     edi, eax
0x18001119e  jmp     loc_1800117D0
0x1800111a3  lea     rdx, aNoremove; "NoRemove"
0x1800111aa  mov     rcx, r14; lpString1
0x1800111ad  call    cs:__imp_lstrcmpiW
0x1800111b3  test    eax, eax
0x1800111b5  jnz     short loc_1800111D1
0x1800111b7  mov     [rbp+2D0h+var_2B0], edi
0x1800111ba  mov     rdx, r14; unsigned __int16 *
0x1800111bd  mov     rcx, r12; this
0x1800111c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800111c5  mov     edi, eax
0x1800111c7  test    eax, eax
0x1800111c9  js      loc_18001182F
0x1800111cf  xor     edi, edi
0x1800111d1  lea     rdx, aVal; "Val"
0x1800111d8  mov     rcx, r14; lpString1
0x1800111db  call    cs:__imp_lstrcmpiW
0x1800111e1  test    eax, eax
0x1800111e3  jnz     loc_1800112D9
0x1800111e9  lea     rdx, [rbp+2D0h+ValueName]; unsigned __int16 *
0x1800111ed  mov     rcx, r12; this
0x1800111f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800111f5  mov     edi, eax
0x1800111f7  test    eax, eax
0x1800111f9  js      loc_18001182F
0x1800111ff  mov     rdx, r14; unsigned __int16 *
0x180011202  mov     rcx, r12; this
0x180011205  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001120a  mov     edi, eax
0x18001120c  test    eax, eax
0x18001120e  js      loc_18001182F
0x180011214  cmp     word ptr [r14], 3Dh ; '='
0x180011219  jnz     loc_1800118AC
0x18001121f  xor     edi, edi
0x180011221  cmp     [rbp+2D0h+var_2C0], edi
0x180011224  jz      short loc_18001126C
0x180011226  mov     [rbp+2D0h+var_298], rdi
0x18001122a  mov     [rbp+2D0h+var_290], rdi
0x18001122e  mov     rax, [rbp+2D0h+hKey]
0x180011232  mov     [rbp+2D0h+var_2A0], rax
0x180011236  mov     byte ptr [rsp+330h+phkResult], dil; bool
0x18001123b  mov     r9, r14; unsigned __int16 *
0x18001123e  lea     r8, [rbp+2D0h+ValueName]; unsigned __int16 *
0x180011242  lea     rdx, [rbp+2D0h+var_2A0]; struct ATL::CRegKey *
0x180011246  mov     rcx, r12; this
0x180011249  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18001124e  mov     edi, eax
0x180011250  test    eax, eax
0x180011252  jns     loc_1800117D4
0x180011258  test    rsi, rsi
0x18001125b  jz      short loc_180011267
0x18001125d  mov     rcx, rsi; hKey
0x180011260  call    cs:__imp_RegCloseKey
0x180011266  nop
0x180011267  jmp     loc_180011878
0x18001126c  test    r13d, r13d
0x18001126f  jnz     short loc_1800112C9
0x180011271  mov     [rbp+2D0h+var_2C8], rdi
0x180011275  lea     rax, [rbp+2D0h+var_2C8]
0x180011279  mov     [rsp+330h+phkResult], rax; phkResult
0x18001127e  mov     r9d, 20006h; samDesired
0x180011284  xor     r8d, r8d; ulOptions
0x180011287  xor     edx, edx; lpSubKey
0x180011289  mov     rcx, [rbp+2D0h+hKey]; hKey
0x18001128d  call    cs:__imp_RegOpenKeyExW
0x180011293  mov     edi, eax
0x180011295  test    eax, eax
0x180011297  jnz     loc_18001189F
0x18001129d  mov     r15, [rbp+2D0h+var_2C8]
0x1800112a1  lea     rdx, [rbp+2D0h+ValueName]; lpValueName
0x1800112a5  mov     rcx, r15; hKey
0x1800112a8  call    cs:__imp_RegDeleteValueW
0x1800112ae  mov     edi, eax
0x1800112b0  test    eax, 0FFFFFFFDh
0x1800112b5  jnz     loc_180011882
0x1800112bb  test    r15, r15
0x1800112be  jz      short loc_1800112C9
0x1800112c0  mov     rcx, r15; hKey
0x1800112c3  call    cs:__imp_RegCloseKey
0x1800112c9  mov     rdx, r14; unsigned __int16 *
0x1800112cc  mov     rcx, r12; this
0x1800112cf  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800112d4  jmp     loc_18001181E
0x1800112d9  movzx   eax, word ptr [r14]
0x1800112dd  test    ax, ax
0x1800112e0  jz      short loc_180011307
0x1800112e2  mov     rcx, r14; lpsz
0x1800112e5  cmp     ax, 5Ch ; '\'
0x1800112e9  jz      short loc_1800112FE
0x1800112eb  call    cs:__imp_CharNextW
0x1800112f1  mov     rcx, rax
0x1800112f4  movzx   eax, word ptr [rax]
0x1800112f7  test    ax, ax
0x1800112fa  jnz     short loc_1800112E5
0x1800112fc  jmp     short loc_180011307
0x1800112fe  test    rcx, rcx
0x180011301  jnz     loc_1800118D3
0x180011307  cmp     [rbp+2D0h+var_2C0], edi
0x18001130a  jz      loc_180011475
0x180011310  mov     [rbp+2D0h+var_2C8], rdi
0x180011314  lea     rax, [rbp+2D0h+var_2C8]
0x180011318  mov     [rsp+330h+phkResult], rax; phkResult
0x18001131d  mov     r9d, 0F003Fh; samDesired
0x180011323  xor     r8d, r8d; ulOptions
0x180011326  mov     rdx, r14; lpSubKey
0x180011329  mov     rdi, [rbp+2D0h+hKey]
0x18001132d  mov     rcx, rdi; hKey
0x180011330  call    cs:__imp_RegOpenKeyExW
0x180011336  xor     r15d, r15d
0x180011339  test    eax, eax
0x18001133b  jnz     short loc_18001135E
0x18001133d  mov     eax, r15d
0x180011340  test    rsi, rsi
0x180011343  jz      short loc_18001134E
0x180011345  mov     rcx, rsi; hKey
0x180011348  call    cs:__imp_RegCloseKey
0x18001134e  mov     rsi, [rbp+2D0h+var_2C8]
0x180011352  mov     [rbp+2D0h+var_280], rsi
0x180011356  test    eax, eax
0x180011358  jz      loc_180011408
0x18001135e  mov     [rbp+2D0h+var_2C8], r15
0x180011362  lea     rax, [rbp+2D0h+var_2C8]
0x180011366  mov     [rsp+330h+phkResult], rax; phkResult
0x18001136b  mov     r9d, 20019h; samDesired
0x180011371  xor     r8d, r8d; ulOptions
0x180011374  mov     rdx, r14; lpSubKey
0x180011377  mov     rcx, rdi; hKey
0x18001137a  call    cs:__imp_RegOpenKeyExW
0x180011380  test    eax, eax
0x180011382  jnz     short loc_1800113A1
0x180011384  mov     eax, r15d
0x180011387  test    rsi, rsi
0x18001138a  jz      short loc_180011395
0x18001138c  mov     rcx, rsi; hKey
0x18001138f  call    cs:__imp_RegCloseKey
0x180011395  mov     rsi, [rbp+2D0h+var_2C8]
0x180011399  mov     [rbp+2D0h+var_280], rsi
0x18001139d  test    eax, eax
0x18001139f  jz      short loc_180011408
0x1800113a1  mov     [rbp+2D0h+dwDisposition], r15d
0x1800113a5  mov     [rbp+2D0h+var_2C8], r15
0x1800113a9  lea     rax, [rbp+2D0h+dwDisposition]
0x1800113ad  mov     [rsp+330h+lpdwDisposition], rax; lpdwDisposition
0x1800113b2  lea     rax, [rbp+2D0h+var_2C8]
0x1800113b6  mov     [rsp+330h+var_2F8], rax; phkResult
0x1800113bb  mov     [rsp+330h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800113c0  mov     [rsp+330h+samDesired], 2001Fh; samDesired
0x1800113c8  mov     dword ptr [rsp+330h+phkResult], r15d; dwOptions
0x1800113cd  xor     r9d, r9d; lpClass
0x1800113d0  xor     r8d, r8d; Reserved
0x1800113d3  mov     rdx, r14; lpSubKey
0x1800113d6  mov     rcx, rdi; hKey
0x1800113d9  call    cs:__imp_RegCreateKeyExW
0x1800113df  test    eax, eax
0x1800113e1  jnz     loc_1800118F7
0x1800113e7  mov     eax, r15d
0x1800113ea  test    rsi, rsi
0x1800113ed  jz      short loc_1800113F8
0x1800113ef  mov     rcx, rsi; hKey
0x1800113f2  call    cs:__imp_RegCloseKey
0x1800113f8  mov     rsi, [rbp+2D0h+var_2C8]
0x1800113fc  mov     [rbp+2D0h+var_280], rsi
0x180011400  test    eax, eax
0x180011402  jnz     loc_1800118F7
0x180011408  movzx   eax, word ptr [r14]
0x18001140c  sub     ax, 4Ch ; 'L'
0x180011410  mov     ecx, 0FFDFh
0x180011415  test    cx, ax
0x180011418  jnz     short loc_180011439
0x18001141a  lea     rdx, aLocalserver32; "LocalServer32"
0x180011421  mov     rcx, r14; lpString1
0x180011424  call    cs:__imp_lstrcmpiW
0x18001142a  movzx   r15d, r15b
0x18001142e  test    eax, eax
0x180011430  mov     eax, 1
0x180011435  cmovz   r15d, eax
0x180011439  mov     rdx, r14; unsigned __int16 *
0x18001143c  mov     rcx, r12; this
0x18001143f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011444  mov     edi, eax
0x180011446  test    eax, eax
0x180011448  js      loc_18001182F
0x18001144e  cmp     word ptr [r14], 3Dh ; '='
0x180011453  jnz     loc_1800117D4
0x180011459  mov     byte ptr [rsp+330h+phkResult], r15b; bool
0x18001145e  mov     r9, r14; unsigned __int16 *
0x180011461  xor     r8d, r8d; unsigned __int16 *
0x180011464  lea     rdx, [rbp+2D0h+var_280]; struct ATL::CRegKey *
0x180011468  mov     rcx, r12; this
0x18001146b  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180011470  jmp     loc_1800117CE
0x180011475  test    r13d, r13d
0x180011478  jnz     short loc_1800114C3
0x18001147a  mov     [rbp+2D0h+var_2C8], rdi
0x18001147e  lea     rax, [rbp+2D0h+var_2C8]
0x180011482  mov     [rsp+330h+phkResult], rax; phkResult
0x180011487  mov     r9d, 20019h; samDesired
0x18001148d  xor     r8d, r8d; ulOptions
0x180011490  mov     rdx, r14; lpSubKey
0x180011493  mov     rcx, [rbp+2D0h+hKey]; hKey
  ... truncated ...
```
