# _Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()

- ea: `0x180157214`
- end: `0x1801581d9`
- name: `_Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()`
- size: `4037`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801581e0`

## callees

- `0x180002a28`
- `0x180002b90`
- `0x180003fe0`
- `0x180006a78`
- `0x180006b10`
- `0x180024558`
- `0x180031664`
- `0x180031730`
- `0x180049bec`
- `0x18004b6ac`
- `0x18004f698`
- `0x180052240`
- `0x180064e8c`
- `0x18008035c`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008abf4`
- `0x18009b164`
- `0x18009b658`
- `0x18009c8c0`
- `0x1800ab56c`
- `0x1800adbd8`
- `0x1800b47f0`
- `0x1800d754c`
- `0x1800de928`
- `0x1800fc72c`
- `0x180107fc4`
- `0x180121810`
- `0x180142fcc`
- `0x180144f54`
- `0x180157214`
- `0x180159cb4`
- `0x1801813e4`
- `0x1801a9494`
- `0x1801b7bd0`
- `0x1801bcde8`
- `0x1801deac8`
- `0x1801dec58`
- `0x1801e23a8`
- `0x1801e37f4`
- `0x1801f1404`
- `0x1801f8e14`
- `0x1801fd640`
- `0x1802051fc`
- `0x18020aac0`
- `0x18020ba94`
- `0x18024b904`
- `0x18027fabc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180157302`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180157302`

## string_xrefs

- `0x18015736f`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x18015742a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801578fb`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x18015796e`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801579f0`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157a56`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157ab9`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157bf0`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157c3a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157cc3`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157e0a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157efc`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157ff1`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180158055`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801580f4`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180158141`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801581c7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180157f7e`: `AgentId`
- `0x180157f27`: `AgentConnectionEstablished_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()(
        struct Microsoft::Diagnostics::ITriggerInst *a1)
{
  struct Microsoft::Diagnostics::ITriggerInst *v1; // r14
  __int64 v2; // rbx
  std::_Ref_count_base *v3; // rsi
  Microsoft::Diagnostics::AgentManager *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v8; // rdx
  unsigned int v9; // r8d
  int JsonBuilderFromBufferOrString; // eax
  unsigned int v11; // ebx
  Microsoft::Diagnostics::AsimovEventSerializer *AsimovEventSerializer; // rax
  struct Microsoft::Diagnostics::ETWTriggerInst *v13; // rcx
  const void *v14; // rax
  const char *v15; // r9
  struct Microsoft::Diagnostics::TriggerListener *TriggerListener; // rax
  __int64 *Consumer; // rax
  __int64 v18; // r8
  __int64 v19; // r12
  std::_Ref_count_base *v20; // r15
  __int64 v21; // rbx
  _QWORD *FullyQualifiedName; // rax
  __int64 v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  __int64 v30; // r15
  __int64 v31; // rdx
  __int64 v32; // rbx
  int v33; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  _OWORD *v37; // rdx
  Microsoft::Diagnostics::TraceManager *TraceManager; // rax
  __int64 v39; // rcx
  int v40; // eax
  int v41; // ebx
  struct Microsoft::Diagnostics::TenantManager *TenantManager; // rbx
  int v43; // eax
  int v44; // eax
  struct Microsoft::Diagnostics::TenantManager *v45; // rbx
  int v46; // eax
  int v47; // eax
  int v48; // ebx
  Microsoft::Diagnostics::AgentManager *v49; // rbx
  __int64 v50; // rcx
  __int64 *v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r15
  Microsoft::Diagnostics::AgentManager *v54; // rbx
  __int64 v55; // r15
  Microsoft::Diagnostics::AgentManager *v56; // rbx
  __int64 v57; // rcx
  _OWORD *v58; // rdx
  char *v59; // rcx
  __int64 v60; // rax
  int v61; // r8d
  int v62; // r9d
  __int64 v63; // rcx
  __int64 v64; // rdx
  int v65; // r8d
  int v66; // r9d
  __int64 v67; // rcx
  Microsoft::Diagnostics::AgentManager *v68; // rcx
  int v69; // eax
  int v70; // eax
  __int64 v71; // rdx
  char v72; // al
  Microsoft::Diagnostics::AgentManager *v73; // rcx
  int v74; // r12d
  __int64 v75; // rdx
  Microsoft::Diagnostics::AgentManager *v76; // rcx
  int v77; // r8d
  int v78; // r9d
  int active; // eax
  struct Microsoft::Diagnostics::DTraceManager *DTraceManager; // rax
  Microsoft::Diagnostics::AgentManager *v81; // rcx
  int v82; // eax
  unsigned int v83; // [rsp+20h] [rbp-6F8h]
  char v84; // [rsp+40h] [rbp-6D8h] BYREF
  char v85[15]; // [rsp+41h] [rbp-6D7h] BYREF
  struct Microsoft::Diagnostics::ITriggerInst *v86; // [rsp+50h] [rbp-6C8h] BYREF
  std::_Ref_count_base *v87; // [rsp+58h] [rbp-6C0h]
  std::_Ref_count_base *v88[2]; // [rsp+60h] [rbp-6B8h] BYREF
  struct Microsoft::Diagnostics::ETWTriggerInst *v89[2]; // [rsp+70h] [rbp-6A8h] BYREF
  __int128 v90; // [rsp+80h] [rbp-698h] BYREF
  _QWORD v91[2]; // [rsp+90h] [rbp-688h] BYREF
  void *lpMem[2]; // [rsp+A0h] [rbp-678h] BYREF
  __int128 v93; // [rsp+B0h] [rbp-668h]
  __int128 v94; // [rsp+C0h] [rbp-658h]
  _OWORD v95[4]; // [rsp+D0h] [rbp-648h] BYREF
  __int64 v96; // [rsp+110h] [rbp-608h]
  char v97; // [rsp+120h] [rbp-5F8h] BYREF
  wchar_t v98[135]; // [rsp+122h] [rbp-5F6h] BYREF
  int v99[282]; // [rsp+230h] [rbp-4E8h] BYREF
  int v100; // [rsp+698h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+0h]

  v1 = a1;
  v86 = a1;
  *(_OWORD *)v88 = 0;
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v90, *(_QWORD *)a1 + 128LL);
  v91[0] = *(_QWORD *)(**((_QWORD **)v1 + 1) + 8LL);
  v2 = *(_QWORD *)v1;
  std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned long,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned long>>,0>>::find(
    *(_QWORD *)v1 + 208LL,
    v89,
    v91);
  if ( v89[0] == *(struct Microsoft::Diagnostics::ETWTriggerInst **)(v2 + 208) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x80070490LL,
      v83);
  std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(v88, (char *)v89[0] + 40);
  v3 = v88[0];
  if ( *((_BYTE *)v88[0] + 249) )
  {
    std::wstring::operator std::wstring_view((char *)v88[0] + 264, v91);
    if ( v91[1] )
    {
      if ( *((_BYTE *)v3 + 329) )
        Microsoft::Diagnostics::AgentManager::LogIdleAgentEvent(v4, v3, 0);
    }
  }
  *((_QWORD *)v3 + 42) = GetTickCount64();
  *((_BYTE *)v3 + 329) = 0;
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v90);
  if ( !**((_BYTE **)v1 + 2) )
  {
    v57 = **((_QWORD **)v1 + 1);
    v58 = *(_OWORD **)(v57 + 24);
    if ( *(_DWORD *)(v57 + 32) - (_DWORD)v58 != 258 )
      goto LABEL_102;
    v59 = &v97;
    v60 = 2;
    do
    {
      *(_OWORD *)v59 = *v58;
      *((_OWORD *)v59 + 1) = v58[1];
      *((_OWORD *)v59 + 2) = v58[2];
      *((_OWORD *)v59 + 3) = v58[3];
      *((_OWORD *)v59 + 4) = v58[4];
      *((_OWORD *)v59 + 5) = v58[5];
      *((_OWORD *)v59 + 6) = v58[6];
      *((_OWORD *)v59 + 7) = v58[7];
      v59 += 128;
      v58 += 8;
      --v60;
    }
    while ( v60 );
    *(_WORD *)v59 = *(_WORD *)v58;
    if ( (unsigned __int8)v97 < 7u )
    {
      if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x8000) )
      {
        v85[0] = 7;
        v84 = 9;
        LOBYTE(v89[0]) = v97;
        v63 = **((_QWORD **)v1 + 1);
        v86 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v63 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
          v63,
          (unsigned int)&dword_1803EB1FC,
          v61,
          v62,
          (__int64)&v86,
          (__int64)v89,
          (__int64)&v84,
          (__int64)v85);
      }
      v41 = -2147024809;
      v64 = 870;
      goto LABEL_112;
    }
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x8000) )
    {
      LOBYTE(v89[0]) = v97;
      v84 = 9;
      v67 = **((_QWORD **)v1 + 1);
      v86 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v67 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v67,
        (unsigned int)byte_1803EB26D,
        v65,
        v66,
        (__int64)&v86,
        (__int64)&v84,
        (__int64)v89);
    }
    v89[0] = 0;
    v41 = StringCchLengthW(v98, 0x80u, (unsigned __int64 *)v89);
    if ( v41 < 0 )
    {
      v64 = 883;
LABEL_112:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v41,
        v83);
      goto LABEL_113;
    }
    std::wstring::_Assign<wchar_t>((char *)v3 + 264, v98, v89[0]);
    v69 = Microsoft::Diagnostics::AgentManager::SetAgentContainerTelemetryId(v68, v3);
    if ( v69 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v69,
        v83);
    *((_BYTE *)v3 + 348) = v97;
    *((_BYTE *)v3 + 249) = 1;
    v86 = (struct Microsoft::Diagnostics::ITriggerInst *)L"AgentConnectionEstablished_0";
    v87 = (std::_Ref_count_base *)28;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v99,
      (unsigned int)&v86,
      0x1000000,
      0,
      0,
      0,
      0);
    std::wstring::operator std::wstring_view((char *)v3 + 264, &v90);
    v86 = (struct Microsoft::Diagnostics::ITriggerInst *)L"AgentId";
    v87 = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v99, (int)&v100);
    v90 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v89, &v90);
    v70 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v99);
    if ( v70 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v70,
        v83);
    v72 = v97;
    if ( (unsigned __int8)v97 > 9u )
      v72 = 9;
    LOBYTE(v91[0]) = v72;
    v86 = (struct Microsoft::Diagnostics::ITriggerInst *)1;
    v87 = (std::_Ref_count_base *)v91;
    LOBYTE(v71) = 1;
    v74 = Microsoft::Diagnostics::AgentTransport::SendAgentMessage(v3, v71, &v86);
    if ( v74 < 0 )
    {
      v75 = 906;
LABEL_129:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v75,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v74,
        v83);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v99);
      if ( v88[1] )
        std::_Ref_count_base::_Decref(v88[1]);
      return (unsigned int)v74;
    }
    if ( (unsigned __int16)(qword_18046330A - 3) > 1u )
    {
      v74 = Microsoft::Diagnostics::AgentManager::SendAuthorizationInfoToAgent(v73, v3);
      if ( v74 < 0 )
      {
        v75 = 910;
        goto LABEL_129;
      }
      v74 = Microsoft::Diagnostics::AgentManager::SendTriggerSettingsToAgent(v76, v3);
      if ( v74 < 0 )
      {
        v75 = 912;
        goto LABEL_129;
      }
      LOWORD(v89[0]) = 0;
      LOBYTE(v78) = 1;
      LOBYTE(v77) = 9;
      active = Microsoft::Diagnostics::AgentManager::SendActiveTracesToAgents(*(_QWORD *)v1, (_DWORD)v3, v77, v78, 0);
      if ( active < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x391,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)active,
          v83);
      DTraceManager = Microsoft::Diagnostics::LifetimeManager::GetDTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::DTraceManager::CreateAgentMessage(DTraceManager, lpMem);
      v82 = Microsoft::Diagnostics::AgentManager::SendUpdatedDTraceRequestsToAgent(
              v81,
              v3,
              (const struct JsonBuilder *)lpMem);
      if ( v82 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x394,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v82,
          v83);
      JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v99);
    goto LABEL_143;
  }
  if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 4 )
  {
    v5 = *((_QWORD *)v1 + 1);
    v6 = *(_QWORD *)(*(_QWORD *)v5 + 24LL);
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v5 + 32LL) - v6) <= 0x48 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)0x8007000DLL,
        v83);
      if ( v88[1] )
        std::_Ref_count_base::_Decref(v88[1]);
      return 2147942413LL;
    }
    v95[0] = *(_OWORD *)v6;
    v95[1] = *(_OWORD *)(v6 + 16);
    v95[2] = *(_OWORD *)(v6 + 32);
    v95[3] = *(_OWORD *)(v6 + 48);
    v96 = *(_QWORD *)(v6 + 64);
    v8 = *(_QWORD *)(*(_QWORD *)v5 + 24LL);
    v9 = *(_DWORD *)(*(_QWORD *)v5 + 32LL) - v8 - 72;
    lpMem[0] = 0;
    lpMem[1] = 0;
    LOBYTE(v93) = 0;
    JsonBuilderFromBufferOrString = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
                                      *((_BYTE *)v3 + 250),
                                      (const void *)(v8 + 72),
                                      v9,
                                      (struct JsonBuilder *)lpMem);
    v11 = JsonBuilderFromBufferOrString;
    if ( JsonBuilderFromBufferOrString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A4,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)JsonBuilderFromBufferOrString,
        v83);
      JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
      if ( v88[1] )
        std::_Ref_count_base::_Decref(v88[1]);
      return v11;
    }
    if ( (unsigned __int16)(qword_18046330A - 3) > 1u )
    {
      Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(v89, (__int64)v95, lpMem, (__int64)v3, 0);
      if ( *((_BYTE *)v3 + 251) )
      {
        v14 = (const void *)(*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::ETWTriggerInst *))(*(_QWORD *)v89[0] + 80LL))(v89[0]);
        if ( memcmp_0(v14, &GUID_NULL, 0x10u) )
          Microsoft::Diagnostics::TraceLoggingDynamicRelogger::RelogEvent(
            (Microsoft::Diagnostics::TraceLoggingDynamicRelogger *)(*(_QWORD *)v1 + 744LL),
            v89[0]);
      }
      if ( !*((_BYTE *)v3 + 349) )
      {
        try
        {
          *((_BYTE *)v3 + 349) = (Microsoft::Diagnostics::IAsimovEvent::NeedsCommonSchemaTranslation(v89[0], 0) ^ 1) + 1;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x3C5,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            v15);
          v3 = v88[0];
          v1 = v86;
        }
      }
      if ( byte_180462A28 )
      {
        TriggerListener = Microsoft::Diagnostics::LifetimeManager::GetTriggerListener((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        LOWORD(v91[0]) = 1;
        Consumer = (__int64 *)Microsoft::Diagnostics::TriggerListener::GetConsumer(TriggerListener, &v86, 1);
        v19 = *Consumer;
        *(_QWORD *)&v90 = *Consumer;
        v20 = (std::_Ref_count_base *)Consumer[1];
        *((_QWORD *)&v90 + 1) = v20;
        *Consumer = 0;
        Consumer[1] = 0;
        if ( v87 )
          std::_Ref_count_base::_Decref(v87);
        LOBYTE(v18) = *((_BYTE *)v3 + 349) == 1;
        Microsoft::Diagnostics::ETWConsumer::AgentEventCallback(v19, v89, v18);
        if ( v20 )
          std::_Ref_count_base::_Decref(v20);
      }
      else if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 17) )
      {
        v21 = *(_QWORD *)(Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(v89[0], &v90) + 8);
        FullyQualifiedName = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(v89[0], &v86);
        v23 = _tlgWrapBinary<wchar_t,2>(v91, *FullyQualifiedName, (unsigned int)v21);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
          v24,
          (unsigned int)byte_1803EB165,
          v25,
          v26,
          v23);
      }
      v13 = v89[1];
    }
    else
    {
      Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(&v86, (__int64)v95, lpMem, (__int64)v3, 1);
      *((_QWORD *)v86 + 37) = 0x4059000000000000LL;
      AsimovEventSerializer = Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistTrigger(AsimovEventSerializer, v86, 0);
      v13 = v87;
    }
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    goto LABEL_34;
  }
  if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 5 )
  {
    if ( *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - (unsigned int)*(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL) == 4 )
    {
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 32784) )
      {
        LODWORD(v91[0]) = v27;
        v29 = **((_QWORD **)v1 + 1);
        v86 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v29 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)byte_1803EB1A5,
          v27,
          v28,
          (__int64)&v86,
          (__int64)v91);
      }
      **((_BYTE **)v1 + 3) = 1;
      goto LABEL_143;
    }
LABEL_102:
    if ( v88[1] )
      std::_Ref_count_base::_Decref(v88[1]);
    return 13;
  }
  if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 8 )
  {
    v30 = *((_QWORD *)v1 + 1);
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v30 + 32LL) - *(_DWORD *)(*(_QWORD *)v30 + 24LL)) < 0x18 )
    {
      v31 = 1004;
LABEL_95:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)0x8007000DLL,
        v83);
      if ( v88[1] )
        std::_Ref_count_base::_Decref(v88[1]);
      return 2147942413LL;
    }
    v32 = *(_QWORD *)v1;
    v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
    v33 = Microsoft::Diagnostics::IAgentIoReceiver::ProcessEscalationDataMessage(v32, &v90, v30);
    v34 = retaddr;
    if ( v33 < 0 )
    {
      v35 = 1005;
LABEL_90:
      wil::details::in1diag3::_Log_Hr(
        v34,
        (void *)v35,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v33,
        v83);
      goto LABEL_143;
    }
    goto LABEL_143;
  }
  if ( !*((_BYTE *)v3 + 249) || **((_BYTE **)v1 + 2) != 10 )
  {
    if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 11 )
    {
      v39 = (unsigned int)(*(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_DWORD *)(**((_QWORD **)v1 + 1) + 24LL));
      if ( (_DWORD)v39 != 16 )
        goto LABEL_102;
      Microsoft::Diagnostics::AgentManager::FulfillScenarioObjectRequest(v39, v88);
      v3 = v88[0];
      goto LABEL_143;
    }
    if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 12 )
      goto LABEL_143;
    if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 15 )
    {
      lpMem[0] = 0;
      lpMem[1] = 0;
      LOBYTE(v93) = 0;
      v40 = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
              *((_BYTE *)v3 + 250),
              *(const void **)(**((_QWORD **)v1 + 1) + 24LL),
              *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL),
              (struct JsonBuilder *)lpMem);
      v41 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v40,
          v83);
LABEL_63:
        JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
        goto LABEL_113;
      }
      TenantManager = Microsoft::Diagnostics::LifetimeManager::GetTenantManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
      v43 = Microsoft::Diagnostics::TenantManager::RegisterTenant(TenantManager, &v90, lpMem);
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x408,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v43,
          v83);
    }
    else
    {
      if ( !*((_BYTE *)v3 + 249) || **((_BYTE **)v1 + 2) != 16 )
      {
        if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 13 )
        {
          v47 = Microsoft::Diagnostics::AgentManager::SnapHostTrace(
                  *(Microsoft::Diagnostics::AgentManager **)v1,
                  v3,
                  **((struct Microsoft::Diagnostics::IoRequest ***)v1 + 1));
          v48 = v47;
          if ( v47 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x416,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)(unsigned int)v47,
              v83);
          LOBYTE(v91[0]) = 13;
          HIDWORD(v91[0]) = v48;
          v49 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
          v33 = Microsoft::Diagnostics::AgentManager::SendApiCompletionMessage(v49, &v90, v91);
          v34 = retaddr;
          if ( v33 >= 0 )
            goto LABEL_143;
          v35 = 1050;
          goto LABEL_90;
        }
        if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 18 )
        {
          v50 = **((_QWORD **)v1 + 1);
          v51 = *(__int64 **)(v50 + 24);
          if ( (unsigned int)(*(_DWORD *)(v50 + 32) - (_DWORD)v51) < 0x20 )
          {
            v31 = 1054;
            goto LABEL_95;
          }
          v52 = *v51;
          *((_BYTE *)v3 + 250) = *v51 & 1;
          *((_BYTE *)v3 + 251) = (v52 & 2) != 0;
          goto LABEL_143;
        }
        if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 19 )
        {
          v53 = *((_QWORD *)v1 + 1);
          if ( *(_DWORD *)(*(_QWORD *)v53 + 32LL) - *(_DWORD *)(*(_QWORD *)v53 + 24LL) != 100 )
            goto LABEL_102;
          v54 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
          v33 = Microsoft::Diagnostics::AgentWatsonCrashManager::RegisterWatsonCrashRequest(
                  (char *)v54 + 808,
                  &v90,
                  v53);
          v34 = retaddr;
          if ( v33 < 0 )
          {
            v35 = 1062;
            goto LABEL_90;
          }
          goto LABEL_143;
        }
        if ( *((_BYTE *)v3 + 249) && **((_BYTE **)v1 + 2) == 20 )
        {
          v55 = *((_QWORD *)v1 + 1);
          if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v55 + 32LL) - *(_DWORD *)(*(_QWORD *)v55 + 24LL)) < 0x64 )
          {
            v31 = 1067;
            goto LABEL_95;
          }
          v56 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
          v33 = Microsoft::Diagnostics::AgentWatsonCrashManager::ProcessWatsonCrash((char *)v56 + 808, &v90, v55);
          v34 = retaddr;
          if ( v33 < 0 )
          {
            v35 = 1068;
            goto LABEL_90;
          }
          goto LABEL_143;
        }
        v41 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x431,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
                (const char *)0xD,
                v83);
LABEL_113:
        if ( v88[1] )
          std::_Ref_count_base::_Decref(v88[1]);
        return (unsigned int)v41;
      }
      lpMem[0] = 0;
      lpMem[1] = 0;
      LOBYTE(v93) = 0;
      v44 = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
              *((_BYTE *)v3 + 250),
              *(const void **)(**((_QWORD **)v1 + 1) + 24LL),
              *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL),
              (struct JsonBuilder *)lpMem);
      v41 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v44,
          v83);
        goto LABEL_63;
      }
      v45 = Microsoft::Diagnostics::LifetimeManager::GetTenantManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v90 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v3, &v86);
      v46 = Microsoft::Diagnostics::TenantManager::UnregisterTenant(v45, &v90, lpMem);
      if ( v46 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x411,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v46,
          v83);
    }
LABEL_34:
    JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
    goto LABEL_143;
  }
  v36 = **((_QWORD **)v1 + 1);
  v37 = *(_OWORD **)(v36 + 24);
  if ( *(_DWORD *)(v36 + 32) - (_DWORD)v37 != 48 )
    goto LABEL_102;
  *(_OWORD *)lpMem = *v37;
  v93 = v37[1];
  v94 = v37[2];
  TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  v33 = Microsoft::Diagnostics::TraceManager::StopInactiveAgentTrace(
          TraceManager,
          v3,
          (const struct Microsoft::Diagnostics::TraceIdMessage *)lpMem);
  v34 = retaddr;
  if ( v33 < 0 )
  {
    v35 = 1013;
    goto LABEL_90;
  }
LABEL_143:
  if ( !**((_BYTE **)v1 + 3) )
  {
    v41 = Microsoft::Diagnostics::AgentTransport::ReceiveAgentMessage(v3);
    if ( v41 < 0 )
    {
      v64 = 1079;
      goto LABEL_112;
    }
  }
  if ( v88[1] )
    std::_Ref_count_base::_Decref(v88[1]);
  return 0;
}

```

