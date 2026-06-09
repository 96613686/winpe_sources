# CMediaSourceBase::CreatePresentationDescriptor(void)

- ea: `0x180076fc0`
- end: `0x180077f6b`
- name: `?CreatePresentationDescriptor@CMediaSourceBase@@IEAAJXZ`
- size: `4011`
- prototype: `__int64 __fastcall(CMediaSourceBase *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18007f4c4`
- `0x1800a1c4c`

## callees

- `0x1800041d0`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003fe50`
- `0x180073b14`
- `0x180076fc0`
- `0x1800a2f58`
- `0x180109590`
- `0x1801095a8`
- `0x18010a450`
- `0x180154418`
- `0x18016e750`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007702b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800770c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800773cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800774f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007758c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800776f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800777a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077839`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800779d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077c16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077e13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007702b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800770c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800773cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800774f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007758c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800776f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800777a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077839`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800779d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077c16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077e13`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180077a82`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180077a82`

## string_xrefs

- `0x180076fdf`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077420`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x1800774b5`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007754a`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x1800775df`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077693`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077747`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x1800777f3`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077887`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077949`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077a2c`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077af8`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077bd2`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077c70`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077da2`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x180077e6d`: `CMediaSourceBase::CreatePresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CMediaSourceBase::CreatePresentationDescriptor(CMediaSourceBase *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rbx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rbx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  IMFStreamDescriptor **v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  IMFStreamDescriptor **v20; // r13
  wchar_t *v21; // rbx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 i; // r15
  __int64 v25; // rax
  __int64 (__fastcall *v26)(CMediaSourceBase *, _QWORD, unsigned int *); // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  struct IMFStreamDescriptor *v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  struct IMFMediaType *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  CallStackTracing *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  wchar_t *v81; // rbx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  int (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  wchar_t *v89; // rbx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  __int64 v92; // rdx
  _QWORD *v93; // rbx
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  wchar_t *v98; // rbx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  __int64 v101; // rax
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // r8
  __int64 v109; // r9
  wchar_t *v110; // rbx
  CallStackTracing *v111; // rax
  struct CallStackContext *v112; // rax
  wchar_t *v113; // rbx
  CallStackTracing *v114; // rax
  struct CallStackContext *v115; // rax
  int (__fastcall ***v116)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r9
  wchar_t *v121; // rbx
  CallStackTracing *v122; // rax
  struct CallStackContext *v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // r8
  __int64 v128; // r9
  wchar_t *v129; // rbx
  CallStackTracing *v130; // rax
  struct CallStackContext *v131; // rax
  DWORD v132; // eax
  DWORD j; // ebx
  IMFStreamDescriptor *v134; // rcx
  DWORD cStreamDescriptors; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v137[4]; // [rsp+44h] [rbp-3Ch] BYREF
  struct IMFMediaType *v138; // [rsp+48h] [rbp-38h] BYREF
  struct IMFStreamDescriptor *v139; // [rsp+50h] [rbp-30h] BYREF
  __int64 v140; // [rsp+58h] [rbp-28h] BYREF
  __int64 v141; // [rsp+60h] [rbp-20h] BYREF
  __int64 v142; // [rsp+68h] [rbp-18h] BYREF
  __int64 v143; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v144; // [rsp+78h] [rbp-8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v137,
    "CMediaSourceBase::CreatePresentationDescriptor",
    1260);
  v2 = *(_QWORD *)this;
  cStreamDescriptors = 0;
  v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, DWORD *))(v2 + 128))(this, &cStreamDescriptors);
  if ( v5 < 0 )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v4, v3, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMediaSourceBase::CreatePresentationDescriptor",
          1271,
          v5);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v11 = 117;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
