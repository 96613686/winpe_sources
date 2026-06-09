# CXMLValue::ScWriteToBSTR(ushort * *)

- ea: `0x140019160`
- end: `0x14001946d`
- name: `?ScWriteToBSTR@CXMLValue@@QEBA?AVSC@mmcerror@@PEAPEAG@Z`
- size: `781`
- prototype: `OLECHAR *__fastcall(__int64, OLECHAR *, BSTR *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140018064`
- `0x140018350`
- `0x140018958`
- `0x14001a078`

## callees

- `0x140019160`
- `0x14001b6c0`
- `0x140026dcc`
- `0x1400369f8`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400191dd`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400192ec`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400193ca`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400191dd`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400192ec`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400193ca`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400191e7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400192a9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400193d4`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400191e7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400192a9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400193d4`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001919a`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400191c3`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001919a`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400191c3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001929f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140019391`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001929f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140019391`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400191f8`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400192d6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400191f8`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400192d6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400191d2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400193bf`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140019400`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400191d2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400193bf`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140019400`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400191ac`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400191ac`
- `ole32!CoTaskMemFree` at `0x140019430`
- `ole32!CoTaskMemFree` at `0x140019430`
- `ole32!StringFromCLSID` at `0x140019419`
- `ole32!StringFromCLSID` at `0x140019419`
- `OLEAUT32!__imp_SysFreeString` at `0x1400192e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400192e1`

## string_xrefs

- `0x1400191a1`: `CXMLValue::ScWriteToBSTR`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
OLECHAR *__fastcall CXMLValue::ScWriteToBSTR(__int64 a1, OLECHAR *a2, BSTR *a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  bool v13; // zf
  unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // r8
  unsigned int v16; // eax
  BSTR v17; // rax
  const struct mmcerror::SC *v18; // rdx
  __int64 v20; // r9
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v31[24]; // [rsp+28h] [rbp-61h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v33[40]; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 v34[40]; // [rsp+70h] [rbp-19h] BYREF

  lpsz = a2;
  mmcerror::SC::SC((mmcerror::SC *)v31, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v31, L"CXMLValue::ScWriteToBSTR");
  v6 = -2147024809;
  if ( a3 )
    v6 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v33, v6);
  mmcerror::SC::operator=(v31, v33);
  mmcerror::SC::~SC((mmcerror::SC *)v33);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v31) )
  {
    *a3 = 0;
    bstrString = 0;
    v7 = *(_DWORD *)a1;
    if ( *(int *)a1 > 7 )
    {
      v21 = v7 - 8;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 )
        {
          v14 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 8LL);
LABEL_23:
          ATL::CComBSTR::operator=(&bstrString, v14);
LABEL_24:
          v17 = bstrString;
          bstrString = 0;
          *a3 = v17;
          goto LABEL_25;
        }
        v23 = v22 - 1;
        if ( !v23 || (v24 = v23 - 1) == 0 )
        {
          v29 = *(_QWORD *)(a1 + 8);
          if ( *(_QWORD *)(v29 + 24) < 8u )
            v29 = a1 + 8;
          v14 = *(unsigned __int16 **)v29;
          goto LABEL_23;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          lpsz = 0;
          StringFromCLSID(*(const IID *const *)(a1 + 8), &lpsz);
          ATL::CComBSTR::operator=(&bstrString, lpsz);
          CoTaskMemFree(lpsz);
          goto LABEL_24;
        }
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
            goto LABEL_40;
          v27 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, BSTR *))(**(_QWORD **)(a1 + 8) + 8LL))(
                  *(_QWORD *)(a1 + 8),
                  v33,
                  &bstrString);
          mmcerror::SC::operator=(v31, v27);
        }
        else
        {
          v28 = ScEncodeBinary(v33, &bstrString, *(_QWORD *)(a1 + 8));
          mmcerror::SC::operator=(v31, v28);
        }
        mmcerror::SC::~SC((mmcerror::SC *)v33);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v31) )
          goto LABEL_25;
        goto LABEL_24;
      }
      v15 = L"%d";
      goto LABEL_20;
    }
    if ( v7 != 7 )
    {
      if ( !v7 )
      {
        v20 = **(unsigned int **)(a1 + 8);
        goto LABEL_29;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( !v9 )
        {
          v16 = StringCchPrintfW(v34, 0x28u, L"0x%02.2x", **(unsigned __int8 **)(a1 + 8), bstrString);
          goto LABEL_21;
        }
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( !v12 )
            {
              v13 = **(_DWORD **)(a1 + 8) == 0;
LABEL_15:
              v14 = L"true";
              if ( v13 )
                v14 = L"false";
              goto LABEL_23;
            }
            if ( v12 == 1 )
            {
              v13 = **(_BYTE **)(a1 + 8) == 0;
              goto LABEL_15;
            }
LABEL_40:
            v18 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v31, 2147500033LL);
            goto LABEL_26;
          }
          v15 = L"0x%04.4x";
          goto LABEL_20;
        }
        v20 = (unsigned int)**(__int16 **)(a1 + 8);
LABEL_29:
        v16 = StringCchPrintfW(v34, 0x28u, L"%d", v20, bstrString);
        goto LABEL_21;
      }
    }
    v15 = L"%u";
LABEL_20:
    v16 = StringCchPrintfW(v34, 0x28u, v15, **(unsigned int **)(a1 + 8), bstrString);
LABEL_21:
    mmcerror::SC::operator=(v31, v16);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v31) )
    {
LABEL_25:
      v18 = (const struct mmcerror::SC *)v31;
LABEL_26:
      mmcerror::SC::SC((mmcerror::SC *)a2, v18);
      SysFreeString(bstrString);
      goto LABEL_27;
    }
    v14 = v34;
    goto LABEL_23;
  }
  mmcerror::SC::SC((mmcerror::SC *)a2, (const struct mmcerror::SC *)v31);
LABEL_27:
  mmcerror::SC::~SC((mmcerror::SC *)v31);
  return a2;
}

```

