# CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)

- ea: `0x18004887c`
- end: `0x180049295`
- name: `?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z`
- size: `2585`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180047fa0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18004887c`
- `0x1800493dc`
- `0x180071a44`
- `0x180073b14`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800489cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048cd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048d73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048e5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048ef9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048f9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004903c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004913f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800491de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800489cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048bf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048cd4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048d73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048e5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048ef9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048f9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004903c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004913f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800491de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800489b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048bd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048d57`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048edd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049020`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800491c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049260`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800489b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048bd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048d57`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048edd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049020`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800491c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049260`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180048a7e`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180048a7e`

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
            v15 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v19 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v23 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v28 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v32 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v47 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v51 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v39 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v43 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v56 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v60 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v11 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x18004887c  mov     [rsp-38h+arg_10], rbx
0x180048881  push    rbp
0x180048882  push    rsi
0x180048883  push    rdi
0x180048884  push    r12
0x180048886  push    r13
0x180048888  push    r14
0x18004888a  push    r15
0x18004888c  mov     rbp, rsp
0x18004888f  sub     rsp, 70h
0x180048893  mov     rax, cs:__security_cookie
0x18004889a  xor     rax, rsp
0x18004889d  mov     [rbp+var_8], rax
0x1800488a1  mov     rsi, rdx
0x1800488a4  lea     r12, aCwmprophandler_9; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x1800488ab  mov     rdi, rcx
0x1800488ae  mov     rdx, r12; char *
0x1800488b1  mov     r8d, 4B4h; int
0x1800488b7  lea     rcx, [rbp+var_3C]; this
0x1800488bb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800488c0  xor     eax, eax
0x1800488c2  lea     r8, [rbp+var_40]
0x1800488c6  mov     qword ptr [rbp+pvar+10h], rax
0x1800488ca  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x1800488d1  mov     rax, [rsi]
0x1800488d4  xor     r14d, r14d
0x1800488d7  xorps   xmm1, xmm1
0x1800488da  mov     [rbp+var_40], r14d
0x1800488de  xorps   xmm0, xmm0
0x1800488e1  mov     rcx, rsi
0x1800488e4  movups  xmmword ptr [rbp+pvar], xmm1
0x1800488e8  mov     rax, [rax+38h]
0x1800488ec  lea     r13d, [r14+13h]
0x1800488f0  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800488f4  mov     word ptr [rbp+pvar], r13w
0x1800488f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488fe  lea     r15d, [r14+1]
0x180048902  test    eax, eax
0x180048904  js      loc_180048A4B
0x18004890a  mov     eax, [rbp+var_40]
0x18004890d  lea     r8, [rbp+pvar]
0x180048911  mov     dword ptr [rbp+pvar+8], eax
0x180048914  lea     rdx, PKEY_Audio_ChannelCount
0x18004891b  mov     rax, [rdi]
0x18004891e  xor     r9d, r9d
0x180048921  mov     rcx, rdi
0x180048924  mov     [rsp+70h+var_50], r15d
0x180048929  mov     rax, [rax+28h]
0x18004892d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048932  mov     ebx, eax
0x180048934  test    eax, eax
0x180048936  jns     short loc_1800489AC
0x180048938  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004893f  test    rcx, rcx
0x180048942  jnz     short loc_180048950
0x180048944  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180048949  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180048950  cmp     [rcx+8], r14b
0x180048954  jz      short loc_180048977
0x180048956  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004895b  cmp     [rax+7CCh], ebx
0x180048961  jz      short loc_180048977
0x180048963  mov     r9d, ebx; int
0x180048966  mov     r8d, 4C5h; int
0x18004896c  mov     rdx, r12; char *
0x18004896f  mov     rcx, rax; this
0x180048972  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048977  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004897e  jb      loc_18004925C
0x180048984  mov     edx, 67h ; 'g'
0x180048989  mov     rcx, cs:WPP_GLOBAL_Control
0x180048990  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180048997  mov     r9, rdi
0x18004899a  mov     [rsp+70h+var_50], ebx
0x18004899e  mov     rcx, [rcx+10h]
0x1800489a2  call    WPP_SF_qD
0x1800489a7  jmp     loc_18004925C
0x1800489ac  lea     rcx, [rbp+pvar]; pvar
0x1800489b0  call    cs:__imp_PropVariantClear
0x1800489b6  mov     ebx, eax
0x1800489b8  test    eax, eax
0x1800489ba  jns     loc_180048A4B
0x1800489c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800489c7  test    rcx, rcx
0x1800489ca  jnz     short loc_180048A0D
0x1800489cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800489d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800489d9  mov     rcx, rax
0x1800489dc  test    rax, rax
0x1800489df  jz      short loc_1800489FF
0x1800489e1  mov     rax, [rax]
0x1800489e4  mov     edx, 7F0h
0x1800489e9  mov     rax, [rax+8]
0x1800489ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489f2  test    eax, eax
0x1800489f4  jz      short loc_1800489FF
0x1800489f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800489fd  jmp     short loc_180048A0D
0x1800489ff  lea     rcx, qword_1801B07E0; this
0x180048a06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048a0d  cmp     [rcx+8], r14b
0x180048a11  jz      short loc_180048A34
0x180048a13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048a18  cmp     [rax+7CCh], ebx
0x180048a1e  jz      short loc_180048A34
0x180048a20  mov     r9d, ebx; int
0x180048a23  mov     r8d, 4C6h; int
0x180048a29  mov     rdx, r12; char *
0x180048a2c  mov     rcx, rax; this
0x180048a2f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048a34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180048a3b  jb      loc_18004925C
0x180048a41  mov     edx, 68h ; 'h'
0x180048a46  jmp     loc_180048989
0x180048a4b  mov     eax, 48h ; 'H'
0x180048a50  lea     r8, [rbp+clsid]
0x180048a54  mov     word ptr [rbp+pvar], ax
0x180048a58  lea     rdx, MF_MT_SUBTYPE
0x180048a5f  mov     rax, [rsi]
0x180048a62  mov     rcx, rsi
0x180048a65  mov     rax, [rax+50h]
0x180048a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a6e  test    eax, eax
0x180048a70  js      loc_180048C6F
0x180048a76  lea     rdx, [rbp+pvar]; ppropvar
0x180048a7a  lea     rcx, [rbp+clsid]; clsid
0x180048a7e  call    cs:__imp_InitPropVariantFromCLSID
0x180048a84  mov     ebx, eax
0x180048a86  test    eax, eax
0x180048a88  jns     loc_180048B19
0x180048a8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048a95  test    rcx, rcx
0x180048a98  jnz     short loc_180048ADB
0x180048a9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048aa0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048aa7  mov     rcx, rax
0x180048aaa  test    rax, rax
0x180048aad  jz      short loc_180048ACD
0x180048aaf  mov     rax, [rax]
0x180048ab2  mov     edx, 7F0h
0x180048ab7  mov     rax, [rax+8]
0x180048abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ac0  test    eax, eax
0x180048ac2  jz      short loc_180048ACD
0x180048ac4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048acb  jmp     short loc_180048ADB
0x180048acd  lea     rcx, qword_1801B07E0; this
0x180048ad4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048adb  cmp     [rcx+8], r14b
0x180048adf  jz      short loc_180048B02
0x180048ae1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048ae6  cmp     [rax+7CCh], ebx
0x180048aec  jz      short loc_180048B02
0x180048aee  mov     r9d, ebx; int
0x180048af1  mov     r8d, 4D5h; int
0x180048af7  mov     rdx, r12; char *
0x180048afa  mov     rcx, rax; this
0x180048afd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048b02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180048b09  jb      loc_18004925C
0x180048b0f  mov     edx, 69h ; 'i'
0x180048b14  jmp     loc_180048989
0x180048b19  mov     rax, [rdi]
0x180048b1c  lea     r8, [rbp+pvar]
0x180048b20  xor     r9d, r9d
0x180048b23  mov     [rsp+70h+var_50], r15d
0x180048b28  lea     rdx, PKEY_Audio_Format
0x180048b2f  mov     rcx, rdi
0x180048b32  mov     rax, [rax+28h]
0x180048b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b3b  mov     ebx, eax
0x180048b3d  test    eax, eax
0x180048b3f  jns     loc_180048BD0
0x180048b45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048b4c  test    rcx, rcx
0x180048b4f  jnz     short loc_180048B92
0x180048b51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048b57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048b5e  mov     rcx, rax
0x180048b61  test    rax, rax
0x180048b64  jz      short loc_180048B84
0x180048b66  mov     rax, [rax]
0x180048b69  mov     edx, 7F0h
0x180048b6e  mov     rax, [rax+8]
0x180048b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b77  test    eax, eax
0x180048b79  jz      short loc_180048B84
0x180048b7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048b82  jmp     short loc_180048B92
0x180048b84  lea     rcx, qword_1801B07E0; this
0x180048b8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048b92  cmp     [rcx+8], r14b
0x180048b96  jz      short loc_180048BB9
0x180048b98  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048b9d  cmp     [rax+7CCh], ebx
0x180048ba3  jz      short loc_180048BB9
0x180048ba5  mov     r9d, ebx; int
0x180048ba8  mov     r8d, 4D6h; int
0x180048bae  mov     rdx, r12; char *
0x180048bb1  mov     rcx, rax; this
0x180048bb4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048bb9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180048bc0  jb      loc_18004925C
0x180048bc6  mov     edx, 6Ah ; 'j'
0x180048bcb  jmp     loc_180048989
0x180048bd0  lea     rcx, [rbp+pvar]; pvar
0x180048bd4  call    cs:__imp_PropVariantClear
0x180048bda  mov     ebx, eax
0x180048bdc  test    eax, eax
0x180048bde  jns     loc_180048C6F
0x180048be4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048beb  test    rcx, rcx
0x180048bee  jnz     short loc_180048C31
0x180048bf0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048bf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048bfd  mov     rcx, rax
0x180048c00  test    rax, rax
0x180048c03  jz      short loc_180048C23
0x180048c05  mov     rax, [rax]
0x180048c08  mov     edx, 7F0h
0x180048c0d  mov     rax, [rax+8]
0x180048c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c16  test    eax, eax
0x180048c18  jz      short loc_180048C23
0x180048c1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048c21  jmp     short loc_180048C31
0x180048c23  lea     rcx, qword_1801B07E0; this
0x180048c2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048c31  cmp     [rcx+8], r14b
0x180048c35  jz      short loc_180048C58
0x180048c37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048c3c  cmp     [rax+7CCh], ebx
0x180048c42  jz      short loc_180048C58
0x180048c44  mov     r9d, ebx; int
0x180048c47  mov     r8d, 4D7h; int
0x180048c4d  mov     rdx, r12; char *
0x180048c50  mov     rcx, rax; this
0x180048c53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048c58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180048c5f  jb      loc_18004925C
0x180048c65  mov     edx, 6Bh ; 'k'
0x180048c6a  jmp     loc_180048989
0x180048c6f  mov     rax, [rsi]
0x180048c72  lea     r8, [rbp+var_40]
0x180048c76  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180048c7d  mov     word ptr [rbp+pvar], r13w
0x180048c82  mov     rcx, rsi
0x180048c85  mov     rax, [rax+38h]
0x180048c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c8e  test    eax, eax
0x180048c90  js      loc_180048DF2
0x180048c96  mov     eax, [rbp+var_40]
0x180048c99  lea     r8, [rbp+pvar]
0x180048c9d  mov     dword ptr [rbp+pvar+8], eax
0x180048ca0  lea     rdx, PKEY_Audio_SampleRate
0x180048ca7  mov     rax, [rdi]
0x180048caa  xor     r9d, r9d
0x180048cad  mov     rcx, rdi
0x180048cb0  mov     [rsp+70h+var_50], r15d
0x180048cb5  mov     rax, [rax+28h]
0x180048cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cbe  mov     ebx, eax
0x180048cc0  test    eax, eax
0x180048cc2  jns     loc_180048D53
0x180048cc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048ccf  test    rcx, rcx
0x180048cd2  jnz     short loc_180048D15
0x180048cd4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048cda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180048ce1  mov     rcx, rax
0x180048ce4  test    rax, rax
0x180048ce7  jz      short loc_180048D07
0x180048ce9  mov     rax, [rax]
0x180048cec  mov     edx, 7F0h
0x180048cf1  mov     rax, [rax+8]
0x180048cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cfa  test    eax, eax
0x180048cfc  jz      short loc_180048D07
0x180048cfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048d05  jmp     short loc_180048D15
0x180048d07  lea     rcx, qword_1801B07E0; this
0x180048d0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048d15  cmp     [rcx+8], r14b
0x180048d19  jz      short loc_180048D3C
0x180048d1b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048d20  cmp     [rax+7CCh], ebx
0x180048d26  jz      short loc_180048D3C
0x180048d28  mov     r9d, ebx; int
0x180048d2b  mov     r8d, 4E1h; int
0x180048d31  mov     rdx, r12; char *
0x180048d34  mov     rcx, rax; this
0x180048d37  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048d3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180048d43  jb      loc_18004925C
0x180048d49  mov     edx, 6Ch ; 'l'
0x180048d4e  jmp     loc_180048989
0x180048d53  lea     rcx, [rbp+pvar]; pvar
0x180048d57  call    cs:__imp_PropVariantClear
0x180048d5d  mov     ebx, eax
0x180048d5f  test    eax, eax
  ... truncated ...
```
