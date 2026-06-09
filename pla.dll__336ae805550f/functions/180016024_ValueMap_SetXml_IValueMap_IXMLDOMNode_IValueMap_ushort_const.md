# ValueMap::SetXml(IValueMap *,IXMLDOMNode *,IValueMap *,ushort const *)

- ea: `0x180016024`
- end: `0x1800174ab`
- name: `?SetXml@ValueMap@@SAJPEAUIValueMap@@PEAUIXMLDOMNode@@0PEBG@Z`
- size: `5255`
- prototype: `static int(struct IValueMap *, struct IXMLDOMNode *, struct IValueMap *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e61c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180009240`
- `0x1800106d0`
- `0x1800157bc`
- `0x180015f98`
- `0x180016024`
- `0x1800174c0`
- `0x1800198b0`
- `0x180040840`
- `0x18005179c`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001650f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001650f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f20`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f20`
- `OLEAUT32!__imp_VariantInit` at `0x180016098`
- `OLEAUT32!__imp_VariantInit` at `0x1800168fb`
- `OLEAUT32!__imp_VariantInit` at `0x180016098`
- `OLEAUT32!__imp_VariantInit` at `0x1800168fb`
- `OLEAUT32!__imp_VariantClear` at `0x180016244`
- `OLEAUT32!__imp_VariantClear` at `0x180016252`
- `OLEAUT32!__imp_VariantClear` at `0x18001637c`
- `OLEAUT32!__imp_VariantClear` at `0x180016909`
- `OLEAUT32!__imp_VariantClear` at `0x180016a4f`
- `OLEAUT32!__imp_VariantClear` at `0x180016b56`
- `OLEAUT32!__imp_VariantClear` at `0x180016c34`
- `OLEAUT32!__imp_VariantClear` at `0x180016d0f`
- `OLEAUT32!__imp_VariantClear` at `0x180016d21`
- `OLEAUT32!__imp_VariantClear` at `0x180016ea9`
- `OLEAUT32!__imp_VariantClear` at `0x1800172dc`
- `OLEAUT32!__imp_VariantClear` at `0x180016244`
- `OLEAUT32!__imp_VariantClear` at `0x180016252`
- `OLEAUT32!__imp_VariantClear` at `0x18001637c`
- `OLEAUT32!__imp_VariantClear` at `0x180016909`
- `OLEAUT32!__imp_VariantClear` at `0x180016a4f`
- `OLEAUT32!__imp_VariantClear` at `0x180016b56`
- `OLEAUT32!__imp_VariantClear` at `0x180016c34`
- `OLEAUT32!__imp_VariantClear` at `0x180016d0f`
- `OLEAUT32!__imp_VariantClear` at `0x180016d21`
- `OLEAUT32!__imp_VariantClear` at `0x180016ea9`
- `OLEAUT32!__imp_VariantClear` at `0x1800172dc`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001655f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001655f`

## string_xrefs

- `0x1800161e4`: `ValueMap::SetXml`
- `0x180016339`: `ValueMap::SetXml`
- `0x180016693`: `ValueMap::SetXml`
- `0x180016e5d`: `ValueMap::SetXml`
- `0x180017034`: `ValueMap::SetXml`
- `0x18001746d`: `ValueMap::SetXml`
- `0x1800169ed`: `ValueMapItem::SetXml`
- `0x180016b33`: `ValueMapItem::SetXml`
- `0x180017162`: `PlaiCreateXPathName`

## pseudocode

```c
__int64 __fastcall ValueMap::SetXml(
        struct IValueMap *a1,
        struct IXMLDOMNode *a2,
        struct IValueMap *a3,
        unsigned __int16 *a4)
{
  struct IValueMap *v5; // r14
  OLECHAR *v6; // r13
  unsigned __int16 *v7; // rsi
  HANDLE ProcessHeap; // rax
  const void *v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // esi
  __int64 v14; // rbx
  __int64 v15; // r14
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // rdx
  __int64 v19; // rbx
  int v20; // eax
  int v21; // eax
  unsigned __int64 v22; // rdx
  __int64 v23; // rbx
  int v24; // eax
  unsigned __int64 v25; // rdx
  __int64 v26; // rbx
  HRESULT (__stdcall *get_namespaceURI)(IXMLDOMNode *, BSTR *); // rbx
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rcx
  OLECHAR *v31; // rax
  unsigned __int64 v32; // rdx
  OLECHAR *v33; // rbx
  int v34; // eax
  unsigned __int64 v35; // rdx
  __int64 v36; // rbx
  int v37; // eax
  unsigned __int64 v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // rbx
  __int64 Class; // rax
  unsigned __int64 v42; // rdx
  int v43; // eax
  unsigned __int64 v44; // rdx
  unsigned __int16 *v45; // r9
  int v46; // eax
  unsigned __int64 v47; // rdx
  int v48; // r14d
  unsigned __int64 v49; // rcx
  __int64 v50; // rax
  unsigned __int16 *v51; // r9
  struct IXMLDOMNode *v52; // r14
  int v53; // eax
  __int64 v54; // rsi
  int v55; // eax
  int v56; // eax
  unsigned __int64 v57; // rdx
  __int64 v58; // rax
  __int64 *v59; // r9
  __int64 *v60; // rax
  int v61; // eax
  int v62; // eax
  unsigned __int64 v63; // rdx
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rsi
  int v67; // eax
  int v68; // eax
  unsigned __int64 v69; // rdx
  __int64 v70; // rax
  __int64 (__fastcall *v71)(__int64, VARIANTARG *); // rax
  int v72; // eax
  int v73; // eax
  unsigned __int64 v74; // rdx
  __int64 v75; // rax
  unsigned __int64 v76; // rdx
  unsigned __int64 v77; // rdx
  struct IValueMapVtbl *lpVtbl; // rax
  unsigned __int64 v79; // rdx
  unsigned __int64 v80; // rdx
  __int64 v82; // rax
  HRESULT (__stdcall *put_Value)(IValueMap *, VARIANT); // rax
  int v84; // eax
  int v85; // eax
  unsigned __int64 v86; // rdx
  __int64 v87; // rbx
  __int64 v88; // [rsp+28h] [rbp-D8h]
  const void *v89; // [rsp+70h] [rbp-90h] BYREF
  __int64 v90; // [rsp+78h] [rbp-88h] BYREF
  __int64 v91; // [rsp+80h] [rbp-80h]
  OLECHAR *v92; // [rsp+88h] [rbp-78h] BYREF
  struct IXMLDOMNode *v93; // [rsp+90h] [rbp-70h] BYREF
  LPCVOID lpMem; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v96; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v97; // [rsp+C0h] [rbp-40h] BYREF
  struct IValueMap *v98; // [rsp+D8h] [rbp-28h]
  __int64 v99; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v100; // [rsp+E8h] [rbp-18h]
  BSTR bstrString[2]; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v102; // [rsp+100h] [rbp+0h] BYREF
  struct IValueMap *v103; // [rsp+120h] [rbp+20h]
  struct IXMLDOMNode *v104; // [rsp+128h] [rbp+28h]
  unsigned __int16 v105[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v106[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v107[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v108[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v109[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v110[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v111[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v112[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v113[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v114[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v115[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v116[64]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v117[64]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v118[64]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v119[64]; // [rsp+830h] [rbp+730h] BYREF
  unsigned __int16 v120[64]; // [rsp+8B0h] [rbp+7B0h] BYREF
  unsigned __int16 v121[64]; // [rsp+930h] [rbp+830h] BYREF
  unsigned __int16 v122[64]; // [rsp+9B0h] [rbp+8B0h] BYREF
  unsigned __int16 v123[64]; // [rsp+A30h] [rbp+930h] BYREF
  unsigned __int16 v124[64]; // [rsp+AB0h] [rbp+9B0h] BYREF
  unsigned __int16 v125[64]; // [rsp+B30h] [rbp+A30h] BYREF

  v103 = a1;
  v96 = 0;
  v5 = a1;
  v98 = a3;
  v91 = 0;
  v93 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = 0;
  v99 = 0;
  bstrString[0] = 0;
  v7 = a4;
  v100 = a4;
  v104 = a2;
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, 0x800u);
  v11 = (unsigned int)xmmword_180169738;
  v12 = qword_180169748;
  v90 = 2048;
  lpMem = v10;
  v89 = v10;
  LODWORD(v92) = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC, 4, byte_180147320, 1, &v92, 4, &v89, 8);
    v12 = qword_180169748;
    v11 = (unsigned int)xmmword_180169738;
  }
  if ( !lpMem )
  {
    LODWORD(v92) = 0;
    LODWORD(v89) = -2147024882;
    v13 = -2147024882;
    if ( (_DWORD)v11 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v12 == (v12 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v105, v11);
      v14 = -1;
      do
        ++v14;
      while ( v105[v14] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v92, 4);
    }
    goto LABEL_12;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"Description", 8, a2, &pvarg) >= 0 )
  {
    v16 = ((__int64 (__fastcall *)(struct IValueMap *, LONGLONG))v5->lpVtbl->put_Description)(v5, pvarg.llVal);
    if ( v16 )
    {
      v17 = PlaiAddValidation(a3, v7, L"Description", v16);
      v13 = v17;
      if ( v17 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v92) = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_12;
        }
        PlaiWhoAmI(v106, v18);
        v19 = -1;
        do
          ++v19;
        while ( v106[v19] );
LABEL_21:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v92, 4, byte_180147320, 1, &v89, 4);
LABEL_12:
        v15 = 0;
        goto LABEL_139;
      }
      v7 = v100;
    }
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"ValueMapType", 3, a2, &pvarg) >= 0 )
  {
    v20 = ((__int64 (__fastcall *)(struct IValueMap *, _QWORD))v5->lpVtbl->put_ValueMapType)(v5, pvarg.cyVal.Lo);
    if ( v20 )
    {
      v21 = PlaiAddValidation(a3, v7, L"ValueMapType", v20);
      v13 = v21;
      if ( v21 < 0 )
      {
        LODWORD(v89) = 0;
        LODWORD(v92) = v21;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_12;
        }
        PlaiWhoAmI(v107, v22);
        v23 = -1;
        do
          ++v23;
        while ( v107[v23] );
        goto LABEL_21;
      }
    }
  }
  v24 = ((__int64 (__fastcall *)(struct IValueMap *, unsigned int *))v5->lpVtbl->get_ValueMapType)(v5, &v96);
  v13 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v92) = v24;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_12;
    }
    PlaiWhoAmI(v108, v25);
    v26 = -1;
    do
      ++v26;
    while ( v108[v26] );
    goto LABEL_21;
  }
  get_namespaceURI = a2->lpVtbl->get_namespaceURI;
  v28 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(bstrString);
  v29 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64))get_namespaceURI)(a2, v28);
  if ( v29 != 1 )
    MicrosoftTelemetryAssertTriggeredArgs(v30, v29);
  PlaiFreeString(0);
  v31 = SysAllocString(L"ValueMapItem");
  v33 = v31;
  if ( !v31 )
  {
    v13 = -2147024882;
    LODWORD(v89) = -2147024882;
    v6 = 0;
    LODWORD(v90) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v125, v32);
      v87 = -1;
      do
        ++v87;
      while ( v125[v87] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v90, 4);
    }
    goto LABEL_12;
  }
  if ( (_DWORD)xmmword_180169738 )
  {
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      v90 = SysStringByteLen(v31);
      v92 = v33;
      LODWORD(v89) = 0;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
        {
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC_STRING, 4, byte_180147320, 1, &v89, 4, &v92, 8);
        }
      }
    }
  }
  v6 = v33;
  v34 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))a2->lpVtbl->selectNodes)(a2, v33, &v99);
  v13 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v92) = v34;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_12;
    }
    PlaiWhoAmI(v109, v35);
    v36 = -1;
    do
      ++v36;
    while ( v109[v36] );
    goto LABEL_21;
  }
  if ( v34 == 1 )
  {
    v13 = 0;
    v15 = 0;
    goto LABEL_139;
  }
  if ( v93 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v93->lpVtbl->Release)(v93);
    v93 = 0;
  }
  v37 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v99 + 72LL))(v99, &v93);
  v13 = v37;
  if ( v37 < 0 )
  {
    LODWORD(v89) = 0;
    LODWORD(v92) = v37;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_12;
    }
    PlaiWhoAmI(v110, v38);
    v39 = -1;
    do
      ++v39;
    while ( v110[v39] );
    goto LABEL_21;
  }
  v40 = -1;
  for ( LODWORD(v92) = 0; ; LODWORD(v92) = (_DWORD)v92 + 1 )
  {
    if ( v13 == 1 )
    {
      VariantClear(&pvarg);
      pvarg.llVal = 0;
      if ( v96 != 1 && v96 != 2 )
        goto LABEL_138;
      if ( (int)PlaiReadXmlElement(L"Value", 21, v104, &pvarg) < 0
        || (put_Value = v5->lpVtbl->put_Value,
            v102 = pvarg,
            (v84 = ((__int64 (__fastcall *)(struct IValueMap *, VARIANTARG *))put_Value)(v5, &v102)) == 0)
        || (v85 = PlaiAddValidation(v98, v100, L"Value", v84), v13 = v85, v85 >= 0) )
      {
        v15 = v91;
        v13 = 0;
        goto LABEL_139;
      }
      LODWORD(v90) = 0;
      LODWORD(v89) = v85;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_138;
      }
      PlaiWhoAmI(v124, v86);
      do
        ++v40;
      while ( v124[v40] );
LABEL_137:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v90, 4);
      goto LABEL_138;
    }
    if ( v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    Class = CreateClassObject<ValueMapItem>();
    v91 = Class;
    v15 = Class;
    if ( !Class )
      break;
    v43 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)Class + 128LL))(Class, v96);
    v13 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v43;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v122, v44);
        do
          ++v40;
        while ( v122[v40] );
        goto LABEL_161;
      }
      goto LABEL_139;
    }
    if ( (_DWORD)v92 == -1 )
    {
      v45 = v100;
      if ( !v100 )
        v45 = (unsigned __int16 *)&szPassword;
      v46 = StringCchPrintfW((unsigned __int16 *)lpMem, 0x400u, L"%s%s/", v45, L"ValueMapItem");
      v48 = v46;
      if ( v46 < 0 )
      {
        v49 = qword_180169748;
        LODWORD(v90) = 0;
        LODWORD(v89) = v46;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v115, v47);
          v50 = -1;
          do
            ++v50;
          while ( v115[v50] );
LABEL_173:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v90, 4);
          v49 = qword_180169748;
          goto LABEL_174;
        }
        goto LABEL_174;
      }
    }
    else
    {
      v51 = v100;
      LODWORD(v88) = (_DWORD)v92;
      if ( !v100 )
        v51 = (unsigned __int16 *)&szPassword;
      v48 = StringCchPrintfW((unsigned __int16 *)lpMem, 0x400u, L"%s%s[%u]/", v51, L"ValueMapItem", v88);
      if ( v48 < 0 )
      {
        v49 = qword_180169748;
        LODWORD(v90) = 0;
        LODWORD(v89) = v48;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v120, v47);
          v82 = -1;
          do
            ++v82;
          while ( v120[v82] );
          goto LABEL_173;
        }
