# CMFPropHandlerBase::GenerateValue(_tagpropertykey const &,tagPROPVARIANT *,CMFProperty::MF_MDACCESS *)

- ea: `0x18003bfb0`
- end: `0x18003c872`
- name: `?GenerateValue@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@PEAW4MF_MDACCESS@CMFProperty@@@Z`
- size: `2242`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *, enum CMFProperty::MF_MDACCESS *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x18003b440`
- `0x18003b5b8`
- `0x18003bb98`
- `0x18003bfb0`
- `0x18004b5f8`
- `0x18004c254`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c137`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c3b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c7c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c137`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c3b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c7c9`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::GenerateValue(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3,
        enum CMFProperty::MF_MDACCESS *a4)
{
  int Instance; // ebx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  DWORD pid; // ecx
  __int64 v26; // rax
  __int64 v27; // rax
  int (__fastcall *v28)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *); // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  PROPVARIANT *p_pvar; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  int (__fastcall *v36)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *); // rax
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  int (__fastcall *v44)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *); // rax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int (__fastcall *v51)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *); // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  CMFVideoThumbnail *v57; // [rsp+30h] [rbp-48h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT v59; // [rsp+50h] [rbp-28h] BYREF
  char v60; // [rsp+C0h] [rbp+48h] BYREF

  Instance = -1072875819;
  if ( *((_DWORD *)this + 226) )
  {
    if ( a2->pid == PKEY_ThumbnailStream.pid )
    {
      v9 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1 )
        v9 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ThumbnailStream.fmtid.Data4;
      if ( !v9 && *((_QWORD *)this + 111) )
      {
        v57 = 0;
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 824);
        Instance = CMFVideoThumbnail::CreateInstance(*((_DWORD *)this + 220), v10, (__int64 *)&v57);
        if ( Instance < 0 )
        {
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::GenerateValue", 824, Instance);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_19;
          v15 = 61;
LABEL_18:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
            this,
            Instance);
LABEL_19:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
          ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v57);
          return (unsigned int)Instance;
        }
        Instance = CMFVideoThumbnail::Generate(v57, *((IStream **)this + 111), a3);
        if ( Instance < 0 )
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
            if ( *((_DWORD *)v19 + 499) != Instance )
              CallStackContext::TraceFailure(v19, "CMFPropHandlerBase::GenerateValue", 826, Instance);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_19;
          v15 = 62;
          goto LABEL_18;
        }
        *(_DWORD *)a4 = 1;
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v57);
      }
    }
  }
  else if ( *((_DWORD *)this + 225) && a2->pid == PKEY_ImageParsingName.pid )
  {
    v20 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ImageParsingName.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ImageParsingName.fmtid.Data1 )
      v20 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ImageParsingName.fmtid.Data4;
    if ( !v20 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 832);
      Instance = CMFPropHandlerBase::GenerateAudioThumbnailHint(this, a3);
      if ( Instance < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != Instance )
            CallStackContext::TraceFailure(v24, "CMFPropHandlerBase::GenerateValue", 832, Instance);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
            this,
            Instance);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
        return (unsigned int)Instance;
      }
      *(_DWORD *)a4 = 0;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
    }
  }
  pid = a2->pid;
  if ( pid == PKEY_GPS_Latitude.pid )
  {
    v26 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_Latitude.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_Latitude.fmtid.Data1 )
      v26 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_GPS_Latitude.fmtid.Data4;
    if ( !v26 )
    {
      v27 = *(_QWORD *)this;
      memset(&v59, 0, sizeof(v59));
      v28 = *(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(v27 + 88);
      memset(&pvar, 0, sizeof(pvar));
      if ( v28(this, &PKEY_GPS_LatitudeNumerator, &v59) >= 0
        && (*(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)this + 88LL))(
             this,
             &PKEY_GPS_LatitudeDenominator,
             &pvar) >= 0 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 843);
        Instance = CMFPropHandlerBase::ConvertGPSUIntArrayIntoDoubleArray(&v59, &pvar, a3);
        if ( Instance >= 0 )
        {
          *(_DWORD *)a4 = 0;
        }
        else
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
            if ( *((_DWORD *)v32 + 499) != Instance )
              CallStackContext::TraceFailure(v32, "CMFPropHandlerBase::GenerateValue", 843, Instance);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
              this,
              Instance);
        }
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
      }
      CMFPropVariant::Clear(&pvar);
      p_pvar = &v59;
      goto LABEL_125;
    }
  }
  if ( pid == PKEY_GPS_Longitude.pid )
  {
    v34 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_Longitude.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_Longitude.fmtid.Data1 )
      v34 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_GPS_Longitude.fmtid.Data4;
    if ( !v34 )
    {
      v35 = *(_QWORD *)this;
      memset(&pvar, 0, sizeof(pvar));
      v36 = *(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(v35 + 88);
      memset(&v59, 0, sizeof(v59));
      if ( v36(this, &PKEY_GPS_LongitudeNumerator, &pvar) < 0
        || (*(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)this + 88LL))(
             this,
             &PKEY_GPS_LongitudeDenominator,
             &v59) < 0 )
      {
        goto LABEL_124;
      }
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 853);
      Instance = CMFPropHandlerBase::ConvertGPSUIntArrayIntoDoubleArray(&pvar, &v59, a3);
      if ( Instance < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != Instance )
            CallStackContext::TraceFailure(v40, "CMFPropHandlerBase::GenerateValue", 853, Instance);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_123;
        v41 = 65;
        goto LABEL_87;
      }
