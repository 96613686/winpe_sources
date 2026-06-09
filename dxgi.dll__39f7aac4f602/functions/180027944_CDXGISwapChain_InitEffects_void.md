# CDXGISwapChain::InitEffects(void)

- ea: `0x180027944`
- end: `0x1800286ea`
- name: `?InitEffects@CDXGISwapChain@@AEAAXXZ`
- size: `3494`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this)`
- caller_count: `3`
- callee_count: `45`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800202ac`
- `0x1800286f0`
- `0x18002d2fc`

## callees

- `0x18000c6b0`
- `0x180011ef0`
- `0x1800137c0`
- `0x1800137f0`
- `0x180015ee0`
- `0x180027944`
- `0x180030320`
- `0x1800306f4`
- `0x18003e5fc`
- `0x180044640`
- `0x180055ed4`
- `0x180056018`
- `0x1800578e8`
- `0x180058f50`
- `0x180058fe8`
- `0x18005ed10`
- `0x180060320`
- `0x180063198`
- `0x1800646b0`
- `0x180066744`
- `0x1800668e4`
- `0x180067d2c`
- `0x180067db4`
- `0x18006bc58`
- `0x18006e404`
- `0x180075fa0`
- `0x18008767c`
- `0x180088468`
- `0x18008d830`
- `0x18008ee9c`
- `0x18008f19c`
- `0x18008f1cc`
- `0x18008f23c`
- `0x180092128`
- `0x180092168`
- `0x18009b934`
- `0x18009b9ec`
- `0x18009bbb4`
- `0x18009bc04`
- `0x18009c6b4`
- `0x18009dbdc`
- `0x18009dc34`
- `0x18009ec6c`
- `0x18009feb0`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180028677`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180028677`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180027c54`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800282f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002857b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800286b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180027c54`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800282f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002857b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800286b9`

## string_xrefs

- `0x180028670`: `SuperResExt.dll`
- `0x180028085`: `onecoreuap\windows\DirectX\dxg\DXGI\dll\pch.cpp`
- `0x180028127`: `onecoreuap\windows\DirectX\dxg\DXGI\dll\pch.cpp`
- `0x180028212`: `onecoreuap\windows\DirectX\dxg\DXGI\dll\pch.cpp`
- `0x18002838b`: `onecoreuap\windows\DirectX\dxg\DXGI\dll\pch.cpp`
- `0x1800281b2`: `Failed to create 11-12 interop device`
- `0x1800283bd`: `Failed to create effect`
- `0x1800282ab`: `ForceComposeDx11 enabled`
- `0x180028696`: `Failed to load-lib SR extension`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CDXGISwapChain::InitEffects(CDXGISwapChain *this)
{
  char v2; // r15
  _QWORD *v3; // rax
  int v4; // edx
  char v5; // r14
  bool v6; // bl
  __int64 v7; // rdx
  __int64 v8; // rcx
  char IsPresentEffectsEnabled; // di
  unsigned int v10; // r9d
  char v11; // r13
  unsigned int v12; // r9d
  bool v13; // r12
  CDXGIOutput *v14; // rcx
  char IsPresentEffectsDisabledByPreference; // al
  char v16; // dl
  char v17; // dl
  unsigned __int8 v18; // r14
  char v19; // bl
  int v20; // edi
  int v21; // ecx
  CModule *v22; // rcx
  CModule *v23; // rcx
  CModule *v24; // rcx
  bool v25; // r9
  bool IsHDREnabled; // bl
  _BYTE *v27; // r14
  __int64 v28; // rcx
  _DWORD *v29; // rax
  __int64 v30; // rdx
  int v31; // edi
  signed int v32; // eax
  CModule *v33; // rcx
  bool v34; // r9
  CDXGIOutput *v35; // r15
  __int64 v36; // rax
  __int64 v37; // rcx
  char *v38; // rdi
  _QWORD *v39; // rax
  unsigned int v40; // ebx
  __int64 v41; // r8
  bool v42; // r9
  unsigned int v43; // edx
  int v44; // ecx
  bool v45; // r9
  unsigned int v46; // eax
  CModule *v47; // rcx
  unsigned int v48; // eax
  __int64 v49; // r10
  __int64 (__fastcall *v50)(_QWORD, char *, __int64, char *); // rax
  signed int EffectsD3D12DeviceAndQueue; // eax
  CModule *v52; // rcx
  bool v53; // r9
  __int64 v54; // r10
  __int64 (__fastcall *v55)(_QWORD, char *, __int64, char *); // rax
  CModule *v56; // rcx
  bool IsForceComposeDx11Enabled; // al
  bool v58; // r9
  char IsEnabled; // al
  CModule *v60; // rcx
  bool v61; // r9
  signed int v62; // edx
  __int64 v63; // rcx
  __int64 (__fastcall *v64)(_QWORD, char *); // rax
  struct CD3D12Device *v65; // rdx
  signed int v66; // eax
  CModule *v67; // rcx
  bool v68; // r9
  CModule *v69; // rcx
  signed int v70; // eax
  bool v71; // r9
  enum DXGI_COLOR_SPACE_TYPE v72; // edx
  signed int v73; // eax
  bool v74; // r9
  HMODULE LibraryA; // rax
  signed int LastErrorFailHr; // eax
  bool v77; // r9
  int v78; // [rsp+20h] [rbp-E0h]
  unsigned int v79; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v80; // [rsp+34h] [rbp-CCh]
  int v81; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v82; // [rsp+3Ch] [rbp-C4h] BYREF
  char IsPresentEffectsValidPowerState; // [rsp+3Dh] [rbp-C3h]
  char v84; // [rsp+3Eh] [rbp-C2h]
  int v85; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v86; // [rsp+48h] [rbp-B8h] BYREF
  int v87; // [rsp+50h] [rbp-B0h]
  unsigned int v88[3]; // [rsp+54h] [rbp-ACh] BYREF
  int v89[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v90; // [rsp+68h] [rbp-98h] BYREF
  __int64 v91; // [rsp+70h] [rbp-90h] BYREF
  char *v92; // [rsp+78h] [rbp-88h] BYREF
  int v93; // [rsp+80h] [rbp-80h]
  _DWORD v94[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v95; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v96[12]; // [rsp+A0h] [rbp-60h] BYREF
  char v97; // [rsp+100h] [rbp+0h]
  char v98[8]; // [rsp+110h] [rbp+10h] BYREF
  char v99[8]; // [rsp+118h] [rbp+18h] BYREF
  char v100[8]; // [rsp+120h] [rbp+20h] BYREF
  int *v101; // [rsp+130h] [rbp+30h]
  CDXGISwapChain *v102; // [rsp+138h] [rbp+38h]
  char v103[16]; // [rsp+140h] [rbp+40h] BYREF
  char v104[24]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v2 = 0;
  v81 = 0;
  v87 = *((_DWORD *)this + 98);
  v93 = *((_DWORD *)this + 140);
  v101 = &v81;
  v102 = this;
  v82 = 0;
  v94[0] = 1;
  v94[1] = 2;
  v3 = v94;
  v95 = v94;
  while ( 1 )
  {
    v79 = *(_DWORD *)v3;
    v80 = 0;
    v84 = 0;
    v85 = 0;
    if ( v79 == 1 )
      break;
    if ( v79 != 2 )
      goto LABEL_70;
    if ( (unsigned __int8)CModule::IsPresentEffectsDeviceApplicable(g_Module) )
    {
      if ( !(unsigned int)CDXGISwapChain::HybridDirectFlipMode(this) || (v5 = 0, byte_180109C53) )
        v5 = 1;
      v6 = v4 != 2
        || byte_180109C56
        || (*((_DWORD *)CDXGIBaseAdapter::InternalGetAdapterDesc(*((CDXGIBaseAdapter **)this + 40)) + 102) & 0x400) == 0;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned __int8)CModule::IsPresentEffectsEnabled(g_Module, v79)
          || *((_DWORD *)this + 82) != 2
          || !(unsigned __int8)CDXGISwapChain::IsFlipModel<0>(this)
          || *((_BYTE *)this + 2115)
          || !v6
          || (v19 = 1, !v5) )
        {
          v19 = 0;
        }
        v85 = 14;
        goto LABEL_69;
      }
      IsPresentEffectsEnabled = CModule::IsPresentEffectsEnabled(g_Module, v79);
      v10 = v79;
      if ( byte_180109C40 )
      {
        LOBYTE(v7) = v79;
        LOBYTE(v8) = (unsigned int)DXGI_EFFECT_STATE::GetEffectTypeDxDbMode(&qword_180109C48, v7) == 0;
      }
      else
      {
        LOBYTE(v8) = 0;
      }
      if ( IsPresentEffectsEnabled || !(_BYTE)v8 )
      {
        if ( (qword_180109BB0 & 1) != 0 || (v11 = 0, (qword_180109C48 & 0x20000000000LL) != 0) )
          v11 = 1;
        IsPresentEffectsValidPowerState = CModule::IsPresentEffectsValidPowerState(v8, v10);
        v13 = 1;
        v14 = (CDXGIOutput *)*((_QWORD *)this + 266);
        if ( !v14 )
          v14 = (CDXGIOutput *)*((_QWORD *)this + 273);
        if ( v12 == 2 && !byte_180109C59 && (dword_180109DA8 & 4) != 0 && v14 )
        {
          v13 = !CDXGIOutput::IsInternalTopology(v14);
          v12 = v79;
        }
        if ( IsPresentEffectsEnabled
          || !(unsigned __int8)CModule::IsStartInPassthroughEnabled(v14, v12)
          || (IsPresentEffectsDisabledByPreference = CModule::IsPresentEffectsDisabledByPreference(g_Module, v79),
              v16 = 1,
              IsPresentEffectsDisabledByPreference) )
        {
          v16 = 0;
        }
        v80 = v16;
        if ( *((_DWORD *)this + 82) == 2
          && (unsigned __int8)CDXGISwapChain::IsFlipModel<0>(this)
          && !*((_BYTE *)this + 2115)
          && v11
          && v6
          && v5
          && (v2 = 1, IsPresentEffectsValidPowerState)
          && v13 )
        {
          v18 = 1;
          if ( IsPresentEffectsEnabled || v17 )
          {
            v19 = 1;
            goto LABEL_45;
          }
        }
        else
        {
          v18 = 0;
        }
        v19 = 0;
LABEL_45:
        v82 = v18;
        v20 = 0;
        v21 = qword_180109D70 & 0xFFFFFFFB | (4 * v18);
        LODWORD(qword_180109D70) = v21;
        if ( !v13 )
        {
          v22 = (CModule *)(v21 & 0xFFFFF2FF);
          LODWORD(v22) = (unsigned int)v22 | 0x200;
          LODWORD(qword_180109D70) = (_DWORD)v22;
          CModule::RecordJournalImpl(v22, 0, "Auto SR not supported on current display", v12);
          v20 = 20;
          v21 = qword_180109D70;
        }
        if ( !IsPresentEffectsValidPowerState )
        {
          v23 = (CModule *)(v21 & 0xFFFFF0FF | 0x700);
          LODWORD(qword_180109D70) = (_DWORD)v23;
          CModule::RecordJournalImpl(v23, 0, "Auto SR not supported on current power source", v12);
          v20 = 19;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2601>::GetImpl'::`2'::impl)
          && !v11 )
        {
          LODWORD(qword_180109D70) = qword_180109D70 & 0xFFFFF0FF | 0x800;
          CModule::RecordJournalImpl(v24, 0, "Auto SR not supported on non-games", v25);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl)
          && v20
          && v2 )
        {
          *((_DWORD *)this + 1112) = v20;
          QueryPerformanceCounter((LARGE_INTEGER *)this + 557);
        }
        v85 = 4 * v80 + 14;
        v2 = 0;
        if ( byte_180109C5A && v18 )
        {
          if ( v19 )
            goto LABEL_74;
          if ( (unsigned __int8)CModule::IsPresentEffectsDeviceApplicable(g_Module) )
          {
            v19 = 1;
            v85 = 18;
            v84 = 1;
            goto LABEL_69;
          }
        }
        else
        {
LABEL_69:
          if ( v19 )
            goto LABEL_74;
        }
      }