LABEL_174:
        LODWORD(v89) = v48;
        v13 = v48;
        LODWORD(v90) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && v49 == (v49 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v121, v47);
          do
            ++v40;
          while ( v121[v40] );
          goto LABEL_137;
        }
        goto LABEL_138;
      }
    }
    v52 = v93;
    memset(&v97, 0, sizeof(v97));
    VariantInit(&v97);
    v97.llVal = 0;
    VariantClear(&v97);
    v97.llVal = 0;
    v53 = PlaiReadXmlElement(L"Key", 8, v52, &v97);
    v54 = v91;
    if ( v53 >= 0 )
    {
      v55 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v91 + 96LL))(v91, v97.llVal);
      if ( v55 )
      {
        v56 = PlaiAddValidation(v98, (const unsigned __int16 *)lpMem, L"Key", v55);
        v13 = v56;
        if ( v56 < 0 )
        {
          LODWORD(v90) = v56;
          LODWORD(v89) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v111, v57);
            v58 = -1;
            do
              ++v58;
            while ( v111[v58] );
            v59 = &v90;
            v60 = (__int64 *)&v89;
            goto LABEL_94;
          }
          goto LABEL_125;
        }
        v54 = v91;
      }
    }
    VariantClear(&v97);
    v97.llVal = 0;
    if ( (int)PlaiReadXmlElement(L"Description", 8, v52, &v97) >= 0 )
    {
      v61 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v54 + 64LL))(v54, v97.llVal);
      if ( v61 )
      {
        v62 = PlaiAddValidation(v98, (const unsigned __int16 *)lpMem, L"Description", v61);
        v13 = v62;
        if ( v62 < 0 )
        {
          LODWORD(v89) = v62;
          LODWORD(v90) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v112, v63);
            v64 = -1;
            do
              ++v64;
            while ( v112[v64] );
            goto LABEL_104;
          }
          goto LABEL_125;
        }
      }
    }
    VariantClear(&v97);
    v97.llVal = 0;
    v65 = PlaiReadXmlElement(L"Enabled", 11, v52, &v97);
    v66 = v91;
    if ( v65 >= 0 )
    {
      v67 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 80LL))(v91, v97.uiVal);
      if ( v67 )
      {
        v68 = PlaiAddValidation(v98, (const unsigned __int16 *)lpMem, L"Enabled", v67);
        v13 = v68;
        if ( v68 < 0 )
        {
          LODWORD(v89) = v68;
          LODWORD(v90) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v113, v69);
            v70 = -1;
            do
              ++v70;
            while ( v113[v70] );
            goto LABEL_104;
          }
          goto LABEL_125;
        }
        v66 = v91;
      }
    }
    VariantClear(&v97);
    v97.llVal = 0;
    if ( (int)PlaiReadXmlElement(L"Value", 21, v52, &v97) >= 0
      && (v71 = *(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v66 + 112LL),
          v102 = v97,
          (v72 = v71(v66, &v102)) != 0)
      && (v73 = PlaiAddValidation(v98, (const unsigned __int16 *)lpMem, L"Value", v72), v13 = v73, v73 < 0) )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v73;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v114, v74);
        v75 = -1;
        do
          ++v75;
        while ( v114[v75] );
