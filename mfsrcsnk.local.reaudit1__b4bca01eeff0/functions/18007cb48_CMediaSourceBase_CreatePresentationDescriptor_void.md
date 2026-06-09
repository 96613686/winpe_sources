# CMediaSourceBase::CreatePresentationDescriptor(void)

- ea: `0x18007cb48`
- end: `0x18007db66`
- name: `?CreatePresentationDescriptor@CMediaSourceBase@@IEAAJXZ`
- size: `4126`
- prototype: `__int64 __fastcall(CMediaSourceBase *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180072b98`
- `0x180074218`

## callees

- `0x180005cf4`
- `0x18000a080`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800476a0`
- `0x180079680`
- `0x18007cb48`
- `0x1800a7e40`
- `0x180110a7c`
- `0x180110a94`
- `0x180111960`
- `0x18015cbec`
- `0x180177948`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cbb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cc57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cd4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cf67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d09d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d1f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d2ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d3fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d4b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d5a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d67a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d75a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d7fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d936`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007da07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cbb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cc57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cd4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cf67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d09d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d1f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d2ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d3fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d4b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d5a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d67a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d75a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d7fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d936`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007da07`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18007d658`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18007d658`

## string_xrefs

- `0x18007cb67`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007cfc0`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d05b`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d0f6`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d191`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d24b`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d305`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d3b7`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d451`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d519`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d602`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d6da`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d7ba`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d85e`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007d996`: `CMediaSourceBase::CreatePresentationDescriptor`
- `0x18007da67`: `CMediaSourceBase::CreatePresentationDescriptor`

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
  wchar_t *v10; // rbx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  IMFStreamDescriptor **v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  IMFStreamDescriptor **v16; // r13
  wchar_t *v17; // rbx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 i; // r15
  __int64 v21; // rax
  __int64 (__fastcall *v22)(CMediaSourceBase *, _QWORD, unsigned int *); // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  struct IMFStreamDescriptor *v28; // rbx
  __int64 v29; // rdx
  struct IMFMediaType *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rcx
  wchar_t *v61; // rbx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  int (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v65; // rdx
  __int64 v66; // rcx
  wchar_t *v67; // rbx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  _QWORD *v71; // rbx
  __int64 v72; // rdx
  __int64 v73; // rcx
  wchar_t *v74; // rbx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  wchar_t *v82; // rbx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  wchar_t *v85; // rbx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  int (__fastcall ***v88)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v89; // rdx
  __int64 v90; // rcx
  wchar_t *v91; // rbx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rdx
  __int64 v96; // rcx
  int v97; // r9d
  wchar_t *v98; // rbx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  DWORD v101; // eax
  DWORD j; // ebx
  IMFStreamDescriptor *v103; // rcx
  DWORD cStreamDescriptors; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v106[4]; // [rsp+44h] [rbp-3Ch] BYREF
  struct IMFMediaType *v107; // [rsp+48h] [rbp-38h] BYREF
  struct IMFStreamDescriptor *v108; // [rsp+50h] [rbp-30h] BYREF
  __int64 v109; // [rsp+58h] [rbp-28h] BYREF
  __int64 v110; // [rsp+60h] [rbp-20h] BYREF
  __int64 v111; // [rsp+68h] [rbp-18h] BYREF
  __int64 v112; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v113; // [rsp+78h] [rbp-8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v106,
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
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( !cStreamDescriptors )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v4, cStreamDescriptors);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v12, "CMediaSourceBase::CreatePresentationDescriptor", 1274, -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v9 = 118;
    goto LABEL_23;
  }
  *((_QWORD *)this + 84) = 0;
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init();
  v13 = (IMFStreamDescriptor **)operator new(saturated_mul(cStreamDescriptors, 8u));
  v16 = v13;
  if ( !v13 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, v14);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v19, "CMediaSourceBase::CreatePresentationDescriptor", 1287, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v9 = 120;
    goto LABEL_23;
  }
  memset_0(v13, 0, 8LL * cStreamDescriptors);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v21 = *(_QWORD *)this;
    if ( (unsigned int)i >= cStreamDescriptors )
      break;
    v22 = *(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, unsigned int *))(v21 + 136);
    v113 = 0;
    v5 = v22(this, (unsigned int)i, &v113);
    if ( v5 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23);
        CallStackTracing::s_wpInstance = v54;
        if ( !v54 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      v53 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v55 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v55 + 499) != v5 )
          CallStackContext::TraceFailure(v55, "CMediaSourceBase::CreatePresentationDescriptor", 1296, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_122;
    }
    v25 = *(_QWORD *)this;
    v107 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFMediaType **))(v25 + 144))(this, v113, &v107);
    if ( v5 < 0 )
    {
      v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v5 )
          CallStackContext::TraceFailure(v52, "CMediaSourceBase::CreatePresentationDescriptor", 1303, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_112;
    }
    v108 = 0;
    v5 = CMediaSourceBase::CreateStreamDescriptor(this, v113, v107, &v108);
    if ( v5 < 0 )
    {
      v47 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v49 + 499) != v5 )
          CallStackContext::TraceFailure(v49, "CMediaSourceBase::CreatePresentationDescriptor", 1310, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      goto LABEL_101;
    }
    v110 = 0;
    v28 = v108;
    v5 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))v108->lpVtbl->GetMediaTypeHandler)(
           v108,
           &v110);
    if ( v5 < 0 )
    {
      v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v5 )
          CallStackContext::TraceFailure(v46, "CMediaSourceBase::CreatePresentationDescriptor", 1317, v5);
      }
      if ( g_wppLevels )
      {
        v37 = 124;
LABEL_89:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
      }
