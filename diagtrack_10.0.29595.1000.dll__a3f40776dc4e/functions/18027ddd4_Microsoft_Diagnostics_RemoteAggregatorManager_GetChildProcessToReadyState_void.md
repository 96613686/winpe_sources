# Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyState(void)

- ea: `0x18027ddd4`
- end: `0x18027e34d`
- name: `?GetChildProcessToReadyState@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ`
- size: `1401`
- prototype: `void __fastcall(Microsoft::Diagnostics::RemoteAggregatorManager *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18027e9d0`

## callees

- `0x18001ef10`
- `0x180024558`
- `0x18002b318`
- `0x180038dc8`
- `0x18003c66c`
- `0x180049bec`
- `0x180055730`
- `0x180058b08`
- `0x180064e34`
- `0x180087328`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x180097bc8`
- `0x1800b47f0`
- `0x1800b6204`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800cc574`
- `0x1800d11c0`
- `0x1800fc72c`
- `0x18010f8f4`
- `0x1801225d0`
- `0x180156e28`
- `0x1801bbc78`
- `0x1801c2524`
- `0x1801c27f8`
- `0x1801c33dc`
- `0x1801cd84c`
- `0x18020aac0`
- `0x18020bab8`
- `0x18023d028`
- `0x18027c94c`
- `0x18027dc3c`
- `0x18027ddd4`
- `0x1802aa708`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18027de20`
- `msvcp_win!_Mtx_unlock` at `0x18027de2b`
- `msvcp_win!_Mtx_unlock` at `0x18027dfc3`
- `msvcp_win!_Mtx_unlock` at `0x18027e089`
- `msvcp_win!_Mtx_unlock` at `0x18027de20`
- `msvcp_win!_Mtx_unlock` at `0x18027de2b`
- `msvcp_win!_Mtx_unlock` at `0x18027dfc3`
- `msvcp_win!_Mtx_unlock` at `0x18027e089`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18027e2ef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18027e2ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18027df94`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18027dfa1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18027df94`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18027dfa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027e28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027e28b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18027e080`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18027e080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18027df20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18027df20`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18027e046`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18027e046`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18027e0fd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18027e0fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18027e16c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18027e16c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18027e058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18027e058`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18027e1b6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18027e1b6`

## string_xrefs

- `0x18027e0e8`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e1d8`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e233`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e249`: `RemoteAggregatorManager_CreateProcessFailed_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyState(
        Microsoft::Diagnostics::RemoteAggregatorManager *this)
{
  struct _Mtx_internal_imp_t *v2; // rbx
  _QWORD *v3; // rbx
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  HANDLE CurrentProcess; // rax
  Microsoft::Diagnostics::RemoteAggregatorManager *v6; // rcx
  void *v7; // rdi
  Microsoft::Diagnostics::RemoteAggregatorManager *v8; // rcx
  void *v9; // rbx
  Microsoft::Diagnostics::RemoteAggregatorManager *v10; // rcx
  HANDLE *v11; // rdi
  void *v12; // rcx
  __int64 v13; // rdx
  const char *v14; // r9
  struct _TP_WAIT *v15; // rcx
  int Key; // eax
  DWORD ProcessId; // eax
  DWORD v18; // r9d
  DWORD v19; // eax
  const char *v20; // r9
  DWORD v21; // eax
  DWORD v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // r8
  char v26; // dl
  char v27; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  void *v30; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v33[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v35[5]; // [rsp+B8h] [rbp-48h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v37[1128]; // [rsp+150h] [rbp+50h] BYREF
  char v38[56]; // [rsp+5B8h] [rbp+4B8h] BYREF
  HANDLE Handles[3]; // [rsp+5F0h] [rbp+4F0h] BYREF
  WCHAR CommandLine[20]; // [rsp+608h] [rbp+508h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+658h] [rbp+558h]

  v2 = (Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1832);
  std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1832));
  if ( *((_BYTE *)this + 1912) )
  {
    _Mtx_unlock(v2);
    return;
  }
  _Mtx_unlock(v2);
  if ( (unsigned int)std::_Atomic_storage<unsigned long,4>::load((char *)this + 1696, 5) )
  {
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v33, (char *)this + 2104);
    v3 = (_QWORD *)*((_QWORD *)this + 281);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>>>(
      (char *)this + 2248,
      (char *)this + 2248,
      v3[1]);
    v3[1] = v3;
    *v3 = v3;
    v3[2] = v3;
    *((_QWORD *)this + 282) = 0;
    Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(this);
    Microsoft::Diagnostics::RemoteAggregatorManager::RefreshAndCopyActiveForwarders(this, v32);
    std::unique_lock<std::recursive_mutex>::unlock(v33);
    ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::ScenarioManager::NotifyNewRemoteForwarders(ScenarioManager, v32);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>>>(
      v32,
      v32);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v33);
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  wcscpy(CommandLine, L"AggregatorHostexe");
  CurrentProcess = GetCurrentProcess();
  v7 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v6, CurrentProcess, 0x100000u);
  v32[0] = v7;
  v9 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v8, *((void **)this + 143), 0);
  v33[0] = v9;
  v30 = Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(v10, *((void **)this + 144), 0);
  v35[0] = 0;
  v35[1] = v7;
  v35[2] = v9;
  v35[3] = v30;
  v35[4] = *((_QWORD *)Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
           + 1);
  ResetEvent(*((HANDLE *)this + 143));
  ResetEvent(*((HANDLE *)this + 144));
  _InterlockedIncrement((volatile signed __int32 *)this + 424);
  std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1968));
  ++*((_DWORD *)this + 522);
  _Mtx_unlock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1968));
  v11 = (HANDLE *)((char *)this + 1160);
  v12 = (void *)*((_QWORD *)this + 145);
  if ( !v12 || Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(v12, 0) )
  {
    StartupInfo.lpReserved2 = (LPBYTE)v35;
    StartupInfo.cbReserved2 = 40;
    if ( !CreateProcessW(0, CommandLine, 0, 0, 1, 0x408u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        v14);
      LOBYTE(v23) = 0;
      LOBYTE(v24) = 0;
      v31[0] = L"RemoteAggregatorManager_CreateProcessFailed_0";
      v31[1] = std::_WChar_traits<wchar_t>::length(L"RemoteAggregatorManager_CreateProcessFailed_0", v23, v25, v24);
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v37,
        (unsigned int)v31,
        0x1000000,
        0,
        v27,
        v26,
        v26);
      LODWORD(v31[0]) = GetLastError();
      *(_QWORD *)&v29 = L"TerminateProcessError";
      *((_QWORD *)&v29 + 1) = std::_WChar_traits<wchar_t>::length(L"TerminateProcessError");
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v37, v38, &v29, v31);
      v29 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v31, &v29);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v37);
      SetEvent(*((HANDLE *)this + 144));
      Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v37);
      goto LABEL_28;
    }
    CloseHandle(ProcessInformation.hThread);
    std::_Mutex_base::lock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1168));
    v15 = (struct _TP_WAIT *)*((_QWORD *)this + 156);
    if ( v15 )
      SetThreadpoolWait(v15, ProcessInformation.hProcess, 0);
    _Mtx_unlock((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1168));
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 1160,
      ProcessInformation.hProcess);
    v31[0] = 0;
    v29 = *(_OWORD *)&off_180370800;
    Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( Key < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        (const char *)(unsigned int)Key,
        bInheritHandles);
    ProcessId = GetProcessId(*v11);
    v29 = *(_OWORD *)&off_180385038;
    Microsoft::Diagnostics::Utils::Registry::SetDword(v31[0], &v29, ProcessId);
    v29 = *(_OWORD *)&off_180385048;
    Microsoft::Diagnostics::Utils::Registry::SetDword(v31[0], &v29, MEMORY[0x7FFE02C4]);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v31);
    v29 = *(_OWORD *)&off_180385028;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v29) || IsDebuggerPresent() )
      v18 = -1;
    else
      v18 = 300000;
    Handles[0] = *((HANDLE *)this + 143);
    Handles[1] = *((HANDLE *)this + 144);
    Handles[2] = *v11;
    v19 = WaitForMultipleObjects(3u, Handles, 0, v18);
    if ( !v19 )
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::UpdateChildProcessReady(this, 1);
      if ( *((_QWORD *)this + 240) != *((_QWORD *)this + 241) )
        Microsoft::Diagnostics::RemoteAggregatorManager::ArmFlushTimer(this);
      goto LABEL_28;
    }
    v21 = v19 - 1;
    if ( !v21 || (v22 = v21 - 1) == 0 )
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
      goto LABEL_28;
    }
    if ( v22 != 256 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
        v20);
    v13 = 2;
  }
  else
  {
    v13 = 0;
  }
  Microsoft::Diagnostics::RemoteAggregatorManager::RestartChildProcess(this, v13);
LABEL_28:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v33);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v32);
}

```