LABEL_70:
      v81 = -2147019873;
    }
LABEL_163:
    v3 = v95 + 1;
    v95 = v3;
    if ( v3 == &v95 )
    {
      v27 = (char *)this + 3920;
      goto LABEL_165;
    }
  }
  IsHDREnabled = CDXGISwapChain::IsHDREnabled(this);
  if ( !CDXGISwapChain::IsBufferUpgradeEligible(this, 1, 0) || !IsHDREnabled )
  {
    v85 = 12;
    if ( CDXGISwapChain::IsBufferUpgradeEligible(this, 0, 1)
      && CModule::EvaluateBufferUpgradeEligibility((CModule *)g_Module, 1)
      && IsHDREnabled )
    {
      *((_DWORD *)this + 1112) = 13;
      QueryPerformanceCounter((LARGE_INTEGER *)this + 557);
      goto LABEL_163;
    }
    goto LABEL_70;
  }
  v85 = 12;
LABEL_74:
  v27 = (char *)this + 3920;
  v28 = *((_QWORD *)this + 509);
  if ( v28 )
  {
    v29 = (_DWORD *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v28 + 24LL))(v28, v104);
    if ( v79 != *v29 )
    {
      CDXGISwapChain::EffectsInfo::Reset((CDXGISwapChain *)((char *)this + 3920));
      if ( *((_QWORD *)this + 509) )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 509, 0);
    }
  }
  if ( (*v27 & 1) != 0 && (v30 = *((_QWORD *)this + 509)) != 0 && v79 == 1 )
  {
    v31 = v87;
    if ( *((_DWORD *)this + 997) == v87 )
    {
      v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 48LL))(*((_QWORD *)this + 509));
      v81 = v32;
      if ( v32 >= 0 )
        goto LABEL_165;
      CModule::RecordJournalImpl(v33, v32, "Failed to flush effect", v34);
    }
  }
  else
  {
    v31 = v87;
  }
  v35 = (CDXGIOutput *)*((_QWORD *)this + 266);
  if ( !v35 )
  {
    v35 = (CDXGIOutput *)*((_QWORD *)this + 273);
    if ( !v35 && v79 == 1 )
    {
      v2 = 0;
      goto LABEL_163;
    }
  }
  *(_OWORD *)((char *)this + 4024) = 0;
  *(_OWORD *)((char *)this + 4040) = 0;
  *(_OWORD *)((char *)this + 4056) = 0;
  *((_DWORD *)this + 986) = v79;
  v36 = *((_QWORD *)this + 32);
  if ( v36 )
    v37 = *(_QWORD *)(v36 + 96);
  else
    v37 = *((_QWORD *)this + 33);
  *((_QWORD *)this + 494) = v37;
  *((_QWORD *)this + 495) = 0;
  *((_QWORD *)this + 496) = *((_QWORD *)this + 115);
  *((_QWORD *)this + 497) = v35;
  *((_DWORD *)this + 996) = *((_DWORD *)this + 1141);
  *((_DWORD *)this + 997) = v31;
  *((_DWORD *)this + 998) = v93;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl) )
    *((_QWORD *)this + 500) = qword_180109C48;
  v92 = 0;
  v90 = 0;
  v91 = 0;
  *(_QWORD *)v89 = 0;
  v38 = (char *)&qword_180109CA0[7 * (int)v79] + 4;
  v86 = 0;
  v39 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>::ensure_data(&v86);
  tip2::details::shared_data<0,0,0>::start(*v39 + 8LL, v103);
  v40 = v79;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>::operator->(
                           &v86,
                           v99)
            + 272LL) = v40;
  tip2::test_data_control<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>::~test_data_control<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>(v99);
  v96[0] = v38;
  v96[1] = (char *)this + 4024;
  v96[2] = &v81;
  v96[3] = &v85;
  v96[4] = &v79;
  v96[5] = &v82;
  v96[6] = this;
  v96[7] = &v92;
  v96[8] = &v91;
  v96[9] = &v90;
  v96[10] = v89;
  v96[11] = &v86;
  v97 = 1;
  v43 = v79;
  if ( v79 == 1 )
  {
    *((_QWORD *)this + 501) = **(_QWORD **)&CDXGIOutput::GetAdapterLuid(v35);
    *((_DWORD *)this + 1004) = *((_DWORD *)v35 + 64);
    v92 = (char *)this + 3952;
    v91 = 72;
    v90 = (char *)this + 4028;
    *(_QWORD *)v89 = 24;
    v2 = 0;
    if ( qword_180109D00 )
    {
      v78 = 24;
      v44 = qword_180109D00((unsigned int)dword_180109CD8, (char *)this + 3952, 72);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46B,
        (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\DXGI\\dll\\pch.cpp",
        (const char *)0x80004005LL,
        v78);
      v44 = -2147467259;
    }
    v43 = v79;
  }
  else
  {
    if ( v79 != 2 )
    {
      v44 = -2147418113;
      v2 = 0;
      goto LABEL_114;
    }
    v92 = (char *)this + 3952;
    v91 = 72;
    v90 = (char *)this + 4028;
    *(_QWORD *)v89 = 44;
    v2 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl) )
      *((_DWORD *)this + 1004) = *(_DWORD *)CModule::GetEffectsConfig(g_Module, v98);
    v88[0] = 0;
    v88[1] = 0;
    CDXGISwapChain::InferBackbufferDimensions(this, *((HWND *)this + 42), v88, &v88[1], 0);
    v46 = *((_DWORD *)this + 94);
    if ( v46 && (v47 = (CModule *)*((unsigned int *)this + 95), (_DWORD)v47) )
    {
      if ( *((_DWORD *)this + 106) == 1 && __PAIR64__((unsigned int)v47, v46) != *(_QWORD *)v88 )
      {
        *((_DWORD *)this + 1143) = 1;
        v81 = -2005270524;
        CModule::RecordJournalImpl(
          v47,
          0x887A0004,
          "Effect not supported due to scaling mode NONE and buffer-window size mismatch",
          v45);
        *((_DWORD *)this + 1010) = 6;
        v97 = 0;
        lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
LABEL_103:
        wil::com_ptr_t<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>,wil::err_returncode_policy>(&v86);
        goto LABEL_163;
      }
      *((_DWORD *)this + 1002) = v46;
      v48 = *((_DWORD *)this + 95);
    }
    else
    {
      *((_DWORD *)this + 1002) = v88[0];
      v48 = v88[1];
    }
    *((_DWORD *)this + 1003) = v48;
    v49 = 7LL * (int)v79;
    v50 = (__int64 (__fastcall *)(_QWORD, char *, __int64, char *))g_Module[v49 + 101];
    if ( v50 )
    {
      v78 = v89[0];
      v44 = v50(LODWORD(g_Module[v49 + 96]), v92, v91, v90);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46B,
        (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\DXGI\\dll\\pch.cpp",
        (const char *)0x80004005LL,
        v78);
      v44 = -2147467259;
    }
    v43 = v79;
  }