LABEL_90:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v110);
LABEL_101:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v108);
LABEL_112:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v107);
LABEL_122:
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v53, v23);
        CallStackTracing::s_wpInstance = v56;
        if ( !v56 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v57 + 499) != v5 )
          CallStackContext::TraceFailure(v57, "CMediaSourceBase::CreatePresentationDescriptor", 1338, v5);
      }
      if ( g_wppLevels )
      {
        v58 = 128;
LABEL_131:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v58, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
        goto LABEL_223;
      }
      goto LABEL_223;
    }
    v30 = v107;
    if ( v107 )
    {
      v107 = 0;
      ((void (__fastcall *)(struct IMFMediaType *))v30->lpVtbl->Release)(v30);
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v110 + 40LL))(v110, 0, &v107);
    if ( v5 < 0 )
    {
      v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != v5 )
          CallStackContext::TraceFailure(v43, "CMediaSourceBase::CreatePresentationDescriptor", 1321, v5);
      }
      if ( g_wppLevels )
      {
        v37 = 125;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, struct IMFMediaType *))(*(_QWORD *)v110 + 48LL))(v110, v107);
    if ( v5 < 0 )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v5 )
          CallStackContext::TraceFailure(v40, "CMediaSourceBase::CreatePresentationDescriptor", 1324, v5);
      }
      if ( g_wppLevels )
      {
        v37 = 126;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD, struct IMFStreamDescriptor *))(*(_QWORD *)this + 152LL))(
           this,
           v113,
           v28);
    if ( v5 < 0 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != v5 )
          CallStackContext::TraceFailure(v36, "CMediaSourceBase::CreatePresentationDescriptor", 1330, v5);
      }
      if ( g_wppLevels )
      {
        v37 = 127;
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v16[i] = v28;
    if ( v28 )
      ((void (__fastcall *)(struct IMFStreamDescriptor *))v28->lpVtbl->AddRef)(v28);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v110);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v108);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v107);
  }
  v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(v21 + 112))(this);
  if ( v5 >= 0 )
  {
    v64 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v109 = 0;
    if ( (**v64)(v64, &IID_IMFMediaEventGenerator, &v109) >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v109 + 32LL))(
             v109,
             (char *)this + 184,
             *((_QWORD *)this + 90));
      if ( v5 < 0 )
      {
        v67 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v65);
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v67 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v67 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
          if ( *((_DWORD *)v69 + 499) != v5 )
            CallStackContext::TraceFailure(v69, "CMediaSourceBase::CreatePresentationDescriptor", 1351, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v70 = 130;
        goto LABEL_155;
      }
    }
    v71 = (_QWORD *)((char *)this + 240);
    v5 = MFCreatePresentationDescriptor(cStreamDescriptors, v16, (IMFPresentationDescriptor **)this + 30);
    if ( v5 < 0 )
    {
      v74 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v73, v72);
        CallStackTracing::s_wpInstance = v75;
        if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
        {
          v74 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v74 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
        if ( *((_DWORD *)v76 + 499) != v5 )
          CallStackContext::TraceFailure(v76, "CMediaSourceBase::CreatePresentationDescriptor", 1361, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_222;
      v70 = 131;
      goto LABEL_155;
    }
    v77 = *(_QWORD *)this;
    v112 = 0;
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, __int64 *))(v77 + 120))(this, &v112);
    if ( v5 < 0 )
    {
      if ( v5 != -1072875781 )
      {
        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v79, v78);
          CallStackTracing::s_wpInstance = v86;
          if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
          {
            v85 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v85 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v85 + 8) )
        {
          v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
          if ( *((_DWORD *)v87 + 499) != v5 )
            CallStackContext::TraceFailure(v87, "CMediaSourceBase::CreatePresentationDescriptor", 1375, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v70 = 133;
LABEL_155:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v70, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
LABEL_222:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v109);
        goto LABEL_223;
      }
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v71 + 176LL))(
             *v71,
             &MF_PD_DURATION,
             v112);
      if ( v5 < 0 )
      {
        v82 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v81, v80);
          CallStackTracing::s_wpInstance = v83;
          if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
          {
            v82 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v82 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v82 + 8) )
        {
          v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
          if ( *((_DWORD *)v84 + 499) != v5 )
            CallStackContext::TraceFailure(v84, "CMediaSourceBase::CreatePresentationDescriptor", 1371, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v70 = 132;
        goto LABEL_155;
      }
    }
    v88 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    v111 = 0;
    if ( (**v88)(v88, &IID_IMFAttributes, &v111) >= 0 )
    {
      v108 = 0;
      v113 = 0;
      if ( (*(int (__fastcall **)(__int64, const IID *, struct IMFStreamDescriptor **, __int64, unsigned int *))(*(_QWORD *)v111 + 120LL))(
             v111,
             &MF_BYTESTREAM_LAST_MODIFIED_TIME,
             &v108,
             8,
             &v113) >= 0
        && v113 == 8 )
      {
        (*(void (__fastcall **)(_QWORD, const IID *, struct IMFStreamDescriptor **, __int64))(*(_QWORD *)*v71 + 208LL))(
          *v71,
          &MF_PD_LAST_MODIFIED_TIME,
          &v108,
          8);
      }
    }
    v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *))(*(_QWORD *)this + 200LL))(this);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(CMediaSourceBase *, _QWORD))(*(_QWORD *)this + 160LL))(this, *v71);
      if ( v5 >= 0 )
      {
        if ( (unsigned __int8)byte_1801BA10B >= 4u )
          WPP_SF_sq(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            136,
            (unsigned int)&WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
            v97,
            (__int64)this);
        if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
        {
          v113 = 1635018061;
          McTemplateU0s4pdpp_EventWriteTransfer(
            v96,
            (unsigned int)Metadata_Loaded,
            (unsigned int)&v113,
            (_DWORD)this,
            v5);
        }
        goto LABEL_221;
      }
      v98 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v96, v95);
        CallStackTracing::s_wpInstance = v99;
        if ( v99 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
        {
          v98 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v98 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v98 + 8) )
      {
        v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
        if ( *((_DWORD *)v100 + 499) != v5 )
          CallStackContext::TraceFailure(v100, "CMediaSourceBase::CreatePresentationDescriptor", 1405, v5);
      }
      if ( !g_wppLevels )
      {
LABEL_221:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v111);
        goto LABEL_222;
      }
      v94 = 135;
    }
    else
    {
      v91 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v90, v89);
        CallStackTracing::s_wpInstance = v92;
        if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
        {
          v91 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v91 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v91 + 8) )
      {
        v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
        if ( *((_DWORD *)v93 + 499) != v5 )
          CallStackContext::TraceFailure(v93, "CMediaSourceBase::CreatePresentationDescriptor", 1399, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_221;
      v94 = 134;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v94, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v5);
    goto LABEL_221;
  }
  v61 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v60, v59);
    CallStackTracing::s_wpInstance = v62;
    if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
    {
      v61 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v61 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v61 + 8) )
  {
    v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
    if ( *((_DWORD *)v63 + 499) != v5 )
      CallStackContext::TraceFailure(v63, "CMediaSourceBase::CreatePresentationDescriptor", 1344, v5);
  }
  if ( g_wppLevels )
  {
    v58 = 129;
    goto LABEL_131;
  }
