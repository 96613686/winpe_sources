# Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(wchar_t const *)

- ea: `0x18029a310`
- end: `0x18029b0e6`
- name: `?SnapHostMiniTrace@AgentUtcApiManager@Diagnostics@Microsoft@@UEAAJPEB_W@Z`
- size: `3542`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::AgentUtcApiManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180020150`
- `0x180022570`
- `0x1800249a0`
- `0x18002b318`
- `0x18002ba00`
- `0x18002cae0`
- `0x18002d7d0`
- `0x18002df00`
- `0x18004f698`
- `0x180052240`
- `0x180056a90`
- `0x180064e34`
- `0x180064e8c`
- `0x180085f08`
- `0x18009c8c0`
- `0x1800bc488`
- `0x1800bc508`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800c53b4`
- `0x1800c5d5c`
- `0x1800cf7d8`
- `0x18010b7dc`
- `0x180140a5c`
- `0x1801b0820`
- `0x1801ba5dc`
- `0x1801bbd5c`
- `0x1801d4e24`
- `0x18020aac0`
- `0x18020aae4`
- `0x18029a310`
- `0x18029df5c`
- `0x1802b8b48`
- `0x1802f2544`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029adc8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029adc8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18029a3fe`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18029a3fe`

## string_xrefs

- `0x18029a35a`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a391`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a3ce`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a415`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a4b7`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a53b`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a5d3`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a708`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a908`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a9d4`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029aab4`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ab77`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ac69`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ade3`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029af59`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(
        Microsoft::Diagnostics::AgentUtcApiManager *this,
        const wchar_t *a2)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  int appended; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  char *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r10
  struct Microsoft::Diagnostics::Agent *Agent; // rbx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // ebx
  struct Microsoft::Diagnostics::Agent *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  struct Microsoft::Diagnostics::Agent *v25; // rax
  void **v26; // rax
  void *v27; // rcx
  struct Microsoft::Diagnostics::Agent *v28; // rax
  int v29; // ebx
  struct Microsoft::Diagnostics::Agent *v30; // rax
  __int64 v31; // rcx
  int RpcImpersonationToken; // eax
  unsigned int v33; // ebx
  struct Microsoft::Diagnostics::Agent *v34; // rax
  __int64 v35; // r8
  Microsoft::Diagnostics::UserManager *v36; // r8
  __int64 UserContextForSid; // rbx
  int UserToken; // eax
  unsigned int v39; // ebx
  struct Microsoft::Diagnostics::Agent *v40; // rax
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // ebx
  struct Microsoft::Diagnostics::Agent *v44; // rax
  struct Microsoft::Diagnostics::Agent *v45; // rax
  int v46; // [rsp+20h] [rbp-188h]
  int v47; // [rsp+20h] [rbp-188h]
  int v48; // [rsp+20h] [rbp-188h]
  size_t Size; // [rsp+30h] [rbp-178h]
  size_t Sizea; // [rsp+30h] [rbp-178h]
  __int128 v51; // [rsp+40h] [rbp-168h] BYREF
  char Src; // [rsp+50h] [rbp-158h] BYREF
  char v53; // [rsp+51h] [rbp-157h] BYREF
  int v54[3]; // [rsp+52h] [rbp-156h] BYREF
  __int64 v55[2]; // [rsp+60h] [rbp-148h] BYREF
  __int64 v56[2]; // [rsp+70h] [rbp-138h] BYREF
  int v57[4]; // [rsp+80h] [rbp-128h] BYREF
  int v58[4]; // [rsp+90h] [rbp-118h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-100h]
  char v61; // [rsp+B0h] [rbp-F8h]
  __int128 v62; // [rsp+C0h] [rbp-E8h] BYREF
  __int128 v63; // [rsp+D0h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+E0h] [rbp-C8h] BYREF
  WCHAR v65[16]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v66[32]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v67[32]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v68[32]; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( a2 )
  {
    if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_180463230 + 1, 0, 0) )
    {
      if ( *((_BYTE *)Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
           + 192) )
      {
        pguid = GUID_NULL;
        v5 = CoCreateGuid(&pguid);
        v6 = v5;
        if ( v5 >= 0 )
        {
          Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(v65);
          v7 = Microsoft::Diagnostics::Utils::String::StringFromGuidW(v68, &pguid, 0);
          std::operator+<wchar_t>(v66, L"hostminitrace_", v7);
          std::wstring::_Tidy_deallocate(v68);
          *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(v66, &v51);
          appended = Microsoft::Diagnostics::Utils::String::AppendPath(v65, v55);
          v9 = appended;
          if ( appended >= 0 )
          {
            *(_OWORD *)v55 = *(_OWORD *)&off_180385550;
            v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v51);
            v10 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(&v63, 0, v55);
            v11 = v10;
            if ( v10 >= 0 )
            {
              *(_QWORD *)&v62 = v65;
              BYTE8(v62) = 1;
              std::wstring::wstring(v67, v65);
              *(_OWORD *)v55 = *(_OWORD *)&off_18036CE20;
              v12 = Microsoft::Diagnostics::Utils::String::AppendPath(v67, v55);
              v13 = v12;
              if ( v12 >= 0 )
              {
                v14 = (char *)operator new(0x58u);
                *(_QWORD *)v57 = v14;
                *((_DWORD *)v14 + 2) = 1;
                *((_DWORD *)v14 + 3) = 1;
                *(_QWORD *)v14 = &std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable';
                *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, &v51);
                Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(v14 + 16, v55);
                *(_QWORD *)&v63 = v14 + 16;
                *((_QWORD *)&v63 + 1) = v14;
                Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
                  v55,
                  &v63);
                *(_OWORD *)v57 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                if ( Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(
                       v16,
                       (__int64)&pguid,
                       (__int128 *)v57,
                       v15) )
                {
                  *(_QWORD *)&v51 = &pguid;
                  BYTE8(v51) = 1;
                  lpMem = 0;
                  v60 = 0;
                  v61 = 1;
                  Src = 2;
                  v55[0] = (__int64)L"tslty";
                  v55[1] = 5;
                  *(_QWORD *)v57 = &lpMem;
                  v57[2] = 0;
                  v57[3] = HIDWORD(v51);
                  LODWORD(Size) = 1;
                  JsonBuilder::AddValue((int)&lpMem, (int)v58, 0, (int)v57, (__int64)v55, 246, Size, &Src);
                  v55[0] = (__int64)L"trid";
                  v55[1] = 4;
                  *(_QWORD *)v57 = &lpMem;
                  v57[2] = 0;
                  v57[3] = v58[3];
                  LODWORD(Sizea) = 16;
                  JsonBuilder::AddValue((int)&lpMem, (int)v58, 0, (int)v57, (__int64)v55, 251, Sizea, &pguid);
                  Agent = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                  gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
                    v55,
                    lpMem,
                    4LL * (unsigned int)v60);
                  LOBYTE(v18) = 13;
                  v19 = Microsoft::Diagnostics::Agent::SendAgentMessage(Agent, v18, v55);
                  v21 = v19;
                  if ( v19 >= 0 )
                  {
                    LOBYTE(v20) = 13;
                    v23 = Microsoft::Diagnostics::AgentUtcApiManager::WaitForHostEvent(this, v20);
                    v24 = v23;
                    if ( v23 >= 0 )
                    {
                      v26 = (void **)*((_QWORD *)v14 + 6);
                      if ( v26 )
                        v27 = *v26;
                      else
                        v27 = 0;
                      if ( Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(v27, 0xEA60u) )
                      {
                        v29 = *((_DWORD *)v14 + 16);
                        if ( v29 >= 0 )
                        {
                          v56[0] = 0;
                          std::wstring::wstring(v68);
                          *(_QWORD *)v57 = 0;
                          RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(
                                                    v31,
                                                    v57,
                                                    v68);
                          v33 = RpcImpersonationToken;
                          if ( RpcImpersonationToken >= 0 )
                          {
                            Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v58);
                            if ( (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v35, v55)
                              && (Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager),
                                  *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v58),
                                  UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v36),
                                  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                                    v56,
                                    0),
                                  UserToken = UMgrQueryUserToken(UserContextForSid, v56),
                                  v39 = UserToken,
                                  UserToken < 0) )
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x55,
                                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                (const char *)(unsigned int)UserToken,
                                v47);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v57);
                              std::wstring::_Tidy_deallocate(v68);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
                              JsonInternal::PodVectorBase::Deallocate(lpMem);
                              v40 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                              v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                              Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                v40,
                                &pguid,
                                &v51);
                              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                              std::wstring::_Tidy_deallocate(v67);
                              v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                              Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                              std::wstring::_Tidy_deallocate(v66);
                              std::wstring::_Tidy_deallocate(v65);
                              return v39;
                            }
                            else
                            {
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v57);
                              std::wstring::_Tidy_deallocate(v68);
                              LOWORD(v54[0]) = 0;
                              v53 = 0;
                              v41 = std::_WChar_traits<wchar_t>::length(a2);
                              v55[0] = (__int64)a2;
                              v55[1] = v41;
                              *(_OWORD *)v57 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                              v42 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
                                      (__int128 *)v57,
                                      (__int128 *)v55,
                                      v56,
                                      (_BYTE *)v54 + 1,
                                      v54,
                                      &v53);
                              v43 = v42;
                              if ( v42 >= 0 )
                              {
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v45 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  v45,
                                  &pguid,
                                  &v51);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                                std::wstring::_Tidy_deallocate(v67);
                                v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                                std::wstring::_Tidy_deallocate(v66);
                                std::wstring::_Tidy_deallocate(v65);
                                return 0;
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0x61,
                                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                  (const char *)(unsigned int)v42,
                                  v48);
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v44 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  v44,
                                  &pguid,
                                  &v51);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                                std::wstring::_Tidy_deallocate(v67);
                                v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                                std::wstring::_Tidy_deallocate(v66);
                                std::wstring::_Tidy_deallocate(v65);
                                return v43;
                              }
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x50,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                              (const char *)(unsigned int)RpcImpersonationToken,
                              v47);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v57);
                            std::wstring::_Tidy_deallocate(v68);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
                            JsonInternal::PodVectorBase::Deallocate(lpMem);
                            v34 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                            Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v34, &pguid, &v51);
                            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                            std::wstring::_Tidy_deallocate(v67);
                            v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                            Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                            std::wstring::_Tidy_deallocate(v66);
                            std::wstring::_Tidy_deallocate(v65);
                            return v33;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x49,
                            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                            (const char *)(unsigned int)v29,
                            v47);
                          JsonInternal::PodVectorBase::Deallocate(lpMem);
                          v30 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                          v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                          Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v30, &pguid, &v51);
                          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                          std::wstring::_Tidy_deallocate(v67);
                          v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                          Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                          std::wstring::_Tidy_deallocate(v66);
                          std::wstring::_Tidy_deallocate(v65);
                          return (unsigned int)v29;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x47,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                          (const char *)0x800705B4LL,
                          v47);
                        JsonInternal::PodVectorBase::Deallocate(lpMem);
                        v28 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                        v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                        Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v28, &pguid, &v51);
                        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                        std::wstring::_Tidy_deallocate(v67);
                        v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                        Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                        std::wstring::_Tidy_deallocate(v66);
                        std::wstring::_Tidy_deallocate(v65);
                        return 2147943860LL;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x43,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                        (const char *)(unsigned int)v23,
                        v47);
                      JsonInternal::PodVectorBase::Deallocate(lpMem);
                      v25 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                      v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                      Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v25, &pguid, &v51);
                      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                      std::wstring::_Tidy_deallocate(v67);
                      v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                      Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                      std::wstring::_Tidy_deallocate(v66);
                      std::wstring::_Tidy_deallocate(v65);
                      return v24;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x40,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                      (const char *)(unsigned int)v19,
                      v47);
                    JsonInternal::PodVectorBase::Deallocate(lpMem);
                    v22 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                    v51 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                    Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v22, &pguid, &v51);
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                    std::wstring::_Tidy_deallocate(v67);
                    v51 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, v58);
                    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v51);
                    std::wstring::_Tidy_deallocate(v66);
                    std::wstring::_Tidy_deallocate(v65);
                    return v21;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2E,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                    (const char *)0x800700B7LL,
                    v46);
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                  std::wstring::_Tidy_deallocate(v67);
                  v62 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v51);
                  Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v62);
                  std::wstring::_Tidy_deallocate(v66);
                  std::wstring::_Tidy_deallocate(v65);
                  return 2147942583LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x29,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                  (const char *)(unsigned int)v12,
                  v46);
                std::wstring::_Tidy_deallocate(v67);
                v62 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v51);
                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v62);
                std::wstring::_Tidy_deallocate(v66);
                std::wstring::_Tidy_deallocate(v65);
                return v13;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x20,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                (const char *)(unsigned int)v10,
                v46);
              std::wstring::_Tidy_deallocate(v66);
              std::wstring::_Tidy_deallocate(v65);
              return v11;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
              (const char *)(unsigned int)appended,
              v46);
            std::wstring::_Tidy_deallocate(v66);
            std::wstring::_Tidy_deallocate(v65);
            return v9;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
            (const char *)(unsigned int)v5,
            v46);
          return v6;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
          (const char *)0x80070032LL,
          v46);
        return 2147942450LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
        (const char *)0x80070015LL,
        v46);
      return 2147942421LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18029a310  mov     [rsp+arg_8], rbx
