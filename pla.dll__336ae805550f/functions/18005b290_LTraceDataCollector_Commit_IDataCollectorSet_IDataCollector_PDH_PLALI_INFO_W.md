# LTraceDataCollector::Commit(IDataCollectorSet *,IDataCollector *,_PDH_PLALI_INFO_W *)

- ea: `0x18005b290`
- end: `0x18005cbc5`
- name: `?Commit@LTraceDataCollector@@SAJPEAUIDataCollectorSet@@PEAUIDataCollector@@PEAU_PDH_PLALI_INFO_W@@@Z`
- size: `6453`
- prototype: `__int64 __fastcall(struct IDataCollectorSet *, struct IDataCollector *, struct _PDH_PLALI_INFO_W *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800b16b0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x1800429d0`
- `0x180057090`
- `0x18005b290`
- `0x1801147b8`
- `0x18011a5f8`
- `0x180132ea0`
- `0x18013ae76`
- `0x18013aee0`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b634`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b645`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b653`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b634`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b645`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005b653`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bf0a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bf92`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005c01a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bf0a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005bf92`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005c01a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b5fc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b60f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b622`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b5fc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b60f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005b622`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005bce1`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005bd76`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005be75`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005bce1`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005bd76`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005be75`

## string_xrefs

- `0x18005b5a4`: `LTraceDataCollector::Commit`
- `0x18005b7ff`: `LTraceDataCollector::Commit`
- `0x18005be27`: `LTraceDataCollector::Commit`
- `0x18005c37f`: `LTraceDataCollector::Commit`
- `0x18005c636`: `LTraceDataCollector::Commit`
- `0x18005c9f5`: `LTraceDataCollector::Commit`
- `0x18005cb80`: `LTraceDataCollector::Commit`

## pseudocode