LABEL_114:
  v81 = v44;
  *(_DWORD *)v27 &= ~0x10u;
  if ( v43 == 2 && v44 == -2147467262 && *((char *)this + 288) >= 0 )
  {
    *(_DWORD *)v27 &= ~4u;
    if ( !*((_QWORD *)this + 545) )
    {
      EffectsD3D12DeviceAndQueue = CDXGISwapChain::CreateEffectsD3D12DeviceAndQueue(
                                     this,
                                     (CDXGISwapChain *)((char *)this + 3920),
                                     v41,
                                     v42);
      v81 = EffectsD3D12DeviceAndQueue;
      if ( EffectsD3D12DeviceAndQueue < 0 )
      {
        CModule::RecordJournalImpl(v52, EffectsD3D12DeviceAndQueue, "Failed to create 11-12 interop device", v53);
        v97 = 0;
        lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
        goto LABEL_103;
      }
      v43 = v79;
    }
    *((_QWORD *)this + 494) = *((_QWORD *)this + 546);
    *((_QWORD *)this + 495) = *((_QWORD *)this + 555);
    v54 = 7LL * (int)v43;
    v55 = (__int64 (__fastcall *)(_QWORD, char *, __int64, char *))g_Module[v54 + 101];
    if ( !v55 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46B,
        (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\DXGI\\dll\\pch.cpp",
        (const char *)0x80004005LL,
        v78);
      v81 = -2147467259;
      goto LABEL_124;
    }
    v78 = v89[0];
    v81 = v55(LODWORD(g_Module[v54 + 96]), v92, v91, v90);
    if ( v81 < 0 )
      goto LABEL_124;
    *(_QWORD *)(*((_QWORD *)this + 547) + 192LL) = *((_QWORD *)this + 555);
    *(_DWORD *)v27 |= 4u;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_AllowForceCompose>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_AllowForceCompose>::GetImpl'::`2'::impl) )
    {
      IsForceComposeDx11Enabled = CModule::IsForceComposeDx11Enabled(v56);
      *(_DWORD *)v27 &= ~0x10u;
      *(_DWORD *)v27 |= 16 * IsForceComposeDx11Enabled;
      if ( IsForceComposeDx11Enabled )
        CModule::RecordJournalImpl((CModule *)IsForceComposeDx11Enabled, 0, "ForceComposeDx11 enabled", v58);
    }
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl);
  v62 = v81;
  if ( IsEnabled && v79 == 2 && v84 && (v81 >= 0 || *((_DWORD *)this + 1010) == 4) )
  {
    *((_DWORD *)this + 1112) = 18;
    QueryPerformanceCounter((LARGE_INTEGER *)this + 557);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>::operator->(
                            &v86,
                            v100)
             + 280LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>::~test_data_control<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>>(v100);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl) )
      v81 = -2005270524;
    goto LABEL_124;
  }
  if ( v81 < 0 || !*((_DWORD *)this + 1007) )
  {
LABEL_124:
    v97 = 0;
    lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
    goto LABEL_103;
  }
  if ( !*((_QWORD *)this + 509) )
  {
    v63 = 7LL * (int)v79;
    v64 = (__int64 (__fastcall *)(_QWORD, char *))g_Module[v63 + 100];
    if ( v64 )
    {
      v62 = v64(LODWORD(g_Module[v63 + 96]), (char *)this + 4072);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x466,
        (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\DXGI\\dll\\pch.cpp",
        (const char *)0x80004005LL,
        v78);
      v62 = -2147467259;
    }
    v81 = v62;
  }
  if ( v62 < 0 )
  {
    CModule::RecordJournalImpl(v60, v62, "Failed to create effect", v61);
    v97 = 0;
    lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
    goto LABEL_103;
  }
  v65 = (struct CD3D12Device *)*((_QWORD *)this + 32);
  if ( v65 && *((_DWORD *)this + 1008) )
  {
    CDXGISwapChain::EffectsInfo::EnsureInternalQueue((CDXGISwapChain *)((char *)this + 3920), v65);
    *((_QWORD *)this + 495) = *((_QWORD *)this + 555);
    *(_QWORD *)(*((_QWORD *)this + 32) + 192LL) = *((_QWORD *)this + 555);
  }
  v78 = v89[0];
  v66 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, char *))(**((_QWORD **)this + 509) + 32LL))(
          *((_QWORD *)this + 509),
          v92,
          v91,
          v90);
  v81 = v66;
  if ( v66 < 0 )
  {
    CModule::RecordJournalImpl(v67, v66, "Initialize failed, effect type is not enabled on the swapchain", v68);
    v97 = 0;
    lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
    goto LABEL_103;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    if ( v80 )
    {
      v70 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 509) + 64LL))(*((_QWORD *)this + 509), 1);
      v81 = v70;
      if ( v70 < 0 )
      {
        CModule::RecordJournalImpl(v69, v70, "Failed to start in passthrough mode", v71);
        v97 = 0;
        lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
        goto LABEL_103;
      }
    }
  }
  *((_DWORD *)this + 1142) = *((_DWORD *)this + 1011);
  v72 = *((_DWORD *)this + 1012);
  if ( v72 != v93 )
  {
    v73 = CDXGISwapChain::SetColorSpaceInternal(this, v72, 0);
    v81 = v73;
    if ( v73 < 0 )
    {
      CModule::RecordJournalImpl(v69, v73, "Overriding color space failed", v74);
      v97 = 0;
      lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
      goto LABEL_103;
    }
  }
  if ( v79 == 2 )
  {
    *((_DWORD *)this + 1143) = 0;
    *((_DWORD *)this + 981) = *((_DWORD *)this + 1013);
    *((_DWORD *)this + 982) = *((_DWORD *)this + 1014);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      if ( !*((_QWORD *)this + 558) )
      {
        LibraryA = LoadLibraryA("SuperResExt.dll");
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          (char *)this + 4464,
          LibraryA);
        if ( !*((_QWORD *)this + 558) )
        {
          LastErrorFailHr = wil::details::GetLastErrorFailHr(v69);
          if ( LastErrorFailHr < 0 )
            CModule::RecordJournalImpl(v69, LastErrorFailHr, "Failed to load-lib SR extension", v77);
        }
      }
    }
  }
  if ( v85 )
  {
    *((_DWORD *)this + 1112) = v85;
    QueryPerformanceCounter((LARGE_INTEGER *)this + 557);
  }
  CModule::WriteEffectApplicableFlag(v69, v79);
  *(_DWORD *)v27 |= 1u;
  v97 = 0;
  lambda_1028541a4df2e7c7c5bd43875c6ad6b3_::operator()(v96);
  wil::com_ptr_t<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<DxgiTipTests::_tip_DxgiEffectsTipTest,DxgiTipTests::_tip_DxgiEffectsTipTest>,wil::err_returncode_policy>(&v86);
