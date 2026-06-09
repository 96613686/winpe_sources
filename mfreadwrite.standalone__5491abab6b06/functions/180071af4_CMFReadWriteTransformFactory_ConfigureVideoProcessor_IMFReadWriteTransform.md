# CMFReadWriteTransformFactory::ConfigureVideoProcessor(IMFReadWriteTransform * *)

- ea: `0x180071af4`
- end: `0x180072466`
- name: `?ConfigureVideoProcessor@CMFReadWriteTransformFactory@@AEAAJPEAPEAUIMFReadWriteTransform@@@Z`
- size: `2418`
- prototype: `__int64 __fastcall(CMFReadWriteTransformFactory *__hidden this, struct IMFReadWriteTransform **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071984`

## callees

- `0x18000517c`
- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x180029900`
- `0x1800595c8`
- `0x18005bfb0`
- `0x180071af4`
- `0x1800724b4`
- `0x1800738c8`
- `0x1800a8c38`
- `0x1800acd2c`
- `0x1800c2364`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071f94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800720be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072215`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071f94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800720be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007206f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007206f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180071f33`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180072064`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800721bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180071f33`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180072064`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800721bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071dfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071caa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071caa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071f54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071ff5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800721dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071f54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071ff5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800721dc`
- `MFPlat!MFTEnumEx` at `0x180071c2f`
- `MFPlat!MFTEnumEx` at `0x180071c2f`

## string_xrefs

- `0x180071b12`: `CMFReadWriteTransformFactory::ConfigureVideoProcessor`
- `0x180071faa`: `CMFReadWriteTransformFactory::ConfigureVideoProcessor`
- `0x1800720d5`: `CMFReadWriteTransformFactory::ConfigureVideoProcessor`
- `0x18007222c`: `CMFReadWriteTransformFactory::ConfigureVideoProcessor`

## pseudocode

```c
__int64 __fastcall CMFReadWriteTransformFactory::ConfigureVideoProcessor(
        CMFReadWriteTransformFactory *this,
        struct IMFReadWriteTransform **a2)
{
  __int64 *v4; // rcx
  struct IMFReadWriteTransform *v5; // rbx
  __int64 v6; // rax
  UINT32 v7; // edi
  int v8; // r13d
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  HRESULT v14; // edi
  unsigned int v15; // r12d
  __int64 i; // r14
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 j; // rsi
  IMFActivate *v21; // rcx
  CallStackTracing *v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // rdx
  CallStackContext *v26; // r14
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  CallStackTracing *v31; // rsi
  CallStackTracing *v32; // rax
  __int64 v33; // rax
  CallStackTracing *v34; // r14
  CallStackTracing *v35; // rax
  __int64 v36; // rdx
  CallStackContext *v37; // r12
  DWORD v38; // r13d
  CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 v43; // rax
  CallStackTracing *v44; // r14
  CallStackTracing *v45; // rax
  CallStackContext *v46; // r12
  DWORD v47; // r13d
  CallStackContext *v48; // rax
  __int64 v49; // rdx
  CallStackTracing *v50; // rcx
  CallStackTracing *v51; // rax
  __int64 v52; // rax
  struct IMFAttributes *v53; // r9
  unsigned int v54; // ecx
  int v55; // eax
  int v56; // esi
  __int64 v57; // rdx
  __int64 v58; // rcx
  int v59; // eax
  struct IMFReadWriteTransform *v60; // rax
  IMFActivate ***pppMFTActivate; // [rsp+20h] [rbp-58h]
  LPVOID ppv[2]; // [rsp+30h] [rbp-48h] BYREF
  GUID guidCategory; // [rsp+40h] [rbp-38h] BYREF
  IMFActivate **v64; // [rsp+50h] [rbp-28h] BYREF
  struct IUnknown *v65; // [rsp+58h] [rbp-20h] BYREF
  struct _GUID v66; // [rsp+60h] [rbp-18h] BYREF
  int v67; // [rsp+C0h] [rbp+48h] BYREF
  struct IMFReadWriteTransform **v68; // [rsp+C8h] [rbp+50h]
  UINT32 pnumMFTActivate; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v70; // [rsp+D8h] [rbp+60h] BYREF

