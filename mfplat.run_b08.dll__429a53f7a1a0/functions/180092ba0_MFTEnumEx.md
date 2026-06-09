# MFTEnumEx

- ea: `0x180092ba0`
- end: `0x1800938c4`
- name: `MFTEnumEx`
- size: `3364`
- prototype: `HRESULT __stdcall(GUID *__struct_ptr guidCategory, UINT32 Flags, const MFT_REGISTER_TYPE_INFO *pInputType, const MFT_REGISTER_TYPE_INFO *pOutputType, IMFActivate ***pppMFTActivate, UINT32 *pnumMFTActivate)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180092840`
- `0x1800a2190`

## callees

- `0x1800016f0`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003f9d4`
- `0x18004cea4`
- `0x18004ced4`
- `0x18004d49c`
- `0x18005f61c`
- `0x180082368`
- `0x180092ba0`
- `0x1800a0bdc`
- `0x1800adb48`
- `0x1800af00c`
- `0x1800afd58`
- `0x1800b095c`
- `0x1800b0be0`
- `0x1800b1260`
- `0x1800b1484`
- `0x1801200d0`
- `0x180120ecc`
- `0x180121575`
- `0x180128588`
- `0x180145550`
- `0x18014648c`
- `0x180147bfc`
- `0x180147e68`
- `0x180147f24`
- `0x180147fe8`
- `0x180148068`
- `0x1801481e4`
- `0x180148a28`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009373d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800937c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009380e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009373d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800937c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009380e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180093396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180093396`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180093860`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180093860`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180092cbc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180092cce`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180092cbc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180092cce`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall MFTEnumEx(
        GUID *guidCategory,
        UINT32 Flags,
        const MFT_REGISTER_TYPE_INFO *pInputType,
        const MFT_REGISTER_TYPE_INFO *pOutputType,
        IMFActivate ***pppMFTActivate,
        UINT32 *pnumMFTActivate)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  const MFT_REGISTER_TYPE_INFO *v9; // r9
  GUID *p_guidSubtype; // r8
  GUID *v12; // rdx
  const MFT_REGISTER_TYPE_INFO *v13; // rcx
  GUID *p_guidMajorType; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // r14d
  __int64 v19; // r14
  CallStackTracing *v20; // rcx
  HRESULT v21; // esi
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  UINT32 v24; // ecx
  unsigned int v25; // edi
  char v26; // si
  struct IMFActivate *v27; // rcx
  unsigned int v28; // r12d
  int v29; // eax
  struct IMFActivate **v30; // rdx
  int v31; // ecx
  signed __int32 v32; // edi
  int v33; // eax
  unsigned int v34; // r12d
  int v35; // r8d
  int v36; // r9d
  char v37; // r12
  int unused; // edi
  unsigned int v39; // ecx
  bool v40; // zf
  unsigned int v41; // eax
  struct IMFActivate **v42; // rax
  unsigned int v43; // r12d
  _QWORD **v44; // r13
  struct IMFActivate ***v45; // r14
  unsigned int lpVtbl; // ebx
  __int64 v47; // rdi
  __int64 v48; // r13
  struct IMFActivate ***v49; // r14
  unsigned int v50; // ebx
  _QWORD **v51; // rsi
  struct IMFActivate *v52; // rax
  __int64 v53; // r13
  struct IMFActivate ***v54; // r14
  __int64 v55; // r8
  __int64 v56; // r13
  struct IMFActivate ***v57; // rbx
  unsigned int v58; // r14d
  _QWORD **v59; // rsi
  struct IMFActivate *v60; // rax
  __int64 v61; // r13
  struct IMFActivate ***v62; // r14
  __int64 v63; // r8
  unsigned int v64; // edi
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v65; // r13
  GUID *v66; // r8
  GUID *v67; // r9
  struct _GUID *v68; // r12
  CallStackTracing *v69; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD *v71; // r12
  unsigned int v72; // r13d
  __int64 i; // rbx
  __int64 v74; // rcx
  _QWORD *v75; // r12
  unsigned int v76; // r13d
  __int64 v77; // rbx
  __int64 v78; // rcx
  __int64 j; // rbx
  struct IMFActivate *v80; // rcx
  _QWORD *v81; // rax
  unsigned int v82; // r12d
  __int64 v83; // rbx
  __int64 v84; // rcx
  __int64 k; // rbx
  struct IMFActivate *v86; // rcx
  CallStackScopeTrace v88; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v89; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v90; // [rsp+58h] [rbp-A8h] BYREF
  int v91; // [rsp+5Ch] [rbp-A4h]
  unsigned int v92; // [rsp+60h] [rbp-A0h] BYREF
  struct HKEY__ hKey; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v94; // [rsp+68h] [rbp-98h] BYREF
  int v95; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v96; // [rsp+70h] [rbp-90h]
  IMFActivate ppActivate; // [rsp+74h] [rbp-8Ch] BYREF
  struct IMFActivate ***v98; // [rsp+80h] [rbp-80h]
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v99; // [rsp+88h] [rbp-78h]
  struct IMFActivate **v100; // [rsp+90h] [rbp-70h] BYREF
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v101; // [rsp+98h] [rbp-68h]
  struct IMFActivate **v102; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v103; // [rsp+A8h] [rbp-58h]
  MFTEnumCache *v104; // [rsp+B0h] [rbp-50h]
  unsigned int *v105; // [rsp+B8h] [rbp-48h]
  LPVOID v106; // [rsp+C0h] [rbp-40h]
  struct IMFActivate **v107; // [rsp+C8h] [rbp-38h] BYREF
  MFTEnumCache *v108; // [rsp+D0h] [rbp-30h] BYREF
  struct IMFActivate **v109; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID *Buf1; // [rsp+E0h] [rbp-20h]
  LPVOID pv; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID v112; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v113; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v114[256]; // [rsp+110h] [rbp+10h] BYREF

  v6 = 0;
  Buf1 = guidCategory;
  v104 = 0;
  v108 = 0;
  v106 = 0;
  v9 = pInputType;
  v109 = 0;
  v103 = 0;
  v107 = 0;
  v99 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)pOutputType;
  v101 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)pInputType;
  v98 = pppMFTActivate;
  v105 = pnumMFTActivate;
  pv = 0;
  v100 = 0;
  v102 = 0;
  LODWORD(ppActivate.lpVtbl) = 0;
  hKey.unused = 0;
  v89 = 0;
  v90 = 0;
  v94 = 0;
  if ( !pnumMFTActivate || !pppMFTActivate )
  {
    CallStackScopeTrace::CallStackScopeTrace(&v88, "MFTEnumEx", 3987);
    v69 = CallStackTracing::s_wpInstance;
    LOBYTE(v19) = 0;
    v21 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v69 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v69 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v69->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v69);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFTEnumEx", 3987, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_136;
    v23 = 105;
    goto LABEL_135;
  }
  if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
  {
    p_guidSubtype = &pOutputType->guidSubtype;
    if ( !pOutputType )
      p_guidSubtype = &GUID_00000000_0000_0000_0000_000000000000;
    v12 = &v9->guidSubtype;
    v13 = pOutputType;
    if ( !pOutputType )
      v13 = (const MFT_REGISTER_TYPE_INFO *)&GUID_00000000_0000_0000_0000_000000000000;
    if ( !v9 )
      v12 = &GUID_00000000_0000_0000_0000_000000000000;
    p_guidMajorType = &v9->guidMajorType;
    if ( !v9 )
      p_guidMajorType = &GUID_00000000_0000_0000_0000_000000000000;
    McTemplateU0djjjjj_EventWriteTransfer(
      (_DWORD)v13,
      (_DWORD)v12,
      Flags,
      (_DWORD)guidCategory,
      (__int64)p_guidMajorType,
      (__int64)v12,
      (__int64)v13,
      (__int64)p_guidSubtype);
  }
  *pnumMFTActivate = 0;
  *pppMFTActivate = 0;
  v18 = RoInitialize(1, *(_QWORD *)&Flags, pInputType, v9);
  if ( v18 == -2147417850 )
    v18 = RoInitialize(0, v15, v16, v17);
  v19 = v18 >= 0;
  HIDWORD(ppActivate.lpVtbl) = v19;
  if ( (Flags & 0xEFFFF800) != 0 )
  {
    CallStackScopeTrace::CallStackScopeTrace(&v88, "MFTEnumEx", 4024);
    v20 = CallStackTracing::s_wpInstance;
    v21 = -2147023892;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v20 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v20->m_fEnabled )
    {
      v22 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( v22->m_result != -2147023892 )
        CallStackContext::TraceFailure(v22, "MFTEnumEx", 4024, -2147023892);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_136;
    v23 = 106;
LABEL_135:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids, 0, v21);
LABEL_136:
    CallStackScopeTrace::~CallStackScopeTrace(&v88);
    goto LABEL_137;
  }
  v24 = 81;
  if ( Flags )
    v24 = Flags;
  v25 = v24 | 1;
  if ( (v24 & 7) != 0 )
    v25 = v24;
  if ( !memcmp_0(guidCategory, &CLSID_VideoInputDeviceCategory, 0x10u)
    || !memcmp_0(guidCategory, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44, 0x10u)
    || (v26 = 0, !memcmp_0(guidCategory, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca, 0x10u)) )
  {
    v26 = 1;
    CallStackScopeTrace::CallStackScopeTrace(&v88, "MFTEnumEx", 4069);
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids);
    CallStackScopeTrace::~CallStackScopeTrace(&v88);
  }
  v95 = v25 & 4;
  if ( (v25 & 4) == 0 )
  {
    v28 = v25;
    goto LABEL_39;
  }
  v28 = v25;
  if ( (unsigned int)HardwareEnumIsGloballyEnabledForCategory(guidCategory) )
  {
LABEL_39:
    v96 = v25;
    goto LABEL_40;
  }
  v28 = v25 & 0xFFFFFFFB;
  v96 = v25 & 0xFFFFFFFB;
