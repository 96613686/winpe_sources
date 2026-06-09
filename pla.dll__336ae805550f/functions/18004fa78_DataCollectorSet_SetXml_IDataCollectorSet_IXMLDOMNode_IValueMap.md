# DataCollectorSet::SetXml(IDataCollectorSet *,IXMLDOMNode *,IValueMap *)

- ea: `0x18004fa78`
- end: `0x180051357`
- name: `?SetXml@DataCollectorSet@@SAJPEAUIDataCollectorSet@@PEAUIXMLDOMNode@@PEAUIValueMap@@@Z`
- size: `6367`
- prototype: `static int(struct IDataCollectorSet *, struct IXMLDOMNode *, struct IValueMap *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040040`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800133cc`
- `0x1800157bc`
- `0x1800174c0`
- `0x180018420`
- `0x1800198b0`
- `0x180026850`
- `0x18003f818`
- `0x180040840`
- `0x18004fa78`
- `0x18005179c`
- `0x180087a88`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180051325`
- `OLEAUT32!__imp_SysFreeString` at `0x180051325`
- `OLEAUT32!__imp_VariantInit` at `0x18004fae7`
- `OLEAUT32!__imp_VariantInit` at `0x18004faf5`
- `OLEAUT32!__imp_VariantInit` at `0x18004fae7`
- `OLEAUT32!__imp_VariantInit` at `0x18004faf5`
- `OLEAUT32!__imp_VariantClear` at `0x18004fb03`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc14`
- `OLEAUT32!__imp_VariantClear` at `0x18004fcf3`
- `OLEAUT32!__imp_VariantClear` at `0x18004fdc8`
- `OLEAUT32!__imp_VariantClear` at `0x18004fe9d`
- `OLEAUT32!__imp_VariantClear` at `0x180051304`
- `OLEAUT32!__imp_VariantClear` at `0x180051312`
- `OLEAUT32!__imp_VariantClear` at `0x18004fb03`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc14`
- `OLEAUT32!__imp_VariantClear` at `0x18004fcf3`
- `OLEAUT32!__imp_VariantClear` at `0x18004fdc8`
- `OLEAUT32!__imp_VariantClear` at `0x18004fe9d`
- `OLEAUT32!__imp_VariantClear` at `0x180051304`
- `OLEAUT32!__imp_VariantClear` at `0x180051312`

## string_xrefs

- `0x18004fbbb`: `DataCollectorSet::SetXml`
- `0x1800506f2`: `Subdirectory`
- `0x180050727`: `Subdirectory`
- `0x1800507c7`: `SubdirectoryFormat`
- `0x1800507fb`: `SubdirectoryFormat`
- `0x180050899`: `SubdirectoryFormatPattern`
- `0x1800508ce`: `SubdirectoryFormatPattern`
- `0x1800502ce`: `RootPath`
- `0x180050303`: `RootPath`
- `0x180050a41`: `TaskRunAsSelf`
- `0x180050a76`: `TaskRunAsSelf`
- `0x180050b14`: `TaskArguments`
- `0x180050b49`: `TaskArguments`
- `0x180050be7`: `TaskUserTextArguments`
- `0x180050c1c`: `TaskUserTextArguments`
- `0x180050cba`: `Security`
- `0x180050cef`: `Security`
- `0x180050d8f`: `StopOnCompletion`
- `0x180050dc4`: `StopOnCompletion`

## pseudocode

