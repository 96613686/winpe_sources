# DynVCPluginLoader::_LoadOnePluginDirect(ushort const *)

- ea: `0x1801bbb28`
- end: `0x1801bc552`
- name: `?_LoadOnePluginDirect@DynVCPluginLoader@@AEAAJPEBG@Z`
- size: `2602`
- prototype: `int(DynVCPluginLoader *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801bb658`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18002a334`
- `0x18002a374`
- `0x180039c98`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x18012962c`
- `0x18012966c`
- `0x180174b04`
- `0x1801b78a8`
- `0x1801b8a38`
- `0x1801b8ad8`
- `0x1801b8d60`
- `0x1801b8ea8`
- `0x1801bbb28`
- `0x1801bca44`
- `0x1801bd9d8`
- `0x1801c120c`
- `0x1804a9adc`
- `0x1804a9b90`
- `0x180688f3e`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1801bbbad`
- `KERNEL32!LoadLibraryW` at `0x1801bbbad`
- `KERNEL32!InitOnceExecuteOnce` at `0x1801bbbf3`
- `KERNEL32!InitOnceExecuteOnce` at `0x1801bbbf3`
- `KERNEL32!GetLastError` at `0x1801bbbd7`
- `KERNEL32!GetLastError` at `0x1801bbc6f`
- `KERNEL32!GetLastError` at `0x1801bbd4c`
- `KERNEL32!GetLastError` at `0x1801bbbd7`
- `KERNEL32!GetLastError` at `0x1801bbc6f`
- `KERNEL32!GetLastError` at `0x1801bbd4c`
- `KERNEL32!CompareStringOrdinal` at `0x1801bbc14`
- `KERNEL32!CompareStringOrdinal` at `0x1801bbc14`
- `KERNEL32!GetProcAddress` at `0x1801bbd3e`
- `KERNEL32!GetProcAddress` at `0x1801bbd3e`
- `KERNEL32!FreeLibrary` at `0x1801bc527`
- `KERNEL32!FreeLibrary` at `0x1801bc527`

## string_xrefs

- `0x1801bc043`: `CreateProxyForPlugin failed for WebAuthn.dll`
- `0x1801bc414`: `Add Plugin`
- `0x1801bc233`: `WebAuthnDvcPluginProxy`
- `0x1801bc1cd`: `QueryInterface for IUnknown on IWTSPluginProxy failed`
- `0x1801bc32b`: `QueryInterface for IWTSPlugin on IWTSPluginProxy failed`
- `0x1801bc27d`: `SetIUnknownProperty( TS_PROP_CORE_WEBAUTHN_DVC_PLUGIN_PROXY ) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DynVCPluginLoader::_LoadOnePluginDirect(
        DynVCPluginLoader *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  int ActivityIdPrefix; // eax
  HMODULE LibraryW; // rax
  HINSTANCE v7; // rdx
  HMODULE v8; // r14
  signed int LastError; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  signed int v13; // eax
  WebAuthnRedirConfig *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v20)(GUID *, unsigned int *, struct IWTSPlugin **); // rdi
  signed int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // eax
  struct IWTSPlugin **v30; // rax
  struct IWTSPlugin **v31; // r12
  HINSTANCE v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned int v39; // eax
  struct IWTSPlugin *v40; // rbx
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rsi
  __int64 v52; // r8
  struct IWTSPluginProxy *v53; // rdi
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  int v62; // eax
  __int64 i; // rdi
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  int v67; // eax
  int v68; // eax
  __int64 v69; // rdi
  unsigned int j; // edx
  struct IWTSPlugin *v71; // rcx
  __int64 v73; // [rsp+28h] [rbp-48h]
  __int64 v74; // [rsp+30h] [rbp-40h] BYREF
  __int64 v75; // [rsp+38h] [rbp-38h] BYREF
  struct IWTSPlugin *v76; // [rsp+40h] [rbp-30h] BYREF
  struct IWTSPluginProxy *v77; // [rsp+48h] [rbp-28h] BYREF
  HMODULE v78; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v79[3]; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v80; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v81; // [rsp+B8h] [rbp+48h] BYREF

  v79[1] = -2;
  v79[0] = 0;
  v80 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, a2, a3);
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      77,
      (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
      ActivityIdPrefix,
      (__int64)a2);
  }
  LibraryW = LoadLibraryW(a2);
  v8 = LibraryW;
  v78 = LibraryW;
  if ( !LibraryW )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect>::GetImpl'::`2'::impl) )
    {
      LastError = GetLastError();
      InitOnceExecuteOnce(&InitOnce, WebAuthnRedirConfig::_anonymous_namespace_::InitializeWebAuthnDynVCPath, 0, 0);
      if ( CompareStringOrdinal(&Buffer, -1, a2, -1, 1) == 2 )
      {
        tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>>(&v81);
        if ( v81 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v81 + 8) )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>::operator->(
                                   &v81,
                                   &v77)
                    + 276LL) = LastError;
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>(&v77);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>,wil::err_returncode_policy>(&v81);
      }
      if ( LastError <= 0 )
        goto LABEL_17;
      LastError = (unsigned __int16)LastError;
    }
    else
    {
      v13 = GetLastError();
      LastError = v13;
      if ( v13 <= 0 )
      {
LABEL_17:
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpX_GetActivityIdPrefix(v11, v10, v12);
          WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, LastError);
        }
        goto LABEL_126;
      }
      LastError = (unsigned __int16)v13;
    }
    LastError |= 0x80070000;
    goto LABEL_17;
  }
  if ( (unsigned int)WebAuthnRedirConfig::IsWebAuthnRedirDynVCPlugin(LibraryW, v7)
    && (unsigned int)WebAuthnRedirConfig::IsWebAuthnRedirGloballyDisabled(v14) )
  {
    LastError = 0;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpX_GetActivityIdPrefix(v16, v15, v17);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids, v18);
    }
    goto LABEL_126;
  }
  ProcAddress = GetProcAddress(v8, "VirtualChannelGetInstance");
  v20 = (__int64 (__fastcall *)(GUID *, unsigned int *, struct IWTSPlugin **))ProcAddress;
  if ( !ProcAddress )
  {
    v21 = GetLastError();
    LastError = v21;
    if ( v21 > 0 )
      LastError = (unsigned __int16)v21 | 0x80070000;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpX_GetActivityIdPrefix(v23, v22, v24);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
        v25,
        LastError);
    }
    goto LABEL_126;
  }
  LastError = ((__int64 (__fastcall *)(GUID *, unsigned int *, _QWORD))ProcAddress)(&IID_IWTSPlugin, &v80, 0);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpX_GetActivityIdPrefix(v27, v26, v28);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
        v29,
        (__int64)"VirtualChannelGetInstance",
        LastError);
    }
    goto LABEL_126;
  }
  v30 = (struct IWTSPlugin **)operator new(saturated_mul(v80, 8u));
  v31 = v30;
  if ( !v30 )
  {
    LastError = -2147024882;
    goto LABEL_126;
  }
  memset_0(v30, 0, 8LL * v80);
  LastError = v20(&IID_IWTSPlugin, &v80, v31);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v35 = RdpX_GetActivityIdPrefix(v33, v32, v34);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
        v35,
        (__int64)"VirtualChannelGetInstance",
        LastError);
    }
    goto LABEL_121;
  }
  if ( !(unsigned int)WebAuthnRedirConfig::IsWebAuthnRedirDynVCPlugin(v8, v32) )
    goto LABEL_104;
  v76 = 0;
  v77 = 0;
  v75 = 0;
  v74 = 0;
  v81 = 0;
  if ( v80 == 1 )
  {
    v40 = *v31;
    if ( !*v31 )
    {
      LastError = -2147418113;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = RdpX_GetActivityIdPrefix(v37, v36, v38);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids, v41);
      }
      goto LABEL_52;
    }
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v76);
    v76 = v40;
    *v31 = 0;
    LastError = CreateProxyForPlugin(v40, &v77);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = RdpX_GetActivityIdPrefix(v43, v42, v44);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v45,
          (__int64)"CreateProxyForPlugin failed for WebAuthn.dll",
          LastError);
      }
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v77 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v77 + 16LL))(v77);
      goto LABEL_53;
    }
    LastError = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 64LL))(
                  *((_QWORD *)this + 11),
                  &v74);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v49 = RdpX_GetActivityIdPrefix(v47, v46, v48);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v49,
          (__int64)"GetCoreAPI failed",
          LastError);
      }
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v77 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v77 + 16LL))(v77);
      goto LABEL_53;
    }
    v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 40LL))(v74);
    if ( !v51 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v50, v52);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v68,
          (__int64)"coreProps");
      }
      LastError = -2147467261;
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v77 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v77 + 16LL))(v77);
      goto LABEL_53;
    }
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
    v81 = v51;
    TCntPtr<IPin>::SafeAddRef(&v81);
    v53 = v77;
    LastError = (**(__int64 (__fastcall ***)(struct IWTSPluginProxy *, GUID *, __int64 *))v77)(
                  v77,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  &v75);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v56 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v54, v55);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v56,
          (__int64)"QueryInterface for IUnknown on IWTSPluginProxy failed",
          LastError);
      }
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v53 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v53 + 16LL))(v53);
      goto LABEL_53;
    }
    LastError = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v51 + 48LL))(
                  v51,
                  "WebAuthnDvcPluginProxy",
                  v75);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v59 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v57, v58);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v59,
          (__int64)"SetIUnknownProperty( TS_PROP_CORE_WEBAUTHN_DVC_PLUGIN_PROXY ) failed",
          LastError);
      }
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v53 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v53 + 16LL))(v53);
      goto LABEL_53;
    }
    LastError = (**(__int64 (__fastcall ***)(struct IWTSPluginProxy *, GUID *, struct IWTSPlugin **))v53)(
                  v53,
                  &GUID_a1230201_1439_4e62_a414_190d0ac3d40e,
                  v31);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v62 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v60, v61);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v62,
          (__int64)"QueryInterface for IWTSPlugin on IWTSPluginProxy failed",
          LastError);
      }
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
      if ( v53 )
        (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v53 + 16LL))(v53);
      goto LABEL_53;
    }
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
    if ( v53 )
      (*(void (__fastcall **)(struct IWTSPluginProxy *))(*(_QWORD *)v53 + 16LL))(v53);
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v76);
LABEL_104:
    for ( i = 0; (unsigned int)i < v80; i = (unsigned int)(i + 1) )
    {
      LastError = (*(__int64 (__fastcall **)(_QWORD, struct IWTSPlugin *))(**((_QWORD **)this + 10) + 32LL))(
                    *((_QWORD *)this + 10),
                    v31[i]);
      if ( LastError < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v67 = RdpX_GetActivityIdPrefix(v65, v64, v66);
        LODWORD(v73) = LastError;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          91,
          (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
          v67,
          (__int64)"Add Plugin",
          v73);
      }
    }
    if ( (unsigned int)DynArray<HINSTANCE__ *,unsigned long>::Add((char *)this + 112, &v78) )
      v8 = 0;
    else
      LastError = -2147024882;
    goto LABEL_121;
  }
  LastError = -2147418113;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v39 = RdpX_GetActivityIdPrefix(v37, v36, v38);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids, v39);
  }
