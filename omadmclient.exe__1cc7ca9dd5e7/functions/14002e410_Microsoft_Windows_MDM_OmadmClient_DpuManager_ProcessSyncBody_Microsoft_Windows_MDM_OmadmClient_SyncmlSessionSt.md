# Microsoft::Windows::MDM::OmadmClient::DpuManager::ProcessSyncBody(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort *,PushRouterSubmitOrigin)

- ea: `0x14002e410`
- end: `0x14002f3b7`
- name: `?ProcessSyncBody@DpuManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEAGW4PushRouterSubmitOrigin@@@Z`
- size: `4007`
- prototype: `int __high(struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, unsigned __int16 *, enum PushRouterSubmitOrigin)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x1400057fc`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x140014894`
- `0x140015660`
- `0x14001a628`
- `0x14002b2d4`
- `0x14002e410`
- `0x14002fca0`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eeb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eeb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f0d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ed65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ed65`
- `coredpus!__imp_FreeSyncMLResultsData` at `0x14002eaba`
- `coredpus!__imp_FreeSyncMLResultsData` at `0x14002ec81`
- `coredpus!__imp_FreeSyncMLResultsData` at `0x14002eaba`
- `coredpus!__imp_FreeSyncMLResultsData` at `0x14002ec81`
- `DMCmnUtils!CopyString` at `0x14002ed82`
- `DMCmnUtils!CopyString` at `0x14002ed82`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::DpuManager::ProcessSyncBody(
        ULONGLONG a1,
        __int64 a2,
        unsigned __int16 *a3,
        int a4)
{
  __int64 v7; // r8
  _QWORD *v8; // r14
  Microsoft::Windows::MDM::OmadmClient::DpuManager *v9; // rcx
  signed int HasDataFromPreviousMessage; // ebx
  __int64 v11; // rcx
  int SyncBody; // eax
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // ebx
  Microsoft::Windows::MDM::OmadmClient *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  bool v23; // zf
  _QWORD *v24; // r14
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  char v37; // al
  int v38; // ebx
  struct COmaDmLogger *Logger; // rax
  __int64 v40; // r8
  struct COmaDmLogger *v41; // rax
  __int64 v42; // r8
  int v43; // eax
  __int64 v44; // rcx
  HLOCAL *v45; // rbx
  int v46; // eax
  const unsigned __int16 *v47; // rdx
  __int64 v48; // rcx
  Microsoft::Windows::MDM::OmadmClient *v49; // rcx
  int v50; // eax
  ULONGLONG v51; // rbx
  __int64 v52; // rax
  signed int LastError; // eax
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  ULONGLONG v57; // rcx
  __int64 v58; // rbx
  __int64 (__fastcall *Ptr)(__int64, _QWORD, _QWORD); // r9
  int v60; // eax
  unsigned int v61; // edx
  int v62; // eax
  signed int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v67; // rcx
  __int64 v68; // r8
  struct COmaDmLogger *v69; // rax
  struct _EVENT_DATA_DESCRIPTOR *v70; // rax
  ULONG v71; // r9d
  __int64 *v72; // rdx
  __int64 v73; // rcx
  int v74[2]; // [rsp+20h] [rbp-138h]
  unsigned int v75; // [rsp+34h] [rbp-124h] BYREF
  int v76; // [rsp+38h] [rbp-120h] BYREF
  int v77; // [rsp+40h] [rbp-118h] BYREF
  ULONGLONG v78; // [rsp+48h] [rbp-110h]
  unsigned int *v79; // [rsp+50h] [rbp-108h]
  _QWORD *v80; // [rsp+58h] [rbp-100h]
  ULONGLONG v81; // [rsp+60h] [rbp-F8h]
  _QWORD v82[3]; // [rsp+68h] [rbp-F0h] BYREF
  int v83; // [rsp+80h] [rbp-D8h]
  unsigned int *v84; // [rsp+88h] [rbp-D0h]
  unsigned __int16 *v85; // [rsp+90h] [rbp-C8h]
  _QWORD *v86; // [rsp+98h] [rbp-C0h]
  ULONGLONG v87; // [rsp+A0h] [rbp-B8h]
  __int128 v88; // [rsp+A8h] [rbp-B0h] BYREF
  __int128 v89; // [rsp+B8h] [rbp-A0h]
  __int128 v90; // [rsp+C8h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v91; // [rsp+D8h] [rbp-80h] BYREF
  int *v92; // [rsp+E8h] [rbp-70h]
  __int64 v93; // [rsp+F0h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v94; // [rsp+F8h] [rbp-60h] BYREF
  int *v95; // [rsp+108h] [rbp-50h]
  __int64 v96; // [rsp+110h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v85 = a3;
  v81 = a1;
  v87 = a1;
  v86 = (_QWORD *)a2;
  v94.Ptr = (ULONGLONG)a3;
  v75 = 0;
  v82[0] = 0;
  v82[1] = "ProcessSyncBody";
  v82[2] = COmaDmLogger::GetLogger();
  v83 = 2;
  v84 = &v75;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v77 = 27;
    v92 = &v77;
    v93 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v7,
      2u,
      &v91);
  }
  v8 = (_QWORD *)(a1 + 216);
  v80 = v8;
  v74[0] = a4;
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)*v8 + 8LL))(*v8, 2, 1800, 1);
  v78 = v81;
  v91.Ptr = v81;
  v79 = &v75;
  *(_QWORD *)&v91.Size = &v75;
  LOBYTE(v92) = 1;
  if ( !v85 )
  {
    HasDataFromPreviousMessage = -805306128;
    v75 = -805306128;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v8 + 16LL))(*v8, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v11, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  SyncBody = Microsoft::Windows::MDM::OmadmClient::DpuManager::ExtractSyncBody(v9, v85);
  HasDataFromPreviousMessage = SyncBody;
  v75 = SyncBody;
  if ( SyncBody < 0 )
  {
    LODWORD(v82[0]) = 21019;
    HIDWORD(v82[0]) = SyncBody;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v8 + 16LL))(*v8, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v13, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  v76 = 0;
  HasDataFromPreviousMessage = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::HasDataFromPreviousMessage(
                                 (Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *)(a2 + 1496),
                                 &v76);
  v75 = HasDataFromPreviousMessage;
  if ( HasDataFromPreviousMessage == -2147024894 )
  {
    HasDataFromPreviousMessage = 0;
    v75 = 0;
  }
  if ( HasDataFromPreviousMessage < 0 )
  {
    LODWORD(v82[0]) = 21044;
    HIDWORD(v82[0]) = HasDataFromPreviousMessage;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v8 + 16LL))(*v8, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v16, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  v17 = v76;
  if ( v76 && (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FoundRemainingLargeMessageResponse,
      v15,
      1u,
      &v94);
  *(_QWORD *)(a2 + 1072) = v85;
  *(_DWORD *)(a2 + 1084) = *(_DWORD *)(a2 + 1592);
  v18 = *(Microsoft::Windows::MDM::OmadmClient **)(a2 + 520);
  *(_QWORD *)(a2 + 1096) = v18;
  *(_DWORD *)(a2 + 1104) = 0;
  if ( (unsigned int)Microsoft::Windows::MDM::OmadmClient::ShouldShowOrginalError(v18, v14) )
    *(_DWORD *)(a2 + 1116) |= 1u;
  *(_DWORD *)(a2 + 1480) = *(_DWORD *)(a2 + 1080);
  if ( !*(_DWORD *)(a2 + 1484) )
  {
    v23 = *(_DWORD *)(a2 + 1912) == 1;
    *(_DWORD *)(a2 + 1088) = v23;
    if ( v23 )
    {
      *(_DWORD *)(a2 + 1108) = -2102722558;
      *(_DWORD *)(a2 + 1112) = 0;
      goto LABEL_37;
    }
    if ( !v17 )
    {
      *(_QWORD *)(a2 + 1108) = 0;
      goto LABEL_37;
    }
LABEL_34:
    *(_DWORD *)(a2 + 1088) = 1;
    *(_DWORD *)(a2 + 1108) = -2102722546;
    goto LABEL_36;
  }
  if ( *(_QWORD *)(a2 + 1448) )
  {
    if ( v17 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20, v19, v21, v22, *(_QWORD *)v74);
    *(_DWORD *)(a2 + 1088) = 1;
    *(_DWORD *)(a2 + 1108) = -2102722547;
    goto LABEL_36;
  }
  v23 = *(_DWORD *)(a2 + 1912) == 1;
  *(_DWORD *)(a2 + 1088) = v23;
  if ( !v23 )
  {
    if ( !v17 )
    {
      *(_DWORD *)(a2 + 1108) = 0;
      goto LABEL_36;
    }
    goto LABEL_34;
  }
  *(_DWORD *)(a2 + 1108) = -2102722558;
LABEL_36:
  *(_DWORD *)(a2 + 1112) = 1;
LABEL_37:
  v24 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( v24 )
  {
    *v24 = &Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::`vftable';
    v24[1] = 0;
    *((_DWORD *)v24 + 4) = 0;
  }
  else
  {
    v24 = 0;
  }
  v86 = v24;
  if ( !v24 )
  {
    HasDataFromPreviousMessage = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
      (const char *)0x8007000ELL,
      v74[0]);
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v80 + 16LL))(*v80, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v25, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  v26 = Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::Initialize(
          (Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24,
          (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2,
          0);
  HasDataFromPreviousMessage = v26;
  v75 = v26;
  if ( v26 < 0 )
  {
    LODWORD(v82[0]) = 9083;
    HIDWORD(v82[0]) = v26;
    Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
    operator delete(v24);
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v80 + 16LL))(*v80, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v27, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v24 + 32LL))(v24, a2 + 1072);
  HasDataFromPreviousMessage = v28;
  v75 = v28;
  if ( v28 < 0 )
  {
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
    {
      v77 = v28;
      v92 = &v77;
      v93 = 4;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)FailedSyncBodyParsingEvent,
        v31,
        2u,
        &v91);
      HasDataFromPreviousMessage = v75;
    }
    LODWORD(v82[0]) = 21093;
    HIDWORD(v82[0]) = HasDataFromPreviousMessage;
    Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
    operator delete(v24);
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v80 + 16LL))(*v80, 2);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v32, OmaDmClientFunctionReturnValueEvent, 27, v75);
    goto LABEL_128;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)SuccessfulSyncBodyParsingEvent,
      v31,
      1u,
      &v94);
    HasDataFromPreviousMessage = v75;
  }
  v33 = 0;
  v77 = 0;
  if ( *(_DWORD *)(a2 + 1484) && *(_DWORD *)(a2 + 1460) == 1 || v76 )
  {
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(*v24 + 40LL))(v24, &v88);
    HasDataFromPreviousMessage = v34;
    v75 = v34;
    if ( v34 < 0 )
    {
      LODWORD(v82[0]) = 21035;
      HIDWORD(v82[0]) = v34;
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v80 + 16LL))(*v80, 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v35, OmaDmClientFunctionReturnValueEvent, 27, v75);
      goto LABEL_128;
    }
    if ( HIDWORD(v89) )
    {
      FreeSyncMLResultsData(&v88);
      v82[0] = 0x82AB00000000520BuLL;
      HasDataFromPreviousMessage = -2102722560;
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v80 + 16LL))(*v80, 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v36, OmaDmClientFunctionReturnValueEvent, 27, v75);
      goto LABEL_128;
    }
    v37 = BYTE12(v90);
    if ( (BYTE12(v90) & 4) != 0 )
    {
      v77 = 1;
      *(_DWORD *)(a2 + 1088) = 1;
      *(_DWORD *)(a2 + 1468) = 1;
      if ( v76 )
      {
        v76 = 30012;
        v38 = -2102722546;
      }
      else
      {
        v38 = -2102722547;
        v76 = 30011;
      }
      Logger = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(Logger, 1, (unsigned int)v76, 0);
      *(_DWORD *)(a2 + 1108) = v38;
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
      {
        v76 = v38;
        v95 = &v76;
        v96 = 4;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)ServerSentUnexpectedAdditionalCommmands,
          v40,
          2u,
          &v94);
      }
      v37 = BYTE12(v90);
    }
    if ( *(int *)(a2 + 1108) >= 0 && ((v37 & 1) != 0 || (v37 & 2) == 0) )
    {
      v77 = 1;
      *(_DWORD *)(a2 + 1468) = 1;
      *(_DWORD *)(a2 + 1088) = 1;
      *(_DWORD *)(a2 + 1108) = -2102788095;
      v41 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v41, 1, 30013, 0);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
      {
        v76 = HIDWORD(v90);
        v95 = &v76;
        v96 = 4;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)ServerSentUnexpectedAdditionalXmlContents,
          v42,
          2u,
          &v94);
      }
    }
    FreeSyncMLResultsData(&v88);
    *(_DWORD *)(a2 + 1112) = 0;
    v43 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v24 + 32LL))(v24, a2 + 1072);
    HasDataFromPreviousMessage = v43;
    v75 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v82[0]) = 21094;
      HIDWORD(v82[0]) = v43;
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v44, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    }
    v33 = v77;
  }
  if ( !*(_DWORD *)(a2 + 1484) || v33 )
    goto LABEL_126;
  if ( *(_DWORD *)(a2 + 1460) == 2 )
    *(_DWORD *)(a2 + 1460) = 0;
  if ( !*(_QWORD *)(a2 + 1448) )
  {
    v45 = (HLOCAL *)(a2 + 1472);
    if ( *(_QWORD *)(a2 + 1472) )
    {
      LocalFree(*v45);
      *v45 = 0;
    }
    v46 = CopyString(v85, 0xFFFFFFFF, (unsigned __int16 **)(a2 + 1472));
    HasDataFromPreviousMessage = v46;
    v75 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
        (const char *)(unsigned int)v46,
        v74[0]);
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v48, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    }
    *(_DWORD *)(a2 + 1132) = *(_DWORD *)(a2 + 1592);
    *(_QWORD *)(a2 + 1120) = *(_QWORD *)(a2 + 1472);
    v49 = *(Microsoft::Windows::MDM::OmadmClient **)(a2 + 520);
    *(_QWORD *)(a2 + 1144) = v49;
    *(_DWORD *)(a2 + 1152) = 0;
    if ( (unsigned int)Microsoft::Windows::MDM::OmadmClient::ShouldShowOrginalError(v49, v47) )
      *(_DWORD *)(a2 + 1164) |= 1u;
    v23 = *(_DWORD *)(a2 + 1912) == 1;
    *(_DWORD *)(a2 + 1136) = v23;
    v50 = -2102722558;
    if ( !v23 )
      v50 = 0;
    *(_DWORD *)(a2 + 1156) = v50;
    *(_DWORD *)(a2 + 1160) = 0;
    v51 = v81;
    v52 = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), ULONGLONG, _QWORD))(**(_QWORD **)(v81 + 160) + 48LL))(
            *(_QWORD *)(v81 + 160),
            Microsoft::Windows::MDM::OmadmClient::DpuManager::DpuInvokerCallback,
            v81,
            0);
    *(_QWORD *)(a2 + 1448) = v52;
    if ( !v52 )
    {
      LastError = GetLastError();
      HasDataFromPreviousMessage = LastError;
      if ( LastError > 0 )
        HasDataFromPreviousMessage = (unsigned __int16)LastError | 0x80070000;
      v75 = HasDataFromPreviousMessage;
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v54, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    }
    v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v51 + 160) + 32LL))(
            *(_QWORD *)(v51 + 160),
            *(_QWORD *)(a2 + 1440));
    HasDataFromPreviousMessage = v55;
    v75 = v55;
    if ( v55 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
        (const char *)(unsigned int)v55,
        v74[0]);
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v56, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    }
    v57 = v81;
    *(_QWORD *)(v81 + 144) = a2;
    *(_DWORD *)(a2 + 1464) = *(_DWORD *)(a2 + 1588);
    *(_DWORD *)(a2 + 1460) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v57 + 160) + 56LL))(
      *(_QWORD *)(v57 + 160),
      *(_QWORD *)(a2 + 1448));
  }
  v58 = *(_QWORD *)(v81 + 160);
  Ptr = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v58 + 40LL);
  v94.Ptr = (ULONGLONG)Ptr;
  v60 = *(_DWORD *)(a2 + 772);
  if ( !v60 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v30, v29, v31, Ptr, *(_QWORD *)v74);
    Ptr = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD))v94.Ptr;
LABEL_113:
    v61 = 60000;
    goto LABEL_115;
  }
  if ( (unsigned int)(7 * v60) < 0x927C0 )
    goto LABEL_113;
  v61 = 7 * v60 / 0xAu;
LABEL_115:
  v62 = Ptr(v58, *(_QWORD *)(a2 + 1440), v61);
  switch ( v62 )
  {
    case 0:
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v81 + 160) + 64LL))(
        *(_QWORD *)(v81 + 160),
        *(_QWORD *)(a2 + 1448));
      *(_QWORD *)(a2 + 1448) = 0;
      *(_DWORD *)(a2 + 1480) = *(_DWORD *)(a2 + 1128);
      *(_DWORD *)(a2 + 1460) = 2;
      if ( *(int *)(a2 + 1456) >= 0 )
      {
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) == 0 )
          goto LABEL_139;
        v70 = &v94;
        v71 = 1;
        v72 = SuccessfulSyncBodyParsingEvent;
      }
      else
      {
        v69 = COmaDmLogger::GetLogger();
        Microsoft::Windows::TelemetryLogger::LogMeasure(v69, 1, 21095, 0);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) == 0 )
          goto LABEL_139;
        v77 = *(_DWORD *)(a2 + 1456);
        v92 = &v77;
        v93 = 4;
        v70 = &v91;
        v71 = 2;
        v72 = FailedSyncBodyParsingEvent;
      }
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)v72,
        v68,
        v71,
        v70);
LABEL_139:
      HasDataFromPreviousMessage = *(_DWORD *)(a2 + 1456);
      v75 = HasDataFromPreviousMessage;
      if ( HasDataFromPreviousMessage < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x278,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\dpumanager.cpp",
          (const char *)(unsigned int)HasDataFromPreviousMessage,
          v74[0]);
        Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
        operator delete(v24);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          McTemplateU0qq_EventWriteTransfer(v73, OmaDmClientFunctionReturnValueEvent, 27, *v79);
        goto LABEL_128;
      }
LABEL_126:
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v65, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    case 128:
      v82[0] = 0x8000FFFF0000526BuLL;
      HasDataFromPreviousMessage = -2147418113;
      Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
      operator delete(v24);
LABEL_130:
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
        McTemplateU0qq_EventWriteTransfer(v67, OmaDmClientFunctionReturnValueEvent, 27, *v79);
      goto LABEL_128;
    case 258:
      HasDataFromPreviousMessage = v75;
      goto LABEL_126;
  }
  if ( v62 != -1 )
  {
    v82[0] = 0x8000FFFF0000526DuLL;
    HasDataFromPreviousMessage = -2147418113;
    Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
    operator delete(v24);
    goto LABEL_130;
  }
  v63 = GetLastError();
  HasDataFromPreviousMessage = v63;
  if ( v63 > 0 )
    HasDataFromPreviousMessage = (unsigned __int16)v63 | 0x80070000;
  LODWORD(v82[0]) = 21100;
  HIDWORD(v82[0]) = HasDataFromPreviousMessage;
  Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper((Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper *)v24);
  operator delete(v24);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v78 + 216) + 16LL))(*(_QWORD *)(v78 + 216), 2);
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(v64, OmaDmClientFunctionReturnValueEvent, 27, *v79);
LABEL_128:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v82);
  return (unsigned int)HasDataFromPreviousMessage;
}

```

## disassembly

```asm
0x14002e410  push    rbx
0x14002e412  push    rsi
0x14002e413  push    rdi
0x14002e414  push    r12
0x14002e416  push    r13
0x14002e418  push    r14
0x14002e41a  push    r15
0x14002e41c  sub     rsp, 120h
0x14002e423  mov     rax, cs:__security_cookie
0x14002e42a  xor     rax, rsp
0x14002e42d  mov     [rsp+158h+var_40], rax
0x14002e435  mov     ebx, r9d
0x14002e438  mov     rax, r8
0x14002e43b  mov     [rsp+158h+var_C8], rax
0x14002e443  mov     rsi, rdx
0x14002e446  mov     r14, rcx
0x14002e449  mov     [rsp+158h+var_F8], rcx
0x14002e44e  mov     [rsp+158h+var_B8], rcx
0x14002e456  mov     [rsp+158h+var_C0], rdx
0x14002e45e  mov     qword ptr [rsp+158h+var_60], rax
0x14002e466  xor     edi, edi
0x14002e468  mov     [rsp+158h+var_124], edi
0x14002e46c  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14002e471  mov     [rsp+158h+var_F0], rdi
0x14002e476  lea     rcx, aProcesssyncbod; "ProcessSyncBody"
0x14002e47d  mov     [rsp+158h+var_E8], rcx
0x14002e482  mov     [rsp+158h+var_E0], rax
0x14002e487  lea     r15d, [rdi+2]
0x14002e48b  mov     [rsp+158h+var_D8], r15d
0x14002e493  lea     rax, [rsp+158h+var_124]
0x14002e498  mov     [rsp+158h+var_D0], rax
0x14002e4a0  lea     r13d, [rdi+1Bh]
0x14002e4a4  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e4ab  jz      short loc_14002E4EE
0x14002e4ad  mov     [rsp+158h+var_118], r13d
0x14002e4b2  lea     rax, [rsp+158h+var_118]
0x14002e4b7  mov     [rsp+158h+var_70], rax
0x14002e4bf  mov     [rsp+158h+var_68], 4
0x14002e4cb  lea     rax, [rsp+158h+var_80]
0x14002e4d3  mov     qword ptr [rsp+158h+var_138], rax
0x14002e4d8  mov     r9d, r15d
0x14002e4db  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14002e4e2  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002e4e9  call    McGenEventWrite_EventWriteTransfer
0x14002e4ee  add     r14, 0D8h
0x14002e4f5  mov     [rsp+158h+var_100], r14
0x14002e4fa  mov     rcx, [r14]
0x14002e4fd  mov     rax, [rcx]
0x14002e500  mov     [rsp+158h+var_138], ebx
0x14002e504  mov     r12d, 1
0x14002e50a  mov     r9d, r12d
0x14002e50d  mov     r8d, 708h
0x14002e513  mov     edx, r15d
0x14002e516  mov     rax, [rax+8]
0x14002e51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e51f  mov     rax, [rsp+158h+var_F8]
0x14002e524  mov     [rsp+158h+var_110], rax
0x14002e529  mov     qword ptr [rsp+158h+var_80], rax
0x14002e531  lea     rax, [rsp+158h+var_124]
0x14002e536  mov     [rsp+158h+var_108], rax
0x14002e53b  mov     [rsp+158h+var_78], rax
0x14002e543  mov     al, r12b
0x14002e546  mov     [rsp+158h+var_128], al
0x14002e54a  mov     byte ptr [rsp+158h+var_70], al
0x14002e551  mov     rax, [rsp+158h+var_C8]
0x14002e559  test    rax, rax
0x14002e55c  jnz     short loc_14002E59C
0x14002e55e  mov     ebx, 0D00000F0h
0x14002e563  mov     [rsp+158h+var_124], ebx
0x14002e567  mov     rcx, [r14]
0x14002e56a  mov     rax, [rcx]
0x14002e56d  mov     edx, r15d
0x14002e570  mov     rax, [rax+10h]
0x14002e574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e579  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e580  jz      short loc_14002E597
0x14002e582  mov     r9d, [rsp+158h+var_124]
0x14002e587  mov     r8d, r13d
0x14002e58a  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14002e591  call    McTemplateU0qq_EventWriteTransfer
0x14002e596  nop
0x14002e597  jmp     loc_14002F1BA
0x14002e59c  mov     rdx, rax; unsigned __int16 *
0x14002e59f  call    ?ExtractSyncBody@DpuManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJPEAG@Z; Microsoft::Windows::MDM::OmadmClient::DpuManager::ExtractSyncBody(ushort *)
0x14002e5a4  mov     ebx, eax
0x14002e5a6  mov     [rsp+158h+var_124], eax
0x14002e5aa  test    eax, eax
0x14002e5ac  jns     short loc_14002E5EF
0x14002e5ae  mov     dword ptr [rsp+158h+var_F0], 521Bh
0x14002e5b6  mov     dword ptr [rsp+158h+var_F0+4], eax
0x14002e5ba  mov     rcx, [r14]
0x14002e5bd  mov     rax, [rcx]
0x14002e5c0  mov     edx, r15d
0x14002e5c3  mov     rax, [rax+10h]
0x14002e5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e5cc  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e5d3  jz      short loc_14002E5EA
0x14002e5d5  mov     r9d, [rsp+158h+var_124]
0x14002e5da  mov     r8d, r13d
0x14002e5dd  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14002e5e4  call    McTemplateU0qq_EventWriteTransfer
0x14002e5e9  nop
0x14002e5ea  jmp     loc_14002F1BA
0x14002e5ef  mov     [rsp+158h+var_120], edi
0x14002e5f3  lea     rcx, [rsi+5D8h]; this
0x14002e5fa  lea     rdx, [rsp+158h+var_120]; int *
0x14002e5ff  call    ?HasDataFromPreviousMessage@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@QEAAJPEAH@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::HasDataFromPreviousMessage(int *)
0x14002e604  mov     ebx, eax
0x14002e606  mov     [rsp+158h+var_124], eax
0x14002e60a  cmp     eax, 80070002h
0x14002e60f  jnz     short loc_14002E617
0x14002e611  mov     ebx, edi
0x14002e613  mov     [rsp+158h+var_124], ebx
0x14002e617  jmp     short loc_14002E67A
0x14002e619  xor     edi, edi
0x14002e61b  lea     r15d, [rdi+2]
0x14002e61f  lea     r13d, [rdi+1Bh]
0x14002e623  lea     r12d, [rdi+1]
0x14002e627  mov     ebx, [rsp+158h+var_124]
0x14002e62b  mov     al, byte ptr [rsp+158h+var_70]
0x14002e632  mov     [rsp+158h+var_128], al
0x14002e636  mov     rax, [rsp+158h+var_78]
0x14002e63e  mov     [rsp+158h+var_108], rax
0x14002e643  mov     rax, qword ptr [rsp+158h+var_80]
0x14002e64b  mov     [rsp+158h+var_110], rax
0x14002e650  mov     rax, [rsp+158h+var_B8]
0x14002e658  mov     [rsp+158h+var_F8], rax
0x14002e65d  mov     rsi, [rsp+158h+var_C0]
0x14002e665  mov     rax, qword ptr [rsp+158h+var_60]
0x14002e66d  mov     [rsp+158h+var_C8], rax
0x14002e675  mov     r14, [rsp+158h+var_100]
0x14002e67a  test    ebx, ebx
0x14002e67c  jns     short loc_14002E6BF
0x14002e67e  mov     dword ptr [rsp+158h+var_F0], 5234h
0x14002e686  mov     dword ptr [rsp+158h+var_F0+4], ebx
0x14002e68a  mov     rcx, [r14]
0x14002e68d  mov     rax, [rcx]
0x14002e690  mov     edx, r15d
0x14002e693  mov     rax, [rax+10h]
0x14002e697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e69c  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e6a3  jz      short loc_14002E6BA
0x14002e6a5  mov     r9d, [rsp+158h+var_124]
0x14002e6aa  mov     r8d, r13d
0x14002e6ad  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14002e6b4  call    McTemplateU0qq_EventWriteTransfer
0x14002e6b9  nop
0x14002e6ba  jmp     loc_14002F1BA
0x14002e6bf  mov     ebx, [rsp+158h+var_120]
0x14002e6c3  test    ebx, ebx
0x14002e6c5  jz      short loc_14002E6F3
0x14002e6c7  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r12b
0x14002e6ce  jz      short loc_14002E6F3
0x14002e6d0  lea     rax, [rsp+158h+var_60]
0x14002e6d8  mov     qword ptr [rsp+158h+var_138], rax; int
0x14002e6dd  mov     r9d, r12d
0x14002e6e0  lea     rdx, FoundRemainingLargeMessageResponse
0x14002e6e7  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002e6ee  call    McGenEventWrite_EventWriteTransfer
0x14002e6f3  mov     rax, [rsp+158h+var_C8]
0x14002e6fb  mov     [rsi+430h], rax
0x14002e702  mov     eax, [rsi+638h]
0x14002e708  mov     [rsi+43Ch], eax
0x14002e70e  mov     rcx, [rsi+208h]; this
0x14002e715  mov     [rsi+448h], rcx
0x14002e71c  mov     [rsi+450h], edi
0x14002e722  call    ?ShouldShowOrginalError@OmadmClient@MDM@Windows@Microsoft@@YAHPEBG@Z; Microsoft::Windows::MDM::OmadmClient::ShouldShowOrginalError(ushort const *)
0x14002e727  test    eax, eax
0x14002e729  jz      short loc_14002E732
0x14002e72b  or      [rsi+45Ch], r12d
0x14002e732  mov     eax, [rsi+438h]
0x14002e738  mov     [rsi+5C8h], eax
0x14002e73e  cmp     [rsi+5CCh], edi
0x14002e744  jnz     short loc_14002E77D
0x14002e746  mov     eax, edi
0x14002e748  cmp     [rsi+778h], r12d
0x14002e74f  setz    al
0x14002e752  mov     [rsi+440h], eax
0x14002e758  jnz     short loc_14002E76C
0x14002e75a  mov     dword ptr [rsi+454h], 82AB0002h
0x14002e764  mov     [rsi+458h], edi
0x14002e76a  jmp     short loc_14002E7E6
0x14002e76c  test    ebx, ebx
0x14002e76e  jnz     short loc_14002E7C6
0x14002e770  mov     qword ptr [rsi+454h], 0
0x14002e77b  jmp     short loc_14002E7E6
0x14002e77d  cmp     [rsi+5A8h], rdi
0x14002e784  jz      short loc_14002E7A2
0x14002e786  test    ebx, ebx
0x14002e788  jz      short loc_14002E78F
0x14002e78a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!fDoDrainLargeResponse")
0x14002e78f  mov     [rsi+440h], r12d
0x14002e796  mov     dword ptr [rsi+454h], 82AB000Dh
0x14002e7a0  jmp     short loc_14002E7DF
0x14002e7a2  mov     eax, edi
0x14002e7a4  cmp     [rsi+778h], r12d
0x14002e7ab  setz    al
0x14002e7ae  mov     [rsi+440h], eax
0x14002e7b4  jnz     short loc_14002E7C2
0x14002e7b6  mov     dword ptr [rsi+454h], 82AB0002h
0x14002e7c0  jmp     short loc_14002E7DF
0x14002e7c2  test    ebx, ebx
0x14002e7c4  jz      short loc_14002E7D9
0x14002e7c6  mov     [rsi+440h], r12d
0x14002e7cd  mov     dword ptr [rsi+454h], 82AB000Eh
0x14002e7d7  jmp     short loc_14002E7DF
0x14002e7d9  mov     [rsi+454h], edi
0x14002e7df  mov     [rsi+458h], r12d
0x14002e7e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e7ed  mov     ecx, 18h; unsigned __int64
0x14002e7f2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002e7f7  mov     r14, rax
0x14002e7fa  test    rax, rax
0x14002e7fd  jz      short loc_14002E813
0x14002e7ff  lea     rax, ??_7CSyncMLDPUContainerWrapper@OmadmClient@MDM@Windows@Microsoft@@6B@; const Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::`vftable'
0x14002e806  mov     [r14], rax
0x14002e809  mov     [r14+8], rdi
0x14002e80d  mov     [r14+10h], edi
0x14002e811  jmp     short loc_14002E816
0x14002e813  mov     r14, rdi
0x14002e816  mov     [rsp+158h+var_C0], r14
0x14002e81e  test    r14, r14
0x14002e821  jnz     short loc_14002E87F
0x14002e823  mov     rcx, [rsp+158h]; this
0x14002e82b  mov     ebx, 8007000Eh
0x14002e830  mov     r9d, ebx; char *
0x14002e833  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14002e83a  mov     edx, 1C2h; void *
0x14002e83f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e844  nop
0x14002e845  mov     rcx, [rsp+158h+var_100]
0x14002e84a  mov     rcx, [rcx]
0x14002e84d  mov     rax, [rcx]
0x14002e850  mov     edx, r15d
0x14002e853  mov     rax, [rax+10h]
0x14002e857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e85c  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e863  jz      short loc_14002E87A
0x14002e865  mov     r9d, [rsp+158h+var_124]
0x14002e86a  mov     r8d, r13d
0x14002e86d  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14002e874  call    McTemplateU0qq_EventWriteTransfer
0x14002e879  nop
0x14002e87a  jmp     loc_14002F1BA
0x14002e87f  xor     r8d, r8d; bool
0x14002e882  mov     rdx, rsi; struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *
0x14002e885  mov     rcx, r14; this
0x14002e888  call    ?Initialize@CSyncMLDPUContainerWrapper@OmadmClient@MDM@Windows@Microsoft@@QEAAJAEAVSyncmlSessionState@2345@_N@Z; Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::Initialize(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,bool)
0x14002e88d  mov     ebx, eax
0x14002e88f  mov     [rsp+158h+var_124], eax
0x14002e893  test    eax, eax
0x14002e895  jns     short loc_14002E8F3
0x14002e897  mov     dword ptr [rsp+158h+var_F0], 237Bh
0x14002e89f  mov     dword ptr [rsp+158h+var_F0+4], eax
0x14002e8a3  mov     rcx, r14; this
0x14002e8a6  call    ??1CSyncMLDPUContainerWrapper@OmadmClient@MDM@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper(void)
0x14002e8ab  mov     edx, 18h
0x14002e8b0  mov     rcx, r14; Block
0x14002e8b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002e8b8  nop
0x14002e8b9  mov     rcx, [rsp+158h+var_100]
0x14002e8be  mov     rcx, [rcx]
0x14002e8c1  mov     rax, [rcx]
0x14002e8c4  mov     edx, r15d
0x14002e8c7  mov     rax, [rax+10h]
0x14002e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e8d0  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002e8d7  jz      short loc_14002E8EE
0x14002e8d9  mov     r9d, [rsp+158h+var_124]
0x14002e8de  mov     r8d, r13d
0x14002e8e1  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14002e8e8  call    McTemplateU0qq_EventWriteTransfer
0x14002e8ed  nop
0x14002e8ee  jmp     loc_14002F1BA
0x14002e8f3  mov     rax, [r14]
0x14002e8f6  lea     rdx, [rsi+430h]
0x14002e8fd  mov     rcx, r14
0x14002e900  mov     rax, [rax+20h]
0x14002e904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e909  mov     ebx, eax
0x14002e90b  mov     [rsp+158h+var_124], eax
0x14002e90f  test    eax, eax
0x14002e911  jns     loc_14002E9C0
0x14002e917  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r15b
0x14002e91e  jz      short loc_14002E964
0x14002e920  mov     [rsp+158h+var_118], eax
0x14002e924  lea     rax, [rsp+158h+var_118]
0x14002e929  mov     [rsp+158h+var_70], rax
0x14002e931  mov     [rsp+158h+var_68], 4
0x14002e93d  lea     rax, [rsp+158h+var_80]
0x14002e945  mov     qword ptr [rsp+158h+var_138], rax
0x14002e94a  mov     r9d, r15d
0x14002e94d  lea     rdx, FailedSyncBodyParsingEvent
0x14002e954  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002e95b  call    McGenEventWrite_EventWriteTransfer
0x14002e960  mov     ebx, [rsp+158h+var_124]
0x14002e964  mov     dword ptr [rsp+158h+var_F0], 5265h
0x14002e96c  mov     dword ptr [rsp+158h+var_F0+4], ebx
0x14002e970  mov     rcx, r14; this
0x14002e973  call    ??1CSyncMLDPUContainerWrapper@OmadmClient@MDM@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::MDM::OmadmClient::CSyncMLDPUContainerWrapper::~CSyncMLDPUContainerWrapper(void)
  ... truncated ...
```
