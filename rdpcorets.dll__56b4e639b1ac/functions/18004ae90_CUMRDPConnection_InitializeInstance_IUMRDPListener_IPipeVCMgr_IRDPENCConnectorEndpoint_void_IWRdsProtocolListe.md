# CUMRDPConnection::InitializeInstance(IUMRDPListener *,IPipeVCMgr *,IRDPENCConnectorEndpoint *,void *,IWRdsProtocolListenerCallback *,CUMRDPProtocolManager *,IRdpMTListener *,ulong,_WRDS_CONNECTION_SETTINGS *,IRDPENCTcpStreamPool *,IRDPENCNetStream *,IUnknown *,char const *)

- ea: `0x18004ae90`
- end: `0x18004bfe9`
- name: `?InitializeInstance@CUMRDPConnection@@UEAAJPEAUIUMRDPListener@@PEAUIPipeVCMgr@@PEAUIRDPENCConnectorEndpoint@@PEAXPEAUIWRdsProtocolListenerCallback@@PEAVCUMRDPProtocolManager@@PEAUIRdpMTListener@@KPEAU_WRDS_CONNECTION_SETTINGS@@PEAUIRDPENCTcpStreamPool@@PEAUIRDPENCNetStream@@PEAUIUnknown@@PEBD@Z`
- size: `4441`
- prototype: `__int64 __fastcall(CUMRDPConnection *this, struct IUMRDPListener *, struct IPipeVCMgr *, struct IRDPENCConnectorEndpoint *, void *, struct IWRdsProtocolListenerCallback *, struct CUMRDPProtocolManager *, struct IRdpMTListener *, unsigned int, struct _WRDS_CONNECTION_SETTINGS *, struct IRDPENCTcpStreamPool *, struct IRDPENCNetStream *, struct IUnknown *, const char *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009088`
- `0x180009628`
- `0x18000f784`
- `0x180010908`
- `0x180010f24`
- `0x180012200`
- `0x18001e8a8`
- `0x1800231f0`
- `0x180033da0`
- `0x180034970`
- `0x18004ae90`
- `0x180050cd4`
- `0x180055d54`
- `0x18006233c`
- `0x18014d010`

## import_xrefs

