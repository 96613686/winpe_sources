# NPrintTicketUtil::CreatePrintTicketFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot * *)

- ea: `0x1800042c0`
- end: `0x180004a74`
- name: `?CreatePrintTicketFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAPEAUTFeatureListRoot@1@@Z`
- size: `1972`
- prototype: `__int64 __fastcall(NPrintTicketUtil *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct NPrintTicketUtil::TFeatureListRoot **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c80`
- `0x180003708`
- `0x180008498`

## callees

- `0x1800042c0`
- `0x180004a7c`
- `0x180004aa8`
- `0x180004abc`
- `0x18000fd6c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004450`
- `OLEAUT32!__imp_SysFreeString` at `0x180004466`
- `OLEAUT32!__imp_SysFreeString` at `0x1800044fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180004511`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046da`
- `OLEAUT32!__imp_SysFreeString` at `0x180004747`
- `OLEAUT32!__imp_SysFreeString` at `0x18000475a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004836`
- `OLEAUT32!__imp_SysFreeString` at `0x18000484c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800049fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a11`
- `OLEAUT32!__imp_SysFreeString` at `0x180004450`
- `OLEAUT32!__imp_SysFreeString` at `0x180004466`
- `OLEAUT32!__imp_SysFreeString` at `0x1800044fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180004511`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046da`
- `OLEAUT32!__imp_SysFreeString` at `0x180004747`
- `OLEAUT32!__imp_SysFreeString` at `0x18000475a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004836`
- `OLEAUT32!__imp_SysFreeString` at `0x18000484c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800049fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a11`

## string_xrefs

- `0x180004418`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180004688`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180004805`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CreatePrintTicketFeatureList(
        NPrintTicketUtil *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct NPrintTicketUtil::TFeatureListRoot **a3)
{
  NPrintTicketUtil::TFeatureListRoot *v5; // rax
  NPrintTicketUtil::TFeatureListRoot *v6; // r14
  __int64 v7; // rcx
  unsigned int v8; // edx
  int v9; // edi
  __int64 v10; // rcx
  int v11; // ebx
  OLECHAR *v12; // r9
  OLECHAR *v13; // r10
  BSTR v14; // rax
  int v15; // ecx
  int v16; // edx
  BSTR v17; // rax
  int v18; // ecx
  int v19; // edx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, __int64 *); // rax
  __int64 v22; // rcx
  int v23; // ebx
  OLECHAR *v24; // r9
  OLECHAR *v25; // r10
  BSTR v26; // rax
  int v27; // ecx
  int v28; // edx
  int v29; // ebx
  __int64 v30; // rcx
  __int64 v31; // rcx
  OLECHAR *v33; // r9
  OLECHAR *v34; // r10
  BSTR v35; // rax
  int v36; // ecx
  int v37; // edx
  BSTR v38; // rax
  int v39; // ecx
  int v40; // edx
  BSTR v41; // rax
  int v42; // ecx
  int v43; // edx
  struct IXMLDOMElement *v44; // [rsp+20h] [rbp-40h] BYREF
  __int64 v45; // [rsp+28h] [rbp-38h] BYREF
  __int64 v46; // [rsp+30h] [rbp-30h] BYREF
  __int128 v47; // [rsp+38h] [rbp-28h]
  BSTR bstrString; // [rsp+98h] [rbp+38h] BYREF
  __int64 v49; // [rsp+A0h] [rbp+40h] BYREF
  BSTR v50; // [rsp+A8h] [rbp+48h] BYREF

  v5 = (NPrintTicketUtil::TFeatureListRoot *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    *(_QWORD *)a2 = 0;
    return 2147942414LL;
  }
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  *(_QWORD *)a2 = 0;
  v7 = *((_QWORD *)this + 3);
  v46 = 0;
  v47 = 0;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 96LL))(v7, &v45);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 80LL))(v45);
    if ( v9 >= 0 )
    {
      v10 = 0;
      v49 = 0;
      v11 = 0;
      while ( 1 )
      {
        if ( v9 < 0 )
        {
LABEL_37:
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          if ( v9 >= 0 )
            v9 = v11 != 0;
          goto LABEL_41;
        }
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL))(v45, &v49);
        if ( v9 )
          goto LABEL_36;
        v44 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v49)(v49, &IID_IXMLDOMElement, &v44) >= 0 )
          break;
