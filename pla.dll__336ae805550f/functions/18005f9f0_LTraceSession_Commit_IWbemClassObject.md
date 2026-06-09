# LTraceSession::Commit(IWbemClassObject *)

- ea: `0x18005f9f0`
- end: `0x180061a3b`
- name: `?Commit@LTraceSession@@MEAAJPEAUIWbemClassObject@@@Z`
- size: `8267`
- prototype: `__int64 __fastcall(LTraceSession *__hidden this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800182a4`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x1800429d0`
- `0x180046c60`
- `0x18005f9f0`
- `0x1801147b8`
- `0x180116404`
- `0x18011a5f8`
- `0x18013aee0`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061952`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061965`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061977`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061952`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061965`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061977`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800611fe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061288`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061311`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800611fe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061288`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180061311`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061918`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006192c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006193f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061918`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006192c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006193f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180061040`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800610d7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18006116b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180061040`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800610d7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18006116b`

## string_xrefs

- `0x18005fb34`: `LTraceSession::Commit`

## pseudocode

```c
__int64 __fastcall LTraceSession::Commit(LTraceSession *this, struct IWbemClassObject *a2)
{
  SAFEARRAY *v3; // r13
  int v5; // eax
  int Ul; // edi
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rbx
  int v14; // eax
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rcx
  int v19; // eax
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rbx
  int v31; // eax
  __int64 v32; // rbx
  int v33; // eax
  __int64 v34; // rbx
  int v35; // eax
  __int64 v36; // rbx
  int v37; // eax
  __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rbx
  int v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rbx
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  const char *v49; // r8
  int v50; // r9d
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int TraceDataProvider; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // eax
  ULONG v64; // r12d
  HRESULT v65; // eax
  HRESULT v66; // eax
  HRESULT v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  const char *v73; // rdx
  int v74; // r8d
  unsigned __int16 *v75; // rax
  __int64 v76; // rdx
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  struct IWbemClassObjectVtbl *v78; // rax
  int v80; // [rsp+70h] [rbp-90h] BYREF
  int v81; // [rsp+78h] [rbp-88h] BYREF
  struct ITraceDataCollector *v82; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  ULONG cElements; // [rsp+A8h] [rbp-58h] BYREF
  struct ITraceDataProvider *v86; // [rsp+B0h] [rbp-50h] BYREF
  int v87; // [rsp+B8h] [rbp-48h] BYREF
  SAFEARRAY *psa; // [rsp+C0h] [rbp-40h] BYREF
  SAFEARRAY *Vector; // [rsp+C8h] [rbp-38h] BYREF
  int v90; // [rsp+D0h] [rbp-30h] BYREF
  int v91; // [rsp+D4h] [rbp-2Ch] BYREF
  void *ppvData; // [rsp+D8h] [rbp-28h] BYREF
  void *v93; // [rsp+E0h] [rbp-20h] BYREF
  void *v94; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v95; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v96; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v97; // [rsp+100h] [rbp+0h] BYREF
  int v98; // [rsp+108h] [rbp+8h] BYREF
  struct _GUID v99; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v100[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v101[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v102[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v103[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v104[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v105[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v106[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v107[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v108[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v109[64]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v110[64]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int16 v111[64]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v112[64]; // [rsp+720h] [rbp+620h] BYREF
  unsigned __int16 v113[64]; // [rsp+7A0h] [rbp+6A0h] BYREF
  unsigned __int16 v114[64]; // [rsp+820h] [rbp+720h] BYREF
  unsigned __int16 v115[64]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v116[64]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v117[64]; // [rsp+9A0h] [rbp+8A0h] BYREF
  unsigned __int16 v118[64]; // [rsp+A20h] [rbp+920h] BYREF
  unsigned __int16 v119[64]; // [rsp+AA0h] [rbp+9A0h] BYREF
  unsigned __int16 v120[64]; // [rsp+B20h] [rbp+A20h] BYREF
  unsigned __int16 v121[64]; // [rsp+BA0h] [rbp+AA0h] BYREF
  unsigned __int16 v122[64]; // [rsp+C20h] [rbp+B20h] BYREF
  unsigned __int16 v123[64]; // [rsp+CA0h] [rbp+BA0h] BYREF
  unsigned __int16 v124[64]; // [rsp+D20h] [rbp+C20h] BYREF
  unsigned __int16 v125[64]; // [rsp+DA0h] [rbp+CA0h] BYREF
  unsigned __int16 v126[64]; // [rsp+E20h] [rbp+D20h] BYREF
  unsigned __int16 v127[64]; // [rsp+EA0h] [rbp+DA0h] BYREF
  unsigned __int16 v128[64]; // [rsp+F20h] [rbp+E20h] BYREF
  unsigned __int16 v129[64]; // [rsp+FA0h] [rbp+EA0h] BYREF
  unsigned __int16 v130[64]; // [rsp+1020h] [rbp+F20h] BYREF
  unsigned __int16 v131[64]; // [rsp+10A0h] [rbp+FA0h] BYREF
  unsigned __int16 v132[64]; // [rsp+1120h] [rbp+1020h] BYREF
  unsigned __int16 v133[64]; // [rsp+11A0h] [rbp+10A0h] BYREF
  unsigned __int16 v134[64]; // [rsp+1220h] [rbp+1120h] BYREF
  unsigned __int16 v135[64]; // [rsp+12A0h] [rbp+11A0h] BYREF
  unsigned __int16 v136[64]; // [rsp+1320h] [rbp+1220h] BYREF
  unsigned __int16 v137[64]; // [rsp+13A0h] [rbp+12A0h] BYREF
  unsigned __int16 v138[64]; // [rsp+1420h] [rbp+1320h] BYREF
  unsigned __int16 v139[64]; // [rsp+14A0h] [rbp+13A0h] BYREF
  unsigned __int16 v140[64]; // [rsp+1520h] [rbp+1420h] BYREF
  unsigned __int16 v141[64]; // [rsp+15A0h] [rbp+14A0h] BYREF
  unsigned __int16 v142[64]; // [rsp+1620h] [rbp+1520h] BYREF
  unsigned __int16 v143[64]; // [rsp+16A0h] [rbp+15A0h] BYREF
  unsigned __int16 v144[64]; // [rsp+1720h] [rbp+1620h] BYREF
  unsigned __int16 v145[64]; // [rsp+17A0h] [rbp+16A0h] BYREF
  unsigned __int16 v146[64]; // [rsp+1820h] [rbp+1720h] BYREF
  unsigned __int16 v147[64]; // [rsp+18A0h] [rbp+17A0h] BYREF
  unsigned __int16 v148[1024]; // [rsp+1920h] [rbp+1820h] BYREF

  v87 = 0;
  v90 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  cElements = 0;
  v3 = 0;
  v98 = 0;
  v95 = 0;
  v96 = 0;
  v82 = 0;
  v97 = 0;
  v86 = 0;
  v84 = 0;
  v91 = 0;
  v99 = 0;
  psa = 0;
  Vector = 0;
  ppvData = 0;
  v94 = 0;
  v93 = 0;
  PlaiVariantInit(&pvarg);
  v5 = (*(__int64 (__fastcall **)(LTraceSession *, struct ITraceDataCollector **))(*(_QWORD *)this + 648LL))(this, &v82);
  Ul = v5;
  if ( v5 < 0 )
  {
    v81 = 0;
    v80 = v5;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v100, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v100[v7] );
LABEL_7:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v80, 4, byte_180147320, 1, &v81, 4);
      goto LABEL_361;
    }
    goto LABEL_361;
  }
  v8 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, int *))v82->lpVtbl->get_StreamMode)(v82, &v87);
  Ul = v8;
  if ( v8 < 0 )
  {
    v81 = 0;
    v80 = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v101, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v101[v9] );
      goto LABEL_7;
    }
    goto LABEL_361;
  }
  if ( v87 != 2 )
  {
    pvarg.vt = 8;
    v10 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_OutputLocation)(
            v82,
            &pvarg.decVal.Lo32);
    Ul = v10;
    if ( v10 < 0 )
    {
      v81 = 0;
      v80 = v10;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v102, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v102[v11] );
        goto LABEL_7;
      }
      goto LABEL_361;
    }
    v12 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
            a2,
            L"LogFileName",
            0,
            &pvarg,
            0);
    Ul = v12;
    if ( v12 < 0 )
    {
      v81 = 0;
      v80 = v12;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v103, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v103[v13] );
        goto LABEL_7;
      }
      goto LABEL_361;
    }
    PlaiVariantClear(&pvarg);
  }
  v14 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, int *))v82->lpVtbl->get_ClockType)(v82, &v90);
  Ul = v14;
  if ( v14 < 0 )
  {
    v81 = 0;
    v80 = v14;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v104, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v104[v17] );
      goto LABEL_7;
    }
    goto LABEL_361;
  }
  switch ( v90 )
  {
    case 1:
      v18 = L"perf";
LABEL_44:
      v19 = PlaiSetVariantEx(v18, &pvarg, v15, v16);
      Ul = v19;
      if ( v19 < 0 )
      {
        v81 = 0;
        v80 = v19;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v105, 0x4000000000000800uLL);
          v20 = -1;
          do
            ++v20;
          while ( v105[v20] );
          goto LABEL_7;
        }
        goto LABEL_361;
      }
      break;
    case 2:
      v18 = L"system";
      goto LABEL_44;
    case 3:
      v18 = L"cycle";
      goto LABEL_44;
  }
  ((void (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
    a2,
    L"ClockType",
    0,
    &pvarg,
    0);
  PlaiVariantClear(&pvarg);
  pvarg.vt = 3;
  v21 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_BufferSize)(
          v82,
          &pvarg.decVal.Lo32);
  Ul = v21;
  if ( v21 >= 0 )
  {
    v23 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
            a2,
            L"BufferSize",
            0,
            &pvarg,
            0);
    Ul = v23;
    if ( v23 >= 0 )
    {
      v25 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_MinimumBuffers)(
              v82,
              &pvarg.decVal.Lo32);
      Ul = v25;
      if ( v25 >= 0 )
      {
        v27 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                a2,
                L"MinimumBuffers",
                0,
                &pvarg,
                0);
        Ul = v27;
        if ( v27 >= 0 )
        {
          v29 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_MaximumBuffers)(
                  v82,
                  &pvarg.decVal.Lo32);
          Ul = v29;
          if ( v29 >= 0 )
          {
            v31 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                    a2,
                    L"MaximumBuffers",
                    0,
                    &pvarg,
                    0);
            Ul = v31;
            if ( v31 >= 0 )
            {
              v33 = (*(__int64 (__fastcall **)(LTraceSession *, CY *))(*(_QWORD *)this + 224LL))(this, &pvarg.cyVal);
              Ul = v33;
              if ( v33 >= 0 )
              {
                v35 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                        a2,
                        L"MaximumFileSize",
                        0,
                        &pvarg,
                        0);
                Ul = v35;
                if ( v35 >= 0 )
                {
                  v37 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_FlushTimer)(
                          v82,
                          &pvarg.decVal.Lo32);
                  Ul = v37;
                  if ( v37 >= 0 )
                  {
                    v39 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                            a2,
                            L"FlushTimer",
                            0,
                            &pvarg,
                            0);
                    Ul = v39;
                    if ( v39 >= 0 )
                    {
                      pvarg.vt = 11;
                      v41 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_LogCircular)(
                              v82,
                              &pvarg.decVal.Lo32);
                      Ul = v41;
                      if ( v41 >= 0 )
                      {
                        v43 = -1;
                        if ( pvarg.iVal == -1 )
                        {
                          v44 = StringCchCopyW(v148, 0x400u, L"Circular");
                          Ul = v44;
                          if ( v44 < 0 )
                          {
                            v80 = v44;
                            v81 = 0;
                            if ( (_DWORD)xmmword_180169738
                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                            {
                              PlaiWhoAmI(v117, 0x4000000000000800uLL);
                              do
                                ++v43;
                              while ( v117[v43] );
                              goto LABEL_7;
                            }
                            goto LABEL_361;
                          }
                        }
                        else
                        {
                          v45 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_LogAppend)(
                                  v82,
                                  &pvarg.decVal.Lo32);
                          Ul = v45;
                          if ( v45 < 0 )
                          {
                            v81 = 0;
                            v80 = v45;
                            if ( (_DWORD)xmmword_180169738
                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                            {
                              PlaiWhoAmI(v118, 0x4000000000000800uLL);
                              do
                                ++v43;
                              while ( v118[v43] );
                              goto LABEL_7;
                            }
                            goto LABEL_361;
                          }
                          if ( pvarg.iVal == -1 )
                          {
                            v46 = StringCchCopyW(v148, 0x400u, L"Append");
                            Ul = v46;
                            if ( v46 < 0 )
                            {
                              v80 = v46;
                              v81 = 0;
                              if ( (_DWORD)xmmword_180169738
                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                              {
                                PlaiWhoAmI(v119, 0x4000000000000800uLL);
                                do
                                  ++v43;
                                while ( v119[v43] );
                                goto LABEL_7;
                              }
                              goto LABEL_361;
                            }
                          }
                          else
                          {
                            v47 = StringCchCopyW(v148, 0x400u, L"Sequential");
                            Ul = v47;
                            if ( v47 < 0 )
                            {
                              v80 = v47;
                              v81 = 0;
                              if ( (_DWORD)xmmword_180169738
                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                              {
                                PlaiWhoAmI(v120, 0x4000000000000800uLL);
                                do
                                  ++v43;
                                while ( v120[v43] );
                                goto LABEL_7;
                              }
                              goto LABEL_361;
                            }
                          }
                        }
                        v48 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, ULONG *))v82->lpVtbl->get_ProcessMode)(
                                v82,
                                &pvarg.decVal.Lo32);
                        Ul = v48;
                        if ( v48 >= 0 )
                        {
                          if ( pvarg.iVal == -1 && (v51 = StringCchCatW(v148, 0x400u, L"|Private"), Ul = v51, v51 < 0) )
                          {
                            v80 = v51;
                            v81 = 0;
                            if ( (_DWORD)xmmword_180169738
                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                            {
                              PlaiWhoAmI(v122, 0x4000000000000800uLL);
                              do
                                ++v43;
                              while ( v122[v43] );
                              goto LABEL_7;
                            }
                          }
                          else if ( (v87 == 2 || v87 == 3)
                                 && (v52 = StringCchCatW(v148, 0x400u, L"|RealTime"), Ul = v52, v52 < 0) )
                          {
                            v80 = v52;
                            v81 = 0;
                            if ( (_DWORD)xmmword_180169738
                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                            {
                              PlaiWhoAmI(v123, 0x4000000000000800uLL);
                              do
                                ++v43;
                              while ( v123[v43] );
                              goto LABEL_7;
                            }
                          }
                          else
                          {
                            v53 = PlaiSetVariantEx(v148, &pvarg, v49, v50);
                            Ul = v53;
                            if ( v53 >= 0 )
                            {
                              v54 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                                      a2,
                                      L"LogFileMode",
                                      0,
                                      &pvarg,
                                      0);
                              Ul = v54;
                              if ( v54 >= 0 )
                              {
                                v55 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, __int64 *))v82->lpVtbl->get_TraceDataProviders)(
                                        v82,
                                        &v97);
                                Ul = v55;
                                if ( v55 >= 0 )
                                {
                                  v56 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 72LL))(
                                          v97,
                                          &v96);
                                  Ul = v56;
                                  if ( v56 >= 0 )
                                  {
                                    v57 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v96)(
                                            v96,
                                            &IID_IEnumVARIANT,
                                            &v95);
                                    Ul = v57;
                                    if ( v57 >= 0 )
                                    {
                                      v58 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v97 + 56LL))(
                                              v97,
                                              &cElements);
                                      Ul = v58;
                                      if ( v58 >= 0 )
                                      {
                                        TraceDataProvider = TraceDataCollector::get_TraceDataProvider(v82, &v86);
                                        Ul = TraceDataProvider;
                                        if ( TraceDataProvider >= 0 )
                                        {
                                          if ( !v86 )
                                            goto LABEL_361;
                                          v60 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v86->lpVtbl->get_KeywordsAny)(
                                                  v86,
                                                  &v84);
                                          Ul = v60;
                                          if ( v60 >= 0 )
                                          {
                                            v61 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v84 + 112LL))(
                                                    v84,
                                                    &v91);
                                            Ul = v61;
                                            if ( v61 >= 0 )
                                            {
                                              if ( v91 == 3 )
                                              {
                                                ((void (__fastcall *)(struct ITraceDataProvider *, struct _GUID *))v86->lpVtbl->get_Guid)(
                                                  v86,
                                                  &v99);
                                                v62 = PlaiGuidToString(&v99, v148, 0x400u);
                                                Ul = v62;
                                                if ( v62 < 0 )
                                                {
                                                  v81 = 0;
                                                  v80 = v62;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v133, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v133[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                v63 = (*(__int64 (__fastcall **)(LTraceSession *, __int64, unsigned __int16 *, SAFEARRAY **, SAFEARRAY **))(*(_QWORD *)this + 672LL))(
                                                        this,
                                                        v84,
                                                        v148,
                                                        &psa,
                                                        &Vector);
                                                Ul = v63;
                                                if ( v63 < 0 )
                                                {
                                                  v81 = 0;
                                                  v80 = v63;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v134, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v134[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                              }
                                              else
                                              {
                                                v64 = 0;
                                                psa = SafeArrayCreateVector(8u, 0, cElements);
                                                if ( !psa )
                                                {
                                                  Ul = -2147024882;
                                                  v81 = 0;
                                                  v80 = -2147024882;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v135, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v135[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                Vector = SafeArrayCreateVector(3u, 0, cElements);
                                                if ( !Vector )
                                                {
                                                  Ul = -2147024882;
                                                  v81 = 0;
                                                  v80 = -2147024882;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v136, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v136[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                v3 = SafeArrayCreateVector(3u, 0, cElements);
                                                if ( !v3 )
                                                {
                                                  Ul = -2147024882;
                                                  v81 = 0;
                                                  v80 = -2147024882;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v137, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v137[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                v65 = SafeArrayAccessData(psa, &ppvData);
                                                Ul = v65;
                                                if ( v65 < 0 )
                                                {
                                                  v80 = v65;
                                                  v81 = 0;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v138, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v138[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                v66 = SafeArrayAccessData(Vector, &v93);
                                                Ul = v66;
                                                if ( v66 < 0 )
                                                {
                                                  v80 = v66;
                                                  v81 = 0;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v139, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v139[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                v67 = SafeArrayAccessData(v3, &v94);
                                                Ul = v67;
                                                if ( v67 < 0 )
                                                {
                                                  v80 = v67;
                                                  v81 = 0;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v140, 0x4000000000000800uLL);
                                                    do
                                                      ++v43;
                                                    while ( v140[v43] );
                                                    goto LABEL_7;
                                                  }
                                                  goto LABEL_361;
                                                }
                                                while ( v64 < cElements )
                                                {
                                                  if ( v86 )
                                                  {
                                                    ((void (__fastcall *)(struct ITraceDataProvider *))v86->lpVtbl->Release)(v86);
                                                    v86 = 0;
                                                  }
                                                  PlaiVariantClear(&pvarg);
                                                  (*(void (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v95 + 24LL))(
                                                    v95,
                                                    1,
                                                    &pvarg,
                                                    &v98);
                                                  v68 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct ITraceDataProvider **))pvarg.llVal)(
                                                          pvarg.llVal,
                                                          &IID_ITraceDataProvider,
                                                          &v86);
                                                  Ul = v68;
                                                  if ( v68 < 0 )
                                                  {
                                                    v80 = v68;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v147, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v147[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  v81 = 0;
                                                  v80 = 0;
                                                  ((void (__fastcall *)(struct ITraceDataProvider *, struct _GUID *))v86->lpVtbl->get_Guid)(
                                                    v86,
                                                    &v99);
                                                  if ( v84 )
                                                  {
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                                                    v84 = 0;
                                                  }
                                                  v69 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v86->lpVtbl->get_KeywordsAny)(
                                                          v86,
                                                          &v84);
                                                  Ul = v69;
                                                  if ( v69 < 0 )
                                                  {
                                                    v80 = v69;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v146, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v146[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  Ul = PlaiGetUlValue<IValueMap>(v84, &v81);
                                                  if ( Ul < 0 )
                                                  {
                                                    v80 = Ul;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v145, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v145[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  if ( v84 )
                                                  {
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                                                    v84 = 0;
                                                  }
                                                  v70 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int64 *))v86->lpVtbl->get_Level)(
                                                          v86,
                                                          &v84);
                                                  Ul = v70;
                                                  if ( v70 < 0 )
                                                  {
                                                    v80 = v70;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v144, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v144[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  v71 = PlaiGetUlValue<IValueMap>(v84, &v80);
                                                  Ul = v71;
                                                  if ( v71 < 0 )
                                                  {
                                                    v80 = v71;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v143, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v143[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  v72 = PlaiGuidToString(&v99, v148, 0x400u);
                                                  Ul = v72;
                                                  if ( v72 < 0 )
                                                  {
                                                    v80 = v72;
                                                    v81 = 0;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v142, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v142[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  v75 = PlaiAllocStringEx(v148, v73, v74);
                                                  v76 = v64;
                                                  *((_QWORD *)ppvData + v64) = v75;
                                                  if ( !*((_QWORD *)ppvData + v64) )
                                                  {
                                                    Ul = -2147024882;
                                                    v81 = 0;
                                                    v80 = -2147024882;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v141, 0x4000000000000800uLL);
                                                      do
                                                        ++v43;
                                                      while ( v141[v43] );
                                                      goto LABEL_7;
                                                    }
                                                    goto LABEL_361;
                                                  }
                                                  ++v64;
                                                  *((_DWORD *)v94 + v76) = v80;
                                                  *((_DWORD *)v93 + v76) = v81;
                                                }
                                              }
                                              PlaiVariantClear(&pvarg);
                                              pvarg.vt = 8200;
                                              pvarg.llVal = (LONGLONG)psa;
                                              ((void (__fastcall *)(struct IWbemClassObject *, const WCHAR *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
                                                a2,
                                                L"Guid",
                                                0,
                                                &pvarg,
                                                0);
                                              pvarg.llVal = (LONGLONG)Vector;
                                              lpVtbl = a2->lpVtbl;
                                              pvarg.vt = 8195;
                                              ((void (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))lpVtbl->Put)(
                                                a2,
                                                L"EnableFlags",
                                                0,
                                                &pvarg,
                                                0);
                                              v78 = a2->lpVtbl;
                                              pvarg.vt = 8195;
                                              pvarg.llVal = (LONGLONG)v3;
                                              ((void (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v78->Put)(
                                                a2,
                                                L"Level",
                                                0,
                                                &pvarg,
                                                0);
                                              pvarg.llVal = 0;
                                              goto LABEL_361;
                                            }
                                            v80 = v61;
                                            v81 = 0;
                                            if ( (_DWORD)xmmword_180169738
                                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                            {
                                              PlaiWhoAmI(v132, 0x4000000000000800uLL);
                                              do
                                                ++v43;
                                              while ( v132[v43] );
                                              goto LABEL_7;
                                            }
                                          }
                                          else
                                          {
                                            v80 = v60;
                                            v81 = 0;
                                            if ( (_DWORD)xmmword_180169738
                                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                            {
                                              PlaiWhoAmI(v131, 0x4000000000000800uLL);
                                              do
                                                ++v43;
                                              while ( v131[v43] );
                                              goto LABEL_7;
                                            }
                                          }
                                        }
                                        else
                                        {
                                          v80 = TraceDataProvider;
                                          v81 = 0;
                                          if ( (_DWORD)xmmword_180169738
                                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                          {
                                            PlaiWhoAmI(v130, 0x4000000000000800uLL);
                                            do
                                              ++v43;
                                            while ( v130[v43] );
                                            goto LABEL_7;
                                          }
                                        }
                                      }
                                      else
                                      {
                                        v80 = v58;
                                        v81 = 0;
                                        if ( (_DWORD)xmmword_180169738
                                          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          PlaiWhoAmI(v129, 0x4000000000000800uLL);
                                          do
                                            ++v43;
                                          while ( v129[v43] );
                                          goto LABEL_7;
                                        }
                                      }
                                    }
                                    else
                                    {
                                      v80 = v57;
                                      v81 = 0;
                                      if ( (_DWORD)xmmword_180169738
                                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                      {
                                        PlaiWhoAmI(v128, 0x4000000000000800uLL);
                                        do
                                          ++v43;
                                        while ( v128[v43] );
                                        goto LABEL_7;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    v80 = v56;
                                    v81 = 0;
                                    if ( (_DWORD)xmmword_180169738
                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                    {
                                      PlaiWhoAmI(v127, 0x4000000000000800uLL);
                                      do
                                        ++v43;
                                      while ( v127[v43] );
                                      goto LABEL_7;
                                    }
                                  }
                                }
                                else
                                {
                                  v80 = v55;
                                  v81 = 0;
                                  if ( (_DWORD)xmmword_180169738
                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                  {
                                    PlaiWhoAmI(v126, 0x4000000000000800uLL);
                                    do
                                      ++v43;
                                    while ( v126[v43] );
                                    goto LABEL_7;
                                  }
                                }
                              }
                              else
                              {
                                v80 = v54;
                                v81 = 0;
                                if ( (_DWORD)xmmword_180169738
                                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  PlaiWhoAmI(v125, 0x4000000000000800uLL);
                                  do
                                    ++v43;
                                  while ( v125[v43] );
                                  goto LABEL_7;
                                }
                              }
                            }
                            else
                            {
                              v80 = v53;
                              v81 = 0;
                              if ( (_DWORD)xmmword_180169738
                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                              {
                                PlaiWhoAmI(v124, 0x4000000000000800uLL);
                                do
                                  ++v43;
                                while ( v124[v43] );
                                goto LABEL_7;
                              }
                            }
                          }
                        }
                        else
                        {
                          v80 = v48;
                          v81 = 0;
                          if ( (_DWORD)xmmword_180169738
                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                          {
                            PlaiWhoAmI(v121, 0x4000000000000800uLL);
                            do
                              ++v43;
                            while ( v121[v43] );
                            goto LABEL_7;
                          }
                        }
                      }
                      else
                      {
                        v81 = 0;
                        v80 = v41;
                        if ( (_DWORD)xmmword_180169738
                          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                        {
                          PlaiWhoAmI(v116, 0x4000000000000800uLL);
                          v42 = -1;
                          do
                            ++v42;
                          while ( v116[v42] );
                          goto LABEL_7;
                        }
                      }
                    }
                    else
                    {
                      v81 = 0;
                      v80 = v39;
                      if ( (_DWORD)xmmword_180169738
                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v115, 0x4000000000000800uLL);
                        v40 = -1;
                        do
                          ++v40;
                        while ( v115[v40] );
                        goto LABEL_7;
                      }
                    }
                  }
                  else
                  {
                    v81 = 0;
                    v80 = v37;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v114, 0x4000000000000800uLL);
                      v38 = -1;
                      do
                        ++v38;
                      while ( v114[v38] );
                      goto LABEL_7;
                    }
                  }
                }
                else
                {
                  v81 = 0;
                  v80 = v35;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v113, 0x4000000000000800uLL);
                    v36 = -1;
                    do
                      ++v36;
                    while ( v113[v36] );
                    goto LABEL_7;
                  }
                }
              }
              else
              {
                v81 = 0;
                v80 = v33;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v112, 0x4000000000000800uLL);
                  v34 = -1;
                  do
                    ++v34;
                  while ( v112[v34] );
                  goto LABEL_7;
                }
              }
            }
            else
            {
              v81 = 0;
              v80 = v31;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v111, 0x4000000000000800uLL);
                v32 = -1;
                do
                  ++v32;
                while ( v111[v32] );
                goto LABEL_7;
              }
            }
          }
          else
          {
            v81 = 0;
            v80 = v29;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v110, 0x4000000000000800uLL);
              v30 = -1;
              do
                ++v30;
              while ( v110[v30] );
              goto LABEL_7;
            }
          }
        }
        else
        {
          v81 = 0;
          v80 = v27;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v109, 0x4000000000000800uLL);
            v28 = -1;
            do
              ++v28;
            while ( v109[v28] );
            goto LABEL_7;
          }
        }
      }
      else
      {
        v81 = 0;
        v80 = v25;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v108, 0x4000000000000800uLL);
          v26 = -1;
          do
            ++v26;
          while ( v108[v26] );
          goto LABEL_7;
        }
      }
    }
    else
    {
      v81 = 0;
      v80 = v23;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v107, 0x4000000000000800uLL);
        v24 = -1;
        do
          ++v24;
        while ( v107[v24] );
        goto LABEL_7;
      }
    }
  }
  else
  {
    v81 = 0;
    v80 = v21;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v106, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v106[v22] );
      goto LABEL_7;
    }
  }
LABEL_361:
  PlaiVariantClear(&pvarg);
  if ( ppvData )
  {
    SafeArrayUnaccessData(psa);
    ppvData = 0;
  }
  if ( v93 )
  {
    SafeArrayUnaccessData(Vector);
    v93 = 0;
  }
  if ( v94 )
  {
    SafeArrayUnaccessData(v3);
    v94 = 0;
  }
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  if ( Vector )
  {
    SafeArrayDestroy(Vector);
    Vector = 0;
  }
  if ( v3 )
    SafeArrayDestroy(v3);
  if ( v86 )
  {
    ((void (__fastcall *)(struct ITraceDataProvider *))v86->lpVtbl->Release)(v86);
    v86 = 0;
  }
  if ( v84 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    v84 = 0;
  }
  if ( v95 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    v95 = 0;
  }
  if ( v96 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
    v96 = 0;
  }
  if ( v82 )
  {
    ((void (__fastcall *)(struct ITraceDataCollector *))v82->lpVtbl->Release)(v82);
    v82 = 0;
  }
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  return (unsigned int)Ul;
}

```