LABEL_122:
      *(_DWORD *)a4 = 0;
      goto LABEL_123;
    }
  }
  if ( pid == PKEY_GPS_LatitudeDecimal.pid )
  {
    v42 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_LatitudeDecimal.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_LatitudeDecimal.fmtid.Data1 )
      v42 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_GPS_LatitudeDecimal.fmtid.Data4;
    if ( !v42 )
    {
      v43 = *(_QWORD *)this;
      memset(&pvar, 0, sizeof(pvar));
      v44 = *(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(v43 + 88);
      memset(&v59, 0, sizeof(v59));
      if ( v44(this, &PKEY_GPS_Latitude, &pvar) < 0
        || (*(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)this + 88LL))(
             this,
             &PKEY_GPS_LatitudeRef,
             &v59) < 0 )
      {
        goto LABEL_124;
      }
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 864);
      Instance = CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(&v59, &pvar, L"N", a3);
      if ( Instance >= 0 )
        goto LABEL_122;
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        if ( *((_DWORD *)v48 + 499) != Instance )
          CallStackContext::TraceFailure(v48, "CMFPropHandlerBase::GenerateValue", 864, Instance);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_123;
      v41 = 66;
      goto LABEL_87;
    }
  }
  if ( pid == PKEY_GPS_LongitudeDecimal.pid )
  {
    v49 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_LongitudeDecimal.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_LongitudeDecimal.fmtid.Data1 )
      v49 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_GPS_LongitudeDecimal.fmtid.Data4;
    if ( !v49 )
    {
      v50 = *(_QWORD *)this;
      memset(&pvar, 0, sizeof(pvar));
      v51 = *(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(v50 + 88);
      memset(&v59, 0, sizeof(v59));
      if ( v51(this, &PKEY_GPS_Longitude, &pvar) < 0
        || (*(int (__fastcall **)(CMFPropHandlerBase *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)this + 88LL))(
             this,
             &PKEY_GPS_LongitudeRef,
             &v59) < 0 )
      {
        goto LABEL_124;
      }
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v60, "CMFPropHandlerBase::GenerateValue", 875);
      Instance = CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(&v59, &pvar, L"E", a3);
      if ( Instance >= 0 )
        goto LABEL_122;
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
        if ( *((_DWORD *)v55 + 499) != Instance )
          CallStackContext::TraceFailure(v55, "CMFPropHandlerBase::GenerateValue", 875, Instance);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_123;
      v41 = 67;
LABEL_87:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v41,
        &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
        this,
        Instance);
LABEL_123:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
LABEL_124:
      CMFPropVariant::Clear(&v59);
      p_pvar = &pvar;
LABEL_125:
      CMFPropVariant::Clear(p_pvar);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003bfb0  push    rbp