LABEL_20:
        v10 = v49;
        if ( v49 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          v10 = 0;
          v49 = 0;
        }
        v8 = (unsigned int)v44;
        if ( v44 )
        {
          ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
          v10 = v49;
        }
      }
      v50 = 0;
      bstrString = 0;
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_namespaceURI)(v44, &v50);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_baseName)(v44, &bstrString);
        if ( v9 >= 0 )
        {
          v12 = v50;
          v13 = bstrString;
          if ( !v50 )
            goto LABEL_16;
          if ( !bstrString )
          {
LABEL_18:
            if ( v12 )
              SysFreeString(v12);
            goto LABEL_20;
          }
          v14 = v50;
          do
          {
            v15 = *(BSTR)((char *)v14
                        + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                        - (char *)v50);
            v16 = *v14 - v15;
            if ( v16 )
              break;
            ++v14;
          }
          while ( v15 );
          if ( v16 )
            goto LABEL_16;
          v17 = bstrString;
          do
          {
            v18 = *(BSTR)((char *)v17 + (char *)L"Feature" - (char *)bstrString);
            v19 = *v17 - v18;
            if ( v19 )
              break;
            ++v17;
          }
          while ( v18 );
          if ( v19 )
          {
LABEL_16:
            if ( v13 )
            {
              SysFreeString(v13);
              v12 = v50;
              bstrString = 0;
            }
            goto LABEL_18;
          }
          v9 = AddToFeatureToListOnVisit(this, v44, (struct TConstructionData *)&v46);
          if ( v9 == 1 )
          {
            v11 = 1;
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v50 )
            {
              SysFreeString(v50);
              v50 = 0;
            }
            if ( v44 )
              ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
LABEL_36:
            v10 = v49;
            goto LABEL_37;
          }
        }
      }
      v12 = v50;
      v13 = bstrString;
      goto LABEL_16;
    }
  }
