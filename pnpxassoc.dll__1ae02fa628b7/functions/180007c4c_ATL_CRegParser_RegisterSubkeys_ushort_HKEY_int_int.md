# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180007c4c`
- end: `0x1800083e9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800078f8`
- `0x180007c4c`

## callees

- `0x180005b14`
- `0x180006290`
- `0x180006764`
- `0x180006e00`
- `0x1800070f0`
- `0x1800077a8`
- `0x180007c4c`
- `0x180008714`
- `0x180012e00`
- `0x180012e90`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008123`
- `msvcrt!wcsncpy_s` at `0x180008123`
- `KERNEL32!lstrcmpiW` at `0x180007cca`
- `KERNEL32!lstrcmpiW` at `0x180007cdd`
- `KERNEL32!lstrcmpiW` at `0x180007d5b`
- `KERNEL32!lstrcmpiW` at `0x180007dc4`
- `KERNEL32!lstrcmpiW` at `0x180007df2`
- `KERNEL32!lstrcmpiW` at `0x180008271`
- `KERNEL32!lstrcmpiW` at `0x180007cca`
- `KERNEL32!lstrcmpiW` at `0x180007cdd`
- `KERNEL32!lstrcmpiW` at `0x180007d5b`
- `KERNEL32!lstrcmpiW` at `0x180007dc4`
- `KERNEL32!lstrcmpiW` at `0x180007df2`
- `KERNEL32!lstrcmpiW` at `0x180008271`
- `ADVAPI32!RegDeleteValueW` at `0x180007eac`
- `ADVAPI32!RegDeleteValueW` at `0x180007eac`
- `ADVAPI32!RegCreateKeyExW` at `0x180007fe4`
- `ADVAPI32!RegCreateKeyExW` at `0x180007fe4`
- `ADVAPI32!RegOpenKeyExW` at `0x180007e8f`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f3d`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f86`
- `ADVAPI32!RegOpenKeyExW` at `0x1800080d1`
- `ADVAPI32!RegOpenKeyExW` at `0x180007e8f`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f3d`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f86`
- `ADVAPI32!RegOpenKeyExW` at `0x1800080d1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000824a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800082e3`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000824a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800082e3`
- `ADVAPI32!RegCloseKey` at `0x180007ec5`
- `ADVAPI32!RegCloseKey` at `0x180007f51`
- `ADVAPI32!RegCloseKey` at `0x180007f9a`
- `ADVAPI32!RegCloseKey` at `0x180007ffc`
- `ADVAPI32!RegCloseKey` at `0x1800080ec`
- `ADVAPI32!RegCloseKey` at `0x180008302`
- `ADVAPI32!RegCloseKey` at `0x180008361`
- `ADVAPI32!RegCloseKey` at `0x18000839d`
- `ADVAPI32!RegCloseKey` at `0x1800083ad`
- `ADVAPI32!RegCloseKey` at `0x180007ec5`
- `ADVAPI32!RegCloseKey` at `0x180007f51`
- `ADVAPI32!RegCloseKey` at `0x180007f9a`
- `ADVAPI32!RegCloseKey` at `0x180007ffc`
- `ADVAPI32!RegCloseKey` at `0x1800080ec`
- `ADVAPI32!RegCloseKey` at `0x180008302`
- `ADVAPI32!RegCloseKey` at `0x180008361`
- `ADVAPI32!RegCloseKey` at `0x18000839d`
- `ADVAPI32!RegCloseKey` at `0x1800083ad`
- `USER32!CharNextW` at `0x180007d2f`
- `USER32!CharNextW` at `0x180007ef6`
- `USER32!CharNextW` at `0x180007d2f`
- `USER32!CharNextW` at `0x180007ef6`

## string_xrefs

