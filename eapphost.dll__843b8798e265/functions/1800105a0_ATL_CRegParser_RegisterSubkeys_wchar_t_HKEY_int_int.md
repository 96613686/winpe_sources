# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x1800105a0`
- end: `0x180010ba4`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1540`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001024c`
- `0x1800105a0`

## callees

- `0x180002af0`
- `0x18000ee98`
- `0x18000f558`
- `0x18000f5cc`
- `0x18000f604`
- `0x18000f7b0`
- `0x18000f8e4`
- `0x18000fb8c`
- `0x18000fc34`
- `0x18000fe08`
- `0x18001012c`
- `0x1800105a0`
- `0x180010c0c`
- `0x180010ce4`
- `0x1800350c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800109ca`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800109ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001080d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001080d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800108c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800108c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001061b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010634`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001070e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010743`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001061b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010634`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001070e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010743`

## string_xrefs

- `0x18001062a`: `ForceRemove`
- `0x180010704`: `NoRemove`
- `0x180010611`: `Delete`

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
  LSTATUS v15; // eax
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
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
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
0x1800105a0  push    rbp
0x1800105a2  push    rbx
0x1800105a3  push    rsi
0x1800105a4  push    rdi
0x1800105a5  push    r12
0x1800105a7  push    r13
0x1800105a9  push    r14
0x1800105ab  push    r15
0x1800105ad  lea     rbp, [rsp-21C8h]
0x1800105b5  mov     eax, 22C8h
0x1800105ba  call    _alloca_probe
0x1800105bf  sub     rsp, rax
0x1800105c2  mov     rax, cs:__security_cookie
0x1800105c9  xor     rax, rsp
0x1800105cc  mov     [rbp+2200h+var_50], rax
0x1800105d3  mov     r15d, r9d
0x1800105d6  mov     [rsp+2300h+var_22B0], r9d
0x1800105db  mov     r13, r8
0x1800105de  mov     rdi, rdx
0x1800105e1  mov     rsi, rcx
0x1800105e4  xor     r14d, r14d
0x1800105e7  mov     [rsp+2300h+var_2290], r14
0x1800105ec  mov     [rsp+2300h+var_2288], r14
0x1800105f1  mov     [rbp+2200h+var_2280], r14
0x1800105f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800105fa  test    eax, eax
0x1800105fc  mov     ebx, eax
0x1800105fe  js      loc_180010B57
0x180010604  xor     r12d, r12d
0x180010607  cmp     word ptr [rdi], 7Dh ; '}'
0x18001060b  jz      loc_180010B57
0x180010611  lea     rdx, String2; "Delete"
0x180010618  mov     rcx, rdi; lpString1
0x18001061b  call    cs:__imp_lstrcmpiW
0x180010622  nop     dword ptr [rax+rax+00h]
0x180010627  mov     r14d, eax
0x18001062a  lea     rdx, aForceremove; "ForceRemove"
0x180010631  mov     rcx, rdi; lpString1
0x180010634  call    cs:__imp_lstrcmpiW
0x18001063b  nop     dword ptr [rax+rax+00h]
0x180010640  test    eax, eax
0x180010642  jz      short loc_18001064D
0x180010644  test    r14d, r14d
0x180010647  jnz     loc_1800106FE
0x18001064d  mov     rdx, rdi; wchar_t *
0x180010650  mov     rcx, rsi; this
0x180010653  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010658  mov     ebx, eax
0x18001065a  test    eax, eax
0x18001065c  js      loc_180010B57
0x180010662  test    r15d, r15d
0x180010665  jz      loc_1800106FE
0x18001066b  mov     [rsp+2300h+hKey], r12
0x180010670  mov     [rsp+2300h+var_22A0], r12
0x180010675  mov     [rsp+2300h+var_2298], r12
0x18001067a  mov     edx, 5Ch ; '\'; wchar_t
0x18001067f  mov     rcx, rdi; lpsz
0x180010682  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180010687  test    rax, rax
0x18001068a  jnz     loc_180010B48
0x180010690  mov     rdx, rdi; wchar_t *
0x180010693  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x180010698  test    eax, eax
0x18001069a  jz      short loc_1800106B3
0x18001069c  mov     [rsp+2300h+hKey], r13
0x1800106a1  mov     rdx, rdi; wchar_t *
0x1800106a4  lea     rcx, [rsp+2300h+hKey]; this
0x1800106a9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x1800106ae  mov     [rsp+2300h+hKey], r12
0x1800106b3  test    r14d, r14d
0x1800106b6  jnz     short loc_1800106F4
0x1800106b8  mov     rdx, rdi; wchar_t *
0x1800106bb  mov     rcx, rsi; this
0x1800106be  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800106c3  mov     ebx, eax
0x1800106c5  xor     r14d, r14d
0x1800106c8  test    eax, eax
0x1800106ca  js      loc_180010B90
0x1800106d0  mov     rdx, rdi; wchar_t *
0x1800106d3  mov     rcx, rsi; this
0x1800106d6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x1800106db  mov     ebx, eax
0x1800106dd  test    eax, eax
0x1800106df  lea     rcx, [rsp+2300h+hKey]; this
0x1800106e4  js      loc_180010B95
0x1800106ea  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800106ef  jmp     loc_180010930
0x1800106f4  lea     rcx, [rsp+2300h+hKey]; this
0x1800106f9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800106fe  mov     r12d, 1
0x180010704  lea     rdx, aNoremove; "NoRemove"
0x18001070b  mov     rcx, rdi; lpString1
0x18001070e  call    cs:__imp_lstrcmpiW
0x180010715  nop     dword ptr [rax+rax+00h]
0x18001071a  xor     r14d, r14d
0x18001071d  test    eax, eax
0x18001071f  jnz     short loc_180010739
0x180010721  mov     r12d, r14d
0x180010724  mov     rdx, rdi; wchar_t *
0x180010727  mov     rcx, rsi; this
0x18001072a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001072f  mov     ebx, eax
0x180010731  test    eax, eax
0x180010733  js      loc_180010B57
0x180010739  lea     rdx, aVal; "Val"
0x180010740  mov     rcx, rdi; lpString1
0x180010743  call    cs:__imp_lstrcmpiW
0x18001074a  nop     dword ptr [rax+rax+00h]
0x18001074f  test    eax, eax
0x180010751  jnz     loc_18001083E
0x180010757  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x18001075e  mov     rcx, rsi; this
0x180010761  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010766  mov     ebx, eax
0x180010768  test    eax, eax
0x18001076a  js      loc_180010B57
0x180010770  mov     rdx, rdi; wchar_t *
0x180010773  mov     rcx, rsi; this
0x180010776  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001077b  mov     ebx, eax
0x18001077d  test    eax, eax
0x18001077f  js      loc_180010B57
0x180010785  cmp     word ptr [rdi], 3Dh ; '='
0x180010789  jnz     loc_180010B52
0x18001078f  test    r15d, r15d
0x180010792  jz      short loc_1800107C6
0x180010794  mov     [rsp+2300h+var_22A0], r14
0x180010799  mov     [rsp+2300h+var_2298], r14
0x18001079e  mov     [rsp+2300h+hKey], r13
0x1800107a3  mov     r9, rdi; wchar_t *
0x1800107a6  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x1800107ad  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800107b2  mov     rcx, rsi; this
0x1800107b5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x1800107ba  mov     ebx, eax
0x1800107bc  mov     [rsp+2300h+hKey], r14
0x1800107c1  jmp     loc_1800106DD
0x1800107c6  cmp     [rbp+2200h+arg_20], r14d
0x1800107cd  jnz     short loc_18001082E
0x1800107cf  test    r12d, r12d
0x1800107d2  jz      short loc_18001082E
0x1800107d4  mov     [rsp+2300h+hKey], r14
0x1800107d9  mov     [rsp+2300h+var_22A0], r14
0x1800107de  mov     [rsp+2300h+var_2298], r14
0x1800107e3  mov     r9d, 20006h; unsigned int
0x1800107e9  xor     r8d, r8d; lpSubKey
0x1800107ec  mov     rdx, r13; hKey
0x1800107ef  lea     rcx, [rsp+2300h+hKey]; this
0x1800107f4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800107f9  test    eax, eax
0x1800107fb  jnz     loc_180010B87
0x180010801  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180010808  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001080d  call    cs:__imp_RegDeleteValueW
0x180010814  nop     dword ptr [rax+rax+00h]
0x180010819  test    eax, 0FFFFFFFDh
0x18001081e  jnz     loc_180010B87
0x180010824  lea     rcx, [rsp+2300h+hKey]; this
0x180010829  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001082e  mov     rdx, rdi; wchar_t *
0x180010831  mov     rcx, rsi; this
0x180010834  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180010839  jmp     loc_1800105FA
0x18001083e  mov     edx, 5Ch ; '\'; wchar_t
0x180010843  mov     rcx, rdi; lpsz
0x180010846  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18001084b  test    rax, rax
0x18001084e  jnz     loc_180010B52
0x180010854  test    r15d, r15d
0x180010857  jz      loc_18001097F
0x18001085d  mov     ebx, 2001Fh
0x180010862  mov     r9d, ebx; unsigned int
0x180010865  mov     r8, rdi; lpSubKey
0x180010868  mov     rdx, r13; hKey
0x18001086b  lea     rcx, [rsp+2300h+var_2290]; this
0x180010870  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010875  test    eax, eax
0x180010877  jz      short loc_1800108F8
0x180010879  lea     r9d, [rbx-6]; unsigned int
0x18001087d  mov     r8, rdi; lpSubKey
0x180010880  mov     rdx, r13; hKey
0x180010883  lea     rcx, [rsp+2300h+var_2290]; this
0x180010888  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001088d  test    eax, eax
0x18001088f  jz      short loc_1800108F8
0x180010891  mov     [rbp+2200h+dwDisposition], r14d
0x180010895  mov     [rbp+2200h+var_2270], r14
0x180010899  lea     rax, [rbp+2200h+dwDisposition]
0x18001089d  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x1800108a2  lea     rax, [rbp+2200h+var_2270]
0x1800108a6  mov     [rsp+2300h+phkResult], rax; phkResult
0x1800108ab  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800108b0  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1800108b4  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x1800108b9  xor     r9d, r9d; lpClass
0x1800108bc  xor     r8d, r8d; Reserved
0x1800108bf  mov     rdx, rdi; lpSubKey
0x1800108c2  mov     rcx, r13; hKey
0x1800108c5  call    cs:__imp_RegCreateKeyExW
0x1800108cc  nop     dword ptr [rax+rax+00h]
0x1800108d1  mov     ecx, eax
0x1800108d3  test    eax, eax
0x1800108d5  jnz     loc_180010A85
0x1800108db  lea     rcx, [rsp+2300h+var_2290]; this
0x1800108e0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800108e5  mov     ecx, eax
0x1800108e7  mov     rax, [rbp+2200h+var_2270]
0x1800108eb  mov     [rsp+2300h+var_2290], rax
0x1800108f0  test    ecx, ecx
0x1800108f2  jnz     loc_180010A85
0x1800108f8  mov     rdx, rdi; wchar_t *
0x1800108fb  mov     rcx, rsi; this
0x1800108fe  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010903  mov     ebx, eax
0x180010905  test    eax, eax
0x180010907  js      loc_180010B57
0x18001090d  cmp     word ptr [rdi], 3Dh ; '='
0x180010911  jnz     short loc_180010930
0x180010913  mov     r9, rdi; wchar_t *
0x180010916  xor     r8d, r8d; wchar_t *
0x180010919  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001091e  mov     rcx, rsi; this
0x180010921  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180010926  mov     ebx, eax
0x180010928  test    eax, eax
0x18001092a  js      loc_180010B57
0x180010930  cmp     word ptr [rdi], 7Bh ; '{'
0x180010934  jnz     loc_180010604
0x18001093a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001093e  inc     rax
0x180010941  cmp     [rdi+rax*2], r14w
0x180010946  jnz     short loc_18001093E
0x180010948  cmp     rax, 1
0x18001094c  jnz     loc_180010604
0x180010952  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180010957  mov     r9d, r15d; int
0x18001095a  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001095f  mov     rdx, rdi; wchar_t *
0x180010962  mov     rcx, rsi; this
0x180010965  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001096a  mov     ebx, eax
0x18001096c  test    eax, eax
0x18001096e  js      loc_180010B57
0x180010974  mov     rdx, rdi
0x180010977  mov     rcx, rsi
0x18001097a  jmp     loc_1800105F5
0x18001097f  cmp     [rbp+2200h+arg_20], r14d
0x180010986  jnz     short loc_1800109A3
0x180010988  mov     r9d, 20019h; unsigned int
0x18001098e  mov     r8, rdi; lpSubKey
0x180010991  mov     rdx, r13; hKey
0x180010994  lea     rcx, [rsp+2300h+var_2290]; this
0x180010999  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001099e  mov     r14d, eax
0x1800109a1  jmp     short loc_1800109A9
0x1800109a3  mov     r14d, 2
0x1800109a9  mov     r15d, 1
0x1800109af  test    r14d, r14d
0x1800109b2  cmovz   r15d, [rbp+2200h+arg_20]
0x1800109ba  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800109be  mov     r8, rdi
0x1800109c1  mov     edx, 104h
0x1800109c6  lea     rcx, [rbp+2200h+var_2260]
0x1800109ca  call    cs:__imp__o_wcsncpy_s
0x1800109d1  nop     dword ptr [rax+rax+00h]
0x1800109d6  mov     ecx, eax; int
0x1800109d8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800109dd  mov     rdx, rdi; wchar_t *
0x1800109e0  mov     rcx, rsi; this
0x1800109e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800109e8  mov     ebx, eax
0x1800109ea  test    eax, eax
0x1800109ec  js      loc_180010B57
0x1800109f2  mov     rdx, rdi; wchar_t *
0x1800109f5  mov     rcx, rsi; this
0x1800109f8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x1800109fd  mov     ebx, eax
0x1800109ff  xor     ecx, ecx
0x180010a01  test    eax, eax
0x180010a03  js      loc_180010B57
0x180010a09  cmp     word ptr [rdi], 7Bh ; '{'
0x180010a0d  jnz     short loc_180010A5E
0x180010a0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a13  inc     rax
0x180010a16  cmp     [rdi+rax*2], cx
0x180010a1a  jnz     short loc_180010A13
0x180010a1c  cmp     rax, 1
0x180010a20  jnz     short loc_180010A5E
0x180010a22  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180010a27  xor     r9d, r9d; int
0x180010a2a  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180010a2f  mov     rdx, rdi; wchar_t *
0x180010a32  mov     rcx, rsi; this
0x180010a35  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010a3a  mov     ebx, eax
0x180010a3c  test    eax, eax
0x180010a3e  jns     short loc_180010A49
0x180010a40  test    r15d, r15d
0x180010a43  jz      loc_180010B57
0x180010a49  mov     rdx, rdi; wchar_t *
  ... truncated ...
```
