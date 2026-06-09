# CWMPropHandlerBase::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)

- ea: `0x180041720`
- end: `0x180042124`
- name: `?AddPresentationDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2564`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a830`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002b460`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180041720`
- `0x180044220`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041c5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041e07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041fb2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041c5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041e07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004179a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041884`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041aa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041c78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041d83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041e23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041fce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004206c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004179a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041884`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041aa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041c78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041d83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041e23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041fce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004206c`

## string_xrefs

- `0x18004173a`: `CWMPropHandlerBase::AddPresentationDescriptorProperties`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddPresentationDescriptorProperties(
        CWMPropHandlerBase *this,
        struct IMFPresentationDescriptor *a2)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v5; // rdx
  HRESULT v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int i; // r14d
  struct IMFPresentationDescriptorVtbl *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  _BYTE v62[16]; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-20h] BYREF
  __int64 v64; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v65; // [rsp+B0h] [rbp+50h] BYREF
  int v66; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v64,
    "CWMPropHandlerBase::AddPresentationDescriptorProperties",
    1809);
  lpVtbl = a2->lpVtbl;
  v65 = 0;
  v66 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v6 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))lpVtbl->GetStreamDescriptorCount)(
         a2,
         &v65);
  if ( v6 < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::AddPresentationDescriptorProperties",
          1820,
          v6);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 162;
LABEL_149:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v6);
      goto LABEL_150;
    }
    goto LABEL_150;
  }
  if ( ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT64)(
         a2,
         &MF_PD_DURATION,
         &pvar.decVal.Lo32) < 0 )
  {
LABEL_35:
    for ( i = 0; i < v65; ++i )
    {
      v20 = a2->lpVtbl;
      v64 = 0;
      v6 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))v20->GetStreamDescriptorByIndex)(
             a2,
             i,
             &v66,
             &v64);
      if ( v6 < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v6 )
            CallStackContext::TraceFailure(v29, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1839, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v26 = 165;
LABEL_61:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
            this,
            v6);
        }
LABEL_62:
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v64);
        goto LABEL_150;
      }
      if ( v66 )
      {
        v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, __int64))(*(_QWORD *)this + 208LL))(this, v64);
        if ( v6 < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v6 )
              CallStackContext::TraceFailure(v25, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1843, v6);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v26 = 166;
            goto LABEL_61;
          }
          goto LABEL_62;
        }
      }
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v64);
    }
    if ( *((_DWORD *)this + 225)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_EncodingBitrate,
                          &v64,
                          v62)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_AUDIO_ENCODING_BITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v30 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v30 + 40))(
             this,
             &PKEY_Audio_EncodingBitrate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != v6 )
            CallStackContext::TraceFailure(v34, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1857, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 167;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
      {
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != v6 )
            CallStackContext::TraceFailure(v38, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1858, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 168;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    if ( *((_DWORD *)this + 226)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Video_EncodingBitrate,
                          &v64,
                          v62)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_VIDEO_ENCODING_BITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v39 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v39 + 40))(
             this,
             &PKEY_Video_EncodingBitrate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v43 + 499) != v6 )
            CallStackContext::TraceFailure(v43, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1870, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 169;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v47 + 499) != v6 )
            CallStackContext::TraceFailure(v47, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1871, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 170;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    if ( *((_DWORD *)this + 225)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_IsVariableBitRate,
                          &v64,
                          v62)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_AUDIO_ISVARIABLEBITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v48 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v48 + 40))(
             this,
             &PKEY_Audio_IsVariableBitRate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != v6 )
            CallStackContext::TraceFailure(v52, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1883, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 171;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != v6 )
            CallStackContext::TraceFailure(v56, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1884, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 172;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    v6 = CWMPropHandlerBase::CheckForTotalBitrateProperty(this);
    if ( v6 < 0 )
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
        if ( *((_DWORD *)v60 + 499) != v6 )
          CallStackContext::TraceFailure(v60, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1893, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 173;
        goto LABEL_149;
      }
    }
    goto LABEL_150;
  }
  pvar.vt = 21;
  v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)this + 40LL))(
         this,
         &PKEY_Media_Duration,
         &pvar,
         0,
         1);
  if ( v6 >= 0 )
  {
    v6 = PropVariantClear(&pvar);
    if ( v6 < 0 )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v6 )
          CallStackContext::TraceFailure(v18, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1830, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 164;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    goto LABEL_35;
  }
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)v14 + 499) != v6 )
      CallStackContext::TraceFailure(v14, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1829, v6);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v10 = 163;
    goto LABEL_149;
  }