LABEL_40:
  if ( v26 )
    goto LABEL_46;
  v29 = MFGetMFTCache(&v108);
  v6 = (struct _RTL_CRITICAL_SECTION *)v108;
  v104 = v108;
  if ( v29 < 0 )
  {
    if ( !v108 )
      goto LABEL_46;
    MFTEnumCache::Release(v108);
    v6 = 0;
    v104 = 0;
    v108 = 0;
  }
  if ( !v6 || (v112 = *guidCategory, v21 = MFTEnumCache::Lookup(v6, &v112, v28, v101, v99, v98, v105), v21 < 0) )
  {
LABEL_46:
    if ( (v28 & 0x10) != 0 )
    {
      v21 = CLocalMFTs::EnumMFTs(
              (CLocalMFTs *)v27,
              guidCategory,
              v28,
              v101,
              v99,
              (struct IMFActivate ***)&pv,
              &ppActivate);
      if ( v21 < 0 )
        goto LABEL_137;
    }
    v91 = EnumSoftwareMFTs(guidCategory, v28, v101, v99, &v109, &hKey);
    v21 = v91;
    if ( v91 >= 0 )
    {
      v106 = v109;
    }
    else
    {
      v21 = 0;
      v91 = 0;
      v106 = 0;
      hKey.unused = 0;
    }
    if ( (v28 & 4) != 0 )
    {
      v91 = EnumHardwareMFTs(guidCategory, v28, v101, v99, &v100, &v89);
      v21 = v91;
      if ( v91 < 0 )
      {
        v21 = 0;
        v91 = 0;
        v100 = 0;
        v89 = 0;
      }
    }
    if ( v95 )
    {
      v91 = EnumDeviceRegHWMFTs(guidCategory, v25, v101, v99, &v107, &v90);
      v21 = v91;
      if ( v91 >= 0 )
      {
        v103 = v107;
      }
      else
      {
        v21 = 0;
        v91 = 0;
        v103 = 0;
        v90 = 0;
      }
    }
    if ( (v28 & 0x10000000) == 0 )
    {
      if ( memcmp_0(guidCategory, &MFT_CATEGORY_VIDEO_PROCESSOR, 0x10u) )
      {
        if ( memcmp_0(guidCategory, &MFT_CATEGORY_AUDIO_EFFECT, 0x10u) )
        {
          if ( memcmp_0(guidCategory, &MFT_CATEGORY_ENCRYPTOR, 0x10u) )
          {
            v91 = EnumPackagedMFTs((v28 & 0x400) == 0, guidCategory, v28, v101, v99, &v102, &v94);
            v21 = v91;
            if ( v91 < 0 )
            {
              v21 = 0;
              v91 = 0;
              v102 = 0;
              v94 = 0;
            }
          }
        }
      }
    }
    v92 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MFTEnum_EngineAccessFilter>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MFTEnum_EngineAccessFilter>::GetImpl'::`2'::impl)
      || !v95
      || memcmp_0(guidCategory, &MFT_CATEGORY_VIDEO_ENCODER, 0x10u) )
    {
LABEL_82:
      unused = hKey.unused;
      v39 = hKey.unused + v89 + v94 + v90;
      v40 = v39 + LODWORD(ppActivate.lpVtbl) == 0;
      v41 = v39 + LODWORD(ppActivate.lpVtbl);
      LODWORD(v27) = (_DWORD)v105;
      *v105 = v41;
      if ( v40 )
      {
        if ( v6 )
        {
          v112 = *guidCategory;
          MFTEnumCache::Add(v6, &v112, v28, v101, v99, *v98, 0);
        }
      }
      else
      {
        v42 = (struct IMFActivate **)CoTaskMemAlloc(8LL * v41);
        v43 = 0;
        *v98 = v42;
        if ( !v42 )
        {
          v21 = -2147024882;
LABEL_137:
          DeleteActivateArray(v98, v105);
          goto LABEL_138;
        }
        memset_0(v42, 0, 8LL * *v105);
        v44 = (_QWORD **)pv;
        if ( pv && LODWORD(ppActivate.lpVtbl) )
        {
          v45 = v98;
          lpVtbl = (unsigned int)ppActivate.lpVtbl;
          do
          {
            v47 = v43;
            (*(void (__fastcall **)(_QWORD *))(*v44[v43] + 8LL))(v44[v43]);
            v27 = (struct IMFActivate *)*v45;
            ++v43;
            (*v45)[v47] = (struct IMFActivate *)v44[v47];
          }
          while ( v43 < lpVtbl );
          v6 = (struct _RTL_CRITICAL_SECTION *)v104;
          LOBYTE(v19) = BYTE4(ppActivate.lpVtbl);
          unused = hKey.unused;
        }
        if ( v106 && unused )
        {
          v48 = 0;
          v49 = v98;
          v50 = hKey.unused;
          v51 = (_QWORD **)v106;
          do
          {
            (*(void (__fastcall **)(_QWORD *))(*v51[v48] + 8LL))(v51[v48]);
            v52 = (struct IMFActivate *)v51[v48];
            v48 = (unsigned int)(v48 + 1);
            v27 = (struct IMFActivate *)*v49;
            v30 = (struct IMFActivate **)v43++;
            (*v49)[(_QWORD)v30] = v52;
          }
          while ( (unsigned int)v48 < v50 );
          v6 = (struct _RTL_CRITICAL_SECTION *)v104;
          v21 = v91;
          LOBYTE(v19) = BYTE4(ppActivate.lpVtbl);
        }
        if ( v100 && v89 )
        {
          v53 = 0;
          v54 = v98;
          do
          {
            ((void (__fastcall *)(struct IMFActivate *))v100[v53]->lpVtbl->AddRef)(v100[v53]);
            v30 = *v54;
            v55 = v43++;
            v27 = v100[v53];
            v53 = (unsigned int)(v53 + 1);
            (*v54)[v55] = v27;
          }
          while ( (unsigned int)v53 < v89 );
          LOBYTE(v19) = BYTE4(ppActivate.lpVtbl);
        }
        if ( v103 && v90 )
        {
          v56 = 0;
          v57 = v98;
          v58 = v90;
          v59 = (_QWORD **)v103;
          do
          {
            (*(void (__fastcall **)(_QWORD *))(*v59[v56] + 8LL))(v59[v56]);
            v60 = (struct IMFActivate *)v59[v56];
            v56 = (unsigned int)(v56 + 1);
            v27 = (struct IMFActivate *)*v57;
            v30 = (struct IMFActivate **)v43++;
            (*v57)[(_QWORD)v30] = v60;
          }
          while ( (unsigned int)v56 < v58 );
          v6 = (struct _RTL_CRITICAL_SECTION *)v104;
          v21 = v91;
          LOBYTE(v19) = BYTE4(ppActivate.lpVtbl);
        }
        if ( v102 && v94 )
        {
          v61 = 0;
          v62 = v98;
          do
          {
            ((void (__fastcall *)(struct IMFActivate *))v102[v61]->lpVtbl->AddRef)(v102[v61]);
            v30 = *v62;
            v63 = v43++;
            v27 = v102[v61];
            v61 = (unsigned int)(v61 + 1);
            (*v62)[v63] = v27;
          }
          while ( (unsigned int)v61 < v94 );
          LOBYTE(v19) = BYTE4(ppActivate.lpVtbl);
        }
        v64 = v96;
        v65 = v99;
        if ( v21 >= 0 && (v96 & 0x40) != 0 )
        {
          v66 = &GUID_00000000_0000_0000_0000_000000000000;
          v67 = (GUID *)((char *)v99 + 16);
          if ( !v99 )
            v67 = &GUID_00000000_0000_0000_0000_000000000000;
          if ( v101 )
            v66 = (GUID *)((char *)v101 + 16);
          v68 = Buf1;
          v21 = SortAndFilterMFTs(Buf1, v96, v66, v67, *v98, v105);
        }
        else
        {
          v68 = Buf1;
        }
        if ( !v6 )
        {
          if ( v21 >= 0 )
            goto LABEL_138;
          goto LABEL_137;
        }
        v112 = *v68;
        v21 = MFTEnumCache::Add(v6, &v112, v64, v101, v65, *v98, *v105);
        if ( v21 >= 0 )
          goto LABEL_138;
      }
      v21 = 0;
      goto LABEL_138;
    }
    v32 = _InterlockedIncrement(&dword_1801FD7D8);
    if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
      McTemplateU0jqq_EventWriteTransfer(v31, (_DWORD)v30, (_DWORD)guidCategory, 3, v32);
    memset_0(v114, 0, sizeof(v114));
    v95 = 0;
    v33 = QueryAllAdaptersEngineAccess(3, v114, &v95);
    v34 = v95;
    LODWORD(v107) = v33;
    if ( v33 >= 0 && v95 )
    {
      CallStackScopeTrace::CallStackScopeTrace(&v88, "MFTEnumEx", 4261);
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids, v34, v32);
      FilterHwMftArrayByEngineAccess((_DWORD)v100, (unsigned int)&v89, (unsigned int)v114, v34, (__int64)&v92);
      FilterHwMftArrayByEngineAccess((_DWORD)v103, (unsigned int)&v90, (unsigned int)v114, v34, (__int64)&v92);
      FilterHwMftArrayByEngineAccess((_DWORD)v106, (unsigned int)&hKey, (unsigned int)v114, v34, (__int64)&v92);
      if ( (unsigned int)dword_1801F81A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801F81A0, 0x400000000000LL) )
      {
        v37 = v92;
        v113 = 0x1000000;
        v95 = v92;
        v92 = v89 + v90;
        LODWORD(v109) = 3;
        *(_QWORD *)&v112.Data1 = guidCategory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v89 + v90,
          (unsigned int)&unk_1801E658B,
          v35,
          v36,
          (__int64)&v112,
          (__int64)&v109,
          (__int64)&v92,
          (__int64)&v95,
          (__int64)&v113);
