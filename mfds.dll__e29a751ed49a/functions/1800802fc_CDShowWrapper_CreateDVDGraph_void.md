# CDShowWrapper::CreateDVDGraph(void)

- ea: `0x1800802fc`
- end: `0x18008184b`
- name: `?CreateDVDGraph@CDShowWrapper@@IEAAJXZ`
- size: `5455`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180033ce0`

## callees

- `0x1800010c0`
- `0x180001170`
- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x18003221c`
- `0x180032570`
- `0x180032988`
- `0x180032a50`
- `0x180035b14`
- `0x180037a10`
- `0x18003bb18`
- `0x180047794`
- `0x18004a638`
- `0x180051ce4`
- `0x180053934`
- `0x180074160`
- `0x180074a06`
- `0x18007c8e8`
- `0x18007fc5c`
- `0x1800802fc`
- `0x180083f14`
- `0x180085fb0`
- `0x180086fcc`
- `0x180089ab0`
- `0x18008a530`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008043f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008043f`
- `MFPlat!MFCreatePathFromURL` at `0x180080761`
- `MFPlat!MFCreatePathFromURL` at `0x180080761`

## string_xrefs

- `0x18008032c`: `CDShowWrapper::CreateDVDGraph`
- `0x18008072a`: `CDShowWrapper::CreateDVDGraph`
- `0x1800807ce`: `CDShowWrapper::CreateDVDGraph`
- `0x18008085d`: `CDShowWrapper::CreateDVDGraph`
- `0x1800808c5`: `CDShowWrapper::CreateDVDGraph`
- `0x18008094f`: `CDShowWrapper::CreateDVDGraph`
- `0x1800809e0`: `CDShowWrapper::CreateDVDGraph`
- `0x180080a5a`: `CDShowWrapper::CreateDVDGraph`
- `0x180080ac1`: `CDShowWrapper::CreateDVDGraph`
- `0x180080e0e`: `CDShowWrapper::CreateDVDGraph`
- `0x180080e68`: `CDShowWrapper::CreateDVDGraph`
- `0x180080ec2`: `CDShowWrapper::CreateDVDGraph`
- `0x180080f15`: `CDShowWrapper::CreateDVDGraph`
- `0x180080fa4`: `CDShowWrapper::CreateDVDGraph`
- `0x180080ffe`: `CDShowWrapper::CreateDVDGraph`
- `0x180081058`: `CDShowWrapper::CreateDVDGraph`
- `0x1800810b2`: `CDShowWrapper::CreateDVDGraph`
- `0x180081105`: `CDShowWrapper::CreateDVDGraph`
- `0x1800811a4`: `CDShowWrapper::CreateDVDGraph`
- `0x180081216`: `CDShowWrapper::CreateDVDGraph`
- `0x18008129b`: `CDShowWrapper::CreateDVDGraph`
- `0x18008131c`: `CDShowWrapper::CreateDVDGraph`
- `0x180081391`: `CDShowWrapper::CreateDVDGraph`
- `0x18008140b`: `CDShowWrapper::CreateDVDGraph`
- `0x18008147f`: `CDShowWrapper::CreateDVDGraph`
- `0x1800814f3`: `CDShowWrapper::CreateDVDGraph`
- `0x18008169e`: `CDShowWrapper::CreateDVDGraph`
- `0x1800816f6`: `CDShowWrapper::CreateDVDGraph`
- `0x180081749`: `CDShowWrapper::CreateDVDGraph`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::CreateDVDGraph(CDShowWrapper *this)
{
  int v2; // r12d
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  __int128 v5; // xmm0
  struct IBaseFilter *v6; // rbx
  __int64 v7; // rdi
  HRESULT CustomDSSampleSink; // esi
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
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
  __int64 v22; // rax
  unsigned __int64 v23; // r11
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rax
  __int64 v29; // r11
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CGITPtr *v34; // rcx
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  int v45; // r13d
  int v46; // r15d
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  __int64 *v56; // rcx
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  CallStackTracing *v61; // rcx
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  CallStackTracing *v64; // rcx
  struct CallStackContext *v65; // rax
  CallStackTracing *v66; // rcx
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rcx
  struct CallStackContext *v69; // rax
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  struct IBaseFilter *v72; // rdx
  CallStackTracing *v73; // rcx
  struct CallStackContext *v74; // rax
  CallStackTracing *v75; // rcx
  struct CallStackContext *v76; // rax
  CallStackTracing *v77; // rcx
  struct CallStackContext *v78; // rax
  CallStackTracing *v79; // rcx
  struct CallStackContext *v80; // rax
  CallStackTracing *v81; // rcx
  struct CallStackContext *v82; // rax
  CallStackTracing *v83; // rcx
  struct CallStackContext *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // r8
  GUID *v89; // rax
  __int64 v90; // rcx
  int v91; // r8d
  int v92; // r9d
  CallStackTracing *v93; // rcx
  struct CallStackContext *v94; // rax
  struct CallStackContext *v95; // rax
  CallStackTracing *v96; // rcx
  struct CallStackContext *v97; // rax
  _BYTE v99[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct IMFCollection *v100; // [rsp+58h] [rbp-A8h] BYREF
  int (__fastcall ***v101)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v102; // [rsp+68h] [rbp-98h] BYREF
  __int64 v103; // [rsp+70h] [rbp-90h] BYREF
  __int64 v104; // [rsp+78h] [rbp-88h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v106; // [rsp+88h] [rbp-78h] BYREF
  __int64 v107; // [rsp+90h] [rbp-70h] BYREF
  __int64 v108; // [rsp+98h] [rbp-68h] BYREF
  __int64 v109; // [rsp+A0h] [rbp-60h] BYREF
  struct IPin *v110; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v112; // [rsp+B8h] [rbp-48h] BYREF
  void *v113; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v114; // [rsp+C8h] [rbp-38h] BYREF
  struct IBaseFilter *v115; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v116; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v117; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v118; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v119; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v120; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v121[34]; // [rsp+100h] [rbp+0h] BYREF
  GUID v122; // [rsp+210h] [rbp+110h] BYREF
  __int128 v123; // [rsp+220h] [rbp+120h] BYREF
  __int128 v124; // [rsp+230h] [rbp+130h]
  _QWORD v125[2]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v126[264]; // [rsp+250h] [rbp+150h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v99, "CDShowWrapper::CreateDVDGraph", 2899);
  v2 = 0;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v5 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      &v122);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
    *((_OWORD *)ThreadRelativeContext + 125) = v5;
  }
  v6 = 0;
  v106 = 0;
  v115 = 0;
  ppv = 0;
  v111 = 0;
  v117 = 0;
  v7 = 0;
  v101 = 0;
  v116 = 0;
  v114 = 0;
  v113 = 0;
  v112 = 0;
  v120 = 0;
  v109 = 0;
  v108 = 0;
  v107 = 0;
  v110 = 0;
  v119 = 0;
  v118 = 0;
  memset_0(v126, 0, 0x208u);
  v123 = 0;
  v124 = 0;
  CustomDSSampleSink = CoCreateInstance(&CLSID_DvdGraphBuilder, 0, 1u, &GUID_fcc152b6_f372_11d0_8e00_00c04fd7c08b, &ppv);
  if ( CustomDSSampleSink < 0 )
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v9 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v10 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v10, "CDShowWrapper::CreateDVDGraph", 2935, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 250;
    goto LABEL_319;
  }
  CustomDSSampleSink = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown **))(*(_QWORD *)ppv + 24LL))(ppv, &v106);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v13 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v13, "CDShowWrapper::CreateDVDGraph", 2937, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 251;
    goto LABEL_319;
  }
  CustomDSSampleSink = CGITPtr::Set(
                         (CDShowWrapper *)((char *)this + 48),
                         &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770,
                         v106);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v15 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v15, "CDShowWrapper::CreateDVDGraph", 2938, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 252;
    goto LABEL_319;
  }
  CustomDSSampleSink = CDShowWrapper::SetDolbyBinding(this);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v17 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v17, "CDShowWrapper::CreateDVDGraph", 2940, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 253;
    goto LABEL_319;
  }
  CustomDSSampleSink = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv + 32LL))(
                         ppv,
                         &IID_IEVRFilterConfig,
                         &v120);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v19 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v19, "CDShowWrapper::CreateDVDGraph", 2943, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 254;
    goto LABEL_319;
  }
  CustomDSSampleSink = StringCchCopyW(v126, 0x104u, L"file:");
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v21 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v21, "CDShowWrapper::CreateDVDGraph", 2949, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 255;
    goto LABEL_319;
  }
  v22 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
  CustomDSSampleSink = StringCchCatW(v126, v23, (const unsigned __int16 *)(v22 + 12));
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v25 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v25, "CDShowWrapper::CreateDVDGraph", 2953, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 256;
    goto LABEL_319;
  }
  if ( (int)MFCreatePathFromURL(v126, &v118) < 0 )
  {
    v28 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
    CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v29 + 40LL))(
                           v29,
                           v28,
                           28673,
                           &v123);
    if ( CustomDSSampleSink < 0 )
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
        if ( *((_DWORD *)v31 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v31, "CDShowWrapper::CreateDVDGraph", 2962, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v11 = 258;
LABEL_319:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        CustomDSSampleSink);
      goto LABEL_320;
    }
  }
  else
  {
    CustomDSSampleSink = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int128 *))(*(_QWORD *)ppv + 40LL))(
                           ppv,
                           v118,
                           28673,
                           &v123);
    if ( CustomDSSampleSink < 0 )
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
        if ( *((_DWORD *)v27 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v27, "CDShowWrapper::CreateDVDGraph", 2958, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v11 = 257;
      goto LABEL_319;
    }
  }
  CustomDSSampleSink = CDShowWrapper::SetupThreadpoolWait(this);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v33 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v33, "CDShowWrapper::CreateDVDGraph", 2969, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 259;
    goto LABEL_319;
  }
  v34 = (CGITPtr *)(*((_QWORD *)this + 1) + 204LL);
  if ( *(_DWORD *)v34 )
  {
    v100 = 0;
    CustomDSSampleSink = CGITPtr::Get(v34, &GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe, (void **)&v100);
    if ( CustomDSSampleSink < 0 )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v35 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext(v35);
        if ( *((_DWORD *)v36 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v36, "CDShowWrapper::CreateDVDGraph", 2979, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_95;
      v37 = 260;
LABEL_94:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v37,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        CustomDSSampleSink);
LABEL_95:
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v100);
      goto LABEL_320;
    }
    CustomDSSampleSink = CDShowWrapper::RegisterServiceProviders(this, v100);
    if ( CustomDSSampleSink < 0 )
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
        if ( *((_DWORD *)v39 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v39, "CDShowWrapper::CreateDVDGraph", 2980, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_95;
      v37 = 261;
      goto LABEL_94;
    }
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v100);
  }
  CustomDSSampleSink = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v106->lpVtbl[1].Release)(v106, &v111);
  if ( CustomDSSampleSink < 0 )
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
      if ( *((_DWORD *)v41 + 499) != CustomDSSampleSink )
        CallStackContext::TraceFailure(v41, "CDShowWrapper::CreateDVDGraph", 2994, CustomDSSampleSink);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v11 = 262;
    goto LABEL_319;
  }
  if ( !v111 )
  {
    v42 = CallStackTracing::s_wpInstance;
    CustomDSSampleSink = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v42 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( *((_DWORD *)v43 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v43, "CDShowWrapper::CreateDVDGraph", 2998, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_320;
    v44 = 263;
    goto LABEL_121;
  }
  v45 = 0;
  v46 = 0;
  do
  {
    ComSmartPtr<IBaseFilter>::operator=(&v101);
    if ( v109 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      v109 = 0;
    }
    if ( v108 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
      v108 = 0;
    }
    if ( v107 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
      v107 = 0;
    }
    CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v111 + 24LL))(v111, 1, &v101);
    if ( CustomDSSampleSink < 0 )
    {
      v96 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v96 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v96 + 8) )
      {
        v97 = CallStackTracing::GetThreadRelativeContext(v96);
        if ( *((_DWORD *)v97 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v97, "CDShowWrapper::CreateDVDGraph", 3011, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v11 = 264;
      goto LABEL_319;
    }
    if ( !v101 )
    {
      v93 = CallStackTracing::s_wpInstance;
      if ( v46 )
      {
        CustomDSSampleSink = -1072875845;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v93 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v93 + 8) )
        {
          v95 = CallStackTracing::GetThreadRelativeContext(v93);
          if ( *((_DWORD *)v95 + 499) != -1072875845 )
            CallStackContext::TraceFailure(v95, "CDShowWrapper::CreateDVDGraph", 3023, -1072875845);
        }
        if ( !g_wppLevels )
          goto LABEL_320;
        v11 = 266;
      }
      else
      {
        CustomDSSampleSink = -1072869756;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v93 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v93 + 8) )
        {
          v94 = CallStackTracing::GetThreadRelativeContext(v93);
          if ( *((_DWORD *)v94 + 499) != -1072869756 )
            CallStackContext::TraceFailure(v94, "CDShowWrapper::CreateDVDGraph", 3019, -1072869756);
        }
        if ( !g_wppLevels )
          goto LABEL_320;
        v11 = 265;
      }
      goto LABEL_319;
    }
    if ( !v45 && (**v101)(v101, &IID_IDvdControl2, &v112) >= 0 && v112 )
    {
      ComSmartPtr<IBaseFilter>::operator=(&v116, &v101);
      v45 = 1;
    }
    if ( v2 || (**v101)(v101, &IID_IMFVideoRenderer, &v108) < 0 || !v108 )
      goto LABEL_144;
    CustomDSSampleSink = (**v101)(v101, &IID_IMFGetService, &v109);
    if ( CustomDSSampleSink < 0 )
    {
      v59 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v59 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext(v59);
        if ( *((_DWORD *)v60 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v60, "CDShowWrapper::CreateDVDGraph", 3045, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v11 = 267;
      goto LABEL_319;
    }
    if ( !v109 )
    {
      v57 = CallStackTracing::s_wpInstance;
      CustomDSSampleSink = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v57 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext(v57);
        if ( *((_DWORD *)v58 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v58, "CDShowWrapper::CreateDVDGraph", 3049, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v44 = 268;
LABEL_121:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v44,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        -2147024882);
      goto LABEL_320;
    }
    ComSmartPtr<IBaseFilter>::operator=(&v115, &v101);
    v6 = v115;
    v104 = 0;
    v100 = 0;
    CustomDSSampleSink = ((__int64 (__fastcall *)(struct IBaseFilter *, struct IMFCollection **))v115->lpVtbl->EnumPins)(
                           v115,
                           &v100);
    if ( CustomDSSampleSink < 0 )
    {
      v54 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v54 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v55 = CallStackTracing::GetThreadRelativeContext(v54);
        if ( *((_DWORD *)v55 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v55, "CDShowWrapper::CreateDVDGraph", 3058, CustomDSSampleSink);
      }
      if ( g_wppLevels )
      {
        v51 = 269;
LABEL_183:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v51,
          &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
          this,
          CustomDSSampleSink);
      }
LABEL_184:
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v100);
      v56 = &v104;
LABEL_185:
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v56);
      goto LABEL_320;
    }
    CustomDSSampleSink = ((__int64 (__fastcall *)(struct IMFCollection *, __int64, __int64 *, _QWORD))v100->lpVtbl->GetElementCount)(
                           v100,
                           1,
                           &v104,
                           0);
    if ( CustomDSSampleSink < 0 )
    {
      v52 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v52 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v53 = CallStackTracing::GetThreadRelativeContext(v52);
        if ( *((_DWORD *)v53 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v53, "CDShowWrapper::CreateDVDGraph", 3059, CustomDSSampleSink);
      }
      if ( g_wppLevels )
      {
        v51 = 270;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v104 + 48LL))(v104, &v119);
    if ( CustomDSSampleSink < 0 )
    {
      v49 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v49 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext(v49);
        if ( *((_DWORD *)v50 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v50, "CDShowWrapper::CreateDVDGraph", 3061, CustomDSSampleSink);
      }
      if ( g_wppLevels )
      {
        v51 = 271;
        goto LABEL_183;
      }
      goto LABEL_184;
    }
    v2 = 1;
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v100);
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v104);
LABEL_144:
    if ( !v46 && (**v101)(v101, &IID_IAMDirectSound, &v107) >= 0 && v107 )
    {
      ComSmartPtr<IBaseFilter>::operator=(&v114, &v101);
      v7 = v114;
      v102 = 0;
      v103 = 0;
      CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v114 + 80LL))(v114, &v103);
      if ( CustomDSSampleSink < 0 )
      {
        v66 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v66 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v67 = CallStackTracing::GetThreadRelativeContext(v66);
          if ( *((_DWORD *)v67 + 499) != CustomDSSampleSink )
            CallStackContext::TraceFailure(v67, "CDShowWrapper::CreateDVDGraph", 3078, CustomDSSampleSink);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v63 = 272;
      }
      else
      {
        CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v103 + 24LL))(
                               v103,
                               1,
                               &v102,
                               0);
        if ( CustomDSSampleSink >= 0 )
        {
          CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, struct IPin **))(*(_QWORD *)v102 + 48LL))(
                                 v102,
                                 &v110);
          if ( CustomDSSampleSink >= 0 )
          {
            v46 = 1;
            ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v103);
            ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v102);
            continue;
          }
          v61 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v61 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v61 + 8) )
          {
            v62 = CallStackTracing::GetThreadRelativeContext(v61);
            if ( *((_DWORD *)v62 + 499) != CustomDSSampleSink )
              CallStackContext::TraceFailure(v62, "CDShowWrapper::CreateDVDGraph", 3081, CustomDSSampleSink);
          }
          if ( g_wppLevels )
          {
            v63 = 274;
            goto LABEL_221;
          }
LABEL_222:
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v103);
          v56 = &v102;
          goto LABEL_185;
        }
        v64 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v64 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v64 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext(v64);
          if ( *((_DWORD *)v65 + 499) != CustomDSSampleSink )
            CallStackContext::TraceFailure(v65, "CDShowWrapper::CreateDVDGraph", 3079, CustomDSSampleSink);
        }
        if ( !g_wppLevels )
          goto LABEL_222;
        v63 = 273;
      }
LABEL_221:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v63,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        CustomDSSampleSink);
      goto LABEL_222;
    }
  }
  while ( !v45 || !v46 || !v2 );
  CustomDSSampleSink = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v106->lpVtbl[1].AddRef)(v106, v7);
  if ( CustomDSSampleSink >= 0 )
  {
    *((_DWORD *)this + 106) = 3;
    CustomDSSampleSink = CDShowWrapper::CreateCustomDSSampleSink(this, v6);
    if ( CustomDSSampleSink >= 0 )
    {
      CustomDSSampleSink = CDShowWrapper::ConnectPin(this, v110, 0, 0);
      if ( CustomDSSampleSink >= 0 )
      {
        memset_0(v121, 0, sizeof(v121));
        CustomDSSampleSink = ((__int64 (__fastcall *)(struct IPin *, _QWORD *))v110->lpVtbl->QueryPinInfo)(v110, v121);
        if ( CustomDSSampleSink >= 0 )
        {
          if ( v121[0] )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v121[0] + 16LL))(v121[0]);
            v121[0] = 0;
          }
          CustomDSSampleSink = CDShowWrapper::CollectMediaTypes(this, v72);
          if ( CustomDSSampleSink >= 0 )
          {
            ComSmartPtr<IBaseFilter>::operator=((char *)this + 64, &v116);
            if ( *((_DWORD *)this + 72) )
            {
              CustomDSSampleSink = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v106->lpVtbl->QueryInterface)(
                                     v106,
                                     &GUID_56a86899_0ad4_11ce_b03a_0020af0ba770,
                                     &v117);
              if ( CustomDSSampleSink >= 0 )
              {
                CustomDSSampleSink = CDShowSource::QueryInterface(
                                       *((CDShowSource **)this + 1),
                                       &GUID_56a86897_0ad4_11ce_b03a_0020af0ba770,
                                       &v113);
                if ( CustomDSSampleSink >= 0 )
                {
                  CustomDSSampleSink = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v117 + 64LL))(v117, v113);
                  if ( CustomDSSampleSink >= 0 )
                  {
                    CDShowSource::SetSession(
                      (CDShowSource *)(*((_QWORD *)this + 1) + 128LL),
                      *((struct IMFTelemetrySession **)this + 60));
                    ComSmartPtr<IBaseFilter>::operator=((char *)this + 56, &ppv);
                    if ( SDWORD2(v124) > 0 )
                    {
                      v86 = *((_QWORD *)this + 60);
                      CustomDSSampleSink = HIDWORD(v124) | 0x40320;
                      if ( !v86
                        || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 320LL))(
                              v86,
                              MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
                      {
                        v87 = *((_QWORD *)this + 60);
                        v88 = 0;
                        v122 = GUID_00000000_0000_0000_0000_000000000000;
                        if ( v87 )
                        {
                          v89 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v87 + 280LL))(
                                          v87,
                                          v125,
                                          0);
                          v90 = *((_QWORD *)this + 60);
                          v122 = *v89;
                          v88 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v90 + 296LL))(v90);
                        }
                        if ( (unsigned int)dword_1800EA260 > 4
                          && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800EA260, v85, v88) )
                        {
                          LODWORD(v103) = DWORD1(v124);
                          v125[0] = &v122;
                          LODWORD(v102) = DWORD2(v124);
                          LODWORD(v104) = CustomDSSampleSink;
                          LODWORD(v100) = v91;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                            DWORD2(v124),
                            (unsigned int)byte_1800DFA49,
                            v91,
                            v92,
                            (__int64)v125,
                            (__int64)&v100,
                            (__int64)&v104,
                            (__int64)&v103,
                            (__int64)&v102);
                        }
                      }
                    }
                    goto LABEL_320;
                  }
                  v83 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::InitInstance();
                    v83 = CallStackTracing::s_wpInstance;
                  }
                  if ( *((_BYTE *)v83 + 8) )
                  {
                    v84 = CallStackTracing::GetThreadRelativeContext(v83);
                    if ( *((_DWORD *)v84 + 499) != CustomDSSampleSink )
                      CallStackContext::TraceFailure(v84, "CDShowWrapper::CreateDVDGraph", 3135, CustomDSSampleSink);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_320;
                  v11 = 283;
                }
                else
                {
                  v81 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::InitInstance();
                    v81 = CallStackTracing::s_wpInstance;
                  }
                  if ( *((_BYTE *)v81 + 8) )
                  {
                    v82 = CallStackTracing::GetThreadRelativeContext(v81);
                    if ( *((_DWORD *)v82 + 499) != CustomDSSampleSink )
                      CallStackContext::TraceFailure(v82, "CDShowWrapper::CreateDVDGraph", 3134, CustomDSSampleSink);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_320;
                  v11 = 282;
                }
              }
              else
              {
                v79 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v79 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v79 + 8) )
                {
                  v80 = CallStackTracing::GetThreadRelativeContext(v79);
                  if ( *((_DWORD *)v80 + 499) != CustomDSSampleSink )
                    CallStackContext::TraceFailure(v80, "CDShowWrapper::CreateDVDGraph", 3133, CustomDSSampleSink);
                }
                if ( !g_wppLevels )
                  goto LABEL_320;
                v11 = 281;
              }
            }
            else
            {
              v77 = CallStackTracing::s_wpInstance;
              CustomDSSampleSink = -1072873832;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v77 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v77 + 8) )
              {
                v78 = CallStackTracing::GetThreadRelativeContext(v77);
                if ( *((_DWORD *)v78 + 499) != -1072873832 )
                  CallStackContext::TraceFailure(v78, "CDShowWrapper::CreateDVDGraph", 3130, -1072873832);
              }
              if ( !g_wppLevels )
                goto LABEL_320;
              v11 = 280;
            }
          }
          else
          {
            v75 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v75 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v75 + 8) )
            {
              v76 = CallStackTracing::GetThreadRelativeContext(v75);
              if ( *((_DWORD *)v76 + 499) != CustomDSSampleSink )
                CallStackContext::TraceFailure(v76, "CDShowWrapper::CreateDVDGraph", 3115, CustomDSSampleSink);
            }
            if ( !g_wppLevels )
              goto LABEL_320;
            v11 = 279;
          }
        }
        else
        {
          v73 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v73 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v73 + 8) )
          {
            v74 = CallStackTracing::GetThreadRelativeContext(v73);
            if ( *((_DWORD *)v74 + 499) != CustomDSSampleSink )
              CallStackContext::TraceFailure(v74, "CDShowWrapper::CreateDVDGraph", 3112, CustomDSSampleSink);
          }
          if ( !g_wppLevels )
            goto LABEL_320;
          v11 = 278;
        }
      }
      else
      {
        v70 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v70 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext(v70);
          if ( *((_DWORD *)v71 + 499) != CustomDSSampleSink )
            CallStackContext::TraceFailure(v71, "CDShowWrapper::CreateDVDGraph", 3105, CustomDSSampleSink);
        }
        if ( !g_wppLevels )
          goto LABEL_320;
        v11 = 277;
      }
    }
    else
    {
      v68 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v68 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v69 = CallStackTracing::GetThreadRelativeContext(v68);
        if ( *((_DWORD *)v69 + 499) != CustomDSSampleSink )
          CallStackContext::TraceFailure(v69, "CDShowWrapper::CreateDVDGraph", 3103, CustomDSSampleSink);
      }
      if ( !g_wppLevels )
        goto LABEL_320;
      v11 = 276;
    }
    goto LABEL_319;
  }
  v47 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v47 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v47 + 8) )
  {
    v48 = CallStackTracing::GetThreadRelativeContext(v47);
    if ( *((_DWORD *)v48 + 499) != CustomDSSampleSink )
      CallStackContext::TraceFailure(v48, "CDShowWrapper::CreateDVDGraph", 3094, CustomDSSampleSink);
  }
  if ( g_wppLevels )
  {
    v11 = 275;
    goto LABEL_319;
  }
LABEL_320:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v119);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v110);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v107);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v108);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v109);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v120);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v112);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v113);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v114);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v115);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v116);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v101);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v117);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v111);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v106);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v99);
  return (unsigned int)CustomDSSampleSink;
}

```

