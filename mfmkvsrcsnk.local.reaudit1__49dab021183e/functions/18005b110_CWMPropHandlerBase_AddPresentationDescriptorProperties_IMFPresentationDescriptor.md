# CWMPropHandlerBase::AddPresentationDescriptorProperties(IMFPresentationDescriptor *)

- ea: `0x18005b110`
- end: `0x18005bb69`
- name: `?AddPresentationDescriptorProperties@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2649`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004eff0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800516a4`
- `0x180055474`
- `0x18005b110`
- `0x18005dd78`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b302`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b670`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b82b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b9e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b302`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b670`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b82b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b9e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b18a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b41d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b4ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b5e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b7a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b84d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b95d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ba08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005baab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b18a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b41d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b4ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b5e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b7a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b84d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b95d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ba08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005baab`

## string_xrefs

- `0x18005b12a`: `CWMPropHandlerBase::AddPresentationDescriptorProperties`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v37 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v33 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v44 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v50 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v57 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v63 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v70 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v76 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v82 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v22 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v16 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18005b110  mov     [rsp-38h+arg_0], rbx
0x18005b115  push    rbp
0x18005b116  push    rsi
0x18005b117  push    rdi
0x18005b118  push    r12
0x18005b11a  push    r13
0x18005b11c  push    r14
0x18005b11e  push    r15
0x18005b120  mov     rbp, rsp
0x18005b123  sub     rsp, 60h
0x18005b127  mov     r15, rdx
0x18005b12a  lea     r13, aCwmprophandler_12; "CWMPropHandlerBase::AddPresentationDesc"...
0x18005b131  mov     rdi, rcx
0x18005b134  mov     rdx, r13; char *
0x18005b137  mov     r8d, 711h; int
0x18005b13d  lea     rcx, [rbp+arg_8]; this
0x18005b141  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005b146  xor     eax, eax
0x18005b148  lea     rdx, [rbp+arg_10]
0x18005b14c  mov     qword ptr [rbp+pvar+10h], rax
0x18005b150  xor     r12d, r12d
0x18005b153  mov     rax, [r15]
0x18005b156  xorps   xmm0, xmm0
0x18005b159  mov     rcx, r15
0x18005b15c  mov     [rbp+arg_10], r12d
0x18005b160  mov     [rbp+arg_18], r12d
0x18005b164  movups  xmmword ptr [rbp+pvar], xmm0
0x18005b168  mov     rax, [rax+108h]
0x18005b16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b174  mov     ebx, eax
0x18005b176  test    eax, eax
0x18005b178  jns     loc_18005B214
0x18005b17e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b185  test    rcx, rcx
0x18005b188  jnz     short loc_18005B1D1
0x18005b18a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b191  nop     dword ptr [rax+rax+00h]
0x18005b196  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b19d  mov     rcx, rax
0x18005b1a0  test    rax, rax
0x18005b1a3  jz      short loc_18005B1C3
0x18005b1a5  mov     rax, [rax]
0x18005b1a8  mov     edx, 7F0h
0x18005b1ad  mov     rax, [rax+8]
0x18005b1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b1b6  test    eax, eax
0x18005b1b8  jz      short loc_18005B1C3
0x18005b1ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b1c1  jmp     short loc_18005B1D1
0x18005b1c3  lea     rcx, qword_1800DBF70; this
0x18005b1ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b1d1  cmp     [rcx+8], r12b
0x18005b1d5  jz      short loc_18005B1F8
0x18005b1d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b1dc  cmp     [rax+7CCh], ebx
0x18005b1e2  jz      short loc_18005B1F8
0x18005b1e4  mov     r9d, ebx; int
0x18005b1e7  mov     r8d, 71Ch; int
0x18005b1ed  mov     rdx, r13; char *
0x18005b1f0  mov     rcx, rax; this
0x18005b1f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b1f8  mov     esi, 1
0x18005b1fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b204  jb      loc_18005BB45
0x18005b20a  mov     edx, 0A2h
0x18005b20f  jmp     loc_18005BB27
0x18005b214  mov     rax, [r15]
0x18005b217  lea     r8, [rbp+pvar+8]
0x18005b21b  lea     rdx, MF_PD_DURATION
0x18005b222  mov     rcx, r15
0x18005b225  mov     rax, [rax+40h]
0x18005b229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b22e  mov     esi, 1
0x18005b233  test    eax, eax
0x18005b235  js      loc_18005B3A9
0x18005b23b  lea     eax, [rsi+14h]
0x18005b23e  mov     [rsp+60h+var_40], esi
0x18005b242  mov     word ptr [rbp+pvar], ax
0x18005b246  lea     r8, [rbp+pvar]
0x18005b24a  mov     rax, [rdi]
0x18005b24d  lea     rdx, PKEY_Media_Duration
0x18005b254  xor     r9d, r9d
0x18005b257  mov     rcx, rdi
0x18005b25a  mov     rax, [rax+28h]
0x18005b25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b263  mov     ebx, eax
0x18005b265  test    eax, eax
0x18005b267  jns     loc_18005B2FE
0x18005b26d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b274  test    rcx, rcx
0x18005b277  jnz     short loc_18005B2C0
0x18005b279  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b280  nop     dword ptr [rax+rax+00h]
0x18005b285  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b28c  mov     rcx, rax
0x18005b28f  test    rax, rax
0x18005b292  jz      short loc_18005B2B2
0x18005b294  mov     rax, [rax]
0x18005b297  mov     edx, 7F0h
0x18005b29c  mov     rax, [rax+8]
0x18005b2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2a5  test    eax, eax
0x18005b2a7  jz      short loc_18005B2B2
0x18005b2a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b2b0  jmp     short loc_18005B2C0
0x18005b2b2  lea     rcx, qword_1800DBF70; this
0x18005b2b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b2c0  cmp     [rcx+8], r12b
0x18005b2c4  jz      short loc_18005B2E7
0x18005b2c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b2cb  cmp     [rax+7CCh], ebx
0x18005b2d1  jz      short loc_18005B2E7
0x18005b2d3  mov     r9d, ebx; int
0x18005b2d6  mov     r8d, 725h; int
0x18005b2dc  mov     rdx, r13; char *
0x18005b2df  mov     rcx, rax; this
0x18005b2e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b2e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b2ee  jb      loc_18005BB45
0x18005b2f4  mov     edx, 0A3h
0x18005b2f9  jmp     loc_18005BB27
0x18005b2fe  lea     rcx, [rbp+pvar]; pvar
0x18005b302  call    cs:__imp_PropVariantClear
0x18005b309  nop     dword ptr [rax+rax+00h]
0x18005b30e  mov     ebx, eax
0x18005b310  test    eax, eax
0x18005b312  jns     loc_18005B3A9
0x18005b318  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b31f  test    rcx, rcx
0x18005b322  jnz     short loc_18005B36B
0x18005b324  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b32b  nop     dword ptr [rax+rax+00h]
0x18005b330  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b337  mov     rcx, rax
0x18005b33a  test    rax, rax
0x18005b33d  jz      short loc_18005B35D
0x18005b33f  mov     rax, [rax]
0x18005b342  mov     edx, 7F0h
0x18005b347  mov     rax, [rax+8]
0x18005b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b350  test    eax, eax
0x18005b352  jz      short loc_18005B35D
0x18005b354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b35b  jmp     short loc_18005B36B
0x18005b35d  lea     rcx, qword_1800DBF70; this
0x18005b364  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b36b  cmp     [rcx+8], r12b
0x18005b36f  jz      short loc_18005B392
0x18005b371  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b376  cmp     [rax+7CCh], ebx
0x18005b37c  jz      short loc_18005B392
0x18005b37e  mov     r9d, ebx; int
0x18005b381  mov     r8d, 726h; int
0x18005b387  mov     rdx, r13; char *
0x18005b38a  mov     rcx, rax; this
0x18005b38d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b392  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b399  jb      loc_18005BB45
0x18005b39f  mov     edx, 0A4h
0x18005b3a4  jmp     loc_18005BB27
0x18005b3a9  mov     r14d, r12d
0x18005b3ac  cmp     r14d, [rbp+arg_10]
0x18005b3b0  jnb     loc_18005B556
0x18005b3b6  mov     rax, [r15]
0x18005b3b9  lea     r9, [rbp+arg_8]
0x18005b3bd  lea     r8, [rbp+arg_18]
0x18005b3c1  mov     [rbp+arg_8], r12
0x18005b3c5  mov     edx, r14d
0x18005b3c8  mov     rcx, r15
0x18005b3cb  mov     rax, [rax+110h]
0x18005b3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3d7  mov     ebx, eax
0x18005b3d9  test    eax, eax
0x18005b3db  js      loc_18005B4A2
0x18005b3e1  cmp     [rbp+arg_18], r12d
0x18005b3e5  jz      short loc_18005B403
0x18005b3e7  mov     rax, [rdi]
0x18005b3ea  mov     rcx, rdi
0x18005b3ed  mov     rdx, [rbp+arg_8]
0x18005b3f1  mov     rax, [rax+0D0h]
0x18005b3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3fd  mov     ebx, eax
0x18005b3ff  test    eax, eax
0x18005b401  js      short loc_18005B411
0x18005b403  lea     rcx, [rbp+arg_8]
0x18005b407  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18005b40c  add     r14d, esi
0x18005b40f  jmp     short loc_18005B3AC
0x18005b411  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b418  test    rcx, rcx
0x18005b41b  jnz     short loc_18005B464
0x18005b41d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b424  nop     dword ptr [rax+rax+00h]
0x18005b429  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b430  mov     rcx, rax
0x18005b433  test    rax, rax
0x18005b436  jz      short loc_18005B456
0x18005b438  mov     rax, [rax]
0x18005b43b  mov     edx, 7F0h
0x18005b440  mov     rax, [rax+8]
0x18005b444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b449  test    eax, eax
0x18005b44b  jz      short loc_18005B456
0x18005b44d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b454  jmp     short loc_18005B464
0x18005b456  lea     rcx, qword_1800DBF70; this
0x18005b45d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b464  cmp     [rcx+8], r12b
0x18005b468  jz      short loc_18005B48B
0x18005b46a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b46f  cmp     [rax+7CCh], ebx
0x18005b475  jz      short loc_18005B48B
0x18005b477  mov     r9d, ebx; int
0x18005b47a  mov     r8d, 733h; int
0x18005b480  mov     rdx, r13; char *
0x18005b483  mov     rcx, rax; this
0x18005b486  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b48b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b492  jb      loc_18005B548
0x18005b498  mov     edx, 0A6h
0x18005b49d  jmp     loc_18005B52A
0x18005b4a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4a9  test    rcx, rcx
0x18005b4ac  jnz     short loc_18005B4F5
0x18005b4ae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b4b5  nop     dword ptr [rax+rax+00h]
0x18005b4ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4c1  mov     rcx, rax
0x18005b4c4  test    rax, rax
0x18005b4c7  jz      short loc_18005B4E7
0x18005b4c9  mov     rax, [rax]
0x18005b4cc  mov     edx, 7F0h
0x18005b4d1  mov     rax, [rax+8]
0x18005b4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4da  test    eax, eax
0x18005b4dc  jz      short loc_18005B4E7
0x18005b4de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4e5  jmp     short loc_18005B4F5
0x18005b4e7  lea     rcx, qword_1800DBF70; this
0x18005b4ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4f5  cmp     [rcx+8], r12b
0x18005b4f9  jz      short loc_18005B51C
0x18005b4fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b500  cmp     [rax+7CCh], ebx
0x18005b506  jz      short loc_18005B51C
0x18005b508  mov     r9d, ebx; int
0x18005b50b  mov     r8d, 72Fh; int
0x18005b511  mov     rdx, r13; char *
0x18005b514  mov     rcx, rax; this
0x18005b517  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b51c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b523  jb      short loc_18005B548
0x18005b525  mov     edx, 0A5h
0x18005b52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b531  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005b538  mov     r9, rdi
0x18005b53b  mov     [rsp+60h+var_40], ebx
0x18005b53f  mov     rcx, [rcx+10h]
0x18005b543  call    WPP_SF_qD
0x18005b548  lea     rcx, [rbp+arg_8]
0x18005b54c  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18005b551  jmp     loc_18005BB45
0x18005b556  mov     r14d, 13h
0x18005b55c  cmp     [rdi+384h], r12d
0x18005b563  jz      loc_18005B717
0x18005b569  lea     rcx, [rdi+30h]
0x18005b56d  lea     r9, [rbp+var_30]
0x18005b571  lea     r8, [rbp+arg_8]
0x18005b575  lea     rdx, PKEY_Audio_EncodingBitrate
0x18005b57c  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18005b581  test    eax, eax
0x18005b583  jnz     loc_18005B717
0x18005b589  mov     rax, [r15]
0x18005b58c  lea     r8, [rbp+pvar+8]
0x18005b590  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x18005b597  mov     rcx, r15
0x18005b59a  mov     rax, [rax+38h]
0x18005b59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b5a3  test    eax, eax
0x18005b5a5  js      loc_18005B717
0x18005b5ab  mov     rax, [rdi]
0x18005b5ae  lea     r8, [rbp+pvar]
0x18005b5b2  xor     r9d, r9d
0x18005b5b5  mov     word ptr [rbp+pvar], r14w
0x18005b5ba  lea     rdx, PKEY_Audio_EncodingBitrate
0x18005b5c1  mov     [rsp+60h+var_40], esi
0x18005b5c5  mov     rcx, rdi
0x18005b5c8  mov     rax, [rax+28h]
0x18005b5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b5d1  mov     ebx, eax
0x18005b5d3  test    eax, eax
0x18005b5d5  jns     loc_18005B66C
0x18005b5db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b5e2  test    rcx, rcx
0x18005b5e5  jnz     short loc_18005B62E
0x18005b5e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b5ee  nop     dword ptr [rax+rax+00h]
0x18005b5f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b5fa  mov     rcx, rax
0x18005b5fd  test    rax, rax
  ... truncated ...
```