## disassembly

```asm
0x18005f9f0  mov     [rsp-8+arg_10], rbx
0x18005f9f5  push    rbp
0x18005f9f6  push    rsi
0x18005f9f7  push    rdi
0x18005f9f8  push    r12
0x18005f9fa  push    r13
0x18005f9fc  push    r14
0x18005f9fe  push    r15
0x18005fa00  lea     rbp, [rsp-2030h]
0x18005fa08  mov     eax, 2130h
0x18005fa0d  call    _alloca_probe
0x18005fa12  sub     rsp, rax
0x18005fa15  mov     rax, cs:__security_cookie
0x18005fa1c  xor     rax, rsp
0x18005fa1f  mov     [rbp+2060h+var_40], rax
0x18005fa26  xor     r15d, r15d
0x18005fa29  xorps   xmm0, xmm0
0x18005fa2c  mov     r12, rcx
0x18005fa2f  mov     [rbp+2060h+var_20A8], r15d
0x18005fa33  xor     eax, eax
0x18005fa35  mov     [rbp+2060h+var_2090], r15d
0x18005fa39  lea     rcx, [rbp+2060h+pvarg]; struct tagVARIANT *
0x18005fa3d  mov     qword ptr [rbp+2060h+pvarg+10h], rax
0x18005fa41  movups  xmmword ptr [rbp+2060h+pvarg], xmm0
0x18005fa45  mov     [rbp+2060h+cElements], r15d
0x18005fa49  mov     r13d, r15d
0x18005fa4c  mov     [rbp+2060h+var_2058], r15d
0x18005fa50  mov     r14, rdx
0x18005fa53  mov     [rbp+2060h+var_2070], r15
0x18005fa57  mov     [rbp+2060h+var_2068], r15
0x18005fa5b  mov     [rbp+2060h+var_20E0], r15
0x18005fa5f  mov     [rbp+2060h+var_2060], r15
0x18005fa63  mov     [rbp+2060h+var_20B0], r15
0x18005fa67  mov     [rbp+2060h+var_20C0], r15
0x18005fa6b  mov     [rbp+2060h+var_208C], r15d
0x18005fa6f  movups  xmmword ptr [rbp+2060h+var_2050.Data1], xmm0
0x18005fa73  mov     [rbp+2060h+psa], r15
0x18005fa77  mov     [rbp+2060h+var_2098], r15
0x18005fa7b  mov     [rbp+2060h+ppvData], r15
0x18005fa7f  mov     [rbp+2060h+var_2078], r15
0x18005fa83  mov     [rbp+2060h+var_2080], r15
0x18005fa87  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x18005fa8c  mov     rax, [r12]
0x18005fa90  lea     rdx, [rbp+2060h+var_20E0]
0x18005fa94  mov     rcx, r12
0x18005fa97  mov     rax, [rax+288h]
0x18005fa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005faa3  mov     edi, eax
0x18005faa5  test    eax, eax
0x18005faa7  jns     loc_18005FB85
0x18005faad  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fab4  mov     [rsp+2160h+var_20E8], r15d
0x18005fab9  mov     [rsp+2160h+var_20F0], eax
0x18005fabd  jz      loc_180061905
0x18005fac3  mov     rdx, 4000000000000800h; unsigned __int64
0x18005facd  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fad4  jz      loc_180061905
0x18005fada  mov     rax, cs:qword_180169748
0x18005fae1  and     rax, rdx
0x18005fae4  cmp     cs:qword_180169748, rax
0x18005faeb  jnz     loc_180061905
0x18005faf1  lea     rcx, [rbp+2060h+var_2040]; unsigned __int16 *
0x18005faf5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fafa  lea     rax, [rbp+2060h+var_2040]
0x18005fafe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fb02  inc     rbx
0x18005fb05  cmp     [rax+rbx*2], r15w
0x18005fb0a  jnz     short loc_18005FB02
0x18005fb0c  lea     rax, [rbp+2060h+var_2040]
0x18005fb10  lea     ecx, [rbx+rbx]
0x18005fb13  add     rcx, 2
0x18005fb17  mov     [rsp+2160h+var_2100], rcx
0x18005fb1c  lea     r9, [rsp+2160h+var_20F0]
0x18005fb21  mov     [rsp+2160h+var_2108], rax
0x18005fb26  lea     rcx, [rsp+2160h+var_20E8]
0x18005fb2b  mov     [rsp+2160h+var_2110], 16h
0x18005fb34  lea     rax, aLtracesessionC_0; "LTraceSession::Commit"
0x18005fb3b  mov     [rsp+2160h+var_2118], rax
0x18005fb40  lea     rdx, PLA_EVENT_ERROR
0x18005fb47  mov     eax, 4
0x18005fb4c  mov     [rsp+2160h+var_2120], rax
0x18005fb51  mov     [rsp+2160h+var_2128], rcx
0x18005fb56  lea     rcx, byte_180147320
0x18005fb5d  mov     [rsp+2160h+var_2130], 1
0x18005fb66  mov     [rsp+2160h+var_2138], rcx
0x18005fb6b  lea     r8d, [rax+1]
0x18005fb6f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005fb76  mov     [rsp+2160h+var_2140], rax
0x18005fb7b  call    EventingWriteEvent
0x18005fb80  jmp     loc_180061905
0x18005fb85  mov     rcx, [rbp+2060h+var_20E0]
0x18005fb89  lea     rdx, [rbp+2060h+var_20A8]
0x18005fb8d  mov     rax, [rcx]
0x18005fb90  mov     rax, [rax+228h]
0x18005fb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb9c  mov     edi, eax
0x18005fb9e  test    eax, eax
0x18005fba0  jns     short loc_18005FC13
0x18005fba2  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fba9  mov     [rsp+2160h+var_20E8], r15d
0x18005fbae  mov     [rsp+2160h+var_20F0], eax
0x18005fbb2  jz      loc_180061905
0x18005fbb8  mov     rdx, 4000000000000800h; unsigned __int64
0x18005fbc2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fbc9  jz      loc_180061905
0x18005fbcf  mov     rax, cs:qword_180169748
0x18005fbd6  and     rax, rdx
0x18005fbd9  cmp     cs:qword_180169748, rax
0x18005fbe0  jnz     loc_180061905
0x18005fbe6  lea     rcx, [rbp+2060h+var_1FC0]; unsigned __int16 *
0x18005fbed  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fbf2  lea     rax, [rbp+2060h+var_1FC0]
0x18005fbf9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fbfd  inc     rbx
0x18005fc00  cmp     [rax+rbx*2], r15w
0x18005fc05  jnz     short loc_18005FBFD
0x18005fc07  lea     rax, [rbp+2060h+var_1FC0]
0x18005fc0e  jmp     loc_18005FB10
0x18005fc13  mov     eax, 8
0x18005fc18  lea     esi, [rax-6]
0x18005fc1b  cmp     [rbp+2060h+var_20A8], esi
0x18005fc1e  jz      loc_18005FD64
0x18005fc24  mov     rcx, [rbp+2060h+var_20E0]
0x18005fc28  lea     rdx, [rbp+2060h+pvarg+8]
0x18005fc2c  mov     word ptr [rbp+2060h+pvarg], ax
0x18005fc30  mov     rax, [rcx]
0x18005fc33  mov     rax, [rax+0D0h]
0x18005fc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc3f  mov     edi, eax
0x18005fc41  test    eax, eax
0x18005fc43  jns     short loc_18005FCBC
0x18005fc45  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fc4c  mov     [rsp+2160h+var_20E8], r15d
0x18005fc51  mov     [rsp+2160h+var_20F0], eax
0x18005fc55  jz      loc_180061905
0x18005fc5b  mov     rdx, 4000000000000800h; unsigned __int64
0x18005fc65  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fc6c  jz      loc_180061905
0x18005fc72  mov     rax, cs:qword_180169748
0x18005fc79  and     rax, rdx
0x18005fc7c  cmp     cs:qword_180169748, rax
0x18005fc83  jnz     loc_180061905
0x18005fc89  lea     rcx, [rbp+2060h+var_1F40]; unsigned __int16 *
0x18005fc90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fc95  lea     rax, [rbp+2060h+var_1F40]
0x18005fc9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fca0  inc     rbx
0x18005fca3  cmp     [rax+rbx*2], r15w
0x18005fca8  jnz     short loc_18005FCA0
0x18005fcaa  lea     ecx, [rbx+rbx]
0x18005fcad  add     rcx, rsi
0x18005fcb0  lea     rax, [rbp+2060h+var_1F40]
0x18005fcb7  jmp     loc_18005FB17
0x18005fcbc  mov     rax, [r14]
0x18005fcbf  lea     r9, [rbp+2060h+pvarg]
0x18005fcc3  xor     r8d, r8d
0x18005fcc6  mov     dword ptr [rsp+2160h+var_2140], r15d
0x18005fccb  lea     rdx, aLogfilename; "LogFileName"
0x18005fcd2  mov     rcx, r14
0x18005fcd5  mov     rax, [rax+28h]
0x18005fcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcde  mov     edi, eax
0x18005fce0  test    eax, eax
0x18005fce2  jns     short loc_18005FD5B
0x18005fce4  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fceb  mov     [rsp+2160h+var_20E8], r15d
0x18005fcf0  mov     [rsp+2160h+var_20F0], eax
0x18005fcf4  jz      loc_180061905
0x18005fcfa  mov     rdx, 4000000000000800h; unsigned __int64
0x18005fd04  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fd0b  jz      loc_180061905
0x18005fd11  mov     rax, cs:qword_180169748
0x18005fd18  and     rax, rdx
0x18005fd1b  cmp     cs:qword_180169748, rax
0x18005fd22  jnz     loc_180061905
0x18005fd28  lea     rcx, [rbp+2060h+var_1EC0]; unsigned __int16 *
0x18005fd2f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fd34  lea     rax, [rbp+2060h+var_1EC0]
0x18005fd3b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fd3f  inc     rbx
0x18005fd42  cmp     [rax+rbx*2], r15w
0x18005fd47  jnz     short loc_18005FD3F
0x18005fd49  lea     ecx, [rbx+rbx]
0x18005fd4c  add     rcx, rsi
0x18005fd4f  lea     rax, [rbp+2060h+var_1EC0]
0x18005fd56  jmp     loc_18005FB17
0x18005fd5b  lea     rcx, [rbp+2060h+pvarg]; struct tagVARIANT *
0x18005fd5f  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18005fd64  mov     rcx, [rbp+2060h+var_20E0]
0x18005fd68  lea     rdx, [rbp+2060h+var_2090]
0x18005fd6c  mov     rax, [rcx]
0x18005fd6f  mov     rax, [rax+130h]
0x18005fd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd7b  mov     edi, eax
0x18005fd7d  test    eax, eax
0x18005fd7f  jns     short loc_18005FDF8
0x18005fd81  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fd88  mov     [rsp+2160h+var_20E8], r15d
0x18005fd8d  mov     [rsp+2160h+var_20F0], eax
0x18005fd91  jz      loc_180061905
0x18005fd97  mov     rdx, 4000000000000800h; unsigned __int64
0x18005fda1  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fda8  jz      loc_180061905
0x18005fdae  mov     rax, cs:qword_180169748
0x18005fdb5  and     rax, rdx
0x18005fdb8  cmp     cs:qword_180169748, rax
0x18005fdbf  jnz     loc_180061905
0x18005fdc5  lea     rcx, [rbp+2060h+var_1E40]; unsigned __int16 *
0x18005fdcc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fdd1  lea     rax, [rbp+2060h+var_1E40]
0x18005fdd8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fddc  inc     rbx
0x18005fddf  cmp     [rax+rbx*2], r15w
0x18005fde4  jnz     short loc_18005FDDC
0x18005fde6  lea     ecx, [rbx+rbx]
0x18005fde9  add     rcx, rsi
0x18005fdec  lea     rax, [rbp+2060h+var_1E40]
0x18005fdf3  jmp     loc_18005FB17
0x18005fdf8  mov     ecx, [rbp+2060h+var_2090]
0x18005fdfb  sub     ecx, 1
0x18005fdfe  jz      short loc_18005FE20
0x18005fe00  sub     ecx, 1
0x18005fe03  jz      short loc_18005FE17
0x18005fe05  cmp     ecx, 1
0x18005fe08  jnz     loc_18005FEAD
0x18005fe0e  lea     rcx, aCycle; "cycle"
0x18005fe15  jmp     short loc_18005FE27
0x18005fe17  lea     rcx, aSystem_1; "system"
0x18005fe1e  jmp     short loc_18005FE27
0x18005fe20  lea     rcx, aPerf; "perf"
0x18005fe27  lea     rdx, [rbp+2060h+pvarg]; pvarg
0x18005fe2b  call    ?PlaiSetVariantEx@@YAJPEBGPEAUtagVARIANT@@PEBDH@Z; PlaiSetVariantEx(ushort const *,tagVARIANT *,char const *,int)
0x18005fe30  mov     edi, eax
0x18005fe32  test    eax, eax
0x18005fe34  jns     short loc_18005FEAD
0x18005fe36  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005fe3d  mov     [rsp+2160h+var_20E8], r15d
0x18005fe42  mov     [rsp+2160h+var_20F0], eax
0x18005fe46  jz      loc_180061905
0x18005fe4c  mov     rdx, 4000000000000800h; unsigned __int64
0x18005fe56  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005fe5d  jz      loc_180061905
0x18005fe63  mov     rax, cs:qword_180169748
0x18005fe6a  and     rax, rdx
0x18005fe6d  cmp     cs:qword_180169748, rax
0x18005fe74  jnz     loc_180061905
0x18005fe7a  lea     rcx, [rbp+2060h+var_1DC0]; unsigned __int16 *
0x18005fe81  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005fe86  lea     rax, [rbp+2060h+var_1DC0]
0x18005fe8d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fe91  inc     rbx
0x18005fe94  cmp     [rax+rbx*2], r15w
0x18005fe99  jnz     short loc_18005FE91
0x18005fe9b  lea     ecx, [rbx+rbx]
0x18005fe9e  add     rcx, rsi
0x18005fea1  lea     rax, [rbp+2060h+var_1DC0]
0x18005fea8  jmp     loc_18005FB17
0x18005fead  mov     rax, [r14]
0x18005feb0  lea     r9, [rbp+2060h+pvarg]
0x18005feb4  xor     r8d, r8d
0x18005feb7  mov     dword ptr [rsp+2160h+var_2140], r15d
0x18005febc  lea     rdx, aClocktype; "ClockType"
0x18005fec3  mov     rcx, r14
0x18005fec6  mov     rax, [rax+28h]
0x18005feca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fecf  lea     rcx, [rbp+2060h+pvarg]; struct tagVARIANT *
0x18005fed3  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18005fed8  mov     rcx, [rbp+2060h+var_20E0]
0x18005fedc  lea     rdx, [rbp+2060h+pvarg+8]
0x18005fee0  mov     eax, 3
0x18005fee5  mov     word ptr [rbp+2060h+pvarg], ax
0x18005fee9  mov     rax, [rcx]
0x18005feec  mov     rax, [rax+100h]
0x18005fef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fef8  mov     edi, eax
0x18005fefa  test    eax, eax
0x18005fefc  jns     short loc_18005FF75
0x18005fefe  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005ff05  mov     [rsp+2160h+var_20E8], r15d
0x18005ff0a  mov     [rsp+2160h+var_20F0], eax
0x18005ff0e  jz      loc_180061905
0x18005ff14  mov     rdx, 4000000000000800h; unsigned __int64
0x18005ff1e  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005ff25  jz      loc_180061905
0x18005ff2b  mov     rax, cs:qword_180169748
0x18005ff32  and     rax, rdx
0x18005ff35  cmp     cs:qword_180169748, rax
0x18005ff3c  jnz     loc_180061905
0x18005ff42  lea     rcx, [rbp+2060h+var_1D40]; unsigned __int16 *
0x18005ff49  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005ff4e  lea     rax, [rbp+2060h+var_1D40]
0x18005ff55  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005ff59  inc     rbx
0x18005ff5c  cmp     [rax+rbx*2], r15w
0x18005ff61  jnz     short loc_18005FF59
0x18005ff63  lea     ecx, [rbx+rbx]
0x18005ff66  add     rcx, rsi
0x18005ff69  lea     rax, [rbp+2060h+var_1D40]
0x18005ff70  jmp     loc_18005FB17
0x18005ff75  mov     rax, [r14]
  ... truncated ...
```