LABEL_41:
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v9 < 0 )
  {
LABEL_83:
    NPrintTicketUtil::TFeatureListRoot::`scalar deleting destructor'(v6, v8);
    return (unsigned int)v9;
  }
  *(_QWORD *)v6 = *((_QWORD *)&v47 + 1);
  v20 = *((_QWORD *)this + 3);
  v46 = 0x100000000LL;
  v47 = 0;
  v45 = 0;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 96LL);
  if ( *((_DWORD *)this + 9) )
  {
    v9 = v21(v20, &v45);
    if ( v9 < 0 )
      goto LABEL_79;
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 80LL))(v45);
    if ( v9 < 0 )
      goto LABEL_79;
    v30 = 0;
    v49 = 0;
    v29 = 0;
    while ( 1 )
    {
      if ( v9 < 0 )
        goto LABEL_75;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL))(v45, &v49);
      if ( v9 )
        goto LABEL_74;
      v44 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v49)(v49, &IID_IXMLDOMElement, &v44) >= 0 )
        break;
LABEL_96:
      v30 = v49;
      if ( v49 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v30 = 0;
        v49 = 0;
      }
      v8 = (unsigned int)v44;
      if ( v44 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
        v30 = v49;
      }
    }
    v50 = 0;
    bstrString = 0;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_namespaceURI)(v44, &v50);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_baseName)(v44, &bstrString);
      if ( v9 >= 0 )
      {
        v33 = v50;
        v34 = bstrString;
        if ( !v50 )
          goto LABEL_92;
        if ( !bstrString )
        {
LABEL_94:
          if ( v33 )
            SysFreeString(v33);
          goto LABEL_96;
        }
        v35 = v50;
        do
        {
          v36 = *(BSTR)((char *)v35
                      + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                      - (char *)v50);
          v37 = *v35 - v36;
          if ( v37 )
            break;
          ++v35;
        }
        while ( v36 );
        if ( v37 )
          goto LABEL_92;
        v38 = bstrString;
        do
        {
          v39 = *(BSTR)((char *)v38 + (char *)L"ParameterDef" - (char *)bstrString);
          v40 = *v38 - v39;
          if ( v40 )
            break;
          ++v38;
        }
        while ( v39 );
        if ( v40 )
        {
LABEL_92:
          if ( v34 )
          {
            SysFreeString(v34);
            v33 = v50;
            bstrString = 0;
          }
          goto LABEL_94;
        }
        v9 = AddParameterToListOnVisit(this, v44, (struct TConstructionData *)&v46);
        if ( v9 == 1 )
        {
          v29 = 1;
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v50 )
          {
            SysFreeString(v50);
            v50 = 0;
          }
          if ( v44 )
            ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
LABEL_74:
          v30 = v49;
LABEL_75:
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v9 >= 0 )
            v9 = v29 != 0;
LABEL_79:
          v31 = v45;
LABEL_80:
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          goto LABEL_82;
        }
      }
    }
    v33 = v50;
    v34 = bstrString;
    goto LABEL_92;
  }
  v9 = v21(v20, &v45);
  if ( v9 < 0 )
    goto LABEL_132;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 80LL))(v45);
  if ( v9 < 0 )
    goto LABEL_132;
  v22 = 0;
  v49 = 0;
  v23 = 0;
  while ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 72LL))(v45, &v49);
    if ( v9 )
      goto LABEL_127;
    v44 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v49)(v49, &IID_IXMLDOMElement, &v44) >= 0 )
    {
      v50 = 0;
      bstrString = 0;
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_namespaceURI)(v44, &v50);
      if ( v9 < 0 )
        goto LABEL_115;
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v44->lpVtbl->get_baseName)(v44, &bstrString);
      if ( v9 < 0 )
        goto LABEL_115;
      v24 = v50;
      v25 = bstrString;
      if ( !v50 )
        goto LABEL_59;
      if ( bstrString )
      {
        v26 = v50;
        do
        {
          v27 = *(BSTR)((char *)v26
                      + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                      - (char *)v50);
          v28 = *v26 - v27;
          if ( v28 )
            break;
          ++v26;
        }
        while ( v27 );
        if ( !v28 )
        {
          v41 = bstrString;
          do
          {
            v42 = *(BSTR)((char *)v41 + (char *)L"ParameterInit" - (char *)bstrString);
            v43 = *v41 - v42;
            if ( v43 )
              break;
            ++v41;
          }
          while ( v42 );
          if ( !v43 )
          {
            v9 = AddParameterToListOnVisit(this, v44, (struct TConstructionData *)&v46);
            if ( v9 == 1 )
            {
              v23 = 1;
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              if ( v50 )
              {
                SysFreeString(v50);
                v50 = 0;
              }
              if ( v44 )
                ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
LABEL_127:
              v22 = v49;
              break;
            }
LABEL_115:
            v24 = v50;
            v25 = bstrString;
          }
        }
LABEL_59:
        if ( v25 )
        {
          SysFreeString(v25);
          v24 = v50;
          bstrString = 0;
        }
      }
      if ( v24 )
        SysFreeString(v24);
    }
    v22 = v49;
    if ( v49 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      v22 = 0;
      v49 = 0;
    }
    v8 = (unsigned int)v44;
    if ( v44 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
      v22 = v49;
    }
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v9 >= 0 )
    v9 = v23 != 0;
LABEL_132:
  v31 = v45;
  if ( v45 )
    goto LABEL_80;
LABEL_82:
  if ( v9 < 0 )
    goto LABEL_83;
  *((_QWORD *)v6 + 1) = *((_QWORD *)&v47 + 1);
  *(_QWORD *)a2 = v6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800042c0  push    rbp
0x1800042c2  push    rsi
0x1800042c3  push    r12
0x1800042c5  push    r14
0x1800042c7  push    r15
0x1800042c9  mov     rbp, rsp
0x1800042cc  sub     rsp, 60h
0x1800042d0  mov     r12, rdx
0x1800042d3  mov     r15, rcx
0x1800042d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800042dd  mov     ecx, 10h; unsigned __int64
0x1800042e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800042e7  xor     esi, esi
0x1800042e9  mov     r14, rax
0x1800042ec  test    rax, rax
0x1800042ef  jz      loc_1800047E0
0x1800042f5  mov     [rax], rsi
0x1800042f8  lea     rdx, [rbp+var_38]
0x1800042fc  mov     [rax+8], rsi
0x180004300  xorps   xmm0, xmm0
0x180004303  mov     [r12], rsi
0x180004307  mov     rcx, [r15+18h]
0x18000430b  mov     [rbp+var_30], rsi
0x18000430f  movdqu  [rbp+var_28], xmm0
0x180004314  mov     [rbp+var_38], rsi
0x180004318  mov     rax, [rcx]
0x18000431b  mov     [rsp+60h+var_8], rdi
0x180004320  mov     [rsp+60h+arg_0], rbx
0x180004328  mov     [rsp+60h+var_10], r13
0x18000432d  mov     rax, [rax+60h]
0x180004331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004336  mov     edi, eax
0x180004338  test    eax, eax
0x18000433a  js      loc_180004551
0x180004340  mov     rcx, [rbp+var_38]
0x180004344  mov     rax, [rcx]
0x180004347  mov     rax, [rax+50h]
0x18000434b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004350  mov     edi, eax
0x180004352  test    eax, eax
0x180004354  js      loc_180004551
0x18000435a  mov     ecx, esi
0x18000435c  lea     r13, aFeature; "Feature"
0x180004363  mov     [rbp+arg_10], rcx
0x180004367  mov     ebx, esi
0x180004369  nop     dword ptr [rax+00000000h]
0x180004370  test    edi, edi
0x180004372  js      loc_180004534
0x180004378  mov     rcx, [rbp+var_38]
0x18000437c  lea     rdx, [rbp+arg_10]
0x180004380  mov     rax, [rcx]
0x180004383  mov     rax, [rax+48h]
0x180004387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438c  mov     edi, eax
0x18000438e  test    eax, eax
0x180004390  jnz     loc_180004530
0x180004396  mov     rcx, [rbp+arg_10]
0x18000439a  lea     r8, [rbp+var_40]
0x18000439e  mov     [rbp+var_40], rsi
0x1800043a2  lea     rdx, IID_IXMLDOMElement
0x1800043a9  mov     rax, [rcx]
0x1800043ac  mov     rax, [rax]
0x1800043af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043b4  test    eax, eax
0x1800043b6  js      loc_18000446C
0x1800043bc  mov     rcx, [rbp+var_40]
0x1800043c0  lea     rdx, [rbp+arg_18]
0x1800043c4  mov     [rbp+arg_18], rsi
0x1800043c8  mov     [rbp+bstrString], rsi
0x1800043cc  mov     rax, [rcx]
0x1800043cf  mov     rax, [rax+138h]
0x1800043d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043db  mov     edi, eax
0x1800043dd  test    eax, eax
0x1800043df  js      loc_1800044AD
0x1800043e5  mov     rcx, [rbp+var_40]
0x1800043e9  lea     rdx, [rbp+bstrString]
0x1800043ed  mov     rax, [rcx]
0x1800043f0  mov     rax, [rax+148h]
0x1800043f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fc  mov     edi, eax
0x1800043fe  test    eax, eax
0x180004400  js      loc_1800044AD
0x180004406  mov     r9, [rbp+arg_18]
0x18000440a  mov     r10, [rbp+bstrString]
0x18000440e  test    r9, r9
0x180004411  jz      short loc_180004448
0x180004413  test    r10, r10
0x180004416  jz      short loc_18000445E
0x180004418  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18000441f  mov     rax, r9
0x180004422  sub     r8, r9
0x180004425  nop     word ptr [rax+rax+00000000h]
0x180004430  movzx   edx, word ptr [rax]
0x180004433  movzx   ecx, word ptr [rax+r8]
0x180004438  sub     edx, ecx
0x18000443a  jnz     short loc_180004444
0x18000443c  add     rax, 2
0x180004440  test    ecx, ecx
0x180004442  jnz     short loc_180004430
0x180004444  test    edx, edx
0x180004446  jz      short loc_1800044B7
0x180004448  test    r10, r10
0x18000444b  jz      short loc_18000445E
0x18000444d  mov     rcx, r10; bstrString
0x180004450  call    cs:__imp_SysFreeString
0x180004456  mov     r9, [rbp+arg_18]
0x18000445a  mov     [rbp+bstrString], rsi
0x18000445e  test    r9, r9
0x180004461  jz      short loc_18000446C
0x180004463  mov     rcx, r9; bstrString
0x180004466  call    cs:__imp_SysFreeString
0x18000446c  mov     rcx, [rbp+arg_10]
0x180004470  test    rcx, rcx
0x180004473  jz      short loc_180004488
0x180004475  mov     rax, [rcx]
0x180004478  mov     rax, [rax+10h]
0x18000447c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004481  mov     rcx, rsi
0x180004484  mov     [rbp+arg_10], rcx
0x180004488  mov     rdx, [rbp+var_40]
0x18000448c  test    rdx, rdx
0x18000448f  jz      loc_180004370
0x180004495  mov     rax, [rdx]
0x180004498  mov     rcx, rdx
0x18000449b  mov     rax, [rax+10h]
0x18000449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a4  mov     rcx, [rbp+arg_10]
0x1800044a8  jmp     loc_180004370
0x1800044ad  mov     r9, [rbp+arg_18]
0x1800044b1  mov     r10, [rbp+bstrString]
0x1800044b5  jmp     short loc_180004448
0x1800044b7  mov     r8, r13
0x1800044ba  mov     rax, r10
0x1800044bd  sub     r8, r10
0x1800044c0  movzx   edx, word ptr [rax]
0x1800044c3  movzx   ecx, word ptr [rax+r8]
0x1800044c8  sub     edx, ecx
0x1800044ca  jnz     short loc_1800044D4
0x1800044cc  add     rax, 2
0x1800044d0  test    ecx, ecx
0x1800044d2  jnz     short loc_1800044C0
0x1800044d4  test    edx, edx
0x1800044d6  jnz     loc_180004448
0x1800044dc  mov     rdx, [rbp+var_40]; struct IXMLDOMElement *
0x1800044e0  lea     r8, [rbp+var_30]; struct TConstructionData *
0x1800044e4  mov     rcx, r15; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800044e7  call    ?AddToFeatureToListOnVisit@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUTConstructionData@@@Z; AddToFeatureToListOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,TConstructionData *)
0x1800044ec  mov     edi, eax
0x1800044ee  cmp     eax, 1
0x1800044f1  jnz     short loc_1800044AD
0x1800044f3  mov     rcx, [rbp+bstrString]; bstrString
0x1800044f7  mov     ebx, eax
0x1800044f9  test    rcx, rcx
0x1800044fc  jz      short loc_180004508
0x1800044fe  call    cs:__imp_SysFreeString
0x180004504  mov     [rbp+bstrString], rsi
0x180004508  mov     rcx, [rbp+arg_18]; bstrString
0x18000450c  test    rcx, rcx
0x18000450f  jz      short loc_18000451B
0x180004511  call    cs:__imp_SysFreeString
0x180004517  mov     [rbp+arg_18], rsi
0x18000451b  mov     rcx, [rbp+var_40]
0x18000451f  test    rcx, rcx
0x180004522  jz      short loc_180004530
0x180004524  mov     rax, [rcx]
0x180004527  mov     rax, [rax+10h]
0x18000452b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004530  mov     rcx, [rbp+arg_10]
0x180004534  test    rcx, rcx
0x180004537  jz      short loc_180004545
0x180004539  mov     rax, [rcx]
0x18000453c  mov     rax, [rax+10h]
0x180004540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004545  test    edi, edi
0x180004547  js      short loc_180004551
0x180004549  test    ebx, ebx
0x18000454b  mov     edi, esi
0x18000454d  setnz   dil
0x180004551  mov     rcx, [rbp+var_38]
0x180004555  test    rcx, rcx
0x180004558  jz      short loc_180004566
0x18000455a  mov     rax, [rcx]
0x18000455d  mov     rax, [rax+10h]
0x180004561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004566  test    edi, edi
0x180004568  js      loc_1800047B7
0x18000456e  mov     rax, qword ptr [rbp+var_28+8]
0x180004572  lea     rdx, [rbp+var_38]
0x180004576  mov     [r14], rax
0x180004579  xorps   xmm0, xmm0
0x18000457c  mov     rcx, [r15+18h]
0x180004580  mov     dword ptr [rbp+var_30], esi
0x180004583  mov     dword ptr [rbp+var_30+4], 1
0x18000458a  movdqu  [rbp+var_28], xmm0
0x18000458f  mov     [rbp+var_38], rsi
0x180004593  mov     rax, [rcx]
0x180004596  mov     rax, [rax+60h]
0x18000459a  cmp     [r15+24h], esi
0x18000459e  jnz     loc_18000488C
0x1800045a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a9  mov     edi, eax
0x1800045ab  test    eax, eax
0x1800045ad  js      loc_180004A51
0x1800045b3  mov     rcx, [rbp+var_38]
0x1800045b7  mov     rax, [rcx]
0x1800045ba  mov     rax, [rax+50h]
0x1800045be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c3  mov     edi, eax
0x1800045c5  test    eax, eax
0x1800045c7  js      loc_180004A51
0x1800045cd  mov     rcx, rsi
0x1800045d0  lea     r13, aParameterinit; "ParameterInit"
0x1800045d7  mov     [rbp+arg_10], rcx
0x1800045db  mov     ebx, esi
0x1800045dd  nop     dword ptr [rax]
0x1800045e0  test    edi, edi
0x1800045e2  js      loc_180004A34
0x1800045e8  mov     rcx, [rbp+var_38]
0x1800045ec  lea     rdx, [rbp+arg_10]
0x1800045f0  mov     rax, [rcx]
0x1800045f3  mov     rax, [rax+48h]
0x1800045f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045fc  mov     edi, eax
0x1800045fe  test    eax, eax
0x180004600  jnz     loc_180004A30
0x180004606  mov     rcx, [rbp+arg_10]
0x18000460a  lea     r8, [rbp+var_40]
0x18000460e  mov     [rbp+var_40], rsi
0x180004612  lea     rdx, IID_IXMLDOMElement
0x180004619  mov     rax, [rcx]
0x18000461c  mov     rax, [rax]
0x18000461f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004624  test    eax, eax
0x180004626  js      loc_1800046E0
0x18000462c  mov     rcx, [rbp+var_40]
0x180004630  lea     rdx, [rbp+arg_18]
0x180004634  mov     [rbp+arg_18], rsi
0x180004638  mov     [rbp+bstrString], rsi
0x18000463c  mov     rax, [rcx]
0x18000463f  mov     rax, [rax+138h]
0x180004646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464b  mov     edi, eax
0x18000464d  test    eax, eax
0x18000464f  js      loc_1800049A1
0x180004655  mov     rcx, [rbp+var_40]
0x180004659  lea     rdx, [rbp+bstrString]
0x18000465d  mov     rax, [rcx]
0x180004660  mov     rax, [rax+148h]
0x180004667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466c  mov     edi, eax
0x18000466e  test    eax, eax
0x180004670  js      loc_1800049A1
0x180004676  mov     r9, [rbp+arg_18]
0x18000467a  mov     r10, [rbp+bstrString]
0x18000467e  test    r9, r9
0x180004681  jz      short loc_1800046BC
0x180004683  test    r10, r10
0x180004686  jz      short loc_1800046D2
0x180004688  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18000468f  mov     rax, r9
0x180004692  sub     r8, r9
0x180004695  nop     word ptr [rax+rax+00000000h]
0x1800046a0  movzx   edx, word ptr [rax]
0x1800046a3  movzx   ecx, word ptr [rax+r8]
0x1800046a8  sub     edx, ecx
0x1800046aa  jnz     short loc_1800046B4
0x1800046ac  add     rax, 2
0x1800046b0  test    ecx, ecx
0x1800046b2  jnz     short loc_1800046A0
0x1800046b4  test    edx, edx
0x1800046b6  jz      loc_1800049AE
0x1800046bc  test    r10, r10
0x1800046bf  jz      short loc_1800046D2
0x1800046c1  mov     rcx, r10; bstrString
0x1800046c4  call    cs:__imp_SysFreeString
0x1800046ca  mov     r9, [rbp+arg_18]
0x1800046ce  mov     [rbp+bstrString], rsi
0x1800046d2  test    r9, r9
0x1800046d5  jz      short loc_1800046E0
0x1800046d7  mov     rcx, r9; bstrString
0x1800046da  call    cs:__imp_SysFreeString
0x1800046e0  mov     rcx, [rbp+arg_10]
0x1800046e4  test    rcx, rcx
0x1800046e7  jz      short loc_1800046FC
0x1800046e9  mov     rax, [rcx]
0x1800046ec  mov     rax, [rax+10h]
0x1800046f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f5  mov     rcx, rsi
0x1800046f8  mov     [rbp+arg_10], rcx
0x1800046fc  mov     rdx, [rbp+var_40]
0x180004700  test    rdx, rdx
0x180004703  jz      loc_1800045E0
0x180004709  mov     rax, [rdx]
0x18000470c  mov     rcx, rdx
0x18000470f  mov     rax, [rax+10h]
0x180004713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004718  mov     rcx, [rbp+arg_10]
0x18000471c  jmp     loc_1800045E0
0x180004721  mov     rdx, [rbp+var_40]; struct IXMLDOMElement *
  ... truncated ...
```
