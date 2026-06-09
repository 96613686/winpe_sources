# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000e1a8`
- end: `0x18000e781`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000dddc`
- `0x18000e1a8`

## callees

- `0x18000677c`
- `0x180006f14`
- `0x180006f84`
- `0x1800077c0`
- `0x180007b44`
- `0x18000c05c`
- `0x18000c348`
- `0x18000c5c0`
- `0x18000c9f4`
- `0x18000dcc8`
- `0x18000e1a8`
- `0x18000f04c`
- `0x18000f11c`
- `0x18002f3b0`
- `0x18002f470`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000e5ae`
- `msvcrt!wcsncpy_s` at `0x18000e5ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e3fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e3fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e4af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e4af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e223`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e236`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e30a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e339`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e223`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e236`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e30a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e339`

## string_xrefs

- `0x18000e22c`: `ForceRemove`
- `0x18000e300`: `NoRemove`
- `0x18000e219`: `Delete`

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
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e1a8  push    rbp
0x18000e1aa  push    rbx
0x18000e1ab  push    rsi
0x18000e1ac  push    rdi
0x18000e1ad  push    r12
0x18000e1af  push    r13
0x18000e1b1  push    r14
0x18000e1b3  push    r15
0x18000e1b5  lea     rbp, [rsp-21C8h]
0x18000e1bd  mov     eax, 22C8h
0x18000e1c2  call    _alloca_probe
0x18000e1c7  sub     rsp, rax
0x18000e1ca  mov     rax, cs:__security_cookie
0x18000e1d1  xor     rax, rsp
0x18000e1d4  mov     [rbp+2200h+var_50], rax
0x18000e1db  mov     r15d, r9d
0x18000e1de  mov     [rsp+2300h+var_22B0], r9d
0x18000e1e3  mov     r13, r8
0x18000e1e6  mov     rdi, rdx
0x18000e1e9  mov     rsi, rcx
0x18000e1ec  xor     r14d, r14d
0x18000e1ef  mov     [rsp+2300h+var_2290], r14
0x18000e1f4  mov     [rsp+2300h+var_2288], r14
0x18000e1f9  mov     [rbp+2200h+var_2280], r14
0x18000e1fd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e202  test    eax, eax
0x18000e204  mov     ebx, eax
0x18000e206  js      loc_18000E735
0x18000e20c  xor     r12d, r12d
0x18000e20f  cmp     word ptr [rdi], 7Dh ; '}'
0x18000e213  jz      loc_18000E735
0x18000e219  lea     rdx, String2; "Delete"
0x18000e220  mov     rcx, rdi; lpString1
0x18000e223  call    cs:__imp_lstrcmpiW
0x18000e229  mov     r14d, eax
0x18000e22c  lea     rdx, aForceremove; "ForceRemove"
0x18000e233  mov     rcx, rdi; lpString1
0x18000e236  call    cs:__imp_lstrcmpiW
0x18000e23c  test    eax, eax
0x18000e23e  jz      short loc_18000E249
0x18000e240  test    r14d, r14d
0x18000e243  jnz     loc_18000E2FA
0x18000e249  mov     rdx, rdi; unsigned __int16 *
0x18000e24c  mov     rcx, rsi; this
0x18000e24f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e254  mov     ebx, eax
0x18000e256  test    eax, eax
0x18000e258  js      loc_18000E735
0x18000e25e  test    r15d, r15d
0x18000e261  jz      loc_18000E2FA
0x18000e267  mov     [rsp+2300h+hKey], r12
0x18000e26c  mov     [rsp+2300h+var_22A0], r12
0x18000e271  mov     [rsp+2300h+var_2298], r12
0x18000e276  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000e27b  mov     rcx, rdi; lpsz
0x18000e27e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000e283  test    rax, rax
0x18000e286  jnz     loc_18000E726
0x18000e28c  mov     rdx, rdi; unsigned __int16 *
0x18000e28f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000e294  test    eax, eax
0x18000e296  jz      short loc_18000E2AF
0x18000e298  mov     [rsp+2300h+hKey], r13
0x18000e29d  mov     rdx, rdi; unsigned __int16 *
0x18000e2a0  lea     rcx, [rsp+2300h+hKey]; this
0x18000e2a5  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000e2aa  mov     [rsp+2300h+hKey], r12
0x18000e2af  test    r14d, r14d
0x18000e2b2  jnz     short loc_18000E2F0
0x18000e2b4  mov     rdx, rdi; unsigned __int16 *
0x18000e2b7  mov     rcx, rsi; this
0x18000e2ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e2bf  mov     ebx, eax
0x18000e2c1  xor     r14d, r14d
0x18000e2c4  test    eax, eax
0x18000e2c6  js      loc_18000E76D
0x18000e2cc  mov     rdx, rdi; unsigned __int16 *
0x18000e2cf  mov     rcx, rsi; this
0x18000e2d2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000e2d7  mov     ebx, eax
0x18000e2d9  test    eax, eax
0x18000e2db  lea     rcx, [rsp+2300h+hKey]; this
0x18000e2e0  js      loc_18000E772
0x18000e2e6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e2eb  jmp     loc_18000E514
0x18000e2f0  lea     rcx, [rsp+2300h+hKey]; this
0x18000e2f5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e2fa  mov     r12d, 1
0x18000e300  lea     rdx, aNoremove; "NoRemove"
0x18000e307  mov     rcx, rdi; lpString1
0x18000e30a  call    cs:__imp_lstrcmpiW
0x18000e310  xor     r14d, r14d
0x18000e313  test    eax, eax
0x18000e315  jnz     short loc_18000E32F
0x18000e317  mov     r12d, r14d
0x18000e31a  mov     rdx, rdi; unsigned __int16 *
0x18000e31d  mov     rcx, rsi; this
0x18000e320  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e325  mov     ebx, eax
0x18000e327  test    eax, eax
0x18000e329  js      loc_18000E735
0x18000e32f  lea     rdx, aVal; "Val"
0x18000e336  mov     rcx, rdi; lpString1
0x18000e339  call    cs:__imp_lstrcmpiW
0x18000e33f  test    eax, eax
0x18000e341  jnz     loc_18000E428
0x18000e347  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000e34e  mov     rcx, rsi; this
0x18000e351  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e356  mov     ebx, eax
0x18000e358  test    eax, eax
0x18000e35a  js      loc_18000E735
0x18000e360  mov     rdx, rdi; unsigned __int16 *
0x18000e363  mov     rcx, rsi; this
0x18000e366  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e36b  mov     ebx, eax
0x18000e36d  test    eax, eax
0x18000e36f  js      loc_18000E735
0x18000e375  cmp     word ptr [rdi], 3Dh ; '='
0x18000e379  jnz     loc_18000E730
0x18000e37f  test    r15d, r15d
0x18000e382  jz      short loc_18000E3B6
0x18000e384  mov     [rsp+2300h+var_22A0], r14
0x18000e389  mov     [rsp+2300h+var_2298], r14
0x18000e38e  mov     [rsp+2300h+hKey], r13
0x18000e393  mov     r9, rdi; unsigned __int16 *
0x18000e396  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000e39d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000e3a2  mov     rcx, rsi; this
0x18000e3a5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000e3aa  mov     ebx, eax
0x18000e3ac  mov     [rsp+2300h+hKey], r14
0x18000e3b1  jmp     loc_18000E2D9
0x18000e3b6  cmp     [rbp+2200h+arg_20], r14d
0x18000e3bd  jnz     short loc_18000E418
0x18000e3bf  test    r12d, r12d
0x18000e3c2  jz      short loc_18000E418
0x18000e3c4  mov     [rsp+2300h+hKey], r14
0x18000e3c9  mov     [rsp+2300h+var_22A0], r14
0x18000e3ce  mov     [rsp+2300h+var_2298], r14
0x18000e3d3  mov     r9d, 20006h; unsigned int
0x18000e3d9  xor     r8d, r8d; lpSubKey
0x18000e3dc  mov     rdx, r13; hKey
0x18000e3df  lea     rcx, [rsp+2300h+hKey]; this
0x18000e3e4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e3e9  test    eax, eax
0x18000e3eb  jnz     loc_18000E764
0x18000e3f1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000e3f8  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000e3fd  call    cs:__imp_RegDeleteValueW
0x18000e403  test    eax, 0FFFFFFFDh
0x18000e408  jnz     loc_18000E764
0x18000e40e  lea     rcx, [rsp+2300h+hKey]; this
0x18000e413  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e418  mov     rdx, rdi; unsigned __int16 *
0x18000e41b  mov     rcx, rsi; this
0x18000e41e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000e423  jmp     loc_18000E202
0x18000e428  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000e42d  mov     rcx, rdi; lpsz
0x18000e430  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000e435  test    rax, rax
0x18000e438  jnz     loc_18000E730
0x18000e43e  test    r15d, r15d
0x18000e441  jz      loc_18000E563
0x18000e447  mov     ebx, 2001Fh
0x18000e44c  mov     r9d, ebx; unsigned int
0x18000e44f  mov     r8, rdi; lpSubKey
0x18000e452  mov     rdx, r13; hKey
0x18000e455  lea     rcx, [rsp+2300h+var_2290]; this
0x18000e45a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e45f  test    eax, eax
0x18000e461  jz      short loc_18000E4DC
0x18000e463  lea     r9d, [rbx-6]; unsigned int
0x18000e467  mov     r8, rdi; lpSubKey
0x18000e46a  mov     rdx, r13; hKey
0x18000e46d  lea     rcx, [rsp+2300h+var_2290]; this
0x18000e472  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e477  test    eax, eax
0x18000e479  jz      short loc_18000E4DC
0x18000e47b  mov     [rbp+2200h+dwDisposition], r14d
0x18000e47f  mov     [rbp+2200h+var_2270], r14
0x18000e483  lea     rax, [rbp+2200h+dwDisposition]
0x18000e487  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000e48c  lea     rax, [rbp+2200h+var_2270]
0x18000e490  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000e495  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000e49a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000e49e  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000e4a3  xor     r9d, r9d; lpClass
0x18000e4a6  xor     r8d, r8d; Reserved
0x18000e4a9  mov     rdx, rdi; lpSubKey
0x18000e4ac  mov     rcx, r13; hKey
0x18000e4af  call    cs:__imp_RegCreateKeyExW
0x18000e4b5  mov     ecx, eax
0x18000e4b7  test    eax, eax
0x18000e4b9  jnz     loc_18000E663
0x18000e4bf  lea     rcx, [rsp+2300h+var_2290]; this
0x18000e4c4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e4c9  mov     ecx, eax
0x18000e4cb  mov     rax, [rbp+2200h+var_2270]
0x18000e4cf  mov     [rsp+2300h+var_2290], rax
0x18000e4d4  test    ecx, ecx
0x18000e4d6  jnz     loc_18000E663
0x18000e4dc  mov     rdx, rdi; unsigned __int16 *
0x18000e4df  mov     rcx, rsi; this
0x18000e4e2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e4e7  mov     ebx, eax
0x18000e4e9  test    eax, eax
0x18000e4eb  js      loc_18000E735
0x18000e4f1  cmp     word ptr [rdi], 3Dh ; '='
0x18000e4f5  jnz     short loc_18000E514
0x18000e4f7  mov     r9, rdi; unsigned __int16 *
0x18000e4fa  xor     r8d, r8d; unsigned __int16 *
0x18000e4fd  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000e502  mov     rcx, rsi; this
0x18000e505  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000e50a  mov     ebx, eax
0x18000e50c  test    eax, eax
0x18000e50e  js      loc_18000E735
0x18000e514  cmp     word ptr [rdi], 7Bh ; '{'
0x18000e518  jnz     loc_18000E20C
0x18000e51e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e522  inc     rax
0x18000e525  cmp     [rdi+rax*2], r14w
0x18000e52a  jnz     short loc_18000E522
0x18000e52c  cmp     rax, 1
0x18000e530  jnz     loc_18000E20C
0x18000e536  mov     [rsp+2300h+dwOptions], r14d; int
0x18000e53b  mov     r9d, r15d; int
0x18000e53e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000e543  mov     rdx, rdi; unsigned __int16 *
0x18000e546  mov     rcx, rsi; this
0x18000e549  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000e54e  mov     ebx, eax
0x18000e550  test    eax, eax
0x18000e552  js      loc_18000E735
0x18000e558  mov     rdx, rdi
0x18000e55b  mov     rcx, rsi
0x18000e55e  jmp     loc_18000E1FD
0x18000e563  cmp     [rbp+2200h+arg_20], r14d
0x18000e56a  jnz     short loc_18000E587
0x18000e56c  mov     r9d, 20019h; unsigned int
0x18000e572  mov     r8, rdi; lpSubKey
0x18000e575  mov     rdx, r13; hKey
0x18000e578  lea     rcx, [rsp+2300h+var_2290]; this
0x18000e57d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e582  mov     r14d, eax
0x18000e585  jmp     short loc_18000E58D
0x18000e587  mov     r14d, 2
0x18000e58d  mov     r15d, 1
0x18000e593  test    r14d, r14d
0x18000e596  cmovz   r15d, [rbp+2200h+arg_20]
0x18000e59e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000e5a2  mov     r8, rdi; Source
0x18000e5a5  mov     edx, 104h; SizeInWords
0x18000e5aa  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000e5ae  call    cs:__imp_wcsncpy_s
0x18000e5b4  mov     ecx, eax; int
0x18000e5b6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000e5bb  mov     rdx, rdi; unsigned __int16 *
0x18000e5be  mov     rcx, rsi; this
0x18000e5c1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e5c6  mov     ebx, eax
0x18000e5c8  test    eax, eax
0x18000e5ca  js      loc_18000E735
0x18000e5d0  mov     rdx, rdi; unsigned __int16 *
0x18000e5d3  mov     rcx, rsi; this
0x18000e5d6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000e5db  mov     ebx, eax
0x18000e5dd  xor     ecx, ecx
0x18000e5df  test    eax, eax
0x18000e5e1  js      loc_18000E735
0x18000e5e7  cmp     word ptr [rdi], 7Bh ; '{'
0x18000e5eb  jnz     short loc_18000E63C
0x18000e5ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e5f1  inc     rax
0x18000e5f4  cmp     [rdi+rax*2], cx
0x18000e5f8  jnz     short loc_18000E5F1
0x18000e5fa  cmp     rax, 1
0x18000e5fe  jnz     short loc_18000E63C
0x18000e600  mov     [rsp+2300h+dwOptions], r15d; int
0x18000e605  xor     r9d, r9d; int
0x18000e608  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000e60d  mov     rdx, rdi; unsigned __int16 *
0x18000e610  mov     rcx, rsi; this
0x18000e613  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000e618  mov     ebx, eax
0x18000e61a  test    eax, eax
0x18000e61c  jns     short loc_18000E627
0x18000e61e  test    r15d, r15d
0x18000e621  jz      loc_18000E735
0x18000e627  mov     rdx, rdi; unsigned __int16 *
0x18000e62a  mov     rcx, rsi; this
0x18000e62d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e632  mov     ebx, eax
0x18000e634  test    eax, eax
0x18000e636  js      loc_18000E735
0x18000e63c  cmp     r14d, 2
0x18000e640  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