LABEL_79:
        CallStackScopeTrace::~CallStackScopeTrace(&v88);
        if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
          McTemplateU0jqqqqd_EventWriteTransfer(
            v89 + v90,
            (_DWORD)v30,
            (_DWORD)guidCategory,
            3,
            v32,
            v89 + v90,
            v37,
            (char)v107);
        v28 = v96;
        goto LABEL_82;
      }
    }
    else
    {
      CallStackScopeTrace::CallStackScopeTrace(&v88, "MFTEnumEx", 4290);
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
        WPP_SF_DDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
          (unsigned int)v107,
          v34,
          v32);
    }
    v37 = v92;
    goto LABEL_79;
  }
LABEL_138:
  v71 = pv;
  if ( pv )
  {
    v72 = (unsigned int)ppActivate.lpVtbl;
    for ( i = 0; (unsigned int)i < v72; i = (unsigned int)(i + 1) )
    {
      v74 = v71[i];
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v71[i] = 0;
      }
    }
    CoTaskMemFree(v71);
  }
  v75 = v106;
  v76 = hKey.unused;
  if ( v106 )
  {
    v77 = 0;
    if ( hKey.unused )
    {
      do
      {
        v78 = v75[v77];
        if ( v78 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          v75[v77] = 0;
        }
        v77 = (unsigned int)(v77 + 1);
      }
      while ( (unsigned int)v77 < v76 );
    }
    CoTaskMemFree(v75);
  }
  if ( v100 )
  {
    for ( j = 0; (unsigned int)j < v89; j = (unsigned int)(j + 1) )
    {
      v80 = v100[j];
      if ( v80 )
      {
        ((void (__fastcall *)(struct IMFActivate *))v80->lpVtbl->Release)(v80);
        v100[j] = 0;
      }
    }
    CoTaskMemFree(v100);
  }
  v81 = v103;
  v82 = v90;
  if ( v103 )
  {
    v83 = 0;
    if ( v90 )
    {
      do
      {
        v84 = v81[v83];
        if ( v84 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
          v81 = v103;
          *((_QWORD *)v103 + v83) = 0;
        }
        v83 = (unsigned int)(v83 + 1);
      }
      while ( (unsigned int)v83 < v82 );
    }
    CoTaskMemFree(v81);
  }
  if ( v102 )
  {
    for ( k = 0; (unsigned int)k < v94; k = (unsigned int)(k + 1) )
    {
      v86 = v102[k];
      if ( v86 )
      {
        ((void (__fastcall *)(struct IMFActivate *))v86->lpVtbl->Release)(v86);
        v102[k] = 0;
      }
    }
    CoTaskMemFree(v102);
  }
  if ( (_BYTE)v19 )
    RoUninitialize();
  if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
    McTemplateU0dqqqqq_EventWriteTransfer((_DWORD)v27, (_DWORD)v30, v21, ppActivate.lpVtbl, v76, v89, v82, v94);
  ComSmartPtr<MFTEnumCache>::~ComSmartPtr<MFTEnumCache>(&v108);
  return v21;
}