## disassembly

```asm
0x180157214  push    rbx
0x180157216  push    rsi
0x180157217  push    rdi
0x180157218  push    r12
0x18015721a  push    r14
0x18015721c  push    r15
0x18015721e  sub     rsp, 6E8h
0x180157225  mov     rax, cs:__security_cookie
0x18015722c  xor     rax, rsp
0x18015722f  mov     [rsp+718h+var_48], rax
0x180157237  mov     r14, rcx
0x18015723a  mov     [rsp+718h+var_6C8], rcx
0x18015723f  xorps   xmm0, xmm0
0x180157242  movdqu  xmmword ptr [rsp+718h+var_6B8], xmm0
0x180157248  mov     rdx, [rcx]
0x18015724b  mov     r12d, 80h
0x180157251  add     rdx, r12
0x180157254  lea     rcx, [rsp+718h+var_698]
0x18015725c  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180157261  nop
0x180157262  mov     rax, [r14+8]
0x180157266  mov     rcx, [rax]
0x180157269  mov     rax, [rcx+8]
0x18015726d  mov     [rsp+718h+var_688], rax
0x180157275  mov     rbx, [r14]
0x180157278  lea     r8, [rsp+718h+var_688]
0x180157280  lea     rdx, [rsp+718h+var_6A8]
0x180157285  lea     rcx, [rbx+0D0h]
0x18015728c  call    ?find@?$_Tree@V?$_Tmap_traits@_KKU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KK@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,ulong,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ulong>>,0>>::find(unsigned __int64 const &)
0x180157291  mov     rdx, [rsp+718h+var_6A8]
0x180157296  cmp     rdx, [rbx+0D0h]
0x18015729d  setz    al
0x1801572a0  mov     rcx, [rsp+718h]; this
0x1801572a8  xor     edi, edi
0x1801572aa  test    al, al
0x1801572ac  jnz     loc_1801581C1
0x1801572b2  add     rdx, 28h ; '('
0x1801572b6  lea     rcx, [rsp+718h+var_6B8]
0x1801572bb  call    ??4?$shared_ptr@VITriggerInst@Diagnostics@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(std::shared_ptr<Microsoft::Diagnostics::ITriggerInst> const &)
0x1801572c0  mov     rsi, [rsp+718h+var_6B8]
0x1801572c5  mov     al, [rsi+0F9h]
0x1801572cb  nop
0x1801572cc  test    al, al
0x1801572ce  jz      short loc_180157302
0x1801572d0  lea     rcx, [rsi+108h]
0x1801572d7  lea     rdx, [rsp+718h+var_688]
0x1801572df  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801572e4  cmp     [rsp+718h+var_680], rdi
0x1801572ec  jz      short loc_180157302
0x1801572ee  cmp     [rsi+149h], dil
0x1801572f5  jz      short loc_180157302
0x1801572f7  xor     r8d, r8d; bool
0x1801572fa  mov     rdx, rsi; struct Microsoft::Diagnostics::AgentTransport *
0x1801572fd  call    ?LogIdleAgentEvent@AgentManager@Diagnostics@Microsoft@@AEAAXAEBVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::LogIdleAgentEvent(Microsoft::Diagnostics::AgentTransport const &,bool)
0x180157302  call    cs:__imp_GetTickCount64
0x180157308  mov     [rsi+150h], rax
0x18015730f  mov     [rsi+149h], dil
0x180157316  lea     rcx, [rsp+718h+var_698]
0x18015731e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180157323  mov     rax, [r14+10h]
0x180157327  cmp     [rax], dil
0x18015732a  jz      loc_180157CDB
0x180157330  mov     al, [rsi+0F9h]
0x180157336  nop
0x180157337  test    al, al
0x180157339  jz      loc_180157699
0x18015733f  mov     rax, [r14+10h]
0x180157343  cmp     byte ptr [rax], 4
0x180157346  jnz     loc_180157699
0x18015734c  mov     r8, [r14+8]
0x180157350  mov     rax, [r8]
0x180157353  mov     rdx, [rax+18h]
0x180157357  mov     ecx, [rax+20h]
0x18015735a  sub     ecx, edx
0x18015735c  cmp     ecx, 48h ; 'H'
0x18015735f  ja      short loc_18015739A
0x180157361  mov     rcx, [rsp+718h]; this
0x180157369  mov     r9d, 8007000Dh; char *
0x18015736f  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180157376  mov     edx, 39Ch; void *
0x18015737b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157380  nop
0x180157381  mov     rcx, [rsp+718h+var_6B8+8]; this
0x180157386  test    rcx, rcx
0x180157389  jz      short loc_180157390
0x18015738b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180157390  mov     eax, 8007000Dh
0x180157395  jmp     loc_1801581A0
0x18015739a  movups  xmm0, xmmword ptr [rdx]
0x18015739d  movaps  [rsp+718h+var_648], xmm0
0x1801573a5  movups  xmm1, xmmword ptr [rdx+10h]
0x1801573a9  movaps  [rsp+718h+var_638], xmm1
0x1801573b1  movups  xmm0, xmmword ptr [rdx+20h]
0x1801573b5  movaps  [rsp+718h+var_628], xmm0
0x1801573bd  movups  xmm1, xmmword ptr [rdx+30h]
0x1801573c1  movaps  [rsp+718h+var_618], xmm1
0x1801573c9  movsd   xmm0, qword ptr [rdx+40h]
0x1801573ce  movsd   [rsp+718h+var_608], xmm0
0x1801573d7  mov     rax, [r8]
0x1801573da  mov     rdx, [rax+18h]
0x1801573de  mov     r8d, [rax+20h]
0x1801573e2  sub     r8d, edx
0x1801573e5  add     r8d, 0FFFFFFB8h; unsigned int
0x1801573e9  mov     [rsp+718h+lpMem], rdi
0x1801573f1  mov     [rsp+718h+lpMem+8], rdi
0x1801573f9  mov     byte ptr [rsp+718h+var_668], dil
0x180157401  mov     cl, [rsi+0FAh]; bool
0x180157407  nop
0x180157408  add     rdx, 48h ; 'H'; void *
0x18015740c  lea     r9, [rsp+718h+lpMem]; struct JsonBuilder *
0x180157414  call    ?CreateJsonBuilderFromBufferOrString@Json@Utils@Diagnostics@Microsoft@@SAJ_NPEBXIAEAVJsonBuilder@@@Z; Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(bool,void const *,uint,JsonBuilder &)
0x180157419  mov     ebx, eax
0x18015741b  test    eax, eax
0x18015741d  jns     short loc_180157460
0x18015741f  mov     rcx, [rsp+718h]; this
0x180157427  mov     r9d, eax; char *
0x18015742a  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180157431  mov     edx, 3A4h; void *
0x180157436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015743b  nop
0x18015743c  mov     rcx, [rsp+718h+lpMem]; lpMem
0x180157444  call    ?Deallocate@PodVectorBase@JsonInternal@@KAXPEAX@Z; JsonInternal::PodVectorBase::Deallocate(void *)
0x180157449  nop
0x18015744a  mov     rcx, [rsp+718h+var_6B8+8]; this
0x18015744f  test    rcx, rcx
0x180157452  jz      short loc_180157459
0x180157454  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180157459  mov     eax, ebx
0x18015745b  jmp     loc_1801581A0
0x180157460  movzx   eax, word ptr cs:qword_18046330A
0x180157467  sub     ax, 3
0x18015746b  mov     ebx, 1
0x180157470  mov     r9, rsi
0x180157473  lea     r8, [rsp+718h+lpMem]
0x18015747b  lea     rdx, [rsp+718h+var_648]
0x180157483  cmp     ax, bx
0x180157486  ja      short loc_1801574D4
0x180157488  mov     byte ptr [rsp+718h+var_6F8], bl
0x18015748c  lea     rcx, [rsp+718h+var_6C8]
0x180157491  call    ?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)
0x180157496  nop
0x180157497  mov     rcx, 4059000000000000h
0x1801574a1  mov     rax, [rsp+718h+var_6C8]
0x1801574a6  mov     [rax+128h], rcx
0x1801574ad  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801574b4  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x1801574b9  xor     r8d, r8d; struct Microsoft::Diagnostics::IScenarioDef *
0x1801574bc  mov     rdx, [rsp+718h+var_6C8]; struct Microsoft::Diagnostics::ITriggerInst *
0x1801574c1  mov     rcx, rax; this
0x1801574c4  call    ?PersistTrigger@AsimovEventSerializer@Diagnostics@Microsoft@@QEAAJAEAVITriggerInst@23@PEBVIScenarioDef@23@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistTrigger(Microsoft::Diagnostics::ITriggerInst &,Microsoft::Diagnostics::IScenarioDef const *)
0x1801574c9  nop
0x1801574ca  mov     rcx, [rsp+718h+var_6C0]
0x1801574cf  jmp     loc_180157660
0x1801574d4  mov     byte ptr [rsp+718h+var_6F8], dil
0x1801574d9  lea     rcx, [rsp+718h+var_6A8]
0x1801574de  call    ?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)
0x1801574e3  nop
0x1801574e4  mov     al, [rsi+0FBh]
0x1801574ea  nop
0x1801574eb  test    al, al
0x1801574ed  jz      short loc_18015752D
0x1801574ef  mov     rcx, [rsp+718h+var_6A8]
0x1801574f4  mov     rax, [rcx]
0x1801574f7  mov     rax, [rax+50h]
0x1801574fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157500  mov     r8d, 10h; Size
0x180157506  lea     rdx, GUID_NULL; Buf2
0x18015750d  mov     rcx, rax; Buf1
0x180157510  call    memcmp_0
0x180157515  test    eax, eax
0x180157517  jz      short loc_18015752D
0x180157519  mov     rcx, [r14]
0x18015751c  add     rcx, 2E8h; this
0x180157523  mov     rdx, [rsp+718h+var_6A8]; struct Microsoft::Diagnostics::ETWTriggerInst *
0x180157528  call    ?RelogEvent@TraceLoggingDynamicRelogger@Diagnostics@Microsoft@@QEAAXAEBVETWTriggerInst@23@@Z; Microsoft::Diagnostics::TraceLoggingDynamicRelogger::RelogEvent(Microsoft::Diagnostics::ETWTriggerInst const &)
0x18015752d  mov     al, [rsi+15Dh]
0x180157533  nop
0x180157534  test    al, al
0x180157536  jnz     short loc_18015755F
0x180157538  xor     edx, edx
0x18015753a  mov     rcx, [rsp+718h+var_6A8]
0x18015753f  call    ?NeedsCommonSchemaTranslation@IAsimovEvent@Diagnostics@Microsoft@@QEAA_NPEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::IAsimovEvent::NeedsCommonSchemaTranslation(std::wstring_view *)
0x180157544  xor     al, bl
0x180157546  add     al, bl
0x180157548  xchg    al, [rsi+15Dh]
0x18015754e  jmp     short loc_18015755F
0x180157550  xor     edi, edi
0x180157552  lea     ebx, [rdi+1]
0x180157555  mov     rsi, [rsp+718h+var_6B8]
0x18015755a  mov     r14, [rsp+718h+var_6C8]
0x18015755f  mov     al, cs:byte_180462A28
0x180157565  nop
0x180157566  test    al, al
0x180157568  jz      loc_1801575F1
0x18015756e  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180157575  call    ?GetTriggerListener@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTriggerListener@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTriggerListener(void)
0x18015757a  mov     word ptr [rsp+718h+var_688], 1
0x180157584  movzx   r8d, word ptr [rsp+718h+var_688]
0x18015758d  lea     rdx, [rsp+718h+var_6C8]
0x180157592  mov     rcx, rax
0x180157595  call    ?GetConsumer@TriggerListener@Diagnostics@Microsoft@@QEAA?AV?$shared_ptr@VIConsumer@Diagnostics@Microsoft@@@std@@U?$optional@VTriggerType@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::TriggerListener::GetConsumer(better_enums::optional<Microsoft::Diagnostics::TriggerType>)
0x18015759a  mov     r12, [rax]
0x18015759d  mov     qword ptr [rsp+718h+var_698], r12
0x1801575a5  mov     r15, [rax+8]
0x1801575a9  mov     qword ptr [rsp+718h+var_698+8], r15
0x1801575b1  mov     [rax], rdi
0x1801575b4  mov     [rax+8], rdi
0x1801575b8  mov     rcx, [rsp+718h+var_6C0]; this
0x1801575bd  test    rcx, rcx
0x1801575c0  jz      short loc_1801575C7
0x1801575c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801575c7  mov     al, [rsi+15Dh]
0x1801575cd  nop
0x1801575ce  cmp     al, bl
0x1801575d0  setz    r8b
0x1801575d4  lea     rdx, [rsp+718h+var_6A8]
0x1801575d9  mov     rcx, r12
0x1801575dc  call    ?AgentEventCallback@ETWConsumer@Diagnostics@Microsoft@@QEAAXAEBV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@_N@Z; Microsoft::Diagnostics::ETWConsumer::AgentEventCallback(std::shared_ptr<Microsoft::Diagnostics::ETWTriggerInst> const &,bool)
0x1801575e1  nop
0x1801575e2  test    r15, r15
0x1801575e5  jz      short loc_18015765B
0x1801575e7  mov     rcx, r15; this
0x1801575ea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801575ef  jmp     short loc_18015765B
0x1801575f1  mov     eax, cs:dword_1804543B0
0x1801575f7  cmp     eax, 4
0x1801575fa  jbe     short loc_18015765B
0x1801575fc  mov     edx, 11h
0x180157601  lea     rcx, dword_1804543B0
0x180157608  call    _tlgKeywordOn
0x18015760d  test    al, al
0x18015760f  jz      short loc_18015765B
0x180157611  lea     rdx, [rsp+718h+var_698]
0x180157619  mov     rcx, [rsp+718h+var_6A8]
0x18015761e  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x180157623  mov     rbx, [rax+8]
0x180157627  lea     rdx, [rsp+718h+var_6C8]
0x18015762c  mov     rcx, [rsp+718h+var_6A8]
0x180157631  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x180157636  mov     r8d, ebx
0x180157639  mov     rdx, [rax]
0x18015763c  lea     rcx, [rsp+718h+var_688]
0x180157644  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180157649  mov     qword ptr [rsp+718h+var_6F8], rax
0x18015764e  lea     rdx, byte_1803EB165
0x180157655  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x18015765a  nop
0x18015765b  mov     rcx, [rsp+718h+var_6A0]; this
0x180157660  test    rcx, rcx
0x180157663  jz      short loc_18015766B
0x180157665  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18015766a  nop
0x18015766b  mov     rcx, [rsp+718h+lpMem]; lpMem
0x180157673  call    ?Deallocate@PodVectorBase@JsonInternal@@KAXPEAX@Z; JsonInternal::PodVectorBase::Deallocate(void *)
0x180157678  nop
0x180157679  jmp     loc_18015816E
0x18015767e  mov     rcx, [rsp+718h+var_6B8+8]; this
0x180157683  test    rcx, rcx
0x180157686  jz      short loc_18015768D
0x180157688  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18015768d  mov     eax, dword ptr [rsp+718h+var_688]
0x180157694  jmp     loc_1801581A0
0x180157699  mov     al, [rsi+0F9h]
0x18015769f  nop
0x1801576a0  test    al, al
0x1801576a2  jz      loc_180157738
0x1801576a8  mov     rax, [r14+10h]
0x1801576ac  cmp     byte ptr [rax], 5
0x1801576af  jnz     loc_180157738
0x1801576b5  mov     rax, [r14+8]
0x1801576b9  mov     rax, [rax]
0x1801576bc  mov     rcx, [rax+18h]
0x1801576c0  mov     eax, [rax+20h]
0x1801576c3  sub     eax, ecx
0x1801576c5  cmp     eax, 4
0x1801576c8  jnz     loc_180157CF2
0x1801576ce  mov     r8d, [rcx]
0x1801576d1  mov     eax, cs:dword_1804543B0
0x1801576d7  cmp     eax, 4
0x1801576da  jbe     short loc_18015772C
0x1801576dc  mov     edx, 8010h
0x1801576e1  lea     rcx, dword_1804543B0
0x1801576e8  call    _tlgKeywordOn
0x1801576ed  test    al, al
0x1801576ef  jz      short loc_18015772C
0x1801576f1  mov     dword ptr [rsp+718h+var_688], r8d
0x1801576f9  mov     rax, [r14+8]
0x1801576fd  mov     rcx, [rax]
0x180157700  mov     rax, [rcx+8]
0x180157704  mov     [rsp+718h+var_6C8], rax
0x180157709  lea     rax, [rsp+718h+var_688]
0x180157711  mov     [rsp+718h+var_6F0], rax
0x180157716  lea     rax, [rsp+718h+var_6C8]
0x18015771b  mov     qword ptr [rsp+718h+var_6F8], rax
0x180157720  lea     rdx, byte_1803EB1A5
0x180157727  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18015772c  mov     rax, [r14+18h]
0x180157730  mov     byte ptr [rax], 1
0x180157733  jmp     loc_18015816E
0x180157738  mov     al, [rsi+0F9h]
  ... truncated ...
```
