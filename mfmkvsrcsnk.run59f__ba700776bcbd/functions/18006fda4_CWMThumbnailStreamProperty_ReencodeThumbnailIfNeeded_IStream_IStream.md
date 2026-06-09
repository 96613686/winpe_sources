# CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)

- ea: `0x18006fda4`
- end: `0x180070c91`
- name: `?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z`
- size: `3821`
- prototype: `int(CWMThumbnailStreamProperty *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073280`

## callees

- `0x180001ff0`
- `0x180002400`
- `0x1800036f9`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800516a4`
- `0x18006fda4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fe4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fe4f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180070070`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180070070`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fe71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ff32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ffe1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007021b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800702dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007044c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800704ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800705b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007071e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800707cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007087c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070933`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800709f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070aa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070b60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fe71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ff32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ffe1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007021b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800702dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007044c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800704ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800705b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007071e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800707cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007087c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070933`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800709f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070aa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070b60`

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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v17 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v23 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v29 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v101 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v107 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v35 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v41 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v47 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v53 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v59 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v65 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v71 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v77 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v83 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v89 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v95 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v113 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v119 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
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
0x18006fda4  push    rbp
0x18006fda6  push    rbx
0x18006fda7  push    rdi
0x18006fda8  push    r12
0x18006fdaa  push    r13
0x18006fdac  push    r14
0x18006fdae  push    r15
0x18006fdb0  lea     rbp, [rsp-27h]
0x18006fdb5  sub     rsp, 0B0h
0x18006fdbc  mov     rax, cs:__security_cookie
0x18006fdc3  xor     rax, rsp
0x18006fdc6  mov     [rbp+57h+var_40], rax
0x18006fdca  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006fdd1  xor     r13d, r13d
0x18006fdd4  mov     r12, r8
0x18006fdd7  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x18006fdde  mov     [r8], r13
0x18006fde1  lea     rbx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18006fde8  mov     r15, rdx
0x18006fdeb  mov     [rbp+57h+var_80], r13
0x18006fdef  mov     r14, rcx
0x18006fdf2  mov     [rbp+57h+var_88], r13
0x18006fdf6  mov     r8d, 2D7h; int
0x18006fdfc  mov     [rbp+57h+var_98], r13
0x18006fe00  mov     rdx, rbx; char *
0x18006fe03  mov     [rbp+57h+var_68], r13
0x18006fe07  lea     rcx, [rbp+57h+var_B0]; this
0x18006fe0b  mov     [rbp+57h+var_90], r13
0x18006fe0f  movdqu  [rbp+57h+var_50], xmm0
0x18006fe14  mov     [rbp+57h+var_A8], r13
0x18006fe18  movdqu  [rbp+57h+Buf1], xmm1
0x18006fe1d  mov     [rbp+57h+var_70], r13
0x18006fe21  mov     [rbp+57h+var_78], r13
0x18006fe25  mov     [rbp+57h+var_9C], r13d
0x18006fe29  mov     [rbp+57h+var_A0], r13d
0x18006fe2d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006fe32  lea     rax, [rbp+57h+var_80]
0x18006fe36  xor     edx, edx; pUnkOuter
0x18006fe38  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18006fe3f  mov     [rsp+0E0h+ppv], rax; ppv
0x18006fe44  lea     r8d, [r13+17h]; dwClsContext
0x18006fe48  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18006fe4f  call    cs:__imp_CoCreateInstance
0x18006fe56  nop     dword ptr [rax+rax+00h]
0x18006fe5b  mov     edi, eax
0x18006fe5d  test    eax, eax
0x18006fe5f  jns     loc_18006FEF6
0x18006fe65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe6c  test    rcx, rcx
0x18006fe6f  jnz     short loc_18006FEB8
0x18006fe71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fe78  nop     dword ptr [rax+rax+00h]
0x18006fe7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe84  mov     rcx, rax
0x18006fe87  test    rax, rax
0x18006fe8a  jz      short loc_18006FEAA
0x18006fe8c  mov     rax, [rax]
0x18006fe8f  mov     edx, 7F0h
0x18006fe94  mov     rax, [rax+8]
0x18006fe98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe9d  test    eax, eax
0x18006fe9f  jz      short loc_18006FEAA
0x18006fea1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fea8  jmp     short loc_18006FEB8
0x18006feaa  lea     rcx, qword_1800DBF70; this
0x18006feb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006feb8  cmp     [rcx+8], r13b
0x18006febc  jz      short loc_18006FEDF
0x18006febe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fec3  cmp     [rax+7CCh], edi
0x18006fec9  jz      short loc_18006FEDF
0x18006fecb  mov     r9d, edi; int
0x18006fece  mov     r8d, 2D7h; int
0x18006fed4  mov     rdx, rbx; char *
0x18006fed7  mov     rcx, rax; this
0x18006feda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fedf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fee6  jb      loc_180070BFE
0x18006feec  mov     edx, 42h ; 'B'
0x18006fef1  jmp     loc_180070BE0
0x18006fef6  mov     rcx, [rbp+57h+var_80]
0x18006fefa  lea     rdx, [rbp+57h+var_88]
0x18006fefe  mov     [rsp+0E0h+ppv], rdx
0x18006ff03  lea     r8, GUID_VendorMicrosoft
0x18006ff0a  xor     r9d, r9d
0x18006ff0d  mov     rdx, r15
0x18006ff10  mov     rax, [rcx]
0x18006ff13  mov     rax, [rax+20h]
0x18006ff17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff1c  mov     edi, eax
0x18006ff1e  test    eax, eax
0x18006ff20  jns     loc_18006FFB7
0x18006ff26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff2d  test    rcx, rcx
0x18006ff30  jnz     short loc_18006FF79
0x18006ff32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ff39  nop     dword ptr [rax+rax+00h]
0x18006ff3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff45  mov     rcx, rax
0x18006ff48  test    rax, rax
0x18006ff4b  jz      short loc_18006FF6B
0x18006ff4d  mov     rax, [rax]
0x18006ff50  mov     edx, 7F0h
0x18006ff55  mov     rax, [rax+8]
0x18006ff59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff5e  test    eax, eax
0x18006ff60  jz      short loc_18006FF6B
0x18006ff62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff69  jmp     short loc_18006FF79
0x18006ff6b  lea     rcx, qword_1800DBF70; this
0x18006ff72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff79  cmp     [rcx+8], r13b
0x18006ff7d  jz      short loc_18006FFA0
0x18006ff7f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ff84  cmp     [rax+7CCh], edi
0x18006ff8a  jz      short loc_18006FFA0
0x18006ff8c  mov     r9d, edi; int
0x18006ff8f  mov     r8d, 2D9h; int
0x18006ff95  mov     rdx, rbx; char *
0x18006ff98  mov     rcx, rax; this
0x18006ff9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ffa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ffa7  jb      loc_180070BFE
0x18006ffad  mov     edx, 43h ; 'C'
0x18006ffb2  jmp     loc_180070BE0
0x18006ffb7  mov     rcx, [rbp+57h+var_88]
0x18006ffbb  lea     rdx, [rbp+57h+Buf1]
0x18006ffbf  mov     rax, [rcx]
0x18006ffc2  mov     rax, [rax+28h]
0x18006ffc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ffcb  mov     edi, eax
0x18006ffcd  test    eax, eax
0x18006ffcf  jns     loc_180070066
0x18006ffd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ffdc  test    rcx, rcx
0x18006ffdf  jnz     short loc_180070028
0x18006ffe1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ffe8  nop     dword ptr [rax+rax+00h]
0x18006ffed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fff4  mov     rcx, rax
0x18006fff7  test    rax, rax
0x18006fffa  jz      short loc_18007001A
0x18006fffc  mov     rax, [rax]
0x18006ffff  mov     edx, 7F0h
0x180070004  mov     rax, [rax+8]
0x180070008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007000d  test    eax, eax
0x18007000f  jz      short loc_18007001A
0x180070011  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070018  jmp     short loc_180070028
0x18007001a  lea     rcx, qword_1800DBF70; this
0x180070021  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070028  cmp     [rcx+8], r13b
0x18007002c  jz      short loc_18007004F
0x18007002e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070033  cmp     [rax+7CCh], edi
0x180070039  jz      short loc_18007004F
0x18007003b  mov     r9d, edi; int
0x18007003e  mov     r8d, 2DBh; int
0x180070044  mov     rdx, rbx; char *
0x180070047  mov     rcx, rax; this
0x18007004a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007004f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070056  jb      loc_180070BFE
0x18007005c  mov     edx, 44h ; 'D'
0x180070061  jmp     loc_180070BE0
0x180070066  mov     r8, r12; ppstm
0x180070069  mov     edx, 1; fDeleteOnRelease
0x18007006e  xor     ecx, ecx; hGlobal
0x180070070  call    cs:__imp_CreateStreamOnHGlobal
0x180070077  nop     dword ptr [rax+rax+00h]
0x18007007c  mov     edi, eax
0x18007007e  test    eax, eax
0x180070080  jns     loc_180070117
0x180070086  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007008d  test    rcx, rcx
0x180070090  jnz     short loc_1800700D9
0x180070092  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070099  nop     dword ptr [rax+rax+00h]
0x18007009e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800700a5  mov     rcx, rax
0x1800700a8  test    rax, rax
0x1800700ab  jz      short loc_1800700CB
0x1800700ad  mov     rax, [rax]
0x1800700b0  mov     edx, 7F0h
0x1800700b5  mov     rax, [rax+8]
0x1800700b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700be  test    eax, eax
0x1800700c0  jz      short loc_1800700CB
0x1800700c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800700c9  jmp     short loc_1800700D9
0x1800700cb  lea     rcx, qword_1800DBF70; this
0x1800700d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800700d9  cmp     [rcx+8], r13b
0x1800700dd  jz      short loc_180070100
0x1800700df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800700e4  cmp     [rax+7CCh], edi
0x1800700ea  jz      short loc_180070100
0x1800700ec  mov     r9d, edi; int
0x1800700ef  mov     r8d, 2DDh; int
0x1800700f5  mov     rdx, rbx; char *
0x1800700f8  mov     rcx, rax; this
0x1800700fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070100  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070107  jb      loc_180070BFE
0x18007010d  mov     edx, 45h ; 'E'
0x180070112  jmp     loc_180070BE0
0x180070117  mov     r8d, 10h; Size
0x18007011d  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x180070124  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180070128  mov     rbx, r13
0x18007012b  call    memcmp_0
0x180070130  test    eax, eax
0x180070132  jz      loc_180070905
0x180070138  mov     rcx, [rbp+57h+var_88]
0x18007013c  lea     r8, [rbp+57h+var_90]
0x180070140  xor     edx, edx
0x180070142  mov     rax, [rcx]
0x180070145  mov     rax, [rax+68h]
0x180070149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007014e  mov     edi, eax
0x180070150  test    eax, eax
0x180070152  jns     loc_1800701ED
0x180070158  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007015f  test    rcx, rcx
0x180070162  jnz     short loc_1800701AB
0x180070164  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007016b  nop     dword ptr [rax+rax+00h]
0x180070170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070177  mov     rcx, rax
0x18007017a  test    rax, rax
0x18007017d  jz      short loc_18007019D
0x18007017f  mov     rax, [rax]
0x180070182  mov     edx, 7F0h
0x180070187  mov     rax, [rax+8]
0x18007018b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070190  test    eax, eax
0x180070192  jz      short loc_18007019D
0x180070194  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007019b  jmp     short loc_1800701AB
0x18007019d  lea     rcx, qword_1800DBF70; this
0x1800701a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800701ab  cmp     [rcx+8], r13b
0x1800701af  jz      short loc_1800701D6
0x1800701b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800701b6  cmp     [rax+7CCh], edi
0x1800701bc  jz      short loc_1800701D6
0x1800701be  mov     r9d, edi; int
0x1800701c1  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x1800701c8  mov     r8d, 2E1h; int
0x1800701ce  mov     rcx, rax; this
0x1800701d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800701d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800701dd  jb      loc_180070BFE
0x1800701e3  mov     edx, 46h ; 'F'
0x1800701e8  jmp     loc_180070BE0
0x1800701ed  mov     rcx, [rbp+57h+var_90]
0x1800701f1  lea     r8, [rbp+57h+var_A0]
0x1800701f5  lea     rdx, [rbp+57h+var_9C]
0x1800701f9  mov     rax, [rcx]
0x1800701fc  mov     rax, [rax+18h]
0x180070200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070205  mov     edi, eax
0x180070207  test    eax, eax
0x180070209  jns     loc_1800702A4
0x18007020f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070216  test    rcx, rcx
0x180070219  jnz     short loc_180070262
0x18007021b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070222  nop     dword ptr [rax+rax+00h]
0x180070227  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007022e  mov     rcx, rax
0x180070231  test    rax, rax
0x180070234  jz      short loc_180070254
0x180070236  mov     rax, [rax]
0x180070239  mov     edx, 7F0h
0x18007023e  mov     rax, [rax+8]
0x180070242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070247  test    eax, eax
0x180070249  jz      short loc_180070254
0x18007024b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070252  jmp     short loc_180070262
0x180070254  lea     rcx, qword_1800DBF70; this
0x18007025b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070262  cmp     [rcx+8], r13b
0x180070266  jz      short loc_18007028D
0x180070268  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007026d  cmp     [rax+7CCh], edi
0x180070273  jz      short loc_18007028D
0x180070275  mov     r9d, edi; int
0x180070278  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18007027f  mov     r8d, 2E3h; int
0x180070285  mov     rcx, rax; this
0x180070288  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007028d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070294  jb      loc_180070BFE
0x18007029a  mov     edx, 47h ; 'G'
0x18007029f  jmp     loc_180070BE0
0x1800702a4  mov     rcx, [rbp+57h+var_80]
0x1800702a8  lea     r9, [rbp+57h+var_98]
  ... truncated ...
```
