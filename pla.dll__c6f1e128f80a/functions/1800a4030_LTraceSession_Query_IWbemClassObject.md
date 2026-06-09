# LTraceSession::Query(IWbemClassObject *)

- ea: `0x1800a4030`
- end: `0x1800a639e`
- name: `?Query@LTraceSession@@MEAAJPEAUIWbemClassObject@@@Z`
- size: `9070`
- prototype: `__int64 __fastcall(LTraceSession *__hidden this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180002ee4`
- `0x180004e98`
- `0x180018420`
- `0x1800198b0`
- `0x180024ea0`
- `0x180026850`
- `0x18002d820`
- `0x1800a4030`
- `0x18013aee0`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800a470e`
- `msvcrt!wcsrchr` at `0x1800a470e`
- `msvcrt!wcsstr` at `0x1800a508f`
- `msvcrt!wcsstr` at `0x1800a508f`
- `msvcrt!_wcsicmp` at `0x1800a491a`
- `msvcrt!_wcsicmp` at `0x1800a4934`
- `msvcrt!_wcsicmp` at `0x1800a494e`
- `msvcrt!_wcsicmp` at `0x1800a491a`
- `msvcrt!_wcsicmp` at `0x1800a4934`
- `msvcrt!_wcsicmp` at `0x1800a494e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a5f7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4176`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a5d0f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a5d0f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5fd8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5fe9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5ff7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5fd8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5fe9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800a5ff7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a566e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a58a0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a5ad8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a566e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a58a0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800a5ad8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5767`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5996`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5bcb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5767`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5996`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800a5bcb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a57db`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a5a0a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a5c4b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a57db`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a5a0a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800a5c4b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fa0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fc6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fa0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800a5fc6`

## pseudocode