LABEL_165:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    CDXGISwapChain::UpdateAppStatus(this);
    if ( v82 )
      CDXGISwapChain::RegisterSettingsChangedCallback(this);
    if ( (*v27 & 1) != 0 && *((_DWORD *)this + 986) == 2 && !byte_180109C58 && (dword_180109DA8 & 1) != 0 )
      CDXGISwapChain::RegisterPowerNotificationCallback(this);
  }
  if ( v81 < 0 )
    CDXGISwapChain::DisableEffects(this);
}

```

## disassembly

```asm
0x180027944  push    rbp
0x180027946  push    rbx
0x180027947  push    rsi
0x180027948  push    rdi
0x180027949  push    r12
0x18002794b  push    r13
0x18002794d  push    r14
0x18002794f  push    r15
0x180027951  lea     rbp, [rsp-78h]
0x180027956  sub     rsp, 178h
0x18002795d  mov     rax, cs:__security_cookie
0x180027964  xor     rax, rsp
0x180027967  mov     [rbp+0B0h+var_48], rax
0x18002796b  mov     rsi, rcx
0x18002796e  xor     r15d, r15d
0x180027971  mov     [rsp+1B0h+var_178], r15d
0x180027976  mov     edi, [rcx+188h]
0x18002797c  mov     [rsp+1B0h+var_160], edi
0x180027980  mov     eax, [rcx+230h]
0x180027986  mov     [rbp+0B0h+var_130], eax
0x180027989  lea     rcx, [rsp+1B0h+var_178]
0x18002798e  mov     [rbp+0B0h+var_80], rcx
0x180027992  mov     [rbp+0B0h+var_78], rsi
0x180027996  mov     [rsp+1B0h+var_174], r15b
0x18002799b  mov     [rbp+0B0h+var_128], 1
0x1800279a2  mov     [rbp+0B0h+var_124], 2
0x1800279a9  lea     rax, [rbp+0B0h+var_128]
0x1800279ad  mov     [rbp+0B0h+var_120], rax
0x1800279b1  lea     rdi, ?g_Module@@3VCModule@@A; CModule g_Module
0x1800279b8  mov     edx, [rax]
0x1800279ba  mov     [rsp+1B0h+var_180], edx
0x1800279be  mov     [rsp+1B0h+var_17C], r15b
0x1800279c3  mov     [rsp+1B0h+var_172], r15b
0x1800279c8  mov     [rsp+1B0h+var_170], r15d
0x1800279cd  mov     ecx, edx
0x1800279cf  sub     ecx, 1
0x1800279d2  jz      loc_180027CF5
0x1800279d8  cmp     ecx, 1
0x1800279db  jnz     loc_180027CE8
0x1800279e1  mov     rcx, rdi
0x1800279e4  call    ?IsPresentEffectsDeviceApplicable@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsDeviceApplicable(DXGI_EFFECT_TYPE)
0x1800279e9  test    al, al
0x1800279eb  jz      loc_18002858D
0x1800279f1  mov     rcx, rsi
0x1800279f4  call    ?HybridDirectFlipMode@CDXGISwapChain@@QEBA?AW4HYBRID_DFLIP_MODE@@XZ; CDXGISwapChain::HybridDirectFlipMode(void)
0x1800279f9  test    eax, eax
0x1800279fb  jz      short loc_180027A09
0x1800279fd  cmp     cs:byte_180109C53, r15b
0x180027a04  mov     r14b, r15b
0x180027a07  jz      short loc_180027A0C
0x180027a09  mov     r14b, 1
0x180027a0c  cmp     edx, 2
0x180027a0f  jnz     short loc_180027A36
0x180027a11  cmp     cs:byte_180109C56, r15b
0x180027a18  jnz     short loc_180027A36
0x180027a1a  mov     rcx, [rsi+140h]; this
0x180027a21  call    ?InternalGetAdapterDesc@CDXGIBaseAdapter@@QEAAAEBUSAdapterDesc@@XZ; CDXGIBaseAdapter::InternalGetAdapterDesc(void)
0x180027a26  mov     ebx, [rax+198h]
0x180027a2c  shr     ebx, 0Ah
0x180027a2f  not     bl
0x180027a31  and     bl, 1
0x180027a34  jmp     short loc_180027A38
0x180027a36  mov     bl, 1
0x180027a38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x180027a3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180027a44  mov     edx, [rsp+1B0h+var_180]
0x180027a48  mov     rcx, rdi
0x180027a4b  test    al, al
0x180027a4d  jz      loc_180027CA7
0x180027a53  call    ?IsPresentEffectsEnabled@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsEnabled(DXGI_EFFECT_TYPE)
0x180027a58  mov     dil, al
0x180027a5b  mov     r9d, [rsp+1B0h+var_180]
0x180027a60  cmp     cs:byte_180109C40, r15b
0x180027a67  jnz     short loc_180027A6E
0x180027a69  mov     cl, r15b
0x180027a6c  jmp     short loc_180027A82
0x180027a6e  mov     dl, r9b
0x180027a71  lea     rcx, qword_180109C48
0x180027a78  call    ?GetEffectTypeDxDbMode@DXGI_EFFECT_STATE@@QEAA?AW4DXGI_EFFECT_MODE@@E@Z; DXGI_EFFECT_STATE::GetEffectTypeDxDbMode(uchar)
0x180027a7d  test    eax, eax
0x180027a7f  setz    cl
0x180027a82  test    dil, dil
0x180027a85  jnz     short loc_180027A8F
0x180027a87  test    cl, cl
0x180027a89  jnz     loc_180027CE8
0x180027a8f  test    byte ptr cs:qword_180109BB0, 1
0x180027a96  jnz     short loc_180027AA7
0x180027a98  test    dword ptr cs:qword_180109C48+4, 200h
0x180027aa2  mov     r13b, r15b
0x180027aa5  jz      short loc_180027AAA
0x180027aa7  mov     r13b, 1
0x180027aaa  mov     edx, r9d
0x180027aad  call    ?IsPresentEffectsValidPowerState@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsValidPowerState(DXGI_EFFECT_TYPE)
0x180027ab2  mov     [rsp+1B0h+var_173], al
0x180027ab6  mov     r12b, 1
0x180027ab9  mov     rcx, [rsi+850h]
0x180027ac0  test    rcx, rcx
0x180027ac3  jnz     short loc_180027ACC
0x180027ac5  mov     rcx, [rsi+888h]; this
0x180027acc  cmp     r9d, 2
0x180027ad0  jnz     short loc_180027B00
0x180027ad2  cmp     cs:byte_180109C59, r15b
0x180027ad9  jnz     short loc_180027B00
0x180027adb  mov     eax, cs:dword_180109DA8
0x180027ae1  shr     eax, 2
0x180027ae4  not     al
0x180027ae6  test    r12b, al
0x180027ae9  jnz     short loc_180027B00
0x180027aeb  test    rcx, rcx
0x180027aee  jz      short loc_180027B00
0x180027af0  call    ?IsInternalTopology@CDXGIOutput@@QEAA_NXZ; CDXGIOutput::IsInternalTopology(void)
0x180027af5  test    al, al
0x180027af7  setz    r12b
0x180027afb  mov     r9d, [rsp+1B0h+var_180]
0x180027b00  test    dil, dil
0x180027b03  jnz     short loc_180027B27
0x180027b05  mov     edx, r9d
0x180027b08  call    ?IsStartInPassthroughEnabled@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsStartInPassthroughEnabled(DXGI_EFFECT_TYPE)
0x180027b0d  test    al, al
0x180027b0f  jz      short loc_180027B27
0x180027b11  mov     edx, [rsp+1B0h+var_180]
0x180027b15  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x180027b1c  call    ?IsPresentEffectsDisabledByPreference@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsDisabledByPreference(DXGI_EFFECT_TYPE)
0x180027b21  test    al, al
0x180027b23  mov     dl, 1
0x180027b25  jz      short loc_180027B2A
0x180027b27  mov     dl, r15b
0x180027b2a  mov     [rsp+1B0h+var_17C], dl
0x180027b2e  cmp     dword ptr [rsi+148h], 2
0x180027b35  jnz     short loc_180027B7A
0x180027b37  mov     rcx, rsi
0x180027b3a  call    ??$IsFlipModel@$0A@@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<0>(void)
0x180027b3f  test    al, al
0x180027b41  jz      short loc_180027B7A
0x180027b43  cmp     [rsi+843h], r15b
0x180027b4a  jnz     short loc_180027B7A
0x180027b4c  test    r13b, r13b
0x180027b4f  jz      short loc_180027B7A
0x180027b51  test    bl, bl
0x180027b53  jz      short loc_180027B7A
0x180027b55  test    r14b, r14b
0x180027b58  jz      short loc_180027B7A
0x180027b5a  mov     r15b, 1
0x180027b5d  cmp     [rsp+1B0h+var_173], 0
0x180027b62  jz      short loc_180027B7A
0x180027b64  test    r12b, r12b
0x180027b67  jz      short loc_180027B7A
0x180027b69  mov     r14b, r15b
0x180027b6c  test    dil, dil
0x180027b6f  jnz     short loc_180027B75
0x180027b71  test    dl, dl
0x180027b73  jz      short loc_180027B7D
0x180027b75  mov     bl, r14b
0x180027b78  jmp     short loc_180027B7F
0x180027b7a  xor     r14b, r14b
0x180027b7d  xor     bl, bl
0x180027b7f  mov     [rsp+1B0h+var_174], r14b
0x180027b84  xor     edi, edi
0x180027b86  movzx   ecx, r14b
0x180027b8a  shl     ecx, 2
0x180027b8d  mov     eax, dword ptr cs:qword_180109D70
0x180027b93  and     eax, 0FFFFFFFBh
0x180027b96  or      ecx, eax
0x180027b98  mov     dword ptr cs:qword_180109D70, ecx
0x180027b9e  test    r12b, r12b
0x180027ba1  jnz     short loc_180027BCC
0x180027ba3  and     ecx, 0FFFFF2FFh
0x180027ba9  bts     ecx, 9; this
0x180027bad  mov     dword ptr cs:qword_180109D70, ecx
0x180027bb3  lea     r8, aAutoSrNotSuppo_0; "Auto SR not supported on current displa"...
0x180027bba  xor     edx, edx; unsigned int
0x180027bbc  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180027bc1  mov     edi, 14h
0x180027bc6  mov     ecx, dword ptr cs:qword_180109D70
0x180027bcc  cmp     [rsp+1B0h+var_173], 0
0x180027bd1  jnz     short loc_180027BF6
0x180027bd3  btr     ecx, 0Bh
0x180027bd7  or      ecx, 700h; this
0x180027bdd  mov     dword ptr cs:qword_180109D70, ecx
0x180027be3  lea     r8, aAutoSrNotSuppo; "Auto SR not supported on current power "...
0x180027bea  xor     edx, edx; unsigned int
0x180027bec  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180027bf1  mov     edi, 13h
0x180027bf6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2601@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2601@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2601>::GetImpl(void)'::`2'::impl
0x180027bfd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2601@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2601>::__private_IsEnabled(void)
0x180027c02  test    al, al
0x180027c04  jz      short loc_180027C2E
0x180027c06  test    r13b, r13b
0x180027c09  jnz     short loc_180027C2E
0x180027c0b  mov     eax, dword ptr cs:qword_180109D70
0x180027c11  and     eax, 0FFFFF8FFh
0x180027c16  bts     eax, 0Bh
0x180027c1a  mov     dword ptr cs:qword_180109D70, eax
0x180027c20  lea     r8, aAutoSrNotSuppo_1; "Auto SR not supported on non-games"
0x180027c27  xor     edx, edx; unsigned int
0x180027c29  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180027c2e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2603@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl(void)'::`2'::impl
0x180027c35  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(void)
0x180027c3a  test    al, al
0x180027c3c  jz      short loc_180027C5A
0x180027c3e  test    edi, edi
0x180027c40  jz      short loc_180027C5A
0x180027c42  test    r15b, r15b
0x180027c45  jz      short loc_180027C5A
0x180027c47  mov     [rsi+1160h], edi
0x180027c4d  lea     rcx, [rsi+1168h]; lpPerformanceCount
0x180027c54  call    cs:__imp_QueryPerformanceCounter
0x180027c5a  movzx   eax, [rsp+1B0h+var_17C]
0x180027c5f  lea     eax, ds:0Eh[rax*4]
0x180027c66  mov     [rsp+1B0h+var_170], eax
0x180027c6a  xor     r15d, r15d
0x180027c6d  cmp     cs:byte_180109C5A, r15b
0x180027c74  jz      short loc_180027CE4
0x180027c76  test    r14b, r14b
0x180027c79  jz      short loc_180027CE4
0x180027c7b  test    bl, bl
0x180027c7d  jnz     loc_180027D24
0x180027c83  mov     edx, [rsp+1B0h+var_180]
0x180027c87  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x180027c8e  call    ?IsPresentEffectsDeviceApplicable@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsDeviceApplicable(DXGI_EFFECT_TYPE)
0x180027c93  test    al, al
0x180027c95  jz      short loc_180027CE8
0x180027c97  mov     bl, 1
0x180027c99  mov     [rsp+1B0h+var_170], 12h
0x180027ca1  mov     [rsp+1B0h+var_172], bl
0x180027ca5  jmp     short loc_180027CE4
0x180027ca7  call    ?IsPresentEffectsEnabled@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsEnabled(DXGI_EFFECT_TYPE)
0x180027cac  test    al, al
0x180027cae  jz      short loc_180027CD9
0x180027cb0  cmp     dword ptr [rsi+148h], 2
0x180027cb7  jnz     short loc_180027CD9
0x180027cb9  mov     rcx, rsi
0x180027cbc  call    ??$IsFlipModel@$0A@@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<0>(void)
0x180027cc1  test    al, al
0x180027cc3  jz      short loc_180027CD9
0x180027cc5  cmp     [rsi+843h], r15b
0x180027ccc  jnz     short loc_180027CD9
0x180027cce  test    bl, bl
0x180027cd0  jz      short loc_180027CD9
0x180027cd2  test    r14b, r14b
0x180027cd5  mov     bl, 1
0x180027cd7  jnz     short loc_180027CDC
0x180027cd9  mov     bl, r15b
0x180027cdc  mov     [rsp+1B0h+var_170], 0Eh
0x180027ce4  test    bl, bl
0x180027ce6  jnz     short loc_180027D24
0x180027ce8  mov     [rsp+1B0h+var_178], 8007139Fh
0x180027cf0  jmp     loc_180028586
0x180027cf5  mov     rcx, rsi; this
0x180027cf8  call    ?IsHDREnabled@CDXGISwapChain@@QEAA_NXZ; CDXGISwapChain::IsHDREnabled(void)
0x180027cfd  mov     bl, al
0x180027cff  xor     r8d, r8d; bool
0x180027d02  mov     dl, 1; bool
0x180027d04  mov     rcx, rsi; this
0x180027d07  call    ?IsBufferUpgradeEligible@CDXGISwapChain@@QEBA_N_N0@Z; CDXGISwapChain::IsBufferUpgradeEligible(bool,bool)
0x180027d0c  test    al, al
0x180027d0e  jz      loc_180028533
0x180027d14  test    bl, bl
0x180027d16  jz      loc_180028533
0x180027d1c  mov     [rsp+1B0h+var_170], 0Ch
0x180027d24  lea     r14, [rsi+0F50h]
0x180027d2b  mov     rcx, [r14+98h]
0x180027d32  test    rcx, rcx
0x180027d35  jz      short loc_180027D6A
0x180027d37  mov     rax, [rcx]
0x180027d3a  lea     rdx, [rbp+0B0h+var_60]
0x180027d3e  mov     rax, [rax+18h]
0x180027d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d47  mov     ecx, [rax]
0x180027d49  cmp     [rsp+1B0h+var_180], ecx
0x180027d4d  jz      short loc_180027D6A
0x180027d4f  mov     rcx, r14; this
0x180027d52  call    ?Reset@EffectsInfo@CDXGISwapChain@@QEAAXXZ; CDXGISwapChain::EffectsInfo::Reset(void)
0x180027d57  lea     rcx, [rsi+0FE8h]; struct IUnknown **
0x180027d5e  cmp     [rcx], r15
0x180027d61  jz      short loc_180027D6A
0x180027d63  xor     edx, edx; struct IUnknown *
0x180027d65  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180027d6a  test    byte ptr [r14], 1
0x180027d6e  jz      short loc_180027DBC
0x180027d70  mov     rdx, [rsi+0FE8h]
0x180027d77  test    rdx, rdx
0x180027d7a  jz      short loc_180027DBC
0x180027d7c  mov     ecx, [rsp+1B0h+var_180]
0x180027d80  sub     ecx, 1
0x180027d83  jnz     short loc_180027DBC
0x180027d85  mov     edi, [rsp+1B0h+var_160]
0x180027d89  cmp     [rsi+0F94h], edi
0x180027d8f  jnz     short loc_180027DC0
0x180027d91  mov     rax, [rdx]
0x180027d94  mov     rcx, rdx
0x180027d97  mov     rax, [rax+30h]
0x180027d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027da0  mov     [rsp+1B0h+var_178], eax
0x180027da4  test    eax, eax
0x180027da6  jns     loc_1800285AD
0x180027dac  lea     r8, aFailedToFlushE; "Failed to flush effect"
0x180027db3  mov     edx, eax; unsigned int
0x180027db5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180027dba  jmp     short loc_180027DC0
  ... truncated ...
```
