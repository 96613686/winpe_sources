# CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)

- ea: `0x180056e58`
- end: `0x1800578b4`
- name: `?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z`
- size: `2652`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180059fa0`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800530e4`
- `0x180056e58`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056fc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800571ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005736f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800574f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180057638`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800577de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005787c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056fc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800571ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005736f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800574f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180057638`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800577de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005787c`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180057096`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180057096`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056fe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800570b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057208`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800572ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005738b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057472`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800575b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057654`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005775b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800577fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056fe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800570b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057208`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800572ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005738b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057472`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800575b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057654`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005775b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800577fa`

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
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v29 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v35 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v42 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v48 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v69 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v75 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v57 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v63 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v82 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v88 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v17 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180056e58  mov     [rsp-38h+arg_10], rbx
0x180056e5d  push    rbp
0x180056e5e  push    rsi
0x180056e5f  push    rdi
0x180056e60  push    r12
0x180056e62  push    r13
0x180056e64  push    r14
0x180056e66  push    r15
0x180056e68  mov     rbp, rsp
0x180056e6b  sub     rsp, 80h
0x180056e72  mov     rax, cs:__security_cookie
0x180056e79  xor     rax, rsp
0x180056e7c  mov     [rbp+var_8], rax
0x180056e80  mov     rsi, rdx
0x180056e83  lea     r12, aCwmprophandler_9; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x180056e8a  mov     rdi, rcx
0x180056e8d  mov     rdx, r12; char *
0x180056e90  mov     r8d, 4B4h; int
0x180056e96  lea     rcx, [rbp+var_4C]; this
0x180056e9a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180056e9f  xor     eax, eax
0x180056ea1  lea     r8, [rbp+var_50]
0x180056ea5  mov     qword ptr [rbp+pvar+10h], rax
0x180056ea9  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x180056eb0  mov     rax, [rsi]
0x180056eb3  xor     r14d, r14d
0x180056eb6  xorps   xmm1, xmm1
0x180056eb9  mov     [rbp+var_50], r14d
0x180056ebd  xorps   xmm0, xmm0
0x180056ec0  mov     rcx, rsi
0x180056ec3  movups  xmmword ptr [rbp+pvar], xmm1
0x180056ec7  mov     rax, [rax+38h]
0x180056ecb  lea     r13d, [r14+13h]
0x180056ecf  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180056ed3  mov     word ptr [rbp+pvar], r13w
0x180056ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056edd  lea     r15d, [r14+1]
0x180056ee1  test    eax, eax
0x180056ee3  js      loc_180057063
0x180056ee9  mov     eax, [rbp+var_50]
0x180056eec  lea     r8, [rbp+pvar]
0x180056ef0  mov     dword ptr [rbp+pvar+8], eax
0x180056ef3  lea     rdx, PKEY_Audio_ChannelCount
0x180056efa  mov     rax, [rdi]
0x180056efd  xor     r9d, r9d
0x180056f00  mov     rcx, rdi
0x180056f03  mov     [rsp+80h+var_60], r15d
0x180056f08  mov     rax, [rax+28h]
0x180056f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f11  mov     ebx, eax
0x180056f13  test    eax, eax
0x180056f15  jns     loc_180056FC4
0x180056f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f22  test    rcx, rcx
0x180056f25  jnz     short loc_180056F68
0x180056f27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180056f2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f34  mov     rcx, rax
0x180056f37  test    rax, rax
0x180056f3a  jz      short loc_180056F5A
0x180056f3c  mov     rax, [rax]
0x180056f3f  mov     edx, 7F0h
0x180056f44  mov     rax, [rax+8]
0x180056f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f4d  test    eax, eax
0x180056f4f  jz      short loc_180056F5A
0x180056f51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f58  jmp     short loc_180056F68
0x180056f5a  lea     rcx, qword_1800D6F70; this
0x180056f61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f68  cmp     [rcx+8], r14b
0x180056f6c  jz      short loc_180056F8F
0x180056f6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180056f73  cmp     [rax+7CCh], ebx
0x180056f79  jz      short loc_180056F8F
0x180056f7b  mov     r9d, ebx; int
0x180056f7e  mov     r8d, 4C5h; int
0x180056f84  mov     rdx, r12; char *
0x180056f87  mov     rcx, rax; this
0x180056f8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180056f8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180056f96  jb      loc_180057878
0x180056f9c  mov     edx, 67h ; 'g'
0x180056fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fa8  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180056faf  mov     r9, rdi
0x180056fb2  mov     [rsp+80h+var_60], ebx
0x180056fb6  mov     rcx, [rcx+10h]
0x180056fba  call    WPP_SF_qD
0x180056fbf  jmp     loc_180057878
0x180056fc4  lea     rcx, [rbp+pvar]; pvar
0x180056fc8  call    cs:__imp_PropVariantClear
0x180056fce  mov     ebx, eax
0x180056fd0  test    eax, eax
0x180056fd2  jns     loc_180057063
0x180056fd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056fdf  test    rcx, rcx
0x180056fe2  jnz     short loc_180057025
0x180056fe4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180056fea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180056ff1  mov     rcx, rax
0x180056ff4  test    rax, rax
0x180056ff7  jz      short loc_180057017
0x180056ff9  mov     rax, [rax]
0x180056ffc  mov     edx, 7F0h
0x180057001  mov     rax, [rax+8]
0x180057005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005700a  test    eax, eax
0x18005700c  jz      short loc_180057017
0x18005700e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057015  jmp     short loc_180057025
0x180057017  lea     rcx, qword_1800D6F70; this
0x18005701e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057025  cmp     [rcx+8], r14b
0x180057029  jz      short loc_18005704C
0x18005702b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057030  cmp     [rax+7CCh], ebx
0x180057036  jz      short loc_18005704C
0x180057038  mov     r9d, ebx; int
0x18005703b  mov     r8d, 4C6h; int
0x180057041  mov     rdx, r12; char *
0x180057044  mov     rcx, rax; this
0x180057047  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005704c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180057053  jb      loc_180057878
0x180057059  mov     edx, 68h ; 'h'
0x18005705e  jmp     loc_180056FA1
0x180057063  mov     eax, 48h ; 'H'
0x180057068  lea     r8, [rbp+clsid]
0x18005706c  mov     word ptr [rbp+pvar], ax
0x180057070  lea     rdx, MF_MT_SUBTYPE
0x180057077  mov     rax, [rsi]
0x18005707a  mov     rcx, rsi
0x18005707d  mov     rax, [rax+50h]
0x180057081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057086  test    eax, eax
0x180057088  js      loc_180057287
0x18005708e  lea     rdx, [rbp+pvar]; ppropvar
0x180057092  lea     rcx, [rbp+clsid]; clsid
0x180057096  call    cs:__imp_InitPropVariantFromCLSID
0x18005709c  mov     ebx, eax
0x18005709e  test    eax, eax
0x1800570a0  jns     loc_180057131
0x1800570a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800570ad  test    rcx, rcx
0x1800570b0  jnz     short loc_1800570F3
0x1800570b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800570b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800570bf  mov     rcx, rax
0x1800570c2  test    rax, rax
0x1800570c5  jz      short loc_1800570E5
0x1800570c7  mov     rax, [rax]
0x1800570ca  mov     edx, 7F0h
0x1800570cf  mov     rax, [rax+8]
0x1800570d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570d8  test    eax, eax
0x1800570da  jz      short loc_1800570E5
0x1800570dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800570e3  jmp     short loc_1800570F3
0x1800570e5  lea     rcx, qword_1800D6F70; this
0x1800570ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800570f3  cmp     [rcx+8], r14b
0x1800570f7  jz      short loc_18005711A
0x1800570f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800570fe  cmp     [rax+7CCh], ebx
0x180057104  jz      short loc_18005711A
0x180057106  mov     r9d, ebx; int
0x180057109  mov     r8d, 4D5h; int
0x18005710f  mov     rdx, r12; char *
0x180057112  mov     rcx, rax; this
0x180057115  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005711a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180057121  jb      loc_180057878
0x180057127  mov     edx, 69h ; 'i'
0x18005712c  jmp     loc_180056FA1
0x180057131  mov     rax, [rdi]
0x180057134  lea     r8, [rbp+pvar]
0x180057138  xor     r9d, r9d
0x18005713b  mov     [rsp+80h+var_60], r15d
0x180057140  lea     rdx, PKEY_Audio_Format
0x180057147  mov     rcx, rdi
0x18005714a  mov     rax, [rax+28h]
0x18005714e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057153  mov     ebx, eax
0x180057155  test    eax, eax
0x180057157  jns     loc_1800571E8
0x18005715d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057164  test    rcx, rcx
0x180057167  jnz     short loc_1800571AA
0x180057169  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005716f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057176  mov     rcx, rax
0x180057179  test    rax, rax
0x18005717c  jz      short loc_18005719C
0x18005717e  mov     rax, [rax]
0x180057181  mov     edx, 7F0h
0x180057186  mov     rax, [rax+8]
0x18005718a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005718f  test    eax, eax
0x180057191  jz      short loc_18005719C
0x180057193  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005719a  jmp     short loc_1800571AA
0x18005719c  lea     rcx, qword_1800D6F70; this
0x1800571a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800571aa  cmp     [rcx+8], r14b
0x1800571ae  jz      short loc_1800571D1
0x1800571b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800571b5  cmp     [rax+7CCh], ebx
0x1800571bb  jz      short loc_1800571D1
0x1800571bd  mov     r9d, ebx; int
0x1800571c0  mov     r8d, 4D6h; int
0x1800571c6  mov     rdx, r12; char *
0x1800571c9  mov     rcx, rax; this
0x1800571cc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800571d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800571d8  jb      loc_180057878
0x1800571de  mov     edx, 6Ah ; 'j'
0x1800571e3  jmp     loc_180056FA1
0x1800571e8  lea     rcx, [rbp+pvar]; pvar
0x1800571ec  call    cs:__imp_PropVariantClear
0x1800571f2  mov     ebx, eax
0x1800571f4  test    eax, eax
0x1800571f6  jns     loc_180057287
0x1800571fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057203  test    rcx, rcx
0x180057206  jnz     short loc_180057249
0x180057208  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005720e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057215  mov     rcx, rax
0x180057218  test    rax, rax
0x18005721b  jz      short loc_18005723B
0x18005721d  mov     rax, [rax]
0x180057220  mov     edx, 7F0h
0x180057225  mov     rax, [rax+8]
0x180057229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005722e  test    eax, eax
0x180057230  jz      short loc_18005723B
0x180057232  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057239  jmp     short loc_180057249
0x18005723b  lea     rcx, qword_1800D6F70; this
0x180057242  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057249  cmp     [rcx+8], r14b
0x18005724d  jz      short loc_180057270
0x18005724f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057254  cmp     [rax+7CCh], ebx
0x18005725a  jz      short loc_180057270
0x18005725c  mov     r9d, ebx; int
0x18005725f  mov     r8d, 4D7h; int
0x180057265  mov     rdx, r12; char *
0x180057268  mov     rcx, rax; this
0x18005726b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057270  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180057277  jb      loc_180057878
0x18005727d  mov     edx, 6Bh ; 'k'
0x180057282  jmp     loc_180056FA1
0x180057287  mov     rax, [rsi]
0x18005728a  lea     r8, [rbp+var_50]
0x18005728e  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180057295  mov     word ptr [rbp+pvar], r13w
0x18005729a  mov     rcx, rsi
0x18005729d  mov     rax, [rax+38h]
0x1800572a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572a6  test    eax, eax
0x1800572a8  js      loc_18005740A
0x1800572ae  mov     eax, [rbp+var_50]
0x1800572b1  lea     r8, [rbp+pvar]
0x1800572b5  mov     dword ptr [rbp+pvar+8], eax
0x1800572b8  lea     rdx, PKEY_Audio_SampleRate
0x1800572bf  mov     rax, [rdi]
0x1800572c2  xor     r9d, r9d
0x1800572c5  mov     rcx, rdi
0x1800572c8  mov     [rsp+80h+var_60], r15d
0x1800572cd  mov     rax, [rax+28h]
0x1800572d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572d6  mov     ebx, eax
0x1800572d8  test    eax, eax
0x1800572da  jns     loc_18005736B
0x1800572e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800572e7  test    rcx, rcx
0x1800572ea  jnz     short loc_18005732D
0x1800572ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800572f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800572f9  mov     rcx, rax
0x1800572fc  test    rax, rax
0x1800572ff  jz      short loc_18005731F
0x180057301  mov     rax, [rax]
0x180057304  mov     edx, 7F0h
0x180057309  mov     rax, [rax+8]
0x18005730d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057312  test    eax, eax
0x180057314  jz      short loc_18005731F
0x180057316  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005731d  jmp     short loc_18005732D
0x18005731f  lea     rcx, qword_1800D6F70; this
0x180057326  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005732d  cmp     [rcx+8], r14b
0x180057331  jz      short loc_180057354
0x180057333  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057338  cmp     [rax+7CCh], ebx
0x18005733e  jz      short loc_180057354
  ... truncated ...
```