LABEL_104:
        v59 = (__int64 *)&v89;
        v60 = &v90;
LABEL_94:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v59, 4, byte_180147320, 1, v60, 4);
      }
    }
    else
    {
      v13 = 0;
    }
LABEL_125:
    VariantClear(&v97);
    if ( v13 < 0 )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_138;
      }
      PlaiWhoAmI(v119, v76);
      do
        ++v40;
      while ( v119[v40] );
      goto LABEL_137;
    }
    VariantClear(&pvarg);
    pvarg.llVal = 0;
    v15 = v91;
    v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, ULONG *))v91)(v91, &IID_IDispatch, (ULONG *)&pvarg.cyVal);
    if ( v13 < 0 )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v13;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v118, v77);
        do
          ++v40;
        while ( v118[v40] );
        goto LABEL_161;
      }
      goto LABEL_139;
    }
    v5 = v103;
    pvarg.vt = 9;
    lpVtbl = v103->lpVtbl;
    v102 = pvarg;
    v13 = ((__int64 (__fastcall *)(struct IValueMap *, VARIANTARG *))lpVtbl->Add)(v103, &v102);
    if ( v13 < 0 )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v13;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v117, v79);
        do
          ++v40;
        while ( v117[v40] );
        goto LABEL_137;
      }
LABEL_138:
      v15 = v91;
      goto LABEL_139;
    }
    if ( v93 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v93->lpVtbl->Release)(v93);
      v93 = 0;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v99 + 72LL))(v99, &v93);
    if ( v13 < 0 )
    {
      LODWORD(v90) = 0;
      LODWORD(v89) = v13;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v116, v80);
        do
          ++v40;
        while ( v116[v40] );
        goto LABEL_137;
      }
      goto LABEL_138;
    }
  }
  v13 = -2147024882;
  LODWORD(v89) = -2147024882;
  LODWORD(v90) = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v123, v42);
    do
      ++v40;
    while ( v123[v40] );
