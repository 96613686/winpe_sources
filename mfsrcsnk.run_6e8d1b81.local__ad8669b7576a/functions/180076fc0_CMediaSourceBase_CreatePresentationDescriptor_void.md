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
  wchar_t *v6; // rbx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rbx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  IMFStreamDescriptor **v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  IMFStreamDescriptor **v17; // r13
  wchar_t *v18; // rbx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 i; // r15
  __int64 v22; // rax
  __int64 (__fastcall *v23)(CMediaSourceBase *, _QWORD, unsigned int *); // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  struct IMFStreamDescriptor *v29; // rbx
  __int64 v30; // rdx
  struct IMFMediaType *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rcx
  wchar_t *v62; // rbx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  int (__fastcall ***v65)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  wchar_t *v68; // rbx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  _QWORD *v72; // rbx
  __int64 v73; // rdx
  __int64 v74; // rcx
  wchar_t *v75; // rbx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  wchar_t *v83; // rbx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  wchar_t *v86; // rbx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  int (__fastcall ***v89)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v90; // rdx
  __int64 v91; // rcx
  wchar_t *v92; // rbx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rcx
  int v98; // r9d
  wchar_t *v99; // rbx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  DWORD v102; // eax
  DWORD j; // ebx
  IMFStreamDescriptor *v104; // rcx
  DWORD cStreamDescriptors; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v107[4]; // [rsp+44h] [rbp-3Ch] BYREF
  struct IMFMediaType *v108; // [rsp+48h] [rbp-38h] BYREF
  struct IMFStreamDescriptor *v109; // [rsp+50h] [rbp-30h] BYREF
  __int64 v110; // [rsp+58h] [rbp-28h] BYREF
  __int64 v111; // [rsp+60h] [rbp-20h] BYREF
  __int64 v112; // [rsp+68h] [rbp-18h] BYREF
  __int64 v113; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v114; // [rsp+78h] [rbp-8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v107,
    "CMediaSourceBase::CreatePresentationDescriptor",
    1260);
  v2 = *(_QWORD *)this;
  cStreamDescriptors = 0;
  v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, DWORD *))(v2 + 128))(this, &cStreamDescriptors);
  if ( v5 < 0 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v4, v3);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMediaSourceBase::CreatePresentationDescriptor",
          1271,
          v5);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v9 = 117;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