0x18003bfb2  push    rbx
0x18003bfb3  push    rsi
0x18003bfb4  push    rdi
0x18003bfb5  push    r12
0x18003bfb7  push    r13
0x18003bfb9  push    r14
0x18003bfbb  push    r15
0x18003bfbd  mov     rbp, rsp
0x18003bfc0  sub     rsp, 78h
0x18003bfc4  xor     r12d, r12d
0x18003bfc7  lea     r13, aCmfprophandler_15; "CMFPropHandlerBase::GenerateValue"
0x18003bfce  mov     r14, r9
0x18003bfd1  mov     r15, r8
0x18003bfd4  mov     rsi, rdx
0x18003bfd7  mov     rdi, rcx
0x18003bfda  mov     ebx, 0C00D36D5h
0x18003bfdf  cmp     [rcx+388h], r12d
0x18003bfe6  jz      loc_18003C1D4
0x18003bfec  mov     eax, cs:PKEY_ThumbnailStream.pid
0x18003bff2  cmp     [rdx+10h], eax
0x18003bff5  jnz     loc_18003C2F1
0x18003bffb  mov     rax, [rdx]
0x18003bffe  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data1
0x18003c005  jnz     short loc_18003C012
0x18003c007  mov     rax, [rdx+8]
0x18003c00b  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data4
0x18003c012  test    rax, rax
0x18003c015  jnz     loc_18003C2F1
0x18003c01b  cmp     [rcx+378h], r12
0x18003c022  jz      loc_18003C2F1
0x18003c028  mov     r8d, 338h; int
0x18003c02e  mov     [rbp+var_48], r12
0x18003c032  mov     rdx, r13; char *
0x18003c035  lea     rcx, [rbp+arg_0]; this
0x18003c039  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003c03e  mov     ecx, [rdi+370h]
0x18003c044  lea     r8, [rbp+var_48]
0x18003c048  call    ?CreateInstance@CMFVideoThumbnail@@SAJW4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAPEAV1@@Z; CMFVideoThumbnail::CreateInstance(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,CMFVideoThumbnail * *)
0x18003c04d  mov     ebx, eax
0x18003c04f  test    eax, eax
0x18003c051  jns     loc_18003C10E
0x18003c057  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c05e  test    rcx, rcx
0x18003c061  jnz     short loc_18003C0A4
0x18003c063  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c069  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c070  mov     rcx, rax
0x18003c073  test    rax, rax
0x18003c076  jz      short loc_18003C096
0x18003c078  mov     rax, [rax]
0x18003c07b  mov     edx, 7F0h
0x18003c080  mov     rax, [rax+8]
0x18003c084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c089  test    eax, eax
0x18003c08b  jz      short loc_18003C096
0x18003c08d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c094  jmp     short loc_18003C0A4
0x18003c096  lea     rcx, qword_18006EB20; this
0x18003c09d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c0a4  cmp     [rcx+8], r12b
0x18003c0a8  jz      short loc_18003C0CB
0x18003c0aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c0af  cmp     [rax+7CCh], ebx
0x18003c0b5  jz      short loc_18003C0CB
0x18003c0b7  mov     r9d, ebx; int
0x18003c0ba  mov     r8d, 338h; int
0x18003c0c0  mov     rdx, r13; char *
0x18003c0c3  mov     rcx, rax; this
0x18003c0c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c0cb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003c0d0  cmp     al, 1
0x18003c0d2  jb      short loc_18003C0F7
0x18003c0d4  mov     edx, 3Dh ; '='
0x18003c0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0e0  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003c0e7  mov     r9, rdi
0x18003c0ea  mov     [rsp+78h+var_58], ebx
0x18003c0ee  mov     rcx, [rcx+10h]
0x18003c0f2  call    WPP_SF_qd
0x18003c0f7  lea     rcx, [rbp+arg_0]; this
0x18003c0fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c100  lea     rcx, [rbp+var_48]
0x18003c104  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18003c109  jmp     loc_18003C85F
0x18003c10e  mov     rdx, [rdi+378h]; pStream
0x18003c115  mov     r8, r15; struct tagPROPVARIANT *
0x18003c118  mov     rcx, [rbp+var_48]; this
0x18003c11c  call    ?Generate@CMFVideoThumbnail@@QEAAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z; CMFVideoThumbnail::Generate(IStream *,tagPROPVARIANT *)
0x18003c121  mov     ebx, eax
0x18003c123  test    eax, eax
0x18003c125  jns     loc_18003C1B6
0x18003c12b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c132  test    rcx, rcx
0x18003c135  jnz     short loc_18003C178
0x18003c137  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c13d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c144  mov     rcx, rax
0x18003c147  test    rax, rax
0x18003c14a  jz      short loc_18003C16A
0x18003c14c  mov     rax, [rax]
0x18003c14f  mov     edx, 7F0h
0x18003c154  mov     rax, [rax+8]
0x18003c158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c15d  test    eax, eax
0x18003c15f  jz      short loc_18003C16A
0x18003c161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c168  jmp     short loc_18003C178
0x18003c16a  lea     rcx, qword_18006EB20; this
0x18003c171  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c178  cmp     [rcx+8], r12b
0x18003c17c  jz      short loc_18003C19F
0x18003c17e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c183  cmp     [rax+7CCh], ebx
0x18003c189  jz      short loc_18003C19F
0x18003c18b  mov     r9d, ebx; int
0x18003c18e  mov     r8d, 33Ah; int
0x18003c194  mov     rdx, r13; char *
0x18003c197  mov     rcx, rax; this
0x18003c19a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c19f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003c1a4  cmp     al, 1
0x18003c1a6  jb      loc_18003C0F7
0x18003c1ac  mov     edx, 3Eh ; '>'
0x18003c1b1  jmp     loc_18003C0D9
0x18003c1b6  lea     rcx, [rbp+arg_0]; this
0x18003c1ba  mov     dword ptr [r14], 1
0x18003c1c1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c1c6  lea     rcx, [rbp+var_48]
0x18003c1ca  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18003c1cf  jmp     loc_18003C2F1
0x18003c1d4  cmp     [rcx+384h], r12d
0x18003c1db  jz      loc_18003C2F1
0x18003c1e1  mov     eax, cs:PKEY_ImageParsingName.pid
0x18003c1e7  cmp     [rdx+10h], eax
0x18003c1ea  jnz     loc_18003C2F1
0x18003c1f0  mov     rax, [rdx]
0x18003c1f3  sub     rax, qword ptr cs:PKEY_ImageParsingName.fmtid.Data1
0x18003c1fa  jnz     short loc_18003C207
0x18003c1fc  mov     rax, [rdx+8]
0x18003c200  sub     rax, qword ptr cs:PKEY_ImageParsingName.fmtid.Data4
0x18003c207  test    rax, rax
0x18003c20a  jnz     loc_18003C2F1
0x18003c210  mov     r8d, 340h; int
0x18003c216  lea     rcx, [rbp+arg_0]; this
0x18003c21a  mov     rdx, r13; char *
0x18003c21d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003c222  mov     rdx, r15; struct tagPROPVARIANT *
0x18003c225  mov     rcx, rdi; this
0x18003c228  call    ?GenerateAudioThumbnailHint@CMFPropHandlerBase@@IEAAJPEAUtagPROPVARIANT@@@Z; CMFPropHandlerBase::GenerateAudioThumbnailHint(tagPROPVARIANT *)
0x18003c22d  mov     ebx, eax
0x18003c22f  test    eax, eax
0x18003c231  jns     loc_18003C2E5
0x18003c237  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c23e  test    rcx, rcx
0x18003c241  jnz     short loc_18003C284
0x18003c243  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c249  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c250  mov     rcx, rax
0x18003c253  test    rax, rax
0x18003c256  jz      short loc_18003C276
0x18003c258  mov     rax, [rax]
0x18003c25b  mov     edx, 7F0h
0x18003c260  mov     rax, [rax+8]
0x18003c264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c269  test    eax, eax
0x18003c26b  jz      short loc_18003C276
0x18003c26d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c274  jmp     short loc_18003C284
0x18003c276  lea     rcx, qword_18006EB20; this
0x18003c27d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c284  cmp     [rcx+8], r12b
0x18003c288  jz      short loc_18003C2AB
0x18003c28a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c28f  cmp     [rax+7CCh], ebx
0x18003c295  jz      short loc_18003C2AB
0x18003c297  mov     r9d, ebx; int
0x18003c29a  mov     r8d, 340h; int
0x18003c2a0  mov     rdx, r13; char *
0x18003c2a3  mov     rcx, rax; this
0x18003c2a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c2ab  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003c2b0  cmp     al, 1
0x18003c2b2  jb      short loc_18003C2D7
0x18003c2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2bb  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003c2c2  mov     edx, 3Fh ; '?'
0x18003c2c7  mov     [rsp+78h+var_58], ebx
0x18003c2cb  mov     r9, rdi
0x18003c2ce  mov     rcx, [rcx+10h]
0x18003c2d2  call    WPP_SF_qd
0x18003c2d7  lea     rcx, [rbp+arg_0]; this
0x18003c2db  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c2e0  jmp     loc_18003C85F
0x18003c2e5  lea     rcx, [rbp+arg_0]; this
0x18003c2e9  mov     [r14], r12d
0x18003c2ec  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c2f1  mov     ecx, [rsi+10h]
0x18003c2f4  cmp     ecx, cs:PKEY_GPS_Latitude.pid
0x18003c2fa  jnz     loc_18003C465
0x18003c300  mov     rax, [rsi]
0x18003c303  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data1
0x18003c30a  jnz     short loc_18003C317
0x18003c30c  mov     rax, [rsi+8]
0x18003c310  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data4
0x18003c317  test    rax, rax
0x18003c31a  jnz     loc_18003C465
0x18003c320  mov     qword ptr [rbp+var_28+10h], rax
0x18003c324  lea     r8, [rbp+var_28]
0x18003c328  mov     qword ptr [rbp+pvar+10h], rax
0x18003c32c  lea     rdx, PKEY_GPS_LatitudeNumerator
0x18003c333  mov     rax, [rdi]
0x18003c336  xorps   xmm0, xmm0
0x18003c339  xorps   xmm1, xmm1
0x18003c33c  mov     rcx, rdi
0x18003c33f  movups  xmmword ptr [rbp+var_28], xmm0
0x18003c343  mov     rax, [rax+58h]
0x18003c347  movups  xmmword ptr [rbp+pvar], xmm1
0x18003c34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c350  test    eax, eax
0x18003c352  js      loc_18003C44E
0x18003c358  mov     rax, [rdi]
0x18003c35b  lea     r8, [rbp+pvar]
0x18003c35f  lea     rdx, PKEY_GPS_LatitudeDenominator
0x18003c366  mov     rcx, rdi
0x18003c369  mov     rax, [rax+58h]
0x18003c36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c372  test    eax, eax
0x18003c374  js      loc_18003C44E
0x18003c37a  mov     esi, 34Bh
0x18003c37f  lea     rcx, [rbp+arg_0]; this
0x18003c383  mov     r8d, esi; int
0x18003c386  mov     rdx, r13; char *
0x18003c389  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003c38e  mov     r8, r15; struct tagPROPVARIANT *
0x18003c391  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x18003c395  lea     rcx, [rbp+var_28]; struct tagPROPVARIANT *
0x18003c399  call    ?ConvertGPSUIntArrayIntoDoubleArray@CMFPropHandlerBase@@CAJAEBUtagPROPVARIANT@@0PEAU2@@Z; CMFPropHandlerBase::ConvertGPSUIntArrayIntoDoubleArray(tagPROPVARIANT const &,tagPROPVARIANT const &,tagPROPVARIANT *)
0x18003c39e  mov     ebx, eax
0x18003c3a0  test    eax, eax
0x18003c3a2  jns     loc_18003C460
0x18003c3a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c3af  test    rcx, rcx
0x18003c3b2  jnz     short loc_18003C3F5
0x18003c3b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c3ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c3c1  mov     rcx, rax
0x18003c3c4  test    rax, rax
0x18003c3c7  jz      short loc_18003C3E7
0x18003c3c9  mov     rax, [rax]
0x18003c3cc  mov     edx, 7F0h
0x18003c3d1  mov     rax, [rax+8]
0x18003c3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3da  test    eax, eax
0x18003c3dc  jz      short loc_18003C3E7
0x18003c3de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c3e5  jmp     short loc_18003C3F5
0x18003c3e7  lea     rcx, qword_18006EB20; this
0x18003c3ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c3f5  cmp     [rcx+8], r12b
0x18003c3f9  jz      short loc_18003C419
0x18003c3fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c400  cmp     [rax+7CCh], ebx
0x18003c406  jz      short loc_18003C419
0x18003c408  mov     r9d, ebx; int
0x18003c40b  mov     r8d, esi; int
0x18003c40e  mov     rdx, r13; char *
0x18003c411  mov     rcx, rax; this
0x18003c414  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c419  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003c41e  cmp     al, 1
0x18003c420  jb      short loc_18003C445
0x18003c422  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c429  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003c430  mov     edx, 40h ; '@'
0x18003c435  mov     [rsp+78h+var_58], ebx
0x18003c439  mov     r9, rdi
0x18003c43c  mov     rcx, [rcx+10h]
0x18003c440  call    WPP_SF_qd
0x18003c445  lea     rcx, [rbp+arg_0]; this
0x18003c449  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c44e  lea     rcx, [rbp+pvar]; pvar
0x18003c452  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18003c457  lea     rcx, [rbp+var_28]
0x18003c45b  jmp     loc_18003C85A
0x18003c460  mov     [r14], r12d
0x18003c463  jmp     short loc_18003C445
0x18003c465  cmp     ecx, cs:PKEY_GPS_Longitude.pid
0x18003c46b  jnz     loc_18003C5BF
0x18003c471  mov     rax, [rsi]
0x18003c474  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data1
0x18003c47b  jnz     short loc_18003C488
0x18003c47d  mov     rax, [rsi+8]
0x18003c481  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data4
0x18003c488  test    rax, rax
0x18003c48b  jnz     loc_18003C5BF
0x18003c491  mov     qword ptr [rbp+pvar+10h], rax
0x18003c495  lea     r8, [rbp+pvar]
0x18003c499  mov     qword ptr [rbp+var_28+10h], rax
0x18003c49d  lea     rdx, PKEY_GPS_LongitudeNumerator
  ... truncated ...
```
