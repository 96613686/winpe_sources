# CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)

- ea: `0x18006cf30`
- end: `0x18006dd9e`
- name: `?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z`
- size: `3694`
- prototype: `int(CWMThumbnailStreamProperty *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070200`

## callees

- `0x180001fd0`
- `0x1800023e0`
- `0x1800036b9`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004f47c`
- `0x18006cf30`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006cfdb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006cfdb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006d1e4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006d1e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cff7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d15b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d37d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d438`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d4eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d59c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d649`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d6f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d7a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d8ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d9a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006da59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006db11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006dbc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006dc74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006cff7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d15b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d37d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d438`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d4eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d59c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d649`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d6f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d7a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d8ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d9a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006da59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006db11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006dbc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006dc74`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
        CWMThumbnailStreamProperty *this,
        struct IStream *a2,
        struct IStream **a3)
{
  __int64 v6; // rdx
  HRESULT StreamOnHGlobal; // edi
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
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 *v101; // rcx
  CallStackTracing *v102; // rax
  struct CallStackContext *v103; // rax
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 *v107; // rcx
  CallStackTracing *v108; // rax
  struct CallStackContext *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 *v113; // rcx
  CallStackTracing *v114; // rax
  struct CallStackContext *v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 *v119; // rcx
  CallStackTracing *v120; // rax
  struct CallStackContext *v121; // rax
  _BYTE v123[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v124; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v125; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v126; // [rsp+44h] [rbp-45h] BYREF
  __int64 v127; // [rsp+48h] [rbp-41h] BYREF
  __int64 v128; // [rsp+50h] [rbp-39h] BYREF
  __int64 v129; // [rsp+58h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-29h] BYREF
  __int64 v131; // [rsp+68h] [rbp-21h] BYREF
  __int64 v132; // [rsp+70h] [rbp-19h] BYREF
  __int64 v133; // [rsp+78h] [rbp-11h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-9h] BYREF
  GUID v135; // [rsp+90h] [rbp+7h] BYREF

  *a3 = 0;
  ppv = 0;
  v129 = 0;
  v127 = 0;
  v133 = 0;
  v128 = 0;
  v135 = GUID_WICPixelFormat24bppRGB;
  v124 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v132 = 0;
  v131 = 0;
  v126 = 0;
  v125 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v123,
    "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
    727);
  StreamOnHGlobal = CoCreateInstance(
                      &CLSID_WICImagingFactory2,
                      0,
                      0x17u,
                      &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                      &ppv);
  if ( StreamOnHGlobal < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          727,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_212;
    v13 = 66;
    goto LABEL_211;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
                      ppv,
                      a2,
                      &GUID_VendorMicrosoft,
                      0,
                      &v129);
  if ( StreamOnHGlobal < 0 )
  {
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
      if ( *((_DWORD *)v19 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v19,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          729,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_212;
    v13 = 67;
    goto LABEL_211;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v129 + 40LL))(v129, &Buf1);
  if ( StreamOnHGlobal < 0 )
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
      if ( *((_DWORD *)v25 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v25,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          731,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_212;
    v13 = 68;
    goto LABEL_211;
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  if ( StreamOnHGlobal < 0 )
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
      if ( *((_DWORD *)v31 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v31,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          733,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_212;
    v13 = 69;
    goto LABEL_211;
  }
  if ( !memcmp_0(&Buf1, &GUID_ContainerFormatJpeg, 0x10u) )
  {
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v101 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v102 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v98, v99, v100);
        CallStackTracing::s_wpInstance = v102;
        if ( v102 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v102 + 8LL))(v102, 2032) )
        {
          v101 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v101 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v101 + 8) )
      {
        v103 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v101);
        if ( *((_DWORD *)v103 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v103,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            788,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 81;
      goto LABEL_211;
    }
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, _QWORD, _QWORD))a2->lpVtbl->CopyTo)(
                        a2,
                        *a3,
                        -1,
                        0,
                        0);
    if ( StreamOnHGlobal < 0 )
    {
      v107 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v104, v105, v106);
        CallStackTracing::s_wpInstance = v108;
        if ( v108 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(v108, 2032) )
        {
          v107 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v107 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v107 + 8) )
      {
        v109 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v107);
        if ( *((_DWORD *)v109 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v109,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            789,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 82;
      goto LABEL_211;
    }
  }
  else
  {
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v129 + 104LL))(v129, 0, &v128);
    if ( StreamOnHGlobal < 0 )
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
        if ( *((_DWORD *)v37 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v37,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            737,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 70;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v128 + 24LL))(
                        v128,
                        &v126,
                        &v125);
    if ( StreamOnHGlobal < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v43,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            739,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 71;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(
                        ppv,
                        &GUID_ContainerFormatJpeg,
                        &GUID_VendorMicrosoft,
                        &v127);
    if ( StreamOnHGlobal < 0 )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v47 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v49 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v49,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            746,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 72;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v127 + 24LL))(v127, *a3, 2);
    if ( StreamOnHGlobal < 0 )
    {
      v53 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
        CallStackTracing::s_wpInstance = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
        {
          v53 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v53 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v53 + 8) )
      {
        v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
        if ( *((_DWORD *)v55 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v55,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            751,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 73;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v127 + 80LL))(
                        v127,
                        &v124,
                        &v131);
    if ( StreamOnHGlobal < 0 )
    {
      v59 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v61,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            753,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 74;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v124 + 24LL))(v124, v131);
    if ( StreamOnHGlobal < 0 )
    {
      v65 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v65 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v65 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v65 + 8) )
      {
        v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
        if ( *((_DWORD *)v67 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v67,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            755,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 75;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v124 + 32LL))(v124, v126, v125);
    if ( StreamOnHGlobal < 0 )
    {
      v71 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
        CallStackTracing::s_wpInstance = v72;
        if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
        {
          v71 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v71 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v71 + 8) )
      {
        v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
        if ( *((_DWORD *)v73 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v73,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            757,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 76;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v124 + 48LL))(v124, &v135);
    if ( StreamOnHGlobal < 0 )
    {
      v77 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75, v76);
        CallStackTracing::s_wpInstance = v78;
        if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
        {
          v77 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v77 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
        if ( *((_DWORD *)v79 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v79,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            770,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 77;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v124 + 88LL))(v124, v128, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v83 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v80, v81, v82);
        CallStackTracing::s_wpInstance = v84;
        if ( v84 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
        {
          v83 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v83 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v83 + 8) )
      {
        v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
        if ( *((_DWORD *)v85 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v85,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            772,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 78;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v124 + 96LL))(v124);
    if ( StreamOnHGlobal < 0 )
    {
      v89 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v86, v87, v88);
        CallStackTracing::s_wpInstance = v90;
        if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
        {
          v89 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v89 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v89 + 8) )
      {
        v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
        if ( *((_DWORD *)v91 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v91,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            774,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 79;
      goto LABEL_211;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v127 + 88LL))(v127);
    if ( StreamOnHGlobal < 0 )
    {
      v95 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v92, v93, v94);
        CallStackTracing::s_wpInstance = v96;
        if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
        {
          v95 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v95 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v95 + 8) )
      {
        v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
        if ( *((_DWORD *)v97 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v97,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            776,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_212;
      v13 = 80;
      goto LABEL_211;
    }
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))(*a3)->lpVtbl->Seek)(*a3, 0, 0, 0);
  if ( StreamOnHGlobal < 0 )
  {
    v113 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v114 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v110, v111, v112);
      CallStackTracing::s_wpInstance = v114;
      if ( v114 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v114 + 8LL))(v114, 2032) )
      {
        v113 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v113 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v113 + 8) )
    {
      v115 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v113);
      if ( *((_DWORD *)v115 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v115,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          795,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_212;
    v13 = 83;
    goto LABEL_211;
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
  if ( StreamOnHGlobal >= 0 )
    goto LABEL_214;
  v119 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v120 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v116, v117, v118);
    CallStackTracing::s_wpInstance = v120;
    if ( v120 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v120 + 8LL))(v120, 2032) )
    {
      v119 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v119 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v119 + 8) )
  {
    v121 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v119);
    if ( *((_DWORD *)v121 + 499) != StreamOnHGlobal )
      CallStackContext::TraceFailure(
        v121,
        "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
        801,
        StreamOnHGlobal);
  }
  if ( g_wppLevels )
  {
    v13 = 84;
LABEL_211:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      StreamOnHGlobal);
  }