LABEL_228:
    ComSmartPtr<IUnknown>::Release((char *)this + 240);
    goto LABEL_229;
  }
  if ( !cStreamDescriptors )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v4, cStreamDescriptors, v6, v7);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v14, "CMediaSourceBase::CreatePresentationDescriptor", 1274, -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v11 = 118;
    goto LABEL_23;
  }
  *((_QWORD *)this + 84) = 0;
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init();
  v15 = (IMFStreamDescriptor **)operator new(saturated_mul(cStreamDescriptors, 8u));
  v20 = v15;
  if ( !v15 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v16, v18, v19);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v23, "CMediaSourceBase::CreatePresentationDescriptor", 1287, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v11 = 120;
    goto LABEL_23;
  }
  memset_0(v15, 0, 8LL * cStreamDescriptors);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v25 = *(_QWORD *)this;
    if ( (unsigned int)i >= cStreamDescriptors )
      break;
    v26 = *(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, unsigned int *))(v25 + 136);
    v144 = 0;
    v5 = v26(this, (unsigned int)i, &v144);
    if ( v5 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27, v29, v30);
        CallStackTracing::s_wpInstance = v72;
        if ( !v72 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      v71 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v73 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v73 + 499) != v5 )
          CallStackContext::TraceFailure(v73, "CMediaSourceBase::CreatePresentationDescriptor", 1296, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_122;
    }
    v31 = *(_QWORD *)this;
    v138 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFMediaType **))(v31 + 144))(this, v144, &v138);
    if ( v5 < 0 )
    {
      v68 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
        CallStackTracing::s_wpInstance = v69;
        if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
        {
          v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v68 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
        if ( *((_DWORD *)v70 + 499) != v5 )
          CallStackContext::TraceFailure(v70, "CMediaSourceBase::CreatePresentationDescriptor", 1303, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_112;
    }
    v139 = 0;
    v5 = CMediaSourceBase::CreateStreamDescriptor(this, v144, v138, &v139);
    if ( v5 < 0 )
    {
      v65 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v65 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v65 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v65 + 8) )
      {
        v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
        if ( *((_DWORD *)v67 + 499) != v5 )
          CallStackContext::TraceFailure(v67, "CMediaSourceBase::CreatePresentationDescriptor", 1310, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_101;
    }
    v141 = 0;
    v38 = v139;
    v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))v139->lpVtbl->GetMediaTypeHandler)(
           v139,
           &v141);
    if ( v5 < 0 )
    {
      v62 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)v64 + 499) != v5 )
          CallStackContext::TraceFailure(v64, "CMediaSourceBase::CreatePresentationDescriptor", 1317, v5);
      }
      if ( g_wppLevels )
      {
        v55 = 124;
LABEL_89:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      }
LABEL_90:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v141);
LABEL_101:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v139);
LABEL_112:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v138);
LABEL_122:
      if ( !CallStackTracing::s_wpInstance )
      {
        v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v71, v27, v29, v30);
        CallStackTracing::s_wpInstance = v74;
        if ( !v74 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v75 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v75 + 499) != v5 )
          CallStackContext::TraceFailure(v75, "CMediaSourceBase::CreatePresentationDescriptor", 1338, v5);
      }
      if ( g_wppLevels )
      {
        v76 = 128;
LABEL_131:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v76, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
        goto LABEL_223;
      }
      goto LABEL_223;
    }
    v42 = v138;
    if ( v138 )
    {
      v138 = 0;
      ((void (__fastcall *)(struct IMFMediaType *))v42->lpVtbl->Release)(v42);
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v141 + 40LL))(v141, 0, &v138);
    if ( v5 < 0 )
    {
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != v5 )
          CallStackContext::TraceFailure(v61, "CMediaSourceBase::CreatePresentationDescriptor", 1321, v5);
      }
      if ( g_wppLevels )
      {
        v55 = 125;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, struct IMFMediaType *))(*(_QWORD *)v141 + 48LL))(v141, v138);
    if ( v5 < 0 )
    {
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v58 + 499) != v5 )
          CallStackContext::TraceFailure(v58, "CMediaSourceBase::CreatePresentationDescriptor", 1324, v5);
      }
      if ( g_wppLevels )
      {
        v55 = 126;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFStreamDescriptor *))(*(_QWORD *)this + 152LL))(
           this,
           v144,
           v38);
    if ( v5 < 0 )
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != v5 )
          CallStackContext::TraceFailure(v54, "CMediaSourceBase::CreatePresentationDescriptor", 1330, v5);
      }
      if ( g_wppLevels )
      {
        v55 = 127;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v20[i] = v38;
    if ( v38 )
      ((void (__fastcall *)(struct IMFStreamDescriptor *))v38->lpVtbl->AddRef)(v38);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v141);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v139);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v138);
  }
  v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(v25 + 112))(this);
  if ( v5 >= 0 )
  {
    v84 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v140 = 0;
    if ( (**v84)(v84, &IID_IMFMediaEventGenerator, &v140) >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v140 + 32LL))(
             v140,
             (char *)this + 184,
             *((_QWORD *)this + 90));
      if ( v5 < 0 )
      {
        v89 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v86, v85, v87, v88);
          CallStackTracing::s_wpInstance = v90;
          if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
          {
            v89 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v89 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v89 + 8) )
        {
          v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
          if ( *((_DWORD *)v91 + 499) != v5 )
            CallStackContext::TraceFailure(v91, "CMediaSourceBase::CreatePresentationDescriptor", 1351, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v92 = 130;
        goto LABEL_155;
      }
    }
    v93 = (_QWORD *)((char *)this + 240);
    v5 = MFCreatePresentationDescriptor(cStreamDescriptors, v20, (IMFPresentationDescriptor **)this + 30);
    if ( v5 < 0 )
    {
      v98 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v95, v94, v96, v97);
        CallStackTracing::s_wpInstance = v99;
        if ( v99 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
        {
          v98 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v98 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v98 + 8) )
      {
        v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
        if ( *((_DWORD *)v100 + 499) != v5 )
          CallStackContext::TraceFailure(v100, "CMediaSourceBase::CreatePresentationDescriptor", 1361, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_222;
      v92 = 131;
      goto LABEL_155;
    }
    v101 = *(_QWORD *)this;
    v143 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, __int64 *))(v101 + 120))(this, &v143);
    if ( v5 < 0 )
    {
      if ( v5 != -1072875781 )
      {
        v113 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v114 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v103, v102, v104, v105);
          CallStackTracing::s_wpInstance = v114;
          if ( v114 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v114 + 8LL))(v114, 2032) )
          {
            v113 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v113 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v113 + 8) )
        {
          v115 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v113);
          if ( *((_DWORD *)v115 + 499) != v5 )
            CallStackContext::TraceFailure(v115, "CMediaSourceBase::CreatePresentationDescriptor", 1375, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v92 = 133;
LABEL_155:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v92, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
LABEL_222:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v140);
        goto LABEL_223;
      }
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v93 + 176LL))(
             *v93,
             &MF_PD_DURATION,
             v143);
      if ( v5 < 0 )
      {
        v110 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v111 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v107, v106, v108, v109);
          CallStackTracing::s_wpInstance = v111;
          if ( v111 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v111 + 8LL))(v111, 2032) )
          {
            v110 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v110 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v110 + 8) )
        {
          v112 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v110);
          if ( *((_DWORD *)v112 + 499) != v5 )
            CallStackContext::TraceFailure(v112, "CMediaSourceBase::CreatePresentationDescriptor", 1371, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v92 = 132;
        goto LABEL_155;
      }
    }
    v116 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v142 = 0;
    if ( (**v116)(v116, &IID_IMFAttributes, &v142) >= 0 )
    {
      v139 = 0;
      v144 = 0;
      if ( (*(int (__fastcall **)(__int64, const IID *, struct IMFStreamDescriptor **, __int64, unsigned int *))(*(_QWORD *)v142 + 120LL))(
             v142,
             &MF_BYTESTREAM_LAST_MODIFIED_TIME,
             &v139,
             8,
             &v144) >= 0
        && v144 == 8 )
      {
        (*(void (__fastcall **)(_QWORD, const IID *, struct IMFStreamDescriptor **, __int64))(*(_QWORD *)*v93 + 208LL))(
          *v93,
          &MF_PD_LAST_MODIFIED_TIME,
          &v139,
          8);
      }
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(*(_QWORD *)this + 200LL))(this);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD))(*(_QWORD *)this + 160LL))(this, *v93);
      if ( v5 >= 0 )
      {
        if ( (unsigned __int8)byte_1801B110B >= 4u )
          WPP_SF_sq(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            136,
            (unsigned int)&WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
            v128,
            (__int64)this);
        if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
        {
          v144 = 1635018061;
          McTemplateU0s4pdpp_EventWriteTransfer(
            v126,
            (unsigned int)&Metadata_Loaded,
            (unsigned int)&v144,
            (_DWORD)this,
            v5);
        }
        goto LABEL_221;
      }
      v129 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v130 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v126, v125, v127, v128);
        CallStackTracing::s_wpInstance = v130;
        if ( v130 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v130 + 8LL))(v130, 2032) )
        {
          v129 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v129 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v129 + 8) )
      {
        v131 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v129);
        if ( *((_DWORD *)v131 + 499) != v5 )
          CallStackContext::TraceFailure(v131, "CMediaSourceBase::CreatePresentationDescriptor", 1405, v5);
      }
      if ( !g_wppLevels )
      {
LABEL_221:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v142);
        goto LABEL_222;
      }
      v124 = 135;
    }
    else
    {
      v121 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v122 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v118, v117, v119, v120);
        CallStackTracing::s_wpInstance = v122;
        if ( v122 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v122 + 8LL))(v122, 2032) )
        {
          v121 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v121 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v121 + 8) )
      {
        v123 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v121);
        if ( *((_DWORD *)v123 + 499) != v5 )
          CallStackContext::TraceFailure(v123, "CMediaSourceBase::CreatePresentationDescriptor", 1399, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_221;
      v124 = 134;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v124, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
    goto LABEL_221;
  }
  v81 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v78, v77, v79, v80);
    CallStackTracing::s_wpInstance = v82;
    if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
    {
      v81 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v81 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v81 + 8) )
  {
    v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
    if ( *((_DWORD *)v83 + 499) != v5 )
      CallStackContext::TraceFailure(v83, "CMediaSourceBase::CreatePresentationDescriptor", 1344, v5);
  }
  if ( g_wppLevels )
  {
    v76 = 129;
    goto LABEL_131;
  }