## disassembly

```asm
0x18027ddd4  mov     [rsp-8+arg_8], rbx
0x18027ddd9  mov     [rsp-8+arg_10], rsi
0x18027ddde  push    rbp
0x18027dddf  push    rdi
0x18027dde0  push    r14
0x18027dde2  lea     rbp, [rsp-540h]
0x18027ddea  sub     rsp, 640h
0x18027ddf1  mov     rax, cs:__security_cookie
0x18027ddf8  xor     rax, rsp
0x18027ddfb  mov     [rbp+550h+var_20], rax
0x18027de02  mov     rsi, rcx
0x18027de05  lea     rbx, [rcx+728h]
0x18027de0c  mov     rcx, rbx; this
0x18027de0f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18027de14  mov     rcx, rbx; _Mtx_t
0x18027de17  cmp     byte ptr [rsi+778h], 0
0x18027de1e  jz      short loc_18027DE2B
0x18027de20  call    cs:__imp__Mtx_unlock
0x18027de26  jmp     loc_18027E326
0x18027de2b  call    cs:__imp__Mtx_unlock
0x18027de31  lea     r14, [rsi+6A0h]
0x18027de38  mov     edx, 5
0x18027de3d  mov     rcx, r14
0x18027de40  call    ?load@?$_Atomic_storage@K$03@std@@QEBAKW4memory_order@2@@Z; std::_Atomic_storage<ulong,4>::load(std::memory_order)
0x18027de45  test    eax, eax
0x18027de47  jz      loc_18027DED8
0x18027de4d  lea     rdx, [rsi+838h]
0x18027de54  lea     rcx, [rbp+550h+var_5C0]
0x18027de58  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18027de5d  nop
0x18027de5e  lea     rdi, [rsi+8C8h]
0x18027de65  mov     rbx, [rdi]
0x18027de68  mov     r8, [rbx+8]
0x18027de6c  mov     rdx, rdi
0x18027de6f  mov     rcx, rdi
0x18027de72  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UControlGroup@RemoteAggregatorManager@Diagnostics@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *>> &,std::_Tree_node<std::pair<std::string const,Microsoft::Diagnostics::RemoteAggregatorManager::ControlGroup>,void *> *)
0x18027de77  mov     [rbx+8], rbx
0x18027de7b  mov     [rbx], rbx
0x18027de7e  mov     [rbx+10h], rbx
0x18027de82  mov     qword ptr [rdi+8], 0
0x18027de8a  mov     rcx, rsi; this
0x18027de8d  call    ?DeserializeControlGroupsFromRegistry@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(void)
0x18027de92  lea     rdx, [rbp+550h+var_5D0]
0x18027de96  mov     rcx, rsi
0x18027de99  call    ?RefreshAndCopyActiveForwarders@RemoteAggregatorManager@Diagnostics@Microsoft@@QEAA?AVForwarderMap@23@XZ; Microsoft::Diagnostics::RemoteAggregatorManager::RefreshAndCopyActiveForwarders(void)
0x18027de9e  nop
0x18027de9f  lea     rcx, [rbp+550h+var_5C0]
0x18027dea3  call    ?unlock@?$unique_lock@Vrecursive_mutex@std@@@std@@QEAAXXZ; std::unique_lock<std::recursive_mutex>::unlock(void)
0x18027dea8  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18027deaf  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x18027deb4  lea     rdx, [rbp+550h+var_5D0]
0x18027deb8  mov     rcx, rax
0x18027debb  call    ?NotifyNewRemoteForwarders@ScenarioManager@Diagnostics@Microsoft@@QEAAX$$QEAVForwarderMap@23@@Z; Microsoft::Diagnostics::ScenarioManager::NotifyNewRemoteForwarders(Microsoft::Diagnostics::ForwarderMap &&)
0x18027dec0  nop
0x18027dec1  lea     rdx, [rbp+550h+var_5D0]
0x18027dec5  lea     rcx, [rbp+550h+var_5D0]
0x18027dec9  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>,void *>> &)
0x18027dece  nop
0x18027decf  lea     rcx, [rbp+550h+var_5C0]
0x18027ded3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18027ded8  xor     edx, edx; Val
0x18027deda  lea     r8d, [rdx+68h]; Size
0x18027dede  lea     rcx, [rbp+550h+StartupInfo]; void *
0x18027dee2  call    memset_0
0x18027dee7  xorps   xmm0, xmm0
0x18027deea  xor     eax, eax
0x18027deec  movups  xmmword ptr [rbp+550h+ProcessInformation.hProcess], xmm0
0x18027def0  mov     qword ptr [rbp+550h+ProcessInformation.dwProcessId], rax
0x18027def4  movups  xmm1, xmmword ptr cs:aAggregatorhost; "AggregatorHost.exe"
0x18027defb  movups  xmmword ptr [rbp+550h+CommandLine], xmm1
0x18027df02  movups  xmm0, xmmword ptr cs:aAggregatorhost+10h; "orHost.exe"
0x18027df09  movups  [rbp+550h+var_38], xmm0
0x18027df10  movsd   xmm1, qword ptr cs:aAggregatorhost+1Eh; "exe"
0x18027df18  movsd   qword ptr [rbp+550h+var_38+0Eh], xmm1
0x18027df20  call    cs:__imp_GetCurrentProcess
0x18027df26  mov     rdx, rax; void *
0x18027df29  mov     r8d, 100000h; unsigned int
0x18027df2f  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x18027df34  mov     rdi, rax
0x18027df37  mov     [rbp+550h+var_5D0], rax
0x18027df3b  xor     r8d, r8d; unsigned int
0x18027df3e  mov     rdx, [rsi+478h]; void *
0x18027df45  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x18027df4a  mov     rbx, rax
0x18027df4d  mov     [rbp+550h+var_5C0], rax
0x18027df51  xor     r8d, r8d; unsigned int
0x18027df54  mov     rdx, [rsi+480h]; void *
0x18027df5b  call    ?DuplicateInheritable@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAPEAXPEAXK@Z; Microsoft::Diagnostics::RemoteAggregatorManager::DuplicateInheritable(void *,ulong)
0x18027df60  mov     [rsp+650h+var_5F0], rax
0x18027df65  mov     [rbp+550h+var_598], 0
0x18027df6d  mov     [rbp+550h+var_590], rdi
0x18027df71  mov     [rbp+550h+var_588], rbx
0x18027df75  mov     [rbp+550h+var_580], rax
0x18027df79  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18027df80  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x18027df85  mov     rcx, [rax+8]
0x18027df89  mov     [rbp+550h+var_578], rcx
0x18027df8d  mov     rcx, [rsi+478h]; hEvent
0x18027df94  call    cs:__imp_ResetEvent
0x18027df9a  mov     rcx, [rsi+480h]; hEvent
0x18027dfa1  call    cs:__imp_ResetEvent
0x18027dfa7  lock inc dword ptr [r14]
0x18027dfab  lea     rbx, [rsi+7B0h]
0x18027dfb2  mov     rcx, rbx; this
0x18027dfb5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18027dfba  inc     dword ptr [rsi+828h]
0x18027dfc0  mov     rcx, rbx; _Mtx_t
0x18027dfc3  call    cs:__imp__Mtx_unlock
0x18027dfc9  lea     rdi, [rsi+488h]
0x18027dfd0  mov     rcx, [rdi]; void *
0x18027dfd3  test    rcx, rcx
0x18027dfd6  jz      short loc_18027DFF2
0x18027dfd8  xor     edx, edx; unsigned int
0x18027dfda  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x18027dfdf  test    al, al
0x18027dfe1  jnz     short loc_18027DFF2
0x18027dfe3  xor     edx, edx
0x18027dfe5  mov     rcx, rsi
0x18027dfe8  call    ?RestartChildProcess@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXVRestartChildProcessReason@EnumDetails@23@@Z; Microsoft::Diagnostics::RemoteAggregatorManager::RestartChildProcess(Microsoft::Diagnostics::EnumDetails::RestartChildProcessReason)
0x18027dfed  jmp     loc_18027E308
0x18027dff2  lea     rax, [rbp+550h+var_598]
0x18027dff6  mov     [rbp+550h+StartupInfo.lpReserved2], rax
0x18027dffa  mov     eax, 28h ; '('
0x18027dfff  mov     [rbp+550h+StartupInfo.cbReserved2], ax
0x18027e003  lea     rax, [rbp+550h+ProcessInformation]
0x18027e007  mov     [rsp+650h+lpProcessInformation], rax; lpProcessInformation
0x18027e00c  lea     rax, [rbp+550h+StartupInfo]
0x18027e010  mov     [rsp+650h+lpStartupInfo], rax; lpStartupInfo
0x18027e015  mov     [rsp+650h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18027e01e  mov     [rsp+650h+lpEnvironment], 0; lpEnvironment
0x18027e027  mov     [rsp+650h+dwCreationFlags], 408h; dwCreationFlags
0x18027e02f  mov     [rsp+650h+bInheritHandles], 1; bInheritHandles
0x18027e037  xor     r9d, r9d; lpThreadAttributes
0x18027e03a  xor     r8d, r8d; lpProcessAttributes
0x18027e03d  lea     rdx, [rbp+550h+CommandLine]; lpCommandLine
0x18027e044  xor     ecx, ecx; lpApplicationName
0x18027e046  call    cs:__imp_CreateProcessW
0x18027e04c  test    eax, eax
0x18027e04e  jz      loc_18027E22C
0x18027e054  mov     rcx, [rbp+550h+ProcessInformation.hThread]; hObject
0x18027e058  call    cs:__imp_CloseHandle
0x18027e05e  lea     rbx, [rsi+490h]
0x18027e065  mov     rcx, rbx; this
0x18027e068  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18027e06d  mov     rcx, [rsi+4E0h]; pwa
0x18027e074  test    rcx, rcx
0x18027e077  jz      short loc_18027E086
0x18027e079  xor     r8d, r8d; pftTimeout
0x18027e07c  mov     rdx, [rbp+550h+ProcessInformation.hProcess]; h
0x18027e080  call    cs:__imp_SetThreadpoolWait
0x18027e086  mov     rcx, rbx; _Mtx_t
0x18027e089  call    cs:__imp__Mtx_unlock
0x18027e08f  mov     rdx, [rbp+550h+ProcessInformation.hProcess]
0x18027e093  mov     rcx, rdi
0x18027e096  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18027e09b  mov     [rsp+650h+var_5E0], 0
0x18027e0a4  movups  xmm0, xmmword ptr cs:off_180370800; "%DiagtrackRegistryRoot%\\Aggregation"
0x18027e0ab  movdqu  [rsp+650h+var_600], xmm0
0x18027e0b1  mov     [rsp+650h+dwCreationFlags], 0; DWORD
0x18027e0b9  mov     [rsp+650h+bInheritHandles], 0F003Fh; int
0x18027e0c1  xor     r9d, r9d
0x18027e0c4  lea     r8, [rsp+650h+var_5E0]
0x18027e0c9  lea     rdx, [rsp+650h+var_600]
0x18027e0ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18027e0d5  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18027e0da  mov     rcx, [rbp+558h]; this
0x18027e0e1  test    eax, eax
0x18027e0e3  jns     short loc_18027E0FA
0x18027e0e5  mov     r9d, eax; char *
0x18027e0e8  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e0ef  mov     edx, 15Bh; void *
0x18027e0f4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18027e0fa  mov     rcx, [rdi]; Process
0x18027e0fd  call    cs:__imp_GetProcessId
0x18027e103  movups  xmm0, xmmword ptr cs:off_180385038; "LastRemoteProcessPid"
0x18027e10a  movdqu  [rsp+650h+var_600], xmm0
0x18027e110  mov     r8d, eax
0x18027e113  lea     rdx, [rsp+650h+var_600]
0x18027e118  mov     rcx, [rsp+650h+var_5E0]
0x18027e11d  call    ?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@K@Z; Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,ulong)
0x18027e122  movups  xmm0, xmmword ptr cs:off_180385048; "LastRemoteProcessEpoch"
0x18027e129  movdqu  [rsp+650h+var_600], xmm0
0x18027e12f  mov     r8d, ds:7FFE02C4h
0x18027e137  lea     rdx, [rsp+650h+var_600]
0x18027e13c  mov     rcx, [rsp+650h+var_5E0]
0x18027e141  call    ?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@K@Z; Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,ulong)
0x18027e146  nop
0x18027e147  lea     rcx, [rsp+650h+var_5E0]
0x18027e14c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18027e151  movups  xmm0, xmmword ptr cs:off_180385028; "DisableWatchdogs"
0x18027e158  movdqu  [rsp+650h+var_600], xmm0
0x18027e15e  lea     rcx, [rsp+650h+var_600]
0x18027e163  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x18027e168  test    al, al
0x18027e16a  jnz     short loc_18027E17E
0x18027e16c  call    cs:__imp_IsDebuggerPresent
0x18027e172  test    eax, eax
0x18027e174  jnz     short loc_18027E17E
0x18027e176  mov     r9d, 493E0h
0x18027e17c  jmp     short loc_18027E182
0x18027e17e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18027e182  mov     rax, [rsi+478h]
0x18027e189  mov     [rbp+550h+Handles], rax
0x18027e190  mov     rax, [rsi+480h]
0x18027e197  mov     [rbp+550h+var_58], rax
0x18027e19e  mov     rax, [rdi]
0x18027e1a1  mov     [rbp+550h+var_50], rax
0x18027e1a8  xor     r8d, r8d; bWaitAll
0x18027e1ab  lea     rdx, [rbp+550h+Handles]; lpHandles
0x18027e1b2  lea     ecx, [r8+3]; nCount
0x18027e1b6  call    cs:__imp_WaitForMultipleObjects
0x18027e1bc  test    eax, eax
0x18027e1be  jz      short loc_18027E201
0x18027e1c0  sub     eax, 1
0x18027e1c3  jz      short loc_18027E1F4
0x18027e1c5  sub     eax, 1
0x18027e1c8  jz      short loc_18027E1F4
0x18027e1ca  cmp     eax, 100h
0x18027e1cf  jz      short loc_18027E1EA
0x18027e1d1  mov     rcx, [rbp+558h]; this
0x18027e1d8  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e1df  mov     edx, 17Fh; void *
0x18027e1e4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18027e1ea  mov     edx, 2
0x18027e1ef  jmp     loc_18027DFE5
0x18027e1f4  mov     rcx, rsi; this
0x18027e1f7  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x18027e1fc  jmp     loc_18027E308
0x18027e201  mov     dl, 1; bool
0x18027e203  mov     rcx, rsi; this
0x18027e206  call    ?UpdateChildProcessReady@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::RemoteAggregatorManager::UpdateChildProcessReady(bool)
0x18027e20b  mov     rax, [rsi+788h]
0x18027e212  cmp     [rsi+780h], rax
0x18027e219  jz      loc_18027E308
0x18027e21f  mov     rcx, rsi; this
0x18027e222  call    ?ArmFlushTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmFlushTimer(void)
0x18027e227  jmp     loc_18027E308
0x18027e22c  mov     rcx, [rbp+558h]; this
0x18027e233  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e23a  mov     edx, 14Bh; void *
0x18027e23f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18027e244  xor     dl, dl
0x18027e246  xor     r9b, r9b
0x18027e249  lea     rcx, aRemoteaggregat; "RemoteAggregatorManager_CreateProcessFa"...
0x18027e250  mov     [rsp+650h+var_5E0], rcx
0x18027e255  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18027e25a  mov     [rsp+650h+var_5D8], rax
0x18027e25f  mov     r8d, 1000000h
0x18027e265  mov     byte ptr [rsp+650h+lpEnvironment], dl
0x18027e269  mov     byte ptr [rsp+650h+dwCreationFlags], dl
0x18027e26d  mov     byte ptr [rsp+650h+bInheritHandles], r9b
0x18027e272  mov     r9, 400000000000h
0x18027e27c  lea     rdx, [rsp+650h+var_5E0]
0x18027e281  lea     rcx, [rbp+550h+var_500]
0x18027e285  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x18027e28a  nop
0x18027e28b  call    cs:__imp_GetLastError
0x18027e291  mov     dword ptr [rsp+650h+var_5E0], eax
0x18027e295  lea     rcx, aTerminateproce; "TerminateProcessError"
0x18027e29c  mov     qword ptr [rsp+650h+var_600], rcx
0x18027e2a1  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18027e2a6  mov     qword ptr [rsp+650h+var_600+8], rax
0x18027e2ab  lea     r9, [rsp+650h+var_5E0]
0x18027e2b0  lea     r8, [rsp+650h+var_600]
0x18027e2b5  lea     rdx, [rbp+550h+var_98]
0x18027e2bc  lea     rcx, [rbp+550h+var_500]
0x18027e2c0  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x18027e2c5  xorps   xmm0, xmm0
0x18027e2c8  movdqa  [rsp+650h+var_600], xmm0
0x18027e2ce  lea     rdx, [rsp+650h+var_600]
0x18027e2d3  lea     rcx, [rsp+650h+var_5E0]
0x18027e2d8  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x18027e2dd  mov     edx, [rax]
0x18027e2df  lea     rcx, [rbp+550h+var_500]; this
0x18027e2e3  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x18027e2e8  mov     rcx, [rsi+480h]; hEvent
0x18027e2ef  call    cs:__imp_SetEvent
0x18027e2f5  mov     rcx, rsi; this
0x18027e2f8  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x18027e2fd  nop
0x18027e2fe  lea     rcx, [rbp+550h+var_500]; this
0x18027e302  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18027e307  nop
0x18027e308  lea     rcx, [rsp+650h+var_5F0]
0x18027e30d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18027e312  nop
0x18027e313  lea     rcx, [rbp+550h+var_5C0]
0x18027e317  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18027e31c  nop
0x18027e31d  lea     rcx, [rbp+550h+var_5D0]
0x18027e321  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18027e326  mov     rcx, [rbp+550h+var_20]
0x18027e32d  xor     rcx, rsp; StackCookie
0x18027e330  call    __security_check_cookie
0x18027e335  lea     r11, [rsp+650h+var_10]
0x18027e33d  mov     rbx, [r11+28h]
0x18027e341  mov     rsi, [r11+30h]
0x18027e345  mov     rsp, r11
0x18027e348  pop     r14
0x18027e34a  pop     rdi
  ... truncated ...
```
