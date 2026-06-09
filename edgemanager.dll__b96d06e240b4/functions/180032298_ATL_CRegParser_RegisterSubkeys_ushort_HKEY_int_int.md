# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180032298`
- end: `0x180032871`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180031ecc`
- `0x180032298`

## callees

- `0x18002b530`
- `0x18002edbc`
- `0x18002f5e0`
- `0x18002f650`
- `0x1800300a0`
- `0x1800301b4`
- `0x1800305a0`
- `0x1800313e0`
- `0x180031720`
- `0x180031880`
- `0x180031db8`
- `0x180032298`
- `0x18003309c`
- `0x18003316c`
- `0x180081700`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003269e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003269e`
- `api-ms-win-core-localregistry-l1-1-0!RegCreateKeyExW` at `0x18003259f`
- `api-ms-win-core-localregistry-l1-1-0!RegCreateKeyExW` at `0x18003259f`
- `api-ms-win-core-localregistry-l1-1-0!RegDeleteValueW` at `0x1800324ed`
- `api-ms-win-core-localregistry-l1-1-0!RegDeleteValueW` at `0x1800324ed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032313`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032326`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800323fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032429`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032313`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032326`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800323fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180032429`

## string_xrefs

- `0x18003231c`: `ForceRemove`
- `0x1800323f0`: `NoRemove`
- `0x180032309`: `Delete`

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
  int v20; // eax
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
  unsigned __int16 v33[264]; // [rsp+A0h] [rbp-60h] BYREF
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
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
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
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
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
0x180032298  push    rbp
0x18003229a  push    rbx
0x18003229b  push    rsi
0x18003229c  push    rdi
0x18003229d  push    r12
0x18003229f  push    r13
0x1800322a1  push    r14
0x1800322a3  push    r15
0x1800322a5  lea     rbp, [rsp-21C8h]
0x1800322ad  mov     eax, 22C8h
0x1800322b2  call    _alloca_probe
0x1800322b7  sub     rsp, rax
0x1800322ba  mov     rax, cs:__security_cookie
0x1800322c1  xor     rax, rsp
0x1800322c4  mov     [rbp+2200h+var_50], rax
0x1800322cb  mov     r15d, r9d
0x1800322ce  mov     [rsp+2300h+var_22B0], r9d
0x1800322d3  mov     r13, r8
0x1800322d6  mov     rdi, rdx
0x1800322d9  mov     rsi, rcx
0x1800322dc  xor     r14d, r14d
0x1800322df  mov     [rsp+2300h+var_2290], r14
0x1800322e4  mov     [rsp+2300h+var_2288], r14
0x1800322e9  mov     [rbp+2200h+var_2280], r14
0x1800322ed  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800322f2  test    eax, eax
0x1800322f4  mov     ebx, eax
0x1800322f6  js      loc_180032825
0x1800322fc  xor     r12d, r12d
0x1800322ff  cmp     word ptr [rdi], 7Dh ; '}'
0x180032303  jz      loc_180032825
0x180032309  lea     rdx, aDelete; "Delete"
0x180032310  mov     rcx, rdi; lpString1
0x180032313  call    cs:__imp_lstrcmpiW
0x180032319  mov     r14d, eax
0x18003231c  lea     rdx, aForceremove; "ForceRemove"
0x180032323  mov     rcx, rdi; lpString1
0x180032326  call    cs:__imp_lstrcmpiW
0x18003232c  test    eax, eax
0x18003232e  jz      short loc_180032339
0x180032330  test    r14d, r14d
0x180032333  jnz     loc_1800323EA
0x180032339  mov     rdx, rdi; unsigned __int16 *
0x18003233c  mov     rcx, rsi; this
0x18003233f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180032344  mov     ebx, eax
0x180032346  test    eax, eax
0x180032348  js      loc_180032825
0x18003234e  test    r15d, r15d
0x180032351  jz      loc_1800323EA
0x180032357  mov     [rsp+2300h+hKey], r12
0x18003235c  mov     [rsp+2300h+var_22A0], r12
0x180032361  mov     [rsp+2300h+var_2298], r12
0x180032366  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003236b  mov     rcx, rdi; lpsz
0x18003236e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180032373  test    rax, rax
0x180032376  jnz     loc_180032816
0x18003237c  mov     rdx, rdi; unsigned __int16 *
0x18003237f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180032384  test    eax, eax
0x180032386  jz      short loc_18003239F
0x180032388  mov     [rsp+2300h+hKey], r13
0x18003238d  mov     rdx, rdi; unsigned __int16 *
0x180032390  lea     rcx, [rsp+2300h+hKey]; this
0x180032395  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18003239a  mov     [rsp+2300h+hKey], r12
0x18003239f  test    r14d, r14d
0x1800323a2  jnz     short loc_1800323E0
0x1800323a4  mov     rdx, rdi; unsigned __int16 *
0x1800323a7  mov     rcx, rsi; this
0x1800323aa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800323af  mov     ebx, eax
0x1800323b1  xor     r14d, r14d
0x1800323b4  test    eax, eax
0x1800323b6  js      loc_18003285D
0x1800323bc  mov     rdx, rdi; unsigned __int16 *
0x1800323bf  mov     rcx, rsi; this
0x1800323c2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800323c7  mov     ebx, eax
0x1800323c9  test    eax, eax
0x1800323cb  lea     rcx, [rsp+2300h+hKey]; this
0x1800323d0  js      loc_180032862
0x1800323d6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800323db  jmp     loc_180032604
0x1800323e0  lea     rcx, [rsp+2300h+hKey]; this
0x1800323e5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800323ea  mov     r12d, 1
0x1800323f0  lea     rdx, aNoremove; "NoRemove"
0x1800323f7  mov     rcx, rdi; lpString1
0x1800323fa  call    cs:__imp_lstrcmpiW
0x180032400  xor     r14d, r14d
0x180032403  test    eax, eax
0x180032405  jnz     short loc_18003241F
0x180032407  mov     r12d, r14d
0x18003240a  mov     rdx, rdi; unsigned __int16 *
0x18003240d  mov     rcx, rsi; this
0x180032410  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180032415  mov     ebx, eax
0x180032417  test    eax, eax
0x180032419  js      loc_180032825
0x18003241f  lea     rdx, aVal; "Val"
0x180032426  mov     rcx, rdi; lpString1
0x180032429  call    cs:__imp_lstrcmpiW
0x18003242f  test    eax, eax
0x180032431  jnz     loc_180032518
0x180032437  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18003243e  mov     rcx, rsi; this
0x180032441  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180032446  mov     ebx, eax
0x180032448  test    eax, eax
0x18003244a  js      loc_180032825
0x180032450  mov     rdx, rdi; unsigned __int16 *
0x180032453  mov     rcx, rsi; this
0x180032456  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003245b  mov     ebx, eax
0x18003245d  test    eax, eax
0x18003245f  js      loc_180032825
0x180032465  cmp     word ptr [rdi], 3Dh ; '='
0x180032469  jnz     loc_180032820
0x18003246f  test    r15d, r15d
0x180032472  jz      short loc_1800324A6
0x180032474  mov     [rsp+2300h+var_22A0], r14
0x180032479  mov     [rsp+2300h+var_2298], r14
0x18003247e  mov     [rsp+2300h+hKey], r13
0x180032483  mov     r9, rdi; unsigned __int16 *
0x180032486  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18003248d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180032492  mov     rcx, rsi; this
0x180032495  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003249a  mov     ebx, eax
0x18003249c  mov     [rsp+2300h+hKey], r14
0x1800324a1  jmp     loc_1800323C9
0x1800324a6  cmp     [rbp+2200h+arg_20], r14d
0x1800324ad  jnz     short loc_180032508
0x1800324af  test    r12d, r12d
0x1800324b2  jz      short loc_180032508
0x1800324b4  mov     [rsp+2300h+hKey], r14
0x1800324b9  mov     [rsp+2300h+var_22A0], r14
0x1800324be  mov     [rsp+2300h+var_2298], r14
0x1800324c3  mov     r9d, 20006h; unsigned int
0x1800324c9  xor     r8d, r8d; lpSubKey
0x1800324cc  mov     rdx, r13; hKey
0x1800324cf  lea     rcx, [rsp+2300h+hKey]; this
0x1800324d4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800324d9  test    eax, eax
0x1800324db  jnz     loc_180032854
0x1800324e1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800324e8  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800324ed  call    cs:__imp_RegDeleteValueW
0x1800324f3  test    eax, 0FFFFFFFDh
0x1800324f8  jnz     loc_180032854
0x1800324fe  lea     rcx, [rsp+2300h+hKey]; this
0x180032503  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180032508  mov     rdx, rdi; unsigned __int16 *
0x18003250b  mov     rcx, rsi; this
0x18003250e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180032513  jmp     loc_1800322F2
0x180032518  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003251d  mov     rcx, rdi; lpsz
0x180032520  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180032525  test    rax, rax
0x180032528  jnz     loc_180032820
0x18003252e  test    r15d, r15d
0x180032531  jz      loc_180032653
0x180032537  mov     ebx, 2001Fh
0x18003253c  mov     r9d, ebx; unsigned int
0x18003253f  mov     r8, rdi; lpSubKey
0x180032542  mov     rdx, r13; hKey
0x180032545  lea     rcx, [rsp+2300h+var_2290]; this
0x18003254a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003254f  test    eax, eax
0x180032551  jz      short loc_1800325CC
0x180032553  lea     r9d, [rbx-6]; unsigned int
0x180032557  mov     r8, rdi; lpSubKey
0x18003255a  mov     rdx, r13; hKey
0x18003255d  lea     rcx, [rsp+2300h+var_2290]; this
0x180032562  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180032567  test    eax, eax
0x180032569  jz      short loc_1800325CC
0x18003256b  mov     [rbp+2200h+dwDisposition], r14d
0x18003256f  mov     [rbp+2200h+var_2270], r14
0x180032573  lea     rax, [rbp+2200h+dwDisposition]
0x180032577  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18003257c  lea     rax, [rbp+2200h+var_2270]
0x180032580  mov     [rsp+2300h+phkResult], rax; phkResult
0x180032585  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003258a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18003258e  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180032593  xor     r9d, r9d; lpClass
0x180032596  xor     r8d, r8d; Reserved
0x180032599  mov     rdx, rdi; lpSubKey
0x18003259c  mov     rcx, r13; hKey
0x18003259f  call    cs:__imp_RegCreateKeyExW
0x1800325a5  mov     ecx, eax
0x1800325a7  test    eax, eax
0x1800325a9  jnz     loc_180032753
0x1800325af  lea     rcx, [rsp+2300h+var_2290]; this
0x1800325b4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800325b9  mov     ecx, eax
0x1800325bb  mov     rax, [rbp+2200h+var_2270]
0x1800325bf  mov     [rsp+2300h+var_2290], rax
0x1800325c4  test    ecx, ecx
0x1800325c6  jnz     loc_180032753
0x1800325cc  mov     rdx, rdi; unsigned __int16 *
0x1800325cf  mov     rcx, rsi; this
0x1800325d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800325d7  mov     ebx, eax
0x1800325d9  test    eax, eax
0x1800325db  js      loc_180032825
0x1800325e1  cmp     word ptr [rdi], 3Dh ; '='
0x1800325e5  jnz     short loc_180032604
0x1800325e7  mov     r9, rdi; unsigned __int16 *
0x1800325ea  xor     r8d, r8d; unsigned __int16 *
0x1800325ed  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800325f2  mov     rcx, rsi; this
0x1800325f5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800325fa  mov     ebx, eax
0x1800325fc  test    eax, eax
0x1800325fe  js      loc_180032825
0x180032604  cmp     word ptr [rdi], 7Bh ; '{'
0x180032608  jnz     loc_1800322FC
0x18003260e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032612  inc     rax
0x180032615  cmp     [rdi+rax*2], r14w
0x18003261a  jnz     short loc_180032612
0x18003261c  cmp     rax, 1
0x180032620  jnz     loc_1800322FC
0x180032626  mov     [rsp+2300h+dwOptions], r14d; int
0x18003262b  mov     r9d, r15d; int
0x18003262e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180032633  mov     rdx, rdi; unsigned __int16 *
0x180032636  mov     rcx, rsi; this
0x180032639  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003263e  mov     ebx, eax
0x180032640  test    eax, eax
0x180032642  js      loc_180032825
0x180032648  mov     rdx, rdi
0x18003264b  mov     rcx, rsi
0x18003264e  jmp     loc_1800322ED
0x180032653  cmp     [rbp+2200h+arg_20], r14d
0x18003265a  jnz     short loc_180032677
0x18003265c  mov     r9d, 20019h; unsigned int
0x180032662  mov     r8, rdi; lpSubKey
0x180032665  mov     rdx, r13; hKey
0x180032668  lea     rcx, [rsp+2300h+var_2290]; this
0x18003266d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180032672  mov     r14d, eax
0x180032675  jmp     short loc_18003267D
0x180032677  mov     r14d, 2
0x18003267d  mov     r15d, 1
0x180032683  test    r14d, r14d
0x180032686  cmovz   r15d, [rbp+2200h+arg_20]
0x18003268e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180032692  mov     r8, rdi
0x180032695  mov     edx, 104h
0x18003269a  lea     rcx, [rbp+2200h+var_2260]
0x18003269e  call    cs:__imp__o_wcsncpy_s
0x1800326a4  mov     ecx, eax; int
0x1800326a6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800326ab  mov     rdx, rdi; unsigned __int16 *
0x1800326ae  mov     rcx, rsi; this
0x1800326b1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800326b6  mov     ebx, eax
0x1800326b8  test    eax, eax
0x1800326ba  js      loc_180032825
0x1800326c0  mov     rdx, rdi; unsigned __int16 *
0x1800326c3  mov     rcx, rsi; this
0x1800326c6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800326cb  mov     ebx, eax
0x1800326cd  xor     ecx, ecx
0x1800326cf  test    eax, eax
0x1800326d1  js      loc_180032825
0x1800326d7  cmp     word ptr [rdi], 7Bh ; '{'
0x1800326db  jnz     short loc_18003272C
0x1800326dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800326e1  inc     rax
0x1800326e4  cmp     [rdi+rax*2], cx
0x1800326e8  jnz     short loc_1800326E1
0x1800326ea  cmp     rax, 1
0x1800326ee  jnz     short loc_18003272C
0x1800326f0  mov     [rsp+2300h+dwOptions], r15d; int
0x1800326f5  xor     r9d, r9d; int
0x1800326f8  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800326fd  mov     rdx, rdi; unsigned __int16 *
0x180032700  mov     rcx, rsi; this
0x180032703  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180032708  mov     ebx, eax
0x18003270a  test    eax, eax
0x18003270c  jns     short loc_180032717
0x18003270e  test    r15d, r15d
0x180032711  jz      loc_180032825
0x180032717  mov     rdx, rdi; unsigned __int16 *
0x18003271a  mov     rcx, rsi; this
0x18003271d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180032722  mov     ebx, eax
0x180032724  test    eax, eax
0x180032726  js      loc_180032825
0x18003272c  cmp     r14d, 2
0x180032730  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