  v68 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v67,
    "CMFReadWriteTransformFactory::ConfigureVideoProcessor",
    1255);
  v4 = (__int64 *)*((_QWORD *)this + 3);
  v64 = 0;
  v5 = 0;
  pnumMFTActivate = 0;
  v6 = *v4;
  v65 = 0;
  v7 = 99;
  v67 = 0;
  v8 = 0;
  if ( (*(int (__fastcall **)(__int64 *, __int64 *, int *))(v6 + 56))(v4, MF_MT_VIDEO_3D, &v67) >= 0 )
    v8 = v67;
  *a2 = 0;
  v9 = *((_QWORD *)this + 5);
  v67 = 0;
  if ( (*(int (__fastcall **)(__int64, const IID *, int *))(*(_QWORD *)v9 + 56LL))(
         v9,
         &MF_READWRITE_ENABLE_HARDWARE_TRANSFORMS,
         &v67) >= 0 )
    v10 = v67;
  else
    v10 = 0;
  v67 = 0;
  if ( v10 == 1 )
    v7 = 103;
  if ( (*(int (__fastcall **)(_QWORD, __int64 *, int *))(**((_QWORD **)this + 5) + 56LL))(
         *((_QWORD *)this + 5),
         MF_LOCAL_PLUGIN_CONTROL_POLICY,
         &v67) >= 0 )
    v11 = v67;
  else
    v11 = 0;
  switch ( v11 )
  {
    case 2:
      v7 |= 0x140u;
      break;
    case 3:
      v7 |= 0x240u;
      break;
    case 1:
      v7 |= 0xC0u;
      break;
  }
  v12 = *((_QWORD *)this + 5);
  v67 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v12 + 56LL))(
         v12,
         MF_DISABLE_LOCALLY_REGISTERED_PLUGINS,
         &v67) >= 0 )
    v13 = v67;
  else
    v13 = 0;
  if ( v13 != 1 )
    v7 |= 0x10u;
  guidCategory = MFT_CATEGORY_VIDEO_PROCESSOR;
  v14 = MFTEnumEx(&guidCategory, v7, 0, 0, &v64, &pnumMFTActivate);
  if ( v14 < 0 )
  {
    v23 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v23 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v26 = (CallStackTracing *)((char *)v23 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v23 + 3));
      if ( Value )
      {
        v26 = Value;
      }
      else if ( !GetLastError() )
      {
        v31 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v30, v29);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
        if ( v33 )
          v26 = (CallStackContext *)v33;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v26 + 499) != v14 )
        CallStackContext::TraceFailure(v26, "CMFReadWriteTransformFactory::ConfigureVideoProcessor", 1304, v14);
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v24 = 121;
LABEL_145:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, this, v14);
    goto LABEL_41;
  }
  v15 = 0;
