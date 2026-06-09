# CWMPropHandlerBase::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)

- ea: `0x180058b70`
- end: `0x180059568`
- name: `?AddPresentationDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2552`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cff0`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004f47c`
- `0x1800530e4`
- `0x180058b70`
- `0x18005b650`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058d56`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800590a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005924f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800593f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058d56`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800590a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005924f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800593f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058bea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058cd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058d72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ef0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800590c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800591cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005926b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800594b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058bea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058cd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058d72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ef0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800590c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800591cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005926b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800594b1`

## string_xrefs

- `0x180058b8a`: `CWMPropHandlerBase::AddPresentationDescriptorProperties`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddPresentationDescriptorProperties(
        CWMPropHandlerBase *this,
        struct IMFPresentationDescriptor *a2)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v5; // rdx
  HRESULT v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  unsigned int i; // r14d
  struct IMFPresentationDescriptorVtbl *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rax
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
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  _BYTE v86[16]; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-20h] BYREF
  __int64 v88; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v89; // [rsp+B0h] [rbp+50h] BYREF
  int v90; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v88,
    "CWMPropHandlerBase::AddPresentationDescriptorProperties",
    1809);
  lpVtbl = a2->lpVtbl;
  v89 = 0;
  v90 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v6 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))lpVtbl->GetStreamDescriptorCount)(
         a2,
         &v89);
  if ( v6 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMPropHandlerBase::AddPresentationDescriptorProperties",
          1820,
          v6);
    }
    if ( g_wppLevels )
    {
      v12 = 162;
LABEL_149:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v6);
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
    for ( i = 0; i < v89; ++i )
    {
      v26 = a2->lpVtbl;
      v88 = 0;
      v6 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))v26->GetStreamDescriptorByIndex)(
             a2,
             i,
             &v90,
             &v88);
      if ( v6 < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != v6 )
            CallStackContext::TraceFailure(v39, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1839, v6);
        }
        if ( g_wppLevels )
        {
          v36 = 165;
LABEL_61:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v6);
        }
LABEL_62:
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v88);
        goto LABEL_150;
      }
      if ( v90 )
      {
        v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, __int64))(*(_QWORD *)this + 208LL))(this, v88);
        if ( v6 < 0 )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != v6 )
              CallStackContext::TraceFailure(v35, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1843, v6);
          }
          if ( g_wppLevels )
          {
            v36 = 166;
            goto LABEL_61;
          }
          goto LABEL_62;
        }
      }
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v88);
    }
    if ( *((_DWORD *)this + 225)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_EncodingBitrate,
                          &v88,
                          v86)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_AUDIO_ENCODING_BITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v40 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v40 + 40))(
             this,
             &PKEY_Audio_EncodingBitrate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
      {
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != v6 )
            CallStackContext::TraceFailure(v46, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1857, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 167;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != v6 )
            CallStackContext::TraceFailure(v52, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1858, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 168;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    if ( *((_DWORD *)this + 226)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Video_EncodingBitrate,
                          &v88,
                          v86)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_VIDEO_ENCODING_BITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v53 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v53 + 40))(
             this,
             &PKEY_Video_EncodingBitrate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v59 + 499) != v6 )
            CallStackContext::TraceFailure(v59, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1870, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 169;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
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
          if ( *((_DWORD *)v65 + 499) != v6 )
            CallStackContext::TraceFailure(v65, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1871, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 170;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    if ( *((_DWORD *)this + 225)
      && !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                          (char *)this + 48,
                          &PKEY_Audio_IsVariableBitRate,
                          &v88,
                          v86)
      && ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_AUDIO_ISVARIABLEBITRATE,
           &pvar.decVal.Lo32) >= 0 )
    {
      v66 = *(_QWORD *)this;
      pvar.vt = 19;
      v6 = (*(__int64 (__fastcall **)(CWMPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *, _QWORD, int))(v66 + 40))(
             this,
             &PKEY_Audio_IsVariableBitRate,
             &pvar,
             0,
             1);
      if ( v6 < 0 )
      {
        v70 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v70 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
          if ( *((_DWORD *)v72 + 499) != v6 )
            CallStackContext::TraceFailure(v72, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1883, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 171;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v6 = PropVariantClear(&pvar);
      if ( v6 < 0 )
      {
        v76 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73, v74, v75);
          CallStackTracing::s_wpInstance = v77;
          if ( v77 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
          {
            v76 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v76 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v76 + 8) )
        {
          v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
          if ( *((_DWORD *)v78 + 499) != v6 )
            CallStackContext::TraceFailure(v78, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1884, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 172;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
    }
    v6 = CWMPropHandlerBase::CheckForTotalBitrateProperty(this);
    if ( v6 < 0 )
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
        if ( *((_DWORD *)v84 + 499) != v6 )
          CallStackContext::TraceFailure(v84, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1893, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 173;
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
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != v6 )
          CallStackContext::TraceFailure(v24, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1830, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 164;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    goto LABEL_35;
  }
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != v6 )
      CallStackContext::TraceFailure(v18, "CWMPropHandlerBase::AddPresentationDescriptorProperties", 1829, v6);
  }
  if ( g_wppLevels )
  {
    v12 = 163;
    goto LABEL_149;
  }
LABEL_150:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v88);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180058b70  mov     [rsp-38h+arg_0], rbx
0x180058b75  push    rbp
0x180058b76  push    rsi
0x180058b77  push    rdi
0x180058b78  push    r12
0x180058b7a  push    r13
0x180058b7c  push    r14
0x180058b7e  push    r15
0x180058b80  mov     rbp, rsp
0x180058b83  sub     rsp, 60h
0x180058b87  mov     r15, rdx
0x180058b8a  lea     r13, aCwmprophandler_12; "CWMPropHandlerBase::AddPresentationDesc"...
0x180058b91  mov     rdi, rcx
0x180058b94  mov     rdx, r13; char *
0x180058b97  mov     r8d, 711h; int
0x180058b9d  lea     rcx, [rbp+arg_8]; this
0x180058ba1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180058ba6  xor     eax, eax
0x180058ba8  lea     rdx, [rbp+arg_10]
0x180058bac  mov     qword ptr [rbp+pvar+10h], rax
0x180058bb0  xor     r12d, r12d
0x180058bb3  mov     rax, [r15]
0x180058bb6  xorps   xmm0, xmm0
0x180058bb9  mov     rcx, r15
0x180058bbc  mov     [rbp+arg_10], r12d
0x180058bc0  mov     [rbp+arg_18], r12d
0x180058bc4  movups  xmmword ptr [rbp+pvar], xmm0
0x180058bc8  mov     rax, [rax+108h]
0x180058bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bd4  mov     ebx, eax
0x180058bd6  test    eax, eax
0x180058bd8  jns     loc_180058C6E
0x180058bde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058be5  test    rcx, rcx
0x180058be8  jnz     short loc_180058C2B
0x180058bea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058bf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058bf7  mov     rcx, rax
0x180058bfa  test    rax, rax
0x180058bfd  jz      short loc_180058C1D
0x180058bff  mov     rax, [rax]
0x180058c02  mov     edx, 7F0h
0x180058c07  mov     rax, [rax+8]
0x180058c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c10  test    eax, eax
0x180058c12  jz      short loc_180058C1D
0x180058c14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058c1b  jmp     short loc_180058C2B
0x180058c1d  lea     rcx, qword_1800D6F70; this
0x180058c24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058c2b  cmp     [rcx+8], r12b
0x180058c2f  jz      short loc_180058C52
0x180058c31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058c36  cmp     [rax+7CCh], ebx
0x180058c3c  jz      short loc_180058C52
0x180058c3e  mov     r9d, ebx; int
0x180058c41  mov     r8d, 71Ch; int
0x180058c47  mov     rdx, r13; char *
0x180058c4a  mov     rcx, rax; this
0x180058c4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058c52  mov     esi, 1
0x180058c57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058c5e  jb      loc_180059545
0x180058c64  mov     edx, 0A2h
0x180058c69  jmp     loc_180059527
0x180058c6e  mov     rax, [r15]
0x180058c71  lea     r8, [rbp+pvar+8]
0x180058c75  lea     rdx, MF_PD_DURATION
0x180058c7c  mov     rcx, r15
0x180058c7f  mov     rax, [rax+40h]
0x180058c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c88  mov     esi, 1
0x180058c8d  test    eax, eax
0x180058c8f  js      loc_180058DF1
0x180058c95  lea     eax, [rsi+14h]
0x180058c98  mov     [rsp+60h+var_40], esi
0x180058c9c  mov     word ptr [rbp+pvar], ax
0x180058ca0  lea     r8, [rbp+pvar]
0x180058ca4  mov     rax, [rdi]
0x180058ca7  lea     rdx, PKEY_Media_Duration
0x180058cae  xor     r9d, r9d
0x180058cb1  mov     rcx, rdi
0x180058cb4  mov     rax, [rax+28h]
0x180058cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cbd  mov     ebx, eax
0x180058cbf  test    eax, eax
0x180058cc1  jns     loc_180058D52
0x180058cc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058cce  test    rcx, rcx
0x180058cd1  jnz     short loc_180058D14
0x180058cd3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058cd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058ce0  mov     rcx, rax
0x180058ce3  test    rax, rax
0x180058ce6  jz      short loc_180058D06
0x180058ce8  mov     rax, [rax]
0x180058ceb  mov     edx, 7F0h
0x180058cf0  mov     rax, [rax+8]
0x180058cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cf9  test    eax, eax
0x180058cfb  jz      short loc_180058D06
0x180058cfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058d04  jmp     short loc_180058D14
0x180058d06  lea     rcx, qword_1800D6F70; this
0x180058d0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058d14  cmp     [rcx+8], r12b
0x180058d18  jz      short loc_180058D3B
0x180058d1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058d1f  cmp     [rax+7CCh], ebx
0x180058d25  jz      short loc_180058D3B
0x180058d27  mov     r9d, ebx; int
0x180058d2a  mov     r8d, 725h; int
0x180058d30  mov     rdx, r13; char *
0x180058d33  mov     rcx, rax; this
0x180058d36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058d3b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058d42  jb      loc_180059545
0x180058d48  mov     edx, 0A3h
0x180058d4d  jmp     loc_180059527
0x180058d52  lea     rcx, [rbp+pvar]; pvar
0x180058d56  call    cs:__imp_PropVariantClear
0x180058d5c  mov     ebx, eax
0x180058d5e  test    eax, eax
0x180058d60  jns     loc_180058DF1
0x180058d66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058d6d  test    rcx, rcx
0x180058d70  jnz     short loc_180058DB3
0x180058d72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058d78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058d7f  mov     rcx, rax
0x180058d82  test    rax, rax
0x180058d85  jz      short loc_180058DA5
0x180058d87  mov     rax, [rax]
0x180058d8a  mov     edx, 7F0h
0x180058d8f  mov     rax, [rax+8]
0x180058d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d98  test    eax, eax
0x180058d9a  jz      short loc_180058DA5
0x180058d9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058da3  jmp     short loc_180058DB3
0x180058da5  lea     rcx, qword_1800D6F70; this
0x180058dac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058db3  cmp     [rcx+8], r12b
0x180058db7  jz      short loc_180058DDA
0x180058db9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058dbe  cmp     [rax+7CCh], ebx
0x180058dc4  jz      short loc_180058DDA
0x180058dc6  mov     r9d, ebx; int
0x180058dc9  mov     r8d, 726h; int
0x180058dcf  mov     rdx, r13; char *
0x180058dd2  mov     rcx, rax; this
0x180058dd5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058dda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058de1  jb      loc_180059545
0x180058de7  mov     edx, 0A4h
0x180058dec  jmp     loc_180059527
0x180058df1  mov     r14d, r12d
0x180058df4  cmp     r14d, [rbp+arg_10]
0x180058df8  jnb     loc_180058F92
0x180058dfe  mov     rax, [r15]
0x180058e01  lea     r9, [rbp+arg_8]
0x180058e05  lea     r8, [rbp+arg_18]
0x180058e09  mov     [rbp+arg_8], r12
0x180058e0d  mov     edx, r14d
0x180058e10  mov     rcx, r15
0x180058e13  mov     rax, [rax+110h]
0x180058e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e1f  mov     ebx, eax
0x180058e21  test    eax, eax
0x180058e23  js      loc_180058EE4
0x180058e29  cmp     [rbp+arg_18], r12d
0x180058e2d  jz      short loc_180058E4B
0x180058e2f  mov     rax, [rdi]
0x180058e32  mov     rcx, rdi
0x180058e35  mov     rdx, [rbp+arg_8]
0x180058e39  mov     rax, [rax+0D0h]
0x180058e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e45  mov     ebx, eax
0x180058e47  test    eax, eax
0x180058e49  js      short loc_180058E59
0x180058e4b  lea     rcx, [rbp+arg_8]
0x180058e4f  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180058e54  add     r14d, esi
0x180058e57  jmp     short loc_180058DF4
0x180058e59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058e60  test    rcx, rcx
0x180058e63  jnz     short loc_180058EA6
0x180058e65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058e6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058e72  mov     rcx, rax
0x180058e75  test    rax, rax
0x180058e78  jz      short loc_180058E98
0x180058e7a  mov     rax, [rax]
0x180058e7d  mov     edx, 7F0h
0x180058e82  mov     rax, [rax+8]
0x180058e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e8b  test    eax, eax
0x180058e8d  jz      short loc_180058E98
0x180058e8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058e96  jmp     short loc_180058EA6
0x180058e98  lea     rcx, qword_1800D6F70; this
0x180058e9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058ea6  cmp     [rcx+8], r12b
0x180058eaa  jz      short loc_180058ECD
0x180058eac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058eb1  cmp     [rax+7CCh], ebx
0x180058eb7  jz      short loc_180058ECD
0x180058eb9  mov     r9d, ebx; int
0x180058ebc  mov     r8d, 733h; int
0x180058ec2  mov     rdx, r13; char *
0x180058ec5  mov     rcx, rax; this
0x180058ec8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058ecd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058ed4  jb      loc_180058F84
0x180058eda  mov     edx, 0A6h
0x180058edf  jmp     loc_180058F66
0x180058ee4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058eeb  test    rcx, rcx
0x180058eee  jnz     short loc_180058F31
0x180058ef0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058ef6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058efd  mov     rcx, rax
0x180058f00  test    rax, rax
0x180058f03  jz      short loc_180058F23
0x180058f05  mov     rax, [rax]
0x180058f08  mov     edx, 7F0h
0x180058f0d  mov     rax, [rax+8]
0x180058f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f16  test    eax, eax
0x180058f18  jz      short loc_180058F23
0x180058f1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058f21  jmp     short loc_180058F31
0x180058f23  lea     rcx, qword_1800D6F70; this
0x180058f2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058f31  cmp     [rcx+8], r12b
0x180058f35  jz      short loc_180058F58
0x180058f37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058f3c  cmp     [rax+7CCh], ebx
0x180058f42  jz      short loc_180058F58
0x180058f44  mov     r9d, ebx; int
0x180058f47  mov     r8d, 72Fh; int
0x180058f4d  mov     rdx, r13; char *
0x180058f50  mov     rcx, rax; this
0x180058f53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058f58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058f5f  jb      short loc_180058F84
0x180058f61  mov     edx, 0A5h
0x180058f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f6d  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180058f74  mov     r9, rdi
0x180058f77  mov     [rsp+60h+var_40], ebx
0x180058f7b  mov     rcx, [rcx+10h]
0x180058f7f  call    WPP_SF_qD
0x180058f84  lea     rcx, [rbp+arg_8]
0x180058f88  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180058f8d  jmp     loc_180059545
0x180058f92  mov     r14d, 13h
0x180058f98  cmp     [rdi+384h], r12d
0x180058f9f  jz      loc_180059141
0x180058fa5  lea     rcx, [rdi+30h]
0x180058fa9  lea     r9, [rbp+var_30]
0x180058fad  lea     r8, [rbp+arg_8]
0x180058fb1  lea     rdx, PKEY_Audio_EncodingBitrate
0x180058fb8  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180058fbd  test    eax, eax
0x180058fbf  jnz     loc_180059141
0x180058fc5  mov     rax, [r15]
0x180058fc8  lea     r8, [rbp+pvar+8]
0x180058fcc  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x180058fd3  mov     rcx, r15
0x180058fd6  mov     rax, [rax+38h]
0x180058fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fdf  test    eax, eax
0x180058fe1  js      loc_180059141
0x180058fe7  mov     rax, [rdi]
0x180058fea  lea     r8, [rbp+pvar]
0x180058fee  xor     r9d, r9d
0x180058ff1  mov     word ptr [rbp+pvar], r14w
0x180058ff6  lea     rdx, PKEY_Audio_EncodingBitrate
0x180058ffd  mov     [rsp+60h+var_40], esi
0x180059001  mov     rcx, rdi
0x180059004  mov     rax, [rax+28h]
0x180059008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005900d  mov     ebx, eax
0x18005900f  test    eax, eax
0x180059011  jns     loc_1800590A2
0x180059017  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005901e  test    rcx, rcx
0x180059021  jnz     short loc_180059064
0x180059023  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059029  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059030  mov     rcx, rax
0x180059033  test    rax, rax
0x180059036  jz      short loc_180059056
0x180059038  mov     rax, [rax]
0x18005903b  mov     edx, 7F0h
0x180059040  mov     rax, [rax+8]
0x180059044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059049  test    eax, eax
0x18005904b  jz      short loc_180059056
  ... truncated ...
```
