# CUMRDPConnection::Initialize(IUnknown *)

- ea: `0x18004a390`
- end: `0x18004ae84`
- name: `?Initialize@CUMRDPConnection@@UEAAJPEAUIUnknown@@@Z`
- size: `2804`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800235c0`

## callees

- `0x1800015f0`
- `0x180002a74`
- `0x1800071c0`
- `0x180009628`
- `0x18000bef4`
- `0x18000ee00`
- `0x180010908`
- `0x180016d28`
- `0x18001bc38`
- `0x180022488`
- `0x180033da0`
- `0x180034970`
- `0x18004a390`
- `0x180050cd4`
- `0x180055cdc`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004a8a7`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004a8a7`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18004a8d1`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18004a8d1`

## string_xrefs

- `0x18004a653`: `Failed to create the platform context`
- `0x18004a6e8`: `ReplaceCustomRdpScheduler`
- `0x18004a70f`: `ConnectionControl DVC configuration status`
- `0x18004a91d`: `ConnectionControl GP configuration status`
- `0x18004aa39`: `Failed to create Input Channel Factory`
- `0x18004aae4`: `Failed to register input plugin factory`
- `0x18004aba5`: `Failed to create Command Channel Factory`
- `0x18004ac50`: `Failed to register command plugin factory`
- `0x18004ad11`: `Failed to create the basic input plugin factory`
- `0x18004adbc`: `Failed to register basic input plugin factory`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::Initialize(CUMRDPConnection *this, struct IUnknown *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int Instance; // ebx
  struct IRDPENCPlatformContext **v7; // rsi
  int v8; // r9d
  int v9; // ecx
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD *v17; // r15
  int v18; // ecx
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // r14d
  int v24; // ecx
  int v25; // r9d
  unsigned int v26; // ebx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const char *v30; // rax
  char *v31; // rdx
  ULONGLONG v32; // rax
  DWORDLONG v33; // rbx
  unsigned __int16 v34; // r8
  bool v35; // zf
  unsigned int v36; // eax
  int v37; // ecx
  int v38; // r9d
  int v39; // ecx
  int v40; // r9d
  int v41; // ecx
  int v42; // r9d
  int v43; // ecx
  int v44; // r9d
  int v45; // ecx
  int v46; // r9d
  int v47; // ecx
  int v48; // r9d
  int v49; // ecx
  int v50; // r9d
  const char *v52; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v53[2]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v54; // [rsp+60h] [rbp-A0h] BYREF
  const char *v55; // [rsp+68h] [rbp-98h] BYREF
  const char *v56; // [rsp+70h] [rbp-90h] BYREF
  const char *v57; // [rsp+78h] [rbp-88h] BYREF
  void *v58[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+90h] [rbp-70h] BYREF

  v58[0] = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CUMRDPConnection *)((char *)this + 152))
    || !(unsigned int)CTSCriticalSection::Initialize((CUMRDPConnection *)((char *)this + 168)) )
  {
    Instance = -2147024882;
    goto LABEL_68;
  }
  *((_DWORD *)this + 7) |= 2u;
  v7 = (struct IRDPENCPlatformContext **)((char *)this + 184);
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IRDPENCPlatformContext,
               (char *)this + 184);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v53[0] = 283;
      v54 = "Invalid context passed in";
      LODWORD(v55) = Instance;
      v57 = "Initialize";
      v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v52 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)qword_1801983B0,
        v5,
        v8,
        (__int64)&v52,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v54);
    }
    goto LABEL_68;
  }
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, GUID *, char *))(*(_QWORD *)*v7 + 48LL))(
               *v7,
               L"RDP::EventLog::Session",
               &IID_IRdpRCMProtoImplEventLogCallback,
               (char *)this + 640);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v55) = 288;
      v52 = "Failed to get the event log session id";
      v53[0] = Instance;
      v54 = "Initialize";
      v57 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)&byte_18019835F,
        v5,
        v10,
        (__int64)&v56,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v52);
    }
    goto LABEL_68;
  }
  if ( (*(int (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, GUID *, char *))(*(_QWORD *)*v7 + 48LL))(
         *v7,
         L"RDP::EventLog::Session",
         &IID_IRdpUMXEventLogCallback,
         (char *)this + 648) < 0
    && (unsigned int)dword_1801B76C8 > 3 )
  {
    v52 = "The rdpumx event log interface is not present. Events won't be logged.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v11,
      (unsigned int)word_18019833A,
      v12,
      v13,
      (__int64)&v52);
  }
  if ( (int)CTraceAndLogUtil<IRdpStateTransitionEventLogCallbacks>::CreateEventLogSession(
              (char *)this + 848,
              *((_QWORD *)this + 81)) < 0
    && (unsigned int)dword_1801B76C8 > 3 )
  {
    v52 = "WVD event log interface is not present. Events won't be logged.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v14,
      (unsigned int)byte_180198315,
      v15,
      v16,
      (__int64)&v52);
  }
  ReadRegistryFlowControlAndDVCSetting(*v7);
  v17 = (_QWORD *)((char *)this + 192);
  Instance = __RDPAPIDLL__CreateInstance(
               (struct IUnknown *)*v7,
               &CLSID_RDPCoreConnectionMgr,
               &IID_IRDPCoreConnectionMgr,
               (void **)this + 24);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v55) = 314;
      v52 = "Failed to create the platform context";
      v53[0] = Instance;
      v54 = "Initialize";
      v57 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&dword_1801982C4,
        v5,
        v19,
        (__int64)&v56,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v52);
    }
    goto LABEL_68;
  }
  if ( v58[0] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
    v58[0] = 0;
  }
  (*(void (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, _QWORD))(*(_QWORD *)*v7 + 64LL))(
    *v7,
    L"ReplaceCustomRdpScheduler",
    0);
  v23 = 1;
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    LODWORD(v55) = 0;
    v52 = "ConnectionControl DVC configuration status";
    v53[0] = 1;
    LODWORD(v56) = 1;
    LODWORD(v57) = 0;
    LODWORD(v54) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)&word_18019822E,
      v21,
      v22,
      (__int64)&v52,
      (__int64)&v54,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)v53,
      (__int64)&v55);
  }
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, __int64))(*(_QWORD *)*v7 + 64LL))(
               *v7,
               L"RDP::RemoteApp::EnableRAILDVC",
               1);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v54) = 427;
      v52 = "Failed to set enable RAIL DVC property";
      LODWORD(v57) = Instance;
      v56 = "Initialize";
      v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      *(_QWORD *)v53 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_1801981DD,
        v5,
        v25,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v56,
        (__int64)&v52);
    }
    goto LABEL_68;
  }
  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp>::GetImpl'::`2'::impl) )
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    v32 = VerSetConditionMask(0, 4u, 3u);
    VersionInformation.dwBuildNumber = 25292;
    v33 = v32;
    if ( !IsWindowsVersionOrGreater(0xAu, 0, v34)
      || (v35 = !VerifyVersionInfoW(&VersionInformation, 4u, v33), v36 = 1, v35) )
    {
      v36 = 0;
    }
    v53[0] = v36;
    CUMRDPConnection::ReadRegistryGroupPolicy(this, L"UseShellAppRuntimeRemoteApp", 0, 0, v53, v53);
    if ( (unsigned int)dword_1801B76C8 <= 4 )
    {
      v26 = v53[0];
LABEL_37:
      if ( v26 )
        goto LABEL_39;
      goto LABEL_38;
    }
    v26 = v53[0];
    v30 = "ConnectionControl GP configuration status";
    LODWORD(v54) = v53[0];
    v31 = byte_18019819D;
