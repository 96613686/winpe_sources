# TraceDataProvider::GetXml(ITraceDataProvider *,IXMLDOMDocument *,IXMLDOMNode *)

- ea: `0x1800c0a88`
- end: `0x1800c1874`
- name: `?GetXml@TraceDataProvider@@SAJPEAUITraceDataProvider@@PEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@@Z`
- size: `3564`
- prototype: `static int(struct ITraceDataProvider *, struct IXMLDOMDocument *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800701e8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x180024ea0`
- `0x180026850`
- `0x18003bb54`
- `0x180041528`
- `0x180088b5c`
- `0x180098730`
- `0x1800a9bac`
- `0x1800c0a88`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c1817`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c1817`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c15d9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c15d9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1804`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1804`

## string_xrefs

- `0x1800c17ac`: `TraceDataProvider::GetXml`

## pseudocode

```c
__int64 __fastcall TraceDataProvider::GetXml(
        struct ITraceDataProvider *a1,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3)
{
  int Node; // eax
  struct IXMLDOMNode *v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rax
  struct IXMLDOMNode **v10; // r9
  struct IXMLDOMNode **v11; // rcx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int Xml; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  HRESULT v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rax
  int v54; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMNode *v55; // [rsp+78h] [rbp-88h] BYREF
  struct IValueMap *v56; // [rsp+80h] [rbp-80h] BYREF
  SAFEARRAY *psa; // [rsp+88h] [rbp-78h] BYREF
  struct tagVARIANT v58; // [rsp+90h] [rbp-70h] BYREF
  void *ppvData; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v60; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v61[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v62[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v63[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v64[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v65[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v66[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v67[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v68[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v69[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v70[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v71[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v72[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v73[64]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v74[64]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v75[64]; // [rsp+7C0h] [rbp+6C0h] BYREF
  unsigned __int16 v76[64]; // [rsp+840h] [rbp+740h] BYREF
  unsigned __int16 v77[64]; // [rsp+8C0h] [rbp+7C0h] BYREF
  unsigned __int16 v78[64]; // [rsp+940h] [rbp+840h] BYREF
  unsigned __int16 v79[64]; // [rsp+9C0h] [rbp+8C0h] BYREF
  unsigned __int16 v80[64]; // [rsp+A40h] [rbp+940h] BYREF
  unsigned __int16 v81[64]; // [rsp+AC0h] [rbp+9C0h] BYREF

  psa = 0;
  ppvData = 0;
  v55 = 0;
  v60 = 0;
  v56 = 0;
  memset(&v58, 0, sizeof(v58));
  PlaiVariantInit(&v58);
  Node = PlaiCreateNode(L"TraceDataProvider", a2, a3, (struct IXMLDOMElement **)&v55);
  v7 = v55;
  v8 = Node;
  if ( Node >= 0 )
  {
    PlaiVariantClear(&v58);
    v12 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, ULONG *))a1->lpVtbl->get_DisplayName)(
            a1,
            &v58.decVal.Lo32);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v58.vt = 8;
      if ( v12 == 3145984 || (v14 = PlaiWriteXmlElement(L"DisplayName", a2, v7, &v58), v8 = v14, v14 >= 0) )
      {
        PlaiVariantClear(&v58);
        v16 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, ULONG *))a1->lpVtbl->get_FilterEnabled)(
                a1,
                &v58.decVal.Lo32);
        v8 = v16;
        if ( v16 >= 0 )
        {
          v58.vt = 11;
          if ( v16 == 3145984 || (v18 = PlaiWriteXmlElement(L"FilterEnabled", a2, v7, &v58), v8 = v18, v18 >= 0) )
          {
            PlaiVariantClear(&v58);
            v20 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, ULONG *))a1->lpVtbl->get_FilterType)(
                    a1,
                    &v58.decVal.Lo32);
            v8 = v20;
            if ( v20 >= 0 )
            {
              v58.vt = 19;
              if ( v20 == 3145984 || (v22 = PlaiWriteXmlElement(L"FilterType", a2, v7, &v58), v8 = v22, v22 >= 0) )
              {
                if ( v56 )
                {
                  ((void (__fastcall *)(struct IValueMap *))v56->lpVtbl->Release)(v56);
                  v56 = 0;
                }
                v24 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_Level)(
                        a1,
                        &v56);
                v8 = v24;
                if ( v24 >= 0 )
                {
                  Xml = ValueMap::GetXml(v56, L"Level", a2, v7);
                  v8 = Xml;
                  if ( Xml >= 0 )
                  {
                    if ( v56 )
                    {
                      ((void (__fastcall *)(struct IValueMap *))v56->lpVtbl->Release)(v56);
                      v56 = 0;
                    }
                    v28 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_KeywordsAny)(
                            a1,
                            &v56);
                    v8 = v28;
                    if ( v28 >= 0 )
                    {
                      v30 = ValueMap::GetXml(v56, L"KeywordsAny", a2, v7);
                      v8 = v30;
                      if ( v30 >= 0 )
                      {
                        if ( v56 )
                        {
                          ((void (__fastcall *)(struct IValueMap *))v56->lpVtbl->Release)(v56);
                          v56 = 0;
                        }
                        v32 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_KeywordsAll)(
                                a1,
                                &v56);
                        v8 = v32;
                        if ( v32 >= 0 )
                        {
                          v34 = ValueMap::GetXml(v56, L"KeywordsAll", a2, v7);
                          v8 = v34;
                          if ( v34 >= 0 )
                          {
                            if ( v56 )
                            {
                              ((void (__fastcall *)(struct IValueMap *))v56->lpVtbl->Release)(v56);
                              v56 = 0;
                            }
                            v36 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_Properties)(
                                    a1,
                                    &v56);
                            v8 = v36;
                            if ( v36 >= 0 )
                            {
                              v38 = ValueMap::GetXml(v56, L"Properties", a2, v7);
                              v8 = v38;
                              if ( v38 >= 0 )
                              {
                                v40 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct _GUID *))a1->lpVtbl->get_Guid)(
                                        a1,
                                        &v60);
                                v8 = v40;
                                if ( v40 >= 0 )
                                {
                                  v43 = PlaiWriteXmlGuid(v41, a2, v7, &v60);
                                  v8 = v43;
                                  if ( v43 >= 0 )
                                  {
                                    v45 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, SAFEARRAY **))a1->lpVtbl->get_FilterData)(
                                            a1,
                                            &psa);
                                    v8 = v45;
                                    if ( v45 >= 0 )
                                    {
                                      if ( !psa || !psa->cDims || !psa->rgsabound[0].cElements )
                                        goto LABEL_163;
                                      v47 = SafeArrayAccessData(psa, &ppvData);
                                      v8 = v47;
                                      if ( v47 >= 0 )
                                      {
                                        PlaiVariantClear(&v58);
                                        v49 = PlaiBase64Encode(
                                                (unsigned __int8 *)ppvData,
                                                psa->rgsabound[0].cElements,
                                                &v58.bstrVal);
                                        v8 = v49;
                                        if ( v49 >= 0 )
                                        {
                                          v58.vt = 8;
                                          v51 = PlaiWriteXmlElement(L"FilterData", a2, v7, &v58);
                                          v8 = v51;
                                          if ( v51 >= 0 )
                                            goto LABEL_163;
                                          LODWORD(v55) = 0;
                                          v54 = v51;
                                          if ( !(_DWORD)xmmword_180169738
                                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                          {
                                            goto LABEL_163;
                                          }
                                          PlaiWhoAmI(v81, 0x4000000000000800uLL);
                                          v52 = -1;
                                          do
                                            ++v52;
                                          while ( v81[v52] );
                                        }
                                        else
                                        {
                                          LODWORD(v55) = 0;
                                          v54 = v49;
                                          if ( !(_DWORD)xmmword_180169738
                                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                          {
                                            goto LABEL_163;
                                          }
                                          PlaiWhoAmI(v80, 0x4000000000000800uLL);
                                          v50 = -1;
                                          do
                                            ++v50;
                                          while ( v80[v50] );
                                        }
                                      }
                                      else
                                      {
                                        LODWORD(v55) = 0;
                                        v54 = v47;
                                        if ( !(_DWORD)xmmword_180169738
                                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          goto LABEL_163;
                                        }
                                        PlaiWhoAmI(v79, 0x4000000000000800uLL);
                                        v48 = -1;
                                        do
                                          ++v48;
                                        while ( v79[v48] );
                                      }
                                    }
                                    else
                                    {
                                      LODWORD(v55) = 0;
                                      v54 = v45;
                                      if ( !(_DWORD)xmmword_180169738
                                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                      {
                                        goto LABEL_163;
                                      }
                                      PlaiWhoAmI(v78, 0x4000000000000800uLL);
                                      v46 = -1;
                                      do
                                        ++v46;
                                      while ( v78[v46] );
                                    }
                                  }
                                  else
                                  {
                                    LODWORD(v55) = 0;
                                    v54 = v43;
                                    if ( !(_DWORD)xmmword_180169738
                                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                    {
                                      goto LABEL_163;
                                    }
                                    PlaiWhoAmI(v77, 0x4000000000000800uLL);
                                    v44 = -1;
                                    do
                                      ++v44;
                                    while ( v77[v44] );
                                  }
                                }
                                else
                                {
                                  LODWORD(v55) = 0;
                                  v54 = v40;
                                  if ( !(_DWORD)xmmword_180169738
                                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                  {
                                    goto LABEL_163;
                                  }
                                  PlaiWhoAmI(v76, 0x4000000000000800uLL);
                                  v42 = -1;
                                  do
                                    ++v42;
                                  while ( v76[v42] );
                                }
                              }
                              else
                              {
                                LODWORD(v55) = 0;
                                v54 = v38;
                                if ( !(_DWORD)xmmword_180169738
                                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  goto LABEL_163;
                                }
                                PlaiWhoAmI(v75, 0x4000000000000800uLL);
                                v39 = -1;
                                do
                                  ++v39;
                                while ( v75[v39] );
                              }
                            }
                            else
                            {
                              LODWORD(v55) = 0;
                              v54 = v36;
                              if ( !(_DWORD)xmmword_180169738
                                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                              {
                                goto LABEL_163;
                              }
                              PlaiWhoAmI(v74, 0x4000000000000800uLL);
                              v37 = -1;
                              do
                                ++v37;
                              while ( v74[v37] );
                            }
                          }
                          else
                          {
                            LODWORD(v55) = 0;
                            v54 = v34;
                            if ( !(_DWORD)xmmword_180169738
                              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                            {
                              goto LABEL_163;
                            }
                            PlaiWhoAmI(v73, 0x4000000000000800uLL);
                            v35 = -1;
                            do
                              ++v35;
                            while ( v73[v35] );
                          }
                        }
                        else
                        {
                          LODWORD(v55) = 0;
                          v54 = v32;
                          if ( !(_DWORD)xmmword_180169738
                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                          {
                            goto LABEL_163;
                          }
                          PlaiWhoAmI(v72, 0x4000000000000800uLL);
                          v33 = -1;
                          do
                            ++v33;
                          while ( v72[v33] );
                        }
                      }
                      else
                      {
                        LODWORD(v55) = 0;
                        v54 = v30;
                        if ( !(_DWORD)xmmword_180169738
                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                        {
                          goto LABEL_163;
                        }
                        PlaiWhoAmI(v71, 0x4000000000000800uLL);
                        v31 = -1;
                        do
                          ++v31;
                        while ( v71[v31] );
                      }
                    }
                    else
                    {
                      LODWORD(v55) = 0;
                      v54 = v28;
                      if ( !(_DWORD)xmmword_180169738
                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                      {
                        goto LABEL_163;
                      }
                      PlaiWhoAmI(v70, 0x4000000000000800uLL);
                      v29 = -1;
                      do
                        ++v29;
                      while ( v70[v29] );
                    }
                  }
                  else
                  {
                    LODWORD(v55) = 0;
                    v54 = Xml;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_163;
                    }
                    PlaiWhoAmI(v69, 0x4000000000000800uLL);
                    v27 = -1;
                    do
                      ++v27;
                    while ( v69[v27] );
                  }
                }
                else
                {
                  LODWORD(v55) = 0;
                  v54 = v24;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_163;
                  }
                  PlaiWhoAmI(v68, 0x4000000000000800uLL);
                  v25 = -1;
                  do
                    ++v25;
                  while ( v68[v25] );
                }
              }
              else
              {
                LODWORD(v55) = 0;
                v54 = v22;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_163;
                }
                PlaiWhoAmI(v67, 0x4000000000000800uLL);
                v23 = -1;
                do
                  ++v23;
                while ( v67[v23] );
              }
            }
            else
            {
              LODWORD(v55) = 0;
              v54 = v20;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_163;
              }
              PlaiWhoAmI(v66, 0x4000000000000800uLL);
              v21 = -1;
              do
                ++v21;
              while ( v66[v21] );
            }
          }
          else
          {
            LODWORD(v55) = 0;
            v54 = v18;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_163;
            }
            PlaiWhoAmI(v65, 0x4000000000000800uLL);
            v19 = -1;
            do
              ++v19;
            while ( v65[v19] );
          }
        }
        else
        {
          LODWORD(v55) = 0;
          v54 = v16;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_163;
          }
          PlaiWhoAmI(v64, 0x4000000000000800uLL);
          v17 = -1;
          do
            ++v17;
          while ( v64[v17] );
        }
      }
      else
      {
        LODWORD(v55) = 0;
        v54 = v14;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_163;
        }
        PlaiWhoAmI(v63, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v63[v15] );
      }
    }
    else
    {
      LODWORD(v55) = 0;
      v54 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_163;
      }
      PlaiWhoAmI(v62, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v62[v13] );
    }
    v10 = (struct IXMLDOMNode **)&v54;
    v11 = &v55;
LABEL_162:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v10, 4, byte_180147320, 1, v11, 4);
    goto LABEL_163;
  }
  v54 = 0;
  LODWORD(v55) = Node;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v61[v9] );
    v10 = &v55;
    v11 = (struct IXMLDOMNode **)&v54;
    goto LABEL_162;
  }
LABEL_163:
  PlaiVariantClear(&v58);
  if ( ppvData )
  {
    SafeArrayUnaccessData(psa);
    ppvData = 0;
  }
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  PlaiFreeString(0);
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  if ( v56 )
    ((void (__fastcall *)(struct IValueMap *))v56->lpVtbl->Release)(v56);
  return v8;
}

```