## disassembly

```asm
0x1800802fc  push    rbp
0x1800802fe  push    rbx
0x1800802ff  push    rsi
0x180080300  push    rdi
0x180080301  push    r12
0x180080303  push    r13
0x180080305  push    r14
0x180080307  push    r15
0x180080309  lea     rbp, [rsp-378h]
0x180080311  sub     rsp, 478h
0x180080318  mov     rax, cs:__security_cookie
0x18008031f  xor     rax, rsp
0x180080322  mov     [rbp+3B0h+var_50], rax
0x180080329  mov     r14, rcx
0x18008032c  lea     r15, aCdshowwrapperC_4; "CDShowWrapper::CreateDVDGraph"
0x180080333  mov     rdx, r15; char *
0x180080336  lea     rcx, [rsp+4B0h+var_460]; this
0x18008033b  mov     r8d, 0B53h; int
0x180080341  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180080346  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008034d  xor     r12d, r12d
0x180080350  cmp     [rcx+8], r12b
0x180080354  jz      short loc_1800803AD
0x180080356  cmp     [r14+1E0h], r12
0x18008035d  jz      short loc_1800803AD
0x18008035f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080364  mov     rcx, [r14+1E0h]
0x18008036b  mov     rdi, rax
0x18008036e  mov     rdx, [rcx]
0x180080371  mov     rax, [rdx+128h]
0x180080378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008037d  mov     rcx, [r14+1E0h]
0x180080384  mov     ebx, eax
0x180080386  mov     rdx, [rcx]
0x180080389  mov     rax, [rdx+118h]
0x180080390  lea     rdx, [rbp+3B0h+var_2A0]
0x180080397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008039c  movups  xmm0, xmmword ptr [rax]
0x18008039f  mov     [rdi+7E0h], ebx
0x1800803a5  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800803ad  mov     rbx, r12
0x1800803b0  mov     [rbp+3B0h+var_428], r12
0x1800803b4  xor     edx, edx; Val
0x1800803b6  mov     [rbp+3B0h+var_3E0], rbx
0x1800803ba  mov     r8d, 208h; Size
0x1800803c0  mov     [rbp+3B0h+var_430], r12
0x1800803c4  lea     rcx, [rbp+3B0h+var_260]; void *
0x1800803cb  mov     [rbp+3B0h+var_400], r12
0x1800803cf  mov     [rbp+3B0h+var_3D0], r12
0x1800803d3  mov     rdi, r12
0x1800803d6  mov     [rsp+4B0h+var_450], r12
0x1800803db  mov     [rbp+3B0h+var_3D8], r12
0x1800803df  mov     [rbp+3B0h+var_3E8], r12
0x1800803e3  mov     [rbp+3B0h+var_3F0], r12
0x1800803e7  mov     [rbp+3B0h+var_3F8], r12
0x1800803eb  mov     [rbp+3B0h+var_3B8], r12
0x1800803ef  mov     [rbp+3B0h+var_410], r12
0x1800803f3  mov     [rbp+3B0h+var_418], r12
0x1800803f7  mov     [rbp+3B0h+var_420], r12
0x1800803fb  mov     [rbp+3B0h+var_408], r12
0x1800803ff  mov     [rbp+3B0h+var_3C0], r12
0x180080403  mov     [rbp+3B0h+var_3C8], r12
0x180080407  call    memset_0
0x18008040c  xorps   xmm0, xmm0
0x18008040f  lea     rax, [rbp+3B0h+var_430]
0x180080413  mov     r13d, 1
0x180080419  mov     [rsp+4B0h+ppv], rax; ppv
0x18008041e  mov     r8d, r13d; dwClsContext
0x180080421  lea     r9, _GUID_fcc152b6_f372_11d0_8e00_00c04fd7c08b; riid
0x180080428  xor     edx, edx; pUnkOuter
0x18008042a  lea     rcx, CLSID_DvdGraphBuilder; rclsid
0x180080431  movups  [rbp+3B0h+var_290], xmm0
0x180080438  movups  [rbp+3B0h+var_280], xmm0
0x18008043f  call    cs:__imp_CoCreateInstance
0x180080446  nop     dword ptr [rax+rax+00h]
0x18008044b  mov     esi, eax
0x18008044d  test    eax, eax
0x18008044f  jns     short loc_1800804A7
0x180080451  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080458  test    rcx, rcx
0x18008045b  jnz     short loc_180080469
0x18008045d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180080462  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180080469  cmp     [rcx+8], r12b
0x18008046d  jz      short loc_180080490
0x18008046f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080474  cmp     [rax+7CCh], esi
0x18008047a  jz      short loc_180080490
0x18008047c  mov     r9d, esi; int
0x18008047f  mov     r8d, 0B77h; int
0x180080485  mov     rdx, r15; char *
0x180080488  mov     rcx, rax; this
0x18008048b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180080490  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180080497  jb      loc_18008178A
0x18008049d  mov     edx, 0FAh
0x1800804a2  jmp     loc_18008176C
0x1800804a7  mov     rcx, [rbp+3B0h+var_430]
0x1800804ab  lea     rdx, [rbp+3B0h+var_428]
0x1800804af  mov     rax, [rcx]
0x1800804b2  mov     rax, [rax+18h]
0x1800804b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800804bb  mov     esi, eax
0x1800804bd  test    eax, eax
0x1800804bf  jns     short loc_180080517
0x1800804c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800804c8  test    rcx, rcx
0x1800804cb  jnz     short loc_1800804D9
0x1800804cd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800804d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800804d9  cmp     [rcx+8], r12b
0x1800804dd  jz      short loc_180080500
0x1800804df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800804e4  cmp     [rax+7CCh], esi
0x1800804ea  jz      short loc_180080500
0x1800804ec  mov     r9d, esi; int
0x1800804ef  mov     r8d, 0B79h; int
0x1800804f5  mov     rdx, r15; char *
0x1800804f8  mov     rcx, rax; this
0x1800804fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180080500  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180080507  jb      loc_18008178A
0x18008050d  mov     edx, 0FBh
0x180080512  jmp     loc_18008176C
0x180080517  mov     r8, [rbp+3B0h+var_428]; struct IUnknown *
0x18008051b  lea     rcx, [r14+30h]; this
0x18008051f  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x180080526  call    ?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x18008052b  mov     esi, eax
0x18008052d  test    eax, eax
0x18008052f  jns     short loc_180080587
0x180080531  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080538  test    rcx, rcx
0x18008053b  jnz     short loc_180080549
0x18008053d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180080542  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180080549  cmp     [rcx+8], r12b
0x18008054d  jz      short loc_180080570
0x18008054f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080554  cmp     [rax+7CCh], esi
0x18008055a  jz      short loc_180080570
0x18008055c  mov     r9d, esi; int
0x18008055f  mov     r8d, 0B7Ah; int
0x180080565  mov     rdx, r15; char *
0x180080568  mov     rcx, rax; this
0x18008056b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180080570  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180080577  jb      loc_18008178A
0x18008057d  mov     edx, 0FCh
0x180080582  jmp     loc_18008176C
0x180080587  mov     rcx, r14; this
0x18008058a  call    ?SetDolbyBinding@CDShowWrapper@@IEAAJXZ; CDShowWrapper::SetDolbyBinding(void)
0x18008058f  mov     esi, eax
0x180080591  test    eax, eax
0x180080593  jns     short loc_1800805EB
0x180080595  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008059c  test    rcx, rcx
0x18008059f  jnz     short loc_1800805AD
0x1800805a1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800805a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800805ad  cmp     [rcx+8], r12b
0x1800805b1  jz      short loc_1800805D4
0x1800805b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800805b8  cmp     [rax+7CCh], esi
0x1800805be  jz      short loc_1800805D4
0x1800805c0  mov     r9d, esi; int
0x1800805c3  mov     r8d, 0B7Ch; int
0x1800805c9  mov     rdx, r15; char *
0x1800805cc  mov     rcx, rax; this
0x1800805cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800805d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800805db  jb      loc_18008178A
0x1800805e1  mov     edx, 0FDh
0x1800805e6  jmp     loc_18008176C
0x1800805eb  mov     rcx, [rbp+3B0h+var_430]
0x1800805ef  lea     r8, [rbp+3B0h+var_3B8]
0x1800805f3  lea     rdx, IID_IEVRFilterConfig
0x1800805fa  mov     rax, [rcx]
0x1800805fd  mov     rax, [rax+20h]
0x180080601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080606  mov     esi, eax
0x180080608  test    eax, eax
0x18008060a  jns     short loc_180080662
0x18008060c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080613  test    rcx, rcx
0x180080616  jnz     short loc_180080624
0x180080618  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18008061d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180080624  cmp     [rcx+8], r12b
0x180080628  jz      short loc_18008064B
0x18008062a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008062f  cmp     [rax+7CCh], esi
0x180080635  jz      short loc_18008064B
0x180080637  mov     r9d, esi; int
0x18008063a  mov     r8d, 0B7Fh; int
0x180080640  mov     rdx, r15; char *
0x180080643  mov     rcx, rax; this
0x180080646  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008064b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180080652  jb      loc_18008178A
0x180080658  mov     edx, 0FEh
0x18008065d  jmp     loc_18008176C
0x180080662  mov     r11d, 104h
0x180080668  lea     r8, aFile_1; "file:"
0x18008066f  mov     edx, r11d; unsigned __int64
0x180080672  lea     rcx, [rbp+3B0h+var_260]; unsigned __int16 *
0x180080679  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008067e  mov     esi, eax
0x180080680  test    eax, eax
0x180080682  jns     short loc_1800806DA
0x180080684  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008068b  test    rcx, rcx
0x18008068e  jnz     short loc_18008069C
0x180080690  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180080695  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008069c  cmp     [rcx+8], r12b
0x1800806a0  jz      short loc_1800806C3
0x1800806a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800806a7  cmp     [rax+7CCh], esi
0x1800806ad  jz      short loc_1800806C3
0x1800806af  mov     r9d, esi; int
0x1800806b2  mov     r8d, 0B85h; int
0x1800806b8  mov     rdx, r15; char *
0x1800806bb  mov     rcx, rax; this
0x1800806be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800806c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800806ca  jb      loc_18008178A
0x1800806d0  mov     edx, 0FFh
0x1800806d5  jmp     loc_18008176C
0x1800806da  lea     rcx, [r14+10h]
0x1800806de  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800806e3  mov     rdx, r11; unsigned __int64
0x1800806e6  lea     rcx, [rbp+3B0h+var_260]; unsigned __int16 *
0x1800806ed  lea     r8, [rax+0Ch]; unsigned __int16 *
0x1800806f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800806f6  mov     esi, eax
0x1800806f8  test    eax, eax
0x1800806fa  jns     short loc_180080756
0x1800806fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080703  test    rcx, rcx
0x180080706  jnz     short loc_180080714
0x180080708  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18008070d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180080714  cmp     [rcx+8], r12b
0x180080718  jz      short loc_18008073F
0x18008071a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008071f  cmp     [rax+7CCh], esi
0x180080725  jz      short loc_18008073F
0x180080727  mov     r9d, esi; int
0x18008072a  lea     rdx, aCdshowwrapperC_4; "CDShowWrapper::CreateDVDGraph"
0x180080731  mov     r8d, 0B89h; int
0x180080737  mov     rcx, rax; this
0x18008073a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008073f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180080746  jb      loc_18008178A
0x18008074c  mov     edx, 100h
0x180080751  jmp     loc_18008176C
0x180080756  lea     rdx, [rbp+3B0h+var_3C8]
0x18008075a  lea     rcx, [rbp+3B0h+var_260]
0x180080761  call    cs:__imp_MFCreatePathFromURL
0x180080768  nop     dword ptr [rax+rax+00h]
0x18008076d  test    eax, eax
0x18008076f  js      loc_1800807FA
0x180080775  mov     rcx, [rbp+3B0h+var_430]
0x180080779  lea     r9, [rbp+3B0h+var_290]
0x180080780  mov     rdx, [rbp+3B0h+var_3C8]
0x180080784  mov     r8d, 7001h
0x18008078a  mov     rax, [rcx]
0x18008078d  mov     rax, [rax+28h]
0x180080791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080796  mov     esi, eax
0x180080798  test    eax, eax
0x18008079a  jns     loc_180080889
0x1800807a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800807a7  test    rcx, rcx
0x1800807aa  jnz     short loc_1800807B8
0x1800807ac  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800807b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800807b8  cmp     [rcx+8], r12b
0x1800807bc  jz      short loc_1800807E3
0x1800807be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800807c3  cmp     [rax+7CCh], esi
0x1800807c9  jz      short loc_1800807E3
0x1800807cb  mov     r9d, esi; int
0x1800807ce  lea     rdx, aCdshowwrapperC_4; "CDShowWrapper::CreateDVDGraph"
0x1800807d5  mov     r8d, 0B8Eh; int
0x1800807db  mov     rcx, rax; this
0x1800807de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800807e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800807ea  jb      loc_18008178A
0x1800807f0  mov     edx, 101h
0x1800807f5  jmp     loc_18008176C
0x1800807fa  mov     r11, [rbp+3B0h+var_430]
0x1800807fe  lea     rcx, [r14+10h]
0x180080802  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180080807  mov     rdx, [r11]
0x18008080a  lea     r9, [rbp+3B0h+var_290]
0x180080811  mov     r8d, 7001h
0x180080817  mov     rcx, r11
0x18008081a  mov     r10, [rdx+28h]
  ... truncated ...
```