LABEL_228:
    ComSmartPtr<IUnknown>::Release((char *)this + 240);
    goto LABEL_229;
  }
  v10 = cStreamDescriptors;
  if ( !cStreamDescriptors )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v4, cStreamDescriptors);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v13, "CMediaSourceBase::CreatePresentationDescriptor", 1274, -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v9 = 118;
    goto LABEL_23;
  }
  *((_QWORD *)this + 84) = 0;
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init((char *)this + 256, v10);
  v14 = (IMFStreamDescriptor **)operator new(saturated_mul(cStreamDescriptors, 8u));
  v17 = v14;
  if ( !v14 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v20, "CMediaSourceBase::CreatePresentationDescriptor", 1287, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v9 = 120;
    goto LABEL_23;
  }
  memset_0(v14, 0, 8LL * cStreamDescriptors);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v22 = *(_QWORD *)this;
    if ( (unsigned int)i >= cStreamDescriptors )
      break;
    v23 = *(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, unsigned int *))(v22 + 136);
    v114 = 0;
    v5 = v23(this, (unsigned int)i, &v114);
    if ( v5 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
        CallStackTracing::s_wpInstance = v55;
        if ( !v55 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      v54 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v56 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v56 + 499) != v5 )
          CallStackContext::TraceFailure(v56, "CMediaSourceBase::CreatePresentationDescriptor", 1296, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_122;
    }
    v26 = *(_QWORD *)this;
    v108 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFMediaType **))(v26 + 144))(this, v114, &v108);
    if ( v5 < 0 )
    {
      v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v52;
        if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
        {
          v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v51 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
        if ( *((_DWORD *)v53 + 499) != v5 )
          CallStackContext::TraceFailure(v53, "CMediaSourceBase::CreatePresentationDescriptor", 1303, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_112;
    }
    v109 = 0;
    v5 = CMediaSourceBase::CreateStreamDescriptor(this, v114, v108, &v109);
    if ( v5 < 0 )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)v50 + 499) != v5 )
          CallStackContext::TraceFailure(v50, "CMediaSourceBase::CreatePresentationDescriptor", 1310, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_101;
    }
    v111 = 0;
    v29 = v109;
    v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))v109->lpVtbl->GetMediaTypeHandler)(
           v109,
           &v111);
    if ( v5 < 0 )
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v5 )
          CallStackContext::TraceFailure(v47, "CMediaSourceBase::CreatePresentationDescriptor", 1317, v5);
      }
      if ( g_wppLevels )
      {
        v38 = 124;
LABEL_89:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      }
LABEL_90:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v111);
LABEL_101:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v109);
LABEL_112:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v108);
LABEL_122:
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v54, v24);
        CallStackTracing::s_wpInstance = v57;
        if ( !v57 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v58 + 499) != v5 )
          CallStackContext::TraceFailure(v58, "CMediaSourceBase::CreatePresentationDescriptor", 1338, v5);
      }
      if ( g_wppLevels )
      {
        v59 = 128;
LABEL_131:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
        goto LABEL_223;
      }
      goto LABEL_223;
    }
    v31 = v108;
    if ( v108 )
    {
      v108 = 0;
      ((void (__fastcall *)(struct IMFMediaType *))v31->lpVtbl->Release)(v31);
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v111 + 40LL))(v111, 0, &v108);
    if ( v5 < 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != v5 )
          CallStackContext::TraceFailure(v44, "CMediaSourceBase::CreatePresentationDescriptor", 1321, v5);
      }
      if ( g_wppLevels )
      {
        v38 = 125;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, struct IMFMediaType *))(*(_QWORD *)v111 + 48LL))(v111, v108);
    if ( v5 < 0 )
    {
      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != v5 )
          CallStackContext::TraceFailure(v41, "CMediaSourceBase::CreatePresentationDescriptor", 1324, v5);
      }
      if ( g_wppLevels )
      {
        v38 = 126;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFStreamDescriptor *))(*(_QWORD *)this + 152LL))(
           this,
           v114,
           v29);
    if ( v5 < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v5 )
          CallStackContext::TraceFailure(v37, "CMediaSourceBase::CreatePresentationDescriptor", 1330, v5);
      }
      if ( g_wppLevels )
      {
        v38 = 127;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v17[i] = v29;
    if ( v29 )
      ((void (__fastcall *)(struct IMFStreamDescriptor *))v29->lpVtbl->AddRef)(v29);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v111);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v109);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v108);
  }
  v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(v22 + 112))(this);
  if ( v5 >= 0 )
  {
    v65 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v110 = 0;
    if ( (**v65)(v65, &IID_IMFMediaEventGenerator, &v110) >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v110 + 32LL))(
             v110,
             (char *)this + 184,
             *((_QWORD *)this + 90));
      if ( v5 < 0 )
      {
        v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v67, v66);
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
            CallStackContext::TraceFailure(v70, "CMediaSourceBase::CreatePresentationDescriptor", 1351, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v71 = 130;
        goto LABEL_155;
      }
    }
    v72 = (_QWORD *)((char *)this + 240);
    v5 = MFCreatePresentationDescriptor(cStreamDescriptors, v17, (IMFPresentationDescriptor **)this + 30);
    if ( v5 < 0 )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v74, v73);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v77 + 499) != v5 )
          CallStackContext::TraceFailure(v77, "CMediaSourceBase::CreatePresentationDescriptor", 1361, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_222;
      v71 = 131;
      goto LABEL_155;
    }
    v78 = *(_QWORD *)this;
    v113 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, __int64 *))(v78 + 120))(this, &v113);
    if ( v5 < 0 )
    {
      if ( v5 != -1072875781 )
      {
        v86 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v80, v79);
          CallStackTracing::s_wpInstance = v87;
          if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
          {
            v86 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v86 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v86 + 8) )
        {
          v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
          if ( *((_DWORD *)v88 + 499) != v5 )
            CallStackContext::TraceFailure(v88, "CMediaSourceBase::CreatePresentationDescriptor", 1375, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v71 = 133;
LABEL_155:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v71, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
LABEL_222:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v110);
        goto LABEL_223;
      }
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v72 + 176LL))(
             *v72,
             &MF_PD_DURATION,
             v113);
      if ( v5 < 0 )
      {
        v83 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v82, v81);
          CallStackTracing::s_wpInstance = v84;
          if ( v84 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
          {
            v83 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v83 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v83 + 8) )
        {
          v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
          if ( *((_DWORD *)v85 + 499) != v5 )
            CallStackContext::TraceFailure(v85, "CMediaSourceBase::CreatePresentationDescriptor", 1371, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v71 = 132;
        goto LABEL_155;
      }
    }
    v89 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v112 = 0;
    if ( (**v89)(v89, &IID_IMFAttributes, &v112) >= 0 )
    {
      v109 = 0;
      v114 = 0;
      if ( (*(int (__fastcall **)(__int64, const IID *, struct IMFStreamDescriptor **, __int64, unsigned int *))(*(_QWORD *)v112 + 120LL))(
             v112,
             &MF_BYTESTREAM_LAST_MODIFIED_TIME,
             &v109,
             8,
             &v114) >= 0
        && v114 == 8 )
      {
        (*(void (__fastcall **)(_QWORD, const IID *, struct IMFStreamDescriptor **, __int64))(*(_QWORD *)*v72 + 208LL))(
          *v72,
          &MF_PD_LAST_MODIFIED_TIME,
          &v109,
          8);
      }
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(*(_QWORD *)this + 200LL))(this);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD))(*(_QWORD *)this + 160LL))(this, *v72);
      if ( v5 >= 0 )
      {
        if ( (unsigned __int8)byte_1801B110B >= 4u )
          WPP_SF_sq(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            136,
            (unsigned int)&WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
            v98,
            (__int64)this);
        if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
        {
          v114 = 1635018061;
          McTemplateU0s4pdpp_EventWriteTransfer(
            v97,
            (unsigned int)Metadata_Loaded,
            (unsigned int)&v114,
            (_DWORD)this,
            v5);
        }
        goto LABEL_221;
      }
      v99 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v97, v96);
        CallStackTracing::s_wpInstance = v100;
        if ( v100 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
        {
          v99 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v99 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v99 + 8) )
      {
        v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
        if ( *((_DWORD *)v101 + 499) != v5 )
          CallStackContext::TraceFailure(v101, "CMediaSourceBase::CreatePresentationDescriptor", 1405, v5);
      }
      if ( !g_wppLevels )
      {
LABEL_221:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v112);
        goto LABEL_222;
      }
      v95 = 135;
    }
    else
    {
      v92 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v91, v90);
        CallStackTracing::s_wpInstance = v93;
        if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
        {
          v92 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v92 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v92 + 8) )
      {
        v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
        if ( *((_DWORD *)v94 + 499) != v5 )
          CallStackContext::TraceFailure(v94, "CMediaSourceBase::CreatePresentationDescriptor", 1399, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_221;
      v95 = 134;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v95, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
    goto LABEL_221;
  }
  v62 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v61, v60);
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
      CallStackContext::TraceFailure(v64, "CMediaSourceBase::CreatePresentationDescriptor", 1344, v5);
  }
  if ( g_wppLevels )
  {
    v59 = 129;
    goto LABEL_131;
  }
LABEL_223:
  v102 = cStreamDescriptors;
  for ( j = 0; j < v102; ++j )
  {
    v104 = v17[j];
    if ( v104 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v104->lpVtbl->Release)(v104);
      v17[j] = 0;
      v102 = cStreamDescriptors;
    }
  }
  operator delete(v17);
  if ( v5 < 0 )
    goto LABEL_228;
LABEL_229:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v107);
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
