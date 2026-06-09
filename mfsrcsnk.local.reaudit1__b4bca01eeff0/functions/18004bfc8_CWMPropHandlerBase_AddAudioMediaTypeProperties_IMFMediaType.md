# CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)

- ea: `0x18004bfc8`
- end: `0x18004ca5a`
- name: `?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z`
- size: `2706`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b6e0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004bfc8`
- `0x18004cba8`
- `0x180077708`
- `0x180079680`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c1f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c2b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c360`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c5e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c737`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c7e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c8eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c996`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c1f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c2b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c360`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c5e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c68d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c737`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c7e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c8eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c996`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c0fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c33e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c4d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c66b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c7c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c974`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ca1e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c0fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c33e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c4d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c66b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c7c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004c974`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ca1e`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18004c1d6`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18004c1d6`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddAudioMediaTypeProperties(CWMPropHandlerBase *this, struct IMFMediaType *a2)
{
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUINT32)(IMFMediaType *, const GUID *const, UINT32 *); // rax
  HRESULT inited; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  struct IMFMediaTypeVtbl *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct IMFMediaTypeVtbl *v35; // rax
  int v36; // eax
  __int64 (__fastcall *v37)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int); // r10
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  struct IMFMediaTypeVtbl *v54; // rax
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  LONG v64; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v65[4]; // [rsp+34h] [rbp-3Ch] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v67[8]; // [rsp+50h] [rbp-20h] BYREF
  IID clsid; // [rsp+58h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v65,
    "CWMPropHandlerBase::AddAudioMediaTypeProperties",
    1204);
  lpVtbl = a2->lpVtbl;
  v64 = 0;
  memset(&pvar, 0, sizeof(pvar));
  GetUINT32 = lpVtbl->GetUINT32;
  clsid = 0;
  pvar.vt = 19;
  if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))GetUINT32)(a2, &MF_MT_AUDIO_NUM_CHANNELS, &v64) < 0 )
    goto LABEL_22;
  pvar.lVal = v64;
  inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
             this,
             &PKEY_Audio_ChannelCount,
             &pvar,
             0,
             1);
  if ( inited < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::AddAudioMediaTypeProperties",
          1221,
          inited);
    }
    if ( g_wppLevels )
    {
      v9 = 103;
LABEL_10:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, inited);
      goto LABEL_149;
    }
    goto LABEL_149;
  }
  inited = PropVariantClear(&pvar);
  if ( inited >= 0 )
  {
LABEL_22:
    pvar.vt = 72;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, IID *))a2->lpVtbl->GetGUID)(
           a2,
           &MF_MT_SUBTYPE,
           &clsid) >= 0 )
    {
      inited = InitPropVariantFromCLSID(&clsid, &pvar);
      if ( inited < 0 )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != inited )
            CallStackContext::TraceFailure(v17, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1237, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 105;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
      inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                 this,
                 &PKEY_Audio_Format,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != inited )
            CallStackContext::TraceFailure(v21, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1238, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 106;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != inited )
            CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1239, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 107;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
    }
    v26 = a2->lpVtbl;
    pvar.vt = 19;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v26->GetUINT32)(
           a2,
           &MF_MT_AUDIO_SAMPLES_PER_SECOND,
           &v64) >= 0 )
    {
      pvar.lVal = v64;
      inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                 this,
                 &PKEY_Audio_SampleRate,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != inited )
            CallStackContext::TraceFailure(v30, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1249, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 108;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != inited )
            CallStackContext::TraceFailure(v34, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1250, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 109;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
    }
    v35 = a2->lpVtbl;
    pvar.vt = 19;
    v36 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v35->GetUINT32)(
            a2,
            &MF_MT_AUDIO_BITS_PER_SAMPLE,
            &v64);
    v37 = *(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL);
    if ( v36 < 0 )
    {
      pvar.lVal = 16;
      inited = v37(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
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
          if ( *((_DWORD *)v49 + 499) != inited )
            CallStackContext::TraceFailure(v49, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1269, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 112;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)v53 + 499) != inited )
            CallStackContext::TraceFailure(v53, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1270, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 113;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
    }
    else
    {
      pvar.lVal = v64;
      inited = v37(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v41 + 499) != inited )
            CallStackContext::TraceFailure(v41, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1260, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 110;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != inited )
            CallStackContext::TraceFailure(v45, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1261, inited);
        }
        if ( g_wppLevels )
        {
          v9 = 111;
          goto LABEL_10;
        }
        goto LABEL_149;
      }
    }
    if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_EncodingBitrate,
                          v67) )
    {
      v54 = a2->lpVtbl;
      pvar.vt = 19;
      if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v54->GetUINT32)(
             a2,
             &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
             &v64) >= 0 )
      {
        pvar.lVal = 8 * v64;
        inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                   this,
                   &PKEY_Audio_EncodingBitrate,
                   &pvar,
                   0,
                   1);
        if ( inited < 0 )
        {
          v56 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
            CallStackTracing::s_wpInstance = v57;
            if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
            {
              v56 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v56 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v56 + 8) )
          {
            v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
            if ( *((_DWORD *)v58 + 499) != inited )
              CallStackContext::TraceFailure(v58, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1285, inited);
          }
          if ( g_wppLevels )
          {
            v9 = 114;
            goto LABEL_10;
          }
          goto LABEL_149;
        }
        inited = PropVariantClear(&pvar);
        if ( inited < 0 )
        {
          v60 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
            CallStackTracing::s_wpInstance = v61;
            if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
            {
              v60 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
            if ( *((_DWORD *)v62 + 499) != inited )
              CallStackContext::TraceFailure(v62, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1286, inited);
          }
          if ( g_wppLevels )
          {
            v9 = 115;
            goto LABEL_10;
          }
          goto LABEL_149;
        }
      }
    }
    inited = 0;
    goto LABEL_149;
  }
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != inited )
      CallStackContext::TraceFailure(v13, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1222, inited);
  }
  if ( g_wppLevels )
  {
    v9 = 104;
    goto LABEL_10;
  }
