# CWMPropHandlerBase::AddAudioMediaTypeProperties(IMFMediaType *)

- ea: `0x18003f9f8`
- end: `0x180040461`
- name: `?AddAudioMediaTypeProperties@CWMPropHandlerBase@@IEAAJPEAUIMFMediaType@@@Z`
- size: `2665`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180042b60`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002b460`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003f9f8`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fb69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fd90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ff15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004009d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800401e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004038a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180040429`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fb69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fd90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ff15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004009d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800401e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004038a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180040429`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18003fc38`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18003fc38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fac7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fb85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fc54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fd0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fdac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fe91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ff31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040019`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800400b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004015e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800401fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800403a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fac7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fb85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fc54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fd0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fdac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fe91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ff31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040019`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800400b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004015e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800401fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800403a6`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddAudioMediaTypeProperties(CWMPropHandlerBase *this, struct IMFMediaType *a2)
{
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUINT32)(IMFMediaType *, const GUID *const, UINT32 *); // rax
  __int64 v6; // rdx
  HRESULT inited; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  struct IMFMediaTypeVtbl *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  struct IMFMediaTypeVtbl *v37; // rax
  int v38; // eax
  __int64 (__fastcall *v39)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int); // r10
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  struct IMFMediaTypeVtbl *v56; // rax
  __int64 v57; // rdx
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  LONG v66; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v67[4]; // [rsp+34h] [rbp-4Ch] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v69[8]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v70[16]; // [rsp+58h] [rbp-28h] BYREF
  IID clsid; // [rsp+68h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v67,
    "CWMPropHandlerBase::AddAudioMediaTypeProperties",
    1204);
  lpVtbl = a2->lpVtbl;
  v66 = 0;
  memset(&pvar, 0, sizeof(pvar));
  GetUINT32 = lpVtbl->GetUINT32;
  clsid = 0;
  pvar.vt = 19;
  if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))GetUINT32)(a2, &MF_MT_AUDIO_NUM_CHANNELS, &v66) < 0 )
    goto LABEL_25;
  pvar.lVal = v66;
  inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
             this,
             &PKEY_Audio_ChannelCount,
             &pvar,
             0,
             1);
  if ( inited < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::AddAudioMediaTypeProperties",
          1221,
          inited);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 103;
LABEL_13:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, inited);
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
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != inited )
            CallStackContext::TraceFailure(v19, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1237, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 105;
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
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != inited )
            CallStackContext::TraceFailure(v23, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1238, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 106;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != inited )
            CallStackContext::TraceFailure(v27, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1239, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 107;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v28 = a2->lpVtbl;
    pvar.vt = 19;
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v28->GetUINT32)(
           a2,
           &MF_MT_AUDIO_SAMPLES_PER_SECOND,
           &v66) >= 0 )
    {
      pvar.lVal = v66;
      inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                 this,
                 &PKEY_Audio_SampleRate,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != inited )
            CallStackContext::TraceFailure(v32, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1249, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 108;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != inited )
            CallStackContext::TraceFailure(v36, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1250, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 109;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v37 = a2->lpVtbl;
    pvar.vt = 19;
    v38 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v37->GetUINT32)(
            a2,
            &MF_MT_AUDIO_BITS_PER_SAMPLE,
            &v66);
    v39 = *(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL);
    if ( v38 < 0 )
    {
      pvar.lVal = 16;
      inited = v39(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != inited )
            CallStackContext::TraceFailure(v51, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1269, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 112;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v53 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)v55 + 499) != inited )
            CallStackContext::TraceFailure(v55, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1270, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 113;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    else
    {
      pvar.lVal = v66;
      inited = v39(this, &PKEY_Audio_SampleSize, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != inited )
            CallStackContext::TraceFailure(v43, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1260, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 110;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v45 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v47 + 499) != inited )
            CallStackContext::TraceFailure(v47, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1261, inited);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 111;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_EncodingBitrate,
                          v69,
                          v70) )
    {
      v56 = a2->lpVtbl;
      pvar.vt = 19;
      if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LONG *))v56->GetUINT32)(
             a2,
             &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
             &v66) >= 0 )
      {
        pvar.lVal = 8 * v66;
        inited = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
                   this,
                   &PKEY_Audio_EncodingBitrate,
                   &pvar,
                   0,
                   1);
        if ( inited < 0 )
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57);
            CallStackTracing::s_wpInstance = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v58 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
            if ( *((_DWORD *)v60 + 499) != inited )
              CallStackContext::TraceFailure(v60, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1285, inited);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 114;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
        inited = PropVariantClear(&pvar);
        if ( inited < 0 )
        {
          v62 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61);
            CallStackTracing::s_wpInstance = v63;
            if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
            {
              v62 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v62 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v62 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
            if ( *((_DWORD *)v64 + 499) != inited )
              CallStackContext::TraceFailure(v64, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1286, inited);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 115;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
      }
    }
    inited = 0;
    goto LABEL_152;
  }
  v13 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != inited )
      CallStackContext::TraceFailure(v15, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1222, inited);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v11 = 104;
    goto LABEL_13;
  }
LABEL_152:
  PropVariantClear(&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18003f9f8  mov     [rsp-38h+arg_10], rbx
0x18003f9fd  push    rbp
0x18003f9fe  push    rsi
0x18003f9ff  push    rdi
0x18003fa00  push    r12
0x18003fa02  push    r13
0x18003fa04  push    r14
0x18003fa06  push    r15
0x18003fa08  mov     rbp, rsp
0x18003fa0b  sub     rsp, 80h
0x18003fa12  mov     rax, cs:__security_cookie
0x18003fa19  xor     rax, rsp
0x18003fa1c  mov     [rbp+var_8], rax
0x18003fa20  mov     rsi, rdx
0x18003fa23  lea     r12, aCwmprophandler_9; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x18003fa2a  mov     rdi, rcx
0x18003fa2d  mov     rdx, r12; char *
0x18003fa30  mov     r8d, 4B4h; int
0x18003fa36  lea     rcx, [rbp+var_4C]; this
0x18003fa3a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003fa3f  xor     eax, eax
0x18003fa41  lea     r8, [rbp+var_50]
0x18003fa45  mov     qword ptr [rbp+pvar+10h], rax
0x18003fa49  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18003fa50  mov     rax, [rsi]
0x18003fa53  xor     r14d, r14d
0x18003fa56  xorps   xmm1, xmm1
0x18003fa59  mov     [rbp+var_50], r14d
0x18003fa5d  xorps   xmm0, xmm0
0x18003fa60  mov     rcx, rsi
0x18003fa63  movups  xmmword ptr [rbp+pvar], xmm1
0x18003fa67  mov     rax, [rax+38h]
0x18003fa6b  lea     r13d, [r14+13h]
0x18003fa6f  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18003fa73  mov     word ptr [rbp+pvar], r13w
0x18003fa78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa7d  lea     r15d, [r14+1]
0x18003fa81  test    eax, eax
0x18003fa83  js      loc_18003FC05
0x18003fa89  mov     eax, [rbp+var_50]
0x18003fa8c  lea     r8, [rbp+pvar]
0x18003fa90  mov     dword ptr [rbp+pvar+8], eax
0x18003fa93  lea     rdx, PKEY_Audio_ChannelCount
0x18003fa9a  mov     rax, [rdi]
0x18003fa9d  xor     r9d, r9d
0x18003faa0  mov     rcx, rdi
0x18003faa3  mov     [rsp+80h+var_60], r15d
0x18003faa8  mov     rax, [rax+28h]
0x18003faac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fab1  mov     ebx, eax
0x18003fab3  test    eax, eax
0x18003fab5  jns     loc_18003FB65
0x18003fabb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fac2  test    rcx, rcx
0x18003fac5  jnz     short loc_18003FB08
0x18003fac7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003facd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fad4  mov     rcx, rax
0x18003fad7  test    rax, rax
0x18003fada  jz      short loc_18003FAFA
0x18003fadc  mov     rax, [rax]
0x18003fadf  mov     edx, 7F0h
0x18003fae4  mov     rax, [rax+8]
0x18003fae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faed  test    eax, eax
0x18003faef  jz      short loc_18003FAFA
0x18003faf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003faf8  jmp     short loc_18003FB08
0x18003fafa  lea     rcx, qword_18006EB20; this
0x18003fb01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fb08  cmp     [rcx+8], r14b
0x18003fb0c  jz      short loc_18003FB2F
0x18003fb0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fb13  cmp     [rax+7CCh], ebx
0x18003fb19  jz      short loc_18003FB2F
0x18003fb1b  mov     r9d, ebx; int
0x18003fb1e  mov     r8d, 4C5h; int
0x18003fb24  mov     rdx, r12; char *
0x18003fb27  mov     rcx, rax; this
0x18003fb2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fb2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fb34  cmp     al, r15b
0x18003fb37  jb      loc_180040425
0x18003fb3d  mov     edx, 67h ; 'g'
0x18003fb42  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb49  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18003fb50  mov     r9, rdi
0x18003fb53  mov     [rsp+80h+var_60], ebx
0x18003fb57  mov     rcx, [rcx+10h]
0x18003fb5b  call    WPP_SF_qd
0x18003fb60  jmp     loc_180040425
0x18003fb65  lea     rcx, [rbp+pvar]; pvar
0x18003fb69  call    cs:__imp_PropVariantClear
0x18003fb6f  mov     ebx, eax
0x18003fb71  test    eax, eax
0x18003fb73  jns     loc_18003FC05
0x18003fb79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fb80  test    rcx, rcx
0x18003fb83  jnz     short loc_18003FBC6
0x18003fb85  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fb8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fb92  mov     rcx, rax
0x18003fb95  test    rax, rax
0x18003fb98  jz      short loc_18003FBB8
0x18003fb9a  mov     rax, [rax]
0x18003fb9d  mov     edx, 7F0h
0x18003fba2  mov     rax, [rax+8]
0x18003fba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbab  test    eax, eax
0x18003fbad  jz      short loc_18003FBB8
0x18003fbaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fbb6  jmp     short loc_18003FBC6
0x18003fbb8  lea     rcx, qword_18006EB20; this
0x18003fbbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fbc6  cmp     [rcx+8], r14b
0x18003fbca  jz      short loc_18003FBED
0x18003fbcc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fbd1  cmp     [rax+7CCh], ebx
0x18003fbd7  jz      short loc_18003FBED
0x18003fbd9  mov     r9d, ebx; int
0x18003fbdc  mov     r8d, 4C6h; int
0x18003fbe2  mov     rdx, r12; char *
0x18003fbe5  mov     rcx, rax; this
0x18003fbe8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fbed  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fbf2  cmp     al, r15b
0x18003fbf5  jb      loc_180040425
0x18003fbfb  mov     edx, 68h ; 'h'
0x18003fc00  jmp     loc_18003FB42
0x18003fc05  mov     eax, 48h ; 'H'
0x18003fc0a  lea     r8, [rbp+clsid]
0x18003fc0e  mov     word ptr [rbp+pvar], ax
0x18003fc12  lea     rdx, MF_MT_SUBTYPE
0x18003fc19  mov     rax, [rsi]
0x18003fc1c  mov     rcx, rsi
0x18003fc1f  mov     rax, [rax+50h]
0x18003fc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc28  test    eax, eax
0x18003fc2a  js      loc_18003FE2C
0x18003fc30  lea     rdx, [rbp+pvar]; ppropvar
0x18003fc34  lea     rcx, [rbp+clsid]; clsid
0x18003fc38  call    cs:__imp_InitPropVariantFromCLSID
0x18003fc3e  mov     ebx, eax
0x18003fc40  test    eax, eax
0x18003fc42  jns     loc_18003FCD4
0x18003fc48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc4f  test    rcx, rcx
0x18003fc52  jnz     short loc_18003FC95
0x18003fc54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fc5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc61  mov     rcx, rax
0x18003fc64  test    rax, rax
0x18003fc67  jz      short loc_18003FC87
0x18003fc69  mov     rax, [rax]
0x18003fc6c  mov     edx, 7F0h
0x18003fc71  mov     rax, [rax+8]
0x18003fc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc7a  test    eax, eax
0x18003fc7c  jz      short loc_18003FC87
0x18003fc7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc85  jmp     short loc_18003FC95
0x18003fc87  lea     rcx, qword_18006EB20; this
0x18003fc8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc95  cmp     [rcx+8], r14b
0x18003fc99  jz      short loc_18003FCBC
0x18003fc9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fca0  cmp     [rax+7CCh], ebx
0x18003fca6  jz      short loc_18003FCBC
0x18003fca8  mov     r9d, ebx; int
0x18003fcab  mov     r8d, 4D5h; int
0x18003fcb1  mov     rdx, r12; char *
0x18003fcb4  mov     rcx, rax; this
0x18003fcb7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fcbc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fcc1  cmp     al, r15b
0x18003fcc4  jb      loc_180040425
0x18003fcca  mov     edx, 69h ; 'i'
0x18003fccf  jmp     loc_18003FB42
0x18003fcd4  mov     rax, [rdi]
0x18003fcd7  lea     r8, [rbp+pvar]
0x18003fcdb  xor     r9d, r9d
0x18003fcde  mov     [rsp+80h+var_60], r15d
0x18003fce3  lea     rdx, PKEY_Audio_Format
0x18003fcea  mov     rcx, rdi
0x18003fced  mov     rax, [rax+28h]
0x18003fcf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcf6  mov     ebx, eax
0x18003fcf8  test    eax, eax
0x18003fcfa  jns     loc_18003FD8C
0x18003fd00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd07  test    rcx, rcx
0x18003fd0a  jnz     short loc_18003FD4D
0x18003fd0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fd12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd19  mov     rcx, rax
0x18003fd1c  test    rax, rax
0x18003fd1f  jz      short loc_18003FD3F
0x18003fd21  mov     rax, [rax]
0x18003fd24  mov     edx, 7F0h
0x18003fd29  mov     rax, [rax+8]
0x18003fd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd32  test    eax, eax
0x18003fd34  jz      short loc_18003FD3F
0x18003fd36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd3d  jmp     short loc_18003FD4D
0x18003fd3f  lea     rcx, qword_18006EB20; this
0x18003fd46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd4d  cmp     [rcx+8], r14b
0x18003fd51  jz      short loc_18003FD74
0x18003fd53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fd58  cmp     [rax+7CCh], ebx
0x18003fd5e  jz      short loc_18003FD74
0x18003fd60  mov     r9d, ebx; int
0x18003fd63  mov     r8d, 4D6h; int
0x18003fd69  mov     rdx, r12; char *
0x18003fd6c  mov     rcx, rax; this
0x18003fd6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fd74  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fd79  cmp     al, r15b
0x18003fd7c  jb      loc_180040425
0x18003fd82  mov     edx, 6Ah ; 'j'
0x18003fd87  jmp     loc_18003FB42
0x18003fd8c  lea     rcx, [rbp+pvar]; pvar
0x18003fd90  call    cs:__imp_PropVariantClear
0x18003fd96  mov     ebx, eax
0x18003fd98  test    eax, eax
0x18003fd9a  jns     loc_18003FE2C
0x18003fda0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fda7  test    rcx, rcx
0x18003fdaa  jnz     short loc_18003FDED
0x18003fdac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fdb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fdb9  mov     rcx, rax
0x18003fdbc  test    rax, rax
0x18003fdbf  jz      short loc_18003FDDF
0x18003fdc1  mov     rax, [rax]
0x18003fdc4  mov     edx, 7F0h
0x18003fdc9  mov     rax, [rax+8]
0x18003fdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdd2  test    eax, eax
0x18003fdd4  jz      short loc_18003FDDF
0x18003fdd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fddd  jmp     short loc_18003FDED
0x18003fddf  lea     rcx, qword_18006EB20; this
0x18003fde6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fded  cmp     [rcx+8], r14b
0x18003fdf1  jz      short loc_18003FE14
0x18003fdf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fdf8  cmp     [rax+7CCh], ebx
0x18003fdfe  jz      short loc_18003FE14
0x18003fe00  mov     r9d, ebx; int
0x18003fe03  mov     r8d, 4D7h; int
0x18003fe09  mov     rdx, r12; char *
0x18003fe0c  mov     rcx, rax; this
0x18003fe0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fe14  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fe19  cmp     al, r15b
0x18003fe1c  jb      loc_180040425
0x18003fe22  mov     edx, 6Bh ; 'k'
0x18003fe27  jmp     loc_18003FB42
0x18003fe2c  mov     rax, [rsi]
0x18003fe2f  lea     r8, [rbp+var_50]
0x18003fe33  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x18003fe3a  mov     word ptr [rbp+pvar], r13w
0x18003fe3f  mov     rcx, rsi
0x18003fe42  mov     rax, [rax+38h]
0x18003fe46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe4b  test    eax, eax
0x18003fe4d  js      loc_18003FFB1
0x18003fe53  mov     eax, [rbp+var_50]
0x18003fe56  lea     r8, [rbp+pvar]
0x18003fe5a  mov     dword ptr [rbp+pvar+8], eax
0x18003fe5d  lea     rdx, PKEY_Audio_SampleRate
0x18003fe64  mov     rax, [rdi]
0x18003fe67  xor     r9d, r9d
0x18003fe6a  mov     rcx, rdi
0x18003fe6d  mov     [rsp+80h+var_60], r15d
0x18003fe72  mov     rax, [rax+28h]
0x18003fe76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe7b  mov     ebx, eax
0x18003fe7d  test    eax, eax
0x18003fe7f  jns     loc_18003FF11
0x18003fe85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe8c  test    rcx, rcx
0x18003fe8f  jnz     short loc_18003FED2
0x18003fe91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fe97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe9e  mov     rcx, rax
0x18003fea1  test    rax, rax
0x18003fea4  jz      short loc_18003FEC4
0x18003fea6  mov     rax, [rax]
0x18003fea9  mov     edx, 7F0h
0x18003feae  mov     rax, [rax+8]
0x18003feb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feb7  test    eax, eax
0x18003feb9  jz      short loc_18003FEC4
0x18003febb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fec2  jmp     short loc_18003FED2
0x18003fec4  lea     rcx, qword_18006EB20; this
0x18003fecb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