LABEL_161:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v89, 4, byte_180147320, 1, &v90, 4);
  }
LABEL_139:
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( lpMem )
    PlaiFree(lpMem, 1);
  PlaiFreeString(v6);
  if ( v99 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
    v99 = 0;
  }
  if ( v93 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v93->lpVtbl->Release)(v93);
    v93 = 0;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016024  push    rbp
0x180016026  push    rbx
0x180016027  push    rsi
0x180016028  push    rdi
0x180016029  push    r12
0x18001602b  push    r13
0x18001602d  push    r14
0x18001602f  push    r15
0x180016031  lea     rbp, [rsp-0AC8h]
0x180016039  sub     rsp, 0BC8h
0x180016040  mov     rax, cs:__security_cookie
0x180016047  xor     rax, rsp
0x18001604a  mov     [rbp+0B00h+var_50], rax
0x180016051  xor     r12d, r12d
0x180016054  mov     [rbp+0B00h+var_AE0], rcx
0x180016058  mov     rbx, r8
0x18001605b  mov     [rbp+0B00h+var_B48], r12d
0x18001605f  mov     r14, rcx
0x180016062  mov     [rbp+0B00h+var_B28], rbx
0x180016066  xorps   xmm0, xmm0
0x180016069  mov     [rbp+0B00h+var_B80], r12
0x18001606d  xor     eax, eax
0x18001606f  mov     [rbp+0B00h+var_B70], r12
0x180016073  lea     rcx, [rbp+0B00h+pvarg]; pvarg
0x180016077  mov     qword ptr [rbp+0B00h+pvarg+10h], rax
0x18001607b  movups  xmmword ptr [rbp+0B00h+pvarg], xmm0
0x18001607f  mov     r13d, r12d
0x180016082  mov     [rbp+0B00h+var_B20], r12
0x180016086  mov     [rbp+0B00h+bstrString], r12
0x18001608a  mov     rsi, r9
0x18001608d  mov     [rbp+0B00h+var_B18], r9
0x180016091  mov     rdi, rdx
0x180016094  mov     [rbp+0B00h+var_AD8], rdx
0x180016098  call    cs:__imp_VariantInit
0x18001609e  mov     qword ptr [rbp+0B00h+pvarg+8], r12
0x1800160a2  call    cs:__imp_GetProcessHeap
0x1800160a8  mov     r15d, 800h
0x1800160ae  xor     edx, edx; dwFlags
0x1800160b0  mov     rcx, rax; hHeap
0x1800160b3  mov     r8d, r15d; dwBytes
0x1800160b6  call    cs:__imp_HeapAlloc
0x1800160bc  mov     edx, dword ptr cs:xmmword_180169738
0x1800160c2  lea     r9d, [r12+8]
0x1800160c7  mov     rcx, cs:qword_180169748
0x1800160ce  mov     r8, 4000000000000200h
0x1800160d8  mov     [rsp+0C00h+var_B88], r15
0x1800160dd  lea     r15d, [r12+4]
0x1800160e2  mov     [rbp+0B00h+lpMem], rax
0x1800160e6  mov     [rsp+0C00h+var_B90], rax
0x1800160eb  mov     dword ptr [rbp+0B00h+var_B78], r12d
0x1800160ef  test    edx, edx
0x1800160f1  jz      short loc_180016166
0x1800160f3  test    qword ptr cs:xmmword_180169738+8, r8
0x1800160fa  jz      short loc_180016166
0x1800160fc  mov     rax, rcx
0x1800160ff  and     rax, r8
0x180016102  cmp     rcx, rax
0x180016105  jnz     short loc_180016166
0x180016107  mov     [rsp+0C00h+var_BB0], r9
0x18001610c  lea     rax, [rsp+0C00h+var_B88]
0x180016111  mov     [rsp+0C00h+var_BB8], rax
0x180016116  lea     rdx, PLA_EVENT_ALLOC
0x18001611d  mov     [rsp+0C00h+var_BC0], r9
0x180016122  lea     rax, [rsp+0C00h+var_B90]
0x180016127  mov     [rsp+0C00h+var_BC8], rax
0x18001612c  lea     r9, byte_180147320
0x180016133  lea     rax, [rbp+0B00h+var_B78]
0x180016137  mov     [rsp+0C00h+var_BD0], r15
0x18001613c  mov     [rsp+0C00h+var_BD8], rax
0x180016141  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180016148  mov     r8d, r15d
0x18001614b  mov     [rsp+0C00h+var_BE0], 1
0x180016154  call    EventingWriteEvent
0x180016159  mov     rcx, cs:qword_180169748
0x180016160  mov     edx, dword ptr cs:xmmword_180169738; unsigned __int64
0x180016166  cmp     [rbp+0B00h+lpMem], r12
0x18001616a  jnz     loc_180016240
0x180016170  mov     dword ptr [rbp+0B00h+var_B78], r12d
0x180016174  mov     eax, 8007000Eh
0x180016179  mov     dword ptr [rsp+0C00h+var_B90], eax
0x18001617d  mov     esi, eax
0x18001617f  test    edx, edx
0x180016181  jz      loc_180016238
0x180016187  mov     rdi, 4000000000000800h
0x180016191  test    qword ptr cs:xmmword_180169738+8, rdi
0x180016198  jz      loc_180016238
0x18001619e  mov     rax, rcx
0x1800161a1  and     rax, rdi
0x1800161a4  cmp     rcx, rax
0x1800161a7  jnz     loc_180016238
0x1800161ad  lea     rcx, [rbp+0B00h+var_AD0]; unsigned __int16 *
0x1800161b1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800161b6  lea     rax, [rbp+0B00h+var_AD0]
0x1800161ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800161be  inc     rbx
0x1800161c1  cmp     [rax+rbx*2], r12w
0x1800161c6  jnz     short loc_1800161BE
0x1800161c8  lea     rax, [rbp+0B00h+var_AD0]
0x1800161cc  lea     ecx, [rbx+rbx]
0x1800161cf  add     rcx, 2
0x1800161d3  lea     r9, byte_180147320
0x1800161da  mov     [rsp+0C00h+var_BA0], rcx
0x1800161df  mov     [rsp+0C00h+var_BA8], rax
0x1800161e4  lea     rax, aValuemapSetxml; "ValueMap::SetXml"
0x1800161eb  mov     [rsp+0C00h+var_BB0], 11h
0x1800161f4  mov     [rsp+0C00h+var_BB8], rax
0x1800161f9  lea     rax, [rbp+0B00h+var_B78]
0x1800161fd  mov     [rsp+0C00h+var_BC0], r15
0x180016202  mov     [rsp+0C00h+var_BC8], rax
0x180016207  mov     [rsp+0C00h+var_BD0], 1
0x180016210  mov     [rsp+0C00h+var_BD8], r9
0x180016215  lea     r9, [rsp+0C00h+var_B90]
0x18001621a  mov     r8d, 5
0x180016220  mov     [rsp+0C00h+var_BE0], r15
0x180016225  lea     rdx, PLA_EVENT_ERROR
0x18001622c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180016233  call    EventingWriteEvent
0x180016238  mov     r14, r12
0x18001623b  jmp     loc_180016EA5
0x180016240  lea     rcx, [rbp+0B00h+pvarg]; pvarg
0x180016244  call    cs:__imp_VariantClear
0x18001624a  lea     rcx, [rbp+0B00h+pvarg]; pvarg
0x18001624e  mov     qword ptr [rbp+0B00h+pvarg+8], r12
0x180016252  call    cs:__imp_VariantClear
0x180016258  mov     edx, 8; unsigned __int16
0x18001625d  mov     qword ptr [rbp+0B00h+pvarg+8], r12
0x180016261  lea     r9, [rbp+0B00h+pvarg]; struct tagVARIANT *
0x180016265  mov     r8, rdi; struct IXMLDOMNode *
0x180016268  lea     rcx, aDescription; "Description"
0x18001626f  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x180016274  test    eax, eax
0x180016276  js      loc_180016378
0x18001627c  mov     rax, [r14]
0x18001627f  mov     rcx, r14
0x180016282  mov     rdx, qword ptr [rbp+0B00h+pvarg+8]
0x180016286  mov     rax, [rax+58h]
0x18001628a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001628f  test    eax, eax
0x180016291  jz      loc_180016378
0x180016297  mov     r9d, eax; int
0x18001629a  lea     r8, aDescription; "Description"
0x1800162a1  mov     rdx, rsi; unsigned __int16 *
0x1800162a4  mov     rcx, rbx; struct IValueMap *
0x1800162a7  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x1800162ac  mov     esi, eax
0x1800162ae  test    eax, eax
0x1800162b0  jns     loc_180016374
0x1800162b6  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800162bd  mov     dword ptr [rsp+0C00h+var_B90], r12d
0x1800162c2  mov     dword ptr [rbp+0B00h+var_B78], eax
0x1800162c5  jz      loc_180016238
0x1800162cb  mov     rdi, 4000000000000800h
0x1800162d5  test    qword ptr cs:xmmword_180169738+8, rdi
0x1800162dc  jz      loc_180016238
0x1800162e2  mov     rax, cs:qword_180169748
0x1800162e9  and     rax, rdi
0x1800162ec  cmp     cs:qword_180169748, rax
0x1800162f3  jnz     loc_180016238
0x1800162f9  lea     rcx, [rbp+0B00h+var_A50]; unsigned __int16 *
0x180016300  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180016305  lea     rax, [rbp+0B00h+var_A50]
0x18001630c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016310  inc     rbx
0x180016313  cmp     [rax+rbx*2], r12w
0x180016318  jnz     short loc_180016310
0x18001631a  lea     rax, [rbp+0B00h+var_A50]
0x180016321  lea     ecx, [rbx+rbx]
0x180016324  add     rcx, 2
0x180016328  lea     r9, byte_180147320
0x18001632f  mov     [rsp+0C00h+var_BA0], rcx
0x180016334  mov     [rsp+0C00h+var_BA8], rax
0x180016339  lea     rax, aValuemapSetxml; "ValueMap::SetXml"
0x180016340  mov     [rsp+0C00h+var_BB0], 11h
0x180016349  mov     [rsp+0C00h+var_BB8], rax
0x18001634e  lea     rax, [rsp+0C00h+var_B90]
0x180016353  mov     [rsp+0C00h+var_BC0], r15
0x180016358  mov     [rsp+0C00h+var_BC8], rax
0x18001635d  mov     [rsp+0C00h+var_BD0], 1
0x180016366  mov     [rsp+0C00h+var_BD8], r9
0x18001636b  lea     r9, [rbp+0B00h+var_B78]
0x18001636f  jmp     loc_18001621A
0x180016374  mov     rsi, [rbp+0B00h+var_B18]
0x180016378  lea     rcx, [rbp+0B00h+pvarg]; pvarg
0x18001637c  call    cs:__imp_VariantClear
0x180016382  mov     edx, 3; unsigned __int16
0x180016387  mov     qword ptr [rbp+0B00h+pvarg+8], r12
0x18001638b  lea     r9, [rbp+0B00h+pvarg]; struct tagVARIANT *
0x18001638f  mov     r8, rdi; struct IXMLDOMNode *
0x180016392  lea     rcx, aValuemaptype; "ValueMapType"
0x180016399  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18001639e  test    eax, eax
0x1800163a0  js      loc_18001644B
0x1800163a6  mov     rax, [r14]
0x1800163a9  mov     rcx, r14
0x1800163ac  mov     edx, dword ptr [rbp+0B00h+pvarg+8]
0x1800163af  mov     rax, [rax+78h]
0x1800163b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163b8  test    eax, eax
0x1800163ba  jz      loc_18001644B
0x1800163c0  mov     r9d, eax; int
0x1800163c3  lea     r8, aValuemaptype; "ValueMapType"
0x1800163ca  mov     rdx, rsi; unsigned __int16 *
0x1800163cd  mov     rcx, rbx; struct IValueMap *
0x1800163d0  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x1800163d5  mov     esi, eax
0x1800163d7  test    eax, eax
0x1800163d9  jns     short loc_18001644B
0x1800163db  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800163e2  mov     dword ptr [rsp+0C00h+var_B90], r12d
0x1800163e7  mov     dword ptr [rbp+0B00h+var_B78], eax
0x1800163ea  jz      loc_180016238
0x1800163f0  mov     rdi, 4000000000000800h
0x1800163fa  test    qword ptr cs:xmmword_180169738+8, rdi
0x180016401  jz      loc_180016238
0x180016407  mov     rax, cs:qword_180169748
0x18001640e  and     rax, rdi
0x180016411  cmp     cs:qword_180169748, rax
0x180016418  jnz     loc_180016238
0x18001641e  lea     rcx, [rbp+0B00h+var_9D0]; unsigned __int16 *
0x180016425  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001642a  lea     rax, [rbp+0B00h+var_9D0]
0x180016431  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016435  inc     rbx
0x180016438  cmp     [rax+rbx*2], r12w
0x18001643d  jnz     short loc_180016435
0x18001643f  lea     rax, [rbp+0B00h+var_9D0]
0x180016446  jmp     loc_180016321
0x18001644b  mov     rax, [r14]
0x18001644e  lea     rdx, [rbp+0B00h+var_B48]
0x180016452  mov     rcx, r14
0x180016455  mov     rax, [rax+70h]
0x180016459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001645e  mov     esi, eax
0x180016460  test    eax, eax
0x180016462  jns     short loc_1800164D4
0x180016464  cmp     dword ptr cs:xmmword_180169738, r12d
0x18001646b  mov     dword ptr [rsp+0C00h+var_B90], r12d
0x180016470  mov     dword ptr [rbp+0B00h+var_B78], eax
0x180016473  jz      loc_180016238
0x180016479  mov     rdi, 4000000000000800h
0x180016483  test    qword ptr cs:xmmword_180169738+8, rdi
0x18001648a  jz      loc_180016238
0x180016490  mov     rax, cs:qword_180169748
0x180016497  and     rax, rdi
0x18001649a  cmp     cs:qword_180169748, rax
0x1800164a1  jnz     loc_180016238
0x1800164a7  lea     rcx, [rbp+0B00h+var_950]; unsigned __int16 *
0x1800164ae  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800164b3  lea     rax, [rbp+0B00h+var_950]
0x1800164ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800164be  inc     rbx
0x1800164c1  cmp     [rax+rbx*2], r12w
0x1800164c6  jnz     short loc_1800164BE
0x1800164c8  lea     rax, [rbp+0B00h+var_950]
0x1800164cf  jmp     loc_180016321
0x1800164d4  mov     rax, [rdi]
0x1800164d7  lea     rcx, [rbp+0B00h+bstrString]
0x1800164db  mov     rbx, [rax+138h]
0x1800164e2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800164e7  mov     rdx, rax
0x1800164ea  mov     rcx, rdi
0x1800164ed  mov     rax, rbx
0x1800164f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f5  cmp     eax, 1
0x1800164f8  jz      short loc_180016501
0x1800164fa  mov     edx, eax
0x1800164fc  call    MicrosoftTelemetryAssertTriggeredArgs
0x180016501  xor     ecx, ecx; bstrString
0x180016503  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180016508  lea     rcx, psz; "ValueMapItem"
0x18001650f  call    cs:__imp_SysAllocString
0x180016515  mov     rbx, rax
0x180016518  test    rax, rax
0x18001651b  jz      loc_1800173E6
0x180016521  cmp     dword ptr cs:xmmword_180169738, r12d
0x180016528  jz      loc_1800165F1
0x18001652e  mov     rsi, 4000000000000200h
0x180016538  test    qword ptr cs:xmmword_180169738+8, rsi
0x18001653f  jz      loc_1800165F1
0x180016545  mov     rcx, cs:qword_180169748
0x18001654c  and     rcx, rsi
0x18001654f  cmp     cs:qword_180169748, rcx
0x180016556  jnz     loc_1800165F1
0x18001655c  mov     rcx, rax; bstr
0x18001655f  call    cs:__imp_SysStringByteLen
0x180016565  cmp     dword ptr cs:xmmword_180169738, r12d
0x18001656c  mov     eax, eax
0x18001656e  mov     [rsp+0C00h+var_B88], rax
0x180016573  mov     [rbp+0B00h+var_B78], rbx
0x180016577  mov     dword ptr [rsp+0C00h+var_B90], r12d
0x18001657c  jz      short loc_1800165F1
0x18001657e  test    qword ptr cs:xmmword_180169738+8, rsi
0x180016585  jz      short loc_1800165F1
0x180016587  mov     rax, cs:qword_180169748
0x18001658e  and     rax, rsi
0x180016591  cmp     cs:qword_180169748, rax
0x180016598  jnz     short loc_1800165F1
0x18001659a  mov     ecx, 8
0x18001659f  lea     rax, [rsp+0C00h+var_B88]
0x1800165a4  mov     [rsp+0C00h+var_BB0], rcx
  ... truncated ...
```