- `0x180007cd0`: `ForceRemove`
- `0x180007db4`: `NoRemove`
- `0x180007cc0`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v5; // rbx
  int v6; // r12d
  HKEY v7; // r15
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
  int v32; // r14d
  LSTATUS v33; // eax
  unsigned int v34; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v36 = a4;
  v5 = 0;
  v37 = a3;
  memset(v39, 0, sizeof(v39));
  v6 = a4;
  v7 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        if ( !v14 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_118;
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
            v40 = v7;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_93;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_93;
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_35;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_112;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 != 61 )
        break;
      if ( v36 )
      {
        v41 = 0;
        v42 = 0;
        v40 = v7;
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_112;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_110;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
          goto LABEL_112;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
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
          goto LABEL_43;
      }
      if ( v23 )
        break;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_128;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v39[0] = hKey;
      if ( v24 )
      {
LABEL_128:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_129;
        v25 = 0;
        if ( v5 )
          v25 = RegCloseKey(v5);
        v5 = hKey;
        v39[0] = hKey;
        if ( v25 )
        {
LABEL_129:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_110;
          v18 = 0;
          if ( v5 )
            v18 = RegCloseKey(v5);
          v5 = phkResult;
          v39[0] = phkResult;
          if ( v18 )
          {
LABEL_110:
            v34 = v18;
            goto LABEL_111;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v39, 0, a2);
        v5 = (HKEY)v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v36;
      goto LABEL_61;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v7, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v39[0] = phkResult;
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
      goto LABEL_112;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_112;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_112;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v7 = v37;
        goto LABEL_93;
      }
      v34 = v27;
LABEL_111:
      Token = ATL::AtlHresultFromWin32(v34);
LABEL_112:
      if ( v5 )
        RegCloseKey(v5);
      return (unsigned int)Token;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v31 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, Destination);
                v5 = (HKEY)v39[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v32 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v33 = RegCloseKey(v5);
      v39[0] = 0;
      v5 = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v36;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x180007c4c  push    rbp
0x180007c4e  push    rbx
0x180007c4f  push    rsi
0x180007c50  push    rdi
0x180007c51  push    r12
0x180007c53  push    r13
0x180007c55  push    r14
0x180007c57  push    r15
0x180007c59  lea     rbp, [rsp-21D8h]
0x180007c61  mov     eax, 22D8h
0x180007c66  call    _alloca_probe
0x180007c6b  sub     rsp, rax
0x180007c6e  mov     rax, cs:__security_cookie
0x180007c75  xor     rax, rsp
0x180007c78  mov     [rbp+2210h+var_50], rax
0x180007c7f  xor     r14d, r14d
0x180007c82  mov     [rsp+2310h+var_22A8], r9d
0x180007c87  mov     ebx, r14d
0x180007c8a  mov     [rsp+2310h+var_22A0], r8
0x180007c8f  mov     [rbp+2210h+var_2290], rbx
0x180007c93  mov     r12d, r9d
0x180007c96  mov     r15, r8
0x180007c99  mov     [rbp+2210h+var_2288], r14
0x180007c9d  mov     rsi, rdx
0x180007ca0  mov     [rbp+2210h+var_2280], r14
0x180007ca4  mov     r13, rcx
0x180007ca7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007cac  mov     edi, eax
0x180007cae  test    eax, eax
0x180007cb0  js      loc_180008369
0x180007cb6  cmp     word ptr [rsi], 7Dh ; '}'
0x180007cba  jz      loc_180008367
0x180007cc0  lea     rdx, String2; "Delete"
0x180007cc7  mov     rcx, rsi; lpString1
0x180007cca  call    cs:__imp_lstrcmpiW
0x180007cd0  lea     rdx, aForceremove; "ForceRemove"
0x180007cd7  mov     rcx, rsi; lpString1
0x180007cda  mov     r14d, eax
0x180007cdd  call    cs:__imp_lstrcmpiW
0x180007ce3  xor     edi, edi
0x180007ce5  test    eax, eax
0x180007ce7  jz      short loc_180007CF2
0x180007ce9  test    r14d, r14d
0x180007cec  jnz     loc_180007DB4
0x180007cf2  mov     rdx, rsi; unsigned __int16 *
0x180007cf5  mov     rcx, r13; this
0x180007cf8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007cfd  mov     edi, eax
0x180007cff  test    eax, eax
0x180007d01  js      loc_180008359
0x180007d07  xor     edi, edi
0x180007d09  test    r12d, r12d
0x180007d0c  jz      loc_180007DB4
0x180007d12  movzx   eax, word ptr [rsi]
0x180007d15  mov     [rbp+2210h+var_2278], rdi
0x180007d19  mov     [rbp+2210h+var_2270], rdi
0x180007d1d  mov     [rbp+2210h+var_2268], rdi
0x180007d21  test    ax, ax
0x180007d24  jz      short loc_180007D4B
0x180007d26  mov     rcx, rsi; lpsz
0x180007d29  cmp     ax, 5Ch ; '\'
0x180007d2d  jz      short loc_180007D42
0x180007d2f  call    cs:__imp_CharNextW
0x180007d35  mov     rcx, rax
0x180007d38  movzx   eax, word ptr [rax]
0x180007d3b  test    ax, ax
0x180007d3e  jnz     short loc_180007D29
0x180007d40  jmp     short loc_180007D4B
0x180007d42  test    rcx, rcx
0x180007d45  jnz     loc_1800083A5
0x180007d4b  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180007d52  mov     edx, edi
0x180007d54  mov     rcx, rsi; lpString1
0x180007d57  mov     rdx, [rax+rdx*8]; lpString2
0x180007d5b  call    cs:__imp_lstrcmpiW
0x180007d61  test    eax, eax
0x180007d63  jz      short loc_180007D7C
0x180007d65  inc     edi
0x180007d67  cmp     edi, 0Ch
0x180007d6a  jl      short loc_180007D4B
0x180007d6c  mov     rdx, rsi; unsigned __int16 *
0x180007d6f  mov     [rbp+2210h+var_2278], r15
0x180007d73  lea     rcx, [rbp+2210h+var_2278]; this
0x180007d77  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007d7c  xor     edi, edi
0x180007d7e  test    r14d, r14d
0x180007d81  jnz     short loc_180007DB4
0x180007d83  mov     rdx, rsi; unsigned __int16 *
0x180007d86  mov     rcx, r13; this
0x180007d89  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007d8e  mov     edi, eax
0x180007d90  test    eax, eax
0x180007d92  js      loc_180008359
0x180007d98  mov     rdx, rsi; unsigned __int16 *
0x180007d9b  mov     rcx, r13; this
0x180007d9e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007da3  xor     edx, edx
0x180007da5  mov     edi, eax
0x180007da7  test    eax, eax
0x180007da9  js      loc_180008359
0x180007daf  jmp     loc_180008057
0x180007db4  lea     rdx, aNoremove; "NoRemove"
0x180007dbb  mov     rcx, rsi; lpString1
0x180007dbe  mov     r12d, 1
0x180007dc4  call    cs:__imp_lstrcmpiW
0x180007dca  test    eax, eax
0x180007dcc  jnz     short loc_180007DE8
0x180007dce  mov     rdx, rsi; unsigned __int16 *
0x180007dd1  mov     rcx, r13; this
0x180007dd4  mov     r12d, edi
0x180007dd7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007ddc  mov     edi, eax
0x180007dde  test    eax, eax
0x180007de0  js      loc_180008359
0x180007de6  xor     edi, edi
0x180007de8  lea     rdx, aVal; "Val"
0x180007def  mov     rcx, rsi; lpString1
0x180007df2  call    cs:__imp_lstrcmpiW
0x180007df8  test    eax, eax
0x180007dfa  jnz     loc_180007EE5
0x180007e00  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007e07  mov     rcx, r13; this
0x180007e0a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007e0f  mov     edi, eax
0x180007e11  test    eax, eax
0x180007e13  js      loc_180008359
0x180007e19  mov     rdx, rsi; unsigned __int16 *
0x180007e1c  mov     rcx, r13; this
0x180007e1f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007e24  xor     edx, edx; lpSubKey
0x180007e26  mov     edi, eax
0x180007e28  test    eax, eax
0x180007e2a  js      loc_180008359
0x180007e30  cmp     word ptr [rsi], 3Dh ; '='
0x180007e34  jnz     loc_1800083A5
0x180007e3a  cmp     [rsp+2310h+var_22A8], edx
0x180007e3e  jz      short loc_180007E67
0x180007e40  mov     [rbp+2210h+var_2270], rdx
0x180007e44  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007e4b  mov     [rbp+2210h+var_2268], rdx
0x180007e4f  mov     r9, rsi; unsigned __int16 *
0x180007e52  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180007e56  mov     [rbp+2210h+var_2278], r15
0x180007e5a  mov     rcx, r13; this
0x180007e5d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007e62  jmp     loc_180008046
0x180007e67  cmp     [rbp+2210h+arg_20], edx
0x180007e6d  jnz     short loc_180007ECB
0x180007e6f  test    r12d, r12d
0x180007e72  jz      short loc_180007ECB
0x180007e74  lea     rax, [rsp+2310h+hKey]
0x180007e79  mov     [rsp+2310h+hKey], rdx
0x180007e7e  mov     r9d, 20006h; samDesired
0x180007e84  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007e89  xor     r8d, r8d; ulOptions
0x180007e8c  mov     rcx, r15; hKey
0x180007e8f  call    cs:__imp_RegOpenKeyExW
0x180007e95  test    eax, eax
0x180007e97  jnz     loc_180008350
0x180007e9d  mov     r14, [rsp+2310h+hKey]
0x180007ea2  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180007ea9  mov     rcx, r14; hKey
0x180007eac  call    cs:__imp_RegDeleteValueW
0x180007eb2  test    eax, 0FFFFFFFDh
0x180007eb7  jnz     loc_18000838C
0x180007ebd  test    r14, r14
0x180007ec0  jz      short loc_180007ECB
0x180007ec2  mov     rcx, r14; hKey
0x180007ec5  call    cs:__imp_RegCloseKey
0x180007ecb  mov     rdx, rsi; unsigned __int16 *
0x180007ece  mov     rcx, r13; this
0x180007ed1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007ed6  mov     edi, eax
0x180007ed8  test    eax, eax
0x180007eda  js      loc_180008359
0x180007ee0  jmp     loc_1800081EE
0x180007ee5  movzx   eax, word ptr [rsi]
0x180007ee8  test    ax, ax
0x180007eeb  jz      short loc_180007F12
0x180007eed  mov     rcx, rsi; lpsz
0x180007ef0  cmp     ax, 5Ch ; '\'
0x180007ef4  jz      short loc_180007F09
0x180007ef6  call    cs:__imp_CharNextW
0x180007efc  mov     rcx, rax
0x180007eff  movzx   eax, word ptr [rax]
0x180007f02  test    ax, ax
0x180007f05  jnz     short loc_180007EF0
0x180007f07  jmp     short loc_180007F12
0x180007f09  test    rcx, rcx
0x180007f0c  jnz     loc_1800083A5
0x180007f12  cmp     [rsp+2310h+var_22A8], edi
0x180007f16  jz      loc_1800080A7
0x180007f1c  lea     rax, [rsp+2310h+hKey]
0x180007f21  mov     [rsp+2310h+hKey], rdi
0x180007f26  mov     r14d, 2001Fh
0x180007f2c  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007f31  mov     r9d, r14d; samDesired
0x180007f34  xor     r8d, r8d; ulOptions
0x180007f37  mov     rdx, rsi; lpSubKey
0x180007f3a  mov     rcx, r15; hKey
0x180007f3d  call    cs:__imp_RegOpenKeyExW
0x180007f43  test    eax, eax
0x180007f45  jnz     short loc_180007F68
0x180007f47  mov     eax, edi
0x180007f49  test    rbx, rbx
0x180007f4c  jz      short loc_180007F57
0x180007f4e  mov     rcx, rbx; hKey
0x180007f51  call    cs:__imp_RegCloseKey
0x180007f57  mov     rbx, [rsp+2310h+hKey]
0x180007f5c  mov     [rbp+2210h+var_2290], rbx
0x180007f60  test    eax, eax
0x180007f62  jz      loc_180008013
0x180007f68  lea     rax, [rsp+2310h+hKey]
0x180007f6d  mov     [rsp+2310h+hKey], rdi
0x180007f72  mov     r9d, 20019h; samDesired
0x180007f78  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007f7d  xor     r8d, r8d; ulOptions
0x180007f80  mov     rdx, rsi; lpSubKey
0x180007f83  mov     rcx, r15; hKey
0x180007f86  call    cs:__imp_RegOpenKeyExW
0x180007f8c  test    eax, eax
0x180007f8e  jnz     short loc_180007FAD
0x180007f90  mov     eax, edi
0x180007f92  test    rbx, rbx
0x180007f95  jz      short loc_180007FA0
0x180007f97  mov     rcx, rbx; hKey
0x180007f9a  call    cs:__imp_RegCloseKey
0x180007fa0  mov     rbx, [rsp+2310h+hKey]
0x180007fa5  mov     [rbp+2210h+var_2290], rbx
0x180007fa9  test    eax, eax
0x180007fab  jz      short loc_180008013
0x180007fad  lea     rax, [rsp+2310h+hKey]
0x180007fb2  mov     dword ptr [rsp+2310h+hKey], edi
0x180007fb6  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180007fbb  xor     r9d, r9d; lpClass
0x180007fbe  lea     rax, [rsp+2310h+var_2298]
0x180007fc3  mov     [rsp+2310h+var_2298], rdi
0x180007fc8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180007fcd  xor     r8d, r8d; Reserved
0x180007fd0  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180007fd5  mov     rdx, rsi; lpSubKey
0x180007fd8  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180007fdd  mov     rcx, r15; hKey
0x180007fe0  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180007fe4  call    cs:__imp_RegCreateKeyExW
0x180007fea  test    eax, eax
0x180007fec  jnz     loc_180008350
0x180007ff2  mov     eax, edi
0x180007ff4  test    rbx, rbx
0x180007ff7  jz      short loc_180008002
0x180007ff9  mov     rcx, rbx; hKey
0x180007ffc  call    cs:__imp_RegCloseKey
0x180008002  mov     rbx, [rsp+2310h+var_2298]
0x180008007  mov     [rbp+2210h+var_2290], rbx
0x18000800b  test    eax, eax
0x18000800d  jnz     loc_180008350
0x180008013  mov     rdx, rsi; unsigned __int16 *
0x180008016  mov     rcx, r13; this
0x180008019  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000801e  xor     edx, edx
0x180008020  mov     edi, eax
0x180008022  test    eax, eax
0x180008024  js      loc_180008359
0x18000802a  cmp     word ptr [rsi], 3Dh ; '='
0x18000802e  jnz     short loc_180008052
0x180008030  mov     r9, rsi; unsigned __int16 *
0x180008033  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180008037  xor     r8d, r8d; unsigned __int16 *
0x18000803a  mov     rcx, r13; this
0x18000803d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008042  mov     rbx, [rbp+2210h+var_2290]
0x180008046  xor     edx, edx
0x180008048  mov     edi, eax
0x18000804a  test    eax, eax
0x18000804c  js      loc_180008359
0x180008052  mov     r12d, [rsp+2310h+var_22A8]
0x180008057  cmp     word ptr [rsi], 7Bh ; '{'
0x18000805b  jnz     loc_1800081EE
0x180008061  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008065  inc     rax
0x180008068  cmp     [rsi+rax*2], dx
0x18000806c  jnz     short loc_180008065
0x18000806e  cmp     rax, 1
0x180008072  jnz     loc_1800081EE
0x180008078  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x18000807c  mov     r9d, r12d; int
0x18000807f  mov     rdx, rsi; unsigned __int16 *
0x180008082  mov     r8, rbx; HKEY
0x180008085  mov     rcx, r13; this
0x180008088  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000808d  mov     edi, eax
0x18000808f  test    eax, eax
0x180008091  js      loc_180008359
0x180008097  mov     rdx, rsi; unsigned __int16 *
0x18000809a  mov     rcx, r13; this
0x18000809d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800080a2  jmp     loc_180007ED6
0x1800080a7  mov     edi, [rbp+2210h+arg_20]
0x1800080ad  xor     eax, eax
0x1800080af  test    edi, edi
  ... truncated ...
```
