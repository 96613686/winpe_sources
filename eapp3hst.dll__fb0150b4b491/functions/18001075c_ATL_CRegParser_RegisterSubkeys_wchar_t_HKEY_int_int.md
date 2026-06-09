# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18001075c`
- end: `0x180010d35`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001043c`
- `0x18001075c`

## callees

- `0x1800017a0`
- `0x18000f2dc`
- `0x18000fa74`
- `0x18000fae4`
- `0x18000fafc`
- `0x18000fc14`
- `0x18000fc40`
- `0x18000fe28`
- `0x18000fee4`
- `0x180010044`
- `0x180010328`
- `0x18001075c`
- `0x180010d90`
- `0x180010e60`
- `0x18002f450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010b62`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010b62`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800109b1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800109b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010a63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010a63`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800108be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800108ed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800108be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800108ed`

## string_xrefs

- `0x1800107e0`: `ForceRemove`
- `0x1800108b4`: `NoRemove`
- `0x1800107cd`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  int v5; // r15d
  wchar_t *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
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
          v29 = 0;
          v30 = 0;
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
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
      v29 = 0;
      v30 = 0;
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
    v29 = 0;
    v30 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001075c  push    rbp
0x18001075e  push    rbx
0x18001075f  push    rsi
0x180010760  push    rdi
0x180010761  push    r12
0x180010763  push    r13
0x180010765  push    r14
0x180010767  push    r15
0x180010769  lea     rbp, [rsp-21C8h]
0x180010771  mov     eax, 22C8h
0x180010776  call    _alloca_probe
0x18001077b  sub     rsp, rax
0x18001077e  mov     rax, cs:__security_cookie
0x180010785  xor     rax, rsp
0x180010788  mov     [rbp+2200h+var_50], rax
0x18001078f  mov     r15d, r9d
0x180010792  mov     [rsp+2300h+var_22B0], r9d
0x180010797  mov     r13, r8
0x18001079a  mov     rdi, rdx
0x18001079d  mov     rsi, rcx
0x1800107a0  xor     r14d, r14d
0x1800107a3  mov     [rsp+2300h+var_2290], r14
0x1800107a8  mov     [rsp+2300h+var_2288], r14
0x1800107ad  mov     [rbp+2200h+var_2280], r14
0x1800107b1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800107b6  test    eax, eax
0x1800107b8  mov     ebx, eax
0x1800107ba  js      loc_180010CE9
0x1800107c0  xor     r12d, r12d
0x1800107c3  cmp     word ptr [rdi], 7Dh ; '}'
0x1800107c7  jz      loc_180010CE9
0x1800107cd  lea     rdx, String2; "Delete"
0x1800107d4  mov     rcx, rdi; lpString1
0x1800107d7  call    cs:__imp_lstrcmpiW
0x1800107dd  mov     r14d, eax
0x1800107e0  lea     rdx, aForceremove; "ForceRemove"
0x1800107e7  mov     rcx, rdi; lpString1
0x1800107ea  call    cs:__imp_lstrcmpiW
0x1800107f0  test    eax, eax
0x1800107f2  jz      short loc_1800107FD
0x1800107f4  test    r14d, r14d
0x1800107f7  jnz     loc_1800108AE
0x1800107fd  mov     rdx, rdi; wchar_t *
0x180010800  mov     rcx, rsi; this
0x180010803  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010808  mov     ebx, eax
0x18001080a  test    eax, eax
0x18001080c  js      loc_180010CE9
0x180010812  test    r15d, r15d
0x180010815  jz      loc_1800108AE
0x18001081b  mov     [rsp+2300h+hKey], r12
0x180010820  mov     [rsp+2300h+var_22A0], r12
0x180010825  mov     [rsp+2300h+var_2298], r12
0x18001082a  mov     edx, 5Ch ; '\'; wchar_t
0x18001082f  mov     rcx, rdi; lpsz
0x180010832  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180010837  test    rax, rax
0x18001083a  jnz     loc_180010CDA
0x180010840  mov     rdx, rdi; wchar_t *
0x180010843  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x180010848  test    eax, eax
0x18001084a  jz      short loc_180010863
0x18001084c  mov     [rsp+2300h+hKey], r13
0x180010851  mov     rdx, rdi; wchar_t *
0x180010854  lea     rcx, [rsp+2300h+hKey]; this
0x180010859  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001085e  mov     [rsp+2300h+hKey], r12
0x180010863  test    r14d, r14d
0x180010866  jnz     short loc_1800108A4
0x180010868  mov     rdx, rdi; wchar_t *
0x18001086b  mov     rcx, rsi; this
0x18001086e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010873  mov     ebx, eax
0x180010875  xor     r14d, r14d
0x180010878  test    eax, eax
0x18001087a  js      loc_180010D21
0x180010880  mov     rdx, rdi; wchar_t *
0x180010883  mov     rcx, rsi; this
0x180010886  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001088b  mov     ebx, eax
0x18001088d  test    eax, eax
0x18001088f  lea     rcx, [rsp+2300h+hKey]; this
0x180010894  js      loc_180010D26
0x18001089a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001089f  jmp     loc_180010AC8
0x1800108a4  lea     rcx, [rsp+2300h+hKey]; this
0x1800108a9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800108ae  mov     r12d, 1
0x1800108b4  lea     rdx, aNoremove; "NoRemove"
0x1800108bb  mov     rcx, rdi; lpString1
0x1800108be  call    cs:__imp_lstrcmpiW
0x1800108c4  xor     r14d, r14d
0x1800108c7  test    eax, eax
0x1800108c9  jnz     short loc_1800108E3
0x1800108cb  mov     r12d, r14d
0x1800108ce  mov     rdx, rdi; wchar_t *
0x1800108d1  mov     rcx, rsi; this
0x1800108d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800108d9  mov     ebx, eax
0x1800108db  test    eax, eax
0x1800108dd  js      loc_180010CE9
0x1800108e3  lea     rdx, aVal; "Val"
0x1800108ea  mov     rcx, rdi; lpString1
0x1800108ed  call    cs:__imp_lstrcmpiW
0x1800108f3  test    eax, eax
0x1800108f5  jnz     loc_1800109DC
0x1800108fb  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x180010902  mov     rcx, rsi; this
0x180010905  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001090a  mov     ebx, eax
0x18001090c  test    eax, eax
0x18001090e  js      loc_180010CE9
0x180010914  mov     rdx, rdi; wchar_t *
0x180010917  mov     rcx, rsi; this
0x18001091a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001091f  mov     ebx, eax
0x180010921  test    eax, eax
0x180010923  js      loc_180010CE9
0x180010929  cmp     word ptr [rdi], 3Dh ; '='
0x18001092d  jnz     loc_180010CE4
0x180010933  test    r15d, r15d
0x180010936  jz      short loc_18001096A
0x180010938  mov     [rsp+2300h+var_22A0], r14
0x18001093d  mov     [rsp+2300h+var_2298], r14
0x180010942  mov     [rsp+2300h+hKey], r13
0x180010947  mov     r9, rdi; wchar_t *
0x18001094a  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x180010951  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180010956  mov     rcx, rsi; this
0x180010959  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18001095e  mov     ebx, eax
0x180010960  mov     [rsp+2300h+hKey], r14
0x180010965  jmp     loc_18001088D
0x18001096a  cmp     [rbp+2200h+arg_20], r14d
0x180010971  jnz     short loc_1800109CC
0x180010973  test    r12d, r12d
0x180010976  jz      short loc_1800109CC
0x180010978  mov     [rsp+2300h+hKey], r14
0x18001097d  mov     [rsp+2300h+var_22A0], r14
0x180010982  mov     [rsp+2300h+var_2298], r14
0x180010987  mov     r9d, 20006h; unsigned int
0x18001098d  xor     r8d, r8d; lpSubKey
0x180010990  mov     rdx, r13; hKey
0x180010993  lea     rcx, [rsp+2300h+hKey]; this
0x180010998  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001099d  test    eax, eax
0x18001099f  jnz     loc_180010D18
0x1800109a5  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800109ac  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800109b1  call    cs:__imp_RegDeleteValueW
0x1800109b7  test    eax, 0FFFFFFFDh
0x1800109bc  jnz     loc_180010D18
0x1800109c2  lea     rcx, [rsp+2300h+hKey]; this
0x1800109c7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800109cc  mov     rdx, rdi; wchar_t *
0x1800109cf  mov     rcx, rsi; this
0x1800109d2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x1800109d7  jmp     loc_1800107B6
0x1800109dc  mov     edx, 5Ch ; '\'; wchar_t
0x1800109e1  mov     rcx, rdi; lpsz
0x1800109e4  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x1800109e9  test    rax, rax
0x1800109ec  jnz     loc_180010CE4
0x1800109f2  test    r15d, r15d
0x1800109f5  jz      loc_180010B17
0x1800109fb  mov     ebx, 2001Fh
0x180010a00  mov     r9d, ebx; unsigned int
0x180010a03  mov     r8, rdi; lpSubKey
0x180010a06  mov     rdx, r13; hKey
0x180010a09  lea     rcx, [rsp+2300h+var_2290]; this
0x180010a0e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010a13  test    eax, eax
0x180010a15  jz      short loc_180010A90
0x180010a17  lea     r9d, [rbx-6]; unsigned int
0x180010a1b  mov     r8, rdi; lpSubKey
0x180010a1e  mov     rdx, r13; hKey
0x180010a21  lea     rcx, [rsp+2300h+var_2290]; this
0x180010a26  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010a2b  test    eax, eax
0x180010a2d  jz      short loc_180010A90
0x180010a2f  mov     [rbp+2200h+dwDisposition], r14d
0x180010a33  mov     [rbp+2200h+var_2270], r14
0x180010a37  lea     rax, [rbp+2200h+dwDisposition]
0x180010a3b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180010a40  lea     rax, [rbp+2200h+var_2270]
0x180010a44  mov     [rsp+2300h+phkResult], rax; phkResult
0x180010a49  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180010a4e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180010a52  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180010a57  xor     r9d, r9d; lpClass
0x180010a5a  xor     r8d, r8d; Reserved
0x180010a5d  mov     rdx, rdi; lpSubKey
0x180010a60  mov     rcx, r13; hKey
0x180010a63  call    cs:__imp_RegCreateKeyExW
0x180010a69  mov     ecx, eax
0x180010a6b  test    eax, eax
0x180010a6d  jnz     loc_180010C17
0x180010a73  lea     rcx, [rsp+2300h+var_2290]; this
0x180010a78  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010a7d  mov     ecx, eax
0x180010a7f  mov     rax, [rbp+2200h+var_2270]
0x180010a83  mov     [rsp+2300h+var_2290], rax
0x180010a88  test    ecx, ecx
0x180010a8a  jnz     loc_180010C17
0x180010a90  mov     rdx, rdi; wchar_t *
0x180010a93  mov     rcx, rsi; this
0x180010a96  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010a9b  mov     ebx, eax
0x180010a9d  test    eax, eax
0x180010a9f  js      loc_180010CE9
0x180010aa5  cmp     word ptr [rdi], 3Dh ; '='
0x180010aa9  jnz     short loc_180010AC8
0x180010aab  mov     r9, rdi; wchar_t *
0x180010aae  xor     r8d, r8d; wchar_t *
0x180010ab1  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180010ab6  mov     rcx, rsi; this
0x180010ab9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180010abe  mov     ebx, eax
0x180010ac0  test    eax, eax
0x180010ac2  js      loc_180010CE9
0x180010ac8  cmp     word ptr [rdi], 7Bh ; '{'
0x180010acc  jnz     loc_1800107C0
0x180010ad2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ad6  inc     rax
0x180010ad9  cmp     [rdi+rax*2], r14w
0x180010ade  jnz     short loc_180010AD6
0x180010ae0  cmp     rax, 1
0x180010ae4  jnz     loc_1800107C0
0x180010aea  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180010aef  mov     r9d, r15d; int
0x180010af2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180010af7  mov     rdx, rdi; wchar_t *
0x180010afa  mov     rcx, rsi; this
0x180010afd  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010b02  mov     ebx, eax
0x180010b04  test    eax, eax
0x180010b06  js      loc_180010CE9
0x180010b0c  mov     rdx, rdi
0x180010b0f  mov     rcx, rsi
0x180010b12  jmp     loc_1800107B1
0x180010b17  cmp     [rbp+2200h+arg_20], r14d
0x180010b1e  jnz     short loc_180010B3B
0x180010b20  mov     r9d, 20019h; unsigned int
0x180010b26  mov     r8, rdi; lpSubKey
0x180010b29  mov     rdx, r13; hKey
0x180010b2c  lea     rcx, [rsp+2300h+var_2290]; this
0x180010b31  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010b36  mov     r14d, eax
0x180010b39  jmp     short loc_180010B41
0x180010b3b  mov     r14d, 2
0x180010b41  mov     r15d, 1
0x180010b47  test    r14d, r14d
0x180010b4a  cmovz   r15d, [rbp+2200h+arg_20]
0x180010b52  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010b56  mov     r8, rdi
0x180010b59  mov     edx, 104h
0x180010b5e  lea     rcx, [rbp+2200h+var_2260]
0x180010b62  call    cs:__imp__o_wcsncpy_s
0x180010b68  mov     ecx, eax; int
0x180010b6a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180010b6f  mov     rdx, rdi; wchar_t *
0x180010b72  mov     rcx, rsi; this
0x180010b75  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010b7a  mov     ebx, eax
0x180010b7c  test    eax, eax
0x180010b7e  js      loc_180010CE9
0x180010b84  mov     rdx, rdi; wchar_t *
0x180010b87  mov     rcx, rsi; this
0x180010b8a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180010b8f  mov     ebx, eax
0x180010b91  xor     ecx, ecx
0x180010b93  test    eax, eax
0x180010b95  js      loc_180010CE9
0x180010b9b  cmp     word ptr [rdi], 7Bh ; '{'
0x180010b9f  jnz     short loc_180010BF0
0x180010ba1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ba5  inc     rax
0x180010ba8  cmp     [rdi+rax*2], cx
0x180010bac  jnz     short loc_180010BA5
0x180010bae  cmp     rax, 1
0x180010bb2  jnz     short loc_180010BF0
0x180010bb4  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180010bb9  xor     r9d, r9d; int
0x180010bbc  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180010bc1  mov     rdx, rdi; wchar_t *
0x180010bc4  mov     rcx, rsi; this
0x180010bc7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010bcc  mov     ebx, eax
0x180010bce  test    eax, eax
0x180010bd0  jns     short loc_180010BDB
0x180010bd2  test    r15d, r15d
0x180010bd5  jz      loc_180010CE9
0x180010bdb  mov     rdx, rdi; wchar_t *
0x180010bde  mov     rcx, rsi; this
0x180010be1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010be6  mov     ebx, eax
0x180010be8  test    eax, eax
0x180010bea  js      loc_180010CE9
0x180010bf0  cmp     r14d, 2
0x180010bf4  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