LABEL_17:
  if ( v15 < 2 )
  {
    if ( v15 != 1 )
    {
LABEL_19:
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i > pnumMFTActivate )
        {
          ++v15;
          goto LABEL_17;
        }
        ppv[0] = 0;
        *(_QWORD *)&guidCategory.Data1 = 0;
        v67 = 0;
        if ( v5 )
        {
          (*(void (__fastcall **)(struct IMFReadWriteTransform *))(*(_QWORD *)v5 + 256LL))(v5);
          ATL::AtlComPtrAssign(&v65, 0);
          v5 = (struct IMFReadWriteTransform *)v65;
        }
        v17 = (_DWORD)i == pnumMFTActivate
            ? CoCreateInstance(
                &GUID_98230571_0087_4204_b020_3282538e57d3,
                0,
                1u,
                &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
                ppv)
            : ((__int64 (__fastcall *)(IMFActivate *, GUID *, LPVOID *))v64[i]->lpVtbl->ActivateObject)(
                v64[i],
                &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
                ppv);
        if ( v17 < 0 )
          break;
        (*(void (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)ppv[0] + 64LL))(ppv[0], &guidCategory);
        if ( v8 )
        {
          if ( !*(_QWORD *)&guidCategory.Data1 )
            goto LABEL_33;
          if ( !(unsigned int)MFGetAttributeUINT32(*(_QWORD *)&guidCategory.Data1, MFT_SUPPORT_3DVIDEO, 0) )
            goto LABEL_31;
        }
        v14 = CMFReadWriteTransformFactory::CheckUpDownTypes(
                this,
                *((struct IMFMediaType **)this + 3),
                (struct IMFTransform *)ppv[0],
                &v67);
        if ( v14 < 0 )
        {
          v44 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v44 + 8) )
          {
            v46 = (CallStackTracing *)((char *)v44 + 208);
            v47 = GetLastError();
            v48 = (CallStackContext *)TlsGetValue(*((_DWORD *)v44 + 3));
            if ( v48 )
            {
              v46 = v48;
            }
            else if ( !GetLastError() )
            {
              v50 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
                CallStackTracing::s_wpInstance = v51;
                if ( v51
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                {
                  v50 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v50 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v52 = (**(__int64 (__fastcall ***)(CallStackTracing *))v50)(v50);
              if ( v52 )
                v46 = (CallStackContext *)v52;
            }
            SetLastError(v47);
            if ( *((_DWORD *)v46 + 499) != v14 )
              CallStackContext::TraceFailure(v46, "CMFReadWriteTransformFactory::ConfigureVideoProcessor", 1372, v14);
          }
          if ( g_wppLevels )
          {
            v36 = 123;
LABEL_104:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids,
              this,
              v14);
          }
LABEL_105:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&guidCategory);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(ppv);
          goto LABEL_41;
        }
        if ( !v67 )
          goto LABEL_31;
        v70 = 0;
        if ( *(_QWORD *)&guidCategory.Data1
          && (*(int (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 5) + 56LL))(
               *((_QWORD *)this + 5),
               MF_ENABLE_3DVIDEO_OUTPUT,
               &v70) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)&guidCategory.Data1 + 168LL))(
            *(_QWORD *)&guidCategory.Data1,
            MF_ENABLE_3DVIDEO_OUTPUT,
            v70);
        }
        v17 = CMFReadWriteTransformFactory::SetVideoProcessorAttributes(
                (struct IMFTransform *)ppv[0],
                *((struct IMFAttributes **)this + 5));
        if ( v17 < 0 )
        {
          if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
          {
            v25 = 124;
LABEL_62:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              v25,
              &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids,
              this,
              v17);
          }
          goto LABEL_31;
        }
        v53 = (struct IMFAttributes *)*((_QWORD *)this + 5);
        v54 = *((_DWORD *)this + 1);
        pppMFTActivate = (IMFActivate ***)*((_QWORD *)this + 4);
        v66 = MFT_CATEGORY_VIDEO_PROCESSOR;
        v55 = CMFReadWriteTransformFactory::CreateTransformWrapper(
                v54,
                (struct IMFTransform *)ppv[0],
                &v66,
                v53,
                (struct IMFMediaType *)pppMFTActivate,
                (struct IMFReadWriteTransform **)&v65);
        v5 = (struct IMFReadWriteTransform *)v65;
        if ( v55 >= 0 )
        {
          if ( *((_QWORD *)this + 6) )
          {
            v56 = MFGetAttributeUINT32(*((_QWORD *)this + 5), &MF_SOURCE_READER_DISABLE_DXVA, 0);
            v14 = (*(__int64 (__fastcall **)(struct IMFReadWriteTransform *, _QWORD))(*(_QWORD *)v5 + 152LL))(
                    v5,
                    *((_QWORD *)this + 6));
            if ( v14 < 0 )
            {
              v34 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v58, v57);
                CallStackTracing::s_wpInstance = v35;
                if ( v35
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                {
                  v34 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v34 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              if ( *((_BYTE *)v34 + 8) )
              {
                v37 = (CallStackTracing *)((char *)v34 + 208);
                v38 = GetLastError();
                v39 = (CallStackContext *)TlsGetValue(*((_DWORD *)v34 + 3));
                if ( v39 )
                {
                  v37 = v39;
                }
                else if ( !GetLastError() )
                {
                  v41 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                    CallStackTracing::s_wpInstance = v42;
                    if ( v42
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                    {
                      v41 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v41 = (CallStackTracing *)&qword_18010C230;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                    }
                  }
                  v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
                  if ( v43 )
                    v37 = (CallStackContext *)v43;
                }
                SetLastError(v38);
                if ( *((_DWORD *)v37 + 499) != v14 )
                  CallStackContext::TraceFailure(
                    v37,
                    "CMFReadWriteTransformFactory::ConfigureVideoProcessor",
                    1410,
                    v14);
              }
              if ( g_wppLevels )
              {
                v36 = 126;
                goto LABEL_104;
              }
              goto LABEL_105;
            }
            if ( !v56 && (*(unsigned int (__fastcall **)(struct IMFReadWriteTransform *))(*(_QWORD *)v5 + 144LL))(v5) )
              (*(void (__fastcall **)(struct IMFReadWriteTransform *, __int64))(*(_QWORD *)v5 + 160LL))(v5, 1);
          }
          if ( *((_QWORD *)this + 1) )
            v59 = CMFReadWriteTransformFactory::ConnectConverterToEncoder(this, v5);
          else
            v59 = CMFReadWriteTransformFactory::ConnectConverterUsingProvidedMediaType(this, v5);
          v14 = v59;
          if ( v59 >= 0 )
          {
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&guidCategory);
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(ppv);
            v60 = v5;
            v5 = 0;
            *v68 = v60;
            goto LABEL_41;
          }
          if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              127,
              &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids,
              this,
              v59);
        }
        else if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            125,
            &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids,
            this,
            v55);
        }
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&guidCategory);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(ppv);
LABEL_35:
        ;
      }
      if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
      {
        v25 = 122;
        goto LABEL_62;
      }