## disassembly

```asm
0x1800c0a88  push    rbp
0x1800c0a8a  push    rbx
0x1800c0a8b  push    rsi
0x1800c0a8c  push    rdi
0x1800c0a8d  push    r13
0x1800c0a8f  push    r14
0x1800c0a91  push    r15
0x1800c0a93  lea     rbp, [rsp-0A50h]
0x1800c0a9b  sub     rsp, 0B50h
0x1800c0aa2  mov     rax, cs:__security_cookie
0x1800c0aa9  xor     rax, rsp
0x1800c0aac  mov     [rbp+0A80h+var_40], rax
0x1800c0ab3  xor     r15d, r15d
0x1800c0ab6  xorps   xmm0, xmm0
0x1800c0ab9  mov     rdi, rcx
0x1800c0abc  mov     [rbp+0A80h+psa], r15
0x1800c0ac0  xor     eax, eax
0x1800c0ac2  mov     [rbp+0A80h+ppvData], r15
0x1800c0ac6  lea     rcx, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0aca  mov     [rsp+0B80h+var_B08], r15
0x1800c0acf  movups  xmmword ptr [rbp+0A80h+var_AD0.Data1], xmm0
0x1800c0ad3  mov     [rbp+0A80h+var_B00], r15
0x1800c0ad7  mov     rbx, r8
0x1800c0ada  movups  xmmword ptr [rbp+0A80h+var_AF0], xmm0
0x1800c0ade  mov     qword ptr [rbp+0A80h+var_AF0+10h], rax
0x1800c0ae2  mov     rsi, rdx
0x1800c0ae5  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800c0aea  lea     r9, [rsp+0B80h+var_B08]; struct IXMLDOMElement **
0x1800c0aef  mov     r8, rbx; struct IXMLDOMNode *
0x1800c0af2  mov     rdx, rsi; struct IXMLDOMDocument *
0x1800c0af5  lea     rcx, aTracedataprovi_12; "TraceDataProvider"
0x1800c0afc  call    ?PlaiCreateNode@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMElement@@@Z; PlaiCreateNode(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,IXMLDOMElement * *)
0x1800c0b01  mov     r14, [rsp+0B80h+var_B08]
0x1800c0b06  mov     ebx, eax
0x1800c0b08  test    eax, eax
0x1800c0b0a  jns     short loc_1800C0B8A
0x1800c0b0c  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0b13  mov     [rsp+0B80h+var_B10], r15d
0x1800c0b18  mov     dword ptr [rsp+0B80h+var_B08], eax
0x1800c0b1c  jz      loc_1800C17F1
0x1800c0b22  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0b2c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0b33  jz      loc_1800C17F1
0x1800c0b39  mov     rax, cs:qword_180169748
0x1800c0b40  and     rax, rdx
0x1800c0b43  cmp     cs:qword_180169748, rax
0x1800c0b4a  jnz     loc_1800C17F1
0x1800c0b50  lea     rcx, [rbp+0A80h+var_AC0]; unsigned __int16 *
0x1800c0b54  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0b59  lea     rcx, [rbp+0A80h+var_AC0]
0x1800c0b5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0b61  inc     rax
0x1800c0b64  cmp     [rcx+rax*2], r15w
0x1800c0b69  jnz     short loc_1800C0B61
0x1800c0b6b  lea     ecx, [rax+rax]
0x1800c0b6e  add     rcx, 2
0x1800c0b72  lea     rax, [rbp+0A80h+var_AC0]
0x1800c0b76  mov     [rsp+0B80h+var_B20], rcx
0x1800c0b7b  lea     r9, [rsp+0B80h+var_B08]
0x1800c0b80  lea     rcx, [rsp+0B80h+var_B10]
0x1800c0b85  jmp     loc_1800C1797
0x1800c0b8a  lea     rcx, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0b8e  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c0b93  mov     rax, [rdi]
0x1800c0b96  lea     rdx, [rbp+0A80h+var_AF0+8]
0x1800c0b9a  mov     rcx, rdi
0x1800c0b9d  mov     rax, [rax+38h]
0x1800c0ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0ba6  mov     ebx, eax
0x1800c0ba8  test    eax, eax
0x1800c0baa  jns     short loc_1800C0C17
0x1800c0bac  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0bb3  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0bb8  mov     [rsp+0B80h+var_B10], eax
0x1800c0bbc  jz      loc_1800C17F1
0x1800c0bc2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0bcc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0bd3  jz      loc_1800C17F1
0x1800c0bd9  mov     rax, cs:qword_180169748
0x1800c0be0  and     rax, rdx
0x1800c0be3  cmp     cs:qword_180169748, rax
0x1800c0bea  jnz     loc_1800C17F1
0x1800c0bf0  lea     rcx, [rbp+0A80h+var_A40]; unsigned __int16 *
0x1800c0bf4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0bf9  lea     rcx, [rbp+0A80h+var_A40]
0x1800c0bfd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0c01  inc     rax
0x1800c0c04  cmp     [rcx+rax*2], r15w
0x1800c0c09  jnz     short loc_1800C0C01
0x1800c0c0b  lea     ecx, [rax+rax]
0x1800c0c0e  lea     rax, [rbp+0A80h+var_A40]
0x1800c0c12  jmp     loc_1800C1784
0x1800c0c17  mov     r13d, 8
0x1800c0c1d  mov     word ptr [rbp+0A80h+var_AF0], r13w
0x1800c0c22  cmp     eax, 300100h
0x1800c0c27  jz      loc_1800C0CBD
0x1800c0c2d  lea     r9, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0c31  mov     r8, r14; struct IXMLDOMNode *
0x1800c0c34  mov     rdx, rsi; struct IXMLDOMDocument *
0x1800c0c37  lea     rcx, aDisplayname; "DisplayName"
0x1800c0c3e  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c0c43  mov     ebx, eax
0x1800c0c45  test    eax, eax
0x1800c0c47  jns     short loc_1800C0CBD
0x1800c0c49  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0c50  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0c55  mov     [rsp+0B80h+var_B10], eax
0x1800c0c59  jz      loc_1800C17F1
0x1800c0c5f  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0c69  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0c70  jz      loc_1800C17F1
0x1800c0c76  mov     rax, cs:qword_180169748
0x1800c0c7d  and     rax, rdx
0x1800c0c80  cmp     cs:qword_180169748, rax
0x1800c0c87  jnz     loc_1800C17F1
0x1800c0c8d  lea     rcx, [rbp+0A80h+var_9C0]; unsigned __int16 *
0x1800c0c94  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0c99  lea     rcx, [rbp+0A80h+var_9C0]
0x1800c0ca0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0ca4  inc     rax
0x1800c0ca7  cmp     [rcx+rax*2], r15w
0x1800c0cac  jnz     short loc_1800C0CA4
0x1800c0cae  lea     ecx, [rax+rax]
0x1800c0cb1  lea     rax, [rbp+0A80h+var_9C0]
0x1800c0cb8  jmp     loc_1800C1784
0x1800c0cbd  lea     rcx, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0cc1  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c0cc6  mov     rax, [rdi]
0x1800c0cc9  lea     rdx, [rbp+0A80h+var_AF0+8]
0x1800c0ccd  mov     rcx, rdi
0x1800c0cd0  mov     rax, [rax+78h]
0x1800c0cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0cd9  mov     ebx, eax
0x1800c0cdb  test    eax, eax
0x1800c0cdd  jns     short loc_1800C0D53
0x1800c0cdf  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0ce6  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0ceb  mov     [rsp+0B80h+var_B10], eax
0x1800c0cef  jz      loc_1800C17F1
0x1800c0cf5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0cff  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0d06  jz      loc_1800C17F1
0x1800c0d0c  mov     rax, cs:qword_180169748
0x1800c0d13  and     rax, rdx
0x1800c0d16  cmp     cs:qword_180169748, rax
0x1800c0d1d  jnz     loc_1800C17F1
0x1800c0d23  lea     rcx, [rbp+0A80h+var_940]; unsigned __int16 *
0x1800c0d2a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0d2f  lea     rcx, [rbp+0A80h+var_940]
0x1800c0d36  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0d3a  inc     rax
0x1800c0d3d  cmp     [rcx+rax*2], r15w
0x1800c0d42  jnz     short loc_1800C0D3A
0x1800c0d44  lea     ecx, [rax+rax]
0x1800c0d47  lea     rax, [rbp+0A80h+var_940]
0x1800c0d4e  jmp     loc_1800C1784
0x1800c0d53  mov     eax, 0Bh
0x1800c0d58  mov     word ptr [rbp+0A80h+var_AF0], ax
0x1800c0d5c  cmp     ebx, 300100h
0x1800c0d62  jz      loc_1800C0DF8
0x1800c0d68  lea     r9, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0d6c  mov     r8, r14; struct IXMLDOMNode *
0x1800c0d6f  mov     rdx, rsi; struct IXMLDOMDocument *
0x1800c0d72  lea     rcx, aFilterenabled; "FilterEnabled"
0x1800c0d79  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c0d7e  mov     ebx, eax
0x1800c0d80  test    eax, eax
0x1800c0d82  jns     short loc_1800C0DF8
0x1800c0d84  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0d8b  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0d90  mov     [rsp+0B80h+var_B10], eax
0x1800c0d94  jz      loc_1800C17F1
0x1800c0d9a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0da4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0dab  jz      loc_1800C17F1
0x1800c0db1  mov     rax, cs:qword_180169748
0x1800c0db8  and     rax, rdx
0x1800c0dbb  cmp     cs:qword_180169748, rax
0x1800c0dc2  jnz     loc_1800C17F1
0x1800c0dc8  lea     rcx, [rbp+0A80h+var_8C0]; unsigned __int16 *
0x1800c0dcf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0dd4  lea     rcx, [rbp+0A80h+var_8C0]
0x1800c0ddb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0ddf  inc     rax
0x1800c0de2  cmp     [rcx+rax*2], r15w
0x1800c0de7  jnz     short loc_1800C0DDF
0x1800c0de9  lea     ecx, [rax+rax]
0x1800c0dec  lea     rax, [rbp+0A80h+var_8C0]
0x1800c0df3  jmp     loc_1800C1784
0x1800c0df8  lea     rcx, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0dfc  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c0e01  mov     rax, [rdi]
0x1800c0e04  lea     rdx, [rbp+0A80h+var_AF0+8]
0x1800c0e08  mov     rcx, rdi
0x1800c0e0b  mov     rax, [rax+88h]
0x1800c0e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0e17  mov     ebx, eax
0x1800c0e19  test    eax, eax
0x1800c0e1b  jns     short loc_1800C0E91
0x1800c0e1d  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0e24  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0e29  mov     [rsp+0B80h+var_B10], eax
0x1800c0e2d  jz      loc_1800C17F1
0x1800c0e33  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0e3d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0e44  jz      loc_1800C17F1
0x1800c0e4a  mov     rax, cs:qword_180169748
0x1800c0e51  and     rax, rdx
0x1800c0e54  cmp     cs:qword_180169748, rax
0x1800c0e5b  jnz     loc_1800C17F1
0x1800c0e61  lea     rcx, [rbp+0A80h+var_840]; unsigned __int16 *
0x1800c0e68  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0e6d  lea     rcx, [rbp+0A80h+var_840]
0x1800c0e74  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0e78  inc     rax
0x1800c0e7b  cmp     [rcx+rax*2], r15w
0x1800c0e80  jnz     short loc_1800C0E78
0x1800c0e82  lea     ecx, [rax+rax]
0x1800c0e85  lea     rax, [rbp+0A80h+var_840]
0x1800c0e8c  jmp     loc_1800C1784
0x1800c0e91  mov     eax, 13h
0x1800c0e96  mov     word ptr [rbp+0A80h+var_AF0], ax
0x1800c0e9a  cmp     ebx, 300100h
0x1800c0ea0  jz      loc_1800C0F36
0x1800c0ea6  lea     r9, [rbp+0A80h+var_AF0]; struct tagVARIANT *
0x1800c0eaa  mov     r8, r14; struct IXMLDOMNode *
0x1800c0ead  mov     rdx, rsi; struct IXMLDOMDocument *
0x1800c0eb0  lea     rcx, aFiltertype; "FilterType"
0x1800c0eb7  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c0ebc  mov     ebx, eax
0x1800c0ebe  test    eax, eax
0x1800c0ec0  jns     short loc_1800C0F36
0x1800c0ec2  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0ec9  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0ece  mov     [rsp+0B80h+var_B10], eax
0x1800c0ed2  jz      loc_1800C17F1
0x1800c0ed8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0ee2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0ee9  jz      loc_1800C17F1
0x1800c0eef  mov     rax, cs:qword_180169748
0x1800c0ef6  and     rax, rdx
0x1800c0ef9  cmp     cs:qword_180169748, rax
0x1800c0f00  jnz     loc_1800C17F1
0x1800c0f06  lea     rcx, [rbp+0A80h+var_7C0]; unsigned __int16 *
0x1800c0f0d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0f12  lea     rcx, [rbp+0A80h+var_7C0]
0x1800c0f19  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0f1d  inc     rax
0x1800c0f20  cmp     [rcx+rax*2], r15w
0x1800c0f25  jnz     short loc_1800C0F1D
0x1800c0f27  lea     ecx, [rax+rax]
0x1800c0f2a  lea     rax, [rbp+0A80h+var_7C0]
0x1800c0f31  jmp     loc_1800C1784
0x1800c0f36  mov     rcx, [rbp+0A80h+var_B00]
0x1800c0f3a  test    rcx, rcx
0x1800c0f3d  jz      short loc_1800C0F4F
0x1800c0f3f  mov     rax, [rcx]
0x1800c0f42  mov     rax, [rax+10h]
0x1800c0f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0f4b  mov     [rbp+0A80h+var_B00], r15
0x1800c0f4f  mov     rax, [rdi]
0x1800c0f52  lea     rdx, [rbp+0A80h+var_B00]
0x1800c0f56  mov     rcx, rdi
0x1800c0f59  mov     rax, [rax+58h]
0x1800c0f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0f62  mov     ebx, eax
0x1800c0f64  test    eax, eax
0x1800c0f66  jns     short loc_1800C0FDC
0x1800c0f68  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0f6f  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c0f74  mov     [rsp+0B80h+var_B10], eax
0x1800c0f78  jz      loc_1800C17F1
0x1800c0f7e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c0f88  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c0f8f  jz      loc_1800C17F1
0x1800c0f95  mov     rax, cs:qword_180169748
0x1800c0f9c  and     rax, rdx
0x1800c0f9f  cmp     cs:qword_180169748, rax
0x1800c0fa6  jnz     loc_1800C17F1
0x1800c0fac  lea     rcx, [rbp+0A80h+var_740]; unsigned __int16 *
0x1800c0fb3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c0fb8  lea     rcx, [rbp+0A80h+var_740]
0x1800c0fbf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0fc3  inc     rax
0x1800c0fc6  cmp     [rcx+rax*2], r15w
0x1800c0fcb  jnz     short loc_1800C0FC3
0x1800c0fcd  lea     ecx, [rax+rax]
0x1800c0fd0  lea     rax, [rbp+0A80h+var_740]
0x1800c0fd7  jmp     loc_1800C1784
0x1800c0fdc  mov     rcx, [rbp+0A80h+var_B00]; struct IValueMap *
0x1800c0fe0  lea     rdx, aLevel_0; "Level"
0x1800c0fe7  mov     r9, r14; struct IXMLDOMNode *
0x1800c0fea  mov     r8, rsi; struct IXMLDOMDocument *
0x1800c0fed  call    ?GetXml@ValueMap@@SAJPEAUIValueMap@@PEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@@Z; ValueMap::GetXml(IValueMap *,ushort const *,IXMLDOMDocument *,IXMLDOMNode *)
0x1800c0ff2  mov     ebx, eax
0x1800c0ff4  test    eax, eax
0x1800c0ff6  jns     short loc_1800C106C
0x1800c0ff8  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800c0fff  mov     dword ptr [rsp+0B80h+var_B08], r15d
0x1800c1004  mov     [rsp+0B80h+var_B10], eax
  ... truncated ...
```