- `RDPBASE!PAL_System_CritSecEnter` at `0x18004af30`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004b04e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004bcaf`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004af30`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004b04e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004bcaf`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ba3a`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ba3a`
- `OLEAUT32!__imp_VariantInit` at `0x18004b9de`
- `OLEAUT32!__imp_VariantInit` at `0x18004ba27`
- `OLEAUT32!__imp_VariantInit` at `0x18004b9de`
- `OLEAUT32!__imp_VariantInit` at `0x18004ba27`
- `OLEAUT32!__imp_VariantClear` at `0x18004ba08`
- `OLEAUT32!__imp_VariantClear` at `0x18004baf7`
- `OLEAUT32!__imp_VariantClear` at `0x18004ba08`
- `OLEAUT32!__imp_VariantClear` at `0x18004baf7`

## string_xrefs

- `0x18004b2a8`: `UserConfiguredTransportMode`
- `0x18004b34e`: `SetPropertyUnsignedLong(CONN_PROPERTY_USER_CONFIG_TRANSPORT) failed.`
- `0x18004b5f7`: `Failed to create lic plugin Factory`
- `0x18004b717`: `Failed to init lic plugin`
- `0x18004b772`: `Failed to register lic plugin factory`
- `0x18004bbaa`: `Failed to initialize the plugin settings`
- `0x18004bcf0`: `Failed to create the terminal name`
- `0x18004bdf2`: `Allocation failed. The ability to query some stack config will not be available.`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::InitializeInstance(
        CUMRDPConnection *this,
        struct IUMRDPListener *a2,
        struct IPipeVCMgr *a3,
        struct IRDPENCConnectorEndpoint *a4,
        void *a5,
        struct IWRdsProtocolListenerCallback *a6,
        struct CUMRDPProtocolManager *a7,
        struct IRdpMTListener *a8,
        unsigned int a9,
        struct _WRDS_CONNECTION_SETTINGS *a10,
        struct IRDPENCTcpStreamPool *a11,
        struct IRDPENCNetStream *a12,
        struct IUnknown *a13,
        const char *a14)
{
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // r9d
  _QWORD *v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rdx
  int v24; // ecx
  signed int v25; // edi
  __int64 *v26; // rdx
  const char **v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  char *v31; // rdx
  const char *v32; // rax
  const char **v33; // rax
  __int64 v34; // rcx
  signed int v35; // eax
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  const char *v42; // rax
  __int16 *v43; // rdx
  signed int v44; // eax
  int v45; // r8d
  int v46; // r9d
  signed int v47; // eax
  int v48; // r8d
  int v49; // r9d
  char *v50; // rdx
  __int64 v51; // rcx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // ebx
  __int64 v56; // rdx
  int v57; // ecx
  __int64 v58; // r8
  int v59; // r9d
  __int64 v60; // rdx
  int v61; // ecx
  __int64 v62; // r8
  int v63; // r9d
  const char **v64; // rcx
  __int64 v65; // r8
  int v66; // ecx
  int v67; // r8d
  int v68; // r9d
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // r8
  unsigned int *v79; // [rsp+20h] [rbp-E0h]
  const char **v80; // [rsp+30h] [rbp-D0h]
  const char **v81; // [rsp+30h] [rbp-D0h]
  const char **v82; // [rsp+38h] [rbp-C8h]
  unsigned int *v83; // [rsp+38h] [rbp-C8h]
  const char **v84; // [rsp+40h] [rbp-C0h]
  const char **v85; // [rsp+40h] [rbp-C0h]
  const char **v86; // [rsp+48h] [rbp-B8h]
  const char **v87; // [rsp+48h] [rbp-B8h]
  unsigned int v88; // [rsp+50h] [rbp-B0h] BYREF
  const char *v89; // [rsp+58h] [rbp-A8h] BYREF
  const char *v90; // [rsp+60h] [rbp-A0h] BYREF
  const char *v91; // [rsp+68h] [rbp-98h] BYREF
  const char *v92; // [rsp+70h] [rbp-90h] BYREF
  const char *v93; // [rsp+78h] [rbp-88h] BYREF
  const char *v94; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v95; // [rsp+88h] [rbp-78h] BYREF
  const char *v96; // [rsp+90h] [rbp-70h] BYREF
  __int64 v97; // [rsp+98h] [rbp-68h] BYREF
  __int64 v98; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v99; // [rsp+A8h] [rbp-58h] BYREF
  void *v100; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v101; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v102; // [rsp+C0h] [rbp-40h] BYREF
  char *v103; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR psz[32]; // [rsp+100h] [rbp+0h] BYREF

  v93 = (const char *)a6;
  v91 = (const char *)a3;
  v89 = (const char *)a4;
  v94 = (const char *)a10;
  v96 = a14;
  v97 = 0;
  v100 = 0;
  v101 = 0;
  v99 = 0;
  v95 = 0;
  memset_0(psz, 0, sizeof(psz));
  v21 = (_QWORD *)((char *)this + 120);
  v22 = 0;
  v98 = 0;
  v103 = (char *)this + 120;
  if ( *((_DWORD *)this + 32) )
    PAL_System_CritSecEnter(*v21, v18, v19);
  if ( !a10 || !a2 || !a7 || !a3 || !a4 && !a5 && !a12 || !v93 )
  {
    v25 = -2147019873;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v91) = 614;
      v96 = "Called in bad state";
      v94 = "InitializeInstance";
      v89 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v26 = (__int64 *)byte_180197EA9;
      v90 = "Error condition failed";
      v86 = &v96;
      v84 = &v94;
      v82 = &v91;
      v80 = &v89;
      v27 = &v90;
      goto LABEL_124;
    }
LABEL_125:
    *((_QWORD *)this + 33) = 0;
    CUMRDPConnection::TerminateInstance(this);
    goto LABEL_126;
  }
  v25 = (*(__int64 (__fastcall **)(struct IUMRDPListener *, OLECHAR *, __int64))(*(_QWORD *)a2 + 32LL))(a2, psz, 32);
  if ( v25 < 0 )
  {
    LODWORD(v21) = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v92) = 617;
      v93 = "Failed to get the listener name";
      v91 = "InitializeInstance";
      v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v26 = qword_180197E58;
      v89 = "Error HResult failed";
      v86 = &v93;
      v84 = &v91;
      v82 = &v92;
      v80 = &v90;
      v27 = &v89;
LABEL_124:
      v88 = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v21,
        (_DWORD)v26,
        v19,
        v20,
        (__int64)v27,
        (__int64)&v88,
        (__int64)v80,
        (__int64)v82,
        (__int64)v84,
        (__int64)v86);
      goto LABEL_125;
    }
    goto LABEL_125;
  }
  v92 = (char *)this + 104;
  if ( *((_DWORD *)this + 28) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 13), v23, v19);
  if ( (*((_DWORD *)this - 5) & 6) != 2 )
  {
    v25 = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v91) = 622;
      v96 = "Called in bad state";
      v94 = "InitializeInstance";
      v89 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v88 = -2147418113;
      v90 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)&byte_180197E07,
        v19,
        v20,
        (__int64)&v90,
        (__int64)&v88,
        (__int64)&v89,
        (__int64)&v91,
        (__int64)&v94,
        (__int64)&v96);
    }
    v64 = &v92;
    goto LABEL_108;
  }
  if ( v91 != *((const char **)this + 27) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 216, v23, v19);
    *((_QWORD *)this + 27) = v91;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 216);
  }
  if ( a2 != *((struct IUMRDPListener **)this + 30) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 240, v23, v19);
    *((_QWORD *)this + 30) = a2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 240);
  }
  if ( v89 != *((const char **)this + 32) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 256, v23, v19);
    *((_QWORD *)this + 32) = v89;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 256);
  }
  *((_QWORD *)this + 33) = a5;
  if ( a12 != *((struct IRDPENCNetStream **)this + 34) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 272, v23, v19);
    *((_QWORD *)this + 34) = a12;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 272);
  }
  if ( a7 != *((struct CUMRDPProtocolManager **)this + 73) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 584, v23, v19);
    *((_QWORD *)this + 73) = a7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 584);
  }
  if ( *((_QWORD *)this + 18) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v98, v23, v19);
    v22 = *((_QWORD *)this + 18);
    v98 = v22;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v98);
  }
  if ( a8 != *((struct IRdpMTListener **)this + 29) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 232, v23, v19);
    *((_QWORD *)this + 29) = a8;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 232);
  }
  *((_DWORD *)this + 167) = a9;
  if ( a11 != *((struct IRDPENCTcpStreamPool **)this + 22) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 176, v23, v19);
    *((_QWORD *)this + 22) = a11;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 176);
  }
  if ( a13 != *((struct IUnknown **)this + 78) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 624, v23, v19);
    *((_QWORD *)this + 78) = a13;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 624);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v92);
  if ( !v22 )
  {
    v25 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 641;
    v89 = "spCoreConMgr is NULL";
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v31 = (char *)&word_180197DB6;
    v32 = "Error condition failed";
    goto LABEL_38;
  }
  CUMRDPConnection::ReadRegistryGroupPolicy(
    (CUMRDPConnection *)((char *)this - 48),
    L"SelectNetworkDetect",
    L"DisableNetworkDetect",
    1,
    0,
    0);
  v34 = *((_QWORD *)this + 17);
  LODWORD(v92) = 0;
  if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, const char **))(*(_QWORD *)v34 + 40LL))(
         v34,
         L"UserConfiguredTransportMode",
         &v92) < 0
    && (CUMRDPConnection::ReadRegistryGroupPolicy(
          (CUMRDPConnection *)((char *)this - 48),
          L"SelectTransport",
          L"UserConfiguredTransportMode",
          1,
          0,
          0),
        (*(int (__fastcall **)(_QWORD, const unsigned __int16 *, const char **))(**((_QWORD **)this + 17) + 40LL))(
          *((_QWORD *)this + 17),
          L"UserConfiguredTransportMode",
          &v92) < 0)
    || !(_DWORD)v92 )
  {
    v35 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this + 17) + 72LL))(
            *((_QWORD *)this + 17),
            L"UserConfiguredTransportMode",
            2);
    if ( v35 < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      v88 = v35;
      v89 = "InitializeInstance";
      v90 = "SetPropertyUnsignedLong(CONN_PROPERTY_USER_CONFIG_TRANSPORT) failed.";
      v91 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)&byte_180197D77,
        v36,
        v37,
        (__int64)&v91,
        (__int64)&v90,
        (__int64)&v88,
        (__int64)&v89);
    }
  }
  v38 = *((_QWORD *)this + 17);
  LODWORD(v92) = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, const char **))(*(_QWORD *)v38 + 40LL))(
         v38,
         L"ReverseConnectMode",
         &v92) >= 0 )
    *((_DWORD *)this + 198) = (_DWORD)v92 != 0;
  if ( *((_DWORD *)this + 198) )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v42 = "This connection is WVD reverse connect";
      v43 = word_180197D52;
LABEL_53:
      v89 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v39,
        (_DWORD)v43,
        v40,
        v41,
        (__int64)&v89);
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v42 = "This connection is direct or non-internet connection";
    v43 = (__int16 *)byte_180197D2D;
    goto LABEL_53;
  }
  v88 = 1;
  CUMRDPConnection::ReadRegistryGroupPolicy(
    (CUMRDPConnection *)((char *)this - 48),
    L"fEnableRemoteFXAdvancedRemoteApp",
    L"RDP::RemoteApp::fEnableRemoteFXAdvancedRemoteApp",
    0,
    &v88,
    0);
  v44 = CUMRDPConnection::CheckAndSetSoftSyncCapabilities((CUMRDPConnection *)((char *)this - 48));
  if ( v44 < 0 && (unsigned int)dword_1801B76C8 > 3 )
  {
    v88 = v44;
    v89 = "InitializeInstance";
    v90 = "Failed to Check and Set Soft Sync Caps";
    v91 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&word_180197CEE,
      v45,
      v46,
      (__int64)&v91,
      (__int64)&v90,
      (__int64)&v88,
      (__int64)&v89);
  }
  v47 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 17) + 72LL))(
          *((_QWORD *)this + 17),
          L"DisableConnectionMonitor",
          0);
  if ( v47 < 0 && (unsigned int)dword_1801B76C8 > 3 )
  {
    v88 = v47;
    v89 = "InitializeInstance";
    v90 = "SetPropertyUnsignedLong(CONN_PROPERTY_DISABLE_CONN_MONITOR) failed.";
    v91 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&byte_180197CAF,
      v48,
      v49,
      (__int64)&v91,
      (__int64)&v90,
      (__int64)&v88,
      (__int64)&v89);
  }
  CUMRDPConnection::ReadRegistryGroupPolicy(
    (CUMRDPConnection *)((char *)this - 48),
    L"DisableConnectionMonitor",
    L"DisableConnectionMonitor",
    1,
    0,
    0);
  v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 17) + 72LL))(
          *((_QWORD *)this + 17),
          L"RDPWDRemoteDesktopMode",
          1);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 740;
    v89 = "SetPropertyUnsignedLong(CONN_PROPERTY_RDPWD_REMOTE_DESKTOP_MODE) failed.";
    v31 = (char *)&word_180197C5E;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
    goto LABEL_38;
  }
  v25 = __RDPAPIDLL__CreateInstance(
          *((struct IUnknown **)this + 17),
          &CLSID_UMRDPLICPluginFactory,
          &IID_IRDPCOREChannelPluginFactory,
          &v100);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 749;
    v89 = "Failed to create lic plugin Factory";
    v31 = byte_180197C0D;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
    goto LABEL_38;
  }
  v25 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v100)(v100, &IID_IUMTSLicensePluginFactory, &v99);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 752;
    v89 = "Failed to QI UMTS LIC factory Interface";
    v31 = (char *)&dword_180197BBC;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
    goto LABEL_38;
  }
  v25 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this - 2))(
          *((_QWORD *)this - 2),
          &IID_IUMTSLicenseEvents,
          &v101);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 755;
    v89 = "Failed to QI UMTS LIC Events Interface";
    v31 = byte_180197B6B;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
    goto LABEL_38;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v99 + 24LL))(v99, v101);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 758;
    v89 = "Failed to init lic plugin";
    v31 = (char *)word_180197B1A;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
    goto LABEL_38;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v22 + 64LL))(v22, v100);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v88 = 761;
    v89 = "Failed to register lic plugin factory";
    v31 = byte_180197AC9;
    v93 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v32 = "Error HResult failed";
LABEL_38:
    v91 = v32;
    v87 = &v89;
    v85 = &v90;
    v83 = &v88;
    v81 = &v93;
    v33 = &v91;
    v90 = "InitializeInstance";
LABEL_39:
    LODWORD(v92) = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v28,
      (_DWORD)v31,
      v29,
      v30,
      (__int64)v33,
      (__int64)&v92,
      (__int64)v81,
      (__int64)v83,
      (__int64)v85,
      (__int64)v87);
    goto LABEL_125;
  }
  v50 = (char *)this + 8;
  if ( this == (CUMRDPConnection *)48 )
    v50 = 0;
  v25 = (*(__int64 (__fastcall **)(const char *, char *, const char *, __int64 *))(*(_QWORD *)v93 + 24LL))(
          v93,
          v50,
          v94,
          &v97);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v89 = "InitializeInstance";
    v94 = "Failed OnConnected to Listener callback";
    v31 = (char *)qword_180197A78;
    v88 = 771;
    v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v93 = "Error HResult failed";
    v87 = &v94;
    v85 = &v89;
    v83 = &v88;
    v81 = &v90;
    v33 = &v93;
    goto LABEL_39;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v97 + 56LL))(v97, &v95);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_125;
    v89 = "InitializeInstance";
    v94 = "Failed to query the connection id";
    v31 = &byte_180197A27;
    v88 = 774;
    v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v93 = "Error HResult failed";
    v87 = &v94;
    v85 = &v89;
    v83 = &v88;
    v81 = &v90;
    v33 = &v93;
    goto LABEL_39;
  }
  v51 = *((_QWORD *)this + 17);
  v88 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v51 + 40LL))(
         v51,
         L"ConnectionID",
         &v88) < 0 )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 17) + 72LL))(
            *((_QWORD *)this + 17),
            L"ConnectionID",
            v95);
    if ( v25 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v89 = "InitializeInstance";
        v94 = "Failed to set the connection id property in the platform context";
        LODWORD(v92) = 790;
        v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v93 = "Error HResult failed";
        LODWORD(v91) = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v52,
          (unsigned int)&word_1801979D6,
          v53,
          v54,
          (__int64)&v93,
          (__int64)&v91,
          (__int64)&v90,
          (__int64)&v92,
          (__int64)&v89,
          (__int64)&v94);
      }
      goto LABEL_125;
    }
  }
  VariantInit(&pvarg);
  v55 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 17) + 24LL))(
          *((_QWORD *)this + 17),
          L"RDP::TerminalName",
          &pvarg);
  VariantClear(&pvarg);
  if ( v55 < 0 )
  {
    memset(&v102, 0, sizeof(v102));
    VariantInit(&v102);
    v102.vt = 8;
    v102.llVal = (LONGLONG)SysAllocString(psz);
    if ( !v102.llVal )
    {
      v25 = -2147024882;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_125;
      v89 = "InitializeInstance";
      v94 = "Failed to alloc the listener name property";
      v31 = byte_180197985;
      LODWORD(v91) = 805;
      v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v93 = "Error condition failed";
      v87 = &v94;
      v85 = &v89;
      v83 = (unsigned int *)&v91;
      v81 = &v90;
      v33 = &v93;
      goto LABEL_39;
    }
    v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 17) + 56LL))(
            *((_QWORD *)this + 17),
            L"RDP::TerminalName",
            &v102);
    VariantClear(&v102);
    if ( v25 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_125;
      v89 = "InitializeInstance";
      v94 = "Failed to set the listener name property in the platform context";
      v31 = (char *)&dword_180197934;
      LODWORD(v91) = 809;
      v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v93 = "Error HResult failed";
      v87 = &v94;
      v85 = &v89;
      v83 = (unsigned int *)&v91;
      v81 = &v90;
      v33 = &v93;
      goto LABEL_39;
    }
  }
  v25 = InitializeGfxSettings(v95, (struct IRDPCollection **)this + 76);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v89 = "InitializeInstance";
      v94 = "Failed to initialize the plugin settings";
      LODWORD(v91) = 815;
      v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v93 = "Error HResult failed";
      v88 = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v57,
        (unsigned int)byte_1801978E3,
        v58,
        v59,
        (__int64)&v93,
        (__int64)&v88,
        (__int64)&v90,
        (__int64)&v91,
        (__int64)&v89,
        (__int64)&v94);
    }
    goto LABEL_125;
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v88 = *((_DWORD *)this + 169);
    v89 = (const char *)*((_QWORD *)this + 24);
    LODWORD(v92) = v95;
    v90 = "Init UMRDP";
    v94 = (char *)this - 48;
    LODWORD(v91) = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v57,
      (unsigned int)byte_18019787D,
      v58,
      v59,
      (__int64)&v90,
      (__int64)&v92,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v91,
      (__int64)&v94);
  }
  v93 = (char *)this + 104;
  if ( *((_DWORD *)this + 28) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 13), v56, v58);
  LODWORD(v79) = v95;
  v25 = StringCchPrintfW((unsigned __int16 *)this + 346, 0x20u, L"%s#%d", psz, v79);
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v89 = "InitializeInstance";
      v94 = "Failed to create the terminal name";
      LODWORD(v91) = 827;
      v90 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v92 = "Error HResult failed";
      v88 = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v61,
        (unsigned int)&dword_18019782C,
        v62,
        v63,
        (__int64)&v92,
        (__int64)&v88,
        (__int64)&v90,
        (__int64)&v91,
        (__int64)&v89,
        (__int64)&v94);
    }
    v64 = &v93;
LABEL_108:
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v64);
    goto LABEL_125;
  }
  if ( !*((_DWORD *)this + 169) && v97 != *((_QWORD *)this + 24) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 192, v60, v62);
    *((_QWORD *)this + 24) = v97;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 192);
  }
  *((_DWORD *)this + 168) = v95;
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v93);
  if ( v96 )
  {
    v65 = -1;
    do
      ++v65;
    while ( v96[v65] );
    if ( !(unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(
                             (char *)this + 632,
                             v96)
      && (unsigned int)dword_1801B76C8 > 3 )
    {
      v96 = "Allocation failed. The ability to query some stack config will not be available.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v66,
        (unsigned int)&byte_180197807,
        v67,
        v68,
        (__int64)&v96);
    }
  }
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 74) + 24LL))(*((_QWORD *)this + 74), (char *)this + 692);
LABEL_126:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v103);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v98, v69, v70);
  v73 = v99;
  if ( v99 )
  {
    v99 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v101, v71, v72);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v100, v74, v75);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v97, v76, v77);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18004ae90  mov     [rsp-8+arg_10], rbx
0x18004ae95  push    rbp
0x18004ae96  push    rsi
0x18004ae97  push    rdi
0x18004ae98  push    r12
0x18004ae9a  push    r13
0x18004ae9c  push    r14
0x18004ae9e  push    r15
0x18004aea0  lea     rbp, [rsp-50h]
0x18004aea5  sub     rsp, 150h
0x18004aeac  mov     rax, cs:__security_cookie
0x18004aeb3  xor     rax, rsp
0x18004aeb6  mov     [rbp+80h+var_40], rax
0x18004aeba  mov     rax, [rbp+80h+arg_28]
0x18004aec1  xor     r13d, r13d
0x18004aec4  mov     r12, [rbp+80h+arg_48]
0x18004aecb  mov     rdi, r8
0x18004aece  mov     [rsp+180h+var_108], rax
0x18004aed3  mov     r15, rdx
0x18004aed6  mov     rax, [rbp+80h+arg_68]
0x18004aedd  mov     rsi, rcx
0x18004aee0  mov     [rsp+180h+var_118], r8
0x18004aee5  lea     rcx, [rbp+80h+psz]; void *
0x18004aee9  lea     r8d, [r13+40h]; Size
0x18004aeed  mov     [rsp+180h+var_128], r9
0x18004aef2  xor     edx, edx; Val
0x18004aef4  mov     [rbp+80h+var_100], r12
0x18004aef8  mov     r14, r9
0x18004aefb  mov     [rbp+80h+var_F0], rax
0x18004aeff  mov     [rbp+80h+var_E8], r13
0x18004af03  mov     [rbp+80h+var_D0], r13
0x18004af07  mov     [rbp+80h+var_C8], r13
0x18004af0b  mov     [rbp+80h+var_D8], r13
0x18004af0f  mov     [rbp+80h+var_F8], r13d
0x18004af13  call    memset_0
0x18004af18  lea     rcx, [rsi+78h]
0x18004af1c  mov     ebx, r13d
0x18004af1f  mov     [rbp+80h+var_E0], rbx
0x18004af23  mov     [rbp+80h+var_A8], rcx
0x18004af27  cmp     [rcx+8], r13d
0x18004af2b  jz      short loc_18004AF36
0x18004af2d  mov     rcx, [rcx]
0x18004af30  call    cs:__imp_PAL_System_CritSecEnter
0x18004af36  test    r12, r12
0x18004af39  jz      loc_18004BECE
0x18004af3f  test    r15, r15
0x18004af42  jz      loc_18004BECE
0x18004af48  mov     r13, [rbp+80h+arg_30]
0x18004af4f  test    r13, r13
0x18004af52  jz      loc_18004BECE
0x18004af58  test    rdi, rdi
0x18004af5b  jz      loc_18004BECE
0x18004af61  mov     r12, [rbp+80h+arg_58]
0x18004af68  test    r14, r14
0x18004af6b  jnz     short loc_18004AF7F
0x18004af6d  cmp     [rbp+80h+arg_20], rbx
0x18004af74  jnz     short loc_18004AF7F
0x18004af76  test    r12, r12
0x18004af79  jz      loc_18004BECE
0x18004af7f  cmp     [rsp+180h+var_108], rbx
0x18004af84  jz      loc_18004BECE
0x18004af8a  mov     rax, [r15]
0x18004af8d  lea     rdx, [rbp+80h+psz]
0x18004af91  mov     r8d, 20h ; ' '
0x18004af97  mov     rcx, r15
0x18004af9a  mov     rax, [rax+20h]
0x18004af9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afa3  mov     edi, eax
0x18004afa5  test    eax, eax
0x18004afa7  jns     loc_18004B03D
0x18004afad  mov     ecx, cs:dword_1801B76C8
0x18004afb3  mov     r14d, 2
0x18004afb9  cmp     ecx, r14d
0x18004afbc  jbe     loc_18004BF68
0x18004afc2  lea     rax, aFailedToGetThe_6; "Failed to get the listener name"
0x18004afc9  mov     dword ptr [rsp+180h+var_110], 269h
0x18004afd1  mov     [rsp+180h+var_108], rax
0x18004afd6  lea     r15, aInitializeinst; "InitializeInstance"
0x18004afdd  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004afe4  mov     [rsp+180h+var_118], r15
0x18004afe9  mov     [rsp+180h+var_120], rax
0x18004afee  lea     rdx, qword_180197E58
0x18004aff5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004affc  mov     [rsp+180h+var_128], rax
0x18004b001  lea     rax, [rsp+180h+var_108]
0x18004b006  mov     [rsp+180h+var_138], rax
0x18004b00b  lea     rax, [rsp+180h+var_118]
0x18004b010  mov     [rsp+180h+var_140], rax
0x18004b015  lea     rax, [rsp+180h+var_110]
0x18004b01a  mov     [rsp+180h+var_148], rax
0x18004b01f  lea     rax, [rsp+180h+var_120]
0x18004b024  mov     [rsp+180h+var_150], rax
0x18004b029  lea     rax, [rsp+180h+var_130]
0x18004b02e  mov     [rsp+180h+var_158], rax
0x18004b033  lea     rax, [rsp+180h+var_128]
0x18004b038  jmp     loc_18004BF5A
0x18004b03d  lea     rax, [rsi+68h]
0x18004b041  mov     [rsp+180h+var_110], rax
0x18004b046  cmp     [rax+8], ebx
0x18004b049  jz      short loc_18004B054
0x18004b04b  mov     rcx, [rax]
0x18004b04e  call    cs:__imp_PAL_System_CritSecEnter
0x18004b054  mov     eax, [rsi-14h]
0x18004b057  mov     r14d, 2
0x18004b05d  and     al, 6
0x18004b05f  cmp     al, r14b
0x18004b062  jnz     loc_18004BE30
0x18004b068  mov     rax, [rsp+180h+var_118]
0x18004b06d  lea     rdi, [rsi+0D8h]
0x18004b074  cmp     rax, [rdi]
0x18004b077  jz      short loc_18004B091
0x18004b079  mov     rcx, rdi
0x18004b07c  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b081  mov     rax, [rsp+180h+var_118]
0x18004b086  mov     rcx, rdi
0x18004b089  mov     [rdi], rax
0x18004b08c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b091  lea     rdi, [rsi+0F0h]
0x18004b098  cmp     r15, [rdi]
0x18004b09b  jz      short loc_18004B0B0
0x18004b09d  mov     rcx, rdi
0x18004b0a0  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b0a5  mov     rcx, rdi
0x18004b0a8  mov     [rdi], r15
0x18004b0ab  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b0b0  mov     r15, [rsp+180h+var_128]
0x18004b0b5  lea     rdi, [rsi+100h]
0x18004b0bc  cmp     r15, [rdi]
0x18004b0bf  jz      short loc_18004B0D4
0x18004b0c1  mov     rcx, rdi
0x18004b0c4  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b0c9  mov     rcx, rdi
0x18004b0cc  mov     [rdi], r15
0x18004b0cf  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b0d4  mov     rax, [rbp+80h+arg_20]
0x18004b0db  lea     rdi, [rsi+110h]
0x18004b0e2  mov     [rsi+108h], rax
0x18004b0e9  cmp     r12, [rdi]
0x18004b0ec  jz      short loc_18004B101
0x18004b0ee  mov     rcx, rdi
0x18004b0f1  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b0f6  mov     rcx, rdi
0x18004b0f9  mov     [rdi], r12
0x18004b0fc  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b101  lea     rdi, [rsi+248h]
0x18004b108  cmp     r13, [rdi]
0x18004b10b  jz      short loc_18004B120
0x18004b10d  mov     rcx, rdi
0x18004b110  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b115  mov     rcx, rdi
0x18004b118  mov     [rdi], r13
0x18004b11b  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b120  xor     r12d, r12d
0x18004b123  cmp     [rsi+90h], r12
0x18004b12a  jz      short loc_18004B149
0x18004b12c  lea     rcx, [rbp+80h+var_E0]
0x18004b130  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b135  mov     rbx, [rsi+90h]
0x18004b13c  lea     rcx, [rbp+80h+var_E0]
0x18004b140  mov     [rbp+80h+var_E0], rbx
0x18004b144  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b149  mov     r15, [rbp+80h+arg_38]
0x18004b150  lea     rdi, [rsi+0E8h]
0x18004b157  cmp     r15, [rdi]
0x18004b15a  jz      short loc_18004B16F
0x18004b15c  mov     rcx, rdi
0x18004b15f  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b164  mov     rcx, rdi
0x18004b167  mov     [rdi], r15
0x18004b16a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b16f  mov     eax, [rbp+80h+arg_40]
0x18004b175  lea     rdi, [rsi+0B0h]
0x18004b17c  mov     r15, [rbp+80h+arg_50]
0x18004b183  mov     [rsi+29Ch], eax
0x18004b189  cmp     r15, [rdi]
0x18004b18c  jz      short loc_18004B1A1
0x18004b18e  mov     rcx, rdi
0x18004b191  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b196  mov     rcx, rdi
0x18004b199  mov     [rdi], r15
0x18004b19c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b1a1  mov     r15, [rbp+80h+arg_60]
0x18004b1a8  lea     rdi, [rsi+270h]
0x18004b1af  cmp     r15, [rdi]
0x18004b1b2  jz      short loc_18004B1C7
0x18004b1b4  mov     rcx, rdi
0x18004b1b7  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004b1bc  mov     rcx, rdi
0x18004b1bf  mov     [rdi], r15
0x18004b1c2  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18004b1c7  lea     rcx, [rsp+180h+var_110]; this
0x18004b1cc  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18004b1d1  test    rbx, rbx
0x18004b1d4  jnz     loc_18004B277
0x18004b1da  mov     eax, cs:dword_1801B76C8
0x18004b1e0  mov     edi, 80004003h
0x18004b1e5  cmp     eax, r14d
0x18004b1e8  jbe     loc_18004BF6B
0x18004b1ee  lea     rax, aSpcoreconmgrIs; "spCoreConMgr is NULL"
0x18004b1f5  mov     [rsp+180h+var_130], 281h
0x18004b1fd  mov     [rsp+180h+var_128], rax
0x18004b202  lea     r15, aInitializeinst; "InitializeInstance"
0x18004b209  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004b210  mov     [rsp+180h+var_108], rax
0x18004b215  lea     rdx, word_180197DB6
0x18004b21c  lea     rax, aErrorCondition; "Error condition failed"
0x18004b223  mov     [rsp+180h+var_118], rax
0x18004b228  lea     rax, [rsp+180h+var_128]
0x18004b22d  mov     [rsp+180h+var_138], rax
0x18004b232  lea     rax, [rsp+180h+var_120]
0x18004b237  mov     [rsp+180h+var_140], rax
0x18004b23c  lea     rax, [rsp+180h+var_130]
0x18004b241  mov     [rsp+180h+var_148], rax
0x18004b246  lea     rax, [rsp+180h+var_108]
0x18004b24b  mov     [rsp+180h+var_150], rax
0x18004b250  lea     rax, [rsp+180h+var_110]
0x18004b255  mov     [rsp+180h+var_158], rax
0x18004b25a  lea     rax, [rsp+180h+var_118]
0x18004b25f  mov     [rsp+180h+var_120], r15
0x18004b264  mov     dword ptr [rsp+180h+var_110], edi
0x18004b268  mov     [rsp+180h+var_160], rax
0x18004b26d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004b272  jmp     loc_18004BF6B
0x18004b277  lea     r13, [rsi-30h]
0x18004b27b  mov     [rsp+180h+var_158], r12; unsigned int *
0x18004b280  mov     rcx, r13; this
0x18004b283  mov     [rsp+180h+var_160], r12; unsigned int *
0x18004b288  mov     r9d, 1; int
0x18004b28e  lea     r8, aDisablenetwork; "DisableNetworkDetect"
0x18004b295  lea     rdx, aSelectnetworkd; "SelectNetworkDetect"
0x18004b29c  call    ?ReadRegistryGroupPolicy@CUMRDPConnection@@AEAAXPEBG0HPEAK1@Z; CUMRDPConnection::ReadRegistryGroupPolicy(ushort const *,ushort const *,int,ulong *,ulong *)
0x18004b2a1  mov     rcx, [rsi+88h]
0x18004b2a8  lea     rdi, aUserconfigured; "UserConfiguredTransportMode"
0x18004b2af  mov     dword ptr [rsp+180h+var_110], r12d
0x18004b2b4  lea     r8, [rsp+180h+var_110]
0x18004b2b9  mov     rdx, rdi
0x18004b2bc  mov     rax, [rcx]
0x18004b2bf  mov     rax, [rax+28h]
0x18004b2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2c8  lea     r15, aInitializeinst; "InitializeInstance"
0x18004b2cf  test    eax, eax
0x18004b2d1  jns     short loc_18004B314
0x18004b2d3  mov     [rsp+180h+var_158], r12; unsigned int *
0x18004b2d8  lea     rdx, aSelecttranspor; "SelectTransport"
0x18004b2df  mov     r9d, 1; int
0x18004b2e5  mov     [rsp+180h+var_160], r12; unsigned int *
0x18004b2ea  mov     r8, rdi; unsigned __int16 *
0x18004b2ed  mov     rcx, r13; this
0x18004b2f0  call    ?ReadRegistryGroupPolicy@CUMRDPConnection@@AEAAXPEBG0HPEAK1@Z; CUMRDPConnection::ReadRegistryGroupPolicy(ushort const *,ushort const *,int,ulong *,ulong *)
0x18004b2f5  mov     rcx, [rsi+88h]
0x18004b2fc  lea     r8, [rsp+180h+var_110]
0x18004b301  mov     rdx, rdi
0x18004b304  mov     rax, [rcx]
0x18004b307  mov     rax, [rax+28h]
0x18004b30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b310  test    eax, eax
0x18004b312  js      short loc_18004B31B
0x18004b314  cmp     dword ptr [rsp+180h+var_110], r12d
0x18004b319  jnz     short loc_18004B39A
0x18004b31b  mov     rcx, [rsi+88h]
0x18004b322  mov     r8d, r14d
0x18004b325  mov     rdx, rdi
0x18004b328  mov     rax, [rcx]
0x18004b32b  mov     rax, [rax+48h]
0x18004b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b334  test    eax, eax
0x18004b336  jns     short loc_18004B39A
0x18004b338  mov     ecx, cs:dword_1801B76C8
0x18004b33e  cmp     ecx, 3
0x18004b341  jbe     short loc_18004B39A
0x18004b343  mov     [rsp+180h+var_130], eax
0x18004b347  lea     rdi, aHresultFailedB; "HResult failed but continue"
0x18004b34e  lea     rax, aSetpropertyuns_3; "SetPropertyUnsignedLong(CONN_PROPERTY_U"...
0x18004b355  mov     [rsp+180h+var_128], r15
0x18004b35a  mov     [rsp+180h+var_120], rax
0x18004b35f  lea     rdx, byte_180197D77
0x18004b366  lea     rax, [rsp+180h+var_128]
0x18004b36b  mov     [rsp+180h+var_118], rdi
0x18004b370  mov     [rsp+180h+var_148], rax
0x18004b375  lea     rax, [rsp+180h+var_130]
0x18004b37a  mov     [rsp+180h+var_150], rax
0x18004b37f  lea     rax, [rsp+180h+var_120]
0x18004b384  mov     [rsp+180h+var_158], rax
0x18004b389  lea     rax, [rsp+180h+var_118]
0x18004b38e  mov     [rsp+180h+var_160], rax
0x18004b393  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004b398  jmp     short loc_18004B3A1
0x18004b39a  lea     rdi, aHresultFailedB; "HResult failed but continue"
0x18004b3a1  mov     rcx, [rsi+88h]
0x18004b3a8  lea     r8, [rsp+180h+var_110]
0x18004b3ad  mov     dword ptr [rsp+180h+var_110], r12d
0x18004b3b2  lea     rdx, aReverseconnect; "ReverseConnectMode"
0x18004b3b9  mov     rax, [rcx]
0x18004b3bc  mov     rax, [rax+28h]
0x18004b3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b3c5  test    eax, eax
0x18004b3c7  js      short loc_18004B3DA
0x18004b3c9  cmp     dword ptr [rsp+180h+var_110], r12d
0x18004b3ce  mov     eax, r12d
0x18004b3d1  setnz   al
  ... truncated ...
```