```c
__int64 __fastcall LTraceSession::Query(LTraceSession *this, struct IWbemClassObject *a2)
{
  DataCollectorSet *v2; // rbx
  TraceDataProvider *Class; // r15
  SAFEARRAY *v4; // r13
  LONGLONG v5; // r14
  SAFEARRAY *v6; // r12
  int v8; // eax
  int v9; // edi
  __int64 v10; // rbx
  int *v11; // r9
  int *v12; // rax
  int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // rbx
  unsigned int v21; // r12d
  int v22; // eax
  const char *v23; // rdx
  int v24; // r8d
  __int64 v25; // rbx
  OLECHAR *v26; // rax
  const unsigned __int16 *v27; // rdi
  wchar_t *v28; // rax
  const char *v29; // rdx
  int v30; // r8d
  OLECHAR *v31; // rax
  _WORD *v32; // rbx
  int v33; // eax
  __int64 v34; // rbx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rbx
  __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rbx
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rbx
  __int64 v44; // rbx
  int v45; // eax
  __int64 v46; // rbx
  __int64 v47; // rbx
  int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rbx
  int v51; // eax
  __int64 v52; // rbx
  __int64 v53; // rbx
  const wchar_t *bstrVal; // rcx
  struct _MODEFLAG near **v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rbx
  __int64 v58; // rdx
  int v59; // eax
  __int64 v60; // rdx
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  SAFEARRAY *parray; // rax
  SAFEARRAY *v66; // r14
  HRESULT UBound; // eax
  HRESULT LBound; // eax
  HRESULT v69; // eax
  SAFEARRAY *v70; // rcx
  HRESULT v71; // eax
  HRESULT v72; // eax
  HRESULT v73; // eax
  SAFEARRAY *v74; // rcx
  HRESULT v75; // eax
  HRESULT v76; // eax
  HRESULT v77; // eax
  LONG i; // r14d
  const OLECHAR *v79; // rcx
  HRESULT v80; // eax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v85; // [rsp+48h] [rbp-B8h]
  __int64 v86; // [rsp+50h] [rbp-B0h]
  int v87; // [rsp+70h] [rbp-90h] BYREF
  DataCollectorSet *v88; // [rsp+78h] [rbp-88h] BYREF
  LONGLONG llVal; // [rsp+80h] [rbp-80h]
  LONGLONG v90; // [rsp+90h] [rbp-70h]
  __int64 v91; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT String2; // [rsp+A0h] [rbp-60h] BYREF
  GUID v93; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D0h] [rbp-30h]
  __int64 *v95; // [rsp+E0h] [rbp-20h] BYREF
  LONG v96; // [rsp+E8h] [rbp-18h] BYREF
  LONG v97; // [rsp+ECh] [rbp-14h] BYREF
  LONG plLbound; // [rsp+F0h] [rbp-10h] BYREF
  LONG plUbound; // [rsp+F4h] [rbp-Ch] BYREF
  LONG v100; // [rsp+F8h] [rbp-8h] BYREF
  LONG v101; // [rsp+FCh] [rbp-4h] BYREF
  void *ppvData; // [rsp+100h] [rbp+0h] BYREF
  void *v103; // [rsp+108h] [rbp+8h] BYREF
  void *v104; // [rsp+110h] [rbp+10h] BYREF
  __int64 v105; // [rsp+118h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+120h] [rbp+20h]
  BSTR v107; // [rsp+128h] [rbp+28h]
  LTraceSession *v108; // [rsp+130h] [rbp+30h]
  struct tagVARIANT v109; // [rsp+138h] [rbp+38h] BYREF
  GUID pclsid; // [rsp+150h] [rbp+50h] BYREF
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
  unsigned __int16 v140[64]; // [rsp+FE0h] [rbp+EE0h] BYREF
  unsigned __int16 v141[64]; // [rsp+1060h] [rbp+F60h] BYREF
  unsigned __int16 v142[64]; // [rsp+10E0h] [rbp+FE0h] BYREF
  unsigned __int16 v143[64]; // [rsp+1160h] [rbp+1060h] BYREF
  unsigned __int16 v144[64]; // [rsp+11E0h] [rbp+10E0h] BYREF
  unsigned __int16 v145[64]; // [rsp+1260h] [rbp+1160h] BYREF
  unsigned __int16 v146[64]; // [rsp+12E0h] [rbp+11E0h] BYREF
  unsigned __int16 v147[64]; // [rsp+1360h] [rbp+1260h] BYREF
  unsigned __int16 v148[64]; // [rsp+13E0h] [rbp+12E0h] BYREF
  unsigned __int16 v149[64]; // [rsp+1460h] [rbp+1360h] BYREF
  unsigned __int16 v150[64]; // [rsp+14E0h] [rbp+13E0h] BYREF
  unsigned __int16 v151[64]; // [rsp+1560h] [rbp+1460h] BYREF
  unsigned __int16 v152[64]; // [rsp+15E0h] [rbp+14E0h] BYREF
  unsigned __int16 v153[64]; // [rsp+1660h] [rbp+1560h] BYREF
  unsigned __int16 v154[64]; // [rsp+16E0h] [rbp+15E0h] BYREF
  unsigned __int16 v155[64]; // [rsp+1760h] [rbp+1660h] BYREF
  unsigned __int16 v156[64]; // [rsp+17E0h] [rbp+16E0h] BYREF

  v108 = this;
  v105 = 0;
  *(_QWORD *)&v93.Data1 = 0;
  v2 = this;
  v95 = 0;
  memset(&String2, 0, sizeof(String2));
  Class = 0;
  v91 = 0;
  memset(&v109, 0, sizeof(v109));
  v4 = 0;
  v5 = 0;
  pclsid = 0;
  v90 = 0;
  v6 = 0;
  ppvData = 0;
  v104 = 0;
  v103 = 0;
  plUbound = 0;
  plLbound = 0;
  v100 = 0;
  v96 = 0;
  v101 = 0;
  v97 = 0;
  bstrString = 0;
  v107 = 0;
  PlaiVariantInit(&v109);
  PlaiVariantInit(&String2);
  v87 = *((_DWORD *)v2 + 14);
  v88 = v2;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "LTraceSession::Query", 21, &v88, 8, &v87, 4, v85, v86);
  }
  if ( *((_DWORD *)v2 + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 16));
  v8 = (*(__int64 (__fastcall **)(DataCollectorSet *, __int64 *))(*(_QWORD *)v2 + 648LL))(v2, &v91);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
            a2,
            L"__SERVER",
            0,
            &String2,
            0,
            0);
    v9 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v112, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v112[v14] );
      goto LABEL_22;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"Name",
           0,
           &v109,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v113, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v113[v15] );
      goto LABEL_22;
    }
    v9 = DataCollectorSet::Query(v2, v109.bstrVal, String2.bstrVal);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v114, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v114[v16] );
      goto LABEL_22;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v91 + 200LL))(v91, v109.llVal);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v115, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v115[v17] );
      goto LABEL_22;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v91 + 528LL))(v91, v109.llVal);
    v9 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v18;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v116, 0x4000000000000800uLL);
      v19 = -1;
      do
        ++v19;
      while ( v116[v19] );
      goto LABEL_22;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"LogFileName",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_348;
      }
      PlaiWhoAmI(v117, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v117[v20] );
LABEL_22:
      v11 = &v87;
      v12 = (int *)&v88;
LABEL_14:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        v11,
        4,
        qword_180147320,
        1,
        v12,
        4,
        "LTraceSession::Query",
        21);
LABEL_15:
      v4 = 0;
      goto LABEL_348;
    }
    v21 = 3;
    if ( String2.llVal && *String2.bstrVal )
    {
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 136LL))(v91);
      v6 = 0;
      v9 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_15;
        }
        PlaiWhoAmI(v118, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v118[v25] );
        goto LABEL_22;
      }
      v26 = PlaiAllocStringEx(String2.bstrVal, v23, v24);
      bstrString = v26;
      v27 = v26;
      if ( !v26
        || ((v28 = wcsrchr(v26, 0x5Cu)) != 0
          ? (v32 = v28 + 1, v31 = PlaiAllocStringEx(v28 + 1, v29, v30), *v32 = 0, v2 = v108)
          : (DataCollectorSet *)(v31 = PlaiAllocStringEx(v27, v29, v30), *v27 = 0),
            (v107 = v31) == 0) )
      {
        v9 = -2147024882;
        goto LABEL_15;
      }
      v33 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v91 + 88LL))(v91, v31);
      v9 = v33;
      if ( v33 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v33;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_15;
        }
        PlaiWhoAmI(v119, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v119[v34] );
        goto LABEL_22;
      }
      v21 = 1;
      v9 = (*(__int64 (__fastcall **)(DataCollectorSet *, BSTR))(*(_QWORD *)v2 + 184LL))(v2, bstrString);
      if ( v9 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_87;
        }
        PlaiWhoAmI(v120, 0x4000000000000800uLL);
        v35 = -1;
        do
          ++v35;
        while ( v120[v35] );
        goto LABEL_86;
      }
    }
    PlaiVariantClear(&String2);
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"ClockType",
           0,
           &String2,
           0,
           0) >= 0 )
    {
      if ( _wcsicmp(L"system", String2.bstrVal) )
        v36 = _wcsicmp(L"perf", String2.bstrVal) ? 3 - (unsigned int)(_wcsicmp(L"cycle", String2.bstrVal) != 0) : 1LL;
      else
        v36 = 2;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v91 + 312LL))(v91, v36);
      if ( v9 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_87;
        }
        PlaiWhoAmI(v121, 0x4000000000000800uLL);
        v37 = -1;
        do
          ++v37;
        while ( v121[v37] );
        goto LABEL_86;
      }
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"BufferSize",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v122, 0x4000000000000800uLL);
      v38 = -1;
      do
        ++v38;
      while ( v122[v38] );
      goto LABEL_86;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 264LL))(v91, String2.cyVal.Lo);
    v9 = v39;
    if ( v39 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v39;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v123, 0x4000000000000800uLL);
        v40 = -1;
        do
          ++v40;
        while ( v123[v40] );
LABEL_86:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v87,
          4,
          qword_180147320,
          1,
          &v88,
          4,
          "LTraceSession::Query",
          21);
LABEL_87:
        v6 = (SAFEARRAY *)v5;
        v4 = (SAFEARRAY *)v5;
        goto LABEL_348;
      }
      goto LABEL_205;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"MinimumBuffers",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v124, 0x4000000000000800uLL);
      v41 = -1;
      do
        ++v41;
      while ( v124[v41] );
      goto LABEL_86;
    }
    v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 432LL))(v91, String2.cyVal.Lo);
    v9 = v42;
    if ( v42 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v42;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v125, 0x4000000000000800uLL);
        v43 = -1;
        do
          ++v43;
        while ( v125[v43] );
        goto LABEL_86;
      }
LABEL_205:
      v6 = 0;
      v4 = 0;
      goto LABEL_348;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"MaximumBuffers",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v126, 0x4000000000000800uLL);
      v44 = -1;
      do
        ++v44;
      while ( v126[v44] );
      goto LABEL_86;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 416LL))(v91, String2.cyVal.Lo);
    v9 = v45;
    if ( v45 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v45;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v127, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v127[v46] );
        goto LABEL_86;
      }
      goto LABEL_205;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"MaximumFileSize",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v128, 0x4000000000000800uLL);
      v47 = -1;
      do
        ++v47;
      while ( v128[v47] );
      goto LABEL_86;
    }
    v48 = (*(__int64 (__fastcall **)(DataCollectorSet *, _QWORD))(*(_QWORD *)v2 + 232LL))(v2, String2.cyVal.Lo);
    v9 = v48;
    if ( v48 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v48;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v129, 0x4000000000000800uLL);
        v49 = -1;
        do
          ++v49;
        while ( v129[v49] );
        goto LABEL_86;
      }
      goto LABEL_205;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"FlushTimer",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v130, 0x4000000000000800uLL);
      v50 = -1;
      do
        ++v50;
      while ( v130[v50] );
      goto LABEL_86;
    }
    v51 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 360LL))(v91, String2.cyVal.Lo);
    v9 = v51;
    if ( v51 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v51;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v131, 0x4000000000000800uLL);
        v52 = -1;
        do
          ++v52;
        while ( v131[v52] );
        goto LABEL_86;
      }
      goto LABEL_205;
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"LogFileMode",
           0,
           &String2,
           0,
           0);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_87;
      }
      PlaiWhoAmI(v132, 0x4000000000000800uLL);
      v53 = -1;
      do
        ++v53;
      while ( v132[v53] );
      goto LABEL_86;
    }
    if ( String2.vt == 8 && (bstrVal = String2.bstrVal) != 0 )
    {
      v55 = &g_ModeFlags;
      if ( off_1801671B8 )
      {
        while ( 1 )
        {
          if ( wcsstr(bstrVal, (const wchar_t *)v55[1]) )
            LODWORD(v5) = *(_DWORD *)v55 | v5;
          v55 += 2;
          if ( !v55[1] )
            break;
          bstrVal = String2.bstrVal;
        }
      }
    }
    else
    {
      LODWORD(v5) = 1;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 344LL))(v91, (unsigned int)v5);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_193;
      }
      PlaiWhoAmI(v133, 0x4000000000000800uLL);
      v56 = -1;
      do
        ++v56;
      while ( v133[v56] );
LABEL_192:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v87,
        4,
        qword_180147320,
        1,
        &v88,
        4,
        "LTraceSession::Query",
        21);
LABEL_193:
      v5 = v90;
      goto LABEL_87;
    }
    PlaiVariantClear(&String2);
    v57 = -1;
    String2.vt = 11;
    if ( (v5 & 2) != 0 )
    {
      v58 = 0xFFFF;
      String2.iVal = -1;
    }
    else
    {
      v58 = 0;
      String2.iVal = 0;
    }
    v59 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v91 + 168LL))(v91, v58);
    v9 = v59;
    if ( v59 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v59;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        v5 = 0;
        goto LABEL_205;
      }
      PlaiWhoAmI(v134, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v134[v57] );
      goto LABEL_192;
    }
    if ( (v5 & 4) != 0 )
    {
      v60 = 0xFFFF;
      String2.iVal = -1;
    }
    else
    {
      v60 = 0;
      String2.iVal = 0;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v91 + 152LL))(v91, v60);
    if ( v9 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v9;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v135, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v135[v57] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v87,
          4,
          qword_180147320,
          1,
          &v88,
          4,
          "LTraceSession::Query",
          21);
      }
      Class = *(TraceDataProvider **)&v93.Data1;
      goto LABEL_217;
    }
    v61 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 184LL))(
            v91,
            (unsigned __int16)(((v5 & 4) != 0) - 1));
    Class = 0;
    v9 = v61;
    if ( v61 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v61;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_217;
      }
      PlaiWhoAmI(v136, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v136[v57] );
LABEL_224:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v87,
        4,
        qword_180147320,
        1,
        &v88,
        4,
        "LTraceSession::Query",
        21);
LABEL_217:
      v5 = (LONGLONG)Class;
      v6 = (SAFEARRAY *)Class;
      v4 = (SAFEARRAY *)Class;
      goto LABEL_348;
    }
    if ( (v5 & 0x100) != 0 )
      v21 = 3;
    v62 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 560LL))(v91, v21);
    v9 = v62;
    if ( v62 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v62;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_217;
      }
      PlaiWhoAmI(v137, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v137[v57] );
      goto LABEL_224;
    }
    v63 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v91 + 568LL))(v91, &v105);
    v9 = v63;
    if ( v63 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v63;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_217;
      }
      PlaiWhoAmI(v138, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v138[v57] );
      goto LABEL_224;
    }
    v64 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const WCHAR *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
            a2,
            L"Guid",
            0,
            &String2,
            0,
            0);
    v9 = v64;
    if ( v64 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v64;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_217;
      }
      PlaiWhoAmI(v139, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v139[v57] );
      goto LABEL_224;
    }
    if ( String2.vt != 8200 )
      goto LABEL_217;
    parray = String2.parray;
    if ( !String2.llVal )
      goto LABEL_217;
    llVal = String2.llVal;
    String2.llVal = 0;
    v66 = parray;
    UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    v9 = UBound;
    if ( UBound < 0 )
    {
      LODWORD(v88) = 0;
      v87 = UBound;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_257;
      }
      PlaiWhoAmI(v140, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v140[v57] );
LABEL_256:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v87,
        4,
        qword_180147320,
        1,
        &v88,
        4,
        "LTraceSession::Query",
        21);
LABEL_257:
      v5 = 0;
      v6 = 0;
LABEL_347:
      v4 = (SAFEARRAY *)llVal;
      goto LABEL_348;
    }
    LBound = SafeArrayGetLBound(v66, 1u, &plLbound);
    v9 = LBound;
    if ( LBound < 0 )
    {
      LODWORD(v88) = 0;
      v87 = LBound;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_257;
      }
      PlaiWhoAmI(v141, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v141[v57] );
      goto LABEL_256;
    }
    v69 = SafeArrayAccessData(v66, &ppvData);
    v9 = v69;
    if ( v69 < 0 )
    {
      LODWORD(v88) = 0;
      v87 = v69;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_257;
      }
      PlaiWhoAmI(v142, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v142[v57] );
      goto LABEL_256;
    }
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"EnableFlags",
           0,
           &String2,
           0,
           0) < 0
      || String2.vt == 1 )
    {
      v6 = 0;
    }
    else
    {
      v6 = String2.parray;
      v70 = String2.parray;
      String2.llVal = 0;
      v71 = SafeArrayGetUBound(v70, 1u, &v100);
      v9 = v71;
      if ( v71 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v71;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_281;
        }
        PlaiWhoAmI(v143, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v143[v57] );
LABEL_280:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v87,
          4,
          qword_180147320,
          1,
          &v88,
          4,
          "LTraceSession::Query",
          21);
LABEL_281:
        v5 = 0;
        goto LABEL_347;
      }
      v72 = SafeArrayGetLBound(v6, 1u, &v96);
      v9 = v72;
      if ( v72 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v72;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_281;
        }
        PlaiWhoAmI(v144, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v144[v57] );
        goto LABEL_280;
      }
      v73 = SafeArrayAccessData(v6, &v103);
      v9 = v73;
      if ( v73 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v73;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_281;
        }
        PlaiWhoAmI(v145, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v145[v57] );
        goto LABEL_280;
      }
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"Level",
           0,
           &String2,
           0,
           0);
    if ( !v9 && String2.vt != 1 )
    {
      v5 = String2.llVal;
      v74 = String2.parray;
      v90 = String2.llVal;
      String2.llVal = 0;
      v75 = SafeArrayGetUBound(v74, 1u, &v101);
      v9 = v75;
      if ( v75 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v75;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_347;
        }
        PlaiWhoAmI(v146, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v146[v57] );
        goto LABEL_305;
      }
      v76 = SafeArrayGetLBound((SAFEARRAY *)v5, 1u, &v97);
      v9 = v76;
      if ( v76 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v76;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_347;
        }
        PlaiWhoAmI(v147, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v147[v57] );
        goto LABEL_305;
      }
      v77 = SafeArrayAccessData((SAFEARRAY *)v5, &v104);
      v9 = v77;
      if ( v77 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v77;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_347;
        }
        PlaiWhoAmI(v148, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v148[v57] );
LABEL_305:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v87,
          4,
          qword_180147320,
          1,
          &v88,
          4,
          "LTraceSession::Query",
          21);
        goto LABEL_347;
      }
    }
    for ( i = plLbound; ; ++i )
    {
      if ( i > plUbound )
        goto LABEL_346;
      Class = CreateClassObject<TraceDataProvider>((__int64)qword_180147320, 0);
      if ( !Class )
      {
        v9 = -2147024882;
        v87 = -2147024882;
        LODWORD(v88) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v156, 0x4000000000000800uLL);
          do
            ++v57;
          while ( v156[v57] );
          goto LABEL_345;
        }
        goto LABEL_346;
      }
      v79 = (const OLECHAR *)*((_QWORD *)ppvData + i - plLbound);
      if ( !v79 )
      {
        v9 = -2147024809;
        v80 = -2147024809;
LABEL_402:
        v87 = v80;
        LODWORD(v88) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v155, 0x4000000000000800uLL);
          do
            ++v57;
          while ( v155[v57] );
          goto LABEL_345;
        }
        goto LABEL_346;
      }
      v80 = CLSIDFromString(v79, &pclsid);
      v9 = v80;
      if ( v80 < 0 )
        goto LABEL_402;
      v81 = *(_QWORD *)Class;
      v93 = pclsid;
      v9 = (*(__int64 (__fastcall **)(TraceDataProvider *, GUID *))(v81 + 80))(Class, &v93);
      if ( v9 < 0 )
        break;
      if ( v95 )
      {
        (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
        v95 = 0;
      }
      v9 = (*(__int64 (__fastcall **)(TraceDataProvider *, __int64 **))(*(_QWORD *)Class + 96LL))(Class, &v95);
      if ( v9 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_346;
        }
        PlaiWhoAmI(v153, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v153[v57] );
LABEL_345:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v87,
          4,
          qword_180147320,
          1,
          &v88,
          4,
          "LTraceSession::Query",
          21);
        goto LABEL_346;
      }
      if ( i >= v96 && i <= v100 )
      {
        pRecInfo = String2.pRecInfo;
        String2.vt = 3;
        String2.lVal = *((_DWORD *)v103 + i - v96);
        v82 = *v95;
        v93 = *(GUID *)&String2.vt;
        v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *))(v82 + 128))(v95, &v93);
        if ( v9 < 0 )
        {
          LODWORD(v88) = 0;
          v87 = v9;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_346;
          }
          PlaiWhoAmI(v149, 0x4000000000000800uLL);
          do
            ++v57;
          while ( v149[v57] );
          goto LABEL_345;
        }
      }
      if ( v95 )
      {
        (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
        v95 = 0;
      }
      v9 = (*(__int64 (__fastcall **)(TraceDataProvider *, __int64 **))(*(_QWORD *)Class + 88LL))(Class, &v95);
      if ( v9 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_346;
        }
        PlaiWhoAmI(v152, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v152[v57] );
        goto LABEL_345;
      }
      if ( i >= v97 && i <= v101 )
      {
        pRecInfo = String2.pRecInfo;
        String2.vt = 3;
        String2.lVal = *((_DWORD *)v104 + i - v97);
        v83 = *v95;
        v93 = *(GUID *)&String2.vt;
        v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *))(v83 + 128))(v95, &v93);
        if ( v9 < 0 )
        {
          LODWORD(v88) = 0;
          v87 = v9;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_346;
          }
          PlaiWhoAmI(v150, 0x4000000000000800uLL);
          do
            ++v57;
          while ( v150[v57] );
          goto LABEL_345;
        }
      }
      v9 = (*(__int64 (__fastcall **)(__int64, TraceDataProvider *))(*(_QWORD *)v105 + 80LL))(v105, Class);
      if ( v9 < 0 )
      {
        LODWORD(v88) = 0;
        v87 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_346;
        }
        PlaiWhoAmI(v151, 0x4000000000000800uLL);
        do
          ++v57;
        while ( v151[v57] );
        goto LABEL_345;
      }
    }
    LODWORD(v88) = 0;
    v87 = v9;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v154, 0x4000000000000800uLL);
      do
        ++v57;
      while ( v154[v57] );
      goto LABEL_345;
    }
LABEL_346:
    v5 = v90;
    goto LABEL_347;
  }
  v87 = 0;
  LODWORD(v88) = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v111, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v111[v10] );
    v11 = (int *)&v88;
    v12 = &v87;
    goto LABEL_14;
  }
LABEL_348:
  if ( *((_DWORD *)v108 + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v108 + 16));
  PlaiVariantClear(&String2);
  PlaiVariantClear(&v109);
  if ( ppvData )
  {
    SafeArrayUnaccessData(v4);
    ppvData = 0;
  }
  if ( v103 )
  {
    SafeArrayUnaccessData(v6);
    v103 = 0;
  }
  if ( v104 )
  {
    SafeArrayUnaccessData((SAFEARRAY *)v5);
    v104 = 0;
  }
  if ( v4 )
    SafeArrayDestroy(v4);
  if ( v6 )
    SafeArrayDestroy(v6);
  if ( v5 )
    SafeArrayDestroy((SAFEARRAY *)v5);
  if ( Class )
    (*(void (__fastcall **)(TraceDataProvider *))(*(_QWORD *)Class + 16LL))(Class);
  if ( v95 )
  {
    (*(void (__fastcall **)(__int64 *))(*v95 + 16))(v95);
    v95 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    v91 = 0;
  }
  if ( v105 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
    v105 = 0;
  }
  PlaiFreeString(bstrString);
  PlaiFreeString(v107);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a4030  mov     [rsp-8+arg_10], rbx
0x1800a4035  push    rbp
0x1800a4036  push    rsi
0x1800a4037  push    rdi
0x1800a4038  push    r12
0x1800a403a  push    r13
0x1800a403c  push    r14
0x1800a403e  push    r15
0x1800a4040  lea     rbp, [rsp-1770h]
0x1800a4048  mov     eax, 1870h
0x1800a404d  call    _alloca_probe
0x1800a4052  sub     rsp, rax
0x1800a4055  mov     rax, cs:__security_cookie
0x1800a405c  xor     rax, rsp
0x1800a405f  mov     [rbp+17A0h+var_40], rax
0x1800a4066  xor     edi, edi
0x1800a4068  mov     [rbp+17A0h+var_1770], rcx
0x1800a406c  xorps   xmm0, xmm0
0x1800a406f  mov     [rbp+17A0h+var_1788], rdi
0x1800a4073  xor     eax, eax
0x1800a4075  mov     qword ptr [rbp+17A0h+var_17E0], rdi
0x1800a4079  mov     rbx, rcx
0x1800a407c  mov     [rbp+17A0h+var_17F0], rax
0x1800a4080  xorps   xmm1, xmm1
0x1800a4083  mov     qword ptr [rbp+17A0h+var_1768+10h], rax
0x1800a4087  lea     rcx, [rbp+17A0h+var_1768]; struct tagVARIANT *
0x1800a408b  mov     [rbp+17A0h+var_17C0], rdi
0x1800a408f  movups  xmmword ptr [rbp+17A0h+String2], xmm0
0x1800a4093  mov     r15d, edi
0x1800a4096  mov     [rbp+17A0h+var_1808], rdi
0x1800a409a  movups  xmmword ptr [rbp+17A0h+var_1768], xmm1
0x1800a409e  mov     r13d, edi
0x1800a40a1  mov     r14d, edi
0x1800a40a4  movups  xmmword ptr [rbp+17A0h+pclsid.Data1], xmm0
0x1800a40a8  mov     [rbp+17A0h+var_1810], rdi
0x1800a40ac  mov     r12d, edi
0x1800a40af  mov     [rbp+17A0h+ppvData], rdi
0x1800a40b3  mov     rsi, rdx
0x1800a40b6  mov     [rbp+17A0h+var_1790], rdi
0x1800a40ba  mov     [rbp+17A0h+var_1798], rdi
0x1800a40be  mov     [rbp+17A0h+plUbound], edi
0x1800a40c1  mov     [rbp+17A0h+plLbound], edi
0x1800a40c4  mov     [rbp+17A0h+var_17A8], edi
0x1800a40c7  mov     [rbp+17A0h+var_17B8], edi
0x1800a40ca  mov     [rbp+17A0h+var_17A4], edi
0x1800a40cd  mov     [rbp+17A0h+var_17B4], edi
0x1800a40d0  mov     [rbp+17A0h+bstrString], rdi
0x1800a40d4  mov     [rbp+17A0h+var_1778], rdi
0x1800a40d8  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800a40dd  lea     rcx, [rbp+17A0h+String2]; struct tagVARIANT *
0x1800a40e1  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800a40e6  cmp     dword ptr cs:xmmword_180169738, edi
0x1800a40ec  mov     eax, [rbx+38h]
0x1800a40ef  mov     [rsp+18A0h+var_1830], eax
0x1800a40f3  mov     [rsp+18A0h+var_1828], rbx
0x1800a40f8  jz      short loc_1800A416D
0x1800a40fa  mov     rdx, 4000000000000400h
0x1800a4104  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a410b  jz      short loc_1800A416D
0x1800a410d  mov     rax, cs:qword_180169748
0x1800a4114  and     rax, rdx
0x1800a4117  cmp     cs:qword_180169748, rax
0x1800a411e  jnz     short loc_1800A416D
0x1800a4120  mov     [rsp+18A0h+var_1860], 4
0x1800a4129  lea     rax, [rsp+18A0h+var_1830]
0x1800a412e  mov     [rsp+18A0h+var_1868], rax
0x1800a4133  lea     r9, aLtracesessionQ; "LTraceSession::Query"
0x1800a413a  lea     rax, [rsp+18A0h+var_1828]
0x1800a413f  mov     [rsp+18A0h+var_1870], 8
0x1800a4148  mov     [rsp+18A0h+var_1878], rax
0x1800a414d  lea     r8d, [rdi+3]
0x1800a4151  lea     rdx, PLA_EVENT_METHOD
0x1800a4158  mov     [rsp+18A0h+var_1880], 15h
0x1800a4161  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a4168  call    EventingWriteEvent
0x1800a416d  cmp     [rbx+8], edi
0x1800a4170  jz      short loc_1800A417C
0x1800a4172  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800a4176  call    cs:__imp_EnterCriticalSection
0x1800a417c  mov     rax, [rbx]
0x1800a417f  lea     rdx, [rbp+17A0h+var_1808]
0x1800a4183  mov     rcx, rbx
0x1800a4186  mov     rax, [rax+288h]
0x1800a418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4192  xor     ecx, ecx
0x1800a4194  mov     edi, eax
0x1800a4196  test    eax, eax
0x1800a4198  jns     loc_1800A427A
0x1800a419e  cmp     dword ptr cs:xmmword_180169738, ecx
0x1800a41a4  mov     [rsp+18A0h+var_1830], ecx
0x1800a41a8  mov     dword ptr [rsp+18A0h+var_1828], eax
0x1800a41ac  jz      loc_1800A5F70
0x1800a41b2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a41bc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a41c3  jz      loc_1800A5F70
0x1800a41c9  mov     rax, cs:qword_180169748
0x1800a41d0  and     rax, rdx
0x1800a41d3  cmp     cs:qword_180169748, rax
0x1800a41da  jnz     loc_1800A5F70
0x1800a41e0  lea     rcx, [rbp+17A0h+var_1740]; unsigned __int16 *
0x1800a41e4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a41e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a41ed  lea     rax, [rbp+17A0h+var_1740]
0x1800a41f1  xor     ecx, ecx
0x1800a41f3  inc     rbx
0x1800a41f6  cmp     [rax+rbx*2], cx
0x1800a41fa  jnz     short loc_1800A41F3
0x1800a41fc  lea     rax, [rbp+17A0h+var_1740]
0x1800a4200  mov     r13d, 1
0x1800a4206  lea     ecx, [rbx+rbx]
0x1800a4209  add     rcx, 2
0x1800a420d  lea     r9, [rsp+18A0h+var_1828]
0x1800a4212  mov     [rsp+18A0h+var_1840], rcx
0x1800a4217  mov     [rsp+18A0h+var_1848], rax
0x1800a421c  lea     rax, aLtracesessionQ; "LTraceSession::Query"
0x1800a4223  mov     [rsp+18A0h+var_1850], 15h
0x1800a422c  mov     [rsp+18A0h+var_1858], rax
0x1800a4231  lea     rax, [rsp+18A0h+var_1830]
0x1800a4236  mov     edx, 4
0x1800a423b  lea     rsi, qword_180147320
0x1800a4242  mov     [rsp+18A0h+var_1860], rdx
0x1800a4247  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a424e  mov     [rsp+18A0h+var_1868], rax
0x1800a4253  mov     [rsp+18A0h+var_1870], r13
0x1800a4258  lea     r8d, [rdx+1]
0x1800a425c  mov     [rsp+18A0h+var_1878], rsi
0x1800a4261  mov     [rsp+18A0h+var_1880], rdx
0x1800a4266  lea     rdx, PLA_EVENT_ERROR
0x1800a426d  call    EventingWriteEvent
0x1800a4272  mov     r13, r12
0x1800a4275  jmp     loc_1800A5F70
0x1800a427a  mov     rax, [rsi]
0x1800a427d  lea     r9, [rbp+17A0h+String2]
0x1800a4281  mov     [rsp+18A0h+var_1878], rcx
0x1800a4286  lea     rdx, aServer; "__SERVER"
0x1800a428d  mov     [rsp+18A0h+var_1880], rcx
0x1800a4292  xor     r8d, r8d
0x1800a4295  mov     rcx, rsi
0x1800a4298  mov     rax, [rax+20h]
0x1800a429c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a42a1  xor     ecx, ecx
0x1800a42a3  mov     edi, eax
0x1800a42a5  test    eax, eax
0x1800a42a7  jns     loc_1800A4353
0x1800a42ad  cmp     dword ptr cs:xmmword_180169738, ecx
0x1800a42b3  mov     dword ptr [rsp+18A0h+var_1828], ecx
0x1800a42b7  mov     [rsp+18A0h+var_1830], eax
0x1800a42bb  jz      loc_1800A5F70
0x1800a42c1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a42cb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a42d2  jz      loc_1800A5F70
0x1800a42d8  mov     rax, cs:qword_180169748
0x1800a42df  and     rax, rdx
0x1800a42e2  cmp     cs:qword_180169748, rax
0x1800a42e9  jnz     loc_1800A5F70
0x1800a42ef  lea     rcx, [rbp+17A0h+var_16C0]; unsigned __int16 *
0x1800a42f6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a42fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a42ff  lea     rax, [rbp+17A0h+var_16C0]
0x1800a4306  xor     ecx, ecx
0x1800a4308  inc     rbx
0x1800a430b  cmp     [rax+rbx*2], cx
0x1800a430f  jnz     short loc_1800A4308
0x1800a4311  lea     rax, [rbp+17A0h+var_16C0]
0x1800a4318  mov     r13d, 1
0x1800a431e  lea     ecx, [rbx+rbx]
0x1800a4321  add     rcx, 2
0x1800a4325  lea     r9, [rsp+18A0h+var_1830]
0x1800a432a  mov     [rsp+18A0h+var_1840], rcx
0x1800a432f  mov     [rsp+18A0h+var_1848], rax
0x1800a4334  lea     rax, aLtracesessionQ; "LTraceSession::Query"
0x1800a433b  mov     [rsp+18A0h+var_1850], 15h
0x1800a4344  mov     [rsp+18A0h+var_1858], rax
0x1800a4349  lea     rax, [rsp+18A0h+var_1828]
0x1800a434e  jmp     loc_1800A4236
0x1800a4353  mov     rax, [rsi]
0x1800a4356  lea     r9, [rbp+17A0h+var_1768]
0x1800a435a  mov     [rsp+18A0h+var_1878], rcx
0x1800a435f  lea     rdx, aName; "Name"
0x1800a4366  mov     [rsp+18A0h+var_1880], rcx
0x1800a436b  xor     r8d, r8d
0x1800a436e  mov     rcx, rsi
0x1800a4371  mov     rax, [rax+20h]
0x1800a4375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a437a  mov     edi, eax
0x1800a437c  xor     eax, eax
0x1800a437e  test    edi, edi
0x1800a4380  jns     short loc_1800A43F2
0x1800a4382  cmp     dword ptr cs:xmmword_180169738, eax
0x1800a4388  mov     dword ptr [rsp+18A0h+var_1828], eax
0x1800a438c  mov     [rsp+18A0h+var_1830], edi
0x1800a4390  jz      loc_1800A5F70
0x1800a4396  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a43a0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a43a7  jz      loc_1800A5F70
0x1800a43ad  mov     rax, cs:qword_180169748
0x1800a43b4  and     rax, rdx
0x1800a43b7  cmp     cs:qword_180169748, rax
0x1800a43be  jnz     loc_1800A5F70
0x1800a43c4  lea     rcx, [rbp+17A0h+var_1640]; unsigned __int16 *
0x1800a43cb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a43d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a43d4  lea     rax, [rbp+17A0h+var_1640]
0x1800a43db  xor     ecx, ecx
0x1800a43dd  inc     rbx
0x1800a43e0  cmp     [rax+rbx*2], cx
0x1800a43e4  jnz     short loc_1800A43DD
0x1800a43e6  lea     rax, [rbp+17A0h+var_1640]
0x1800a43ed  jmp     loc_1800A4318
0x1800a43f2  mov     r8, [rbp+17A0h+String2+8]; unsigned __int16 *
0x1800a43f6  mov     rcx, rbx; this
0x1800a43f9  mov     rdx, qword ptr [rbp+17A0h+var_1768+8]; unsigned __int16 *
0x1800a43fd  call    ?Query@DataCollectorSet@@UEAAJPEAG0@Z; DataCollectorSet::Query(ushort *,ushort *)
0x1800a4402  mov     edi, eax
0x1800a4404  xor     eax, eax
0x1800a4406  test    edi, edi
0x1800a4408  jns     short loc_1800A447A
0x1800a440a  cmp     dword ptr cs:xmmword_180169738, eax
0x1800a4410  mov     dword ptr [rsp+18A0h+var_1828], eax
0x1800a4414  mov     [rsp+18A0h+var_1830], edi
0x1800a4418  jz      loc_1800A5F70
0x1800a441e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a4428  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a442f  jz      loc_1800A5F70
0x1800a4435  mov     rax, cs:qword_180169748
0x1800a443c  and     rax, rdx
0x1800a443f  cmp     cs:qword_180169748, rax
0x1800a4446  jnz     loc_1800A5F70
0x1800a444c  lea     rcx, [rbp+17A0h+var_15C0]; unsigned __int16 *
0x1800a4453  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a4458  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a445c  lea     rax, [rbp+17A0h+var_15C0]
0x1800a4463  xor     ecx, ecx
0x1800a4465  inc     rbx
0x1800a4468  cmp     [rax+rbx*2], cx
0x1800a446c  jnz     short loc_1800A4465
0x1800a446e  lea     rax, [rbp+17A0h+var_15C0]
0x1800a4475  jmp     loc_1800A4318
0x1800a447a  mov     rcx, [rbp+17A0h+var_1808]
0x1800a447e  mov     rdx, qword ptr [rbp+17A0h+var_1768+8]
0x1800a4482  mov     rax, [rcx]
0x1800a4485  mov     rax, [rax+0C8h]
0x1800a448c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4491  mov     edi, eax
0x1800a4493  xor     eax, eax
0x1800a4495  test    edi, edi
0x1800a4497  jns     short loc_1800A4509
0x1800a4499  cmp     dword ptr cs:xmmword_180169738, eax
0x1800a449f  mov     dword ptr [rsp+18A0h+var_1828], eax
0x1800a44a3  mov     [rsp+18A0h+var_1830], edi
0x1800a44a7  jz      loc_1800A5F70
0x1800a44ad  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a44b7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a44be  jz      loc_1800A5F70
0x1800a44c4  mov     rax, cs:qword_180169748
0x1800a44cb  and     rax, rdx
0x1800a44ce  cmp     cs:qword_180169748, rax
0x1800a44d5  jnz     loc_1800A5F70
0x1800a44db  lea     rcx, [rbp+17A0h+var_1540]; unsigned __int16 *
0x1800a44e2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a44e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a44eb  lea     rax, [rbp+17A0h+var_1540]
0x1800a44f2  xor     ecx, ecx
0x1800a44f4  inc     rbx
0x1800a44f7  cmp     [rax+rbx*2], cx
0x1800a44fb  jnz     short loc_1800A44F4
0x1800a44fd  lea     rax, [rbp+17A0h+var_1540]
0x1800a4504  jmp     loc_1800A4318
0x1800a4509  mov     rcx, [rbp+17A0h+var_1808]
0x1800a450d  mov     rdx, qword ptr [rbp+17A0h+var_1768+8]
0x1800a4511  mov     rax, [rcx]
0x1800a4514  mov     rax, [rax+210h]
0x1800a451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4520  xor     ecx, ecx
0x1800a4522  mov     edi, eax
0x1800a4524  test    eax, eax
0x1800a4526  jns     short loc_1800A4598
0x1800a4528  cmp     dword ptr cs:xmmword_180169738, ecx
0x1800a452e  mov     dword ptr [rsp+18A0h+var_1828], ecx
0x1800a4532  mov     [rsp+18A0h+var_1830], eax
0x1800a4536  jz      loc_1800A5F70
0x1800a453c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a4546  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a454d  jz      loc_1800A5F70
0x1800a4553  mov     rax, cs:qword_180169748
0x1800a455a  and     rax, rdx
0x1800a455d  cmp     cs:qword_180169748, rax
0x1800a4564  jnz     loc_1800A5F70
0x1800a456a  lea     rcx, [rbp+17A0h+var_14C0]; unsigned __int16 *
0x1800a4571  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a4576  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a457a  lea     rax, [rbp+17A0h+var_14C0]
0x1800a4581  xor     ecx, ecx
0x1800a4583  inc     rbx
0x1800a4586  cmp     [rax+rbx*2], cx
0x1800a458a  jnz     short loc_1800A4583
0x1800a458c  lea     rax, [rbp+17A0h+var_14C0]
0x1800a4593  jmp     loc_1800A4318
0x1800a4598  mov     rax, [rsi]
0x1800a459b  lea     r9, [rbp+17A0h+String2]
  ... truncated ...
```
