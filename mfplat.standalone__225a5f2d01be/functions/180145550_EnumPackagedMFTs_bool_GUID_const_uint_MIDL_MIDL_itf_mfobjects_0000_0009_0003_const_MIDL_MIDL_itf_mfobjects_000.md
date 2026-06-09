# EnumPackagedMFTs(bool,_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)

- ea: `0x180145550`
- end: `0x180146485`
- name: `?EnumPackagedMFTs@@YAJ_NAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@2PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `3893`
- prototype: `int(bool, const struct _GUID *, unsigned int, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFActivate ***, unsigned int *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180092ba0`

## callees

- `0x180004870`
- `0x180015b20`
- `0x18001fce4`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180056284`
- `0x1800807f8`
- `0x1800883f0`
- `0x18008ce34`
- `0x1800916b8`
- `0x1800a93a4`
- `0x1800ac4b4`
- `0x1800e7c0c`
- `0x1800ee5f4`
- `0x1801200d0`
- `0x180121575`
- `0x180122e90`
- `0x180125958`
- `0x180144be0`
- `0x180144c80`
- `0x180145550`
- `0x1801478c8`
- `0x18019343c`
- `0x1801934b0`
- `0x180193c08`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180145928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014642c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180145928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014642c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801458f3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801458f3`
- `ext-ms-mf-pal-l2-1-0!XboxValidDecoderUsage` at `0x180145659`
- `ext-ms-mf-pal-l2-1-0!XboxValidDecoderUsage` at `0x180145659`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18014581a`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18014581a`

## pseudocode

```c
__int64 __fastcall EnumPackagedMFTs(
        char a1,
        const struct _GUID *a2,
        unsigned int a3,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a4,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a5,
        struct IMFActivate ***a6,
        unsigned int *a7)
{
  unsigned int v7; // r12d
  char v9; // si
  const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v10; // r14
  bool v11; // zf
  const unsigned __int16 *v12; // rdi
  const struct KnownPackageInfo near *const *v13; // rbx
  const struct KnownPackageInfo near *const *v14; // r12
  const struct KnownPackageInfo near *const *v15; // rdi
  unsigned int j; // ecx
  unsigned int i; // r8d
  unsigned int v18; // r15d
  unsigned int v19; // esi
  __int64 v20; // r14
  unsigned int v21; // esi
  __int64 v22; // r14
  __int64 v23; // rcx
  CallStackTracing *v24; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rdx
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  unsigned int v29; // r15d
  enum MF_PLUGIN_CONTROL_POLICY v30; // r12d
  __int64 v31; // rdx
  struct IMFActivate *v32; // rsi
  bool v33; // r14
  unsigned int *v34; // r14
  unsigned __int64 v35; // rcx
  __int64 v36; // rdx
  void *v37; // rcx
  __int64 v38; // r8
  void **v39; // r9
  void *v40; // r10
  int v41; // eax
  __int64 v42; // rcx
  _QWORD *v43; // rax
  unsigned int v44; // esi
  unsigned __int64 v45; // rcx
  __int64 v46; // rdx
  void *v47; // rcx
  void **v48; // r9
  void *v49; // r10
  CallStackTracing *v50; // rcx
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  CallStackTracing *v56; // rcx
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  CallStackTracing *v60; // rcx
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  CallStackTracing *v65; // rcx
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // r14
  __int64 v74; // rdi
  struct IMFActivate ***v75; // rbx
  unsigned int *v76; // r15
  struct IMFActivate *v77; // rcx
  LPVOID *v78; // rdx
  unsigned int k; // edi
  __int64 v80; // rcx
  char v82[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFActivate *v84; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v85; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v86; // [rsp+60h] [rbp-A0h]
  CallStackScopeTrace v87; // [rsp+68h] [rbp-98h] BYREF
  int v88; // [rsp+6Ch] [rbp-94h]
  unsigned int v89; // [rsp+70h] [rbp-90h] BYREF
  struct IMFActivate ***v90; // [rsp+78h] [rbp-88h]
  __int64 *v91; // [rsp+80h] [rbp-80h] BYREF
  const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v92; // [rsp+88h] [rbp-78h]
  const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v93; // [rsp+90h] [rbp-70h]
  __int64 v94; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v95; // [rsp+A0h] [rbp-60h]
  __int64 v96; // [rsp+A4h] [rbp-5Ch]
  Windows::Internal::StringReference v97; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v98[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v99; // [rsp+F0h] [rbp-10h]
  char v100; // [rsp+F2h] [rbp-Eh]
  __int128 v101; // [rsp+100h] [rbp+0h]
  int v102; // [rsp+110h] [rbp+10h]
  void **v103; // [rsp+118h] [rbp+18h]
  __int64 v104; // [rsp+120h] [rbp+20h]
  __int16 v105; // [rsp+138h] [rbp+38h]
  char v106; // [rsp+13Ah] [rbp+3Ah]
  __int64 v107; // [rsp+280h] [rbp+180h]
  int v108; // [rsp+288h] [rbp+188h]
  __int64 v109; // [rsp+290h] [rbp+190h]
  _BYTE v110[1280]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v7 = a3;
  v88 = a3;
  v9 = a1;
  v82[0] = a1;
  v93 = a5;
  v90 = a6;
  v10 = a4;
  v86 = a7;
  v92 = a4;
  CallStackScopeTrace::CallStackScopeTrace(&v87, "EnumPackagedMFTs", 2336);
  *a7 = 0;
  *a6 = 0;
  v11 = *(_QWORD *)&a2->Data1 == MFT_CATEGORY_VIDEO_RENDERER_EFFECT;
  v91 = 0;
  v94 = 0;
  v96 = 0;
  v95 = 0;
  if ( v11 && *(_QWORD *)a2->Data4 == 0x95DAC206DFE0E78AuLL )
  {
    v12 = L"windows.videoRendererEffect";
    goto LABEL_48;
  }
  v13 = 0;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MFT_CATEGORY_VIDEO_DECODER.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)MFT_CATEGORY_VIDEO_DECODER.Data4 )
  {
    if ( (unsigned __int8)IsXboxValidDecoderUsagePresent() )
    {
      *(_OWORD *)&v97._hstring = *((_OWORD *)v10 + 1);
      if ( !(unsigned int)XboxValidDecoderUsage(&v97) )
        goto LABEL_216;
    }
  }
  if ( v10 )
    v14 = (const struct KnownPackageInfo near *const *)((char *)v10 + 16);
  else
    v14 = 0;
  if ( v93 )
    v15 = (const struct KnownPackageInfo near *const *)((char *)v93 + 16);
  else
    v15 = 0;
  if ( v14 )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( *v14 == (const struct KnownPackageInfo near *const)*((_QWORD *)&guidSkipCodecPackQuerySubtypes.Data1 + 2 * i)
        && *((_QWORD *)v14 + 1) == *(_QWORD *)&guidSkipCodecPackQuerySubtypes.Data4[16 * i]
        || v15
        && *v15 == (const struct KnownPackageInfo near *const)*((_QWORD *)&guidSkipCodecPackQuerySubtypes.Data1 + 2 * i)
        && *((_QWORD *)v15 + 1) == *(_QWORD *)&guidSkipCodecPackQuerySubtypes.Data4[16 * i] )
      {
        goto LABEL_216;
      }
    }
LABEL_28:
    v18 = 0;
    while ( 1 )
    {
      v13 = &g_KnownPackages + 13 * v18;
      if ( v14 )
        break;
LABEL_35:
      if ( v15 )
      {
        v21 = 0;
        do
        {
          v22 = 2LL * v21;
          if ( memcmp_0((char *)&v13[v22 + 6] + 4, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
          {
            if ( *(const struct KnownPackageInfo near *const *)((char *)&v13[v22 + 6] + 4) == *v15
              && *(const struct KnownPackageInfo near *const *)((char *)&v13[v22 + 7] + 4) == (const struct KnownPackageInfo near *const)*((_QWORD *)v15 + 1) )
            {
              goto LABEL_43;
            }
          }
        }
        while ( ++v21 < 2 );
      }
      if ( ++v18 >= 0x10 )
      {
        v13 = 0;
        goto LABEL_43;
      }
    }
    v19 = 0;
    while ( 1 )
    {
      v20 = 2LL * v19;
      if ( memcmp_0((char *)&v13[v20 + 2] + 4, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        if ( *(const struct KnownPackageInfo near *const *)((char *)&v13[v20 + 2] + 4) == *v14
          && *(const struct KnownPackageInfo near *const *)((char *)&v13[v20 + 3] + 4) == (const struct KnownPackageInfo near *const)*((_QWORD *)v14 + 1) )
        {
          break;
        }
      }
      if ( ++v19 >= 2 )
        goto LABEL_35;
    }
LABEL_43:
    v9 = v82[0];
    v10 = v92;
    goto LABEL_44;
  }
  if ( v15 )
  {
    for ( j = 0; j < 2; ++j )
    {
      if ( *v15 == (const struct KnownPackageInfo near *const)*((_QWORD *)&guidSkipCodecPackQuerySubtypes.Data1 + 2 * j)
        && *((_QWORD *)v15 + 1) == *(_QWORD *)&guidSkipCodecPackQuerySubtypes.Data4[16 * j] )
      {
        goto LABEL_216;
      }
    }
    goto LABEL_28;
  }
LABEL_44:
  v7 = v88;
  v12 = L"windows.mediaCodec";
  if ( ((v88 & 0x400) == 0 || (v88 & 0x240) == 0x240) && v13 )
    v12 = (const unsigned __int16 *)*((_QWORD *)v13 + 11);
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  Windows::Internal::StringReference::_ConstructorHelper(&v97, v12);
  LOBYTE(v23) = v9;
  LODWORD(v13) = GetMediaComponentPackageInfo(v23, v97._hstring, &v91);
  if ( (int)v13 < 0 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v24 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v24->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v24);
      if ( ThreadRelativeContext->m_result != (_DWORD)v13 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "EnumPackagedMFTs", 2388, (int)v13);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_208;
    v26 = 52;
LABEL_58:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
      0,
      (_DWORD)v13);
LABEL_208:
    v34 = v86;
    goto LABEL_209;
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
  {
    lpsz = 0;
    if ( StringFromCLSID(a2, &lpsz) >= 0 )
    {
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids, lpsz);
      CoTaskMemFree(lpsz);
    }
  }
  v89 = 0;
  LODWORD(v13) = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v91 + 56))(v91, &v89);
  if ( (int)v13 < 0 )
  {
    v27 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v27 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v27->m_fEnabled )
    {
      v28 = CallStackTracing::GetThreadRelativeContext(v27);
      if ( v28->m_result != (_DWORD)v13 )
        CallStackContext::TraceFailure(v28, "EnumPackagedMFTs", 2401, (int)v13);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_208;
    v26 = 54;
    goto LABEL_58;
  }
  v29 = 0;
  if ( v89 )
  {
    v30 = PolicyFromMFTFlags(v7);
    do
    {
      lpsz = 0;
      v85 = 0;
      v82[0] = 0;
      v31 = *v91;
      v84 = 0;
      LODWORD(v13) = (*(__int64 (__fastcall **)(__int64 *, _QWORD, LPOLESTR *))(v31 + 48))(v91, v29, &lpsz);
      if ( (int)v13 < 0 )
      {
        v70 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v70 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v70->m_fEnabled )
        {
          v71 = CallStackTracing::GetThreadRelativeContext(v70);
          if ( v71->m_result != (_DWORD)v13 )
            CallStackContext::TraceFailure(v71, "EnumPackagedMFTs", 2412, (int)v13);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_121;
        v69 = 55;
LABEL_188:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v69,
          &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
          0,
          (_DWORD)v13);
        goto LABEL_121;
      }
      LODWORD(v13) = (**(__int64 (__fastcall ***)(LPOLESTR, GUID *, __int64 *))lpsz)(
                       lpsz,
                       &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                       &v85);
      if ( (int)v13 < 0 )
      {
        v67 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v67 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v67->m_fEnabled )
        {
          v68 = CallStackTracing::GetThreadRelativeContext(v67);
          if ( v68->m_result != (_DWORD)v13 )
            CallStackContext::TraceFailure(v68, "EnumPackagedMFTs", 2414, (int)v13);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_121;
        v69 = 56;
        goto LABEL_188;
      }
      if ( *(_QWORD *)&a2->Data1 == MFT_CATEGORY_VIDEO_RENDERER_EFFECT && *(_QWORD *)a2->Data4 == 0x95DAC206DFE0E78AuLL )
      {
        v105 = 0;
        v106 = 0;
        memset(v98, 0, sizeof(v98));
        v103 = &CTDynArray<_GUID,20>::`vftable';
        v99 = 0;
        v100 = 0;
        v101 = 0;
        v102 = 0;
        v104 = 0;
        v107 = 0;
        v108 = 0;
        v109 = 0;
        LODWORD(v13) = MatchAndGetPackagedRendererEffectAttributes(v85, (unsigned int)v88, v10, v98, v82);
        if ( (int)v13 < 0 )
        {
          v56 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v56 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v56 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v56->m_fEnabled )
          {
            v57 = CallStackTracing::GetThreadRelativeContext(v56);
            if ( v57->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v57, "EnumPackagedMFTs", 2424, (int)v13);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_120;
          v53 = 57;
LABEL_119:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v53,
            &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
            0,
            (_DWORD)v13);
          goto LABEL_120;
        }
        if ( !v82[0] )
        {
          VideoRendererPackInfo::~VideoRendererPackInfo((VideoRendererPackInfo *)v98);
LABEL_83:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v85);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&lpsz);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v84);
          goto LABEL_102;
        }
        LODWORD(v13) = CreateMediaExtensionActivateFromInfo((struct InprocMFTExtensionInfo *)v98, &v84);
        if ( (int)v13 < 0 )
        {
          v54 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v54 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v54 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v54->m_fEnabled )
          {
            v55 = CallStackTracing::GetThreadRelativeContext(v54);
            if ( v55->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v55, "EnumPackagedMFTs", 2431, (int)v13);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_120;
          v53 = 58;
          goto LABEL_119;
        }
        v32 = v84;
        LODWORD(v13) = SetPackagedActivateAttributes(v84, v30, (struct VideoRendererPackInfo *)v98);
        if ( (int)v13 < 0 )
        {
          v51 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v51 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v51 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v51->m_fEnabled )
          {
            v52 = CallStackTracing::GetThreadRelativeContext(v51);
            if ( v52->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v52, "EnumPackagedMFTs", 2434, (int)v13);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v53 = 59;
            goto LABEL_119;
          }
LABEL_120:
          VideoRendererPackInfo::~VideoRendererPackInfo((VideoRendererPackInfo *)v98);
          goto LABEL_121;
        }
        v33 = ExtensionInfo::IsLicenseCheckRequired((ExtensionInfo *)v98);
        VideoRendererPackInfo::~VideoRendererPackInfo((VideoRendererPackInfo *)v98);
      }
      else
      {
        CodecPackInfo::CodecPackInfo((CodecPackInfo *)v110);
        LODWORD(v13) = MatchAndGetPackagedMFTAttributes(v85, a2, (unsigned int)v88, v10, v93, v110, v82);
        if ( (int)v13 < 0 )
        {
          v65 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v65 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v65 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v65->m_fEnabled )
          {
            v66 = CallStackTracing::GetThreadRelativeContext(v65);
            if ( v66->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v66, "EnumPackagedMFTs", 2448, (int)v13);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_160;
          v62 = 60;
LABEL_159:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v62,
            &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
            0,
            (_DWORD)v13);
          goto LABEL_160;
        }
        if ( !v82[0] || (unsigned __int8)SkipPackagedEncoderHMFT(a2, v110) )
        {
          CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v110);
          goto LABEL_83;
        }
        LODWORD(v13) = CreateMediaExtensionActivateFromInfo((struct InprocMFTExtensionInfo *)v110, &v84);
        if ( (int)v13 < 0 )
        {
          v63 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v63 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v63 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v63->m_fEnabled )
          {
            v64 = CallStackTracing::GetThreadRelativeContext(v63);
            if ( v64->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v64, "EnumPackagedMFTs", 2460, (int)v13);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_160;
          v62 = 61;
          goto LABEL_159;
        }
        v32 = v84;
        LODWORD(v13) = SetPackagedActivateAttributes(v84, v30, (struct CodecPackInfo *)v110);
        if ( (int)v13 < 0 )
        {
          v60 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v60 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v60->m_fEnabled )
          {
            v61 = CallStackTracing::GetThreadRelativeContext(v60);
            if ( v61->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v61, "EnumPackagedMFTs", 2463, (int)v13);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v62 = 62;
            goto LABEL_159;
          }
LABEL_160:
          CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v110);
LABEL_121:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v85);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&lpsz);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v84);
          goto LABEL_208;
        }
        v33 = ExtensionInfo::IsLicenseCheckRequired((ExtensionInfo *)v110);
        CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v110);
      }
      if ( v89 == 1 || !v33 )
      {
        v34 = v86;
        v97._hstring = 0;
        v35 = *v86 + 1;
        *v90 = 0;
        LODWORD(v13) = ULongLongMult(v35, 8u, (unsigned __int64 *)&v97);
        if ( (int)v13 >= 0 )
        {
          v41 = CTCoAllocPolicy::Realloc(v37, v36, v40, (SIZE_T)v97._hstring, v39);
          v39 = (void **)v90;
          LODWORD(v13) = v41;
        }
        if ( (int)v13 < 0 )
        {
          v58 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( ((unsigned int (__fastcall *)(CallStackTracing *, __int64, __int64, void **))stru_1801FC290.CheckVersionMatch)(
                   &stru_1801FC290,
                   2032,
                   v38,
                   v39) )
            {
              v58 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v58 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v58->m_fEnabled )
          {
            v59 = CallStackTracing::GetThreadRelativeContext(v58);
            if ( v59->m_result != (_DWORD)v13 )
              CallStackContext::TraceFailure(v59, "EnumPackagedMFTs", 2472, (int)v13);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
              0,
              (_DWORD)v13);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v85);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&lpsz);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v84);
LABEL_209:
          v78 = (LPVOID *)v90;
          if ( *v90 )
          {
            for ( k = 0; k < *v34; ++k )
            {
              v80 = *((_QWORD *)*v78 + k);
              if ( v80 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                v78 = (LPVOID *)v90;
                (*v90)[k] = 0;
              }
            }
            CoTaskMemFree(*v78);
            *v90 = 0;
          }
          *v34 = 0;
          goto LABEL_216;
        }
        v42 = *v34;
        v43 = *v39;
        v84 = 0;
        v43[v42] = v32;
        ++*v34;
      }
      else
      {
        CTUnkArray<IMFActivate>::Add(&v94, v32);
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v85);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&lpsz);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v84);
      v10 = v92;
LABEL_102:
      ++v29;
    }
    while ( v29 < v89 );
  }
  v44 = v95;
  if ( v95 )
  {
    v34 = v86;
    v97._hstring = 0;
    v45 = v95 + *v86;
    *v90 = 0;
    v88 = ULongLongMult(v45, 8u, (unsigned __int64 *)&v97);
    LODWORD(v13) = v88;
    if ( v88 >= 0 )
    {
      LODWORD(v13) = CTCoAllocPolicy::Realloc(v47, v46, v49, (SIZE_T)v97._hstring, v48);
      v88 = (int)v13;
    }
    if ( (int)v13 < 0 )
    {
      v50 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v50 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v50->m_fEnabled )
      {
        v72 = CallStackTracing::GetThreadRelativeContext(v50);
        if ( v72->m_result != (_DWORD)v13 )
          CallStackContext::TraceFailure(v72, "EnumPackagedMFTs", 2485, (int)v13);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
          0,
          (_DWORD)v13);
      goto LABEL_209;
    }
    v73 = v94;
    v74 = 0;
    v75 = v90;
    v76 = v86;
    do
    {
      v77 = *(struct IMFActivate **)(v73 + 8 * v74);
      (*v75)[(*v76)++] = v77;
      ((void (__fastcall *)(struct IMFActivate *))v77->lpVtbl->AddRef)(v77);
      v74 = (unsigned int)(v74 + 1);
    }
    while ( (unsigned int)v74 < v44 );
    LODWORD(v13) = v88;
  }
LABEL_216:
  CTUnkArray<IMFActivate>::~CTUnkArray<IMFActivate>(&v94);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  CallStackScopeTrace::~CallStackScopeTrace(&v87);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180145550  mov     [rsp-8+arg_10], rbx
0x180145555  push    rbp
0x180145556  push    rsi
0x180145557  push    rdi
0x180145558  push    r12
0x18014555a  push    r13
0x18014555c  push    r14
0x18014555e  push    r15
0x180145560  lea     rbp, [rsp-6B0h]
0x180145568  sub     rsp, 7B0h
0x18014556f  mov     rax, cs:__security_cookie
0x180145576  xor     rax, rsp
0x180145579  mov     [rbp+6E0h+var_40], rax
0x180145580  mov     rax, [rbp+6E0h+arg_20]
0x180145587  mov     r12d, r8d
0x18014558a  mov     rdi, [rbp+6E0h+arg_28]
0x180145591  mov     r13, rdx
0x180145594  mov     r15, [rbp+6E0h+arg_30]
0x18014559b  lea     rdx, aEnumpackagedmf; "EnumPackagedMFTs"
0x1801455a2  mov     [rsp+7E0h+var_774], r8d
0x1801455a7  mov     sil, cl
0x1801455aa  mov     [rsp+7E0h+var_7A0], cl
0x1801455ae  mov     r8d, 920h; int
0x1801455b4  lea     rcx, [rsp+7E0h+var_778]; this
0x1801455b9  mov     [rbp+6E0h+var_750], rax
0x1801455bd  mov     [rsp+7E0h+var_768], rdi
0x1801455c2  mov     r14, r9
0x1801455c5  mov     [rsp+7E0h+var_780], r15
0x1801455ca  mov     [rbp+6E0h+var_758], r9
0x1801455ce  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801455d3  mov     dword ptr [r15], 0
0x1801455da  mov     qword ptr [rdi], 0
0x1801455e1  mov     rax, [r13+0]
0x1801455e5  cmp     rax, cs:MFT_CATEGORY_VIDEO_RENDERER_EFFECT
0x1801455ec  mov     [rbp+6E0h+var_760], 0
0x1801455f4  mov     [rbp+6E0h+var_748], 0
0x1801455fc  mov     [rbp+6E0h+var_73C], 0
0x180145604  mov     [rbp+6E0h+var_740], 0
0x18014560b  jnz     short loc_180145626
0x18014560d  mov     rax, [r13+8]
0x180145611  cmp     rax, cs:qword_1801D7E90
0x180145618  jnz     short loc_180145626
0x18014561a  lea     rdi, aWindowsVideore; "windows.videoRendererEffect"
0x180145621  jmp     loc_1801457FA
0x180145626  mov     rax, [r13+0]
0x18014562a  xor     ebx, ebx
0x18014562c  cmp     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180145633  jnz     short loc_180145667
0x180145635  mov     rax, [r13+8]
0x180145639  cmp     rax, qword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data4
0x180145640  jnz     short loc_180145667
0x180145642  call    IsXboxValidDecoderUsagePresent
0x180145647  test    al, al
0x180145649  jz      short loc_180145667
0x18014564b  movups  xmm0, xmmword ptr [r14+10h]
0x180145650  lea     rcx, [rbp+6E0h+var_730]
0x180145654  movdqu  xmmword ptr [rbp+6E0h+var_730._hstring], xmm0
0x180145659  call    cs:__imp_XboxValidDecoderUsage
0x18014565f  test    eax, eax
0x180145661  jz      loc_18014643D
0x180145667  test    r14, r14
0x18014566a  jz      short loc_180145672
0x18014566c  lea     r12, [r14+10h]
0x180145670  jmp     short loc_180145675
0x180145672  xor     r12d, r12d
0x180145675  mov     rax, [rbp+6E0h+var_750]
0x180145679  test    rax, rax
0x18014567c  jz      short loc_180145684
0x18014567e  lea     rdi, [rax+10h]
0x180145682  jmp     short loc_180145686
0x180145684  xor     edi, edi
0x180145686  test    r12, r12
0x180145689  jnz     short loc_1801456C4
0x18014568b  test    rdi, rdi
0x18014568e  jz      loc_1801457D0
0x180145694  xor     ecx, ecx
0x180145696  lea     rdx, ?guidSkipCodecPackQuerySubtypes@@3QBU_GUID@@B; _GUID const near * const guidSkipCodecPackQuerySubtypes
0x18014569d  mov     rax, [rdi]
0x1801456a0  mov     r8d, ecx
0x1801456a3  add     r8, r8
0x1801456a6  cmp     rax, [rdx+r8*8]
0x1801456aa  jnz     short loc_1801456BB
0x1801456ac  mov     rax, [rdi+8]
0x1801456b0  cmp     rax, [rdx+r8*8+8]
0x1801456b5  jz      loc_18014643D
0x1801456bb  inc     ecx
0x1801456bd  cmp     ecx, 2
0x1801456c0  jb      short loc_18014569D
0x1801456c2  jmp     short loc_180145714
0x1801456c4  xor     r8d, r8d
0x1801456c7  lea     rdx, ?guidSkipCodecPackQuerySubtypes@@3QBU_GUID@@B; _GUID const near * const guidSkipCodecPackQuerySubtypes
0x1801456ce  mov     rax, [r12]
0x1801456d2  mov     ecx, r8d
0x1801456d5  add     rcx, rcx
0x1801456d8  cmp     rax, [rdx+rcx*8]
0x1801456dc  jnz     short loc_1801456EE
0x1801456de  mov     rax, [r12+8]
0x1801456e3  cmp     rax, [rdx+rcx*8+8]
0x1801456e8  jz      loc_18014643D
0x1801456ee  test    rdi, rdi
0x1801456f1  jz      short loc_18014570B
0x1801456f3  mov     rax, [rdi]
0x1801456f6  cmp     rax, [rdx+rcx*8]
0x1801456fa  jnz     short loc_18014570B
0x1801456fc  mov     rax, [rdi+8]
0x180145700  cmp     rax, [rdx+rcx*8+8]
0x180145705  jz      loc_18014643D
0x18014570b  inc     r8d
0x18014570e  cmp     r8d, 2
0x180145712  jb      short loc_1801456CE
0x180145714  xor     r15d, r15d
0x180145717  mov     eax, r15d
0x18014571a  imul    rbx, rax, 68h ; 'h'
0x18014571e  lea     rax, ?g_KnownPackages@@3QBUKnownPackageInfo@@B; KnownPackageInfo const near * const g_KnownPackages
0x180145725  add     rbx, rax
0x180145728  test    r12, r12
0x18014572b  jz      short loc_180145771
0x18014572d  xor     esi, esi
0x18014572f  mov     r14d, esi
0x180145732  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180145739  shl     r14, 4
0x18014573d  mov     r8d, 10h; Size
0x180145743  lea     rcx, [r14+14h]
0x180145747  add     rcx, rbx; Buf1
0x18014574a  call    memcmp_0
0x18014574f  test    eax, eax
0x180145751  jz      short loc_18014576A
0x180145753  mov     rax, [r14+rbx+14h]
0x180145758  cmp     rax, [r12]
0x18014575c  jnz     short loc_18014576A
0x18014575e  mov     rax, [r14+rbx+1Ch]
0x180145763  cmp     rax, [r12+8]
0x180145768  jz      short loc_1801457C7
0x18014576a  inc     esi
0x18014576c  cmp     esi, 2
0x18014576f  jb      short loc_18014572F
0x180145771  test    rdi, rdi
0x180145774  jz      short loc_1801457B8
0x180145776  xor     esi, esi
0x180145778  mov     r14d, esi
0x18014577b  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180145782  shl     r14, 4
0x180145786  mov     r8d, 10h; Size
0x18014578c  lea     rcx, [r14+34h]
0x180145790  add     rcx, rbx; Buf1
0x180145793  call    memcmp_0
0x180145798  test    eax, eax
0x18014579a  jz      short loc_1801457B1
0x18014579c  mov     rax, [r14+rbx+34h]
0x1801457a1  cmp     rax, [rdi]
0x1801457a4  jnz     short loc_1801457B1
0x1801457a6  mov     rax, [r14+rbx+3Ch]
0x1801457ab  cmp     rax, [rdi+8]
0x1801457af  jz      short loc_1801457C7
0x1801457b1  inc     esi
0x1801457b3  cmp     esi, 2
0x1801457b6  jb      short loc_180145778
0x1801457b8  inc     r15d
0x1801457bb  cmp     r15d, 10h
0x1801457bf  jb      loc_180145717
0x1801457c5  xor     ebx, ebx
0x1801457c7  mov     sil, [rsp+7E0h+var_7A0]
0x1801457cc  mov     r14, [rbp+6E0h+var_758]
0x1801457d0  mov     r12d, [rsp+7E0h+var_774]
0x1801457d5  lea     rdi, aWindowsMediaco_0; "windows.mediaCodec"
0x1801457dc  bt      r12d, 0Ah
0x1801457e1  jnb     short loc_1801457F1
0x1801457e3  mov     ecx, 240h
0x1801457e8  mov     eax, r12d
0x1801457eb  and     eax, ecx
0x1801457ed  cmp     eax, ecx
0x1801457ef  jnz     short loc_1801457FA
0x1801457f1  test    rbx, rbx
0x1801457f4  jz      short loc_1801457FA
0x1801457f6  mov     rdi, [rbx+58h]
0x1801457fa  lea     rcx, [rbp+6E0h+var_760]
0x1801457fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145803  mov     rdx, rdi; unsigned __int16 *
0x180145806  lea     rcx, [rbp+6E0h+var_730]; this
0x18014580a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18014580f  mov     rdx, [rbp+6E0h+var_730._hstring]
0x180145813  lea     r8, [rbp+6E0h+var_760]
0x180145817  mov     cl, sil
0x18014581a  call    cs:__imp_GetMediaComponentPackageInfo
0x180145820  xor     esi, esi
0x180145822  mov     ebx, eax
0x180145824  test    eax, eax
0x180145826  jns     loc_1801458D6
0x18014582c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145833  test    rcx, rcx
0x180145836  jnz     short loc_180145876
0x180145838  mov     rdx, cs:stru_1801FC290.__vftable
0x18014583f  lea     rcx, stru_1801FC290
0x180145846  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014584d  mov     rax, [rdx+8]
0x180145851  mov     edx, 7F0h
0x180145856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014585b  test    eax, eax
0x18014585d  jnz     short loc_18014586F
0x18014585f  lea     rcx, stru_1801F8A30
0x180145866  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014586d  jmp     short loc_180145876
0x18014586f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180145876  cmp     [rcx+8], sil
0x18014587a  jz      short loc_1801458A1
0x18014587c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145881  cmp     [rax+7CCh], ebx
0x180145887  jz      short loc_1801458A1
0x180145889  mov     r9d, ebx; int
0x18014588c  lea     rdx, aEnumpackagedmf; "EnumPackagedMFTs"
0x180145893  mov     r8d, 954h; int
0x180145899  mov     rcx, rax; this
0x18014589c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801458a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801458a8  jb      loc_1801463E0
0x1801458ae  mov     edx, 34h ; '4'
0x1801458b3  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x1801458ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1801458c1  xor     r9d, r9d
0x1801458c4  mov     dword ptr [rsp+7E0h+var_7C0], ebx
0x1801458c8  mov     rcx, [rcx+10h]
0x1801458cc  call    WPP_SF_qD
0x1801458d1  jmp     loc_1801463E0
0x1801458d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1801458dd  lea     rdi, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x1801458e4  jb      short loc_18014592E
0x1801458e6  lea     rdx, [rsp+7E0h+lpsz]; lplpsz
0x1801458eb  mov     [rsp+7E0h+lpsz], rsi
0x1801458f0  mov     rcx, r13; rclsid
0x1801458f3  call    cs:__imp_StringFromCLSID
0x1801458f9  test    eax, eax
0x1801458fb  js      short loc_18014592E
0x1801458fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180145904  jb      short loc_180145923
0x180145906  mov     rcx, cs:WPP_GLOBAL_Control
0x18014590d  mov     edx, 35h ; '5'
0x180145912  mov     r9, [rsp+7E0h+lpsz]
0x180145917  mov     r8, rdi
0x18014591a  mov     rcx, [rcx+10h]
0x18014591e  call    WPP_SF_S
0x180145923  mov     rcx, [rsp+7E0h+lpsz]; pv
0x180145928  call    cs:__imp_CoTaskMemFree
0x18014592e  mov     rcx, [rbp+6E0h+var_760]
0x180145932  lea     rdx, [rsp+7E0h+var_770]
0x180145937  mov     [rsp+7E0h+var_770], esi
0x18014593b  mov     rax, [rcx]
0x18014593e  mov     rax, [rax+38h]
0x180145942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145947  mov     ebx, eax
0x180145949  test    eax, eax
0x18014594b  jns     loc_1801459E0
0x180145951  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145958  test    rcx, rcx
0x18014595b  jnz     short loc_18014599B
0x18014595d  mov     rax, cs:stru_1801FC290.__vftable
0x180145964  lea     rcx, stru_1801FC290
0x18014596b  mov     edx, 7F0h
0x180145970  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145977  mov     rax, [rax+8]
0x18014597b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145980  test    eax, eax
0x180145982  jnz     short loc_180145994
0x180145984  lea     rcx, stru_1801F8A30
0x18014598b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145992  jmp     short loc_18014599B
0x180145994  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014599b  cmp     [rcx+8], sil
0x18014599f  jz      short loc_1801459C6
0x1801459a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801459a6  cmp     [rax+7CCh], ebx
0x1801459ac  jz      short loc_1801459C6
0x1801459ae  mov     r9d, ebx; int
0x1801459b1  lea     rdx, aEnumpackagedmf; "EnumPackagedMFTs"
0x1801459b8  mov     r8d, 961h; int
0x1801459be  mov     rcx, rax; this
0x1801459c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801459c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801459cd  jb      loc_1801463E0
0x1801459d3  mov     edx, 36h ; '6'
0x1801459d8  mov     r8, rdi
0x1801459db  jmp     loc_1801458BA
0x1801459e0  mov     r15d, esi
0x1801459e3  cmp     [rsp+7E0h+var_770], esi
0x1801459e7  jbe     loc_180145CF3
0x1801459ed  mov     ecx, r12d; unsigned int
0x1801459f0  call    ?PolicyFromMFTFlags@@YA?AW4MF_PLUGIN_CONTROL_POLICY@@I@Z; PolicyFromMFTFlags(uint)
0x1801459f5  mov     r12d, eax
0x1801459f8  mov     rcx, [rbp+6E0h+var_760]
0x1801459fc  lea     r8, [rsp+7E0h+lpsz]
0x180145a01  mov     [rsp+7E0h+lpsz], rsi
0x180145a06  mov     [rsp+7E0h+var_788], rsi
0x180145a0b  mov     [rsp+7E0h+var_7A0], sil
0x180145a10  mov     rdx, [rcx]
0x180145a13  mov     [rsp+7E0h+var_790], rsi
0x180145a18  mov     rax, [rdx+30h]
0x180145a1c  mov     edx, r15d
0x180145a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145a24  mov     ebx, eax
0x180145a26  test    eax, eax
0x180145a28  js      loc_1801462B9
  ... truncated ...
```
