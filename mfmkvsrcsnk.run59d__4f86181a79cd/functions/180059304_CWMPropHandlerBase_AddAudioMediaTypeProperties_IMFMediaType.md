# CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)

- ea: `0x180059304`
- end: `0x180059ddf`
- name: `?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z`
- size: `2779`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005c5f0`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180055474`
- `0x180059304`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005947a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800596bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059851`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800599e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059b3e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059cf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059da0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005947a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800596bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059851`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800599e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059b3e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059cf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180059da0`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180059554`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180059554`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800593d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005949c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059576`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059633`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800596de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800597c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059960`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059a0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059b60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059d18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800593d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005949c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059576`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059633`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800596de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800597c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059960`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059a0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059b60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059d18`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddAudioMediaTypeProperties(CWMPropHandlerBase *this, struct IMFMediaType *a2)
{
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUINT32)(IMFMediaType *, const GUID *const, UINT32 *); // rax
  __int64 v6; // rdx
  HRESULT inited; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct IMFMediaTypeVtbl *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct IMFMediaTypeVtbl *v51; // rax
  int v52; // eax
  __int64 (__fastcall *v53)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int); // r10
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  struct IMFMediaTypeVtbl *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 *v88; // rcx
  CallStackTracing *v89; // rax
  struct CallStackContext *v90; // rax
  LONG v92; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v93[4]; // [rsp+34h] [rbp-4Ch] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v95[8]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v96[16]; // [rsp+58h] [rbp-28h] BYREF
  IID clsid; // [rsp+68h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v93,
    "CWMPropHandlerBase::AddAudioMediaTypeProperties",
    1204);
  lpVtbl = a2->lpVtbl;
  v92 = 0;
  memset(&pvar, 0, sizeof(pvar));
  GetUINT32 = lpVtbl->GetUINT32;
  clsid = 0;
  pvar.vt = 19;
  if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))GetUINT32)(a2, &MF_MT_AUDIO_NUM_CHANNELS, &v92) < 0 )
    goto LABEL_25;
  pvar.lVal = v92;
  inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
             this,
             &PKEY_Audio_ChannelCount,
             &pvar,
             0,
             1);
  if ( inited < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::AddAudioMediaTypeProperties",
          1221,
          inited);
    }
    if ( g_wppLevels )
    {
      v13 = 103;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, inited);
      goto LABEL_152;
    }
    goto LABEL_152;
  }
  inited = PropVariantClear(&pvar);
  if ( inited >= 0 )
  {
LABEL_25:
    pvar.vt = 72;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, IID *))a2->lpVtbl->GetGUID)(
           a2,
           &MF_MT_SUBTYPE,
           &clsid) >= 0 )
    {
      inited = InitPropVariantFromCLSID(&clsid, &pvar);
      if ( inited < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != inited )
            CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1237, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 105;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                 this,
                 &PKEY_Audio_Format,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)v31 + 499) != inited )
            CallStackContext::TraceFailure(v31, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1238, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 106;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != inited )
            CallStackContext::TraceFailure(v37, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1239, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 107;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v38 = a2->lpVtbl;
    pvar.vt = 19;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v38->GetUINT32)(
           a2,
           &MF_MT_AUDIO_SAMPLES_PER_SECOND,
           &v92) >= 0 )
    {
      pvar.lVal = v92;
      inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                 this,
                 &PKEY_Audio_SampleRate,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != inited )
            CallStackContext::TraceFailure(v44, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1249, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 108;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
          if ( *((_DWORD *)v50 + 499) != inited )
            CallStackContext::TraceFailure(v50, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1250, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 109;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v51 = a2->lpVtbl;
    pvar.vt = 19;
    v52 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v51->GetUINT32)(
            a2,
            &MF_MT_AUDIO_BITS_PER_SAMPLE,
            &v92);
    v53 = *(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL);
    if ( v52 < 0 )
    {
      pvar.lVal = 16;
      inited = v53(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != inited )
            CallStackContext::TraceFailure(v71, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1269, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 112;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v75 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
          CallStackTracing::s_wpInstance = v76;
          if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
          {
            v75 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v75 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v75 + 8) )
        {
          v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
          if ( *((_DWORD *)v77 + 499) != inited )
            CallStackContext::TraceFailure(v77, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1270, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 113;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    else
    {
      pvar.lVal = v92;
      inited = v53(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
          CallStackTracing::s_wpInstance = v58;
          if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
          {
            v57 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v57 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v57 + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
          if ( *((_DWORD *)v59 + 499) != inited )
            CallStackContext::TraceFailure(v59, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1260, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 110;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != inited )
            CallStackContext::TraceFailure(v65, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1261, inited);
        }
        if ( g_wppLevels )
        {
          v13 = 111;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_EncodingBitrate,
                          v95,
                          v96) )
    {
      v78 = a2->lpVtbl;
      pvar.vt = 19;
      if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v78->GetUINT32)(
             a2,
             &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
             &v92) >= 0 )
      {
        pvar.lVal = 8 * v92;
        inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                   this,
                   &PKEY_Audio_EncodingBitrate,
                   &pvar,
                   0,
                   1);
        if ( inited < 0 )
        {
          v82 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79, v80, v81);
            CallStackTracing::s_wpInstance = v83;
            if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
            {
              v82 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v82 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v82 + 8) )
          {
            v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
            if ( *((_DWORD *)v84 + 499) != inited )
              CallStackContext::TraceFailure(v84, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1285, inited);
          }
          if ( g_wppLevels )
          {
            v13 = 114;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
        inited = PropVariantClear(&pvar);
        if ( inited < 0 )
        {
          v88 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v89 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v85, v86, v87);
            CallStackTracing::s_wpInstance = v89;
            if ( v89 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v89 + 8LL))(v89, 2032) )
            {
              v88 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v88 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v88 + 8) )
          {
            v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v88);
            if ( *((_DWORD *)v90 + 499) != inited )
              CallStackContext::TraceFailure(v90, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1286, inited);
          }
          if ( g_wppLevels )
          {
            v13 = 115;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
      }
    }
    inited = 0;
    goto LABEL_152;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != inited )
      CallStackContext::TraceFailure(v19, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1222, inited);
  }
  if ( g_wppLevels )
  {
    v13 = 104;
    goto LABEL_13;
  }