```

## disassembly

```asm
0x180092ba0  push    rbp
0x180092ba2  push    rbx
0x180092ba3  push    rsi
0x180092ba4  push    rdi
0x180092ba5  push    r12
0x180092ba7  push    r13
0x180092ba9  push    r14
0x180092bab  push    r15
0x180092bad  lea     rbp, [rsp-128h]
0x180092bb5  sub     rsp, 228h
0x180092bbc  mov     rax, cs:__security_cookie
0x180092bc3  xor     rax, rsp
0x180092bc6  mov     [rbp+160h+var_50], rax
0x180092bcd  mov     r14, [rbp+160h+pnumMFTActivate]
0x180092bd4  xor     r12d, r12d
0x180092bd7  mov     rsi, [rbp+160h+pppMFTActivate]
0x180092bde  mov     ebx, r12d
0x180092be1  mov     [rbp+160h+Buf1], rcx
0x180092be5  mov     rax, r9
0x180092be8  mov     [rbp+160h+var_1B0], rbx
0x180092bec  mov     r13, rcx
0x180092bef  mov     [rbp+160h+var_190], rbx
0x180092bf3  mov     ecx, r12d
0x180092bf6  mov     [rbp+160h+var_1A0], rcx
0x180092bfa  mov     r9, r8
0x180092bfd  mov     [rbp+160h+var_188], rcx
0x180092c01  mov     edi, edx
0x180092c03  mov     [rbp+160h+var_1B8], rcx
0x180092c07  mov     [rbp+160h+var_198], rcx
0x180092c0b  mov     [rbp+160h+var_1D8], rax
0x180092c0f  mov     [rbp+160h+var_1C8], r8
0x180092c13  mov     [rbp+160h+var_1E0], rsi
0x180092c17  mov     [rbp+160h+var_1A8], r14
0x180092c1b  mov     [rbp+160h+pv], r12
0x180092c1f  mov     [rbp+160h+var_1D0], r12
0x180092c23  mov     [rbp+160h+var_1C0], r12
0x180092c27  mov     dword ptr [rsp+260h+var_1EC.lpVtbl], r12d
0x180092c2c  mov     [rsp+260h+var_1FC.unused], r12d
0x180092c31  mov     [rsp+260h+var_20C], r12d
0x180092c36  mov     [rsp+260h+var_208], r12d
0x180092c3b  mov     [rsp+260h+var_1F8], r12d
0x180092c40  test    r14, r14
0x180092c43  jz      loc_180093625
0x180092c49  test    rsi, rsi
0x180092c4c  jz      loc_180093625
0x180092c52  test    cs:Microsoft_Windows_MediaFoundation_PlatformEnableBits, 2
0x180092c59  lea     r10, _GUID_00000000_0000_0000_0000_000000000000
0x180092c60  jz      short loc_180092CAD
0x180092c62  lea     r8, [rax+10h]
0x180092c66  test    rax, rax
0x180092c69  jnz     short loc_180092C6E
0x180092c6b  mov     r8, r10
0x180092c6e  test    rax, rax
0x180092c71  lea     rdx, [r9+10h]
0x180092c75  mov     rcx, rax
0x180092c78  cmovz   rcx, r10
0x180092c7c  test    r9, r9
0x180092c7f  jnz     short loc_180092C84
0x180092c81  mov     rdx, r10
0x180092c84  mov     [rsp+260h+var_228], r8
0x180092c89  test    r9, r9
0x180092c8c  mov     rax, r9
0x180092c8f  mov     [rsp+260h+ppActivate], rcx
0x180092c94  cmovz   rax, r10
0x180092c98  mov     [rsp+260h+hKey], rdx
0x180092c9d  mov     r9, r13
0x180092ca0  mov     [rsp+260h+var_240], rax
0x180092ca5  mov     r8d, edi
0x180092ca8  call    McTemplateU0djjjjj_EventWriteTransfer
0x180092cad  mov     [r14], r12d
0x180092cb0  mov     r15d, 1
0x180092cb6  mov     ecx, r15d
0x180092cb9  mov     [rsi], r12
0x180092cbc  call    cs:__imp_RoInitialize
0x180092cc2  mov     r14d, eax
0x180092cc5  cmp     eax, 80010106h
0x180092cca  jnz     short loc_180092CD7
0x180092ccc  xor     ecx, ecx
0x180092cce  call    cs:__imp_RoInitialize
0x180092cd4  mov     r14d, eax
0x180092cd7  shr     r14d, 1Fh
0x180092cdb  xor     r14b, r15b
0x180092cde  mov     dword ptr [rsp+260h+var_1EC.lpVtbl+4], r14d
0x180092ce3  test    edi, 0EFFFF800h
0x180092ce9  jz      loc_180092D96
0x180092cef  mov     ebx, 0FB8h
0x180092cf4  lea     rdx, aMftenumex_0; "MFTEnumEx"
0x180092cfb  mov     r8d, ebx; int
0x180092cfe  lea     rcx, [rsp+260h+var_210]; this
0x180092d03  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180092d08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092d0f  mov     esi, 800703ECh
0x180092d14  test    rcx, rcx
0x180092d17  jnz     short loc_180092D57
0x180092d19  mov     rax, cs:stru_1801FC290.__vftable
0x180092d20  lea     rcx, stru_1801FC290
0x180092d27  mov     edx, 7F0h
0x180092d2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180092d33  mov     rax, [rax+8]
0x180092d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d3c  test    eax, eax
0x180092d3e  jnz     short loc_180092D50
0x180092d40  lea     rcx, stru_1801F8A30
0x180092d47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180092d4e  jmp     short loc_180092D57
0x180092d50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180092d57  cmp     [rcx+8], r12b
0x180092d5b  jz      short loc_180092D7F
0x180092d5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180092d62  cmp     [rax+7CCh], esi
0x180092d68  jz      short loc_180092D7F
0x180092d6a  mov     r9d, esi; int
0x180092d6d  lea     rdx, aMftenumex_0; "MFTEnumEx"
0x180092d74  mov     r8d, ebx; int
0x180092d77  mov     rcx, rax; this
0x180092d7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180092d7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180092d86  jb      loc_1800936E9
0x180092d8c  mov     edx, 6Ah ; 'j'
0x180092d91  jmp     loc_1800936CB
0x180092d96  test    edi, edi
0x180092d98  lea     rdx, CLSID_VideoInputDeviceCategory; Buf2
0x180092d9f  mov     ecx, 51h ; 'Q'
0x180092da4  mov     esi, 10h
0x180092da9  cmovnz  ecx, edi
0x180092dac  mov     r8d, esi; Size
0x180092daf  mov     edi, ecx
0x180092db1  or      edi, r15d
0x180092db4  test    cl, 7
0x180092db7  cmovnz  edi, ecx
0x180092dba  mov     rcx, r13; Buf1
0x180092dbd  call    memcmp_0
0x180092dc2  test    eax, eax
0x180092dc4  jz      short loc_180092DF8
0x180092dc6  mov     r8d, esi; Size
0x180092dc9  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44; Buf2
0x180092dd0  mov     rcx, r13; Buf1
0x180092dd3  call    memcmp_0
0x180092dd8  test    eax, eax
0x180092dda  jz      short loc_180092DF8
0x180092ddc  mov     r8d, 10h; Size
0x180092de2  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca; Buf2
0x180092de9  mov     rcx, r13; Buf1
0x180092dec  mov     sil, r12b
0x180092def  call    memcmp_0
0x180092df4  test    eax, eax
0x180092df6  jnz     short loc_180092E41
0x180092df8  mov     r8d, 0FE5h; int
0x180092dfe  lea     rdx, aMftenumex_0; "MFTEnumEx"
0x180092e05  lea     rcx, [rsp+260h+var_210]; this
0x180092e0a  mov     sil, r15b
0x180092e0d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180092e12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180092e19  jb      short loc_180092E37
0x180092e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092e22  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x180092e29  mov     edx, 6Bh ; 'k'
0x180092e2e  mov     rcx, [rcx+10h]
0x180092e32  call    WPP_SF_
0x180092e37  lea     rcx, [rsp+260h+var_210]; this
0x180092e3c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180092e41  mov     eax, edi
0x180092e43  and     eax, 4
0x180092e46  mov     [rsp+260h+var_1F4], eax
0x180092e4a  jz      short loc_180092E66
0x180092e4c  mov     rcx, r13; struct _GUID *
0x180092e4f  call    ?HardwareEnumIsGloballyEnabledForCategory@@YAHAEBU_GUID@@@Z; HardwareEnumIsGloballyEnabledForCategory(_GUID const &)
0x180092e54  mov     r12d, edi
0x180092e57  test    eax, eax
0x180092e59  jnz     short loc_180092E69
0x180092e5b  and     r12d, 0FFFFFFFBh
0x180092e5f  mov     [rsp+260h+var_1F0], r12d
0x180092e64  jmp     short loc_180092E6D
0x180092e66  mov     r12d, edi
0x180092e69  mov     [rsp+260h+var_1F0], edi
0x180092e6d  test    sil, sil
0x180092e70  jnz     short loc_180092EEE
0x180092e72  lea     rcx, [rbp+160h+var_190]; struct MFTEnumCache **
0x180092e76  call    ?MFGetMFTCache@@YAJPEAPEAUMFTEnumCache@@@Z; MFGetMFTCache(MFTEnumCache * *)
0x180092e7b  mov     rbx, [rbp+160h+var_190]
0x180092e7f  mov     [rbp+160h+var_1B0], rbx
0x180092e83  test    eax, eax
0x180092e85  jns     short loc_180092E9E
0x180092e87  test    rbx, rbx
0x180092e8a  jz      short loc_180092EEE
0x180092e8c  mov     rcx, rbx; this
0x180092e8f  call    ?Release@MFTEnumCache@@QEAAKXZ; MFTEnumCache::Release(void)
0x180092e94  xor     ebx, ebx
0x180092e96  mov     [rbp+160h+var_1B0], rbx
0x180092e9a  mov     [rbp+160h+var_190], rbx
0x180092e9e  test    rbx, rbx
0x180092ea1  jz      short loc_180092EEE
0x180092ea3  movups  xmm0, xmmword ptr [r13+0]
0x180092ea8  mov     r9, [rbp+160h+var_1C8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092eac  lea     rdx, [rbp+160h+var_170]; Buf1
0x180092eb0  mov     eax, 8
0x180092eb5  mov     rcx, rbx
0x180092eb8  cmovz   rcx, rax; lpCriticalSection
0x180092ebc  mov     r8d, r12d; unsigned int
0x180092ebf  mov     rax, [rbp+160h+var_1A8]
0x180092ec3  mov     [rsp+260h+ppActivate], rax; unsigned int *
0x180092ec8  mov     rax, [rbp+160h+var_1E0]
0x180092ecc  mov     [rsp+260h+hKey], rax; struct IMFActivate ***
0x180092ed1  mov     rax, [rbp+160h+var_1D8]
0x180092ed5  mov     [rsp+260h+var_240], rax; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092eda  movdqu  xmmword ptr [rbp+160h+var_170.Data1], xmm0
0x180092edf  call    ?Lookup@MFTEnumCache@@QEAAJU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z; MFTEnumCache::Lookup(_GUID,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x180092ee4  mov     esi, eax
0x180092ee6  test    eax, eax
0x180092ee8  jns     loc_180093700
0x180092eee  test    r12b, 10h
0x180092ef2  jz      short loc_180092F29
0x180092ef4  mov     r9, [rbp+160h+var_1C8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092ef8  lea     rax, [rsp+260h+var_1EC]
0x180092efd  mov     [rsp+260h+ppActivate], rax; ppActivate
0x180092f02  mov     r8d, r12d; unsigned int
0x180092f05  lea     rax, [rbp+160h+pv]
0x180092f09  mov     rdx, r13; struct _GUID *
0x180092f0c  mov     [rsp+260h+hKey], rax; struct IMFActivate ***
0x180092f11  mov     rax, [rbp+160h+var_1D8]
0x180092f15  mov     [rsp+260h+var_240], rax; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092f1a  call    ?EnumMFTs@CLocalMFTs@@QEAAJAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z; CLocalMFTs::EnumMFTs(_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x180092f1f  mov     esi, eax
0x180092f21  test    eax, eax
0x180092f23  js      loc_1800936F3
0x180092f29  mov     r9, [rbp+160h+var_1D8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092f2d  lea     rax, [rsp+260h+var_1FC]
0x180092f32  mov     r8, [rbp+160h+var_1C8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092f36  mov     edx, r12d; unsigned int
0x180092f39  mov     [rsp+260h+hKey], rax; hKey
0x180092f3e  mov     rcx, r13; struct _GUID *
0x180092f41  lea     rax, [rbp+160h+var_188]
0x180092f45  mov     [rsp+260h+var_240], rax; struct IMFActivate ***
0x180092f4a  call    ?EnumSoftwareMFTs@@YAJAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z; EnumSoftwareMFTs(_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x180092f4f  mov     [rsp+260h+var_204], eax
0x180092f53  mov     esi, eax
0x180092f55  test    eax, eax
0x180092f57  jns     short loc_180092F69
0x180092f59  xor     esi, esi
0x180092f5b  mov     [rsp+260h+var_204], esi
0x180092f5f  mov     [rbp+160h+var_1A0], rsi
0x180092f63  mov     [rsp+260h+var_1FC.unused], esi
0x180092f67  jmp     short loc_180092F71
0x180092f69  mov     rax, [rbp+160h+var_188]
0x180092f6d  mov     [rbp+160h+var_1A0], rax
0x180092f71  test    r12b, 4
0x180092f75  jz      short loc_180092FB5
0x180092f77  mov     r9, [rbp+160h+var_1D8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092f7b  lea     rax, [rsp+260h+var_20C]
0x180092f80  mov     r8, [rbp+160h+var_1C8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092f84  mov     edx, r12d; unsigned int
0x180092f87  mov     [rsp+260h+hKey], rax; unsigned int *
0x180092f8c  mov     rcx, r13; struct _GUID *
0x180092f8f  lea     rax, [rbp+160h+var_1D0]
0x180092f93  mov     [rsp+260h+var_240], rax; struct IMFActivate ***
0x180092f98  call    ?EnumHardwareMFTs@@YAJAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z; EnumHardwareMFTs(_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x180092f9d  mov     [rsp+260h+var_204], eax
0x180092fa1  mov     esi, eax
0x180092fa3  test    eax, eax
0x180092fa5  jns     short loc_180092FB5
0x180092fa7  xor     esi, esi
0x180092fa9  mov     [rsp+260h+var_204], esi
0x180092fad  mov     [rbp+160h+var_1D0], rsi
0x180092fb1  mov     [rsp+260h+var_20C], esi
0x180092fb5  cmp     [rsp+260h+var_1F4], 0
0x180092fba  jz      short loc_180093007
0x180092fbc  mov     r9, [rbp+160h+var_1D8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092fc0  lea     rax, [rsp+260h+var_208]
0x180092fc5  mov     r8, [rbp+160h+var_1C8]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180092fc9  mov     edx, edi; unsigned int
0x180092fcb  mov     [rsp+260h+hKey], rax; unsigned int *
0x180092fd0  mov     rcx, r13; struct _GUID *
0x180092fd3  lea     rax, [rbp+160h+var_198]
0x180092fd7  mov     [rsp+260h+var_240], rax; struct IMFActivate ***
0x180092fdc  call    ?EnumDeviceRegHWMFTs@@YAJAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z; EnumDeviceRegHWMFTs(_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x180092fe1  xor     edi, edi
0x180092fe3  mov     [rsp+260h+var_204], eax
0x180092fe7  mov     esi, eax
0x180092fe9  test    eax, eax
0x180092feb  jns     short loc_180092FFD
0x180092fed  mov     esi, edi
0x180092fef  mov     [rsp+260h+var_204], edi
0x180092ff3  mov     [rbp+160h+var_1B8], rdi
0x180092ff7  mov     [rsp+260h+var_208], edi
0x180092ffb  jmp     short loc_180093009
0x180092ffd  mov     rax, [rbp+160h+var_198]
0x180093001  mov     [rbp+160h+var_1B8], rax
0x180093005  jmp     short loc_180093009
0x180093007  xor     edi, edi
0x180093009  bt      r12d, 1Ch
0x18009300e  jb      loc_1800930B1
0x180093014  mov     r8d, 10h; Size
0x18009301a  lea     rdx, MFT_CATEGORY_VIDEO_PROCESSOR; Buf2
0x180093021  mov     rcx, r13; Buf1
0x180093024  call    memcmp_0
0x180093029  test    eax, eax
0x18009302b  jz      loc_1800930B1
0x180093031  mov     r8d, 10h; Size
0x180093037  lea     rdx, MFT_CATEGORY_AUDIO_EFFECT; Buf2
0x18009303e  mov     rcx, r13; Buf1
  ... truncated ...
```