LABEL_52:
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v81);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v74);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v75);
LABEL_53:
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v76);
LABEL_121:
  v69 = 0;
  for ( j = v80; (unsigned int)v69 < j; v69 = (unsigned int)(v69 + 1) )
  {
    v71 = v31[v69];
    if ( v71 )
    {
      ((void (__fastcall *)(struct IWTSPlugin *))v71->lpVtbl->Release)(v71);
      j = v80;
    }
  }
  operator delete(v31);
LABEL_126:
  if ( v8 )
    FreeLibrary(v8);
  TCntPtr<ITSViewerRecorder>::SafeRelease(v79);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1801bbb28  mov     rax, rsp
0x1801bbb2b  push    rbp
0x1801bbb2c  push    rdi
0x1801bbb2d  push    r12
0x1801bbb2f  push    r14
0x1801bbb31  push    r15
0x1801bbb33  mov     rbp, rsp
0x1801bbb36  sub     rsp, 70h
0x1801bbb3a  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1801bbb42  mov     [rax+8], rbx
0x1801bbb46  mov     [rax+10h], rsi
0x1801bbb4a  mov     rdi, rdx
0x1801bbb4d  mov     r15, rcx
0x1801bbb50  mov     [rbp+var_18], 0
0x1801bbb58  mov     [rbp+arg_10], 0
0x1801bbb5f  lea     rsi, WPP_GLOBAL_Control
0x1801bbb66  lea     r12, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801bbb6d  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbb74  cmp     rax, rsi
0x1801bbb77  jz      short loc_1801BBBAA
0x1801bbb79  test    byte ptr [rax+1Ch], 1
0x1801bbb7d  jz      short loc_1801BBBAA
0x1801bbb7f  cmp     byte ptr [rax+19h], 4
0x1801bbb83  jb      short loc_1801BBBAA
0x1801bbb85  call    RdpX_GetActivityIdPrefix
0x1801bbb8a  mov     edx, 4Dh ; 'M'
0x1801bbb8f  mov     qword ptr [rsp+70h+bIgnoreCase], rdi
0x1801bbb94  mov     r9d, eax
0x1801bbb97  mov     r8, r12
0x1801bbb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbba1  mov     rcx, [rcx+10h]
0x1801bbba5  call    WPP_SF_DS
0x1801bbbaa  mov     rcx, rdi; lpLibFileName
0x1801bbbad  call    cs:__imp_LoadLibraryW
0x1801bbbb3  mov     r14, rax
0x1801bbbb6  mov     [rbp+var_20], rax
0x1801bbbba  test    rax, rax
0x1801bbbbd  jnz     loc_1801BBCD6
0x1801bbbc3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect> `wil::Feature<__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect>::GetImpl(void)'::`2'::impl
0x1801bbbca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnRedirectionInVMConnect>::__private_IsEnabled(void)
0x1801bbbcf  test    al, al
0x1801bbbd1  jz      loc_1801BBC6F
0x1801bbbd7  call    cs:__imp_GetLastError
0x1801bbbdd  mov     ebx, eax
0x1801bbbdf  xor     r9d, r9d; Context
0x1801bbbe2  xor     r8d, r8d; Parameter
0x1801bbbe5  lea     rdx, WebAuthnRedirConfig___anonymous_namespace___InitializeWebAuthnDynVCPath; InitFn
0x1801bbbec  lea     rcx, InitOnce; InitOnce
0x1801bbbf3  call    cs:__imp_InitOnceExecuteOnce
0x1801bbbf9  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1801bbc01  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801bbc05  mov     r9d, ecx; cchCount2
0x1801bbc08  mov     r8, rdi; lpString2
0x1801bbc0b  mov     edx, ecx; cchCount1
0x1801bbc0d  lea     rcx, Buffer; lpString1
0x1801bbc14  call    cs:__imp_CompareStringOrdinal
0x1801bbc1a  cmp     eax, 2
0x1801bbc1d  jnz     short loc_1801BBC66
0x1801bbc1f  lea     rcx, [rbp+arg_18]
0x1801bbc23  call    ??$open@V?$tip_test@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>>(void)
0x1801bbc28  mov     rcx, [rbp+arg_18]
0x1801bbc2c  test    rcx, rcx
0x1801bbc2f  jz      short loc_1801BBC5D
0x1801bbc31  add     rcx, 8
0x1801bbc35  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1801bbc3a  test    al, al
0x1801bbc3c  jz      short loc_1801BBC5D
0x1801bbc3e  lea     rdx, [rbp+var_28]
0x1801bbc42  lea     rcx, [rbp+arg_18]
0x1801bbc46  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>::operator->(void)
0x1801bbc4b  mov     rcx, [rax]
0x1801bbc4e  mov     [rcx+114h], ebx
0x1801bbc54  lea     rcx, [rbp+var_28]
0x1801bbc58  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>>(void)
0x1801bbc5d  lea     rcx, [rbp+arg_18]
0x1801bbc61  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthnRedirectionInVMConnectTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthnRedirectionInVMConnectTipTest,_tip_WebAuthnRedirectionInVMConnectTipTest>,wil::err_returncode_policy>(void)
0x1801bbc66  test    ebx, ebx
0x1801bbc68  jle     short loc_1801BBC84
0x1801bbc6a  movzx   ebx, bx
0x1801bbc6d  jmp     short loc_1801BBC7E
0x1801bbc6f  call    cs:__imp_GetLastError
0x1801bbc75  mov     ebx, eax
0x1801bbc77  test    eax, eax
0x1801bbc79  jle     short loc_1801BBC84
0x1801bbc7b  movzx   ebx, ax
0x1801bbc7e  or      ebx, 80070000h
0x1801bbc84  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbc8b  cmp     rax, rsi
0x1801bbc8e  jz      loc_1801BC51F
0x1801bbc94  test    byte ptr [rax+1Ch], 1
0x1801bbc98  jz      loc_1801BC51F
0x1801bbc9e  cmp     byte ptr [rax+19h], 2
0x1801bbca2  jb      loc_1801BC51F
0x1801bbca8  call    RdpX_GetActivityIdPrefix
0x1801bbcad  mov     edx, 4Eh ; 'N'
0x1801bbcb2  mov     dword ptr [rsp+70h+var_48], ebx; char
0x1801bbcb6  mov     qword ptr [rsp+70h+bIgnoreCase], rdi; __int64
0x1801bbcbb  mov     r9d, eax
0x1801bbcbe  mov     r8, r12
0x1801bbcc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbcc8  mov     rcx, [rcx+10h]; LoggerHandle
0x1801bbccc  call    WPP_SF_DSd
0x1801bbcd1  jmp     loc_1801BC51F
0x1801bbcd6  mov     rcx, r14; hModule
0x1801bbcd9  call    ?IsWebAuthnRedirDynVCPlugin@WebAuthnRedirConfig@@YAHPEAUHINSTANCE__@@@Z; WebAuthnRedirConfig::IsWebAuthnRedirDynVCPlugin(HINSTANCE__ *)
0x1801bbcde  test    eax, eax
0x1801bbce0  jz      short loc_1801BBD34
0x1801bbce2  call    ?IsWebAuthnRedirGloballyDisabled@WebAuthnRedirConfig@@YAHXZ; WebAuthnRedirConfig::IsWebAuthnRedirGloballyDisabled(void)
0x1801bbce7  test    eax, eax
0x1801bbce9  jz      short loc_1801BBD34
0x1801bbceb  xor     ebx, ebx
0x1801bbced  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbcf4  cmp     rax, rsi
0x1801bbcf7  jz      loc_1801BC51F
0x1801bbcfd  test    byte ptr [rax+1Ch], 1
0x1801bbd01  jz      loc_1801BC51F
0x1801bbd07  cmp     byte ptr [rax+19h], 4
0x1801bbd0b  jb      loc_1801BC51F
0x1801bbd11  call    RdpX_GetActivityIdPrefix
0x1801bbd16  lea     edx, [rbx+4Fh]
0x1801bbd19  mov     r9d, eax
0x1801bbd1c  mov     r8, r12
0x1801bbd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbd26  mov     rcx, [rcx+10h]
0x1801bbd2a  call    WPP_SF_d
0x1801bbd2f  jmp     loc_1801BC51F
0x1801bbd34  lea     rdx, aVirtualchannel_1; "VirtualChannelGetInstance"
0x1801bbd3b  mov     rcx, r14; hModule
0x1801bbd3e  call    cs:__imp_GetProcAddress
0x1801bbd44  mov     rdi, rax
0x1801bbd47  test    rax, rax
0x1801bbd4a  jnz     short loc_1801BBDAE
0x1801bbd4c  call    cs:__imp_GetLastError
0x1801bbd52  mov     ebx, eax
0x1801bbd54  test    eax, eax
0x1801bbd56  jle     short loc_1801BBD61
0x1801bbd58  movzx   ebx, ax
0x1801bbd5b  or      ebx, 80070000h
0x1801bbd61  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbd68  cmp     rax, rsi
0x1801bbd6b  jz      loc_1801BC51F
0x1801bbd71  test    byte ptr [rax+1Ch], 1
0x1801bbd75  jz      loc_1801BC51F
0x1801bbd7b  cmp     byte ptr [rax+19h], 2
0x1801bbd7f  jb      loc_1801BC51F
0x1801bbd85  call    RdpX_GetActivityIdPrefix
0x1801bbd8a  mov     edx, 50h ; 'P'
0x1801bbd8f  mov     [rsp+70h+bIgnoreCase], ebx
0x1801bbd93  mov     r9d, eax
0x1801bbd96  mov     r8, r12
0x1801bbd99  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbda0  mov     rcx, [rcx+10h]
0x1801bbda4  call    WPP_SF_Dd
0x1801bbda9  jmp     loc_1801BC51F
0x1801bbdae  xor     r8d, r8d
0x1801bbdb1  lea     rdx, [rbp+arg_10]
0x1801bbdb5  lea     rcx, IID_IWTSPlugin
0x1801bbdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbdc1  mov     ebx, eax
0x1801bbdc3  test    eax, eax
0x1801bbdc5  jns     short loc_1801BBE20
0x1801bbdc7  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbdce  cmp     rax, rsi
0x1801bbdd1  jz      loc_1801BC51F
0x1801bbdd7  test    byte ptr [rax+1Ch], 8
0x1801bbddb  jz      loc_1801BC51F
0x1801bbde1  cmp     byte ptr [rax+19h], 2
0x1801bbde5  jb      loc_1801BC51F
0x1801bbdeb  call    RdpX_GetActivityIdPrefix
0x1801bbdf0  mov     edx, 51h ; 'Q'
0x1801bbdf5  mov     dword ptr [rsp+70h+var_48], ebx
0x1801bbdf9  lea     rcx, aVirtualchannel_1; "VirtualChannelGetInstance"
0x1801bbe00  mov     qword ptr [rsp+70h+bIgnoreCase], rcx
0x1801bbe05  mov     r9d, eax
0x1801bbe08  mov     r8, r12
0x1801bbe0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbe12  mov     rcx, [rcx+10h]
0x1801bbe16  call    WPP_SF_DsD
0x1801bbe1b  jmp     loc_1801BC51F
0x1801bbe20  mov     ecx, [rbp+arg_10]
0x1801bbe23  mov     eax, 8
0x1801bbe28  mul     rcx
0x1801bbe2b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bbe32  cmovb   rax, rcx
0x1801bbe36  mov     rcx, rax; Size
0x1801bbe39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801bbe3e  mov     r12, rax
0x1801bbe41  test    rax, rax
0x1801bbe44  jnz     short loc_1801BBE50
0x1801bbe46  mov     ebx, 8007000Eh
0x1801bbe4b  jmp     loc_1801BC51F
0x1801bbe50  mov     r8d, [rbp+arg_10]
0x1801bbe54  shl     r8, 3; Size
0x1801bbe58  xor     edx, edx; Val
0x1801bbe5a  mov     rcx, r12; void *
0x1801bbe5d  call    memset_0
0x1801bbe62  mov     r8, r12
0x1801bbe65  lea     rdx, [rbp+arg_10]
0x1801bbe69  lea     rcx, IID_IWTSPlugin
0x1801bbe70  mov     rax, rdi
0x1801bbe73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbe78  mov     ebx, eax
0x1801bbe7a  test    eax, eax
0x1801bbe7c  jns     short loc_1801BBEDB
0x1801bbe7e  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbe85  cmp     rax, rsi
0x1801bbe88  jz      loc_1801BC4F0
0x1801bbe8e  test    byte ptr [rax+1Ch], 8
0x1801bbe92  jz      loc_1801BC4F0
0x1801bbe98  cmp     byte ptr [rax+19h], 2
0x1801bbe9c  jb      loc_1801BC4F0
0x1801bbea2  call    RdpX_GetActivityIdPrefix
0x1801bbea7  mov     edx, 52h ; 'R'
0x1801bbeac  mov     dword ptr [rsp+70h+var_48], ebx
0x1801bbeb0  lea     rcx, aVirtualchannel_1; "VirtualChannelGetInstance"
0x1801bbeb7  mov     qword ptr [rsp+70h+bIgnoreCase], rcx
0x1801bbebc  mov     r9d, eax
0x1801bbebf  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801bbec6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbecd  mov     rcx, [rcx+10h]
0x1801bbed1  call    WPP_SF_DsD
0x1801bbed6  jmp     loc_1801BC4F0
0x1801bbedb  mov     rcx, r14; hModule
0x1801bbede  call    ?IsWebAuthnRedirDynVCPlugin@WebAuthnRedirConfig@@YAHPEAUHINSTANCE__@@@Z; WebAuthnRedirConfig::IsWebAuthnRedirDynVCPlugin(HINSTANCE__ *)
0x1801bbee3  test    eax, eax
0x1801bbee5  jz      loc_1801BC3CD
0x1801bbeeb  mov     [rbp+var_30], 0
0x1801bbef3  mov     [rbp+var_28], 0
0x1801bbefb  mov     [rbp+var_38], 0
0x1801bbf03  mov     [rbp+var_40], 0
0x1801bbf0b  mov     [rbp+arg_18], 0
0x1801bbf13  cmp     [rbp+arg_10], 1
0x1801bbf17  jz      short loc_1801BBF87
0x1801bbf19  mov     ebx, 8000FFFFh
0x1801bbf1e  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbf25  cmp     rax, rsi
0x1801bbf28  jz      short loc_1801BBF5B
0x1801bbf2a  test    byte ptr [rax+1Ch], 1
0x1801bbf2e  jz      short loc_1801BBF5B
0x1801bbf30  cmp     byte ptr [rax+19h], 2
0x1801bbf34  jb      short loc_1801BBF5B
0x1801bbf36  call    RdpX_GetActivityIdPrefix
0x1801bbf3b  mov     edx, 53h ; 'S'
0x1801bbf40  mov     r9d, eax
0x1801bbf43  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801bbf4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbf51  mov     rcx, [rcx+10h]
0x1801bbf55  call    WPP_SF_d
0x1801bbf5a  nop
0x1801bbf5b  lea     rcx, [rbp+arg_18]; void *
0x1801bbf5f  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbf64  nop
0x1801bbf65  lea     rcx, [rbp+var_40]; void *
0x1801bbf69  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbf6e  nop
0x1801bbf6f  lea     rcx, [rbp+var_38]; void *
0x1801bbf73  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbf78  nop
0x1801bbf79  lea     rcx, [rbp+var_30]; void *
0x1801bbf7d  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbf82  jmp     loc_1801BC4F0
0x1801bbf87  mov     rbx, [r12]
0x1801bbf8b  test    rbx, rbx
0x1801bbf8e  jnz     short loc_1801BBFF2
0x1801bbf90  mov     ebx, 8000FFFFh
0x1801bbf95  mov     rax, cs:WPP_GLOBAL_Control
0x1801bbf9c  cmp     rax, rsi
0x1801bbf9f  jz      short loc_1801BBFD2
0x1801bbfa1  test    byte ptr [rax+1Ch], 1
0x1801bbfa5  jz      short loc_1801BBFD2
0x1801bbfa7  cmp     byte ptr [rax+19h], 2
0x1801bbfab  jb      short loc_1801BBFD2
0x1801bbfad  call    RdpX_GetActivityIdPrefix
0x1801bbfb2  mov     edx, 54h ; 'T'
0x1801bbfb7  mov     r9d, eax
0x1801bbfba  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801bbfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bbfc8  mov     rcx, [rcx+10h]
0x1801bbfcc  call    WPP_SF_d
0x1801bbfd1  nop
0x1801bbfd2  lea     rcx, [rbp+arg_18]; void *
0x1801bbfd6  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbfdb  nop
0x1801bbfdc  lea     rcx, [rbp+var_40]; void *
0x1801bbfe0  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbfe5  nop
0x1801bbfe6  lea     rcx, [rbp+var_38]; void *
0x1801bbfea  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbfef  nop
0x1801bbff0  jmp     short loc_1801BBF79
0x1801bbff2  lea     rcx, [rbp+var_30]; void *
0x1801bbff6  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801bbffb  mov     [rbp+var_30], rbx
0x1801bbfff  mov     qword ptr [r12], 0
0x1801bc007  lea     rdx, [rbp+var_28]; struct IWTSPluginProxy **
0x1801bc00b  mov     rcx, rbx; struct IWTSPlugin *
0x1801bc00e  call    ?CreateProxyForPlugin@@YAJPEAUIWTSPlugin@@PEAPEAUIWTSPluginProxy@@@Z; CreateProxyForPlugin(IWTSPlugin *,IWTSPluginProxy * *)
0x1801bc013  mov     ebx, eax
0x1801bc015  test    eax, eax
0x1801bc017  jns     loc_1801BC0A3
  ... truncated ...
```