LABEL_31:
      if ( *(_QWORD *)&guidCategory.Data1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&guidCategory.Data1 + 16LL))(*(_QWORD *)&guidCategory.Data1);
LABEL_33:
      if ( ppv[0] )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      goto LABEL_35;
    }
    if ( v8 )
    {
      v8 = 0;
      goto LABEL_19;
    }
  }
  if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 128, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, this);
  v14 = -1072875819;
  if ( g_wppLevels >= 0x10u )
  {
    v24 = 129;
    goto LABEL_145;
  }
LABEL_41:
  for ( j = 0; (unsigned int)j < pnumMFTActivate; j = (unsigned int)(j + 1) )
  {
    v21 = v64[j];
    if ( v21 )
    {
      ((void (__fastcall *)(IMFActivate *))v21->lpVtbl->Release)(v21);
      v64[j] = 0;
    }
  }
  CoTaskMemFree(v64);
  v64 = 0;
  if ( v5 )
  {
    (*(void (__fastcall **)(struct IMFReadWriteTransform *))(*(_QWORD *)v5 + 256LL))(v5);
    (*(void (__fastcall **)(struct IMFReadWriteTransform *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v67);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180071af4  mov     [rsp-40h+arg_8], rdx
0x180071af9  push    rbp
0x180071afa  push    rbx
0x180071afb  push    rsi
0x180071afc  push    rdi
0x180071afd  push    r12
0x180071aff  push    r13
0x180071b01  push    r14
0x180071b03  push    r15
0x180071b05  mov     rbp, rsp
0x180071b08  sub     rsp, 78h
0x180071b0c  mov     rsi, rdx
0x180071b0f  mov     r15, rcx
0x180071b12  lea     rdx, aCmfreadwritetr_124; "CMFReadWriteTransformFactory::Configure"...
0x180071b19  mov     r8d, 4E7h; int
0x180071b1f  lea     rcx, [rbp+arg_0]; this
0x180071b23  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071b28  mov     rcx, [r15+18h]
0x180071b2c  lea     r8, [rbp+arg_0]
0x180071b30  xor     r14d, r14d
0x180071b33  lea     rdx, MF_MT_VIDEO_3D
0x180071b3a  mov     [rbp+var_28], r14
0x180071b3e  mov     ebx, r14d
0x180071b41  mov     [rbp+arg_10], r14d
0x180071b45  mov     rax, [rcx]
0x180071b48  mov     [rbp+var_20], rbx
0x180071b4c  lea     edi, [r14+63h]
0x180071b50  mov     [rbp+arg_0], r14d
0x180071b54  mov     rax, [rax+38h]
0x180071b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b5d  mov     r13d, r14d
0x180071b60  test    eax, eax
0x180071b62  jns     loc_180072264
0x180071b68  mov     [rsi], r14
0x180071b6b  lea     r8, [rbp+arg_0]
0x180071b6f  mov     rcx, [r15+28h]
0x180071b73  lea     rdx, MF_READWRITE_ENABLE_HARDWARE_TRANSFORMS
0x180071b7a  mov     [rbp+arg_0], ebx
0x180071b7d  mov     rax, [rcx]
0x180071b80  mov     rax, [rax+38h]
0x180071b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b89  test    eax, eax
0x180071b8b  jns     loc_18007226D
0x180071b91  xor     eax, eax
0x180071b93  cmp     eax, 1
0x180071b96  mov     [rbp+arg_0], ebx
0x180071b99  mov     ecx, 67h ; 'g'
0x180071b9e  lea     r8, [rbp+arg_0]
0x180071ba2  cmovz   edi, ecx
0x180071ba5  lea     rdx, MF_LOCAL_PLUGIN_CONTROL_POLICY
0x180071bac  mov     rcx, [r15+28h]
0x180071bb0  mov     rax, [rcx]
0x180071bb3  mov     rax, [rax+38h]
0x180071bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071bbc  test    eax, eax
0x180071bbe  jns     loc_180072275
0x180071bc4  xor     eax, eax
0x180071bc6  cmp     eax, 2
0x180071bc9  jnz     loc_18007227D
0x180071bcf  or      edi, 140h
0x180071bd5  mov     rcx, [r15+28h]
0x180071bd9  lea     r8, [rbp+arg_0]
0x180071bdd  lea     rdx, MF_DISABLE_LOCALLY_REGISTERED_PLUGINS
0x180071be4  mov     [rbp+arg_0], ebx
0x180071be7  mov     rax, [rcx]
0x180071bea  mov     rax, [rax+38h]
0x180071bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071bf3  test    eax, eax
0x180071bf5  jns     loc_1800722A1
0x180071bfb  xor     eax, eax
0x180071bfd  cmp     eax, 1
0x180071c00  jz      short loc_180071C05
0x180071c02  or      edi, 10h
0x180071c05  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_PROCESSOR.Data1
0x180071c0c  lea     rax, [rbp+arg_10]
0x180071c10  xor     r9d, r9d; pOutputType
0x180071c13  mov     [rsp+78h+pnumMFTActivate], rax; pnumMFTActivate
0x180071c18  lea     rcx, [rbp+guidCategory]; guidCategory
0x180071c1c  lea     rax, [rbp+var_28]
0x180071c20  xor     r8d, r8d; pInputType
0x180071c23  mov     edx, edi; Flags
0x180071c25  mov     [rsp+78h+pppMFTActivate], rax; pppMFTActivate
0x180071c2a  movdqu  xmmword ptr [rbp+guidCategory.Data1], xmm0
0x180071c2f  call    cs:__imp_MFTEnumEx
0x180071c35  mov     edi, eax
0x180071c37  test    eax, eax
0x180071c39  js      loc_180071E50
0x180071c3f  xor     r12d, r12d
0x180071c42  cmp     r12d, 2
0x180071c46  jnb     loc_180071DA6
0x180071c4c  cmp     r12d, 1
0x180071c50  jz      loc_180071D9D
0x180071c56  xor     r14d, r14d
0x180071c59  cmp     r14d, [rbp+arg_10]
0x180071c5d  ja      loc_180071E48
0x180071c63  mov     [rbp+ppv], 0
0x180071c6b  mov     qword ptr [rbp+guidCategory.Data1], 0
0x180071c73  mov     [rbp+arg_0], 0
0x180071c7a  test    rbx, rbx
0x180071c7d  jnz     loc_180071D47
0x180071c83  cmp     r14d, [rbp+arg_10]
0x180071c87  jnz     loc_180071D76
0x180071c8d  xor     edx, edx; pUnkOuter
0x180071c8f  lea     rax, [rbp+ppv]
0x180071c93  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x180071c9a  mov     [rsp+78h+pppMFTActivate], rax; ppv
0x180071c9f  lea     rcx, _GUID_98230571_0087_4204_b020_3282538e57d3; rclsid
0x180071ca6  lea     r8d, [rdx+1]; dwClsContext
0x180071caa  call    cs:__imp_CoCreateInstance
0x180071cb0  test    eax, eax
0x180071cb2  js      loc_180071E80
0x180071cb8  mov     rcx, [rbp+ppv]
0x180071cbc  lea     rdx, [rbp+guidCategory]
0x180071cc0  mov     rax, [rcx]
0x180071cc3  mov     rax, [rax+40h]
0x180071cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ccc  test    r13d, r13d
0x180071ccf  jz      short loc_180071CED
0x180071cd1  mov     rcx, qword ptr [rbp+guidCategory.Data1]
0x180071cd5  test    rcx, rcx
0x180071cd8  jz      short loc_180071D2A
0x180071cda  xor     r8d, r8d
0x180071cdd  lea     rdx, MFT_SUPPORT_3DVIDEO
0x180071ce4  call    MFGetAttributeUINT32
0x180071ce9  test    eax, eax
0x180071ceb  jz      short loc_180071D15
0x180071ced  mov     r8, [rbp+ppv]; struct IMFTransform *
0x180071cf1  lea     r9, [rbp+arg_0]; int *
0x180071cf5  mov     rdx, [r15+18h]; struct IMFMediaType *
0x180071cf9  mov     rcx, r15; this
0x180071cfc  call    ?CheckUpDownTypes@CMFReadWriteTransformFactory@@AEAAJPEAUIMFMediaType@@PEAUIMFTransform@@PEAH@Z; CMFReadWriteTransformFactory::CheckUpDownTypes(IMFMediaType *,IMFTransform *,int *)
0x180071d01  mov     edi, eax
0x180071d03  test    eax, eax
0x180071d05  js      loc_18007210D
0x180071d0b  cmp     [rbp+arg_0], 0
0x180071d0f  jnz     loc_180071E94
0x180071d15  mov     rcx, qword ptr [rbp+guidCategory.Data1]
0x180071d19  test    rcx, rcx
0x180071d1c  jz      short loc_180071D2A
0x180071d1e  mov     rax, [rcx]
0x180071d21  mov     rax, [rax+10h]
0x180071d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d2a  mov     rcx, [rbp+ppv]
0x180071d2e  test    rcx, rcx
0x180071d31  jz      short loc_180071D3F
0x180071d33  mov     rax, [rcx]
0x180071d36  mov     rax, [rax+10h]
0x180071d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d3f  inc     r14d
0x180071d42  jmp     loc_180071C59
0x180071d47  mov     rax, [rbx]
0x180071d4a  mov     rcx, rbx
0x180071d4d  mov     rax, [rax+100h]
0x180071d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d59  test    rbx, rbx
0x180071d5c  jz      loc_180071C83
0x180071d62  xor     edx, edx; struct IUnknown *
0x180071d64  lea     rcx, [rbp+var_20]; struct IUnknown **
0x180071d68  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180071d6d  mov     rbx, [rbp+var_20]
0x180071d71  jmp     loc_180071C83
0x180071d76  mov     rax, [rbp+var_28]
0x180071d7a  lea     r8, [rbp+ppv]
0x180071d7e  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x180071d85  mov     rcx, [rax+r14*8]
0x180071d89  mov     rax, [rcx]
0x180071d8c  mov     rax, [rax+108h]
0x180071d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d98  jmp     loc_180071CB0
0x180071d9d  test    r13d, r13d
0x180071da0  jnz     loc_1800722A9
0x180071da6  cmp     cs:byte_18010CAF1, 10h
0x180071dad  jnb     loc_18007241A
0x180071db3  mov     edi, 0C00D36D5h
0x180071db8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180071dbf  jnb     loc_18007243E
0x180071dc5  xor     esi, esi
0x180071dc7  xor     r15d, r15d
0x180071dca  cmp     [rbp+arg_10], r15d
0x180071dce  jbe     short loc_180071DF8
0x180071dd0  mov     rax, [rbp+var_28]
0x180071dd4  mov     rcx, [rax+rsi*8]
0x180071dd8  test    rcx, rcx
0x180071ddb  jz      short loc_180071DF1
0x180071ddd  mov     rax, [rcx]
0x180071de0  mov     rax, [rax+10h]
0x180071de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071de9  mov     rax, [rbp+var_28]
0x180071ded  mov     [rax+rsi*8], r15
0x180071df1  inc     esi
0x180071df3  cmp     esi, [rbp+arg_10]
0x180071df6  jb      short loc_180071DD0
0x180071df8  mov     rcx, [rbp+var_28]; pv
0x180071dfc  call    cs:__imp_CoTaskMemFree
0x180071e02  mov     [rbp+var_28], r15
0x180071e06  test    rbx, rbx
0x180071e09  jz      short loc_180071E2C
0x180071e0b  mov     rax, [rbx]
0x180071e0e  mov     rcx, rbx
0x180071e11  mov     rax, [rax+100h]
0x180071e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e1d  mov     rcx, [rbx]
0x180071e20  mov     rax, [rcx+10h]
0x180071e24  mov     rcx, rbx
0x180071e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e2c  lea     rcx, [rbp+arg_0]; this
0x180071e30  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180071e35  mov     eax, edi
0x180071e37  add     rsp, 78h
0x180071e3b  pop     r15
0x180071e3d  pop     r14
0x180071e3f  pop     r13
0x180071e41  pop     r12
0x180071e43  pop     rdi
0x180071e44  pop     rsi
0x180071e45  pop     rbx
0x180071e46  pop     rbp
0x180071e47  retn
0x180071e48  inc     r12d
0x180071e4b  jmp     loc_180071C42
0x180071e50  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e57  test    rsi, rsi
0x180071e5a  jz      loc_180071F0F
0x180071e60  cmp     [rsi+8], bl
0x180071e63  jnz     loc_180071F20
0x180071e69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071e70  jb      loc_180071DC5
0x180071e76  mov     edx, 79h ; 'y'
0x180071e7b  jmp     loc_180072443
0x180071e80  cmp     cs:byte_18010CAF1, 10h
0x180071e87  jb      loc_180071D15
0x180071e8d  mov     edx, 7Ah ; 'z'
0x180071e92  jmp     short loc_180071EEC
0x180071e94  cmp     qword ptr [rbp+guidCategory.Data1], 0
0x180071e99  mov     [rbp+arg_18], 0
0x180071ea0  jz      short loc_180071EC5
0x180071ea2  mov     rcx, [r15+28h]
0x180071ea6  lea     r8, [rbp+arg_18]
0x180071eaa  lea     rdx, MF_ENABLE_3DVIDEO_OUTPUT
0x180071eb1  mov     rax, [rcx]
0x180071eb4  mov     rax, [rax+38h]
0x180071eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ebd  test    eax, eax
0x180071ebf  jns     loc_1800722B1
0x180071ec5  mov     rdx, [r15+28h]; struct IMFAttributes *
0x180071ec9  mov     rcx, [rbp+ppv]; struct IMFTransform *
0x180071ecd  call    ?SetVideoProcessorAttributes@CMFReadWriteTransformFactory@@SAJPEAUIMFTransform@@PEAUIMFAttributes@@@Z; CMFReadWriteTransformFactory::SetVideoProcessorAttributes(IMFTransform *,IMFAttributes *)
0x180071ed2  test    eax, eax
0x180071ed4  jns     loc_1800722D4
0x180071eda  cmp     cs:byte_18010CAF1, 10h
0x180071ee1  jb      loc_180071D15
0x180071ee7  mov     edx, 7Ch ; '|'
0x180071eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180071ef3  lea     r8, WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids
0x180071efa  mov     r9, r15
0x180071efd  mov     dword ptr [rsp+78h+pppMFTActivate], eax
0x180071f01  mov     rcx, [rcx+38h]
0x180071f05  call    WPP_SF_qD
0x180071f0a  jmp     loc_180071D15
0x180071f0f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180071f14  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f1b  jmp     loc_180071E60
0x180071f20  lea     r14, [rsi+0D0h]
0x180071f27  call    cs:__imp_GetLastError
0x180071f2d  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180071f30  mov     r12d, eax
0x180071f33  call    cs:__imp_TlsGetValue
0x180071f39  test    rax, rax
0x180071f3c  jnz     short loc_180071F8E
0x180071f3e  call    cs:__imp_GetLastError
0x180071f44  test    eax, eax
0x180071f46  jnz     short loc_180071F91
0x180071f48  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f4f  test    rsi, rsi
0x180071f52  jnz     short loc_180071F77
0x180071f54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071f5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f61  mov     rcx, rax
0x180071f64  test    rax, rax
0x180071f67  jnz     short loc_180071FC4
0x180071f69  lea     rsi, qword_18010C230
0x180071f70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f77  mov     rax, [rsi]
0x180071f7a  mov     rcx, rsi
0x180071f7d  mov     rax, [rax]
0x180071f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f85  test    rax, rax
0x180071f88  cmovnz  r14, rax
0x180071f8c  jmp     short loc_180071F91
0x180071f8e  mov     r14, rax
0x180071f91  mov     ecx, r12d; dwErrCode
0x180071f94  call    cs:__imp_SetLastError
0x180071f9a  cmp     [r14+7CCh], edi
0x180071fa1  jz      loc_180071E69
0x180071fa7  mov     r9d, edi; int
0x180071faa  lea     rdx, aCmfreadwritetr_124; "CMFReadWriteTransformFactory::Configure"...
0x180071fb1  mov     r8d, 518h; int
0x180071fb7  mov     rcx, r14; this
0x180071fba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071fbf  jmp     loc_180071E69
  ... truncated ...
```