LABEL_30:
    v52 = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (_DWORD)v31,
      v28,
      v29,
      (__int64)&v52,
      (__int64)&v54);
    goto LABEL_37;
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    LODWORD(v54) = 0;
    v30 = "ConnectionControl KIR containment status";
    v31 = byte_18019815D;
    goto LABEL_30;
  }
LABEL_38:
  v23 = 0;
LABEL_39:
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, _QWORD))(*(_QWORD *)*v7 + 64LL))(
               *v7,
               L"RDP::RemoteApp::EnableRAILShellAppRuntime",
               v23);
  if ( Instance >= 0 )
  {
    if ( v58[0] )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
      v58[0] = 0;
    }
    Instance = __RDPAPIDLL__CreateInstance(
                 (struct IUnknown *)*v7,
                 &CLSID_RdpInputChannelFactory,
                 &IID_IRDPCOREChannelPluginFactory,
                 v58);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v17 + 64LL))(*v17, v58[0]);
      if ( Instance >= 0 )
      {
        if ( v58[0] )
        {
          TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
          v58[0] = 0;
        }
        Instance = __RDPAPIDLL__CreateInstance(
                     (struct IUnknown *)*v7,
                     &CLSID_RdpCommandChannelFactory,
                     &IID_IRDPCOREChannelPluginFactory,
                     v58);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v17 + 64LL))(*v17, v58[0]);
          if ( Instance >= 0 )
          {
            if ( v58[0] )
            {
              TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
              v58[0] = 0;
            }
            Instance = __RDPAPIDLL__CreateInstance(
                         (struct IUnknown *)*v7,
                         &CLSID_RDPENCBasicInputPluginFactory,
                         &IID_IRDPCOREChannelPluginFactory,
                         v58);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v17 + 64LL))(*v17, v58[0]);
              if ( Instance >= 0 )
              {
                if ( v58[0] )
                {
                  TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
                  v58[0] = 0;
                }
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                LODWORD(v54) = 502;
                v52 = "Failed to register basic input plugin factory";
                LODWORD(v57) = Instance;
                v56 = "Initialize";
                v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                *(_QWORD *)v53 = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v49,
                  (unsigned int)&word_180197F26,
                  v5,
                  v50,
                  (__int64)v53,
                  (__int64)&v57,
                  (__int64)&v55,
                  (__int64)&v54,
                  (__int64)&v56,
                  (__int64)&v52);
              }
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              LODWORD(v54) = 499;
              v52 = "Failed to create the basic input plugin factory";
              LODWORD(v57) = Instance;
              v56 = "Initialize";
              v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
              *(_QWORD *)v53 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v47,
                (unsigned int)&byte_180197F77,
                v5,
                v48,
                (__int64)v53,
                (__int64)&v57,
                (__int64)&v55,
                (__int64)&v54,
                (__int64)&v56,
                (__int64)&v52);
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v54) = 491;
            v52 = "Failed to register command plugin factory";
            LODWORD(v57) = Instance;
            v56 = "Initialize";
            v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            *(_QWORD *)v53 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v45,
              (unsigned int)qword_180197FC8,
              v5,
              v46,
              (__int64)v53,
              (__int64)&v57,
              (__int64)&v55,
              (__int64)&v54,
              (__int64)&v56,
              (__int64)&v52);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v54) = 488;
          v52 = "Failed to create Command Channel Factory";
          LODWORD(v57) = Instance;
          v56 = "Initialize";
          v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          *(_QWORD *)v53 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v43,
            (unsigned int)byte_180198019,
            v5,
            v44,
            (__int64)v53,
            (__int64)&v57,
            (__int64)&v55,
            (__int64)&v54,
            (__int64)&v56,
            (__int64)&v52);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v54) = 480;
        v52 = "Failed to register input plugin factory";
        LODWORD(v57) = Instance;
        v56 = "Initialize";
        v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        *(_QWORD *)v53 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v41,
          (unsigned int)word_18019806A,
          v5,
          v42,
          (__int64)v53,
          (__int64)&v57,
          (__int64)&v55,
          (__int64)&v54,
          (__int64)&v56,
          (__int64)&v52);
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v54) = 477;
      v52 = "Failed to create Input Channel Factory";
      LODWORD(v57) = Instance;
      v56 = "Initialize";
      v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      *(_QWORD *)v53 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v39,
        (unsigned int)byte_1801980BB,
        v5,
        v40,
        (__int64)v53,
        (__int64)&v57,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v56,
        (__int64)&v52);
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    LODWORD(v54) = 469;
    v52 = "Failed to set enable RAIL ShellAppRuntime property";
    LODWORD(v57) = Instance;
    v56 = "Initialize";
    v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    *(_QWORD *)v53 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v37,
      (unsigned int)&dword_18019810C,
      v5,
      v38,
      (__int64)v53,
      (__int64)&v57,
      (__int64)&v55,
      (__int64)&v54,
      (__int64)&v56,
      (__int64)&v52);
  }