0x18029a315  mov     [rsp+arg_10], rsi
0x18029a31a  push    rdi
0x18029a31b  push    r12
0x18029a31d  push    r13
0x18029a31f  push    r14
0x18029a321  push    r15
0x18029a323  sub     rsp, 180h
0x18029a32a  mov     rax, cs:__security_cookie
0x18029a331  xor     rax, rsp
0x18029a334  mov     [rsp+1A8h+var_38], rax
0x18029a33c  mov     r14, rdx
0x18029a33f  mov     r15, rcx
0x18029a342  xor     r12d, r12d
0x18029a345  test    rdx, rdx
0x18029a348  jnz     short loc_18029A371
0x18029a34a  mov     rcx, [rsp+1A8h]; this
0x18029a352  mov     ebx, 80070057h
0x18029a357  mov     r9d, ebx; char *
0x18029a35a  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a361  lea     edx, [r14+12h]; void *
0x18029a365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a36a  mov     eax, ebx
0x18029a36c  jmp     loc_18029B0B8
0x18029a371  mov     rcx, r12
0x18029a374  xor     eax, eax
0x18029a376  lock cmpxchg qword ptr cs:xmmword_180463230+8, rcx
0x18029a37f  jnz     short loc_18029A3A9
0x18029a381  mov     rcx, [rsp+1A8h]; this
0x18029a389  mov     ebx, 80070015h
0x18029a38e  mov     r9d, ebx; char *
0x18029a391  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a398  mov     edx, 13h; void *
0x18029a39d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a3a2  mov     eax, ebx
0x18029a3a4  jmp     loc_18029B0B8
0x18029a3a9  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029a3b0  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a3b5  cmp     [rax+0C0h], r12b
0x18029a3bc  jnz     short loc_18029A3E6
0x18029a3be  mov     rcx, [rsp+1A8h]; this
0x18029a3c6  mov     ebx, 80070032h
0x18029a3cb  mov     r9d, ebx; char *
0x18029a3ce  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a3d5  mov     edx, 16h; void *
0x18029a3da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a3df  mov     eax, ebx
0x18029a3e1  jmp     loc_18029B0B8
0x18029a3e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18029a3ed  movdqu  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x18029a3f6  lea     rcx, [rsp+1A8h+pguid]; pguid
0x18029a3fe  call    cs:__imp_CoCreateGuid
0x18029a404  mov     ebx, eax
0x18029a406  test    eax, eax
0x18029a408  jns     short loc_18029A42D
0x18029a40a  mov     rcx, [rsp+1A8h]; this
0x18029a412  mov     r9d, eax; char *
0x18029a415  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a41c  mov     edx, 1Ah; void *
0x18029a421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a426  mov     eax, ebx
0x18029a428  jmp     loc_18029B0B8
0x18029a42d  lea     rcx, [rsp+1A8h+var_B8]; lpSrc
0x18029a435  call    ?GetUtcTemporaryPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(void)
0x18029a43a  nop
0x18029a43b  xor     r8d, r8d
0x18029a43e  lea     rdx, [rsp+1A8h+pguid]
0x18029a446  lea     rcx, [rsp+1A8h+var_58]
0x18029a44e  call    ?StringFromGuidW@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::StringFromGuidW(_GUID const &,bool)
0x18029a453  nop
0x18029a454  mov     r8, rax
0x18029a457  lea     rdx, aHostminitrace; "hostminitrace_"
0x18029a45e  lea     rcx, [rsp+1A8h+var_98]
0x18029a466  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x18029a46b  nop
0x18029a46c  lea     rcx, [rsp+1A8h+var_58]
0x18029a474  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a479  lea     rdx, [rsp+1A8h+var_168]
0x18029a47e  lea     rcx, [rsp+1A8h+var_98]
0x18029a486  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a48b  movups  xmm0, xmmword ptr [rax]
0x18029a48e  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a494  lea     rdx, [rsp+1A8h+var_148]
0x18029a499  lea     rcx, [rsp+1A8h+var_B8]
0x18029a4a1  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18029a4a6  mov     ebx, eax
0x18029a4a8  test    eax, eax
0x18029a4aa  jns     short loc_18029A4EB
0x18029a4ac  mov     rcx, [rsp+1A8h]; this
0x18029a4b4  mov     r9d, eax; char *
0x18029a4b7  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a4be  mov     edx, 1Fh; void *
0x18029a4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a4c8  nop
0x18029a4c9  lea     rcx, [rsp+1A8h+var_98]
0x18029a4d1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a4d6  nop
0x18029a4d7  lea     rcx, [rsp+1A8h+var_B8]
0x18029a4df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a4e4  mov     eax, ebx
0x18029a4e6  jmp     loc_18029B0B8
0x18029a4eb  movups  xmm0, xmmword ptr cs:off_180385550; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x18029a4f2  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a4f8  lea     rdx, [rsp+1A8h+var_168]
0x18029a4fd  lea     rcx, [rsp+1A8h+var_B8]
0x18029a505  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a50a  movups  xmm0, xmmword ptr [rax]
0x18029a50d  movdqu  [rsp+1A8h+var_D8], xmm0
0x18029a516  lea     r8, [rsp+1A8h+var_148]
0x18029a51b  xor     edx, edx
0x18029a51d  lea     rcx, [rsp+1A8h+var_D8]
0x18029a525  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x18029a52a  mov     ebx, eax
0x18029a52c  test    eax, eax
0x18029a52e  jns     short loc_18029A56F
0x18029a530  mov     rcx, [rsp+1A8h]; this
0x18029a538  mov     r9d, eax; char *
0x18029a53b  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a542  mov     edx, 20h ; ' '; void *
0x18029a547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a54c  nop
0x18029a54d  lea     rcx, [rsp+1A8h+var_98]
0x18029a555  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a55a  nop
0x18029a55b  lea     rcx, [rsp+1A8h+var_B8]
0x18029a563  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a568  mov     eax, ebx
0x18029a56a  jmp     loc_18029B0B8
0x18029a56f  lea     rax, [rsp+1A8h+var_B8]
0x18029a577  mov     qword ptr [rsp+1A8h+var_E8], rax
0x18029a57f  mov     r13d, 1
0x18029a585  mov     byte ptr [rsp+1A8h+var_E8+8], r13b
0x18029a58d  lea     rdx, [rsp+1A8h+var_B8]
0x18029a595  lea     rcx, [rsp+1A8h+var_78]
0x18029a59d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18029a5a2  nop
0x18029a5a3  movaps  xmm0, xmmword ptr cs:off_18036CE20; "minitrace.etl"
0x18029a5aa  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a5b0  lea     rdx, [rsp+1A8h+var_148]
0x18029a5b5  lea     rcx, [rsp+1A8h+var_78]
0x18029a5bd  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18029a5c2  mov     ebx, eax
0x18029a5c4  test    eax, eax
0x18029a5c6  jns     short loc_18029A640
0x18029a5c8  mov     rcx, [rsp+1A8h]; this
0x18029a5d0  mov     r9d, eax; char *
0x18029a5d3  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a5da  lea     edx, [r13+28h]; void *
0x18029a5de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a5e3  nop
0x18029a5e4  lea     rcx, [rsp+1A8h+var_78]
0x18029a5ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a5f1  nop
0x18029a5f2  lea     rdx, [rsp+1A8h+var_168]
0x18029a5f7  lea     rcx, [rsp+1A8h+var_B8]
0x18029a5ff  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a604  movups  xmm0, xmmword ptr [rax]
0x18029a607  movdqu  [rsp+1A8h+var_E8], xmm0
0x18029a610  lea     rcx, [rsp+1A8h+var_E8]
0x18029a618  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x18029a61d  nop
0x18029a61e  lea     rcx, [rsp+1A8h+var_98]
0x18029a626  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a62b  nop
0x18029a62c  lea     rcx, [rsp+1A8h+var_B8]
0x18029a634  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a639  mov     eax, ebx
0x18029a63b  jmp     loc_18029B0B8
0x18029a640  mov     ecx, 58h ; 'X'; Size
0x18029a645  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029a64a  mov     rdi, rax
0x18029a64d  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a655  mov     [rax+8], r13d
0x18029a659  mov     [rax+0Ch], r13d
0x18029a65d  lea     rax, ??_7?$_Ref_count_obj2@UEscalationDataRequest@Diagnostics@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable'
0x18029a664  mov     [rdi], rax
0x18029a667  lea     rsi, [rdi+10h]
0x18029a66b  lea     rdx, [rsp+1A8h+var_168]
0x18029a670  lea     rcx, [rsp+1A8h+var_78]
0x18029a678  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a67d  movups  xmm0, xmmword ptr [rax]
0x18029a680  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a686  lea     rdx, [rsp+1A8h+var_148]
0x18029a68b  mov     rcx, rsi
0x18029a68e  call    ??0EscalationDataRequest@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(std::wstring_view)
0x18029a693  nop
0x18029a694  mov     qword ptr [rsp+1A8h+var_D8], rsi
0x18029a69c  mov     qword ptr [rsp+1A8h+var_D8+8], rdi
0x18029a6a4  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029a6ab  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a6b0  mov     r10, rax
0x18029a6b3  lea     rdx, [rsp+1A8h+var_D8]; void *
0x18029a6bb  lea     rcx, [rsp+1A8h+var_148]; void *
0x18029a6c0  call    ??0?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> const &)
0x18029a6c5  movups  xmm0, xmmword ptr cs:?k_hostAgentTransportId@Agent@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::Agent::k_hostAgentTransportId
0x18029a6cc  movdqu  xmmword ptr [rsp+1A8h+var_128], xmm0
0x18029a6d5  mov     r9, rax
0x18029a6d8  lea     r8, [rsp+1A8h+var_128]
0x18029a6e0  lea     rdx, [rsp+1A8h+pguid]
0x18029a6e8  mov     rcx, r10
0x18029a6eb  call    ?RegisterEscalationDataRequest@IAgentIoReceiver@Diagnostics@Microsoft@@QEAA_NAEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@6@@Z; Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(_GUID const &,std::wstring_view,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>)
0x18029a6f0  test    al, al
0x18029a6f2  jnz     loc_18029A77F
0x18029a6f8  mov     rcx, [rsp+1A8h]; this
0x18029a700  mov     ebx, 800700B7h
0x18029a705  mov     r9d, ebx; char *
0x18029a708  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a70f  mov     edx, 2Eh ; '.'; void *
0x18029a714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a719  nop
0x18029a71a  mov     rcx, rdi; this
0x18029a71d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18029a722  nop
0x18029a723  lea     rcx, [rsp+1A8h+var_78]
0x18029a72b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a730  nop
0x18029a731  lea     rdx, [rsp+1A8h+var_168]
0x18029a736  lea     rcx, [rsp+1A8h+var_B8]
0x18029a73e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a743  movups  xmm0, xmmword ptr [rax]
0x18029a746  movdqu  [rsp+1A8h+var_E8], xmm0
0x18029a74f  lea     rcx, [rsp+1A8h+var_E8]
0x18029a757  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x18029a75c  nop
0x18029a75d  lea     rcx, [rsp+1A8h+var_98]
0x18029a765  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a76a  nop
0x18029a76b  lea     rcx, [rsp+1A8h+var_B8]
0x18029a773  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a778  mov     eax, ebx
0x18029a77a  jmp     loc_18029B0B8
0x18029a77f  lea     rax, [rsp+1A8h+pguid]
0x18029a787  mov     qword ptr [rsp+1A8h+var_168], rax
0x18029a78c  mov     byte ptr [rsp+1A8h+var_168+8], r13b
0x18029a791  mov     [rsp+1A8h+lpMem], r12
0x18029a799  mov     [rsp+1A8h+var_100], r12
0x18029a7a1  mov     [rsp+1A8h+var_F8], r13b
0x18029a7a9  mov     [rsp+1A8h+var_158], 2
0x18029a7ae  mov     rax, cs:off_180385510; "tslty"
0x18029a7b5  mov     [rsp+1A8h+var_148], rax
0x18029a7ba  mov     [rsp+1A8h+var_148+8], 5
0x18029a7c3  lea     rax, [rsp+1A8h+lpMem]
0x18029a7cb  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a7d3  mov     [rsp+1A8h+var_128+8], r12d
0x18029a7db  mov     eax, dword ptr [rsp+1A8h+var_168+0Ch]
0x18029a7df  mov     [rsp+1A8h+var_128+0Ch], eax
0x18029a7e6  lea     rax, [rsp+1A8h+var_158]
0x18029a7eb  mov     [rsp+1A8h+Src], rax; Src
0x18029a7f0  mov     dword ptr [rsp+1A8h+Size], r13d; Size
0x18029a7f5  mov     [rsp+1A8h+var_180], 0F6h; int
0x18029a7fd  lea     rax, [rsp+1A8h+var_148]
0x18029a802  mov     [rsp+1A8h+var_188], rax; __int64
0x18029a807  lea     r9, [rsp+1A8h+var_128]; int
0x18029a80f  xor     r8d, r8d; int
0x18029a812  lea     rdx, [rsp+1A8h+var_118]; int
0x18029a81a  lea     rcx, [rsp+1A8h+lpMem]; int
0x18029a822  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x18029a827  mov     rax, cs:off_180385520; "trid"
0x18029a82e  mov     [rsp+1A8h+var_148], rax
0x18029a833  mov     [rsp+1A8h+var_148+8], 4
0x18029a83c  lea     rax, [rsp+1A8h+lpMem]
0x18029a844  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a84c  mov     [rsp+1A8h+var_128+8], r12d
0x18029a854  mov     eax, [rsp+1A8h+var_10C]
0x18029a85b  mov     [rsp+1A8h+var_128+0Ch], eax
0x18029a862  lea     rax, [rsp+1A8h+pguid]
0x18029a86a  mov     [rsp+1A8h+Src], rax; Src
0x18029a86f  mov     dword ptr [rsp+1A8h+Size], 10h; Size
0x18029a877  mov     [rsp+1A8h+var_180], 0FBh; int
0x18029a87f  lea     rax, [rsp+1A8h+var_148]
0x18029a884  mov     [rsp+1A8h+var_188], rax; int
0x18029a889  lea     r9, [rsp+1A8h+var_128]; int
0x18029a891  xor     r8d, r8d; int
0x18029a894  lea     rdx, [rsp+1A8h+var_118]; int
0x18029a89c  lea     rcx, [rsp+1A8h+lpMem]; int
0x18029a8a4  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x18029a8a9  lea     r13, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x18029a8b0  mov     rcx, r13; this
0x18029a8b3  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a8b8  mov     rbx, rax
0x18029a8bb  mov     r8d, dword ptr [rsp+1A8h+var_100]
0x18029a8c3  shl     r8, 2
0x18029a8c7  mov     rdx, [rsp+1A8h+lpMem]
0x18029a8cf  lea     rcx, [rsp+1A8h+var_148]
0x18029a8d4  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x18029a8d9  movups  xmm0, xmmword ptr [rsp+1A8h+var_148]
0x18029a8de  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a8e4  lea     r8, [rsp+1A8h+var_148]
0x18029a8e9  mov     dl, 0Dh
0x18029a8eb  mov     rcx, rbx
0x18029a8ee  call    ?SendAgentMessage@Agent@Diagnostics@Microsoft@@QEAAJVAgentMessageType@23@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Agent::SendAgentMessage(Microsoft::Diagnostics::AgentMessageType,gsl::span<gsl::byte const,-1>)
0x18029a8f3  mov     ebx, eax
0x18029a8f5  test    eax, eax
0x18029a8f7  jns     loc_18029A9B5
0x18029a8fd  mov     rcx, [rsp+1A8h]; this
0x18029a905  mov     r9d, eax; char *
0x18029a908  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a90f  mov     edx, 40h ; '@'; void *
0x18029a914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a919  nop
  ... truncated ...
```