```c
__int64 __fastcall DataCollectorSet::SetXml(struct IDataCollectorSet *a1, struct IXMLDOMNode *a2, struct IValueMap *a3)
{
  OLECHAR *v4; // r15
  struct IDataCollectorSetVtbl *lpVtbl; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  int *v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  int v53; // eax
  __int64 v54; // rax
  int v55; // eax
  int v56; // eax
  __int64 v57; // rax
  int v58; // eax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  int v62; // eax
  __int64 v63; // rax
  int v64; // eax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  int v68; // eax
  __int64 v69; // rax
  int v70; // eax
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  int v74; // eax
  __int64 v75; // rax
  int v76; // eax
  int v77; // eax
  __int64 v78; // rax
  int v79; // eax
  __int64 v80; // rax
  int v81; // eax
  __int64 v82; // rax
  int v83; // eax
  const unsigned __int16 *v84; // r9
  __int64 v85; // rax
  int v86; // eax
  __int64 v87; // rax
  HRESULT (__stdcall *get_namespaceURI)(IXMLDOMNode *, BSTR *); // rbx
  __int64 v89; // rax
  unsigned int v90; // eax
  __int64 v91; // rcx
  const char *v92; // rdx
  int v93; // r8d
  unsigned __int16 *v94; // rax
  __int64 v95; // rax
  int v96; // eax
  __int64 v97; // rax
  int v98; // eax
  __int64 v99; // rax
  int v101; // [rsp+70h] [rbp-90h] BYREF
  int v102; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v104; // [rsp+98h] [rbp-68h] BYREF
  struct IDataManager *v105; // [rsp+A0h] [rbp-60h] BYREF
  struct IDataCollectorCollection *v106; // [rsp+A8h] [rbp-58h] BYREF
  struct IScheduleCollection *v107; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v108; // [rsp+B8h] [rbp-48h] BYREF
  BSTR bstrString[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v110[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v111[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v112[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v113[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v114[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v115[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v116[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v117[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v118[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v119[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v120[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v121[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v122[64]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v123[64]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v124[64]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned __int16 v125[64]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v126[64]; // [rsp+8E0h] [rbp+7E0h] BYREF
  unsigned __int16 v127[64]; // [rsp+960h] [rbp+860h] BYREF
  unsigned __int16 v128[64]; // [rsp+9E0h] [rbp+8E0h] BYREF
  unsigned __int16 v129[64]; // [rsp+A60h] [rbp+960h] BYREF
  unsigned __int16 v130[64]; // [rsp+AE0h] [rbp+9E0h] BYREF
  unsigned __int16 v131[64]; // [rsp+B60h] [rbp+A60h] BYREF
  unsigned __int16 v132[64]; // [rsp+BE0h] [rbp+AE0h] BYREF
  unsigned __int16 v133[64]; // [rsp+C60h] [rbp+B60h] BYREF
  unsigned __int16 v134[64]; // [rsp+CE0h] [rbp+BE0h] BYREF
  unsigned __int16 v135[64]; // [rsp+D60h] [rbp+C60h] BYREF
  unsigned __int16 v136[64]; // [rsp+DE0h] [rbp+CE0h] BYREF
  unsigned __int16 v137[64]; // [rsp+E60h] [rbp+D60h] BYREF
  unsigned __int16 v138[64]; // [rsp+EE0h] [rbp+DE0h] BYREF
  unsigned __int16 v139[64]; // [rsp+F60h] [rbp+E60h] BYREF

  v106 = 0;
  v107 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v105 = 0;
  v4 = 0;
  memset(&v108, 0, sizeof(v108));
  v104 = 0;
  bstrString[0] = 0;
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantInit(&v108);
  v108.llVal = 0;
  VariantClear(&v108);
  lpVtbl = a1->lpVtbl;
  v108.llVal = 0;
  v8 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, CY *))lpVtbl->get_Name)(a1, &v108.cyVal);
  v9 = v8;
  if ( v8 < 0 )
  {
    v101 = 0;
    v102 = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v110, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v110[v10] );
      v11 = &v102;
      v12 = &v101;
      goto LABEL_8;
    }
    goto LABEL_263;
  }
  v108.vt = 8;
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"Duration", 19, a2, &pvarg) >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_Duration)(a1, pvarg.cyVal.Lo);
    if ( v13 )
    {
      v14 = PlaiAddValidation(a3, 0, L"Duration", v13);
      v9 = v14;
      if ( v14 < 0 )
      {
        v102 = 0;
        v101 = v14;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v111, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v111[v15] );
        goto LABEL_17;
      }
    }
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"Description", 8, a2, &pvarg) >= 0 )
  {
    v16 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Description)(a1, pvarg.llVal);
    if ( v16 )
    {
      v17 = PlaiAddValidation(a3, 0, L"Description", v16);
      v9 = v17;
      if ( v17 < 0 )
      {
        v102 = 0;
        v101 = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v112, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v112[v18] );
        goto LABEL_17;
      }
    }
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"DescriptionUnresolved", 8, a2, &pvarg) >= 0 )
  {
    v19 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Description)(a1, pvarg.llVal);
    if ( v19 )
    {
      v20 = PlaiAddValidation(a3, 0, L"Description", v19);
      v9 = v20;
      if ( v20 < 0 )
      {
        v102 = 0;
        v101 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v113, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v113[v21] );
        goto LABEL_17;
      }
    }
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"DisplayName", 8, a2, &pvarg) >= 0 )
  {
    v22 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_DisplayName)(a1, pvarg.llVal);
    if ( v22 )
    {
      v23 = PlaiAddValidation(a3, 0, L"DisplayName", v22);
      v9 = v23;
      if ( v23 < 0 )
      {
        v102 = 0;
        v101 = v23;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v114, 0x4000000000000800uLL);
        v24 = -1;
        do
          ++v24;
        while ( v114[v24] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"DisplayNameUnresolved", 8, a2, &pvarg) >= 0 )
  {
    v25 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_DisplayName)(a1, pvarg.llVal);
    if ( v25 )
    {
      v26 = PlaiAddValidation(a3, 0, L"DisplayName", v25);
      v9 = v26;
      if ( v26 < 0 )
      {
        v102 = 0;
        v101 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v115, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v115[v27] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SchedulesEnabled", 11, a2, &pvarg) >= 0 )
  {
    v28 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_SchedulesEnabled)(
            a1,
            pvarg.uiVal);
    if ( v28 )
    {
      v29 = PlaiAddValidation(a3, 0, L"SchedulesEnabled", v28);
      v9 = v29;
      if ( v29 < 0 )
      {
        v102 = 0;
        v101 = v29;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v116, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v116[v30] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"Keyword", 8200, a2, &pvarg) >= 0 )
  {
    v31 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Keywords)(a1, pvarg.llVal);
    if ( v31 )
    {
      v32 = PlaiAddValidation(a3, 0, L"Keywords", v31);
      v9 = v32;
      if ( v32 < 0 )
      {
        v102 = 0;
        v101 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v117, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v117[v33] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"LatestOutputLocation", 8, a2, &pvarg) >= 0 )
  {
    v34 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_LatestOutputLocation)(
            a1,
            pvarg.llVal);
    if ( v34 )
    {
      v35 = PlaiAddValidation(a3, 0, L"LatestOutputLocation", v34);
      v9 = v35;
      if ( v35 < 0 )
      {
        v102 = 0;
        v101 = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v118, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v118[v36] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"RootPath", 8, a2, &pvarg) >= 0 )
  {
    v37 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_RootPath)(a1, pvarg.llVal);
    if ( v37 )
    {
      v38 = PlaiAddValidation(a3, 0, L"RootPath", v37);
      v9 = v38;
      if ( v38 < 0 )
      {
        v102 = 0;
        v101 = v38;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v119, 0x4000000000000800uLL);
        v39 = -1;
        do
          ++v39;
        while ( v119[v39] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"Segment", 11, a2, &pvarg) >= 0 )
  {
    v40 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_Segment)(a1, pvarg.uiVal);
    if ( v40 )
    {
      v41 = PlaiAddValidation(a3, 0, L"Segment", v40);
      v9 = v41;
      if ( v41 < 0 )
      {
        v102 = 0;
        v101 = v41;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v120, 0x4000000000000800uLL);
        v42 = -1;
        do
          ++v42;
        while ( v120[v42] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SegmentMaxDuration", 19, a2, &pvarg) >= 0 )
  {
    v43 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_SegmentMaxDuration)(
            a1,
            pvarg.cyVal.Lo);
    if ( v43 )
    {
      v44 = PlaiAddValidation(a3, 0, L"SegmentMaxDuration", v43);
      v9 = v44;
      if ( v44 < 0 )
      {
        v102 = 0;
        v101 = v44;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v121, 0x4000000000000800uLL);
        v45 = -1;
        do
          ++v45;
        while ( v121[v45] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SegmentMaxSize", 19, a2, &pvarg) >= 0 )
  {
    v46 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_SegmentMaxSize)(
            a1,
            pvarg.cyVal.Lo);
    if ( v46 )
    {
      v47 = PlaiAddValidation(a3, 0, L"SegmentMaxSize", v46);
      v9 = v47;
      if ( v47 < 0 )
      {
        v102 = 0;
        v101 = v47;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v122, 0x4000000000000800uLL);
        v48 = -1;
        do
          ++v48;
        while ( v122[v48] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SerialNumber", 19, a2, &pvarg) >= 0 )
  {
    v49 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_SerialNumber)(a1, pvarg.cyVal.Lo);
    if ( v49 )
    {
      v50 = PlaiAddValidation(a3, 0, L"SerialNumber", v49);
      v9 = v50;
      if ( v50 < 0 )
      {
        v102 = 0;
        v101 = v50;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v123, 0x4000000000000800uLL);
        v51 = -1;
        do
          ++v51;
        while ( v123[v51] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"Subdirectory", 8, a2, &pvarg) >= 0 )
  {
    v52 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Subdirectory)(a1, pvarg.llVal);
    if ( v52 )
    {
      v53 = PlaiAddValidation(a3, 0, L"Subdirectory", v52);
      v9 = v53;
      if ( v53 < 0 )
      {
        v102 = 0;
        v101 = v53;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v124, 0x4000000000000800uLL);
        v54 = -1;
        do
          ++v54;
        while ( v124[v54] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SubdirectoryFormat", 3, a2, &pvarg) >= 0 )
  {
    v55 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_SubdirectoryFormat)(
            a1,
            pvarg.cyVal.Lo);
    if ( v55 )
    {
      v56 = PlaiAddValidation(a3, 0, L"SubdirectoryFormat", v55);
      v9 = v56;
      if ( v56 < 0 )
      {
        v102 = 0;
        v101 = v56;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v125, 0x4000000000000800uLL);
        v57 = -1;
        do
          ++v57;
        while ( v125[v57] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SubdirectoryFormatPattern", 8, a2, &pvarg) >= 0 )
  {
    v58 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_SubdirectoryFormatPattern)(
            a1,
            pvarg.llVal);
    if ( v58 )
    {
      v59 = PlaiAddValidation(a3, 0, L"SubdirectoryFormatPattern", v58);
      v9 = v59;
      if ( v59 < 0 )
      {
        v102 = 0;
        v101 = v59;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v126, 0x4000000000000800uLL);
        v60 = -1;
        do
          ++v60;
        while ( v126[v60] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"Task", 8, a2, &pvarg) >= 0 )
  {
    v61 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Task)(a1, pvarg.llVal);
    if ( v61 )
    {
      v62 = PlaiAddValidation(a3, 0, L"Task", v61);
      v9 = v62;
      if ( v62 < 0 )
      {
        v102 = 0;
        v101 = v62;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v127, 0x4000000000000800uLL);
        v63 = -1;
        do
          ++v63;
        while ( v127[v63] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"TaskRunAsSelf", 11, a2, &pvarg) >= 0 )
  {
    v64 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_TaskRunAsSelf)(a1, pvarg.uiVal);
    if ( v64 )
    {
      v65 = PlaiAddValidation(a3, 0, L"TaskRunAsSelf", v64);
      v9 = v65;
      if ( v65 < 0 )
      {
        v102 = 0;
        v101 = v65;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v128, 0x4000000000000800uLL);
        v66 = -1;
        do
          ++v66;
        while ( v128[v66] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"TaskArguments", 8, a2, &pvarg) >= 0 )
  {
    v67 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_TaskArguments)(a1, pvarg.llVal);
    if ( v67 )
    {
      v68 = PlaiAddValidation(a3, 0, L"TaskArguments", v67);
      v9 = v68;
      if ( v68 < 0 )
      {
        v102 = 0;
        v101 = v68;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v129, 0x4000000000000800uLL);
        v69 = -1;
        do
          ++v69;
        while ( v129[v69] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"TaskUserTextArguments", 8, a2, &pvarg) >= 0 )
  {
    v70 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_TaskUserTextArguments)(
            a1,
            pvarg.llVal);
    if ( v70 )
    {
      v71 = PlaiAddValidation(a3, 0, L"TaskUserTextArguments", v70);
      v9 = v71;
      if ( v71 < 0 )
      {
        v102 = 0;
        v101 = v71;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v130, 0x4000000000000800uLL);
        v72 = -1;
        do
          ++v72;
        while ( v130[v72] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"Security", 8, a2, &pvarg) >= 0 )
  {
    v73 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, LONGLONG))a1->lpVtbl->put_Security)(a1, pvarg.llVal);
    if ( v73 )
    {
      v74 = PlaiAddValidation(a3, 0, L"Security", v73);
      v9 = v74;
      if ( v74 < 0 )
      {
        v102 = 0;
        v101 = v74;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v131, 0x4000000000000800uLL);
        v75 = -1;
        do
          ++v75;
        while ( v131[v75] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"StopOnCompletion", 11, a2, &pvarg) >= 0 )
  {
    v76 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a1->lpVtbl->put_StopOnCompletion)(
            a1,
            pvarg.uiVal);
    if ( v76 )
    {
      v77 = PlaiAddValidation(a3, 0, L"StopOnCompletion", v76);
      v9 = v77;
      if ( v77 < 0 )
      {
        v102 = 0;
        v101 = v77;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_263;
        }
        PlaiWhoAmI(v132, 0x4000000000000800uLL);
        v78 = -1;
        do
          ++v78;
        while ( v132[v78] );
        goto LABEL_17;
      }
    }
  }
  v79 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, struct IDataCollectorCollection **))a1->lpVtbl->get_DataCollectors)(
          a1,
          &v106);
  v9 = v79;
  if ( v79 < 0 )
  {
    v102 = 0;
    v101 = v79;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v133, 0x4000000000000800uLL);
    v80 = -1;
    do
      ++v80;
    while ( v133[v80] );
    goto LABEL_17;
  }
  v81 = DataCollectorCollection::SetXml(v106, a2, a3);
  v9 = v81;
  if ( v81 < 0 )
  {
    v102 = 0;
    v101 = v81;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v134, 0x4000000000000800uLL);
    v82 = -1;
    do
      ++v82;
    while ( v134[v82] );
    goto LABEL_17;
  }
  v83 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, struct IScheduleCollection **))a1->lpVtbl->get_Schedules)(
          a1,
          &v107);
  v9 = v83;
  if ( v83 < 0 )
  {
    v102 = 0;
    v101 = v83;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v135, 0x4000000000000800uLL);
    v85 = -1;
    do
      ++v85;
    while ( v135[v85] );
    goto LABEL_17;
  }
  v86 = TriggerCollection::SetXml(v107, a2, a3, v84);
  v9 = v86;
  if ( v86 < 0 )
  {
    v102 = 0;
    v101 = v86;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v136, 0x4000000000000800uLL);
    v87 = -1;
    do
      ++v87;
    while ( v136[v87] );
    goto LABEL_17;
  }
  get_namespaceURI = a2->lpVtbl->get_namespaceURI;
  v89 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(bstrString);
  v90 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64))get_namespaceURI)(a2, v89);
  if ( v90 != 1 )
    MicrosoftTelemetryAssertTriggeredArgs(v91, v90);
  PlaiFreeString(0);
  v94 = PlaiAllocStringEx(L"DataManager", v92, v93);
  v4 = v94;
  if ( !v94 )
  {
    v9 = -2147024882;
    v101 = -2147024882;
    v102 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v137, 0x4000000000000800uLL);
    v95 = -1;
    do
      ++v95;
    while ( v137[v95] );
    goto LABEL_17;
  }
  v96 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, unsigned __int16 *, struct IXMLDOMNode **))a2->lpVtbl->selectSingleNode)(
          a2,
          v94,
          &v104);
  v9 = v96;
  if ( v96 < 0 )
  {
    v102 = 0;
    v101 = v96;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_263;
    }
    PlaiWhoAmI(v138, 0x4000000000000800uLL);
    v97 = -1;
    do
      ++v97;
    while ( v138[v97] );
LABEL_17:
    v11 = &v101;
    v12 = &v102;
LABEL_8:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
    goto LABEL_263;
  }
  if ( v96 == 1
    || !v104
    || ((int (__fastcall *)(struct IDataCollectorSet *, struct IDataManager **))a1->lpVtbl->get_DataManager)(a1, &v105) < 0
    || !v105
    || (v98 = DataManager::SetXml(v105, v104, a3, L"DataManager"), v9 = v98, v98 >= 0) )
  {
    v9 = 0;
    goto LABEL_263;
  }
  v102 = 0;
  v101 = v98;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v139, 0x4000000000000800uLL);
    v99 = -1;
    do
      ++v99;
    while ( v139[v99] );
    goto LABEL_17;
  }
LABEL_263:
  PlaiFreeString(v4);
  if ( v104 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v104->lpVtbl->Release)(v104);
    v104 = 0;
  }
  if ( v105 )
  {
    ((void (__fastcall *)(struct IDataManager *))v105->lpVtbl->Release)(v105);
    v105 = 0;
  }
  if ( v106 )
  {
    ((void (__fastcall *)(struct IDataCollectorCollection *))v106->lpVtbl->Release)(v106);
    v106 = 0;
  }
  if ( v107 )
  {
    ((void (__fastcall *)(struct IScheduleCollection *))v107->lpVtbl->Release)(v107);
    v107 = 0;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&v108);
  v108.llVal = 0;
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return v9;
}

```

