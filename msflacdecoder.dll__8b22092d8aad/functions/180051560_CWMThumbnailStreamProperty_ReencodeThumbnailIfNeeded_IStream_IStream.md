# CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)

- ea: `0x180051560`
- end: `0x180051f98`
- name: `?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z`
- size: `2616`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800543d0`

## callees

- `0x1800018e4`
- `0x180001e80`
- `0x180016b18`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e18`
- `0x180039e60`
- `0x180051560`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180051769`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180051769`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005160b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005160b`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
        CWMThumbnailStreamProperty *this,
        struct IStream *a2,
        struct IStream **a3)
{
  HRESULT StreamOnHGlobal; // edi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  _BYTE v47[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v48; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v50; // [rsp+44h] [rbp-45h] BYREF
  __int64 v51; // [rsp+48h] [rbp-41h] BYREF
  __int64 v52; // [rsp+50h] [rbp-39h] BYREF
  __int64 v53; // [rsp+58h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-29h] BYREF
  __int64 v55; // [rsp+68h] [rbp-21h] BYREF
  __int64 v56; // [rsp+70h] [rbp-19h] BYREF
  __int64 v57; // [rsp+78h] [rbp-11h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-9h] BYREF
  GUID v59; // [rsp+90h] [rbp+7h] BYREF

  *a3 = 0;
  ppv = 0;
  v53 = 0;
  v51 = 0;
  v57 = 0;
  v52 = 0;
  v59 = GUID_WICPixelFormat24bppRGB;
  v48 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v56 = 0;
  v55 = 0;
  v50 = 0;
  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v47,
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
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          727,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 66;
    goto LABEL_154;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
                      ppv,
                      a2,
                      &GUID_VendorMicrosoft,
                      0,
                      &v53);
  if ( StreamOnHGlobal < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v11 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v11,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          729,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 67;
    goto LABEL_154;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v53 + 40LL))(v53, &Buf1);
  if ( StreamOnHGlobal < 0 )
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v13 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v13,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          731,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 68;
    goto LABEL_154;
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  if ( StreamOnHGlobal < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v14 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v15 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v15,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          733,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 69;
    goto LABEL_154;
  }
  if ( !memcmp_0(&Buf1, &GUID_ContainerFormatJpeg, 0x10u) )
  {
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( *((_DWORD *)v39 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v39,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            788,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 81;
      goto LABEL_154;
    }
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, _QWORD, _QWORD))a2->lpVtbl->CopyTo)(
                        a2,
                        *a3,
                        -1,
                        0,
                        0);
    if ( StreamOnHGlobal < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v40 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( *((_DWORD *)v41 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v41,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            789,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 82;
      goto LABEL_154;
    }
  }
  else
  {
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 104LL))(v53, 0, &v52);
    if ( StreamOnHGlobal < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v16 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v17 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v17,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            737,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 70;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v52 + 24LL))(
                        v52,
                        &v50,
                        &v49);
    if ( StreamOnHGlobal < 0 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v18 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( *((_DWORD *)v19 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v19,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            739,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 71;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(
                        ppv,
                        &GUID_ContainerFormatJpeg,
                        &GUID_VendorMicrosoft,
                        &v51);
    if ( StreamOnHGlobal < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v20 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v21 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v21,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            746,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 72;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v51 + 24LL))(v51, *a3, 2);
    if ( StreamOnHGlobal < 0 )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v22 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( *((_DWORD *)v23 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v23,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            751,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 73;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v51 + 80LL))(
                        v51,
                        &v48,
                        &v55);
    if ( StreamOnHGlobal < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( *((_DWORD *)v25 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v25,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            753,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 74;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 24LL))(v48, v55);
    if ( StreamOnHGlobal < 0 )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( *((_DWORD *)v27 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v27,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            755,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 75;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 32LL))(v48, v50, v49);
    if ( StreamOnHGlobal < 0 )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v28 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v28);
        if ( *((_DWORD *)v29 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v29,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            757,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 76;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v48 + 48LL))(v48, &v59);
    if ( StreamOnHGlobal < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v30 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext(v30);
        if ( *((_DWORD *)v31 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v31,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            770,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 77;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 88LL))(v48, v52, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v32 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v32);
        if ( *((_DWORD *)v33 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v33,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            772,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 78;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 96LL))(v48);
    if ( StreamOnHGlobal < 0 )
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v34 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( *((_DWORD *)v35 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v35,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            774,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 79;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 88LL))(v51);
    if ( StreamOnHGlobal < 0 )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext(v36);
        if ( *((_DWORD *)v37 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v37,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            776,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 80;
      goto LABEL_154;
    }
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))(*a3)->lpVtbl->Seek)(*a3, 0, 0, 0);
  if ( StreamOnHGlobal < 0 )
  {
    v42 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v42 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( *((_DWORD *)v43 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v43,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          795,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 83;
    goto LABEL_154;
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
  if ( StreamOnHGlobal >= 0 )
    goto LABEL_157;
  v44 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v44 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v44 + 8) )
  {
    v45 = CallStackTracing::GetThreadRelativeContext(v44);
    if ( *((_DWORD *)v45 + 499) != StreamOnHGlobal )
      CallStackContext::TraceFailure(v45, "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded", 801, StreamOnHGlobal);
  }
  if ( g_wppLevels )
  {
    v9 = 84;
LABEL_154:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      StreamOnHGlobal);
  }
LABEL_155:
  if ( *a3 )
  {
    ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
    *a3 = 0;
  }
LABEL_157:
  operator delete(0);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v55);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v56);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v48);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v52);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v57);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v51);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v53);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&ppv);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180051560  push    rbp
0x180051562  push    rbx
0x180051563  push    rdi
0x180051564  push    r12
0x180051566  push    r13
0x180051568  push    r14
0x18005156a  push    r15
0x18005156c  lea     rbp, [rsp-27h]
0x180051571  sub     rsp, 0B0h
0x180051578  mov     rax, cs:__security_cookie
0x18005157f  xor     rax, rsp
0x180051582  mov     [rbp+57h+var_40], rax
0x180051586  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18005158d  xor     r13d, r13d
0x180051590  mov     r12, r8
0x180051593  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x18005159a  mov     [r8], r13
0x18005159d  lea     rbx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x1800515a4  mov     r15, rdx
0x1800515a7  mov     [rbp+57h+var_80], r13
0x1800515ab  mov     r14, rcx
0x1800515ae  mov     [rbp+57h+var_88], r13
0x1800515b2  mov     r8d, 2D7h; int
0x1800515b8  mov     [rbp+57h+var_98], r13
0x1800515bc  mov     rdx, rbx; char *
0x1800515bf  mov     [rbp+57h+var_68], r13
0x1800515c3  lea     rcx, [rbp+57h+var_B0]; this
0x1800515c7  mov     [rbp+57h+var_90], r13
0x1800515cb  movdqu  [rbp+57h+var_50], xmm0
0x1800515d0  mov     [rbp+57h+var_A8], r13
0x1800515d4  movdqu  [rbp+57h+Buf1], xmm1
0x1800515d9  mov     [rbp+57h+var_70], r13
0x1800515dd  mov     [rbp+57h+var_78], r13
0x1800515e1  mov     [rbp+57h+var_9C], r13d
0x1800515e5  mov     [rbp+57h+var_A0], r13d
0x1800515e9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800515ee  lea     rax, [rbp+57h+var_80]
0x1800515f2  xor     edx, edx; pUnkOuter
0x1800515f4  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800515fb  mov     [rsp+0E0h+ppv], rax; ppv
0x180051600  lea     r8d, [r13+17h]; dwClsContext
0x180051604  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18005160b  call    cs:__imp_CoCreateInstance
0x180051611  mov     edi, eax
0x180051613  test    eax, eax
0x180051615  jns     short loc_18005166D
0x180051617  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005161e  test    rcx, rcx
0x180051621  jnz     short loc_18005162F
0x180051623  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051628  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005162f  cmp     [rcx+8], r13b
0x180051633  jz      short loc_180051656
0x180051635  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005163a  cmp     [rax+7CCh], edi
0x180051640  jz      short loc_180051656
0x180051642  mov     r9d, edi; int
0x180051645  mov     r8d, 2D7h; int
0x18005164b  mov     rdx, rbx; char *
0x18005164e  mov     rcx, rax; this
0x180051651  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051656  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005165d  jb      loc_180051F06
0x180051663  mov     edx, 42h ; 'B'
0x180051668  jmp     loc_180051EE8
0x18005166d  mov     rcx, [rbp+57h+var_80]
0x180051671  lea     rdx, [rbp+57h+var_88]
0x180051675  mov     [rsp+0E0h+ppv], rdx
0x18005167a  lea     r8, GUID_VendorMicrosoft
0x180051681  xor     r9d, r9d
0x180051684  mov     rdx, r15
0x180051687  mov     rax, [rcx]
0x18005168a  mov     rax, [rax+20h]
0x18005168e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051693  mov     edi, eax
0x180051695  test    eax, eax
0x180051697  jns     short loc_1800516EF
0x180051699  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800516a0  test    rcx, rcx
0x1800516a3  jnz     short loc_1800516B1
0x1800516a5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800516aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800516b1  cmp     [rcx+8], r13b
0x1800516b5  jz      short loc_1800516D8
0x1800516b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800516bc  cmp     [rax+7CCh], edi
0x1800516c2  jz      short loc_1800516D8
0x1800516c4  mov     r9d, edi; int
0x1800516c7  mov     r8d, 2D9h; int
0x1800516cd  mov     rdx, rbx; char *
0x1800516d0  mov     rcx, rax; this
0x1800516d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800516d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800516df  jb      loc_180051F06
0x1800516e5  mov     edx, 43h ; 'C'
0x1800516ea  jmp     loc_180051EE8
0x1800516ef  mov     rcx, [rbp+57h+var_88]
0x1800516f3  lea     rdx, [rbp+57h+Buf1]
0x1800516f7  mov     rax, [rcx]
0x1800516fa  mov     rax, [rax+28h]
0x1800516fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051703  mov     edi, eax
0x180051705  test    eax, eax
0x180051707  jns     short loc_18005175F
0x180051709  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051710  test    rcx, rcx
0x180051713  jnz     short loc_180051721
0x180051715  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005171a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051721  cmp     [rcx+8], r13b
0x180051725  jz      short loc_180051748
0x180051727  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005172c  cmp     [rax+7CCh], edi
0x180051732  jz      short loc_180051748
0x180051734  mov     r9d, edi; int
0x180051737  mov     r8d, 2DBh; int
0x18005173d  mov     rdx, rbx; char *
0x180051740  mov     rcx, rax; this
0x180051743  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051748  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005174f  jb      loc_180051F06
0x180051755  mov     edx, 44h ; 'D'
0x18005175a  jmp     loc_180051EE8
0x18005175f  mov     r8, r12; ppstm
0x180051762  mov     edx, 1; fDeleteOnRelease
0x180051767  xor     ecx, ecx; hGlobal
0x180051769  call    cs:__imp_CreateStreamOnHGlobal
0x18005176f  mov     edi, eax
0x180051771  test    eax, eax
0x180051773  jns     short loc_1800517CB
0x180051775  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005177c  test    rcx, rcx
0x18005177f  jnz     short loc_18005178D
0x180051781  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051786  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005178d  cmp     [rcx+8], r13b
0x180051791  jz      short loc_1800517B4
0x180051793  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051798  cmp     [rax+7CCh], edi
0x18005179e  jz      short loc_1800517B4
0x1800517a0  mov     r9d, edi; int
0x1800517a3  mov     r8d, 2DDh; int
0x1800517a9  mov     rdx, rbx; char *
0x1800517ac  mov     rcx, rax; this
0x1800517af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800517b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800517bb  jb      loc_180051F06
0x1800517c1  mov     edx, 45h ; 'E'
0x1800517c6  jmp     loc_180051EE8
0x1800517cb  mov     r8d, 10h; Size
0x1800517d1  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x1800517d8  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800517dc  mov     rbx, r13
0x1800517df  call    memcmp_0
0x1800517e4  test    eax, eax
0x1800517e6  jz      loc_180051D08
0x1800517ec  mov     rcx, [rbp+57h+var_88]
0x1800517f0  lea     r8, [rbp+57h+var_90]
0x1800517f4  xor     edx, edx
0x1800517f6  mov     rax, [rcx]
0x1800517f9  mov     rax, [rax+68h]
0x1800517fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051802  mov     edi, eax
0x180051804  test    eax, eax
0x180051806  jns     short loc_180051862
0x180051808  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005180f  test    rcx, rcx
0x180051812  jnz     short loc_180051820
0x180051814  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051819  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051820  cmp     [rcx+8], r13b
0x180051824  jz      short loc_18005184B
0x180051826  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005182b  cmp     [rax+7CCh], edi
0x180051831  jz      short loc_18005184B
0x180051833  mov     r9d, edi; int
0x180051836  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18005183d  mov     r8d, 2E1h; int
0x180051843  mov     rcx, rax; this
0x180051846  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005184b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051852  jb      loc_180051F06
0x180051858  mov     edx, 46h ; 'F'
0x18005185d  jmp     loc_180051EE8
0x180051862  mov     rcx, [rbp+57h+var_90]
0x180051866  lea     r8, [rbp+57h+var_A0]
0x18005186a  lea     rdx, [rbp+57h+var_9C]
0x18005186e  mov     rax, [rcx]
0x180051871  mov     rax, [rax+18h]
0x180051875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005187a  mov     edi, eax
0x18005187c  test    eax, eax
0x18005187e  jns     short loc_1800518DA
0x180051880  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051887  test    rcx, rcx
0x18005188a  jnz     short loc_180051898
0x18005188c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051891  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051898  cmp     [rcx+8], r13b
0x18005189c  jz      short loc_1800518C3
0x18005189e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800518a3  cmp     [rax+7CCh], edi
0x1800518a9  jz      short loc_1800518C3
0x1800518ab  mov     r9d, edi; int
0x1800518ae  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x1800518b5  mov     r8d, 2E3h; int
0x1800518bb  mov     rcx, rax; this
0x1800518be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800518c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800518ca  jb      loc_180051F06
0x1800518d0  mov     edx, 47h ; 'G'
0x1800518d5  jmp     loc_180051EE8
0x1800518da  mov     rcx, [rbp+57h+var_80]
0x1800518de  lea     r9, [rbp+57h+var_98]
0x1800518e2  lea     r8, GUID_VendorMicrosoft
0x1800518e9  lea     rdx, GUID_ContainerFormatJpeg
0x1800518f0  mov     rax, [rcx]
0x1800518f3  mov     rax, [rax+40h]
0x1800518f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518fc  mov     edi, eax
0x1800518fe  test    eax, eax
0x180051900  jns     short loc_18005195C
0x180051902  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051909  test    rcx, rcx
0x18005190c  jnz     short loc_18005191A
0x18005190e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051913  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005191a  cmp     [rcx+8], r13b
0x18005191e  jz      short loc_180051945
0x180051920  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051925  cmp     [rax+7CCh], edi
0x18005192b  jz      short loc_180051945
0x18005192d  mov     r9d, edi; int
0x180051930  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x180051937  mov     r8d, 2EAh; int
0x18005193d  mov     rcx, rax; this
0x180051940  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051945  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005194c  jb      loc_180051F06
0x180051952  mov     edx, 48h ; 'H'
0x180051957  jmp     loc_180051EE8
0x18005195c  mov     rcx, [rbp+57h+var_98]
0x180051960  mov     r8d, 2
0x180051966  mov     rdx, [r12]
0x18005196a  mov     rax, [rcx]
0x18005196d  mov     rax, [rax+18h]
0x180051971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051976  mov     edi, eax
0x180051978  test    eax, eax
0x18005197a  jns     short loc_1800519D6
0x18005197c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051983  test    rcx, rcx
0x180051986  jnz     short loc_180051994
0x180051988  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005198d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051994  cmp     [rcx+8], r13b
0x180051998  jz      short loc_1800519BF
0x18005199a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005199f  cmp     [rax+7CCh], edi
0x1800519a5  jz      short loc_1800519BF
0x1800519a7  mov     r9d, edi; int
0x1800519aa  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x1800519b1  mov     r8d, 2EFh; int
0x1800519b7  mov     rcx, rax; this
0x1800519ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800519bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800519c6  jb      loc_180051F06
0x1800519cc  mov     edx, 49h ; 'I'
0x1800519d1  jmp     loc_180051EE8
0x1800519d6  mov     rcx, [rbp+57h+var_98]
0x1800519da  lea     r8, [rbp+57h+var_78]
0x1800519de  lea     rdx, [rbp+57h+var_A8]
0x1800519e2  mov     rax, [rcx]
0x1800519e5  mov     rax, [rax+50h]
0x1800519e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519ee  mov     edi, eax
0x1800519f0  test    eax, eax
0x1800519f2  jns     short loc_180051A4E
0x1800519f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800519fb  test    rcx, rcx
0x1800519fe  jnz     short loc_180051A0C
0x180051a00  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051a05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051a0c  cmp     [rcx+8], r13b
0x180051a10  jz      short loc_180051A37
0x180051a12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051a17  cmp     [rax+7CCh], edi
0x180051a1d  jz      short loc_180051A37
0x180051a1f  mov     r9d, edi; int
0x180051a22  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x180051a29  mov     r8d, 2F1h; int
0x180051a2f  mov     rcx, rax; this
0x180051a32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051a37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051a3e  jb      loc_180051F06
0x180051a44  mov     edx, 4Ah ; 'J'
0x180051a49  jmp     loc_180051EE8
0x180051a4e  mov     rcx, [rbp+57h+var_A8]
0x180051a52  mov     rdx, [rbp+57h+var_78]
0x180051a56  mov     rax, [rcx]
  ... truncated ...
```