```c
__int64 __fastcall LTraceDataCollector::Commit(
        struct IDataCollectorSet *a1,
        struct IDataCollector *a2,
        struct _PDH_PLALI_INFO_W *a3)
{
  SAFEARRAY *v4; // r15
  SAFEARRAY *v5; // r14
  SAFEARRAY *Vector; // r13
  unsigned __int16 *v9; // r12
  HRESULT v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  struct ITraceDataCollector *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  struct ITraceDataCollector *v17; // rcx
  signed int v18; // eax
  __int64 v19; // rax
  struct ITraceDataCollector *v20; // rcx
  signed int v21; // eax
  __int64 v22; // rax
  struct ITraceDataCollector *v23; // rcx
  signed int v24; // eax
  __int64 v25; // rax
  struct ITraceDataCollector *v26; // rcx
  signed int v27; // eax
  __int64 v28; // rax
  signed int v29; // eax
  __int64 v30; // rax
  signed int v31; // eax
  __int64 v32; // rax
  signed int v33; // eax
  __int64 v34; // rax
  signed int v35; // eax
  __int64 v36; // rax
  signed int TraceDataProvider; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  ULONG i; // r15d
  signed int v46; // eax
  signed int v47; // eax
  signed int Ul; // eax
  signed int v49; // eax
  signed int v50; // eax
  signed int v51; // eax
  signed int v52; // eax
  const char *v53; // rdx
  int v54; // r8d
  unsigned __int16 *v55; // rax
  const char *v56; // rdx
  int v57; // r8d
  unsigned __int16 *v58; // rax
  const char *v59; // rdx
  int v60; // r8d
  unsigned __int16 *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  SAFEARRAY *v74; // rcx
  signed int v75; // eax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  int v79; // [rsp+20h] [rbp-E0h]
  unsigned int v80; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v81; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *v82; // [rsp+80h] [rbp-80h]
  SAFEARRAY *psa; // [rsp+88h] [rbp-78h]
  ULONG cElements; // [rsp+90h] [rbp-70h] BYREF
  __int64 v85; // [rsp+98h] [rbp-68h] BYREF
  struct ITraceDataCollector *v86; // [rsp+A0h] [rbp-60h] BYREF
  struct ITraceDataProvider *v87; // [rsp+A8h] [rbp-58h] BYREF
  void *ppvData; // [rsp+B0h] [rbp-50h] BYREF
  void *v89; // [rsp+B8h] [rbp-48h] BYREF
  void *v90; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v91; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v92; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v93; // [rsp+D8h] [rbp-28h] BYREF
  int v94; // [rsp+E0h] [rbp-20h] BYREF
  struct tagVARIANT v95; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID Buf1; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v97[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v98[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v99[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v100[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v101[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v102[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v103[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v104[64]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v105[64]; // [rsp+510h] [rbp+410h] BYREF
  unsigned __int16 v106[64]; // [rsp+590h] [rbp+490h] BYREF
  unsigned __int16 v107[64]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v108[64]; // [rsp+690h] [rbp+590h] BYREF
  unsigned __int16 v109[64]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v110[64]; // [rsp+790h] [rbp+690h] BYREF
  unsigned __int16 v111[64]; // [rsp+810h] [rbp+710h] BYREF
  unsigned __int16 v112[64]; // [rsp+890h] [rbp+790h] BYREF
  unsigned __int16 v113[64]; // [rsp+910h] [rbp+810h] BYREF
  unsigned __int16 v114[64]; // [rsp+990h] [rbp+890h] BYREF
  unsigned __int16 v115[64]; // [rsp+A10h] [rbp+910h] BYREF
  unsigned __int16 v116[64]; // [rsp+A90h] [rbp+990h] BYREF
  unsigned __int16 v117[64]; // [rsp+B10h] [rbp+A10h] BYREF
  unsigned __int16 v118[64]; // [rsp+B90h] [rbp+A90h] BYREF
  unsigned __int16 v119[64]; // [rsp+C10h] [rbp+B10h] BYREF
  unsigned __int16 v120[64]; // [rsp+C90h] [rbp+B90h] BYREF
  unsigned __int16 v121[64]; // [rsp+D10h] [rbp+C10h] BYREF
  unsigned __int16 v122[64]; // [rsp+D90h] [rbp+C90h] BYREF
  unsigned __int16 v123[64]; // [rsp+E10h] [rbp+D10h] BYREF
  unsigned __int16 v124[64]; // [rsp+E90h] [rbp+D90h] BYREF
  unsigned __int16 v125[64]; // [rsp+F10h] [rbp+E10h] BYREF
  unsigned __int16 v126[64]; // [rsp+F90h] [rbp+E90h] BYREF
  unsigned __int16 v127[64]; // [rsp+1010h] [rbp+F10h] BYREF
  unsigned __int16 v128[64]; // [rsp+1090h] [rbp+F90h] BYREF
  unsigned __int16 v129[64]; // [rsp+1110h] [rbp+1010h] BYREF
  unsigned __int16 v130[64]; // [rsp+1190h] [rbp+1090h] BYREF

  cElements = 0;
  v4 = 0;
  v94 = 0;
  v5 = 0;
  Vector = 0;
  ppvData = 0;
  v90 = 0;
  v89 = 0;
  v91 = 0;
  v92 = 0;
  v86 = 0;
  v87 = 0;
  v93 = 0;
  v85 = 0;
  memset(&v95, 0, sizeof(v95));
  Buf1 = 0;
  PlaiVariantInit(&v95);
  v9 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v79);
  if ( !v9 )
  {
    v10 = -2147024882;
    v80 = -2147024882;
    v81 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v97, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v97[v11] );
    goto LABEL_283;
  }
  v10 = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, struct ITraceDataCollector **))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_ITraceDataCollector,
          &v86);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v98, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v98[v12] );
    goto LABEL_283;
  }
  v13 = v86;
  *(_DWORD *)a3 |= 0x10200u;
  *((_DWORD *)a3 + 6) = 1;
  v10 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, char *))v13->lpVtbl->get_BufferSize)(
          v13,
          (char *)a3 + 248);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v99, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v99[v14] );
    goto LABEL_283;
  }
  v10 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, char *))a1->lpVtbl->get_SegmentMaxSize)(
          a1,
          (char *)a3 + 28);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v100, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v100[v15] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
      v5 = 0;
      goto LABEL_30;
    }
LABEL_29:
    v5 = 0;
    goto LABEL_30;
  }
  if ( *((_DWORD *)a3 + 7) )
    *(_DWORD *)a3 |= 4u;
  v17 = v86;
  *(_DWORD *)a3 |= 0x200000u;
  v18 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, char *))v17->lpVtbl->get_FlushTimer)(
          v17,
          (char *)a3 + 252);
  v10 = v18;
  if ( v18 < 0 )
  {
    v81 = 0;
    v80 = v18;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v101, 0x4000000000000800uLL);
    v19 = -1;
    do
      ++v19;
    while ( v101[v19] );
    goto LABEL_65;
  }
  v20 = v86;
  *(_DWORD *)a3 |= 0x80000u;
  v21 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, char *))v20->lpVtbl->get_MinimumBuffers)(
          v20,
          (char *)a3 + 244);
  v10 = v21;
  if ( v21 < 0 )
  {
    v81 = 0;
    v80 = v21;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v102, 0x4000000000000800uLL);
    v22 = -1;
    do
      ++v22;
    while ( v102[v22] );
    goto LABEL_65;
  }
  v23 = v86;
  *(_DWORD *)a3 |= 0x100000u;
  v24 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, char *))v23->lpVtbl->get_MaximumBuffers)(
          v23,
          (char *)a3 + 240);
  v10 = v24;
  if ( v24 < 0 )
  {
    v81 = 0;
    v80 = v24;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v103, 0x4000000000000800uLL);
    v25 = -1;
    do
      ++v25;
    while ( v103[v25] );
    goto LABEL_65;
  }
  v26 = v86;
  *(_DWORD *)a3 |= 0x20000u;
  v27 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, char *))v26->lpVtbl->get_SessionName)(
          v26,
          (char *)a3 + 224);
  v10 = v27;
  if ( v27 < 0 )
  {
    v81 = 0;
    v80 = v27;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v104, 0x4000000000000800uLL);
    v28 = -1;
    do
      ++v28;
    while ( v104[v28] );
    goto LABEL_65;
  }
  v29 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, __int64 *))v86->lpVtbl->get_TraceDataProviders)(
          v86,
          &v93);
  v10 = v29;
  if ( v29 < 0 )
  {
    v81 = 0;
    v80 = v29;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v105, 0x4000000000000800uLL);
    v30 = -1;
    do
      ++v30;
    while ( v105[v30] );
    goto LABEL_65;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v93 + 72LL))(v93, &v91);
  v10 = v31;
  if ( v31 < 0 )
  {
    v81 = 0;
    v80 = v31;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v106, 0x4000000000000800uLL);
    v32 = -1;
    do
      ++v32;
    while ( v106[v32] );
    goto LABEL_65;
  }
  v33 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v91)(v91, &IID_IEnumVARIANT, &v92);
  v10 = v33;
  if ( v33 < 0 )
  {
    v81 = 0;
    v80 = v33;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v107, 0x4000000000000800uLL);
    v34 = -1;
    do
      ++v34;
    while ( v107[v34] );
    goto LABEL_65;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v93 + 56LL))(v93, &cElements);
  v10 = v35;
  if ( v35 < 0 )
  {
    v81 = 0;
    v80 = v35;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v108, 0x4000000000000800uLL);
    v36 = -1;
    do
      ++v36;
    while ( v108[v36] );
    goto LABEL_65;
  }
  TraceDataProvider = TraceDataCollector::get_TraceDataProvider(v86, &v87);
  v10 = TraceDataProvider;
  if ( TraceDataProvider < 0 )
  {
    v81 = 0;
    v80 = TraceDataProvider;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v109, 0x4000000000000800uLL);
    v38 = -1;
    do
      ++v38;
    while ( v109[v38] );
    goto LABEL_65;
  }
  psa = SafeArrayCreateVector(8u, 0, cElements);
  v4 = psa;
  if ( !psa )
  {
    v10 = -2147024882;
    v80 = -2147024882;
    v81 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_29;
    }
    PlaiWhoAmI(v110, 0x4000000000000800uLL);
    v39 = -1;
    do
      ++v39;
    while ( v110[v39] );
LABEL_65:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
    goto LABEL_29;
  }
  Vector = SafeArrayCreateVector(8u, 0, cElements);
  if ( !Vector )
  {
    v10 = -2147024882;
    v80 = -2147024882;
    v81 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v111, 0x4000000000000800uLL);
      v40 = -1;
      do
        ++v40;
      while ( v111[v40] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
    }
    goto LABEL_30;
  }
  v82 = SafeArrayCreateVector(8u, 0, cElements);
  v5 = v82;
  if ( !v82 )
  {
    v10 = -2147024882;
    v80 = -2147024882;
    v81 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v112, 0x4000000000000800uLL);
    v41 = -1;
    do
      ++v41;
    while ( v112[v41] );
    goto LABEL_283;
  }
  v10 = SafeArrayAccessData(psa, &ppvData);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v113, 0x4000000000000800uLL);
    v42 = -1;
    do
      ++v42;
    while ( v113[v42] );
    goto LABEL_283;
  }
  v10 = SafeArrayAccessData(Vector, &v89);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v114, 0x4000000000000800uLL);
    v43 = -1;
    do
      ++v43;
    while ( v114[v43] );
    goto LABEL_283;
  }
  v10 = SafeArrayAccessData(v82, &v90);
  if ( v10 < 0 )
  {
    v81 = 0;
    v80 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_30;
    }
    PlaiWhoAmI(v115, 0x4000000000000800uLL);
    v44 = -1;
    do
      ++v44;
    while ( v115[v44] );
    goto LABEL_283;
  }
  *(_DWORD *)a3 |= 0x400000u;
  for ( i = 0; ; ++i )
  {
    if ( i >= cElements )
    {
      v4 = psa;
      v74 = psa;
      *((_DWORD *)a3 + 48) = 1;
      v75 = PlaiSafeArrayToStrings(v74, (unsigned __int16 **)a3 + 25);
      v10 = v75;
      if ( v75 < 0 )
      {
        v81 = 0;
        v80 = v75;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v128, 0x4000000000000800uLL);
          v76 = -1;
          do
            ++v76;
          while ( v128[v76] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
        }
        v5 = v82;
        goto LABEL_30;
      }
      v5 = v82;
      v10 = PlaiSafeArrayToStrings(v82, (unsigned __int16 **)a3 + 27);
      if ( v10 >= 0 )
      {
        v10 = PlaiSafeArrayToStrings(Vector, (unsigned __int16 **)a3 + 26);
        if ( v10 >= 0 )
          goto LABEL_30;
        v81 = 0;
        v80 = v10;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_30;
        }
        PlaiWhoAmI(v130, 0x4000000000000800uLL);
        v78 = -1;
        do
          ++v78;
        while ( v130[v78] );
      }
      else
      {
        v81 = 0;
        v80 = v10;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_30;
        }
        PlaiWhoAmI(v129, 0x4000000000000800uLL);
        v77 = -1;
        do
          ++v77;
        while ( v129[v77] );
      }
LABEL_283:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
      goto LABEL_30;
    }
    if ( v87 )
    {
      ((void (__fastcall *)(struct ITraceDataProvider *))v87->lpVtbl->Release)(v87);
      v87 = 0;
    }
    PlaiVariantClear(&v95);
    (*(void (__fastcall **)(__int64, __int64, struct tagVARIANT *, int *))(*(_QWORD *)v92 + 24LL))(v92, 1, &v95, &v94);
    v46 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct ITraceDataProvider **))v95.llVal)(
            v95.llVal,
            &IID_ITraceDataProvider,
            &v87);
    v81 = 0;
    v10 = v46;
    if ( v46 < 0 )
    {
      v80 = v46;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v127, 0x4000000000000800uLL);
        v73 = -1;
        do
          ++v73;
        while ( v127[v73] );
LABEL_194:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
      }
      goto LABEL_195;
    }
    v80 = 0;
    ((void (__fastcall *)(struct ITraceDataProvider *, struct _GUID *))v87->lpVtbl->get_Guid)(v87, &Buf1);
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    v47 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v87->lpVtbl->get_KeywordsAny)(v87, &v85);
    v10 = v47;
    if ( v47 < 0 )
    {
      v81 = 0;
      v80 = v47;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v126, 0x4000000000000800uLL);
        v72 = -1;
        do
          ++v72;
        while ( v126[v72] );
        goto LABEL_194;
      }
      goto LABEL_195;
    }
    Ul = PlaiGetUlValue<IValueMap>(v85, &v80);
    v10 = Ul;
    if ( Ul < 0 )
    {
      v81 = 0;
      v80 = Ul;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v125, 0x4000000000000800uLL);
        v71 = -1;
        do
          ++v71;
        while ( v125[v71] );
        goto LABEL_194;
      }
      goto LABEL_195;
    }
    if ( !i && !memcmp_0(&Buf1, &SystemTraceControlGuid, 0x10u) )
    {
      v49 = PlaliTranslateKernelFlags((unsigned int *)a3 + 64, &v80, 1);
      v10 = v49;
      if ( v49 >= 0 )
      {
        *(_DWORD *)a3 &= ~0x400000u;
        *(_DWORD *)a3 |= 0x800000u;
        goto LABEL_178;
      }
      v81 = 0;
      v80 = v49;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v116, 0x4000000000000800uLL);
        v62 = -1;
        do
          ++v62;
        while ( v116[v62] );
        goto LABEL_194;
      }
LABEL_195:
      v5 = v82;
      v4 = psa;
      goto LABEL_30;
    }
LABEL_178:
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    v50 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v87->lpVtbl->get_Level)(v87, &v85);
    v10 = v50;
    if ( v50 < 0 )
    {
      v81 = 0;
      v80 = v50;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v124, 0x4000000000000800uLL);
        v70 = -1;
        do
          ++v70;
        while ( v124[v70] );
        goto LABEL_194;
      }
      goto LABEL_195;
    }
    v51 = PlaiGetUlValue<IValueMap>(v85, &v81);
    v10 = v51;
    if ( v51 < 0 )
    {
      v81 = 0;
      v80 = v51;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v123, 0x4000000000000800uLL);
        v69 = -1;
        do
          ++v69;
        while ( v123[v69] );
        goto LABEL_194;
      }
      goto LABEL_195;
    }
    v52 = PlaiGuidToString(&Buf1, v9, 0x400u);
    v10 = v52;
    if ( v52 < 0 )
    {
      v81 = 0;
      v80 = v52;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v122, 0x4000000000000800uLL);
        v68 = -1;
        do
          ++v68;
        while ( v122[v68] );
        goto LABEL_194;
      }
      goto LABEL_195;
    }
    v55 = PlaiAllocStringEx(v9, v53, v54);
    *((_QWORD *)ppvData + i) = v55;
    if ( !*((_QWORD *)ppvData + i) )
    {
      v10 = -2147024882;
      v80 = -2147024882;
      v81 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_195;
      }
      PlaiWhoAmI(v121, 0x4000000000000800uLL);
      v67 = -1;
      do
        ++v67;
      while ( v121[v67] );
      goto LABEL_225;
    }
    v10 = StringCchPrintfW(v9, 0x400u, L"%d", v81);
    if ( v10 < 0 )
    {
      v81 = 0;
      v80 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_195;
      }
      PlaiWhoAmI(v120, 0x4000000000000800uLL);
      v66 = -1;
      do
        ++v66;
      while ( v120[v66] );
      goto LABEL_225;
    }
    v58 = PlaiAllocStringEx(v9, v56, v57);
    *((_QWORD *)v90 + i) = v58;
    if ( !*((_QWORD *)v90 + i) )
    {
      v10 = -2147024882;
      v80 = -2147024882;
      v81 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_195;
      }
      PlaiWhoAmI(v119, 0x4000000000000800uLL);
      v65 = -1;
      do
        ++v65;
      while ( v119[v65] );
      goto LABEL_225;
    }
    v10 = StringCchPrintfW(v9, 0x400u, L"%d", v80);
    if ( v10 < 0 )
    {
      v81 = 0;
      v80 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_195;
      }
      PlaiWhoAmI(v118, 0x4000000000000800uLL);
      v64 = -1;
      do
        ++v64;
      while ( v118[v64] );
      goto LABEL_225;
    }
    v61 = PlaiAllocStringEx(v9, v59, v60);
    *((_QWORD *)v89 + i) = v61;
    if ( !*((_QWORD *)v89 + i) )
      break;
  }
  v10 = -2147024882;
  v80 = -2147024882;
  v81 = 0;
  if ( !(_DWORD)xmmword_180169738
    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
  {
    goto LABEL_195;
  }
  PlaiWhoAmI(v117, 0x4000000000000800uLL);
  v63 = -1;
  do
    ++v63;
  while ( v117[v63] );
LABEL_225:
  EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
  v5 = v82;
  v4 = psa;
LABEL_30:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v4);
    ppvData = 0;
  }
  if ( v89 )
  {
    SafeArrayUnaccessData(Vector);
    v89 = 0;
  }
  if ( v90 )
  {
    SafeArrayUnaccessData(v5);
    v90 = 0;
  }
  if ( v4 )
    SafeArrayDestroy(v4);
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( Vector )
    SafeArrayDestroy(Vector);
  PlaiVariantClear(&v95);
  if ( v9 )
    PlaiFree(v9, 1);
  if ( v85 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    v85 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    v91 = 0;
  }
  if ( v92 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    v92 = 0;
  }
  if ( v86 )
  {
    ((void (__fastcall *)(struct ITraceDataCollector *))v86->lpVtbl->Release)(v86);
    v86 = 0;
  }
  if ( v87 )
  {
    ((void (__fastcall *)(struct ITraceDataProvider *))v87->lpVtbl->Release)(v87);
    v87 = 0;
  }
  if ( v93 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005b290  mov     [rsp-8+arg_18], rbx
0x18005b295  push    rbp
0x18005b296  push    rsi
0x18005b297  push    rdi
0x18005b298  push    r12
0x18005b29a  push    r13
0x18005b29c  push    r14
0x18005b29e  push    r15
0x18005b2a0  lea     rbp, [rsp-1120h]
0x18005b2a8  mov     eax, 1220h
0x18005b2ad  call    _alloca_probe
0x18005b2b2  sub     rsp, rax
0x18005b2b5  mov     rax, cs:__security_cookie
0x18005b2bc  xor     rax, rsp
0x18005b2bf  mov     [rbp+1150h+var_40], rax
0x18005b2c6  mov     rsi, rcx
0x18005b2c9  xorps   xmm0, xmm0
0x18005b2cc  xor     ecx, ecx
0x18005b2ce  xor     eax, eax
0x18005b2d0  mov     [rbp+1150h+cElements], ecx
0x18005b2d3  mov     r15d, ecx
0x18005b2d6  mov     [rbp+1150h+var_1170], ecx
0x18005b2d9  mov     r14d, ecx
0x18005b2dc  mov     r13d, ecx
0x18005b2df  mov     [rbp+1150h+ppvData], rcx
0x18005b2e3  mov     [rbp+1150h+var_1190], rcx
0x18005b2e7  mov     rdi, r8
0x18005b2ea  mov     [rbp+1150h+var_1198], rcx
0x18005b2ee  mov     rbx, rdx
0x18005b2f1  mov     [rbp+1150h+var_1188], rcx
0x18005b2f5  mov     [rbp+1150h+var_1180], rcx
0x18005b2f9  mov     [rbp+1150h+var_11B0], rcx
0x18005b2fd  mov     [rbp+1150h+var_11A8], rcx
0x18005b301  mov     [rbp+1150h+var_1178], rcx
0x18005b305  mov     [rbp+1150h+var_11B8], rcx
0x18005b309  lea     rcx, [rbp+1150h+var_1168]; struct tagVARIANT *
0x18005b30d  movups  xmmword ptr [rbp+1150h+var_1168], xmm0
0x18005b311  mov     qword ptr [rbp+1150h+var_1168+10h], rax
0x18005b315  movups  [rbp+1150h+Buf1], xmm0
0x18005b319  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x18005b31e  lea     r9, byte_180147320; char *
0x18005b325  xor     r8d, r8d; int
0x18005b328  lea     edx, [r13+1]; int
0x18005b32c  mov     ecx, 800h; dwBytes
0x18005b331  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18005b336  xor     ecx, ecx
0x18005b338  mov     r12, rax
0x18005b33b  test    rax, rax
0x18005b33e  jnz     short loc_18005B3B6
0x18005b340  cmp     dword ptr cs:xmmword_180169738, ecx
0x18005b346  mov     eax, 8007000Eh
0x18005b34b  mov     ebx, eax
0x18005b34d  mov     [rsp+1250h+var_11E0], eax
0x18005b351  mov     [rsp+1250h+var_11D8], ecx
0x18005b355  jz      loc_18005B5F1
0x18005b35b  mov     rdx, 4000000000000800h; unsigned __int64
0x18005b365  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005b36c  jz      loc_18005B5F1
0x18005b372  mov     rax, cs:qword_180169748
0x18005b379  and     rax, rdx
0x18005b37c  cmp     cs:qword_180169748, rax
0x18005b383  jnz     loc_18005B5F1
0x18005b389  lea     rcx, [rbp+1150h+var_1140]; unsigned __int16 *
0x18005b38d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005b392  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b396  lea     rcx, [rbp+1150h+var_1140]
0x18005b39a  xor     edi, edi
0x18005b39c  inc     rax
0x18005b39f  cmp     [rcx+rax*2], di
0x18005b3a3  jnz     short loc_18005B39C
0x18005b3a5  lea     ecx, [rax+rax]
0x18005b3a8  lea     rax, [rbp+1150h+var_1140]
0x18005b3ac  mov     esi, 4
0x18005b3b1  jmp     loc_18005CB56
0x18005b3b6  mov     rax, [rbx]
0x18005b3b9  lea     r8, [rbp+1150h+var_11B0]
0x18005b3bd  lea     rdx, IID_ITraceDataCollector
0x18005b3c4  mov     rcx, rbx
0x18005b3c7  mov     rax, [rax]
0x18005b3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3cf  mov     ebx, eax
0x18005b3d1  xor     eax, eax
0x18005b3d3  test    ebx, ebx
0x18005b3d5  jns     short loc_18005B44A
0x18005b3d7  cmp     dword ptr cs:xmmword_180169738, eax
0x18005b3dd  mov     [rsp+1250h+var_11D8], eax
0x18005b3e1  mov     [rsp+1250h+var_11E0], ebx
0x18005b3e5  jz      loc_18005B5F1
0x18005b3eb  mov     rdx, 4000000000000800h; unsigned __int64
0x18005b3f5  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005b3fc  jz      loc_18005B5F1
0x18005b402  mov     rax, cs:qword_180169748
0x18005b409  and     rax, rdx
0x18005b40c  cmp     cs:qword_180169748, rax
0x18005b413  jnz     loc_18005B5F1
0x18005b419  lea     rcx, [rbp+1150h+var_10C0]; unsigned __int16 *
0x18005b420  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005b425  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b429  lea     rcx, [rbp+1150h+var_10C0]
0x18005b430  xor     edi, edi
0x18005b432  inc     rax
0x18005b435  cmp     [rcx+rax*2], di
0x18005b439  jnz     short loc_18005B432
0x18005b43b  lea     ecx, [rax+rax]
0x18005b43e  lea     rax, [rbp+1150h+var_10C0]
0x18005b445  jmp     loc_18005B3AC
0x18005b44a  mov     rcx, [rbp+1150h+var_11B0]
0x18005b44e  lea     rdx, [rdi+0F8h]
0x18005b455  or      dword ptr [rdi], 10200h
0x18005b45b  mov     dword ptr [rdi+18h], 1
0x18005b462  mov     rax, [rcx]
0x18005b465  mov     rax, [rax+100h]
0x18005b46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b471  mov     ebx, eax
0x18005b473  xor     eax, eax
0x18005b475  test    ebx, ebx
0x18005b477  jns     short loc_18005B4EC
0x18005b479  cmp     dword ptr cs:xmmword_180169738, eax
0x18005b47f  mov     [rsp+1250h+var_11D8], eax
0x18005b483  mov     [rsp+1250h+var_11E0], ebx
0x18005b487  jz      loc_18005B5F1
0x18005b48d  mov     rdx, 4000000000000800h; unsigned __int64
0x18005b497  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005b49e  jz      loc_18005B5F1
0x18005b4a4  mov     rax, cs:qword_180169748
0x18005b4ab  and     rax, rdx
0x18005b4ae  cmp     cs:qword_180169748, rax
0x18005b4b5  jnz     loc_18005B5F1
0x18005b4bb  lea     rcx, [rbp+1150h+var_1040]; unsigned __int16 *
0x18005b4c2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005b4c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b4cb  lea     rcx, [rbp+1150h+var_1040]
0x18005b4d2  xor     edi, edi
0x18005b4d4  inc     rax
0x18005b4d7  cmp     [rcx+rax*2], di
0x18005b4db  jnz     short loc_18005B4D4
0x18005b4dd  lea     ecx, [rax+rax]
0x18005b4e0  lea     rax, [rbp+1150h+var_1040]
0x18005b4e7  jmp     loc_18005B3AC
0x18005b4ec  mov     rax, [rsi]
0x18005b4ef  lea     rdx, [rdi+1Ch]
0x18005b4f3  mov     rcx, rsi
0x18005b4f6  mov     rax, [rax+0E0h]
0x18005b4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b502  mov     ebx, eax
0x18005b504  xor     eax, eax
0x18005b506  test    ebx, ebx
0x18005b508  jns     loc_18005B732
0x18005b50e  cmp     dword ptr cs:xmmword_180169738, eax
0x18005b514  mov     [rsp+1250h+var_11D8], eax
0x18005b518  mov     [rsp+1250h+var_11E0], ebx
0x18005b51c  jz      loc_18005B5EE
0x18005b522  mov     rdx, 4000000000000800h; unsigned __int64
0x18005b52c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005b533  jz      loc_18005B5EE
0x18005b539  mov     rax, cs:qword_180169748
0x18005b540  and     rax, rdx
0x18005b543  cmp     cs:qword_180169748, rax
0x18005b54a  jnz     loc_18005B5EE
0x18005b550  lea     rcx, [rbp+1150h+var_FC0]; unsigned __int16 *
0x18005b557  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005b55c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b560  lea     rcx, [rbp+1150h+var_FC0]
0x18005b567  xor     edi, edi
0x18005b569  inc     rax
0x18005b56c  cmp     [rcx+rax*2], di
0x18005b570  jnz     short loc_18005B569
0x18005b572  lea     ecx, [rax+rax]
0x18005b575  mov     esi, 4
0x18005b57a  add     rcx, 2
0x18005b57e  lea     rax, [rbp+1150h+var_FC0]
0x18005b585  mov     [rsp+1250h+var_11F0], rcx
0x18005b58a  lea     r9, [rsp+1250h+var_11E0]
0x18005b58f  mov     [rsp+1250h+var_11F8], rax
0x18005b594  lea     rdx, PLA_EVENT_ERROR
0x18005b59b  mov     [rsp+1250h+var_1200], 1Ch
0x18005b5a4  lea     rax, aLtracedatacoll_0; "LTraceDataCollector::Commit"
0x18005b5ab  mov     [rsp+1250h+var_1208], rax
0x18005b5b0  lea     r8d, [rsi+1]
0x18005b5b4  mov     [rsp+1250h+var_1210], rsi
0x18005b5b9  lea     rax, [rsp+1250h+var_11D8]
0x18005b5be  mov     [rsp+1250h+var_1218], rax
0x18005b5c3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005b5ca  lea     rax, byte_180147320
0x18005b5d1  mov     [rsp+1250h+var_1220], 1
0x18005b5da  mov     [rsp+1250h+var_1228], rax
0x18005b5df  mov     [rsp+1250h+var_1230], rsi
0x18005b5e4  call    EventingWriteEvent
0x18005b5e9  mov     r14, rdi
0x18005b5ec  jmp     short loc_18005B5F3
0x18005b5ee  mov     r14, r13
0x18005b5f1  xor     edi, edi
0x18005b5f3  cmp     [rbp+1150h+ppvData], rdi
0x18005b5f7  jz      short loc_18005B606
0x18005b5f9  mov     rcx, r15; psa
0x18005b5fc  call    cs:__imp_SafeArrayUnaccessData
0x18005b602  mov     [rbp+1150h+ppvData], rdi
0x18005b606  cmp     [rbp+1150h+var_1198], rdi
0x18005b60a  jz      short loc_18005B619
0x18005b60c  mov     rcx, r13; psa
0x18005b60f  call    cs:__imp_SafeArrayUnaccessData
0x18005b615  mov     [rbp+1150h+var_1198], rdi
0x18005b619  cmp     [rbp+1150h+var_1190], rdi
0x18005b61d  jz      short loc_18005B62C
0x18005b61f  mov     rcx, r14; psa
0x18005b622  call    cs:__imp_SafeArrayUnaccessData
0x18005b628  mov     [rbp+1150h+var_1190], rdi
0x18005b62c  test    r15, r15
0x18005b62f  jz      short loc_18005B63A
0x18005b631  mov     rcx, r15; psa
0x18005b634  call    cs:__imp_SafeArrayDestroy
0x18005b63a  xor     r15d, r15d
0x18005b63d  test    r14, r14
0x18005b640  jz      short loc_18005B64B
0x18005b642  mov     rcx, r14; psa
0x18005b645  call    cs:__imp_SafeArrayDestroy
0x18005b64b  test    r13, r13
0x18005b64e  jz      short loc_18005B659
0x18005b650  mov     rcx, r13; psa
0x18005b653  call    cs:__imp_SafeArrayDestroy
0x18005b659  lea     rcx, [rbp+1150h+var_1168]; struct tagVARIANT *
0x18005b65d  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18005b662  test    r12, r12
0x18005b665  jz      short loc_18005B674
0x18005b667  mov     edx, 1; int
0x18005b66c  mov     rcx, r12; lpMem
0x18005b66f  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18005b674  mov     rcx, [rbp+1150h+var_11B8]
0x18005b678  test    rcx, rcx
0x18005b67b  jz      short loc_18005B68D
0x18005b67d  mov     rax, [rcx]
0x18005b680  mov     rax, [rax+10h]
0x18005b684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b689  mov     [rbp+1150h+var_11B8], r15
0x18005b68d  mov     rcx, [rbp+1150h+var_1188]
0x18005b691  test    rcx, rcx
0x18005b694  jz      short loc_18005B6A6
0x18005b696  mov     rax, [rcx]
0x18005b699  mov     rax, [rax+10h]
0x18005b69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6a2  mov     [rbp+1150h+var_1188], r15
0x18005b6a6  mov     rcx, [rbp+1150h+var_1180]
0x18005b6aa  test    rcx, rcx
0x18005b6ad  jz      short loc_18005B6BF
0x18005b6af  mov     rax, [rcx]
0x18005b6b2  mov     rax, [rax+10h]
0x18005b6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6bb  mov     [rbp+1150h+var_1180], r15
0x18005b6bf  mov     rcx, [rbp+1150h+var_11B0]
0x18005b6c3  test    rcx, rcx
0x18005b6c6  jz      short loc_18005B6D8
0x18005b6c8  mov     rax, [rcx]
0x18005b6cb  mov     rax, [rax+10h]
0x18005b6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6d4  mov     [rbp+1150h+var_11B0], r15
0x18005b6d8  mov     rcx, [rbp+1150h+var_11A8]
0x18005b6dc  test    rcx, rcx
0x18005b6df  jz      short loc_18005B6F1
0x18005b6e1  mov     rax, [rcx]
0x18005b6e4  mov     rax, [rax+10h]
0x18005b6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6ed  mov     [rbp+1150h+var_11A8], r15
0x18005b6f1  mov     rcx, [rbp+1150h+var_1178]
0x18005b6f5  test    rcx, rcx
0x18005b6f8  jz      short loc_18005B706
0x18005b6fa  mov     rax, [rcx]
0x18005b6fd  mov     rax, [rax+10h]
0x18005b701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b706  mov     eax, ebx
0x18005b708  mov     rcx, [rbp+1150h+var_40]
0x18005b70f  xor     rcx, rsp; StackCookie
0x18005b712  call    __security_check_cookie
0x18005b717  mov     rbx, [rsp+1250h+arg_18]
0x18005b71f  add     rsp, 1220h
0x18005b726  pop     r15
0x18005b728  pop     r14
0x18005b72a  pop     r13
0x18005b72c  pop     r12
0x18005b72e  pop     rdi
0x18005b72f  pop     rsi
0x18005b730  pop     rbp
0x18005b731  retn
0x18005b732  mov     esi, 4
0x18005b737  cmp     [rdi+1Ch], eax
0x18005b73a  jz      short loc_18005B73E
0x18005b73c  or      [rdi], esi
0x18005b73e  mov     rcx, [rbp+1150h+var_11B0]
0x18005b742  lea     rdx, [rdi+0FCh]
0x18005b749  bts     dword ptr [rdi], 15h
0x18005b74d  mov     rax, [rcx]
0x18005b750  mov     rax, [rax+160h]
0x18005b757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b75c  mov     ebx, eax
0x18005b75e  test    eax, eax
0x18005b760  jns     loc_18005B844
0x18005b766  cmp     dword ptr cs:xmmword_180169738, r14d
0x18005b76d  mov     [rsp+1250h+var_11D8], r14d
0x18005b772  mov     [rsp+1250h+var_11E0], eax
0x18005b776  jz      loc_18005B5EE
0x18005b77c  mov     rdx, 4000000000000800h; unsigned __int64
  ... truncated ...
```