LABEL_223:
  v132 = cStreamDescriptors;
  for ( j = 0; j < v132; ++j )
  {
    v134 = v20[j];
    if ( v134 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v134->lpVtbl->Release)(v134);
      v20[j] = 0;
      v132 = cStreamDescriptors;
    }
  }
  operator delete(v20);
  if ( v5 < 0 )
    goto LABEL_228;
LABEL_229:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v137);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180076fc0  mov     [rsp-28h+arg_8], rbx
0x180076fc5  mov     [rsp-28h+arg_10], rsi
0x180076fca  push    rbp
0x180076fcb  push    rdi
0x180076fcc  push    r12
0x180076fce  push    r13
0x180076fd0  push    r15
0x180076fd2  mov     rbp, rsp
0x180076fd5  sub     rsp, 80h
0x180076fdc  mov     rsi, rcx
0x180076fdf  lea     r15, aCmediasourceba_32; "CMediaSourceBase::CreatePresentationDes"...
0x180076fe6  mov     rdx, r15; char *
0x180076fe9  lea     rcx, [rbp+var_3C]; this
0x180076fed  mov     r8d, 4ECh; int
0x180076ff3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076ff8  mov     rax, [rsi]
0x180076ffb  lea     rdx, [rbp+cStreamDescriptors]
0x180076fff  mov     rcx, rsi
0x180077002  mov     [rbp+cStreamDescriptors], 0
0x180077009  mov     rax, [rax+80h]
0x180077010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077015  mov     edi, eax
0x180077017  test    eax, eax
0x180077019  jns     loc_1800770AD
0x18007701f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077026  test    rbx, rbx
0x180077029  jnz     short loc_18007706C
0x18007702b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077031  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077038  mov     rcx, rax
0x18007703b  test    rax, rax
0x18007703e  jz      short loc_18007705E
0x180077040  mov     rax, [rax]
0x180077043  mov     edx, 7F0h
0x180077048  mov     rax, [rax+8]
0x18007704c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077051  test    eax, eax
0x180077053  jz      short loc_18007705E
0x180077055  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007705c  jmp     short loc_18007706C
0x18007705e  lea     rbx, qword_1801B07E0
0x180077065  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007706c  cmp     byte ptr [rbx+8], 0
0x180077070  jz      short loc_180077096
0x180077072  mov     rcx, rbx; this
0x180077075  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007707a  cmp     [rax+7CCh], edi
0x180077080  jz      short loc_180077096
0x180077082  mov     r9d, edi; int
0x180077085  mov     r8d, 4F7h; int
0x18007708b  mov     rdx, r15; char *
0x18007708e  mov     rcx, rax; this
0x180077091  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077096  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007709d  jb      loc_180077F38
0x1800770a3  mov     edx, 75h ; 'u'
0x1800770a8  jmp     loc_180077146
0x1800770ad  mov     edx, [rbp+cStreamDescriptors]
0x1800770b0  test    edx, edx
0x1800770b2  jnz     loc_180077169
0x1800770b8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800770bf  mov     edi, 80004005h
0x1800770c4  test    rbx, rbx
0x1800770c7  jnz     short loc_18007710A
0x1800770c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800770cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800770d6  mov     rcx, rax
0x1800770d9  test    rax, rax
0x1800770dc  jz      short loc_1800770FC
0x1800770de  mov     rax, [rax]
0x1800770e1  mov     edx, 7F0h
0x1800770e6  mov     rax, [rax+8]
0x1800770ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770ef  test    eax, eax
0x1800770f1  jz      short loc_1800770FC
0x1800770f3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800770fa  jmp     short loc_18007710A
0x1800770fc  lea     rbx, qword_1801B07E0
0x180077103  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007710a  cmp     byte ptr [rbx+8], 0
0x18007710e  jz      short loc_180077134
0x180077110  mov     rcx, rbx; this
0x180077113  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077118  cmp     [rax+7CCh], edi
0x18007711e  jz      short loc_180077134
0x180077120  mov     r9d, edi; int
0x180077123  mov     r8d, 4FAh; int
0x180077129  mov     rdx, r15; char *
0x18007712c  mov     rcx, rax; this
0x18007712f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077134  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007713b  jb      loc_180077F38
0x180077141  mov     edx, 76h ; 'v'
0x180077146  mov     rcx, cs:WPP_GLOBAL_Control
0x18007714d  lea     r8, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x180077154  mov     r9, rsi
0x180077157  mov     dword ptr [rsp+80h+var_60], edi
0x18007715b  mov     rcx, [rcx+10h]
0x18007715f  call    WPP_SF_qD
0x180077164  jmp     loc_180077F38
0x180077169  lea     rcx, [rsi+100h]
0x180077170  mov     qword ptr [rcx+1A0h], 0
0x18007717b  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x180077180  mov     ecx, [rbp+cStreamDescriptors]
0x180077183  mov     eax, 8
0x180077188  mul     rcx
0x18007718b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180077192  cmovb   rax, rcx
0x180077196  mov     rcx, rax; Size
0x180077199  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007719e  mov     r13, rax
0x1800771a1  test    rax, rax
0x1800771a4  jnz     loc_18007723D
0x1800771aa  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771b1  mov     edi, 8007000Eh
0x1800771b6  test    rbx, rbx
0x1800771b9  jnz     short loc_1800771FC
0x1800771bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800771c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771c8  mov     rcx, rax
0x1800771cb  test    rax, rax
0x1800771ce  jz      short loc_1800771EE
0x1800771d0  mov     rax, [rax]
0x1800771d3  mov     edx, 7F0h
0x1800771d8  mov     rax, [rax+8]
0x1800771dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771e1  test    eax, eax
0x1800771e3  jz      short loc_1800771EE
0x1800771e5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771ec  jmp     short loc_1800771FC
0x1800771ee  lea     rbx, qword_1801B07E0
0x1800771f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771fc  cmp     byte ptr [rbx+8], 0
0x180077200  jz      short loc_180077226
0x180077202  mov     rcx, rbx; this
0x180077205  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007720a  cmp     [rax+7CCh], edi
0x180077210  jz      short loc_180077226
0x180077212  mov     r9d, edi; int
0x180077215  mov     r8d, 507h; int
0x18007721b  mov     rdx, r15; char *
0x18007721e  mov     rcx, rax; this
0x180077221  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077226  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007722d  jb      loc_180077F38
0x180077233  mov     edx, 78h ; 'x'
0x180077238  jmp     loc_180077146
0x18007723d  mov     r8d, [rbp+cStreamDescriptors]
0x180077241  xor     edx, edx; Val
0x180077243  shl     r8, 3; Size
0x180077247  mov     rcx, r13; void *
0x18007724a  call    memset_0
0x18007724f  xor     r15d, r15d
0x180077252  lea     r12, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x180077259  mov     rcx, rsi
0x18007725c  mov     rax, [rsi]
0x18007725f  cmp     r15d, [rbp+cStreamDescriptors]
0x180077263  jnb     loc_1800778CD
0x180077269  mov     rax, [rax+88h]
0x180077270  lea     r8, [rbp+var_8]
0x180077274  xor     ebx, ebx
0x180077276  mov     edx, r15d
0x180077279  mov     [rbp+var_8], ebx
0x18007727c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077281  lea     r12, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x180077288  mov     edi, eax
0x18007728a  test    eax, eax
0x18007728c  js      loc_180077792
0x180077292  mov     rax, [rsi]
0x180077295  lea     r8, [rbp+var_38]
0x180077299  mov     edx, [rbp+var_8]
0x18007729c  mov     rcx, rsi
0x18007729f  mov     [rbp+var_38], rbx
0x1800772a3  mov     rax, [rax+90h]
0x1800772aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772af  mov     edi, eax
0x1800772b1  test    eax, eax
0x1800772b3  js      loc_1800776DE
0x1800772b9  mov     r8, [rbp+var_38]; struct IMFMediaType *
0x1800772bd  lea     r9, [rbp+var_30]; struct IMFStreamDescriptor **
0x1800772c1  mov     edx, [rbp+var_8]; unsigned int
0x1800772c4  mov     rcx, rsi; this
0x1800772c7  mov     [rbp+var_30], rbx
0x1800772cb  call    ?CreateStreamDescriptor@CMediaSourceBase@@IEAAJKPEAUIMFMediaType@@PEAPEAUIMFStreamDescriptor@@@Z; CMediaSourceBase::CreateStreamDescriptor(ulong,IMFMediaType *,IMFStreamDescriptor * *)
0x1800772d0  mov     edi, eax
0x1800772d2  test    eax, eax
0x1800772d4  js      loc_18007762A
0x1800772da  mov     [rbp+var_20], rbx
0x1800772de  lea     rdx, [rbp+var_20]
0x1800772e2  mov     rbx, [rbp+var_30]
0x1800772e6  mov     rcx, rbx
0x1800772e9  mov     rax, [rbx]
0x1800772ec  mov     rax, [rax+110h]
0x1800772f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772f8  mov     edi, eax
0x1800772fa  test    eax, eax
0x1800772fc  js      loc_180077576
0x180077302  mov     rcx, [rbp+var_38]
0x180077306  test    rcx, rcx
0x180077309  jz      short loc_18007731F
0x18007730b  mov     [rbp+var_38], 0
0x180077313  mov     rax, [rcx]
0x180077316  mov     rax, [rax+10h]
0x18007731a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007731f  mov     rcx, [rbp+var_20]
0x180077323  lea     r8, [rbp+var_38]
0x180077327  xor     edx, edx
0x180077329  mov     rax, [rcx]
0x18007732c  mov     rax, [rax+28h]
0x180077330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077335  mov     edi, eax
0x180077337  test    eax, eax
0x180077339  js      loc_1800774E1
0x18007733f  mov     rcx, [rbp+var_20]
0x180077343  mov     rdx, [rbp+var_38]
0x180077347  mov     rax, [rcx]
0x18007734a  mov     rax, [rax+30h]
0x18007734e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077353  mov     edi, eax
0x180077355  test    eax, eax
0x180077357  js      loc_18007744C
0x18007735d  mov     rax, [rsi]
0x180077360  mov     r8, rbx
0x180077363  mov     edx, [rbp+var_8]
0x180077366  mov     rcx, rsi
0x180077369  mov     rax, [rax+98h]
0x180077370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077375  mov     edi, eax
0x180077377  test    eax, eax
0x180077379  js      short loc_1800773B7
0x18007737b  mov     [r13+r15*8+0], rbx
0x180077380  test    rbx, rbx
0x180077383  jz      short loc_180077394
0x180077385  mov     rax, [rbx]
0x180077388  mov     rcx, rbx
0x18007738b  mov     rax, [rax+8]
0x18007738f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077394  lea     rcx, [rbp+var_20]; void *
0x180077398  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18007739d  lea     rcx, [rbp+var_30]; void *
0x1800773a1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800773a6  lea     rcx, [rbp+var_38]; void *
0x1800773aa  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800773af  inc     r15d
0x1800773b2  jmp     loc_180077259
0x1800773b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773be  lea     rbx, qword_1801B07E0
0x1800773c5  xor     r15d, r15d
0x1800773c8  test    rcx, rcx
0x1800773cb  jnz     short loc_18007740A
0x1800773cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800773d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773da  mov     rcx, rax
0x1800773dd  test    rax, rax
0x1800773e0  jz      short loc_180077400
0x1800773e2  mov     rax, [rax]
0x1800773e5  mov     edx, 7F0h
0x1800773ea  mov     rax, [rax+8]
0x1800773ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773f3  test    eax, eax
0x1800773f5  jz      short loc_180077400
0x1800773f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773fe  jmp     short loc_18007740A
0x180077400  mov     rcx, rbx; this
0x180077403  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007740a  cmp     [rcx+8], r15b
0x18007740e  jz      short loc_180077435
0x180077410  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077415  cmp     [rax+7CCh], edi
0x18007741b  jz      short loc_180077435
0x18007741d  mov     r9d, edi; int
0x180077420  lea     rdx, aCmediasourceba_32; "CMediaSourceBase::CreatePresentationDes"...
0x180077427  mov     r8d, 532h; int
0x18007742d  mov     rcx, rax; this
0x180077430  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077435  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007743c  jb      loc_18007761C
0x180077442  mov     edx, 7Fh
0x180077447  jmp     loc_180077602
0x18007744c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077453  lea     rbx, qword_1801B07E0
0x18007745a  xor     r15d, r15d
0x18007745d  test    rcx, rcx
0x180077460  jnz     short loc_18007749F
0x180077462  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077468  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007746f  mov     rcx, rax
0x180077472  test    rax, rax
0x180077475  jz      short loc_180077495
0x180077477  mov     rax, [rax]
0x18007747a  mov     edx, 7F0h
0x18007747f  mov     rax, [rax+8]
0x180077483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077488  test    eax, eax
0x18007748a  jz      short loc_180077495
0x18007748c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077493  jmp     short loc_18007749F
0x180077495  mov     rcx, rbx; this
0x180077498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007749f  cmp     [rcx+8], r15b
  ... truncated ...
```