LABEL_68:
  TCntPtr<IRdpSQMLogger>::SafeRelease(v58, v4, v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004a390  mov     [rsp-8+arg_10], rbx
0x18004a395  mov     [rsp-8+arg_18], rsi
0x18004a39a  push    rbp
0x18004a39b  push    rdi
0x18004a39c  push    r12
0x18004a39e  push    r14
0x18004a3a0  push    r15
0x18004a3a2  lea     rbp, [rsp-0C0h]
0x18004a3aa  sub     rsp, 1C0h
0x18004a3b1  mov     rax, cs:__security_cookie
0x18004a3b8  xor     rax, rsp
0x18004a3bb  mov     [rbp+0E0h+var_30], rax
0x18004a3c2  mov     rdi, rcx
0x18004a3c5  xor     r12d, r12d
0x18004a3c8  add     rcx, 98h; this
0x18004a3cf  mov     [rbp+0E0h+var_160], r12
0x18004a3d3  mov     rbx, rdx
0x18004a3d6  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18004a3db  test    eax, eax
0x18004a3dd  jnz     short loc_18004A3E9
0x18004a3df  mov     ebx, 8007000Eh
0x18004a3e4  jmp     loc_18004AE4E
0x18004a3e9  lea     rcx, [rdi+0A8h]; this
0x18004a3f0  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18004a3f5  test    eax, eax
0x18004a3f7  jz      short loc_18004A3DF
0x18004a3f9  or      dword ptr [rdi+1Ch], 2
0x18004a3fd  lea     rsi, [rdi+0B8h]
0x18004a404  mov     rax, [rbx]
0x18004a407  lea     rdx, IID_IRDPENCPlatformContext
0x18004a40e  mov     r8, rsi
0x18004a411  mov     rcx, rbx
0x18004a414  mov     rax, [rax]
0x18004a417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a41c  mov     ebx, eax
0x18004a41e  test    eax, eax
0x18004a420  jns     loc_18004A4BE
0x18004a426  mov     ecx, cs:dword_1801B76C8
0x18004a42c  cmp     ecx, 2
0x18004a42f  jbe     loc_18004AE4E
0x18004a435  lea     rax, aInvalidContext; "Invalid context passed in"
0x18004a43c  mov     [rsp+1E0h+var_188], 11Bh
0x18004a444  mov     [rsp+1E0h+var_180], rax
0x18004a449  lea     rdx, qword_1801983B0
0x18004a450  lea     rax, aInitialize; "Initialize"
0x18004a457  mov     dword ptr [rsp+1E0h+var_178], ebx
0x18004a45b  mov     [rsp+1E0h+var_168], rax
0x18004a460  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004a467  mov     [rsp+1E0h+var_170], rax
0x18004a46c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004a473  mov     [rsp+1E0h+var_190], rax
0x18004a478  lea     rax, [rsp+1E0h+var_180]
0x18004a47d  mov     [rsp+1E0h+var_198], rax
0x18004a482  lea     rax, [rsp+1E0h+var_168]
0x18004a487  mov     [rsp+1E0h+var_1A0], rax
0x18004a48c  lea     rax, [rsp+1E0h+var_188]
0x18004a491  mov     [rsp+1E0h+var_1A8], rax
0x18004a496  lea     rax, [rsp+1E0h+var_170]
0x18004a49b  mov     [rsp+1E0h+var_1B0], rax
0x18004a4a0  lea     rax, [rsp+1E0h+var_178]
0x18004a4a5  mov     [rsp+1E0h+var_1B8], rax
0x18004a4aa  lea     rax, [rsp+1E0h+var_190]
0x18004a4af  mov     [rsp+1E0h+var_1C0], rax
0x18004a4b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004a4b9  jmp     loc_18004AE4E
0x18004a4be  mov     rcx, [rsi]
0x18004a4c1  lea     r9, [rdi+280h]
0x18004a4c8  lea     r8, IID_IRdpRCMProtoImplEventLogCallback
0x18004a4cf  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18004a4d6  mov     rax, [rcx]
0x18004a4d9  mov     rax, [rax+30h]
0x18004a4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4e2  mov     ebx, eax
0x18004a4e4  test    eax, eax
0x18004a4e6  jns     loc_18004A57A
0x18004a4ec  mov     eax, cs:dword_1801B76C8
0x18004a4f2  cmp     eax, 2
0x18004a4f5  jbe     loc_18004AE4E
0x18004a4fb  lea     rax, aFailedToGetThe_1; "Failed to get the event log session id"
0x18004a502  mov     dword ptr [rsp+1E0h+var_178], 120h
0x18004a50a  mov     [rsp+1E0h+var_190], rax
0x18004a50f  lea     rdx, byte_18019835F
0x18004a516  lea     rax, aInitialize; "Initialize"
0x18004a51d  mov     [rsp+1E0h+var_188], ebx
0x18004a521  mov     [rsp+1E0h+var_180], rax
0x18004a526  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004a52d  mov     [rsp+1E0h+var_168], rax
0x18004a532  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004a539  mov     [rsp+1E0h+var_170], rax
0x18004a53e  lea     rax, [rsp+1E0h+var_190]
0x18004a543  mov     [rsp+1E0h+var_198], rax
0x18004a548  lea     rax, [rsp+1E0h+var_180]
0x18004a54d  mov     [rsp+1E0h+var_1A0], rax
0x18004a552  lea     rax, [rsp+1E0h+var_178]
0x18004a557  mov     [rsp+1E0h+var_1A8], rax
0x18004a55c  lea     rax, [rsp+1E0h+var_168]
0x18004a561  mov     [rsp+1E0h+var_1B0], rax
0x18004a566  lea     rax, [rsp+1E0h+var_188]
0x18004a56b  mov     [rsp+1E0h+var_1B8], rax
0x18004a570  lea     rax, [rsp+1E0h+var_170]
0x18004a575  jmp     loc_18004A4AF
0x18004a57a  mov     rcx, [rsi]
0x18004a57d  lea     rbx, [rdi+288h]
0x18004a584  mov     r9, rbx
0x18004a587  lea     r8, IID_IRdpUMXEventLogCallback
0x18004a58e  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18004a595  mov     rax, [rcx]
0x18004a598  mov     rax, [rax+30h]
0x18004a59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5a1  test    eax, eax
0x18004a5a3  jns     short loc_18004A5D2
0x18004a5a5  mov     eax, cs:dword_1801B76C8
0x18004a5ab  cmp     eax, 3
0x18004a5ae  jbe     short loc_18004A5D2
0x18004a5b0  lea     rax, aTheRdpumxEvent; "The rdpumx event log interface is not p"...
0x18004a5b7  mov     [rsp+1E0h+var_190], rax
0x18004a5bc  lea     rdx, word_18019833A
0x18004a5c3  lea     rax, [rsp+1E0h+var_190]
0x18004a5c8  mov     [rsp+1E0h+var_1C0], rax
0x18004a5cd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004a5d2  mov     rdx, [rbx]
0x18004a5d5  lea     rcx, [rdi+350h]
0x18004a5dc  call    ?CreateEventLogSession@?$CTraceAndLogUtil@VIRdpStateTransitionEventLogCallbacks@@@@QEAAJPEAUIUnknown@@AEBU_GUID@@@Z; CTraceAndLogUtil<IRdpStateTransitionEventLogCallbacks>::CreateEventLogSession(IUnknown *,_GUID const &)
0x18004a5e1  test    eax, eax
0x18004a5e3  jns     short loc_18004A612
0x18004a5e5  mov     eax, cs:dword_1801B76C8
0x18004a5eb  cmp     eax, 3
0x18004a5ee  jbe     short loc_18004A612
0x18004a5f0  lea     rax, aWvdEventLogInt; "WVD event log interface is not present."...
0x18004a5f7  mov     [rsp+1E0h+var_190], rax
0x18004a5fc  lea     rdx, byte_180198315
0x18004a603  lea     rax, [rsp+1E0h+var_190]
0x18004a608  mov     [rsp+1E0h+var_1C0], rax
0x18004a60d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004a612  mov     rcx, [rsi]; struct IRDPENCPlatformContext *
0x18004a615  call    ?ReadRegistryFlowControlAndDVCSetting@@YAXPEAUIRDPENCPlatformContext@@@Z; ReadRegistryFlowControlAndDVCSetting(IRDPENCPlatformContext *)
0x18004a61a  mov     rcx, [rsi]; struct IUnknown *
0x18004a61d  lea     r15, [rdi+0C0h]
0x18004a624  mov     r9, r15; void **
0x18004a627  lea     r8, IID_IRDPCoreConnectionMgr; struct _GUID *
0x18004a62e  lea     rdx, CLSID_RDPCoreConnectionMgr; struct _GUID *
0x18004a635  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18004a63a  mov     ebx, eax
0x18004a63c  test    eax, eax
0x18004a63e  jns     loc_18004A6D2
0x18004a644  mov     eax, cs:dword_1801B76C8
0x18004a64a  cmp     eax, 2
0x18004a64d  jbe     loc_18004AE4E
0x18004a653  lea     rax, aFailedToCreate_52; "Failed to create the platform context"
0x18004a65a  mov     dword ptr [rsp+1E0h+var_178], 13Ah
0x18004a662  mov     [rsp+1E0h+var_190], rax
0x18004a667  lea     rdx, dword_1801982C4
0x18004a66e  lea     rax, aInitialize; "Initialize"
0x18004a675  mov     [rsp+1E0h+var_188], ebx
0x18004a679  mov     [rsp+1E0h+var_180], rax
0x18004a67e  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004a685  mov     [rsp+1E0h+var_168], rax
0x18004a68a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004a691  mov     [rsp+1E0h+var_170], rax
0x18004a696  lea     rax, [rsp+1E0h+var_190]
0x18004a69b  mov     [rsp+1E0h+var_198], rax
0x18004a6a0  lea     rax, [rsp+1E0h+var_180]
0x18004a6a5  mov     [rsp+1E0h+var_1A0], rax
0x18004a6aa  lea     rax, [rsp+1E0h+var_178]
0x18004a6af  mov     [rsp+1E0h+var_1A8], rax
0x18004a6b4  lea     rax, [rsp+1E0h+var_168]
0x18004a6b9  mov     [rsp+1E0h+var_1B0], rax
0x18004a6be  lea     rax, [rsp+1E0h+var_188]
0x18004a6c3  mov     [rsp+1E0h+var_1B8], rax
0x18004a6c8  lea     rax, [rsp+1E0h+var_170]
0x18004a6cd  jmp     loc_18004A4AF
0x18004a6d2  cmp     [rbp+0E0h+var_160], r12
0x18004a6d6  jz      short loc_18004A6E5
0x18004a6d8  lea     rcx, [rbp+0E0h+var_160]
0x18004a6dc  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18004a6e1  mov     [rbp+0E0h+var_160], r12
0x18004a6e5  mov     rcx, [rsi]
0x18004a6e8  lea     rdx, aReplacecustomr; "ReplaceCustomRdpScheduler"
0x18004a6ef  xor     r8d, r8d
0x18004a6f2  mov     rax, [rcx]
0x18004a6f5  mov     rax, [rax+40h]
0x18004a6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6fe  mov     eax, cs:dword_1801B76C8
0x18004a704  mov     r14d, 1
0x18004a70a  cmp     eax, 4
0x18004a70d  jbe     short loc_18004A77C
0x18004a70f  lea     rax, aConnectioncont_0; "ConnectionControl DVC configuration sta"...
0x18004a716  mov     dword ptr [rsp+1E0h+var_178], r12d
0x18004a71b  mov     [rsp+1E0h+var_190], rax
0x18004a720  lea     rdx, word_18019822E
0x18004a727  lea     rax, [rsp+1E0h+var_178]
0x18004a72c  mov     [rsp+1E0h+var_188], r14d
0x18004a731  mov     [rsp+1E0h+var_198], rax
0x18004a736  lea     rax, [rsp+1E0h+var_188]
0x18004a73b  mov     [rsp+1E0h+var_1A0], rax
0x18004a740  lea     rax, [rsp+1E0h+var_170]
0x18004a745  mov     [rsp+1E0h+var_1A8], rax
0x18004a74a  lea     rax, [rsp+1E0h+var_168]
0x18004a74f  mov     [rsp+1E0h+var_1B0], rax
0x18004a754  lea     rax, [rsp+1E0h+var_180]
0x18004a759  mov     [rsp+1E0h+var_1B8], rax
0x18004a75e  lea     rax, [rsp+1E0h+var_190]
0x18004a763  mov     [rsp+1E0h+var_1C0], rax
0x18004a768  mov     dword ptr [rsp+1E0h+var_170], r14d
0x18004a76d  mov     dword ptr [rsp+1E0h+var_168], r12d
0x18004a772  mov     dword ptr [rsp+1E0h+var_180], r12d
0x18004a777  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004a77c  mov     rcx, [rsi]
0x18004a77f  lea     rdx, aRdpRemoteappEn; "RDP::RemoteApp::EnableRAILDVC"
0x18004a786  mov     r8d, r14d
0x18004a789  mov     rax, [rcx]
0x18004a78c  mov     rax, [rax+40h]
0x18004a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a795  mov     ebx, eax
0x18004a797  test    eax, eax
0x18004a799  jns     loc_18004A82D
0x18004a79f  mov     eax, cs:dword_1801B76C8
0x18004a7a5  cmp     eax, 2
0x18004a7a8  jbe     loc_18004AE4E
0x18004a7ae  lea     rax, aFailedToSetEna_0; "Failed to set enable RAIL DVC property"
0x18004a7b5  mov     dword ptr [rsp+1E0h+var_180], 1ABh
0x18004a7bd  mov     [rsp+1E0h+var_190], rax
0x18004a7c2  lea     rdx, byte_1801981DD
0x18004a7c9  lea     rax, aInitialize; "Initialize"
0x18004a7d0  mov     dword ptr [rsp+1E0h+var_168], ebx
0x18004a7d4  mov     [rsp+1E0h+var_170], rax
0x18004a7d9  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004a7e0  mov     [rsp+1E0h+var_178], rax
0x18004a7e5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004a7ec  mov     qword ptr [rsp+1E0h+var_188], rax
0x18004a7f1  lea     rax, [rsp+1E0h+var_190]
0x18004a7f6  mov     [rsp+1E0h+var_198], rax
0x18004a7fb  lea     rax, [rsp+1E0h+var_170]
0x18004a800  mov     [rsp+1E0h+var_1A0], rax
0x18004a805  lea     rax, [rsp+1E0h+var_180]
0x18004a80a  mov     [rsp+1E0h+var_1A8], rax
0x18004a80f  lea     rax, [rsp+1E0h+var_178]
0x18004a814  mov     [rsp+1E0h+var_1B0], rax
0x18004a819  lea     rax, [rsp+1E0h+var_168]
0x18004a81e  mov     [rsp+1E0h+var_1B8], rax
0x18004a823  lea     rax, [rsp+1E0h+var_188]
0x18004a828  jmp     loc_18004A4AF
0x18004a82d  mov     ebx, r12d
0x18004a830  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp>::GetImpl(void)'::`2'::impl
0x18004a837  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OneDriveRemoteApp>::__private_IsEnabled(void)
0x18004a83c  test    al, al
0x18004a83e  jnz     short loc_18004A885
0x18004a840  mov     eax, cs:dword_1801B76C8
0x18004a846  cmp     eax, 4
0x18004a849  jbe     loc_18004A93C
0x18004a84f  mov     dword ptr [rsp+1E0h+var_180], r12d
0x18004a854  lea     rax, aConnectioncont; "ConnectionControl KIR containment statu"...
0x18004a85b  lea     rdx, byte_18019815D
0x18004a862  mov     [rsp+1E0h+var_190], rax
0x18004a867  lea     rax, [rsp+1E0h+var_180]
0x18004a86c  mov     [rsp+1E0h+var_1B8], rax
0x18004a871  lea     rax, [rsp+1E0h+var_190]
0x18004a876  mov     [rsp+1E0h+var_1C0], rax
0x18004a87b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004a880  jmp     loc_18004A938
0x18004a885  xor     edx, edx; Val
0x18004a887  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18004a88e  mov     r8d, 118h; Size
0x18004a894  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x18004a898  call    memset_0
0x18004a89d  mov     r8b, 3; Condition
0x18004a8a0  mov     edx, 4; TypeMask
0x18004a8a5  xor     ecx, ecx; ConditionMask
0x18004a8a7  call    cs:__imp_VerSetConditionMask
0x18004a8ad  xor     edx, edx; unsigned __int16
0x18004a8af  mov     [rbp+0E0h+VersionInformation.dwBuildNumber], 62CCh
0x18004a8b6  mov     rbx, rax
0x18004a8b9  lea     ecx, [rdx+0Ah]; unsigned __int16
0x18004a8bc  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18004a8c1  test    al, al
0x18004a8c3  jz      short loc_18004A8DE
0x18004a8c5  mov     r8, rbx; dwlConditionMask
0x18004a8c8  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x18004a8cc  mov     edx, 4; dwTypeMask
0x18004a8d1  call    cs:__imp_VerifyVersionInfoW
0x18004a8d7  test    eax, eax
0x18004a8d9  mov     eax, r14d
0x18004a8dc  jnz     short loc_18004A8E1
0x18004a8de  mov     eax, r12d
0x18004a8e1  mov     [rsp+1E0h+var_188], eax
0x18004a8e5  lea     rdx, aUseshellapprun; "UseShellAppRuntimeRemoteApp"
0x18004a8ec  lea     rax, [rsp+1E0h+var_188]
0x18004a8f1  xor     r9d, r9d; int
0x18004a8f4  mov     [rsp+1E0h+var_1B8], rax; unsigned int *
0x18004a8f9  xor     r8d, r8d; unsigned __int16 *
0x18004a8fc  lea     rax, [rsp+1E0h+var_188]
0x18004a901  mov     rcx, rdi; this
0x18004a904  mov     [rsp+1E0h+var_1C0], rax; unsigned int *
0x18004a909  call    ?ReadRegistryGroupPolicy@CUMRDPConnection@@AEAAXPEBG0HPEAK1@Z; CUMRDPConnection::ReadRegistryGroupPolicy(ushort const *,ushort const *,int,ulong *,ulong *)
0x18004a90e  mov     eax, cs:dword_1801B76C8
0x18004a914  cmp     eax, 4
0x18004a917  jbe     short loc_18004A934
0x18004a919  mov     ebx, [rsp+1E0h+var_188]
0x18004a91d  lea     rax, aConnectioncont_1; "ConnectionControl GP configuration stat"...
0x18004a924  mov     dword ptr [rsp+1E0h+var_180], ebx
  ... truncated ...
```