LABEL_152:
  PropVariantClear(&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v93);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180059304  mov     [rsp-38h+arg_10], rbx
0x180059309  push    rbp
0x18005930a  push    rsi
0x18005930b  push    rdi
0x18005930c  push    r12
0x18005930e  push    r13
0x180059310  push    r14
0x180059312  push    r15
0x180059314  mov     rbp, rsp
0x180059317  sub     rsp, 80h
0x18005931e  mov     rax, cs:__security_cookie
0x180059325  xor     rax, rsp
0x180059328  mov     [rbp+var_8], rax
0x18005932c  mov     rsi, rdx
0x18005932f  lea     r12, aCwmprophandler_9; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x180059336  mov     rdi, rcx
0x180059339  mov     rdx, r12; char *
0x18005933c  mov     r8d, 4B4h; int
0x180059342  lea     rcx, [rbp+var_4C]; this
0x180059346  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005934b  xor     eax, eax
0x18005934d  lea     r8, [rbp+var_50]
0x180059351  mov     qword ptr [rbp+pvar+10h], rax
0x180059355  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18005935c  mov     rax, [rsi]
0x18005935f  xor     r14d, r14d
0x180059362  xorps   xmm1, xmm1
0x180059365  mov     [rbp+var_50], r14d
0x180059369  xorps   xmm0, xmm0
0x18005936c  mov     rcx, rsi
0x18005936f  movups  xmmword ptr [rbp+pvar], xmm1
0x180059373  mov     rax, [rax+38h]
0x180059377  lea     r13d, [r14+13h]
0x18005937b  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18005937f  mov     word ptr [rbp+pvar], r13w
0x180059384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059389  lea     r15d, [r14+1]
0x18005938d  test    eax, eax
0x18005938f  js      loc_180059521
0x180059395  mov     eax, [rbp+var_50]
0x180059398  lea     r8, [rbp+pvar]
0x18005939c  mov     dword ptr [rbp+pvar+8], eax
0x18005939f  lea     rdx, PKEY_Audio_ChannelCount
0x1800593a6  mov     rax, [rdi]
0x1800593a9  xor     r9d, r9d
0x1800593ac  mov     rcx, rdi
0x1800593af  mov     [rsp+80h+var_60], r15d
0x1800593b4  mov     rax, [rax+28h]
0x1800593b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593bd  mov     ebx, eax
0x1800593bf  test    eax, eax
0x1800593c1  jns     loc_180059476
0x1800593c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800593ce  test    rcx, rcx
0x1800593d1  jnz     short loc_18005941A
0x1800593d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800593da  nop     dword ptr [rax+rax+00h]
0x1800593df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800593e6  mov     rcx, rax
0x1800593e9  test    rax, rax
0x1800593ec  jz      short loc_18005940C
0x1800593ee  mov     rax, [rax]
0x1800593f1  mov     edx, 7F0h
0x1800593f6  mov     rax, [rax+8]
0x1800593fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593ff  test    eax, eax
0x180059401  jz      short loc_18005940C
0x180059403  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005940a  jmp     short loc_18005941A
0x18005940c  lea     rcx, qword_1800DBF70; this
0x180059413  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005941a  cmp     [rcx+8], r14b
0x18005941e  jz      short loc_180059441
0x180059420  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059425  cmp     [rax+7CCh], ebx
0x18005942b  jz      short loc_180059441
0x18005942d  mov     r9d, ebx; int
0x180059430  mov     r8d, 4C5h; int
0x180059436  mov     rdx, r12; char *
0x180059439  mov     rcx, rax; this
0x18005943c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059441  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180059448  jb      loc_180059D9C
0x18005944e  mov     edx, 67h ; 'g'
0x180059453  mov     rcx, cs:WPP_GLOBAL_Control
0x18005945a  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180059461  mov     r9, rdi
0x180059464  mov     [rsp+80h+var_60], ebx
0x180059468  mov     rcx, [rcx+10h]
0x18005946c  call    WPP_SF_qD
0x180059471  jmp     loc_180059D9C
0x180059476  lea     rcx, [rbp+pvar]; pvar
0x18005947a  call    cs:__imp_PropVariantClear
0x180059481  nop     dword ptr [rax+rax+00h]
0x180059486  mov     ebx, eax
0x180059488  test    eax, eax
0x18005948a  jns     loc_180059521
0x180059490  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059497  test    rcx, rcx
0x18005949a  jnz     short loc_1800594E3
0x18005949c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800594a3  nop     dword ptr [rax+rax+00h]
0x1800594a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800594af  mov     rcx, rax
0x1800594b2  test    rax, rax
0x1800594b5  jz      short loc_1800594D5
0x1800594b7  mov     rax, [rax]
0x1800594ba  mov     edx, 7F0h
0x1800594bf  mov     rax, [rax+8]
0x1800594c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594c8  test    eax, eax
0x1800594ca  jz      short loc_1800594D5
0x1800594cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800594d3  jmp     short loc_1800594E3
0x1800594d5  lea     rcx, qword_1800DBF70; this
0x1800594dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800594e3  cmp     [rcx+8], r14b
0x1800594e7  jz      short loc_18005950A
0x1800594e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800594ee  cmp     [rax+7CCh], ebx
0x1800594f4  jz      short loc_18005950A
0x1800594f6  mov     r9d, ebx; int
0x1800594f9  mov     r8d, 4C6h; int
0x1800594ff  mov     rdx, r12; char *
0x180059502  mov     rcx, rax; this
0x180059505  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005950a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180059511  jb      loc_180059D9C
0x180059517  mov     edx, 68h ; 'h'
0x18005951c  jmp     loc_180059453
0x180059521  mov     eax, 48h ; 'H'
0x180059526  lea     r8, [rbp+clsid]
0x18005952a  mov     word ptr [rbp+pvar], ax
0x18005952e  lea     rdx, MF_MT_SUBTYPE
0x180059535  mov     rax, [rsi]
0x180059538  mov     rcx, rsi
0x18005953b  mov     rax, [rax+50h]
0x18005953f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059544  test    eax, eax
0x180059546  js      loc_180059763
0x18005954c  lea     rdx, [rbp+pvar]; ppropvar
0x180059550  lea     rcx, [rbp+clsid]; clsid
0x180059554  call    cs:__imp_InitPropVariantFromCLSID
0x18005955b  nop     dword ptr [rax+rax+00h]
0x180059560  mov     ebx, eax
0x180059562  test    eax, eax
0x180059564  jns     loc_1800595FB
0x18005956a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059571  test    rcx, rcx
0x180059574  jnz     short loc_1800595BD
0x180059576  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005957d  nop     dword ptr [rax+rax+00h]
0x180059582  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059589  mov     rcx, rax
0x18005958c  test    rax, rax
0x18005958f  jz      short loc_1800595AF
0x180059591  mov     rax, [rax]
0x180059594  mov     edx, 7F0h
0x180059599  mov     rax, [rax+8]
0x18005959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595a2  test    eax, eax
0x1800595a4  jz      short loc_1800595AF
0x1800595a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800595ad  jmp     short loc_1800595BD
0x1800595af  lea     rcx, qword_1800DBF70; this
0x1800595b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800595bd  cmp     [rcx+8], r14b
0x1800595c1  jz      short loc_1800595E4
0x1800595c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800595c8  cmp     [rax+7CCh], ebx
0x1800595ce  jz      short loc_1800595E4
0x1800595d0  mov     r9d, ebx; int
0x1800595d3  mov     r8d, 4D5h; int
0x1800595d9  mov     rdx, r12; char *
0x1800595dc  mov     rcx, rax; this
0x1800595df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800595e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800595eb  jb      loc_180059D9C
0x1800595f1  mov     edx, 69h ; 'i'
0x1800595f6  jmp     loc_180059453
0x1800595fb  mov     rax, [rdi]
0x1800595fe  lea     r8, [rbp+pvar]
0x180059602  xor     r9d, r9d
0x180059605  mov     [rsp+80h+var_60], r15d
0x18005960a  lea     rdx, PKEY_Audio_Format
0x180059611  mov     rcx, rdi
0x180059614  mov     rax, [rax+28h]
0x180059618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005961d  mov     ebx, eax
0x18005961f  test    eax, eax
0x180059621  jns     loc_1800596B8
0x180059627  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005962e  test    rcx, rcx
0x180059631  jnz     short loc_18005967A
0x180059633  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005963a  nop     dword ptr [rax+rax+00h]
0x18005963f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059646  mov     rcx, rax
0x180059649  test    rax, rax
0x18005964c  jz      short loc_18005966C
0x18005964e  mov     rax, [rax]
0x180059651  mov     edx, 7F0h
0x180059656  mov     rax, [rax+8]
0x18005965a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005965f  test    eax, eax
0x180059661  jz      short loc_18005966C
0x180059663  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005966a  jmp     short loc_18005967A
0x18005966c  lea     rcx, qword_1800DBF70; this
0x180059673  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005967a  cmp     [rcx+8], r14b
0x18005967e  jz      short loc_1800596A1
0x180059680  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059685  cmp     [rax+7CCh], ebx
0x18005968b  jz      short loc_1800596A1
0x18005968d  mov     r9d, ebx; int
0x180059690  mov     r8d, 4D6h; int
0x180059696  mov     rdx, r12; char *
0x180059699  mov     rcx, rax; this
0x18005969c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800596a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800596a8  jb      loc_180059D9C
0x1800596ae  mov     edx, 6Ah ; 'j'
0x1800596b3  jmp     loc_180059453
0x1800596b8  lea     rcx, [rbp+pvar]; pvar
0x1800596bc  call    cs:__imp_PropVariantClear
0x1800596c3  nop     dword ptr [rax+rax+00h]
0x1800596c8  mov     ebx, eax
0x1800596ca  test    eax, eax
0x1800596cc  jns     loc_180059763
0x1800596d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800596d9  test    rcx, rcx
0x1800596dc  jnz     short loc_180059725
0x1800596de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800596e5  nop     dword ptr [rax+rax+00h]
0x1800596ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800596f1  mov     rcx, rax
0x1800596f4  test    rax, rax
0x1800596f7  jz      short loc_180059717
0x1800596f9  mov     rax, [rax]
0x1800596fc  mov     edx, 7F0h
0x180059701  mov     rax, [rax+8]
0x180059705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005970a  test    eax, eax
0x18005970c  jz      short loc_180059717
0x18005970e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059715  jmp     short loc_180059725
0x180059717  lea     rcx, qword_1800DBF70; this
0x18005971e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180059725  cmp     [rcx+8], r14b
0x180059729  jz      short loc_18005974C
0x18005972b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059730  cmp     [rax+7CCh], ebx
0x180059736  jz      short loc_18005974C
0x180059738  mov     r9d, ebx; int
0x18005973b  mov     r8d, 4D7h; int
0x180059741  mov     rdx, r12; char *
0x180059744  mov     rcx, rax; this
0x180059747  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005974c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180059753  jb      loc_180059D9C
0x180059759  mov     edx, 6Bh ; 'k'
0x18005975e  jmp     loc_180059453
0x180059763  mov     rax, [rsi]
0x180059766  lea     r8, [rbp+var_50]
0x18005976a  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180059771  mov     word ptr [rbp+pvar], r13w
0x180059776  mov     rcx, rsi
0x180059779  mov     rax, [rax+38h]
0x18005977d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059782  test    eax, eax
0x180059784  js      loc_1800598F8
0x18005978a  mov     eax, [rbp+var_50]
0x18005978d  lea     r8, [rbp+pvar]
0x180059791  mov     dword ptr [rbp+pvar+8], eax
0x180059794  lea     rdx, PKEY_Audio_SampleRate
0x18005979b  mov     rax, [rdi]
0x18005979e  xor     r9d, r9d
0x1800597a1  mov     rcx, rdi
0x1800597a4  mov     [rsp+80h+var_60], r15d
0x1800597a9  mov     rax, [rax+28h]
0x1800597ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597b2  mov     ebx, eax
0x1800597b4  test    eax, eax
0x1800597b6  jns     loc_18005984D
0x1800597bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800597c3  test    rcx, rcx
0x1800597c6  jnz     short loc_18005980F
0x1800597c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800597cf  nop     dword ptr [rax+rax+00h]
0x1800597d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800597db  mov     rcx, rax
0x1800597de  test    rax, rax
0x1800597e1  jz      short loc_180059801
0x1800597e3  mov     rax, [rax]
0x1800597e6  mov     edx, 7F0h
0x1800597eb  mov     rax, [rax+8]
0x1800597ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597f4  test    eax, eax
0x1800597f6  jz      short loc_180059801
  ... truncated ...
```