## disassembly

```asm
0x140019160  mov     [rsp-8+arg_18], rbx
0x140019165  mov     [rsp-8+arg_8], rdx
0x14001916a  push    rbp
0x14001916b  push    rsi
0x14001916c  push    rdi
0x14001916d  lea     rbp, [rsp-47h]
0x140019172  sub     rsp, 0D0h
0x140019179  mov     rax, cs:__security_cookie
0x140019180  xor     rax, rsp
0x140019183  mov     [rbp+57h+var_20], rax
0x140019187  mov     rsi, r8
0x14001918a  mov     rbx, rdx
0x14001918d  mov     rdi, rcx
0x140019190  mov     [rbp+57h+lpsz], rdx
0x140019194  xor     edx, edx
0x140019196  lea     rcx, [rbp+57h+var_B8]
0x14001919a  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400191a0  nop
0x1400191a1  lea     rdx, aCxmlvalueScwri; "CXMLValue::ScWriteToBSTR"
0x1400191a8  lea     rcx, [rbp+57h+var_B8]
0x1400191ac  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400191b2  mov     edx, 80070057h
0x1400191b7  xor     eax, eax
0x1400191b9  test    rsi, rsi
0x1400191bc  cmovnz  edx, eax
0x1400191bf  lea     rcx, [rbp+57h+var_98]
0x1400191c3  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400191c9  nop
0x1400191ca  lea     rdx, [rbp+57h+var_98]
0x1400191ce  lea     rcx, [rbp+57h+var_B8]
0x1400191d2  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400191d8  nop
0x1400191d9  lea     rcx, [rbp+57h+var_98]
0x1400191dd  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400191e3  lea     rcx, [rbp+57h+var_B8]
0x1400191e7  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400191ed  test    al, al
0x1400191ef  jz      short loc_140019203
0x1400191f1  lea     rdx, [rbp+57h+var_B8]
0x1400191f5  mov     rcx, rbx
0x1400191f8  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400191fe  jmp     loc_1400192E8
0x140019203  mov     qword ptr [rsi], 0
0x14001920a  mov     [rbp+57h+bstrString], 0
0x140019212  mov     ecx, [rdi]
0x140019214  cmp     ecx, 7
0x140019217  jg      loc_140019351
0x14001921d  jz      loc_14001933C
0x140019223  test    ecx, ecx
0x140019225  jz      loc_140019348
0x14001922b  sub     ecx, 1
0x14001922e  jz      loc_14001933C
0x140019234  sub     ecx, 1
0x140019237  jz      loc_140019328
0x14001923d  sub     ecx, 1
0x140019240  jz      loc_140019314
0x140019246  sub     ecx, 1
0x140019249  jz      short loc_14001927D
0x14001924b  sub     ecx, 1
0x14001924e  jz      short loc_140019274
0x140019250  cmp     ecx, 1
0x140019253  jnz     loc_140019388
0x140019259  mov     rax, [rdi+8]
0x14001925d  cmp     byte ptr [rax], 0
0x140019260  lea     rdx, aTrue; "true"
0x140019267  lea     rcx, aFalse; "false"
0x14001926e  cmovz   rdx, rcx
0x140019272  jmp     short loc_1400192B7
0x140019274  mov     rax, [rdi+8]
0x140019278  cmp     dword ptr [rax], 0
0x14001927b  jmp     short loc_140019260
0x14001927d  lea     r8, a0x044x; "0x%04.4x"
0x140019284  mov     r9, [rdi+8]
0x140019288  mov     r9d, [r9]
0x14001928b  mov     edx, 28h ; '('; unsigned __int64
0x140019290  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x140019294  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140019299  mov     edx, eax
0x14001929b  lea     rcx, [rbp+57h+var_B8]
0x14001929f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400192a5  lea     rcx, [rbp+57h+var_B8]
0x1400192a9  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400192af  test    al, al
0x1400192b1  jnz     short loc_1400192CF
0x1400192b3  lea     rdx, [rbp+57h+var_70]
0x1400192b7  lea     rcx, [rbp+57h+bstrString]
0x1400192bb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400192c0  mov     rax, [rbp+57h+bstrString]
0x1400192c4  mov     [rbp+57h+bstrString], 0
0x1400192cc  mov     [rsi], rax
0x1400192cf  lea     rdx, [rbp+57h+var_B8]
0x1400192d3  mov     rcx, rbx
0x1400192d6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400192dc  nop
0x1400192dd  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400192e1  call    cs:__imp_SysFreeString
0x1400192e7  nop
0x1400192e8  lea     rcx, [rbp+57h+var_B8]
0x1400192ec  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400192f2  mov     rax, rbx
0x1400192f5  mov     rcx, [rbp+57h+var_20]
0x1400192f9  xor     rcx, rsp; StackCookie
0x1400192fc  call    __security_check_cookie
0x140019301  mov     rbx, [rsp+0E0h+arg_18]
0x140019309  add     rsp, 0D0h
0x140019310  pop     rdi
0x140019311  pop     rsi
0x140019312  pop     rbp
0x140019313  retn
0x140019314  mov     rax, [rdi+8]
0x140019318  movsx   r9d, word ptr [rax]
0x14001931c  lea     r8, aD_1; "%d"
0x140019323  jmp     loc_14001928B
0x140019328  mov     rax, [rdi+8]
0x14001932c  movzx   r9d, byte ptr [rax]
0x140019330  lea     r8, a0x022x; "0x%02.2x"
0x140019337  jmp     loc_14001928B
0x14001933c  lea     r8, aU; "%u"
0x140019343  jmp     loc_140019284
0x140019348  mov     r9, [rdi+8]
0x14001934c  mov     r9d, [r9]
0x14001934f  jmp     short loc_14001931C
0x140019351  sub     ecx, 8
0x140019354  jz      loc_140019460
0x14001935a  sub     ecx, 1
0x14001935d  jz      loc_140019453
0x140019363  sub     ecx, 1
0x140019366  jz      loc_14001943B
0x14001936c  sub     ecx, 1
0x14001936f  jz      loc_14001943B
0x140019375  sub     ecx, 1
0x140019378  jz      loc_140019409
0x14001937e  sub     ecx, 1
0x140019381  jz      short loc_1400193E7
0x140019383  cmp     ecx, 1
0x140019386  jz      short loc_14001939F
0x140019388  mov     edx, 80004001h
0x14001938d  lea     rcx, [rbp+57h+var_B8]
0x140019391  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140019397  mov     rdx, rax
0x14001939a  jmp     loc_1400192D3
0x14001939f  mov     rcx, [rdi+8]
0x1400193a3  mov     rax, [rcx]
0x1400193a6  lea     r8, [rbp+57h+bstrString]
0x1400193aa  lea     rdx, [rbp+57h+var_98]
0x1400193ae  mov     rax, [rax+8]
0x1400193b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400193b7  nop
0x1400193b8  mov     rdx, rax
0x1400193bb  lea     rcx, [rbp+57h+var_B8]
0x1400193bf  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400193c5  nop
0x1400193c6  lea     rcx, [rbp+57h+var_98]
0x1400193ca  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400193d0  lea     rcx, [rbp+57h+var_B8]
0x1400193d4  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400193da  test    al, al
0x1400193dc  jnz     loc_1400192CF
0x1400193e2  jmp     loc_1400192C0
0x1400193e7  mov     r8, [rdi+8]
0x1400193eb  lea     rdx, [rbp+57h+bstrString]
0x1400193ef  lea     rcx, [rbp+57h+var_98]
0x1400193f3  call    ScEncodeBinary
0x1400193f8  nop
0x1400193f9  mov     rdx, rax
0x1400193fc  lea     rcx, [rbp+57h+var_B8]
0x140019400  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140019406  nop
0x140019407  jmp     short loc_1400193C6
0x140019409  mov     [rbp+57h+lpsz], 0
0x140019411  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x140019415  mov     rcx, [rdi+8]; rclsid
0x140019419  call    cs:__imp_StringFromCLSID
0x14001941f  mov     rdx, [rbp+57h+lpsz]
0x140019423  lea     rcx, [rbp+57h+bstrString]
0x140019427  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x14001942c  mov     rcx, [rbp+57h+lpsz]; pv
0x140019430  call    cs:__imp_CoTaskMemFree
0x140019436  jmp     loc_1400192C0
0x14001943b  lea     rax, [rdi+8]
0x14001943f  mov     rdx, [rax]
0x140019442  cmp     qword ptr [rdx+18h], 8
0x140019447  cmovb   rdx, rax
0x14001944b  mov     rdx, [rdx]
0x14001944e  jmp     loc_1400192B7
0x140019453  mov     rdx, [rdi+8]
0x140019457  mov     rdx, [rdx+8]
0x14001945b  jmp     loc_1400192B7
0x140019460  lea     r8, aD_1; "%d"
0x140019467  jmp     loc_140019284
```
