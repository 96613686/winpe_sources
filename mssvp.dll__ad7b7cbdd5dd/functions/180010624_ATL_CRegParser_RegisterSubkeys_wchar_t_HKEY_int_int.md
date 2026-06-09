# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x180010624`
- end: `0x180010bb5`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1425`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180010268`
- `0x180010624`

## callees

- `0x180006270`
- `0x18000b6ac`
- `0x18000be84`
- `0x18000bed0`
- `0x18000c22c`
- `0x18000c344`
- `0x18000c3f0`
- `0x18000d3dc`
- `0x18000dfb4`
- `0x18000e960`
- `0x18000ec74`
- `0x180010154`
- `0x180010624`
- `0x180011760`
- `0x1800118f0`
- `0x180038ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800109e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800109e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001087a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001087a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800106a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800106b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010787`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800106a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800106b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010787`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800107b6`

## string_xrefs

- `0x1800106a9`: `ForceRemove`
- `0x18001077d`: `NoRemove`
- `0x180010696`: `Delete`

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
  wchar_t *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  HKEY v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v33[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v32, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v30 = 0;
        v31 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_78;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v32, a3, v7, v16, v27)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v32, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_78;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v33, 260, v7, -1);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
        }
      }
      v5 = a4;
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, v33) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, v33);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
          if ( v17 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v30 = 0;
            v31 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v30 = 0;
      v31 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v30 = 0;
    v31 = 0;
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
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010624  push    rbp
0x180010626  push    rbx
0x180010627  push    rsi
0x180010628  push    rdi
0x180010629  push    r12
0x18001062b  push    r13
0x18001062d  push    r14
0x18001062f  push    r15
0x180010631  lea     rbp, [rsp-21A8h]
0x180010639  mov     eax, 22A8h
0x18001063e  call    _alloca_probe
0x180010643  sub     rsp, rax
0x180010646  mov     rax, cs:__security_cookie
0x18001064d  xor     rax, rsp
0x180010650  mov     [rbp+21E0h+var_50], rax
0x180010657  mov     r15d, r9d
0x18001065a  mov     [rsp+22E0h+var_22A0], r9d
0x18001065f  mov     r13, r8
0x180010662  mov     rdi, rdx
0x180010665  mov     rsi, rcx
0x180010668  xor     r14d, r14d
0x18001066b  mov     [rsp+22E0h+var_2280], r14
0x180010670  mov     [rsp+22E0h+var_2278], r14
0x180010675  mov     [rsp+22E0h+var_2270], r14
0x18001067a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001067f  test    eax, eax
0x180010681  mov     ebx, eax
0x180010683  js      loc_180010B69
0x180010689  xor     r12d, r12d
0x18001068c  cmp     word ptr [rdi], 7Dh ; '}'
0x180010690  jz      loc_180010B69
0x180010696  lea     rdx, aDelete; "Delete"
0x18001069d  mov     rcx, rdi; lpString1
0x1800106a0  call    cs:__imp_lstrcmpiW
0x1800106a6  mov     r14d, eax
0x1800106a9  lea     rdx, aForceremove; "ForceRemove"
0x1800106b0  mov     rcx, rdi; lpString1
0x1800106b3  call    cs:__imp_lstrcmpiW
0x1800106b9  test    eax, eax
0x1800106bb  jz      short loc_1800106C6
0x1800106bd  test    r14d, r14d
0x1800106c0  jnz     loc_180010777
0x1800106c6  mov     rdx, rdi; wchar_t *
0x1800106c9  mov     rcx, rsi; this
0x1800106cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800106d1  mov     ebx, eax
0x1800106d3  test    eax, eax
0x1800106d5  js      loc_180010B69
0x1800106db  test    r15d, r15d
0x1800106de  jz      loc_180010777
0x1800106e4  mov     [rsp+22E0h+hKey], r12
0x1800106e9  mov     [rsp+22E0h+var_2290], r12
0x1800106ee  mov     [rsp+22E0h+var_2288], r12
0x1800106f3  mov     edx, 5Ch ; '\'; wchar_t
0x1800106f8  mov     rcx, rdi; lpsz
0x1800106fb  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180010700  test    rax, rax
0x180010703  jnz     loc_180010B5A
0x180010709  mov     rdx, rdi; wchar_t *
0x18001070c  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x180010711  test    eax, eax
0x180010713  jz      short loc_18001072C
0x180010715  mov     [rsp+22E0h+hKey], r13
0x18001071a  mov     rdx, rdi; wchar_t *
0x18001071d  lea     rcx, [rsp+22E0h+hKey]; this
0x180010722  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180010727  mov     [rsp+22E0h+hKey], r12
0x18001072c  test    r14d, r14d
0x18001072f  jnz     short loc_18001076D
0x180010731  mov     rdx, rdi; wchar_t *
0x180010734  mov     rcx, rsi; this
0x180010737  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001073c  mov     ebx, eax
0x18001073e  xor     r14d, r14d
0x180010741  test    eax, eax
0x180010743  js      loc_180010BA1
0x180010749  mov     rdx, rdi; wchar_t *
0x18001074c  mov     rcx, rsi; this
0x18001074f  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180010754  mov     ebx, eax
0x180010756  test    eax, eax
0x180010758  lea     rcx, [rsp+22E0h+hKey]; this
0x18001075d  js      loc_180010BA6
0x180010763  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010768  jmp     loc_180010948
0x18001076d  lea     rcx, [rsp+22E0h+hKey]; this
0x180010772  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010777  mov     r12d, 1
0x18001077d  lea     rdx, aNoremove; "NoRemove"
0x180010784  mov     rcx, rdi; lpString1
0x180010787  call    cs:__imp_lstrcmpiW
0x18001078d  xor     r14d, r14d
0x180010790  test    eax, eax
0x180010792  jnz     short loc_1800107AC
0x180010794  mov     r12d, r14d
0x180010797  mov     rdx, rdi; wchar_t *
0x18001079a  mov     rcx, rsi; this
0x18001079d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800107a2  mov     ebx, eax
0x1800107a4  test    eax, eax
0x1800107a6  js      loc_180010B69
0x1800107ac  lea     rdx, aVal; "Val"
0x1800107b3  mov     rcx, rdi; lpString1
0x1800107b6  call    cs:__imp_lstrcmpiW
0x1800107bc  test    eax, eax
0x1800107be  jnz     loc_1800108A5
0x1800107c4  lea     rdx, [rbp+21E0h+ValueName]; wchar_t *
0x1800107cb  mov     rcx, rsi; this
0x1800107ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800107d3  mov     ebx, eax
0x1800107d5  test    eax, eax
0x1800107d7  js      loc_180010B69
0x1800107dd  mov     rdx, rdi; wchar_t *
0x1800107e0  mov     rcx, rsi; this
0x1800107e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800107e8  mov     ebx, eax
0x1800107ea  test    eax, eax
0x1800107ec  js      loc_180010B69
0x1800107f2  cmp     word ptr [rdi], 3Dh ; '='
0x1800107f6  jnz     loc_180010B64
0x1800107fc  test    r15d, r15d
0x1800107ff  jz      short loc_180010833
0x180010801  mov     [rsp+22E0h+var_2290], r14
0x180010806  mov     [rsp+22E0h+var_2288], r14
0x18001080b  mov     [rsp+22E0h+hKey], r13
0x180010810  mov     r9, rdi; wchar_t *
0x180010813  lea     r8, [rbp+21E0h+ValueName]; wchar_t *
0x18001081a  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18001081f  mov     rcx, rsi; this
0x180010822  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180010827  mov     ebx, eax
0x180010829  mov     [rsp+22E0h+hKey], r14
0x18001082e  jmp     loc_180010756
0x180010833  cmp     [rbp+21E0h+arg_20], r14d
0x18001083a  jnz     short loc_180010895
0x18001083c  test    r12d, r12d
0x18001083f  jz      short loc_180010895
0x180010841  mov     [rsp+22E0h+hKey], r14
0x180010846  mov     [rsp+22E0h+var_2290], r14
0x18001084b  mov     [rsp+22E0h+var_2288], r14
0x180010850  mov     r9d, 20006h; unsigned int
0x180010856  xor     r8d, r8d; lpSubKey
0x180010859  mov     rdx, r13; hKey
0x18001085c  lea     rcx, [rsp+22E0h+hKey]; this
0x180010861  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010866  test    eax, eax
0x180010868  jnz     loc_180010B98
0x18001086e  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180010875  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18001087a  call    cs:__imp_RegDeleteValueW
0x180010880  test    eax, 0FFFFFFFDh
0x180010885  jnz     loc_180010B98
0x18001088b  lea     rcx, [rsp+22E0h+hKey]; this
0x180010890  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010895  mov     rdx, rdi; wchar_t *
0x180010898  mov     rcx, rsi; this
0x18001089b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x1800108a0  jmp     loc_18001067F
0x1800108a5  mov     edx, 5Ch ; '\'; wchar_t
0x1800108aa  mov     rcx, rdi; lpsz
0x1800108ad  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x1800108b2  test    rax, rax
0x1800108b5  jnz     loc_180010B64
0x1800108bb  test    r15d, r15d
0x1800108be  jz      loc_180010997
0x1800108c4  mov     r9d, 2001Fh; unsigned int
0x1800108ca  mov     r8, rdi; lpSubKey
0x1800108cd  mov     rdx, r13; hKey
0x1800108d0  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800108d5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800108da  test    eax, eax
0x1800108dc  jz      short loc_180010910
0x1800108de  mov     r9d, 20019h; unsigned int
0x1800108e4  mov     r8, rdi; lpSubKey
0x1800108e7  mov     rdx, r13; hKey
0x1800108ea  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800108ef  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800108f4  test    eax, eax
0x1800108f6  jz      short loc_180010910
0x1800108f8  mov     r8, rdi; lpSubKey
0x1800108fb  mov     rdx, r13; hKey
0x1800108fe  lea     rcx, [rsp+22E0h+var_2280]; this
0x180010903  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180010908  test    eax, eax
0x18001090a  jnz     loc_180010BAD
0x180010910  mov     rdx, rdi; wchar_t *
0x180010913  mov     rcx, rsi; this
0x180010916  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001091b  mov     ebx, eax
0x18001091d  test    eax, eax
0x18001091f  js      loc_180010B69
0x180010925  cmp     word ptr [rdi], 3Dh ; '='
0x180010929  jnz     short loc_180010948
0x18001092b  mov     r9, rdi; wchar_t *
0x18001092e  xor     r8d, r8d; wchar_t *
0x180010931  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180010936  mov     rcx, rsi; this
0x180010939  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18001093e  mov     ebx, eax
0x180010940  test    eax, eax
0x180010942  js      loc_180010B69
0x180010948  cmp     word ptr [rdi], 7Bh ; '{'
0x18001094c  jnz     loc_180010689
0x180010952  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010956  inc     rax
0x180010959  cmp     [rdi+rax*2], r14w
0x18001095e  jnz     short loc_180010956
0x180010960  cmp     rax, 1
0x180010964  jnz     loc_180010689
0x18001096a  mov     [rsp+22E0h+var_22C0], r14d; int
0x18001096f  mov     r9d, r15d; int
0x180010972  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180010977  mov     rdx, rdi; wchar_t *
0x18001097a  mov     rcx, rsi; this
0x18001097d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010982  mov     ebx, eax
0x180010984  test    eax, eax
0x180010986  js      loc_180010B69
0x18001098c  mov     rdx, rdi
0x18001098f  mov     rcx, rsi
0x180010992  jmp     loc_18001067A
0x180010997  cmp     [rbp+21E0h+arg_20], r14d
0x18001099e  jnz     short loc_1800109BB
0x1800109a0  mov     r9d, 20019h; unsigned int
0x1800109a6  mov     r8, rdi; lpSubKey
0x1800109a9  mov     rdx, r13; hKey
0x1800109ac  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800109b1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800109b6  mov     r14d, eax
0x1800109b9  jmp     short loc_1800109C1
0x1800109bb  mov     r14d, 2
0x1800109c1  mov     r15d, 1
0x1800109c7  test    r14d, r14d
0x1800109ca  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800109d2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800109d6  mov     r8, rdi
0x1800109d9  mov     edx, 104h
0x1800109de  lea     rcx, [rbp+21E0h+var_2260]
0x1800109e2  call    cs:__imp__o_wcsncpy_s
0x1800109e8  mov     ecx, eax; int
0x1800109ea  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800109ef  mov     rdx, rdi; wchar_t *
0x1800109f2  mov     rcx, rsi; this
0x1800109f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800109fa  mov     ebx, eax
0x1800109fc  test    eax, eax
0x1800109fe  js      loc_180010B69
0x180010a04  mov     rdx, rdi; wchar_t *
0x180010a07  mov     rcx, rsi; this
0x180010a0a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180010a0f  mov     ebx, eax
0x180010a11  xor     ecx, ecx
0x180010a13  test    eax, eax
0x180010a15  js      loc_180010B69
0x180010a1b  cmp     word ptr [rdi], 7Bh ; '{'
0x180010a1f  jnz     short loc_180010A70
0x180010a21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a25  inc     rax
0x180010a28  cmp     [rdi+rax*2], cx
0x180010a2c  jnz     short loc_180010A25
0x180010a2e  cmp     rax, 1
0x180010a32  jnz     short loc_180010A70
0x180010a34  mov     [rsp+22E0h+var_22C0], r15d; int
0x180010a39  xor     r9d, r9d; int
0x180010a3c  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180010a41  mov     rdx, rdi; wchar_t *
0x180010a44  mov     rcx, rsi; this
0x180010a47  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010a4c  mov     ebx, eax
0x180010a4e  test    eax, eax
0x180010a50  jns     short loc_180010A5B
0x180010a52  test    r15d, r15d
0x180010a55  jz      loc_180010B69
0x180010a5b  mov     rdx, rdi; wchar_t *
0x180010a5e  mov     rcx, rsi; this
0x180010a61  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010a66  mov     ebx, eax
0x180010a68  test    eax, eax
0x180010a6a  js      loc_180010B69
0x180010a70  cmp     r14d, 2
0x180010a74  mov     r15d, [rsp+22E0h+var_22A0]
0x180010a79  jz      loc_180010689
0x180010a7f  test    r14d, r14d
0x180010a82  jz      short loc_180010AA3
0x180010a84  xor     r12d, r12d
0x180010a87  cmp     [rbp+21E0h+arg_20], r12d
0x180010a8e  jnz     loc_18001068C
0x180010a94  mov     ecx, r14d; unsigned int
0x180010a97  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180010a9c  mov     ebx, eax
0x180010a9e  jmp     loc_180010B69
0x180010aa3  xor     r14d, r14d
0x180010aa6  cmp     [rbp+21E0h+arg_20], r14d
0x180010aad  jz      short loc_180010AED
0x180010aaf  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180010ab4  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180010ab9  test    eax, eax
0x180010abb  jz      short loc_180010AED
0x180010abd  lea     rdx, [rbp+21E0h+var_2260]; wchar_t *
0x180010ac1  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
  ... truncated ...
```