LABEL_149:
  PropVariantClear(&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v65);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18004bfc8  mov     [rsp-38h+arg_10], rbx
0x18004bfcd  push    rbp
0x18004bfce  push    rsi
0x18004bfcf  push    rdi
0x18004bfd0  push    r12
0x18004bfd2  push    r13
0x18004bfd4  push    r14
0x18004bfd6  push    r15
0x18004bfd8  mov     rbp, rsp
0x18004bfdb  sub     rsp, 70h
0x18004bfdf  mov     rax, cs:__security_cookie
0x18004bfe6  xor     rax, rsp
0x18004bfe9  mov     [rbp+var_8], rax
0x18004bfed  mov     rsi, rdx
0x18004bff0  lea     r12, aCwmprophandler_9; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x18004bff7  mov     rdi, rcx
0x18004bffa  mov     rdx, r12; char *
0x18004bffd  mov     r8d, 4B4h; int
0x18004c003  lea     rcx, [rbp+var_3C]; this
0x18004c007  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004c00c  xor     eax, eax
0x18004c00e  lea     r8, [rbp+var_40]
0x18004c012  mov     qword ptr [rbp+pvar+10h], rax
0x18004c016  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18004c01d  mov     rax, [rsi]
0x18004c020  xor     r14d, r14d
0x18004c023  xorps   xmm1, xmm1
0x18004c026  mov     [rbp+var_40], r14d
0x18004c02a  xorps   xmm0, xmm0
0x18004c02d  mov     rcx, rsi
0x18004c030  movups  xmmword ptr [rbp+pvar], xmm1
0x18004c034  mov     rax, [rax+38h]
0x18004c038  lea     r13d, [r14+13h]
0x18004c03c  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18004c040  mov     word ptr [rbp+pvar], r13w
0x18004c045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c04a  lea     r15d, [r14+1]
0x18004c04e  test    eax, eax
0x18004c050  js      loc_18004C1A3
0x18004c056  mov     eax, [rbp+var_40]
0x18004c059  lea     r8, [rbp+pvar]
0x18004c05d  mov     dword ptr [rbp+pvar+8], eax
0x18004c060  lea     rdx, PKEY_Audio_ChannelCount
0x18004c067  mov     rax, [rdi]
0x18004c06a  xor     r9d, r9d
0x18004c06d  mov     rcx, rdi
0x18004c070  mov     [rsp+70h+var_50], r15d
0x18004c075  mov     rax, [rax+28h]
0x18004c079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c07e  mov     ebx, eax
0x18004c080  test    eax, eax
0x18004c082  jns     short loc_18004C0F8
0x18004c084  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c08b  test    rcx, rcx
0x18004c08e  jnz     short loc_18004C09C
0x18004c090  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004c095  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004c09c  cmp     [rcx+8], r14b
0x18004c0a0  jz      short loc_18004C0C3
0x18004c0a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c0a7  cmp     [rax+7CCh], ebx
0x18004c0ad  jz      short loc_18004C0C3
0x18004c0af  mov     r9d, ebx; int
0x18004c0b2  mov     r8d, 4C5h; int
0x18004c0b8  mov     rdx, r12; char *
0x18004c0bb  mov     rcx, rax; this
0x18004c0be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c0c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004c0ca  jb      loc_18004CA1A
0x18004c0d0  mov     edx, 67h ; 'g'
0x18004c0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0dc  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18004c0e3  mov     r9, rdi
0x18004c0e6  mov     [rsp+70h+var_50], ebx
0x18004c0ea  mov     rcx, [rcx+10h]
0x18004c0ee  call    WPP_SF_qD
0x18004c0f3  jmp     loc_18004CA1A
0x18004c0f8  lea     rcx, [rbp+pvar]; pvar
0x18004c0fc  call    cs:__imp_PropVariantClear
0x18004c103  nop     dword ptr [rax+rax+00h]
0x18004c108  mov     ebx, eax
0x18004c10a  test    eax, eax
0x18004c10c  jns     loc_18004C1A3
0x18004c112  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c119  test    rcx, rcx
0x18004c11c  jnz     short loc_18004C165
0x18004c11e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c125  nop     dword ptr [rax+rax+00h]
0x18004c12a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c131  mov     rcx, rax
0x18004c134  test    rax, rax
0x18004c137  jz      short loc_18004C157
0x18004c139  mov     rax, [rax]
0x18004c13c  mov     edx, 7F0h
0x18004c141  mov     rax, [rax+8]
0x18004c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c14a  test    eax, eax
0x18004c14c  jz      short loc_18004C157
0x18004c14e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c155  jmp     short loc_18004C165
0x18004c157  lea     rcx, qword_1801B97E0; this
0x18004c15e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c165  cmp     [rcx+8], r14b
0x18004c169  jz      short loc_18004C18C
0x18004c16b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c170  cmp     [rax+7CCh], ebx
0x18004c176  jz      short loc_18004C18C
0x18004c178  mov     r9d, ebx; int
0x18004c17b  mov     r8d, 4C6h; int
0x18004c181  mov     rdx, r12; char *
0x18004c184  mov     rcx, rax; this
0x18004c187  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c18c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004c193  jb      loc_18004CA1A
0x18004c199  mov     edx, 68h ; 'h'
0x18004c19e  jmp     loc_18004C0D5
0x18004c1a3  mov     eax, 48h ; 'H'
0x18004c1a8  lea     r8, [rbp+clsid]
0x18004c1ac  mov     word ptr [rbp+pvar], ax
0x18004c1b0  lea     rdx, MF_MT_SUBTYPE
0x18004c1b7  mov     rax, [rsi]
0x18004c1ba  mov     rcx, rsi
0x18004c1bd  mov     rax, [rax+50h]
0x18004c1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1c6  test    eax, eax
0x18004c1c8  js      loc_18004C3E5
0x18004c1ce  lea     rdx, [rbp+pvar]; ppropvar
0x18004c1d2  lea     rcx, [rbp+clsid]; clsid
0x18004c1d6  call    cs:__imp_InitPropVariantFromCLSID
0x18004c1dd  nop     dword ptr [rax+rax+00h]
0x18004c1e2  mov     ebx, eax
0x18004c1e4  test    eax, eax
0x18004c1e6  jns     loc_18004C27D
0x18004c1ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c1f3  test    rcx, rcx
0x18004c1f6  jnz     short loc_18004C23F
0x18004c1f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c1ff  nop     dword ptr [rax+rax+00h]
0x18004c204  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c20b  mov     rcx, rax
0x18004c20e  test    rax, rax
0x18004c211  jz      short loc_18004C231
0x18004c213  mov     rax, [rax]
0x18004c216  mov     edx, 7F0h
0x18004c21b  mov     rax, [rax+8]
0x18004c21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c224  test    eax, eax
0x18004c226  jz      short loc_18004C231
0x18004c228  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c22f  jmp     short loc_18004C23F
0x18004c231  lea     rcx, qword_1801B97E0; this
0x18004c238  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c23f  cmp     [rcx+8], r14b
0x18004c243  jz      short loc_18004C266
0x18004c245  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c24a  cmp     [rax+7CCh], ebx
0x18004c250  jz      short loc_18004C266
0x18004c252  mov     r9d, ebx; int
0x18004c255  mov     r8d, 4D5h; int
0x18004c25b  mov     rdx, r12; char *
0x18004c25e  mov     rcx, rax; this
0x18004c261  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c266  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004c26d  jb      loc_18004CA1A
0x18004c273  mov     edx, 69h ; 'i'
0x18004c278  jmp     loc_18004C0D5
0x18004c27d  mov     rax, [rdi]
0x18004c280  lea     r8, [rbp+pvar]
0x18004c284  xor     r9d, r9d
0x18004c287  mov     [rsp+70h+var_50], r15d
0x18004c28c  lea     rdx, PKEY_Audio_Format
0x18004c293  mov     rcx, rdi
0x18004c296  mov     rax, [rax+28h]
0x18004c29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c29f  mov     ebx, eax
0x18004c2a1  test    eax, eax
0x18004c2a3  jns     loc_18004C33A
0x18004c2a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2b0  test    rcx, rcx
0x18004c2b3  jnz     short loc_18004C2FC
0x18004c2b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c2bc  nop     dword ptr [rax+rax+00h]
0x18004c2c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2c8  mov     rcx, rax
0x18004c2cb  test    rax, rax
0x18004c2ce  jz      short loc_18004C2EE
0x18004c2d0  mov     rax, [rax]
0x18004c2d3  mov     edx, 7F0h
0x18004c2d8  mov     rax, [rax+8]
0x18004c2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2e1  test    eax, eax
0x18004c2e3  jz      short loc_18004C2EE
0x18004c2e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2ec  jmp     short loc_18004C2FC
0x18004c2ee  lea     rcx, qword_1801B97E0; this
0x18004c2f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c2fc  cmp     [rcx+8], r14b
0x18004c300  jz      short loc_18004C323
0x18004c302  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c307  cmp     [rax+7CCh], ebx
0x18004c30d  jz      short loc_18004C323
0x18004c30f  mov     r9d, ebx; int
0x18004c312  mov     r8d, 4D6h; int
0x18004c318  mov     rdx, r12; char *
0x18004c31b  mov     rcx, rax; this
0x18004c31e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c323  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004c32a  jb      loc_18004CA1A
0x18004c330  mov     edx, 6Ah ; 'j'
0x18004c335  jmp     loc_18004C0D5
0x18004c33a  lea     rcx, [rbp+pvar]; pvar
0x18004c33e  call    cs:__imp_PropVariantClear
0x18004c345  nop     dword ptr [rax+rax+00h]
0x18004c34a  mov     ebx, eax
0x18004c34c  test    eax, eax
0x18004c34e  jns     loc_18004C3E5
0x18004c354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c35b  test    rcx, rcx
0x18004c35e  jnz     short loc_18004C3A7
0x18004c360  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c367  nop     dword ptr [rax+rax+00h]
0x18004c36c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c373  mov     rcx, rax
0x18004c376  test    rax, rax
0x18004c379  jz      short loc_18004C399
0x18004c37b  mov     rax, [rax]
0x18004c37e  mov     edx, 7F0h
0x18004c383  mov     rax, [rax+8]
0x18004c387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c38c  test    eax, eax
0x18004c38e  jz      short loc_18004C399
0x18004c390  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c397  jmp     short loc_18004C3A7
0x18004c399  lea     rcx, qword_1801B97E0; this
0x18004c3a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c3a7  cmp     [rcx+8], r14b
0x18004c3ab  jz      short loc_18004C3CE
0x18004c3ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c3b2  cmp     [rax+7CCh], ebx
0x18004c3b8  jz      short loc_18004C3CE
0x18004c3ba  mov     r9d, ebx; int
0x18004c3bd  mov     r8d, 4D7h; int
0x18004c3c3  mov     rdx, r12; char *
0x18004c3c6  mov     rcx, rax; this
0x18004c3c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c3ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004c3d5  jb      loc_18004CA1A
0x18004c3db  mov     edx, 6Bh ; 'k'
0x18004c3e0  jmp     loc_18004C0D5
0x18004c3e5  mov     rax, [rsi]
0x18004c3e8  lea     r8, [rbp+var_40]
0x18004c3ec  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x18004c3f3  mov     word ptr [rbp+pvar], r13w
0x18004c3f8  mov     rcx, rsi
0x18004c3fb  mov     rax, [rax+38h]
0x18004c3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c404  test    eax, eax
0x18004c406  js      loc_18004C57A
0x18004c40c  mov     eax, [rbp+var_40]
0x18004c40f  lea     r8, [rbp+pvar]
0x18004c413  mov     dword ptr [rbp+pvar+8], eax
0x18004c416  lea     rdx, PKEY_Audio_SampleRate
0x18004c41d  mov     rax, [rdi]
0x18004c420  xor     r9d, r9d
0x18004c423  mov     rcx, rdi
0x18004c426  mov     [rsp+70h+var_50], r15d
0x18004c42b  mov     rax, [rax+28h]
0x18004c42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c434  mov     ebx, eax
0x18004c436  test    eax, eax
0x18004c438  jns     loc_18004C4CF
0x18004c43e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c445  test    rcx, rcx
0x18004c448  jnz     short loc_18004C491
0x18004c44a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c451  nop     dword ptr [rax+rax+00h]
0x18004c456  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c45d  mov     rcx, rax
0x18004c460  test    rax, rax
0x18004c463  jz      short loc_18004C483
0x18004c465  mov     rax, [rax]
0x18004c468  mov     edx, 7F0h
0x18004c46d  mov     rax, [rax+8]
0x18004c471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c476  test    eax, eax
0x18004c478  jz      short loc_18004C483
0x18004c47a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c481  jmp     short loc_18004C491
0x18004c483  lea     rcx, qword_1801B97E0; this
0x18004c48a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c491  cmp     [rcx+8], r14b
0x18004c495  jz      short loc_18004C4B8
0x18004c497  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c49c  cmp     [rax+7CCh], ebx
0x18004c4a2  jz      short loc_18004C4B8
0x18004c4a4  mov     r9d, ebx; int
0x18004c4a7  mov     r8d, 4E1h; int
0x18004c4ad  mov     rdx, r12; char *
0x18004c4b0  mov     rcx, rax; this
0x18004c4b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