LABEL_150:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v64);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180041720  mov     [rsp-38h+arg_0], rbx
0x180041725  push    rbp
0x180041726  push    rsi
0x180041727  push    rdi
0x180041728  push    r12
0x18004172a  push    r13
0x18004172c  push    r14
0x18004172e  push    r15
0x180041730  mov     rbp, rsp
0x180041733  sub     rsp, 60h
0x180041737  mov     r15, rdx
0x18004173a  lea     r13, aCwmprophandler_12; "CWMPropHandlerBase::AddPresentationDesc"...
0x180041741  mov     rdi, rcx
0x180041744  mov     rdx, r13; char *
0x180041747  mov     r8d, 711h; int
0x18004174d  lea     rcx, [rbp+arg_8]; this
0x180041751  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180041756  xor     eax, eax
0x180041758  lea     rdx, [rbp+arg_10]
0x18004175c  mov     qword ptr [rbp+pvar+10h], rax
0x180041760  xor     r12d, r12d
0x180041763  mov     rax, [r15]
0x180041766  xorps   xmm0, xmm0
0x180041769  mov     rcx, r15
0x18004176c  mov     [rbp+arg_10], r12d
0x180041770  mov     [rbp+arg_18], r12d
0x180041774  movups  xmmword ptr [rbp+pvar], xmm0
0x180041778  mov     rax, [rax+108h]
0x18004177f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041784  mov     ebx, eax
0x180041786  test    eax, eax
0x180041788  jns     loc_18004181F
0x18004178e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041795  test    rcx, rcx
0x180041798  jnz     short loc_1800417DB
0x18004179a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800417a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417a7  mov     rcx, rax
0x1800417aa  test    rax, rax
0x1800417ad  jz      short loc_1800417CD
0x1800417af  mov     rax, [rax]
0x1800417b2  mov     edx, 7F0h
0x1800417b7  mov     rax, [rax+8]
0x1800417bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417c0  test    eax, eax
0x1800417c2  jz      short loc_1800417CD
0x1800417c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417cb  jmp     short loc_1800417DB
0x1800417cd  lea     rcx, qword_18006EB20; this
0x1800417d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417db  cmp     [rcx+8], r12b
0x1800417df  jz      short loc_180041802
0x1800417e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800417e6  cmp     [rax+7CCh], ebx
0x1800417ec  jz      short loc_180041802
0x1800417ee  mov     r9d, ebx; int
0x1800417f1  mov     r8d, 71Ch; int
0x1800417f7  mov     rdx, r13; char *
0x1800417fa  mov     rcx, rax; this
0x1800417fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041802  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041807  mov     esi, 1
0x18004180c  cmp     al, sil
0x18004180f  jb      loc_180042101
0x180041815  mov     edx, 0A2h
0x18004181a  jmp     loc_1800420E3
0x18004181f  mov     rax, [r15]
0x180041822  lea     r8, [rbp+pvar+8]
0x180041826  lea     rdx, MF_PD_DURATION
0x18004182d  mov     rcx, r15
0x180041830  mov     rax, [rax+40h]
0x180041834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041839  mov     esi, 1
0x18004183e  test    eax, eax
0x180041840  js      loc_1800419A4
0x180041846  lea     eax, [rsi+14h]
0x180041849  mov     [rsp+60h+var_40], esi
0x18004184d  mov     word ptr [rbp+pvar], ax
0x180041851  lea     r8, [rbp+pvar]
0x180041855  mov     rax, [rdi]
0x180041858  lea     rdx, PKEY_Media_Duration
0x18004185f  xor     r9d, r9d
0x180041862  mov     rcx, rdi
0x180041865  mov     rax, [rax+28h]
0x180041869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004186e  mov     ebx, eax
0x180041870  test    eax, eax
0x180041872  jns     loc_180041904
0x180041878  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004187f  test    rcx, rcx
0x180041882  jnz     short loc_1800418C5
0x180041884  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004188a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041891  mov     rcx, rax
0x180041894  test    rax, rax
0x180041897  jz      short loc_1800418B7
0x180041899  mov     rax, [rax]
0x18004189c  mov     edx, 7F0h
0x1800418a1  mov     rax, [rax+8]
0x1800418a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418aa  test    eax, eax
0x1800418ac  jz      short loc_1800418B7
0x1800418ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418b5  jmp     short loc_1800418C5
0x1800418b7  lea     rcx, qword_18006EB20; this
0x1800418be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418c5  cmp     [rcx+8], r12b
0x1800418c9  jz      short loc_1800418EC
0x1800418cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800418d0  cmp     [rax+7CCh], ebx
0x1800418d6  jz      short loc_1800418EC
0x1800418d8  mov     r9d, ebx; int
0x1800418db  mov     r8d, 725h; int
0x1800418e1  mov     rdx, r13; char *
0x1800418e4  mov     rcx, rax; this
0x1800418e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800418ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800418f1  cmp     al, sil
0x1800418f4  jb      loc_180042101
0x1800418fa  mov     edx, 0A3h
0x1800418ff  jmp     loc_1800420E3
0x180041904  lea     rcx, [rbp+pvar]; pvar
0x180041908  call    cs:__imp_PropVariantClear
0x18004190e  mov     ebx, eax
0x180041910  test    eax, eax
0x180041912  jns     loc_1800419A4
0x180041918  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004191f  test    rcx, rcx
0x180041922  jnz     short loc_180041965
0x180041924  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004192a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041931  mov     rcx, rax
0x180041934  test    rax, rax
0x180041937  jz      short loc_180041957
0x180041939  mov     rax, [rax]
0x18004193c  mov     edx, 7F0h
0x180041941  mov     rax, [rax+8]
0x180041945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004194a  test    eax, eax
0x18004194c  jz      short loc_180041957
0x18004194e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041955  jmp     short loc_180041965
0x180041957  lea     rcx, qword_18006EB20; this
0x18004195e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041965  cmp     [rcx+8], r12b
0x180041969  jz      short loc_18004198C
0x18004196b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041970  cmp     [rax+7CCh], ebx
0x180041976  jz      short loc_18004198C
0x180041978  mov     r9d, ebx; int
0x18004197b  mov     r8d, 726h; int
0x180041981  mov     rdx, r13; char *
0x180041984  mov     rcx, rax; this
0x180041987  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004198c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041991  cmp     al, sil
0x180041994  jb      loc_180042101
0x18004199a  mov     edx, 0A4h
0x18004199f  jmp     loc_1800420E3
0x1800419a4  mov     r14d, r12d
0x1800419a7  cmp     r14d, [rbp+arg_10]
0x1800419ab  jnb     loc_180041B47
0x1800419b1  mov     rax, [r15]
0x1800419b4  lea     r9, [rbp+arg_8]
0x1800419b8  lea     r8, [rbp+arg_18]
0x1800419bc  mov     [rbp+arg_8], r12
0x1800419c0  mov     edx, r14d
0x1800419c3  mov     rcx, r15
0x1800419c6  mov     rax, [rax+110h]
0x1800419cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419d2  mov     ebx, eax
0x1800419d4  test    eax, eax
0x1800419d6  js      loc_180041A98
0x1800419dc  cmp     [rbp+arg_18], r12d
0x1800419e0  jz      short loc_1800419FE
0x1800419e2  mov     rax, [rdi]
0x1800419e5  mov     rcx, rdi
0x1800419e8  mov     rdx, [rbp+arg_8]
0x1800419ec  mov     rax, [rax+0D0h]
0x1800419f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419f8  mov     ebx, eax
0x1800419fa  test    eax, eax
0x1800419fc  js      short loc_180041A0C
0x1800419fe  lea     rcx, [rbp+arg_8]
0x180041a02  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180041a07  add     r14d, esi
0x180041a0a  jmp     short loc_1800419A7
0x180041a0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a13  test    rcx, rcx
0x180041a16  jnz     short loc_180041A59
0x180041a18  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041a1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a25  mov     rcx, rax
0x180041a28  test    rax, rax
0x180041a2b  jz      short loc_180041A4B
0x180041a2d  mov     rax, [rax]
0x180041a30  mov     edx, 7F0h
0x180041a35  mov     rax, [rax+8]
0x180041a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a3e  test    eax, eax
0x180041a40  jz      short loc_180041A4B
0x180041a42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a49  jmp     short loc_180041A59
0x180041a4b  lea     rcx, qword_18006EB20; this
0x180041a52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a59  cmp     [rcx+8], r12b
0x180041a5d  jz      short loc_180041A80
0x180041a5f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041a64  cmp     [rax+7CCh], ebx
0x180041a6a  jz      short loc_180041A80
0x180041a6c  mov     r9d, ebx; int
0x180041a6f  mov     r8d, 733h; int
0x180041a75  mov     rdx, r13; char *
0x180041a78  mov     rcx, rax; this
0x180041a7b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041a80  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041a85  cmp     al, sil
0x180041a88  jb      loc_180041B39
0x180041a8e  mov     edx, 0A6h
0x180041a93  jmp     loc_180041B1B
0x180041a98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041a9f  test    rcx, rcx
0x180041aa2  jnz     short loc_180041AE5
0x180041aa4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041aaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041ab1  mov     rcx, rax
0x180041ab4  test    rax, rax
0x180041ab7  jz      short loc_180041AD7
0x180041ab9  mov     rax, [rax]
0x180041abc  mov     edx, 7F0h
0x180041ac1  mov     rax, [rax+8]
0x180041ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aca  test    eax, eax
0x180041acc  jz      short loc_180041AD7
0x180041ace  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041ad5  jmp     short loc_180041AE5
0x180041ad7  lea     rcx, qword_18006EB20; this
0x180041ade  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041ae5  cmp     [rcx+8], r12b
0x180041ae9  jz      short loc_180041B0C
0x180041aeb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041af0  cmp     [rax+7CCh], ebx
0x180041af6  jz      short loc_180041B0C
0x180041af8  mov     r9d, ebx; int
0x180041afb  mov     r8d, 72Fh; int
0x180041b01  mov     rdx, r13; char *
0x180041b04  mov     rcx, rax; this
0x180041b07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041b0c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041b11  cmp     al, sil
0x180041b14  jb      short loc_180041B39
0x180041b16  mov     edx, 0A5h
0x180041b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b22  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180041b29  mov     r9, rdi
0x180041b2c  mov     [rsp+60h+var_40], ebx
0x180041b30  mov     rcx, [rcx+10h]
0x180041b34  call    WPP_SF_qd
0x180041b39  lea     rcx, [rbp+arg_8]
0x180041b3d  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180041b42  jmp     loc_180042101
0x180041b47  mov     r14d, 13h
0x180041b4d  cmp     [rdi+384h], r12d
0x180041b54  jz      loc_180041CF8
0x180041b5a  lea     rcx, [rdi+30h]
0x180041b5e  lea     r9, [rbp+var_30]
0x180041b62  lea     r8, [rbp+arg_8]
0x180041b66  lea     rdx, PKEY_Audio_EncodingBitrate
0x180041b6d  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180041b72  test    eax, eax
0x180041b74  jnz     loc_180041CF8
0x180041b7a  mov     rax, [r15]
0x180041b7d  lea     r8, [rbp+pvar+8]
0x180041b81  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x180041b88  mov     rcx, r15
0x180041b8b  mov     rax, [rax+38h]
0x180041b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b94  test    eax, eax
0x180041b96  js      loc_180041CF8
0x180041b9c  mov     rax, [rdi]
0x180041b9f  lea     r8, [rbp+pvar]
0x180041ba3  xor     r9d, r9d
0x180041ba6  mov     word ptr [rbp+pvar], r14w
0x180041bab  lea     rdx, PKEY_Audio_EncodingBitrate
0x180041bb2  mov     [rsp+60h+var_40], esi
0x180041bb6  mov     rcx, rdi
0x180041bb9  mov     rax, [rax+28h]
0x180041bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bc2  mov     ebx, eax
0x180041bc4  test    eax, eax
0x180041bc6  jns     loc_180041C58
0x180041bcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041bd3  test    rcx, rcx
0x180041bd6  jnz     short loc_180041C19
0x180041bd8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041bde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041be5  mov     rcx, rax
0x180041be8  test    rax, rax
0x180041beb  jz      short loc_180041C0B
0x180041bed  mov     rax, [rax]
  ... truncated ...
```