LABEL_223:
  v101 = cStreamDescriptors;
  for ( j = 0; j < v101; ++j )
  {
    v103 = v16[j];
    if ( v103 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v103->lpVtbl->Release)(v103);
      v16[j] = 0;
      v101 = cStreamDescriptors;
    }
  }
  operator delete(v16);
  if ( v5 < 0 )
    goto LABEL_228;
LABEL_229:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v106);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007cb48  mov     [rsp-28h+arg_8], rbx
0x18007cb4d  mov     [rsp-28h+arg_10], rsi
0x18007cb52  push    rbp
0x18007cb53  push    rdi
0x18007cb54  push    r12
0x18007cb56  push    r13
0x18007cb58  push    r15
0x18007cb5a  mov     rbp, rsp
0x18007cb5d  sub     rsp, 80h
0x18007cb64  mov     rsi, rcx
0x18007cb67  lea     r15, aCmediasourceba_32; "CMediaSourceBase::CreatePresentationDes"...
0x18007cb6e  mov     rdx, r15; char *
0x18007cb71  lea     rcx, [rbp+var_3C]; this
0x18007cb75  mov     r8d, 4ECh; int
0x18007cb7b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007cb80  mov     rax, [rsi]
0x18007cb83  lea     rdx, [rbp+cStreamDescriptors]
0x18007cb87  mov     rcx, rsi
0x18007cb8a  mov     [rbp+cStreamDescriptors], 0
0x18007cb91  mov     rax, [rax+80h]
0x18007cb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb9d  mov     edi, eax
0x18007cb9f  test    eax, eax
0x18007cba1  jns     loc_18007CC3B
0x18007cba7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cbae  test    rbx, rbx
0x18007cbb1  jnz     short loc_18007CBFA
0x18007cbb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007cbba  nop     dword ptr [rax+rax+00h]
0x18007cbbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cbc6  mov     rcx, rax
0x18007cbc9  test    rax, rax
0x18007cbcc  jz      short loc_18007CBEC
0x18007cbce  mov     rax, [rax]
0x18007cbd1  mov     edx, 7F0h
0x18007cbd6  mov     rax, [rax+8]
0x18007cbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cbdf  test    eax, eax
0x18007cbe1  jz      short loc_18007CBEC
0x18007cbe3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cbea  jmp     short loc_18007CBFA
0x18007cbec  lea     rbx, qword_1801B97E0
0x18007cbf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cbfa  cmp     byte ptr [rbx+8], 0
0x18007cbfe  jz      short loc_18007CC24
0x18007cc00  mov     rcx, rbx; this
0x18007cc03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007cc08  cmp     [rax+7CCh], edi
0x18007cc0e  jz      short loc_18007CC24
0x18007cc10  mov     r9d, edi; int
0x18007cc13  mov     r8d, 4F7h; int
0x18007cc19  mov     rdx, r15; char *
0x18007cc1c  mov     rcx, rax; this
0x18007cc1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007cc24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cc2b  jb      loc_18007DB32
0x18007cc31  mov     edx, 75h ; 'u'
0x18007cc36  jmp     loc_18007CCDA
0x18007cc3b  mov     edx, [rbp+cStreamDescriptors]
0x18007cc3e  test    edx, edx
0x18007cc40  jnz     loc_18007CCFD
0x18007cc46  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cc4d  mov     edi, 80004005h
0x18007cc52  test    rbx, rbx
0x18007cc55  jnz     short loc_18007CC9E
0x18007cc57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007cc5e  nop     dword ptr [rax+rax+00h]
0x18007cc63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cc6a  mov     rcx, rax
0x18007cc6d  test    rax, rax
0x18007cc70  jz      short loc_18007CC90
0x18007cc72  mov     rax, [rax]
0x18007cc75  mov     edx, 7F0h
0x18007cc7a  mov     rax, [rax+8]
0x18007cc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc83  test    eax, eax
0x18007cc85  jz      short loc_18007CC90
0x18007cc87  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cc8e  jmp     short loc_18007CC9E
0x18007cc90  lea     rbx, qword_1801B97E0
0x18007cc97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cc9e  cmp     byte ptr [rbx+8], 0
0x18007cca2  jz      short loc_18007CCC8
0x18007cca4  mov     rcx, rbx; this
0x18007cca7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ccac  cmp     [rax+7CCh], edi
0x18007ccb2  jz      short loc_18007CCC8
0x18007ccb4  mov     r9d, edi; int
0x18007ccb7  mov     r8d, 4FAh; int
0x18007ccbd  mov     rdx, r15; char *
0x18007ccc0  mov     rcx, rax; this
0x18007ccc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ccc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cccf  jb      loc_18007DB32
0x18007ccd5  mov     edx, 76h ; 'v'
0x18007ccda  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cce1  lea     r8, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x18007cce8  mov     r9, rsi
0x18007cceb  mov     dword ptr [rsp+80h+var_60], edi
0x18007ccef  mov     rcx, [rcx+10h]
0x18007ccf3  call    WPP_SF_qD
0x18007ccf8  jmp     loc_18007DB32
0x18007ccfd  lea     rcx, [rsi+100h]
0x18007cd04  mov     qword ptr [rcx+1A0h], 0
0x18007cd0f  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x18007cd14  mov     ecx, [rbp+cStreamDescriptors]
0x18007cd17  mov     eax, 8
0x18007cd1c  mul     rcx
0x18007cd1f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007cd26  cmovb   rax, rcx
0x18007cd2a  mov     rcx, rax; Size
0x18007cd2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007cd32  mov     r13, rax
0x18007cd35  test    rax, rax
0x18007cd38  jnz     loc_18007CDD7
0x18007cd3e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cd45  mov     edi, 8007000Eh
0x18007cd4a  test    rbx, rbx
0x18007cd4d  jnz     short loc_18007CD96
0x18007cd4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007cd56  nop     dword ptr [rax+rax+00h]
0x18007cd5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cd62  mov     rcx, rax
0x18007cd65  test    rax, rax
0x18007cd68  jz      short loc_18007CD88
0x18007cd6a  mov     rax, [rax]
0x18007cd6d  mov     edx, 7F0h
0x18007cd72  mov     rax, [rax+8]
0x18007cd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd7b  test    eax, eax
0x18007cd7d  jz      short loc_18007CD88
0x18007cd7f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cd86  jmp     short loc_18007CD96
0x18007cd88  lea     rbx, qword_1801B97E0
0x18007cd8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cd96  cmp     byte ptr [rbx+8], 0
0x18007cd9a  jz      short loc_18007CDC0
0x18007cd9c  mov     rcx, rbx; this
0x18007cd9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007cda4  cmp     [rax+7CCh], edi
0x18007cdaa  jz      short loc_18007CDC0
0x18007cdac  mov     r9d, edi; int
0x18007cdaf  mov     r8d, 507h; int
0x18007cdb5  mov     rdx, r15; char *
0x18007cdb8  mov     rcx, rax; this
0x18007cdbb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007cdc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cdc7  jb      loc_18007DB32
0x18007cdcd  mov     edx, 78h ; 'x'
0x18007cdd2  jmp     loc_18007CCDA
0x18007cdd7  mov     r8d, [rbp+cStreamDescriptors]
0x18007cddb  xor     edx, edx; Val
0x18007cddd  shl     r8, 3; Size
0x18007cde1  mov     rcx, r13; void *
0x18007cde4  call    memset_0
0x18007cde9  xor     r15d, r15d
0x18007cdec  lea     r12, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x18007cdf3  mov     rcx, rsi
0x18007cdf6  mov     rax, [rsi]
0x18007cdf9  cmp     r15d, [rbp+cStreamDescriptors]
0x18007cdfd  jnb     loc_18007D497
0x18007ce03  mov     rax, [rax+88h]
0x18007ce0a  lea     r8, [rbp+var_8]
0x18007ce0e  xor     ebx, ebx
0x18007ce10  mov     edx, r15d
0x18007ce13  mov     [rbp+var_8], ebx
0x18007ce16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce1b  lea     r12, WPP_735b9883034235cea6dbd7724b1afea7_Traceguids
0x18007ce22  mov     edi, eax
0x18007ce24  test    eax, eax
0x18007ce26  js      loc_18007D350
0x18007ce2c  mov     rax, [rsi]
0x18007ce2f  lea     r8, [rbp+var_38]
0x18007ce33  mov     edx, [rbp+var_8]
0x18007ce36  mov     rcx, rsi
0x18007ce39  mov     [rbp+var_38], rbx
0x18007ce3d  mov     rax, [rax+90h]
0x18007ce44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce49  mov     edi, eax
0x18007ce4b  test    eax, eax
0x18007ce4d  js      loc_18007D296
0x18007ce53  mov     r8, [rbp+var_38]; struct IMFMediaType *
0x18007ce57  lea     r9, [rbp+var_30]; struct IMFStreamDescriptor **
0x18007ce5b  mov     edx, [rbp+var_8]; unsigned int
0x18007ce5e  mov     rcx, rsi; this
0x18007ce61  mov     [rbp+var_30], rbx
0x18007ce65  call    ?CreateStreamDescriptor@CMediaSourceBase@@IEAAJKPEAUIMFMediaType@@PEAPEAUIMFStreamDescriptor@@@Z; CMediaSourceBase::CreateStreamDescriptor(ulong,IMFMediaType *,IMFStreamDescriptor * *)
0x18007ce6a  mov     edi, eax
0x18007ce6c  test    eax, eax
0x18007ce6e  js      loc_18007D1DC
0x18007ce74  mov     [rbp+var_20], rbx
0x18007ce78  lea     rdx, [rbp+var_20]
0x18007ce7c  mov     rbx, [rbp+var_30]
0x18007ce80  mov     rcx, rbx
0x18007ce83  mov     rax, [rbx]
0x18007ce86  mov     rax, [rax+110h]
0x18007ce8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce92  mov     edi, eax
0x18007ce94  test    eax, eax
0x18007ce96  js      loc_18007D122
0x18007ce9c  mov     rcx, [rbp+var_38]
0x18007cea0  test    rcx, rcx
0x18007cea3  jz      short loc_18007CEB9
0x18007cea5  mov     [rbp+var_38], 0
0x18007cead  mov     rax, [rcx]
0x18007ceb0  mov     rax, [rax+10h]
0x18007ceb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ceb9  mov     rcx, [rbp+var_20]
0x18007cebd  lea     r8, [rbp+var_38]
0x18007cec1  xor     edx, edx
0x18007cec3  mov     rax, [rcx]
0x18007cec6  mov     rax, [rax+28h]
0x18007ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cecf  mov     edi, eax
0x18007ced1  test    eax, eax
0x18007ced3  js      loc_18007D087
0x18007ced9  mov     rcx, [rbp+var_20]
0x18007cedd  mov     rdx, [rbp+var_38]
0x18007cee1  mov     rax, [rcx]
0x18007cee4  mov     rax, [rax+30h]
0x18007cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ceed  mov     edi, eax
0x18007ceef  test    eax, eax
0x18007cef1  js      loc_18007CFEC
0x18007cef7  mov     rax, [rsi]
0x18007cefa  mov     r8, rbx
0x18007cefd  mov     edx, [rbp+var_8]
0x18007cf00  mov     rcx, rsi
0x18007cf03  mov     rax, [rax+98h]
0x18007cf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf0f  mov     edi, eax
0x18007cf11  test    eax, eax
0x18007cf13  js      short loc_18007CF51
0x18007cf15  mov     [r13+r15*8+0], rbx
0x18007cf1a  test    rbx, rbx
0x18007cf1d  jz      short loc_18007CF2E
0x18007cf1f  mov     rax, [rbx]
0x18007cf22  mov     rcx, rbx
0x18007cf25  mov     rax, [rax+8]
0x18007cf29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf2e  lea     rcx, [rbp+var_20]; void *
0x18007cf32  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18007cf37  lea     rcx, [rbp+var_30]; void *
0x18007cf3b  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18007cf40  lea     rcx, [rbp+var_38]; void *
0x18007cf44  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18007cf49  inc     r15d
0x18007cf4c  jmp     loc_18007CDF3
0x18007cf51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cf58  lea     rbx, qword_1801B97E0
0x18007cf5f  xor     r15d, r15d
0x18007cf62  test    rcx, rcx
0x18007cf65  jnz     short loc_18007CFAA
0x18007cf67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007cf6e  nop     dword ptr [rax+rax+00h]
0x18007cf73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cf7a  mov     rcx, rax
0x18007cf7d  test    rax, rax
0x18007cf80  jz      short loc_18007CFA0
0x18007cf82  mov     rax, [rax]
0x18007cf85  mov     edx, 7F0h
0x18007cf8a  mov     rax, [rax+8]
0x18007cf8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf93  test    eax, eax
0x18007cf95  jz      short loc_18007CFA0
0x18007cf97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cf9e  jmp     short loc_18007CFAA
0x18007cfa0  mov     rcx, rbx; this
0x18007cfa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cfaa  cmp     [rcx+8], r15b
0x18007cfae  jz      short loc_18007CFD5
0x18007cfb0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007cfb5  cmp     [rax+7CCh], edi
0x18007cfbb  jz      short loc_18007CFD5
0x18007cfbd  mov     r9d, edi; int
0x18007cfc0  lea     rdx, aCmediasourceba_32; "CMediaSourceBase::CreatePresentationDes"...
0x18007cfc7  mov     r8d, 532h; int
0x18007cfcd  mov     rcx, rax; this
0x18007cfd0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007cfd5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cfdc  jb      loc_18007D1CE
0x18007cfe2  mov     edx, 7Fh
0x18007cfe7  jmp     loc_18007D1B4
0x18007cfec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cff3  lea     rbx, qword_1801B97E0
0x18007cffa  xor     r15d, r15d
0x18007cffd  test    rcx, rcx
0x18007d000  jnz     short loc_18007D045
0x18007d002  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d009  nop     dword ptr [rax+rax+00h]
0x18007d00e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d015  mov     rcx, rax
0x18007d018  test    rax, rax
0x18007d01b  jz      short loc_18007D03B
0x18007d01d  mov     rax, [rax]
0x18007d020  mov     edx, 7F0h
0x18007d025  mov     rax, [rax+8]
0x18007d029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d02e  test    eax, eax
0x18007d030  jz      short loc_18007D03B
  ... truncated ...
```