LABEL_212:
  if ( *a3 )
  {
    ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
    *a3 = 0;
  }
LABEL_214:
  operator delete(0);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v123);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v131);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v132);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v124);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v128);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v133);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v127);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v129);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&ppv);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18006cf30  push    rbp
0x18006cf32  push    rbx
0x18006cf33  push    rdi
0x18006cf34  push    r12
0x18006cf36  push    r13
0x18006cf38  push    r14
0x18006cf3a  push    r15
0x18006cf3c  lea     rbp, [rsp-27h]
0x18006cf41  sub     rsp, 0B0h
0x18006cf48  mov     rax, cs:__security_cookie
0x18006cf4f  xor     rax, rsp
0x18006cf52  mov     [rbp+57h+var_40], rax
0x18006cf56  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006cf5d  xor     r13d, r13d
0x18006cf60  mov     r12, r8
0x18006cf63  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x18006cf6a  mov     [r8], r13
0x18006cf6d  lea     rbx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18006cf74  mov     r15, rdx
0x18006cf77  mov     [rbp+57h+var_80], r13
0x18006cf7b  mov     r14, rcx
0x18006cf7e  mov     [rbp+57h+var_88], r13
0x18006cf82  mov     r8d, 2D7h; int
0x18006cf88  mov     [rbp+57h+var_98], r13
0x18006cf8c  mov     rdx, rbx; char *
0x18006cf8f  mov     [rbp+57h+var_68], r13
0x18006cf93  lea     rcx, [rbp+57h+var_B0]; this
0x18006cf97  mov     [rbp+57h+var_90], r13
0x18006cf9b  movdqu  [rbp+57h+var_50], xmm0
0x18006cfa0  mov     [rbp+57h+var_A8], r13
0x18006cfa4  movdqu  [rbp+57h+Buf1], xmm1
0x18006cfa9  mov     [rbp+57h+var_70], r13
0x18006cfad  mov     [rbp+57h+var_78], r13
0x18006cfb1  mov     [rbp+57h+var_9C], r13d
0x18006cfb5  mov     [rbp+57h+var_A0], r13d
0x18006cfb9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006cfbe  lea     rax, [rbp+57h+var_80]
0x18006cfc2  xor     edx, edx; pUnkOuter
0x18006cfc4  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18006cfcb  mov     [rsp+0E0h+ppv], rax; ppv
0x18006cfd0  lea     r8d, [r13+17h]; dwClsContext
0x18006cfd4  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18006cfdb  call    cs:__imp_CoCreateInstance
0x18006cfe1  mov     edi, eax
0x18006cfe3  test    eax, eax
0x18006cfe5  jns     loc_18006D076
0x18006cfeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006cff2  test    rcx, rcx
0x18006cff5  jnz     short loc_18006D038
0x18006cff7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006cffd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d004  mov     rcx, rax
0x18006d007  test    rax, rax
0x18006d00a  jz      short loc_18006D02A
0x18006d00c  mov     rax, [rax]
0x18006d00f  mov     edx, 7F0h
0x18006d014  mov     rax, [rax+8]
0x18006d018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d01d  test    eax, eax
0x18006d01f  jz      short loc_18006D02A
0x18006d021  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d028  jmp     short loc_18006D038
0x18006d02a  lea     rcx, qword_1800D6F70; this
0x18006d031  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d038  cmp     [rcx+8], r13b
0x18006d03c  jz      short loc_18006D05F
0x18006d03e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d043  cmp     [rax+7CCh], edi
0x18006d049  jz      short loc_18006D05F
0x18006d04b  mov     r9d, edi; int
0x18006d04e  mov     r8d, 2D7h; int
0x18006d054  mov     rdx, rbx; char *
0x18006d057  mov     rcx, rax; this
0x18006d05a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d05f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d066  jb      loc_18006DD0C
0x18006d06c  mov     edx, 42h ; 'B'
0x18006d071  jmp     loc_18006DCEE
0x18006d076  mov     rcx, [rbp+57h+var_80]
0x18006d07a  lea     rdx, [rbp+57h+var_88]
0x18006d07e  mov     [rsp+0E0h+ppv], rdx
0x18006d083  lea     r8, GUID_VendorMicrosoft
0x18006d08a  xor     r9d, r9d
0x18006d08d  mov     rdx, r15
0x18006d090  mov     rax, [rcx]
0x18006d093  mov     rax, [rax+20h]
0x18006d097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d09c  mov     edi, eax
0x18006d09e  test    eax, eax
0x18006d0a0  jns     loc_18006D131
0x18006d0a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0ad  test    rcx, rcx
0x18006d0b0  jnz     short loc_18006D0F3
0x18006d0b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d0b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0bf  mov     rcx, rax
0x18006d0c2  test    rax, rax
0x18006d0c5  jz      short loc_18006D0E5
0x18006d0c7  mov     rax, [rax]
0x18006d0ca  mov     edx, 7F0h
0x18006d0cf  mov     rax, [rax+8]
0x18006d0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0d8  test    eax, eax
0x18006d0da  jz      short loc_18006D0E5
0x18006d0dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0e3  jmp     short loc_18006D0F3
0x18006d0e5  lea     rcx, qword_1800D6F70; this
0x18006d0ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0f3  cmp     [rcx+8], r13b
0x18006d0f7  jz      short loc_18006D11A
0x18006d0f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d0fe  cmp     [rax+7CCh], edi
0x18006d104  jz      short loc_18006D11A
0x18006d106  mov     r9d, edi; int
0x18006d109  mov     r8d, 2D9h; int
0x18006d10f  mov     rdx, rbx; char *
0x18006d112  mov     rcx, rax; this
0x18006d115  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d11a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d121  jb      loc_18006DD0C
0x18006d127  mov     edx, 43h ; 'C'
0x18006d12c  jmp     loc_18006DCEE
0x18006d131  mov     rcx, [rbp+57h+var_88]
0x18006d135  lea     rdx, [rbp+57h+Buf1]
0x18006d139  mov     rax, [rcx]
0x18006d13c  mov     rax, [rax+28h]
0x18006d140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d145  mov     edi, eax
0x18006d147  test    eax, eax
0x18006d149  jns     loc_18006D1DA
0x18006d14f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d156  test    rcx, rcx
0x18006d159  jnz     short loc_18006D19C
0x18006d15b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d161  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d168  mov     rcx, rax
0x18006d16b  test    rax, rax
0x18006d16e  jz      short loc_18006D18E
0x18006d170  mov     rax, [rax]
0x18006d173  mov     edx, 7F0h
0x18006d178  mov     rax, [rax+8]
0x18006d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d181  test    eax, eax
0x18006d183  jz      short loc_18006D18E
0x18006d185  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d18c  jmp     short loc_18006D19C
0x18006d18e  lea     rcx, qword_1800D6F70; this
0x18006d195  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d19c  cmp     [rcx+8], r13b
0x18006d1a0  jz      short loc_18006D1C3
0x18006d1a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d1a7  cmp     [rax+7CCh], edi
0x18006d1ad  jz      short loc_18006D1C3
0x18006d1af  mov     r9d, edi; int
0x18006d1b2  mov     r8d, 2DBh; int
0x18006d1b8  mov     rdx, rbx; char *
0x18006d1bb  mov     rcx, rax; this
0x18006d1be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d1c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d1ca  jb      loc_18006DD0C
0x18006d1d0  mov     edx, 44h ; 'D'
0x18006d1d5  jmp     loc_18006DCEE
0x18006d1da  mov     r8, r12; ppstm
0x18006d1dd  mov     edx, 1; fDeleteOnRelease
0x18006d1e2  xor     ecx, ecx; hGlobal
0x18006d1e4  call    cs:__imp_CreateStreamOnHGlobal
0x18006d1ea  mov     edi, eax
0x18006d1ec  test    eax, eax
0x18006d1ee  jns     loc_18006D27F
0x18006d1f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d1fb  test    rcx, rcx
0x18006d1fe  jnz     short loc_18006D241
0x18006d200  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d206  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d20d  mov     rcx, rax
0x18006d210  test    rax, rax
0x18006d213  jz      short loc_18006D233
0x18006d215  mov     rax, [rax]
0x18006d218  mov     edx, 7F0h
0x18006d21d  mov     rax, [rax+8]
0x18006d221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d226  test    eax, eax
0x18006d228  jz      short loc_18006D233
0x18006d22a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d231  jmp     short loc_18006D241
0x18006d233  lea     rcx, qword_1800D6F70; this
0x18006d23a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d241  cmp     [rcx+8], r13b
0x18006d245  jz      short loc_18006D268
0x18006d247  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d24c  cmp     [rax+7CCh], edi
0x18006d252  jz      short loc_18006D268
0x18006d254  mov     r9d, edi; int
0x18006d257  mov     r8d, 2DDh; int
0x18006d25d  mov     rdx, rbx; char *
0x18006d260  mov     rcx, rax; this
0x18006d263  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d268  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d26f  jb      loc_18006DD0C
0x18006d275  mov     edx, 45h ; 'E'
0x18006d27a  jmp     loc_18006DCEE
0x18006d27f  mov     r8d, 10h; Size
0x18006d285  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x18006d28c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18006d290  mov     rbx, r13
0x18006d293  call    memcmp_0
0x18006d298  test    eax, eax
0x18006d29a  jz      loc_18006DA2B
0x18006d2a0  mov     rcx, [rbp+57h+var_88]
0x18006d2a4  lea     r8, [rbp+57h+var_90]
0x18006d2a8  xor     edx, edx
0x18006d2aa  mov     rax, [rcx]
0x18006d2ad  mov     rax, [rax+68h]
0x18006d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2b6  mov     edi, eax
0x18006d2b8  test    eax, eax
0x18006d2ba  jns     loc_18006D34F
0x18006d2c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d2c7  test    rcx, rcx
0x18006d2ca  jnz     short loc_18006D30D
0x18006d2cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d2d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d2d9  mov     rcx, rax
0x18006d2dc  test    rax, rax
0x18006d2df  jz      short loc_18006D2FF
0x18006d2e1  mov     rax, [rax]
0x18006d2e4  mov     edx, 7F0h
0x18006d2e9  mov     rax, [rax+8]
0x18006d2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2f2  test    eax, eax
0x18006d2f4  jz      short loc_18006D2FF
0x18006d2f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d2fd  jmp     short loc_18006D30D
0x18006d2ff  lea     rcx, qword_1800D6F70; this
0x18006d306  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d30d  cmp     [rcx+8], r13b
0x18006d311  jz      short loc_18006D338
0x18006d313  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d318  cmp     [rax+7CCh], edi
0x18006d31e  jz      short loc_18006D338
0x18006d320  mov     r9d, edi; int
0x18006d323  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18006d32a  mov     r8d, 2E1h; int
0x18006d330  mov     rcx, rax; this
0x18006d333  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d338  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d33f  jb      loc_18006DD0C
0x18006d345  mov     edx, 46h ; 'F'
0x18006d34a  jmp     loc_18006DCEE
0x18006d34f  mov     rcx, [rbp+57h+var_90]
0x18006d353  lea     r8, [rbp+57h+var_A0]
0x18006d357  lea     rdx, [rbp+57h+var_9C]
0x18006d35b  mov     rax, [rcx]
0x18006d35e  mov     rax, [rax+18h]
0x18006d362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d367  mov     edi, eax
0x18006d369  test    eax, eax
0x18006d36b  jns     loc_18006D400
0x18006d371  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d378  test    rcx, rcx
0x18006d37b  jnz     short loc_18006D3BE
0x18006d37d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d383  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d38a  mov     rcx, rax
0x18006d38d  test    rax, rax
0x18006d390  jz      short loc_18006D3B0
0x18006d392  mov     rax, [rax]
0x18006d395  mov     edx, 7F0h
0x18006d39a  mov     rax, [rax+8]
0x18006d39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d3a3  test    eax, eax
0x18006d3a5  jz      short loc_18006D3B0
0x18006d3a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d3ae  jmp     short loc_18006D3BE
0x18006d3b0  lea     rcx, qword_1800D6F70; this
0x18006d3b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d3be  cmp     [rcx+8], r13b
0x18006d3c2  jz      short loc_18006D3E9
0x18006d3c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d3c9  cmp     [rax+7CCh], edi
0x18006d3cf  jz      short loc_18006D3E9
0x18006d3d1  mov     r9d, edi; int
0x18006d3d4  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18006d3db  mov     r8d, 2E3h; int
0x18006d3e1  mov     rcx, rax; this
0x18006d3e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d3e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d3f0  jb      loc_18006DD0C
0x18006d3f6  mov     edx, 47h ; 'G'
0x18006d3fb  jmp     loc_18006DCEE
0x18006d400  mov     rcx, [rbp+57h+var_80]
0x18006d404  lea     r9, [rbp+57h+var_98]
0x18006d408  lea     r8, GUID_VendorMicrosoft
0x18006d40f  lea     rdx, GUID_ContainerFormatJpeg
0x18006d416  mov     rax, [rcx]
0x18006d419  mov     rax, [rax+40h]
0x18006d41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d422  mov     edi, eax
0x18006d424  test    eax, eax
0x18006d426  jns     loc_18006D4BB
  ... truncated ...
```