## disassembly

```asm
0x18004fa78  mov     [rsp-8+arg_18], rbx
0x18004fa7d  push    rbp
0x18004fa7e  push    rsi
0x18004fa7f  push    rdi
0x18004fa80  push    r12
0x18004fa82  push    r13
0x18004fa84  push    r14
0x18004fa86  push    r15
0x18004fa88  lea     rbp, [rsp-0EF0h]
0x18004fa90  sub     rsp, 0FF0h
0x18004fa97  mov     rax, cs:__security_cookie
0x18004fa9e  xor     rax, rsp
0x18004faa1  mov     [rbp+0F20h+var_40], rax
0x18004faa8  xor     r12d, r12d
0x18004faab  xor     eax, eax
0x18004faad  mov     rdi, rcx
0x18004fab0  mov     qword ptr [rbp+0F20h+pvarg+10h], rax
0x18004fab4  xorps   xmm0, xmm0
0x18004fab7  mov     qword ptr [rbp+0F20h+var_F68+10h], rax
0x18004fabb  xorps   xmm1, xmm1
0x18004fabe  mov     [rbp+0F20h+var_F78], r12
0x18004fac2  lea     rcx, [rbp+0F20h+pvarg]; pvarg
0x18004fac6  mov     [rbp+0F20h+var_F70], r12
0x18004faca  movups  xmmword ptr [rbp+0F20h+pvarg], xmm0
0x18004face  mov     [rbp+0F20h+var_F80], r12
0x18004fad2  mov     r15d, r12d
0x18004fad5  movups  xmmword ptr [rbp+0F20h+var_F68], xmm1
0x18004fad9  mov     [rbp+0F20h+var_F88], r12
0x18004fadd  mov     r14, r8
0x18004fae0  mov     [rbp+0F20h+bstrString], r12
0x18004fae4  mov     rsi, rdx
0x18004fae7  call    cs:__imp_VariantInit
0x18004faed  lea     rcx, [rbp+0F20h+var_F68]; pvarg
0x18004faf1  mov     qword ptr [rbp+0F20h+pvarg+8], r12
0x18004faf5  call    cs:__imp_VariantInit
0x18004fafb  lea     rcx, [rbp+0F20h+var_F68]; pvarg
0x18004faff  mov     qword ptr [rbp+0F20h+var_F68+8], r12
0x18004fb03  call    cs:__imp_VariantClear
0x18004fb09  mov     rax, [rdi]
0x18004fb0c  lea     rdx, [rbp+0F20h+var_F68+8]
0x18004fb10  mov     rcx, rdi
0x18004fb13  mov     qword ptr [rbp+0F20h+var_F68+8], r12
0x18004fb17  mov     rax, [rax+0A0h]
0x18004fb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb23  mov     ebx, eax
0x18004fb25  test    eax, eax
0x18004fb27  jns     loc_18004FC05
0x18004fb2d  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004fb34  mov     [rsp+1020h+var_FB0], r12d
0x18004fb39  mov     [rsp+1020h+var_FA8], eax
0x18004fb3d  jz      loc_180051294
0x18004fb43  mov     rdx, 4000000000000800h; unsigned __int64
0x18004fb4d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004fb54  jz      loc_180051294
0x18004fb5a  mov     rax, cs:qword_180169748
0x18004fb61  and     rax, rdx
0x18004fb64  cmp     cs:qword_180169748, rax
0x18004fb6b  jnz     loc_180051294
0x18004fb71  lea     rcx, [rbp+0F20h+var_F40]; unsigned __int16 *
0x18004fb75  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004fb7a  lea     rcx, [rbp+0F20h+var_F40]
0x18004fb7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fb82  inc     rax
0x18004fb85  cmp     [rcx+rax*2], r12w
0x18004fb8a  jnz     short loc_18004FB82
0x18004fb8c  lea     ecx, [rax+rax]
0x18004fb8f  add     rcx, 2
0x18004fb93  lea     rax, [rbp+0F20h+var_F40]
0x18004fb97  mov     [rsp+1020h+var_FC0], rcx
0x18004fb9c  lea     r9, [rsp+1020h+var_FA8]
0x18004fba1  lea     rcx, [rsp+1020h+var_FB0]
0x18004fba6  mov     [rsp+1020h+var_FC8], rax
0x18004fbab  lea     rdx, PLA_EVENT_ERROR
0x18004fbb2  mov     [rsp+1020h+var_FD0], 19h
0x18004fbbb  lea     rax, aDatacollectors_62; "DataCollectorSet::SetXml"
0x18004fbc2  mov     [rsp+1020h+var_FD8], rax
0x18004fbc7  mov     eax, 4
0x18004fbcc  mov     [rsp+1020h+var_FE0], rax
0x18004fbd1  mov     [rsp+1020h+var_FE8], rcx
0x18004fbd6  lea     rcx, byte_180147320
0x18004fbdd  mov     [rsp+1020h+var_FF0], 1
0x18004fbe6  mov     [rsp+1020h+var_FF8], rcx
0x18004fbeb  lea     r8d, [rax+1]
0x18004fbef  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004fbf6  mov     [rsp+1020h+var_1000], rax
0x18004fbfb  call    EventingWriteEvent
0x18004fc00  jmp     loc_180051294
0x18004fc05  mov     r13d, 8
0x18004fc0b  lea     rcx, [rbp+0F20h+pvarg]; pvarg
0x18004fc0f  mov     word ptr [rbp+0F20h+var_F68], r13w
0x18004fc14  call    cs:__imp_VariantClear
0x18004fc1a  lea     edx, [r13+0Bh]; unsigned __int16
0x18004fc1e  mov     qword ptr [rbp+0F20h+pvarg+8], r12
0x18004fc22  lea     r9, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004fc26  mov     r8, rsi; struct IXMLDOMNode *
0x18004fc29  lea     rcx, aDuration; "Duration"
0x18004fc30  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004fc35  test    eax, eax
0x18004fc37  js      loc_18004FCEF
0x18004fc3d  mov     rax, [rdi]
0x18004fc40  mov     rcx, rdi
0x18004fc43  mov     edx, dword ptr [rbp+0F20h+pvarg+8]
0x18004fc46  mov     rax, [rax+48h]
0x18004fc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc4f  test    eax, eax
0x18004fc51  jz      loc_18004FCEF
0x18004fc57  mov     r9d, eax; int
0x18004fc5a  lea     r8, aDuration; "Duration"
0x18004fc61  xor     edx, edx; unsigned __int16 *
0x18004fc63  mov     rcx, r14; struct IValueMap *
0x18004fc66  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004fc6b  mov     ebx, eax
0x18004fc6d  test    eax, eax
0x18004fc6f  jns     short loc_18004FCEF
0x18004fc71  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004fc78  mov     [rsp+1020h+var_FA8], r12d
0x18004fc7d  mov     [rsp+1020h+var_FB0], eax
0x18004fc81  jz      loc_180051294
0x18004fc87  mov     rdx, 4000000000000800h; unsigned __int64
0x18004fc91  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004fc98  jz      loc_180051294
0x18004fc9e  mov     rax, cs:qword_180169748
0x18004fca5  and     rax, rdx
0x18004fca8  cmp     cs:qword_180169748, rax
0x18004fcaf  jnz     loc_180051294
0x18004fcb5  lea     rcx, [rbp+0F20h+var_EC0]; unsigned __int16 *
0x18004fcb9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004fcbe  lea     rcx, [rbp+0F20h+var_EC0]
0x18004fcc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fcc6  inc     rax
0x18004fcc9  cmp     [rcx+rax*2], r12w
0x18004fcce  jnz     short loc_18004FCC6
0x18004fcd0  lea     ecx, [rax+rax]
0x18004fcd3  lea     rax, [rbp+0F20h+var_EC0]
0x18004fcd7  add     rcx, 2
0x18004fcdb  lea     r9, [rsp+1020h+var_FB0]
0x18004fce0  mov     [rsp+1020h+var_FC0], rcx
0x18004fce5  lea     rcx, [rsp+1020h+var_FA8]
0x18004fcea  jmp     loc_18004FBA6
0x18004fcef  lea     rcx, [rbp+0F20h+pvarg]; pvarg
0x18004fcf3  call    cs:__imp_VariantClear
0x18004fcf9  mov     edx, r13d; unsigned __int16
0x18004fcfc  mov     qword ptr [rbp+0F20h+pvarg+8], r12
0x18004fd00  lea     r9, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004fd04  mov     r8, rsi; struct IXMLDOMNode *
0x18004fd07  lea     rcx, aDescription; "Description"
0x18004fd0e  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004fd13  test    eax, eax
0x18004fd15  js      loc_18004FDC4
0x18004fd1b  mov     rax, [rdi]
0x18004fd1e  mov     rcx, rdi
0x18004fd21  mov     rdx, qword ptr [rbp+0F20h+pvarg+8]
0x18004fd25  mov     rax, [rax+58h]
0x18004fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd2e  test    eax, eax
0x18004fd30  jz      loc_18004FDC4
0x18004fd36  mov     r9d, eax; int
0x18004fd39  lea     r8, aDescription; "Description"
0x18004fd40  xor     edx, edx; unsigned __int16 *
0x18004fd42  mov     rcx, r14; struct IValueMap *
0x18004fd45  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004fd4a  mov     ebx, eax
0x18004fd4c  test    eax, eax
0x18004fd4e  jns     short loc_18004FDC4
0x18004fd50  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004fd57  mov     [rsp+1020h+var_FA8], r12d
0x18004fd5c  mov     [rsp+1020h+var_FB0], eax
0x18004fd60  jz      loc_180051294
0x18004fd66  mov     rdx, 4000000000000800h; unsigned __int64
0x18004fd70  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004fd77  jz      loc_180051294
0x18004fd7d  mov     rax, cs:qword_180169748
0x18004fd84  and     rax, rdx
0x18004fd87  cmp     cs:qword_180169748, rax
0x18004fd8e  jnz     loc_180051294
0x18004fd94  lea     rcx, [rbp+0F20h+var_E40]; unsigned __int16 *
0x18004fd9b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004fda0  lea     rcx, [rbp+0F20h+var_E40]
0x18004fda7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fdab  inc     rax
0x18004fdae  cmp     [rcx+rax*2], r12w
0x18004fdb3  jnz     short loc_18004FDAB
0x18004fdb5  lea     ecx, [rax+rax]
0x18004fdb8  lea     rax, [rbp+0F20h+var_E40]
0x18004fdbf  jmp     loc_18004FCD7
0x18004fdc4  lea     rcx, [rbp+0F20h+pvarg]; pvarg
0x18004fdc8  call    cs:__imp_VariantClear
0x18004fdce  mov     edx, r13d; unsigned __int16
0x18004fdd1  mov     qword ptr [rbp+0F20h+pvarg+8], r12
0x18004fdd5  lea     r9, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004fdd9  mov     r8, rsi; struct IXMLDOMNode *
0x18004fddc  lea     rcx, aDescriptionunr; "DescriptionUnresolved"
0x18004fde3  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004fde8  test    eax, eax
0x18004fdea  js      loc_18004FE99
0x18004fdf0  mov     rax, [rdi]
0x18004fdf3  mov     rcx, rdi
0x18004fdf6  mov     rdx, qword ptr [rbp+0F20h+pvarg+8]
0x18004fdfa  mov     rax, [rax+58h]
0x18004fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe03  test    eax, eax
0x18004fe05  jz      loc_18004FE99
0x18004fe0b  mov     r9d, eax; int
0x18004fe0e  lea     r8, aDescription; "Description"
0x18004fe15  xor     edx, edx; unsigned __int16 *
0x18004fe17  mov     rcx, r14; struct IValueMap *
0x18004fe1a  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004fe1f  mov     ebx, eax
0x18004fe21  test    eax, eax
0x18004fe23  jns     short loc_18004FE99
0x18004fe25  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004fe2c  mov     [rsp+1020h+var_FA8], r12d
0x18004fe31  mov     [rsp+1020h+var_FB0], eax
0x18004fe35  jz      loc_180051294
0x18004fe3b  mov     rdx, 4000000000000800h; unsigned __int64
0x18004fe45  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004fe4c  jz      loc_180051294
0x18004fe52  mov     rax, cs:qword_180169748
0x18004fe59  and     rax, rdx
0x18004fe5c  cmp     cs:qword_180169748, rax
0x18004fe63  jnz     loc_180051294
0x18004fe69  lea     rcx, [rbp+0F20h+var_DC0]; unsigned __int16 *
0x18004fe70  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004fe75  lea     rcx, [rbp+0F20h+var_DC0]
0x18004fe7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fe80  inc     rax
0x18004fe83  cmp     [rcx+rax*2], r12w
0x18004fe88  jnz     short loc_18004FE80
0x18004fe8a  lea     ecx, [rax+rax]
0x18004fe8d  lea     rax, [rbp+0F20h+var_DC0]
0x18004fe94  jmp     loc_18004FCD7
0x18004fe99  lea     rcx, [rbp+0F20h+pvarg]; pvarg
0x18004fe9d  call    cs:__imp_VariantClear
0x18004fea3  mov     edx, r13d; unsigned __int16
0x18004fea6  mov     qword ptr [rbp+0F20h+pvarg+8], r12
0x18004feaa  lea     r9, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004feae  mov     r8, rsi; struct IXMLDOMNode *
0x18004feb1  lea     rcx, aDisplayname; "DisplayName"
0x18004feb8  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004febd  test    eax, eax
0x18004febf  js      loc_18004FF6E
0x18004fec5  mov     rax, [rdi]
0x18004fec8  mov     rcx, rdi
0x18004fecb  mov     rdx, qword ptr [rbp+0F20h+pvarg+8]
0x18004fecf  mov     rax, [rax+70h]
0x18004fed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fed8  test    eax, eax
0x18004feda  jz      loc_18004FF6E
0x18004fee0  mov     r9d, eax; int
0x18004fee3  lea     r8, aDisplayname; "DisplayName"
0x18004feea  xor     edx, edx; unsigned __int16 *
0x18004feec  mov     rcx, r14; struct IValueMap *
0x18004feef  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004fef4  mov     ebx, eax
0x18004fef6  test    eax, eax
0x18004fef8  jns     short loc_18004FF6E
0x18004fefa  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004ff01  mov     [rsp+1020h+var_FA8], r12d
0x18004ff06  mov     [rsp+1020h+var_FB0], eax
0x18004ff0a  jz      loc_180051294
0x18004ff10  mov     rdx, 4000000000000800h; unsigned __int64
0x18004ff1a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004ff21  jz      loc_180051294
0x18004ff27  mov     rax, cs:qword_180169748
0x18004ff2e  and     rax, rdx
0x18004ff31  cmp     cs:qword_180169748, rax
0x18004ff38  jnz     loc_180051294
0x18004ff3e  lea     rcx, [rbp+0F20h+var_D40]; unsigned __int16 *
0x18004ff45  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004ff4a  lea     rcx, [rbp+0F20h+var_D40]
0x18004ff51  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ff55  inc     rax
0x18004ff58  cmp     [rcx+rax*2], r12w
0x18004ff5d  jnz     short loc_18004FF55
0x18004ff5f  lea     ecx, [rax+rax]
0x18004ff62  lea     rax, [rbp+0F20h+var_D40]
0x18004ff69  jmp     loc_18004FCD7
0x18004ff6e  lea     rcx, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004ff72  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18004ff77  mov     edx, r13d; unsigned __int16
0x18004ff7a  lea     r9, [rbp+0F20h+pvarg]; struct tagVARIANT *
0x18004ff7e  mov     r8, rsi; struct IXMLDOMNode *
0x18004ff81  lea     rcx, aDisplaynameunr; "DisplayNameUnresolved"
0x18004ff88  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004ff8d  test    eax, eax
0x18004ff8f  js      loc_18005003E
0x18004ff95  mov     rax, [rdi]
0x18004ff98  mov     rcx, rdi
0x18004ff9b  mov     rdx, qword ptr [rbp+0F20h+pvarg+8]
0x18004ff9f  mov     rax, [rax+70h]
0x18004ffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffa8  test    eax, eax
0x18004ffaa  jz      loc_18005003E
0x18004ffb0  mov     r9d, eax; int
0x18004ffb3  lea     r8, aDisplayname; "DisplayName"
0x18004ffba  xor     edx, edx; unsigned __int16 *
0x18004ffbc  mov     rcx, r14; struct IValueMap *
0x18004ffbf  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004ffc4  mov     ebx, eax
0x18004ffc6  test    eax, eax
  ... truncated ...
```
