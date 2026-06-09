# NPrintTicketUtil::AutoMapPrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)

- ea: `0x180003708`
- end: `0x180003c13`
- name: `?AutoMapPrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(NPrintTicketUtil *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct NPrintTicketUtil::TFeatureListRoot *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000856c`
- `0x180008f20`
- `0x18000e608`

## callees

- `0x180003708`
- `0x180003c20`
- `0x1800042c0`
- `0x18001c920`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003873`
- `OLEAUT32!__imp_SysFreeString` at `0x180003889`
- `OLEAUT32!__imp_SysFreeString` at `0x180003929`
- `OLEAUT32!__imp_SysFreeString` at `0x18000393c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003acb`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ae1`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b94`
- `OLEAUT32!__imp_SysFreeString` at `0x180003873`
- `OLEAUT32!__imp_SysFreeString` at `0x180003889`
- `OLEAUT32!__imp_SysFreeString` at `0x180003929`
- `OLEAUT32!__imp_SysFreeString` at `0x18000393c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003acb`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ae1`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b94`

## string_xrefs

- `0x180003845`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180003a9d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::AutoMapPrintTicketToFeatureList(
        NPrintTicketUtil *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct NPrintTicketUtil::TFeatureListRoot **a3)
{
  int PrintTicketFeatureList; // eax
  struct NPrintTicketUtil::TFeatureListRoot *v6; // rdx
  NPrintTicketUtil *v7; // r14
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // edi
  OLECHAR *v12; // rax
  OLECHAR *v13; // rcx
  BSTR v14; // rdx
  int v15; // r8d
  int v16; // r9d
  BSTR v17; // rdx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // edi
  OLECHAR *v24; // rax
  OLECHAR *v25; // rcx
  BSTR v26; // rdx
  int v27; // r8d
  int v28; // r9d
  BSTR v29; // rdx
  int v30; // r9d
  int v31; // r8d
  int v32; // eax
  __int64 v34; // [rsp+20h] [rbp-30h] BYREF
  struct IXMLDOMElement *v35; // [rsp+28h] [rbp-28h] BYREF
  __int64 v36; // [rsp+30h] [rbp-20h] BYREF
  __int64 v37; // [rsp+38h] [rbp-18h] BYREF
  __int64 v38; // [rsp+40h] [rbp-10h]
  __int64 v39; // [rsp+48h] [rbp-8h]
  BSTR bstrString; // [rsp+90h] [rbp+40h] BYREF
  BSTR v41; // [rsp+98h] [rbp+48h] BYREF

  bstrString = 0;
  PrintTicketFeatureList = NPrintTicketUtil::CreatePrintTicketFeatureList(
                             this,
                             (struct NPrintTicketUtil::CPrintTicketWrapper *)&bstrString,
                             a3);
  v7 = (NPrintTicketUtil *)bstrString;
  v8 = PrintTicketFeatureList;
  if ( PrintTicketFeatureList < 0 )
    goto LABEL_87;
  v9 = *((_QWORD *)this + 3);
  v37 = 0;
  v38 = *(_QWORD *)bstrString;
  v39 = *(_QWORD *)a2;
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 96LL))(v9, &v36);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
    if ( v8 >= 0 )
    {
      v10 = 0;
      v11 = 0;
      v34 = 0;
      while ( 1 )
      {
        if ( v8 < 0 )
        {
LABEL_38:
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          if ( v8 >= 0 )
            v8 = v11 != 0;
          goto LABEL_42;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 72LL))(v36, &v34);
        if ( v8 )
          goto LABEL_37;
        v35 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v34)(v34, &IID_IXMLDOMElement, &v35) >= 0 )
          break;
LABEL_20:
        v10 = v34;
        if ( v34 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          v10 = 0;
          v34 = 0;
        }
        v6 = (struct NPrintTicketUtil::TFeatureListRoot *)v35;
        if ( v35 )
        {
          ((void (__fastcall *)(struct IXMLDOMElement *))v35->lpVtbl->Release)(v35);
          v10 = v34;
        }
      }
      v41 = 0;
      bstrString = 0;
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v35->lpVtbl->get_namespaceURI)(v35, &v41);
      if ( v8 < 0
        || (v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v35->lpVtbl->get_baseName)(v35, &bstrString),
            v8 < 0) )
      {
        v13 = bstrString;
      }
      else
      {
        v12 = v41;
        v13 = bstrString;
        if ( !v41 )
          goto LABEL_16;
        if ( !bstrString )
        {
LABEL_18:
          if ( v12 )
            SysFreeString(v12);
          goto LABEL_20;
        }
        v14 = v41;
        do
        {
          v15 = *(BSTR)((char *)v14
                      + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                      - (char *)v41);
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
            v12 = v41;
            bstrString = 0;
          }
          goto LABEL_18;
        }
        v20 = AutoMapNamedElementOnVisit(this, v35, (struct TAutomappingData *)&v37);
        v13 = bstrString;
        v8 = v20;
        if ( v20 == 1 )
        {
          v11 = 1;
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v41 )
          {
            SysFreeString(v41);
            v41 = 0;
          }
          if ( v35 )
            ((void (__fastcall *)(struct IXMLDOMElement *))v35->lpVtbl->Release)(v35);
LABEL_37:
          v10 = v34;
          goto LABEL_38;
        }
      }
      v12 = v41;
      goto LABEL_16;
    }
  }
LABEL_42:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v8 < 0 )
    goto LABEL_87;
  v21 = *((_QWORD *)this + 3);
  v37 = 1;
  v38 = *(_QWORD *)v7;
  v39 = *(_QWORD *)a2;
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 96LL))(v21, &v36);
  if ( v8 < 0 )
    goto LABEL_85;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
  if ( v8 < 0 )
    goto LABEL_85;
  v22 = 0;
  v23 = 0;
  v34 = 0;
  while ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 72LL))(v36, &v34);
    if ( v8 )
      goto LABEL_80;
    v35 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v34)(v34, &IID_IXMLDOMElement, &v35) >= 0 )
    {
      v41 = 0;
      bstrString = 0;
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v35->lpVtbl->get_namespaceURI)(v35, &v41);
      if ( v8 < 0
        || (v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v35->lpVtbl->get_baseName)(v35, &bstrString),
            v8 < 0) )
      {
        v25 = bstrString;
        goto LABEL_68;
      }
      v24 = v41;
      v25 = bstrString;
      if ( v41 )
      {
        if ( bstrString )
        {
          v26 = v41;
          do
          {
            v27 = *(BSTR)((char *)v26
                        + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                        - (char *)v41);
            v28 = *v26 - v27;
            if ( v28 )
              break;
            ++v26;
          }
          while ( v27 );
          if ( !v28 )
          {
            v29 = bstrString;
            do
            {
              v30 = *(BSTR)((char *)v29 + (char *)L"ParameterInit" - (char *)bstrString);
              v31 = *v29 - v30;
              if ( v31 )
                break;
              ++v29;
            }
            while ( v30 );
            if ( !v31 )
            {
              v32 = AutoMapNamedElementOnVisit(this, v35, (struct TAutomappingData *)&v37);
              v25 = bstrString;
              v8 = v32;
              if ( v32 == 1 )
              {
                v23 = 1;
                if ( bstrString )
                {
                  SysFreeString(bstrString);
                  bstrString = 0;
                }
                if ( v41 )
                {
                  SysFreeString(v41);
                  v41 = 0;
                }
                if ( v35 )
                  ((void (__fastcall *)(struct IXMLDOMElement *))v35->lpVtbl->Release)(v35);
LABEL_80:
                v22 = v34;
                break;
              }
LABEL_68:
              v24 = v41;
            }
          }
          goto LABEL_59;
        }
      }
      else
      {
LABEL_59:
        if ( v25 )
        {
          SysFreeString(v25);
          v24 = v41;
          bstrString = 0;
        }
      }
      if ( v24 )
        SysFreeString(v24);
    }
    v22 = v34;
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v22 = 0;
      v34 = 0;
    }
    v6 = (struct NPrintTicketUtil::TFeatureListRoot *)v35;
    if ( v35 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v35->lpVtbl->Release)(v35);
      v22 = v34;
    }
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v8 >= 0 )
    v8 = v23 != 0;
LABEL_85:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
LABEL_87:
  if ( v7 )
    NPrintTicketUtil::DeletePrintTicketFeatureList(v7, v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003708  mov     [rsp-28h+arg_0], rbx
0x18000370d  mov     [rsp-28h+arg_8], rsi
0x180003712  push    rbp
0x180003713  push    rdi
0x180003714  push    r12
0x180003716  push    r14
0x180003718  push    r15
0x18000371a  mov     rbp, rsp
0x18000371d  sub     rsp, 50h
0x180003721  mov     rsi, rdx
0x180003724  xor     r12d, r12d
0x180003727  lea     rdx, [rbp+bstrString]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000372b  mov     [rbp+bstrString], r12
0x18000372f  mov     r15, rcx
0x180003732  call    ?CreatePrintTicketFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAPEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::CreatePrintTicketFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot * *)
0x180003737  mov     r14, [rbp+bstrString]
0x18000373b  mov     ebx, eax
0x18000373d  test    eax, eax
0x18000373f  js      loc_180003BE9
0x180003745  mov     rcx, [r15+18h]
0x180003749  lea     rdx, [rbp+var_20]
0x18000374d  mov     [rbp+var_18], r12
0x180003751  mov     rax, [r14]
0x180003754  mov     [rbp+var_10], rax
0x180003758  mov     rax, [rsi]
0x18000375b  mov     [rbp+var_8], rax
0x18000375f  mov     [rbp+var_20], r12
0x180003763  mov     rax, [rcx]
0x180003766  mov     rax, [rax+60h]
0x18000376a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376f  mov     ebx, eax
0x180003771  test    eax, eax
0x180003773  js      loc_18000397C
0x180003779  mov     rcx, [rbp+var_20]
0x18000377d  mov     rax, [rcx]
0x180003780  mov     rax, [rax+50h]
0x180003784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003789  mov     ebx, eax
0x18000378b  test    eax, eax
0x18000378d  js      loc_18000397C
0x180003793  mov     ecx, r12d
0x180003796  mov     edi, r12d
0x180003799  mov     [rbp+var_30], rcx
0x18000379d  test    ebx, ebx
0x18000379f  js      loc_18000395F
0x1800037a5  mov     rcx, [rbp+var_20]
0x1800037a9  lea     rdx, [rbp+var_30]
0x1800037ad  mov     rax, [rcx]
0x1800037b0  mov     rax, [rax+48h]
0x1800037b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b9  mov     ebx, eax
0x1800037bb  test    eax, eax
0x1800037bd  jnz     loc_18000395B
0x1800037c3  mov     rcx, [rbp+var_30]
0x1800037c7  lea     r8, [rbp+var_28]
0x1800037cb  mov     [rbp+var_28], r12
0x1800037cf  lea     rdx, IID_IXMLDOMElement
0x1800037d6  mov     rax, [rcx]
0x1800037d9  mov     rax, [rax]
0x1800037dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e1  test    eax, eax
0x1800037e3  js      loc_18000388F
0x1800037e9  mov     rcx, [rbp+var_28]
0x1800037ed  lea     rdx, [rbp+arg_18]
0x1800037f1  mov     [rbp+arg_18], r12
0x1800037f5  mov     [rbp+bstrString], r12
0x1800037f9  mov     rax, [rcx]
0x1800037fc  mov     rax, [rax+138h]
0x180003803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003808  mov     ebx, eax
0x18000380a  test    eax, eax
0x18000380c  js      loc_1800038D0
0x180003812  mov     rcx, [rbp+var_28]
0x180003816  lea     rdx, [rbp+bstrString]
0x18000381a  mov     rax, [rcx]
0x18000381d  mov     rax, [rax+148h]
0x180003824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003829  mov     ebx, eax
0x18000382b  test    eax, eax
0x18000382d  js      loc_1800038D0
0x180003833  mov     rax, [rbp+arg_18]
0x180003837  mov     rcx, [rbp+bstrString]; bstrString
0x18000383b  test    rax, rax
0x18000383e  jz      short loc_18000386E
0x180003840  test    rcx, rcx
0x180003843  jz      short loc_180003881
0x180003845  lea     r10, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18000384c  mov     rdx, rax
0x18000384f  sub     r10, rax
0x180003852  movzx   r9d, word ptr [rdx]
0x180003856  movzx   r8d, word ptr [rdx+r10]
0x18000385b  sub     r9d, r8d
0x18000385e  jnz     short loc_180003869
0x180003860  add     rdx, 2
0x180003864  test    r8d, r8d
0x180003867  jnz     short loc_180003852
0x180003869  test    r9d, r9d
0x18000386c  jz      short loc_1800038DA
0x18000386e  test    rcx, rcx
0x180003871  jz      short loc_180003881
0x180003873  call    cs:__imp_SysFreeString
0x180003879  mov     rax, [rbp+arg_18]
0x18000387d  mov     [rbp+bstrString], r12
0x180003881  test    rax, rax
0x180003884  jz      short loc_18000388F
0x180003886  mov     rcx, rax; bstrString
0x180003889  call    cs:__imp_SysFreeString
0x18000388f  mov     rcx, [rbp+var_30]
0x180003893  test    rcx, rcx
0x180003896  jz      short loc_1800038AB
0x180003898  mov     rax, [rcx]
0x18000389b  mov     rax, [rax+10h]
0x18000389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a4  mov     rcx, r12
0x1800038a7  mov     [rbp+var_30], rcx
0x1800038ab  mov     rdx, [rbp+var_28]
0x1800038af  test    rdx, rdx
0x1800038b2  jz      loc_18000379D
0x1800038b8  mov     rax, [rdx]
0x1800038bb  mov     rcx, rdx
0x1800038be  mov     rax, [rax+10h]
0x1800038c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c7  mov     rcx, [rbp+var_30]
0x1800038cb  jmp     loc_18000379D
0x1800038d0  mov     rcx, [rbp+bstrString]
0x1800038d4  mov     rax, [rbp+arg_18]
0x1800038d8  jmp     short loc_18000386E
0x1800038da  lea     r10, aFeature; "Feature"
0x1800038e1  mov     rdx, rcx
0x1800038e4  sub     r10, rcx
0x1800038e7  movzx   r9d, word ptr [rdx]
0x1800038eb  movzx   r8d, word ptr [rdx+r10]
0x1800038f0  sub     r9d, r8d
0x1800038f3  jnz     short loc_1800038FE
0x1800038f5  add     rdx, 2
0x1800038f9  test    r8d, r8d
0x1800038fc  jnz     short loc_1800038E7
0x1800038fe  test    r9d, r9d
0x180003901  jnz     loc_18000386E
0x180003907  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x18000390b  lea     r8, [rbp+var_18]; struct TAutomappingData *
0x18000390f  mov     rcx, r15; this
0x180003912  call    ?AutoMapNamedElementOnVisit@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUTAutomappingData@@@Z; AutoMapNamedElementOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,TAutomappingData *)
0x180003917  mov     rcx, [rbp+bstrString]; bstrString
0x18000391b  mov     ebx, eax
0x18000391d  cmp     eax, 1
0x180003920  jnz     short loc_1800038D4
0x180003922  mov     edi, eax
0x180003924  test    rcx, rcx
0x180003927  jz      short loc_180003933
0x180003929  call    cs:__imp_SysFreeString
0x18000392f  mov     [rbp+bstrString], r12
0x180003933  mov     rcx, [rbp+arg_18]; bstrString
0x180003937  test    rcx, rcx
0x18000393a  jz      short loc_180003946
0x18000393c  call    cs:__imp_SysFreeString
0x180003942  mov     [rbp+arg_18], r12
0x180003946  mov     rcx, [rbp+var_28]
0x18000394a  test    rcx, rcx
0x18000394d  jz      short loc_18000395B
0x18000394f  mov     rax, [rcx]
0x180003952  mov     rax, [rax+10h]
0x180003956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000395b  mov     rcx, [rbp+var_30]
0x18000395f  test    rcx, rcx
0x180003962  jz      short loc_180003970
0x180003964  mov     rax, [rcx]
0x180003967  mov     rax, [rax+10h]
0x18000396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003970  test    ebx, ebx
0x180003972  js      short loc_18000397C
0x180003974  test    edi, edi
0x180003976  mov     ebx, r12d
0x180003979  setnz   bl
0x18000397c  mov     rcx, [rbp+var_20]
0x180003980  test    rcx, rcx
0x180003983  jz      short loc_180003991
0x180003985  mov     rax, [rcx]
0x180003988  mov     rax, [rax+10h]
0x18000398c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003991  test    ebx, ebx
0x180003993  js      loc_180003BE9
0x180003999  mov     rcx, [r15+18h]
0x18000399d  lea     rdx, [rbp+var_20]
0x1800039a1  mov     [rbp+var_18], 1
0x1800039a9  mov     rax, [r14]
0x1800039ac  mov     [rbp+var_10], rax
0x1800039b0  mov     rax, [rsi]
0x1800039b3  mov     [rbp+var_8], rax
0x1800039b7  mov     [rbp+var_20], r12
0x1800039bb  mov     rax, [rcx]
0x1800039be  mov     rax, [rax+60h]
0x1800039c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c7  mov     ebx, eax
0x1800039c9  test    eax, eax
0x1800039cb  js      loc_180003BD4
0x1800039d1  mov     rcx, [rbp+var_20]
0x1800039d5  mov     rax, [rcx]
0x1800039d8  mov     rax, [rax+50h]
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  mov     ebx, eax
0x1800039e3  test    eax, eax
0x1800039e5  js      loc_180003BD4
0x1800039eb  mov     rcx, r12
0x1800039ee  mov     edi, r12d
0x1800039f1  mov     [rbp+var_30], rcx
0x1800039f5  test    ebx, ebx
0x1800039f7  js      loc_180003BB7
0x1800039fd  mov     rcx, [rbp+var_20]
0x180003a01  lea     rdx, [rbp+var_30]
0x180003a05  mov     rax, [rcx]
0x180003a08  mov     rax, [rax+48h]
0x180003a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a11  mov     ebx, eax
0x180003a13  test    eax, eax
0x180003a15  jnz     loc_180003BB3
0x180003a1b  mov     rcx, [rbp+var_30]
0x180003a1f  lea     r8, [rbp+var_28]
0x180003a23  mov     [rbp+var_28], r12
0x180003a27  lea     rdx, IID_IXMLDOMElement
0x180003a2e  mov     rax, [rcx]
0x180003a31  mov     rax, [rax]
0x180003a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a39  test    eax, eax
0x180003a3b  js      loc_180003AE7
0x180003a41  mov     rcx, [rbp+var_28]
0x180003a45  lea     rdx, [rbp+arg_18]
0x180003a49  mov     [rbp+arg_18], r12
0x180003a4d  mov     [rbp+bstrString], r12
0x180003a51  mov     rax, [rcx]
0x180003a54  mov     rax, [rax+138h]
0x180003a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a60  mov     ebx, eax
0x180003a62  test    eax, eax
0x180003a64  js      loc_180003B28
0x180003a6a  mov     rcx, [rbp+var_28]
0x180003a6e  lea     rdx, [rbp+bstrString]
0x180003a72  mov     rax, [rcx]
0x180003a75  mov     rax, [rax+148h]
0x180003a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a81  mov     ebx, eax
0x180003a83  test    eax, eax
0x180003a85  js      loc_180003B28
0x180003a8b  mov     rax, [rbp+arg_18]
0x180003a8f  mov     rcx, [rbp+bstrString]; bstrString
0x180003a93  test    rax, rax
0x180003a96  jz      short loc_180003AC6
0x180003a98  test    rcx, rcx
0x180003a9b  jz      short loc_180003AD9
0x180003a9d  lea     r10, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180003aa4  mov     rdx, rax
0x180003aa7  sub     r10, rax
0x180003aaa  movzx   r9d, word ptr [rdx]
0x180003aae  movzx   r8d, word ptr [rdx+r10]
0x180003ab3  sub     r9d, r8d
0x180003ab6  jnz     short loc_180003AC1
0x180003ab8  add     rdx, 2
0x180003abc  test    r8d, r8d
0x180003abf  jnz     short loc_180003AAA
0x180003ac1  test    r9d, r9d
0x180003ac4  jz      short loc_180003B32
0x180003ac6  test    rcx, rcx
0x180003ac9  jz      short loc_180003AD9
0x180003acb  call    cs:__imp_SysFreeString
0x180003ad1  mov     rax, [rbp+arg_18]
0x180003ad5  mov     [rbp+bstrString], r12
0x180003ad9  test    rax, rax
0x180003adc  jz      short loc_180003AE7
0x180003ade  mov     rcx, rax; bstrString
0x180003ae1  call    cs:__imp_SysFreeString
0x180003ae7  mov     rcx, [rbp+var_30]
0x180003aeb  test    rcx, rcx
0x180003aee  jz      short loc_180003B03
0x180003af0  mov     rax, [rcx]
0x180003af3  mov     rax, [rax+10h]
0x180003af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afc  mov     rcx, r12
0x180003aff  mov     [rbp+var_30], rcx
0x180003b03  mov     rdx, [rbp+var_28]
0x180003b07  test    rdx, rdx
0x180003b0a  jz      loc_1800039F5
0x180003b10  mov     rax, [rdx]
0x180003b13  mov     rcx, rdx
0x180003b16  mov     rax, [rax+10h]
0x180003b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1f  mov     rcx, [rbp+var_30]
0x180003b23  jmp     loc_1800039F5
0x180003b28  mov     rcx, [rbp+bstrString]
0x180003b2c  mov     rax, [rbp+arg_18]
0x180003b30  jmp     short loc_180003AC6
0x180003b32  lea     r10, aParameterinit; "ParameterInit"
0x180003b39  mov     rdx, rcx
0x180003b3c  sub     r10, rcx
0x180003b3f  movzx   r8d, word ptr [rdx]
0x180003b43  movzx   r9d, word ptr [rdx+r10]
0x180003b48  sub     r8d, r9d
0x180003b4b  jnz     short loc_180003B56
0x180003b4d  add     rdx, 2
0x180003b51  test    r9d, r9d
0x180003b54  jnz     short loc_180003B3F
  ... truncated ...
```
