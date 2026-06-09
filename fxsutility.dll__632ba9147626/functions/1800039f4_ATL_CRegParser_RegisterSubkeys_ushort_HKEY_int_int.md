# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800039f4`
- end: `0x180004350`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2396`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800035fc`
- `0x1800039f4`

## callees

- `0x180002274`
- `0x180002e08`
- `0x180003040`
- `0x1800034a8`
- `0x1800039f4`
- `0x18000445c`
- `0x180004808`
- `0x180015cf0`

## import_xrefs

- `msvcrt!malloc` at `0x180003eb0`
- `msvcrt!malloc` at `0x180003fa3`
- `msvcrt!malloc` at `0x180003eb0`
- `msvcrt!malloc` at `0x180003fa3`
- `msvcrt!free` at `0x180003feb`
- `msvcrt!free` at `0x180003ff6`
- `msvcrt!free` at `0x180004216`
- `msvcrt!free` at `0x18000422e`
- `msvcrt!free` at `0x18000427f`
- `msvcrt!free` at `0x1800042a6`
- `msvcrt!free` at `0x1800042ca`
- `msvcrt!free` at `0x1800042ee`
- `msvcrt!free` at `0x180004308`
- `msvcrt!free` at `0x180004320`
- `msvcrt!free` at `0x180003feb`
- `msvcrt!free` at `0x180003ff6`
- `msvcrt!free` at `0x180004216`
- `msvcrt!free` at `0x18000422e`
- `msvcrt!free` at `0x18000427f`
- `msvcrt!free` at `0x1800042a6`
- `msvcrt!free` at `0x1800042ca`
- `msvcrt!free` at `0x1800042ee`
- `msvcrt!free` at `0x180004308`
- `msvcrt!free` at `0x180004320`
- `KERNEL32!lstrcmpiW` at `0x180003a7a`
- `KERNEL32!lstrcmpiW` at `0x180003a8d`
- `KERNEL32!lstrcmpiW` at `0x180003b0c`
- `KERNEL32!lstrcmpiW` at `0x180003b69`
- `KERNEL32!lstrcmpiW` at `0x180003b97`
- `KERNEL32!lstrcmpiW` at `0x180003de0`
- `KERNEL32!lstrcmpiW` at `0x1800040fa`
- `KERNEL32!lstrcmpiW` at `0x180003a7a`
- `KERNEL32!lstrcmpiW` at `0x180003a8d`
- `KERNEL32!lstrcmpiW` at `0x180003b0c`
- `KERNEL32!lstrcmpiW` at `0x180003b69`
- `KERNEL32!lstrcmpiW` at `0x180003b97`
- `KERNEL32!lstrcmpiW` at `0x180003de0`
- `KERNEL32!lstrcmpiW` at `0x1800040fa`
- `KERNEL32!lstrcpynW` at `0x180003eeb`
- `KERNEL32!lstrcpynW` at `0x180003eeb`
- `USER32!CharNextW` at `0x180003ae0`
- `USER32!CharNextW` at `0x180003ca7`
- `USER32!CharNextW` at `0x180003ae0`
- `USER32!CharNextW` at `0x180003ca7`
- `ADVAPI32!RegDeleteValueW` at `0x180003c64`
- `ADVAPI32!RegDeleteValueW` at `0x180003c64`
- `ADVAPI32!RegEnumValueW` at `0x180003fd7`
- `ADVAPI32!RegEnumValueW` at `0x180003fd7`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c49`
- `ADVAPI32!RegOpenKeyExW` at `0x180003cec`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d36`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e53`
- `ADVAPI32!RegOpenKeyExW` at `0x180003c49`
- `ADVAPI32!RegOpenKeyExW` at `0x180003cec`
- `ADVAPI32!RegOpenKeyExW` at `0x180003d36`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e53`
- `ADVAPI32!RegCreateKeyExW` at `0x180003d95`
- `ADVAPI32!RegCreateKeyExW` at `0x180003d95`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f34`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f81`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800040d9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f34`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f81`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800040d9`
- `ADVAPI32!RegCloseKey` at `0x180003c1c`
- `ADVAPI32!RegCloseKey` at `0x180003c7f`
- `ADVAPI32!RegCloseKey` at `0x180003d04`
- `ADVAPI32!RegCloseKey` at `0x180003d4b`
- `ADVAPI32!RegCloseKey` at `0x180003dae`
- `ADVAPI32!RegCloseKey` at `0x180003e67`
- `ADVAPI32!RegCloseKey` at `0x180004137`
- `ADVAPI32!RegCloseKey` at `0x1800041f3`
- `ADVAPI32!RegCloseKey` at `0x180004207`
- `ADVAPI32!RegCloseKey` at `0x180004253`
- `ADVAPI32!RegCloseKey` at `0x180004270`
- `ADVAPI32!RegCloseKey` at `0x180004297`
- `ADVAPI32!RegCloseKey` at `0x1800042bb`
- `ADVAPI32!RegCloseKey` at `0x1800042df`
- `ADVAPI32!RegCloseKey` at `0x180003c1c`
- `ADVAPI32!RegCloseKey` at `0x180003c7f`
- `ADVAPI32!RegCloseKey` at `0x180003d04`
- `ADVAPI32!RegCloseKey` at `0x180003d4b`
- `ADVAPI32!RegCloseKey` at `0x180003dae`
- `ADVAPI32!RegCloseKey` at `0x180003e67`
- `ADVAPI32!RegCloseKey` at `0x180004137`
- `ADVAPI32!RegCloseKey` at `0x1800041f3`
- `ADVAPI32!RegCloseKey` at `0x180004207`
- `ADVAPI32!RegCloseKey` at `0x180004253`
- `ADVAPI32!RegCloseKey` at `0x180004270`
- `ADVAPI32!RegCloseKey` at `0x180004297`
- `ADVAPI32!RegCloseKey` at `0x1800042bb`
- `ADVAPI32!RegCloseKey` at `0x1800042df`

## string_xrefs

- `0x180003a83`: `ForceRemove`
- `0x180003b5f`: `NoRemove`
- `0x180003a70`: `Delete`

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
0x1800039f4  push    rbp
0x1800039f6  push    rbx
0x1800039f7  push    rsi
0x1800039f8  push    rdi
0x1800039f9  push    r12
0x1800039fb  push    r13
0x1800039fd  push    r14
0x1800039ff  push    r15
0x180003a01  sub     rsp, 2F8h
0x180003a08  lea     rbp, [rsp+60h]
0x180003a0d  mov     rax, cs:__security_cookie
0x180003a14  xor     rax, rbp
0x180003a17  mov     [rbp+2D0h+var_50], rax
0x180003a1e  mov     [rbp+2D0h+var_2C0], r9d
0x180003a22  mov     [rbp+2D0h+hKey], r8
0x180003a26  mov     r14, rdx
0x180003a29  mov     r12, rcx
0x180003a2c  xor     r13d, r13d
0x180003a2f  mov     ebx, r13d
0x180003a32  mov     [rbp+2D0h+var_268], rbx
0x180003a36  mov     esi, r13d
0x180003a39  mov     [rbp+2D0h+var_280], r13
0x180003a3d  mov     [rbp+2D0h+var_278], r13
0x180003a41  mov     [rbp+2D0h+var_270], r13
0x180003a45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003a4a  mov     edi, eax
0x180003a4c  test    eax, eax
0x180003a4e  jns     short loc_180003A55
0x180003a50  jmp     loc_18000432D
0x180003a55  mov     [rbp+2D0h+lpString1], r13
0x180003a59  mov     [rbp+2D0h+var_2B0], 1
0x180003a60  mov     r13d, [rbp+2D0h+arg_20]
0x180003a67  mov     [rbp+2D0h+var_288], r13d
0x180003a6b  jmp     loc_1800041E0
0x180003a70  lea     rdx, aDelete; "Delete"
0x180003a77  mov     rcx, r14; lpString1
0x180003a7a  call    cs:__imp_lstrcmpiW
0x180003a80  mov     r15d, eax
0x180003a83  lea     rdx, aForceremove; "ForceRemove"
0x180003a8a  mov     rcx, r14; lpString1
0x180003a8d  call    cs:__imp_lstrcmpiW
0x180003a93  xor     edi, edi
0x180003a95  test    eax, eax
0x180003a97  jz      short loc_180003AA2
0x180003a99  test    r15d, r15d
0x180003a9c  jnz     loc_180003B5F
0x180003aa2  mov     rdx, r14; unsigned __int16 *
0x180003aa5  mov     rcx, r12; this
0x180003aa8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003aad  mov     edi, eax
0x180003aaf  test    eax, eax
0x180003ab1  js      loc_1800041EB
0x180003ab7  xor     edi, edi
0x180003ab9  cmp     [rbp+2D0h+var_2C0], edi
0x180003abc  jz      loc_180003B5F
0x180003ac2  mov     [rbp+2D0h+var_2A0], rdi
0x180003ac6  mov     [rbp+2D0h+var_298], rdi
0x180003aca  mov     [rbp+2D0h+var_290], rdi
0x180003ace  movzx   eax, word ptr [r14]
0x180003ad2  test    ax, ax
0x180003ad5  jz      short loc_180003AFC
0x180003ad7  mov     rcx, r14; lpsz
0x180003ada  cmp     ax, 5Ch ; '\'
0x180003ade  jz      short loc_180003AF3
0x180003ae0  call    cs:__imp_CharNextW
0x180003ae6  mov     rcx, rax
0x180003ae9  movzx   eax, word ptr [rax]
0x180003aec  test    ax, ax
0x180003aef  jnz     short loc_180003ADA
0x180003af1  jmp     short loc_180003AFC
0x180003af3  test    rcx, rcx
0x180003af6  jnz     loc_1800041FF
0x180003afc  mov     edx, edi
0x180003afe  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1PAPEBGA; ushort const * near * ATL::CRegParser::rgszNeverDelete
0x180003b05  mov     rdx, [rax+rdx*8]; lpString2
0x180003b09  mov     rcx, r14; lpString1
0x180003b0c  call    cs:__imp_lstrcmpiW
0x180003b12  test    eax, eax
0x180003b14  jz      short loc_180003B31
0x180003b16  inc     edi
0x180003b18  cmp     edi, 2
0x180003b1b  jl      short loc_180003AFC
0x180003b1d  mov     rax, [rbp+2D0h+hKey]
0x180003b21  mov     [rbp+2D0h+var_2A0], rax
0x180003b25  mov     rdx, r14; unsigned __int16 *
0x180003b28  lea     rcx, [rbp+2D0h+var_2A0]; this
0x180003b2c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003b31  xor     edi, edi
0x180003b33  test    r15d, r15d
0x180003b36  jnz     short loc_180003B5F
0x180003b38  mov     rdx, r14; unsigned __int16 *
0x180003b3b  mov     rcx, r12; this
0x180003b3e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003b43  mov     edi, eax
0x180003b45  test    eax, eax
0x180003b47  js      loc_180004226
0x180003b4d  mov     rdx, r14; unsigned __int16 *
0x180003b50  mov     rcx, r12; this
0x180003b53  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003b58  mov     edi, eax
0x180003b5a  jmp     loc_18000418C
0x180003b5f  lea     rdx, aNoremove; "NoRemove"
0x180003b66  mov     rcx, r14; lpString1
0x180003b69  call    cs:__imp_lstrcmpiW
0x180003b6f  test    eax, eax
0x180003b71  jnz     short loc_180003B8D
0x180003b73  mov     [rbp+2D0h+var_2B0], edi
0x180003b76  mov     rdx, r14; unsigned __int16 *
0x180003b79  mov     rcx, r12; this
0x180003b7c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003b81  mov     edi, eax
0x180003b83  test    eax, eax
0x180003b85  js      loc_1800041EB
0x180003b8b  xor     edi, edi
0x180003b8d  lea     rdx, aVal; "Val"
0x180003b94  mov     rcx, r14; lpString1
0x180003b97  call    cs:__imp_lstrcmpiW
0x180003b9d  test    eax, eax
0x180003b9f  jnz     loc_180003C95
0x180003ba5  lea     rdx, [rbp+2D0h+ValueName]; unsigned __int16 *
0x180003ba9  mov     rcx, r12; this
0x180003bac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bb1  mov     edi, eax
0x180003bb3  test    eax, eax
0x180003bb5  js      loc_1800041EB
0x180003bbb  mov     rdx, r14; unsigned __int16 *
0x180003bbe  mov     rcx, r12; this
0x180003bc1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bc6  mov     edi, eax
0x180003bc8  test    eax, eax
0x180003bca  js      loc_1800041EB
0x180003bd0  cmp     word ptr [r14], 3Dh ; '='
0x180003bd5  jnz     loc_180004268
0x180003bdb  xor     edi, edi
0x180003bdd  cmp     [rbp+2D0h+var_2C0], edi
0x180003be0  jz      short loc_180003C28
0x180003be2  mov     [rbp+2D0h+var_298], rdi
0x180003be6  mov     [rbp+2D0h+var_290], rdi
0x180003bea  mov     rax, [rbp+2D0h+hKey]
0x180003bee  mov     [rbp+2D0h+var_2A0], rax
0x180003bf2  mov     byte ptr [rsp+330h+phkResult], dil; bool
0x180003bf7  mov     r9, r14; unsigned __int16 *
0x180003bfa  lea     r8, [rbp+2D0h+ValueName]; unsigned __int16 *
0x180003bfe  lea     rdx, [rbp+2D0h+var_2A0]; struct ATL::CRegKey *
0x180003c02  mov     rcx, r12; this
0x180003c05  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180003c0a  mov     edi, eax
0x180003c0c  test    eax, eax
0x180003c0e  jns     loc_180004190
0x180003c14  test    rsi, rsi
0x180003c17  jz      short loc_180003C23
0x180003c19  mov     rcx, rsi; hKey
0x180003c1c  call    cs:__imp_RegCloseKey
0x180003c22  nop
0x180003c23  jmp     loc_180004234
0x180003c28  test    r13d, r13d
0x180003c2b  jnz     short loc_180003C85
0x180003c2d  mov     [rbp+2D0h+var_2C8], rdi
0x180003c31  lea     rax, [rbp+2D0h+var_2C8]
0x180003c35  mov     [rsp+330h+phkResult], rax; phkResult
0x180003c3a  mov     r9d, 20006h; samDesired
0x180003c40  xor     r8d, r8d; ulOptions
0x180003c43  xor     edx, edx; lpSubKey
0x180003c45  mov     rcx, [rbp+2D0h+hKey]; hKey
0x180003c49  call    cs:__imp_RegOpenKeyExW
0x180003c4f  mov     edi, eax
0x180003c51  test    eax, eax
0x180003c53  jnz     loc_18000425B
0x180003c59  mov     r15, [rbp+2D0h+var_2C8]
0x180003c5d  lea     rdx, [rbp+2D0h+ValueName]; lpValueName
0x180003c61  mov     rcx, r15; hKey
0x180003c64  call    cs:__imp_RegDeleteValueW
0x180003c6a  mov     edi, eax
0x180003c6c  test    eax, 0FFFFFFFDh
0x180003c71  jnz     loc_18000423E
0x180003c77  test    r15, r15
0x180003c7a  jz      short loc_180003C85
0x180003c7c  mov     rcx, r15; hKey
0x180003c7f  call    cs:__imp_RegCloseKey
0x180003c85  mov     rdx, r14; unsigned __int16 *
0x180003c88  mov     rcx, r12; this
0x180003c8b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180003c90  jmp     loc_1800041DA
0x180003c95  movzx   eax, word ptr [r14]
0x180003c99  test    ax, ax
0x180003c9c  jz      short loc_180003CC3
0x180003c9e  mov     rcx, r14; lpsz
0x180003ca1  cmp     ax, 5Ch ; '\'
0x180003ca5  jz      short loc_180003CBA
0x180003ca7  call    cs:__imp_CharNextW
0x180003cad  mov     rcx, rax
0x180003cb0  movzx   eax, word ptr [rax]
0x180003cb3  test    ax, ax
0x180003cb6  jnz     short loc_180003CA1
0x180003cb8  jmp     short loc_180003CC3
0x180003cba  test    rcx, rcx
0x180003cbd  jnz     loc_18000428F
0x180003cc3  cmp     [rbp+2D0h+var_2C0], edi
0x180003cc6  jz      loc_180003E31
0x180003ccc  mov     [rbp+2D0h+var_2C8], rdi
0x180003cd0  lea     rax, [rbp+2D0h+var_2C8]
0x180003cd4  mov     [rsp+330h+phkResult], rax; phkResult
0x180003cd9  mov     r9d, 0F003Fh; samDesired
0x180003cdf  xor     r8d, r8d; ulOptions
0x180003ce2  mov     rdx, r14; lpSubKey
0x180003ce5  mov     rdi, [rbp+2D0h+hKey]
0x180003ce9  mov     rcx, rdi; hKey
0x180003cec  call    cs:__imp_RegOpenKeyExW
0x180003cf2  xor     r15d, r15d
0x180003cf5  test    eax, eax
0x180003cf7  jnz     short loc_180003D1A
0x180003cf9  mov     eax, r15d
0x180003cfc  test    rsi, rsi
0x180003cff  jz      short loc_180003D0A
0x180003d01  mov     rcx, rsi; hKey
0x180003d04  call    cs:__imp_RegCloseKey
0x180003d0a  mov     rsi, [rbp+2D0h+var_2C8]
0x180003d0e  mov     [rbp+2D0h+var_280], rsi
0x180003d12  test    eax, eax
0x180003d14  jz      loc_180003DC4
0x180003d1a  mov     [rbp+2D0h+var_2C8], r15
0x180003d1e  lea     rax, [rbp+2D0h+var_2C8]
0x180003d22  mov     [rsp+330h+phkResult], rax; phkResult
0x180003d27  mov     r9d, 20019h; samDesired
0x180003d2d  xor     r8d, r8d; ulOptions
0x180003d30  mov     rdx, r14; lpSubKey
0x180003d33  mov     rcx, rdi; hKey
0x180003d36  call    cs:__imp_RegOpenKeyExW
0x180003d3c  test    eax, eax
0x180003d3e  jnz     short loc_180003D5D
0x180003d40  mov     eax, r15d
0x180003d43  test    rsi, rsi
0x180003d46  jz      short loc_180003D51
0x180003d48  mov     rcx, rsi; hKey
0x180003d4b  call    cs:__imp_RegCloseKey
0x180003d51  mov     rsi, [rbp+2D0h+var_2C8]
0x180003d55  mov     [rbp+2D0h+var_280], rsi
0x180003d59  test    eax, eax
0x180003d5b  jz      short loc_180003DC4
0x180003d5d  mov     [rbp+2D0h+dwDisposition], r15d
0x180003d61  mov     [rbp+2D0h+var_2C8], r15
0x180003d65  lea     rax, [rbp+2D0h+dwDisposition]
0x180003d69  mov     [rsp+330h+lpdwDisposition], rax; lpdwDisposition
0x180003d6e  lea     rax, [rbp+2D0h+var_2C8]
0x180003d72  mov     [rsp+330h+var_2F8], rax; phkResult
0x180003d77  mov     [rsp+330h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180003d7c  mov     [rsp+330h+samDesired], 2001Fh; samDesired
0x180003d84  mov     dword ptr [rsp+330h+phkResult], r15d; dwOptions
0x180003d89  xor     r9d, r9d; lpClass
0x180003d8c  xor     r8d, r8d; Reserved
0x180003d8f  mov     rdx, r14; lpSubKey
0x180003d92  mov     rcx, rdi; hKey
0x180003d95  call    cs:__imp_RegCreateKeyExW
0x180003d9b  test    eax, eax
0x180003d9d  jnz     loc_1800042B3
0x180003da3  mov     eax, r15d
0x180003da6  test    rsi, rsi
0x180003da9  jz      short loc_180003DB4
0x180003dab  mov     rcx, rsi; hKey
0x180003dae  call    cs:__imp_RegCloseKey
0x180003db4  mov     rsi, [rbp+2D0h+var_2C8]
0x180003db8  mov     [rbp+2D0h+var_280], rsi
0x180003dbc  test    eax, eax
0x180003dbe  jnz     loc_1800042B3
0x180003dc4  movzx   eax, word ptr [r14]
0x180003dc8  sub     ax, 4Ch ; 'L'
0x180003dcc  mov     ecx, 0FFDFh
0x180003dd1  test    cx, ax
0x180003dd4  jnz     short loc_180003DF5
0x180003dd6  lea     rdx, aLocalserver32; "LocalServer32"
0x180003ddd  mov     rcx, r14; lpString1
0x180003de0  call    cs:__imp_lstrcmpiW
0x180003de6  movzx   r15d, r15b
0x180003dea  test    eax, eax
0x180003dec  mov     eax, 1
0x180003df1  cmovz   r15d, eax
0x180003df5  mov     rdx, r14; unsigned __int16 *
0x180003df8  mov     rcx, r12; this
0x180003dfb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003e00  mov     edi, eax
0x180003e02  test    eax, eax
0x180003e04  js      loc_1800041EB
0x180003e0a  cmp     word ptr [r14], 3Dh ; '='
0x180003e0f  jnz     loc_180004190
0x180003e15  mov     byte ptr [rsp+330h+phkResult], r15b; bool
0x180003e1a  mov     r9, r14; unsigned __int16 *
0x180003e1d  xor     r8d, r8d; unsigned __int16 *
0x180003e20  lea     rdx, [rbp+2D0h+var_280]; struct ATL::CRegKey *
0x180003e24  mov     rcx, r12; this
0x180003e27  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x180003e2c  jmp     loc_18000418A
0x180003e31  test    r13d, r13d
0x180003e34  jnz     short loc_180003E7F
0x180003e36  mov     [rbp+2D0h+var_2C8], rdi
0x180003e3a  lea     rax, [rbp+2D0h+var_2C8]
0x180003e3e  mov     [rsp+330h+phkResult], rax; phkResult
0x180003e43  mov     r9d, 20019h; samDesired
0x180003e49  xor     r8d, r8d; ulOptions
0x180003e4c  mov     rdx, r14; lpSubKey
0x180003e4f  mov     rcx, [rbp+2D0h+hKey]; hKey
  ... truncated ...
```
