# Microsoft::Diagnostics::GetKernelDumpActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x18032cdf0`
- end: `0x18032d75b`
- name: `?Execute@GetKernelDumpActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `2411`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001ef98`
- `0x180020150`
- `0x180021538`
- `0x180025430`
- `0x180027c28`
- `0x180027e50`
- `0x180028ba8`
- `0x18002b7c0`
- `0x18002df00`
- `0x180031168`
- `0x180052240`
- `0x180055730`
- `0x180064e8c`
- `0x18009c8c0`
- `0x1800bc658`
- `0x1800c4b14`
- `0x1800d11c0`
- `0x1800e99a0`
- `0x1800f85ac`
- `0x180108548`
- `0x180138608`
- `0x180142fcc`
- `0x1801c2380`
- `0x1801d2b8c`
- `0x1801dc068`
- `0x18020aac0`
- `0x18020bab8`
- `0x18032cdf0`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18032d05b`
- `msvcp_win!_Mtx_unlock` at `0x18032d174`
- `msvcp_win!_Mtx_unlock` at `0x18032d1b4`
- `msvcp_win!_Mtx_unlock` at `0x18032d2f9`
- `msvcp_win!_Mtx_unlock` at `0x18032d36b`
- `msvcp_win!_Mtx_unlock` at `0x18032d47c`
- `msvcp_win!_Mtx_unlock` at `0x18032d513`
- `msvcp_win!_Mtx_unlock` at `0x18032d54b`
- `msvcp_win!_Mtx_unlock` at `0x18032d05b`
- `msvcp_win!_Mtx_unlock` at `0x18032d174`
- `msvcp_win!_Mtx_unlock` at `0x18032d1b4`
- `msvcp_win!_Mtx_unlock` at `0x18032d2f9`
- `msvcp_win!_Mtx_unlock` at `0x18032d36b`
- `msvcp_win!_Mtx_unlock` at `0x18032d47c`
- `msvcp_win!_Mtx_unlock` at `0x18032d513`
- `msvcp_win!_Mtx_unlock` at `0x18032d54b`
- `ntdll!NtSystemDebugControl` at `0x18032d3ae`
- `ntdll!NtSystemDebugControl` at `0x18032d3ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18032ceec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18032ceec`

## string_xrefs

- `0x18032ce37`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032ce8c`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d046`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d154`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d2e0`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d34b`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d458`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d4ef`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`
- `0x18032d6ca`: `onecore\base\telemetry\utc\service\scenarios\actions\getkerneldumpaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetKernelDumpActionDef::Execute(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int appended; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // rcx
  unsigned __int64 FileTimeAsULL; // r15
  _QWORD *ScenarioDef; // rax
  __int16 v13; // bx
  unsigned int Qword; // ebx
  unsigned __int64 v15; // rdi
  int v16; // r8d
  int v17; // r9d
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // r8d
  int v21; // r9d
  int updated; // eax
  unsigned int v23; // ebx
  NTSTATUS v24; // edi
  _QWORD *v25; // rax
  __int16 v26; // bx
  int v27; // r9d
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  void *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-128h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-128h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-128h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-128h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-128h]
  int v43[4]; // [rsp+40h] [rbp-108h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-F8h] BYREF
  std::_Ref_count_base *v45[2]; // [rsp+60h] [rbp-E8h] BYREF
  void *TokenHandle[2]; // [rsp+70h] [rbp-D8h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+88h] [rbp-C0h] BYREF
  _DWORD InputBuffer[10]; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-90h]
  __int64 v51; // [rsp+C0h] [rbp-88h]
  int v52; // [rsp+C8h] [rbp-80h]
  int v53; // [rsp+CCh] [rbp-7Ch]
  __int64 *v54; // [rsp+E0h] [rbp-68h]
  LPCWSTR lpFileName[4]; // [rsp+E8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)0x8007010BLL,
      dwCreationDisposition);
    return 2147942667LL;
  }
  std::wstring::wstring((__int64)lpFileName, a2);
  *(_OWORD *)TokenHandle = *(_OWORD *)&Microsoft::Diagnostics::GetKernelDumpActionDef::k_kernelDumpFileName;
  appended = Microsoft::Diagnostics::Utils::String::AppendPath(lpFileName, TokenHandle);
  v9 = appended;
  if ( appended < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    std::wstring::_Tidy_deallocate(lpFileName);
    return v9;
  }
  v10 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v10 = lpFileName[0];
  v44[0] = CreateFileW(v10, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  memset_0(InputBuffer, 0, 0x48u);
  InputBuffer[0] = 1;
  v52 = *(_BYTE *)(a1 + 128) == 0 ? 8 : 0;
  v50 = v44[0];
  v51 = 0;
  *(_OWORD *)TokenHandle = *(_OWORD *)&off_18038C510;
  if ( Microsoft::Diagnostics::Utils::General::IsTestHookEnabled((__int128 *)TokenHandle) )
    v52 &= ~8u;
  if ( Microsoft::Diagnostics::Utils::Os::GetTotalPhysicalMemoryInBytes() <= 0x800000000LL )
    v53 |= 1u;
  v54 = Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex;
  std::_Mutex_base::lock((std::_Mutex_base *)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  v47 = 0;
  v48 = 0;
  ScenarioDef = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a4, v45);
  v13 = *(_WORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*ScenarioDef + 80LL))(*ScenarioDef, v43);
  if ( v45[1] )
    std::_Ref_count_base::_Decref(v45[1]);
  if ( v13 == 1 )
    goto LABEL_30;
  *(_OWORD *)v45 = *(_OWORD *)&off_18038C4F0;
  *(_OWORD *)v43 = *(_OWORD *)&off_18038C4E0;
  Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v43, v45, &v48);
  if ( (int)(Qword + 0x80000000) >= 0 && Qword != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)Qword,
      dwCreationDispositiona);
    _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
    std::wstring::_Tidy_deallocate(lpFileName);
    return Qword;
  }
  v15 = FileTimeAsULL - v48;
  if ( FileTimeAsULL - v48 > FileTimeAsULL )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
    {
      *(_QWORD *)v43 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&unk_1804033F8,
        v16,
        v17,
        (__int64)v43);
    }
    *(_OWORD *)v45 = *(_OWORD *)&off_18038C4F0;
    *(_OWORD *)v43 = *(_OWORD *)&off_18038C4E0;
    v18 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, FileTimeAsULL, 0);
    v19 = v18;
    if ( v18 >= 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)0x87C51041LL,
        dwCreationDispositionb);
      _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      std::wstring::_Tidy_deallocate(lpFileName);
      return 2277838913LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositionb);
      _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v19;
    }
  }
  if ( v15 > 0xC92A69C000LL
    || (*(_OWORD *)v45 = *(_OWORD *)&off_18038C500,
        *(_OWORD *)v43 = *(_OWORD *)&off_18038C4E0,
        Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v43, v45, &v47),
        v47 < 5) )
  {
LABEL_30:
    TokenHandle[0] = 0;
    LOBYTE(TokenHandle[1]) = 0;
    updated = Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(TokenHandle);
    v23 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)updated,
        dwCreationDispositiona);
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v23;
    }
    v24 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
    v25 = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a4, v45);
    v26 = *(_WORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v25 + 80LL))(*v25, v43);
    if ( v45[1] )
      std::_Ref_count_base::_Decref(v45[1]);
    if ( v26 == 1 )
      goto LABEL_42;
    v27 = v47;
    if ( !v47 || !v48 )
    {
      *(_OWORD *)v45 = *(_OWORD *)&off_18038C4F0;
      *(_OWORD *)v43 = *(_OWORD *)&off_18038C4E0;
      v28 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, FileTimeAsULL, 0);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
          (const char *)(unsigned int)v28,
          dwCreationDispositiond);
        Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
        _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
        std::wstring::_Tidy_deallocate(lpFileName);
        return v29;
      }
      v27 = v47;
    }
    *(_OWORD *)v45 = *(_OWORD *)&off_18038C500;
    *(_OWORD *)v43 = *(_OWORD *)&off_18038C4E0;
    v30 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v43, (int)v45, v27 + 1, 0);
    v31 = v30;
    if ( v30 >= 0 )
    {
LABEL_42:
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      v32 = (void *)(a3 + 168);
      if ( v24 < 0 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<(v32);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        {
          v43[0] = v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)byte_180403331,
            v35,
            v36,
            (__int64)v43);
        }
        if ( v24 == -1073741248 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
            (const char *)0x87C52307LL,
            dwCreationDispositionc);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
          std::wstring::_Tidy_deallocate(lpFileName);
          return 2277843719LL;
        }
        else
        {
          v37 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xCE,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
                  (const char *)(unsigned int)v24,
                  dwCreationDispositionc);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
          std::wstring::_Tidy_deallocate(lpFileName);
          return v37;
        }
      }
      else
      {
        Microsoft::Diagnostics::WideStringStream::operator<<(v32);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        *(_OWORD *)v45 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, TokenHandle);
        Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a3 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        *(_OWORD *)v45 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, TokenHandle);
        Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a3, v45);
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        {
          v43[0] = v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)byte_1804033BD,
            v33,
            v34,
            (__int64)v43);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
        std::wstring::_Tidy_deallocate(lpFileName);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
        (const char *)(unsigned int)v30,
        dwCreationDispositionc);
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)TokenHandle);
      _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v31;
    }
  }
  else
  {
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
    {
      *(_QWORD *)v43 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)byte_180403369,
        v20,
        v21,
        (__int64)v43);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getkerneldumpaction.cpp",
      (const char *)0x87C51041LL,
      dwCreationDispositiona);
    _Mtx_unlock((_Mtx_t)Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
    std::wstring::_Tidy_deallocate(lpFileName);
    return 2277838913LL;
  }
}

```

## disassembly

```asm
0x18032cdf0  push    rbx
0x18032cdf2  push    rsi
0x18032cdf3  push    rdi
0x18032cdf4  push    r12
0x18032cdf6  push    r13
0x18032cdf8  push    r14
0x18032cdfa  push    r15
0x18032cdfc  sub     rsp, 110h
0x18032ce03  mov     rax, cs:__security_cookie
0x18032ce0a  xor     rax, rsp
0x18032ce0d  mov     [rsp+148h+var_40], rax
0x18032ce15  mov     r12, r9
0x18032ce18  mov     r14, r8
0x18032ce1b  mov     rdi, rcx
0x18032ce1e  xor     r13d, r13d
0x18032ce21  cmp     [rdx+8], r13
0x18032ce25  jnz     short loc_18032CE4E
0x18032ce27  mov     rcx, [rsp+148h]; this
0x18032ce2f  mov     ebx, 8007010Bh
0x18032ce34  mov     r9d, ebx; char *
0x18032ce37  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032ce3e  lea     edx, [r13+1Eh]; void *
0x18032ce42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032ce47  mov     eax, ebx
0x18032ce49  jmp     loc_18032D737
0x18032ce4e  lea     rcx, [rsp+148h+lpFileName]
0x18032ce56  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18032ce5b  nop
0x18032ce5c  movups  xmm0, xmmword ptr cs:?k_kernelDumpFileName@GetKernelDumpActionDef@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::GetKernelDumpActionDef::k_kernelDumpFileName
0x18032ce63  movdqu  xmmword ptr [rsp+148h+TokenHandle], xmm0
0x18032ce69  lea     rdx, [rsp+148h+TokenHandle]
0x18032ce6e  lea     rcx, [rsp+148h+lpFileName]
0x18032ce76  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18032ce7b  mov     ebx, eax
0x18032ce7d  test    eax, eax
0x18032ce7f  jns     short loc_18032CEB2
0x18032ce81  mov     rcx, [rsp+148h]; this
0x18032ce89  mov     r9d, eax; char *
0x18032ce8c  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032ce93  mov     edx, 20h ; ' '; void *
0x18032ce98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032ce9d  nop
0x18032ce9e  lea     rcx, [rsp+148h+lpFileName]
0x18032cea6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032ceab  mov     eax, ebx
0x18032cead  jmp     loc_18032D737
0x18032ceb2  lea     rcx, [rsp+148h+lpFileName]
0x18032ceba  cmp     [rsp+148h+var_48], 7
0x18032cec3  cmova   rcx, [rsp+148h+lpFileName]; lpFileName
0x18032cecc  mov     [rsp+148h+hTemplateFile], r13; hTemplateFile
0x18032ced1  mov     [rsp+148h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18032ced9  mov     [rsp+148h+dwCreationDisposition], 2; int
0x18032cee1  xor     r9d, r9d; lpSecurityAttributes
0x18032cee4  xor     r8d, r8d; dwShareMode
0x18032cee7  mov     edx, 0C0000000h; dwDesiredAccess
0x18032ceec  call    cs:__imp_CreateFileW
0x18032cef2  mov     rbx, rax
0x18032cef5  mov     [rsp+148h+var_F8], rax
0x18032cefa  xor     edx, edx; Val
0x18032cefc  lea     r8d, [rdx+48h]; Size
0x18032cf00  lea     rcx, [rsp+148h+InputBuffer]; void *
0x18032cf08  call    memset_0
0x18032cf0d  mov     esi, 1
0x18032cf12  mov     [rsp+148h+InputBuffer], esi
0x18032cf19  mov     al, [rdi+80h]
0x18032cf1f  neg     al
0x18032cf21  sbb     ecx, ecx
0x18032cf23  not     ecx
0x18032cf25  and     ecx, 8
0x18032cf28  mov     [rsp+148h+var_80], ecx
0x18032cf2f  mov     [rsp+148h+var_90], rbx
0x18032cf37  mov     [rsp+148h+var_88], r13
0x18032cf3f  movups  xmm0, xmmword ptr cs:off_18038C510; "CollectKernelDumpsUnderMemoryPressure"
0x18032cf46  movdqu  xmmword ptr [rsp+148h+TokenHandle], xmm0
0x18032cf4c  lea     rcx, [rsp+148h+TokenHandle]
0x18032cf51  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x18032cf56  test    al, al
0x18032cf58  jz      short loc_18032CF62
0x18032cf5a  and     [rsp+148h+var_80], 0FFFFFFF7h
0x18032cf62  call    ?GetTotalPhysicalMemoryInBytes@Os@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Os::GetTotalPhysicalMemoryInBytes(void)
0x18032cf67  mov     rcx, 800000000h
0x18032cf71  cmp     rax, rcx
0x18032cf74  ja      short loc_18032CF7D
0x18032cf76  or      [rsp+148h+var_7C], esi
0x18032cf7d  lea     rdi, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; std::recursive_mutex Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex
0x18032cf84  mov     [rsp+148h+var_68], rdi
0x18032cf8c  mov     rcx, rdi; this
0x18032cf8f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18032cf94  nop
0x18032cf95  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18032cf9a  mov     r15, rax
0x18032cf9d  mov     [rsp+148h+var_C8], r13
0x18032cfa5  mov     [rsp+148h+var_C0], r13
0x18032cfad  lea     rdx, [rsp+148h+var_E8]
0x18032cfb2  mov     rcx, r12
0x18032cfb5  call    ?GetScenarioDef@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(void)
0x18032cfba  nop
0x18032cfbb  mov     rcx, [rax]
0x18032cfbe  mov     rdx, [rcx]
0x18032cfc1  mov     rax, [rdx+50h]
0x18032cfc5  lea     rdx, [rsp+148h+var_108]
0x18032cfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032cfcf  movzx   ebx, word ptr [rax]
0x18032cfd2  mov     rcx, [rsp+148h+var_E8+8]; this
0x18032cfd7  test    rcx, rcx
0x18032cfda  jz      short loc_18032CFE1
0x18032cfdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18032cfe1  cmp     bx, si
0x18032cfe4  mov     rsi, 0FFFFFFFF80000002h
0x18032cfeb  jz      loc_18032D326
0x18032cff1  movups  xmm0, xmmword ptr cs:off_18038C4F0; "FirstKernelDumpTime"
0x18032cff8  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x18032cffe  movups  xmm1, xmmword ptr cs:off_18038C4E0; "%DiagtrackRegistryRoot%\\Scenarios"
0x18032d005  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x18032d00b  lea     r9, [rsp+148h+var_C0]
0x18032d013  lea     r8, [rsp+148h+var_E8]
0x18032d018  lea     rdx, [rsp+148h+var_108]
0x18032d01d  mov     rcx, rsi
0x18032d020  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x18032d025  mov     ebx, eax
0x18032d027  mov     eax, 80000000h
0x18032d02c  lea     edx, [rbx+rax]; unsigned int
0x18032d02f  test    eax, edx
0x18032d031  jnz     short loc_18032D081
0x18032d033  cmp     ebx, 80070002h
0x18032d039  jz      short loc_18032D081
0x18032d03b  mov     rcx, [rsp+148h]; this
0x18032d043  mov     r9d, ebx; char *
0x18032d046  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032d04d  mov     edx, 55h ; 'U'; void *
0x18032d052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d057  nop
0x18032d058  mov     rcx, rdi; _Mtx_t
0x18032d05b  call    cs:__imp__Mtx_unlock
0x18032d061  nop
0x18032d062  lea     rcx, [rsp+148h+var_F8]
0x18032d067  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18032d06c  nop
0x18032d06d  lea     rcx, [rsp+148h+lpFileName]
0x18032d075  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032d07a  mov     eax, ebx
0x18032d07c  jmp     loc_18032D737
0x18032d081  mov     rdi, r15
0x18032d084  sub     rdi, [rsp+148h+var_C0]
0x18032d08c  cmp     rdi, r15
0x18032d08f  jbe     loc_18032D1DA
0x18032d095  lea     rbx, [r14+0A8h]
0x18032d09c  lea     rdx, aTimeIntervalCh; "Time interval check produced an underfl"...
0x18032d0a3  mov     rcx, rbx; Src
0x18032d0a6  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d0ab  lea     rdx, aFiletimeInterv; "Filetime interval: "
0x18032d0b2  mov     rcx, rbx; Src
0x18032d0b5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d0ba  mov     rdx, rdi
0x18032d0bd  mov     rcx, rbx; Src
0x18032d0c0  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x18032d0c5  lea     rdx, asc_1803A0C7C; "\r\n"
0x18032d0cc  mov     rcx, rbx; Src
0x18032d0cf  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d0d4  mov     eax, cs:dword_1804543B0
0x18032d0da  cmp     eax, 2
0x18032d0dd  jbe     short loc_18032D116
0x18032d0df  mov     edx, 4
0x18032d0e4  lea     rcx, dword_1804543B0
0x18032d0eb  call    _tlgKeywordOn
0x18032d0f0  test    al, al
0x18032d0f2  jz      short loc_18032D116
0x18032d0f4  mov     qword ptr [rsp+148h+var_108], rdi
0x18032d0f9  lea     rax, [rsp+148h+var_108]
0x18032d0fe  mov     qword ptr [rsp+148h+dwCreationDisposition], rax
0x18032d103  lea     rdx, unk_1804033F8
0x18032d10a  lea     rcx, dword_1804543B0
0x18032d111  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18032d116  movups  xmm0, xmmword ptr cs:off_18038C4F0; "FirstKernelDumpTime"
0x18032d11d  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x18032d123  movups  xmm1, xmmword ptr cs:off_18038C4E0; "%DiagtrackRegistryRoot%\\Scenarios"
0x18032d12a  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x18032d130  mov     [rsp+148h+dwCreationDisposition], r13d; int
0x18032d135  mov     r9, r15; int
0x18032d138  lea     r8, [rsp+148h+var_E8]; int
0x18032d13d  lea     rdx, [rsp+148h+var_108]; int
0x18032d142  mov     rcx, rsi; int
0x18032d145  call    ?SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z; Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)
0x18032d14a  mov     ebx, eax
0x18032d14c  mov     rcx, [rsp+148h]; this
0x18032d154  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032d15b  test    eax, eax
0x18032d15d  jns     short loc_18032D19A
0x18032d15f  mov     r9d, eax; char *
0x18032d162  mov     edx, 6Fh ; 'o'; void *
0x18032d167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d16c  nop
0x18032d16d  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x18032d174  call    cs:__imp__Mtx_unlock
0x18032d17a  nop
0x18032d17b  lea     rcx, [rsp+148h+var_F8]
0x18032d180  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18032d185  nop
0x18032d186  lea     rcx, [rsp+148h+lpFileName]
0x18032d18e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032d193  mov     eax, ebx
0x18032d195  jmp     loc_18032D737
0x18032d19a  mov     ebx, 87C51041h
0x18032d19f  mov     r9d, ebx; char *
0x18032d1a2  mov     edx, 71h ; 'q'; void *
0x18032d1a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d1ac  nop
0x18032d1ad  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x18032d1b4  call    cs:__imp__Mtx_unlock
0x18032d1ba  nop
0x18032d1bb  lea     rcx, [rsp+148h+var_F8]
0x18032d1c0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18032d1c5  nop
0x18032d1c6  lea     rcx, [rsp+148h+lpFileName]
0x18032d1ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032d1d3  mov     eax, ebx
0x18032d1d5  jmp     loc_18032D737
0x18032d1da  mov     rax, 0C92A69C000h
0x18032d1e4  cmp     rdi, rax
0x18032d1e7  ja      loc_18032D31F
0x18032d1ed  movups  xmm0, xmmword ptr cs:off_18038C500; "KernelDumpCounter"
0x18032d1f4  movdqu  xmmword ptr [rsp+148h+var_E8], xmm0
0x18032d1fa  movups  xmm1, xmmword ptr cs:off_18038C4E0; "%DiagtrackRegistryRoot%\\Scenarios"
0x18032d201  movdqu  xmmword ptr [rsp+148h+var_108], xmm1
0x18032d207  lea     r9, [rsp+148h+var_C8]
0x18032d20f  lea     r8, [rsp+148h+var_E8]
0x18032d214  lea     rdx, [rsp+148h+var_108]
0x18032d219  mov     rcx, rsi
0x18032d21c  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x18032d221  cmp     [rsp+148h+var_C8], 5
0x18032d22a  jb      loc_18032D31F
0x18032d230  lea     rbx, [r14+0A8h]
0x18032d237  lea     rdx, aMaximumKernelD; "Maximum kernel dump per 24 hours limit "...
0x18032d23e  mov     rcx, rbx; Src
0x18032d241  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d246  lea     rdx, aTimefromfirstd; "TimeFromFirstDump: "
0x18032d24d  mov     rcx, rbx; Src
0x18032d250  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d255  mov     rdx, rdi
0x18032d258  mov     rcx, rbx; Src
0x18032d25b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x18032d260  lea     rdx, aKerneldumpcoun; "KernelDumpCount: "
0x18032d267  mov     rcx, rbx; Src
0x18032d26a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d26f  mov     rdx, [rsp+148h+var_C8]
0x18032d277  mov     rcx, rbx; Src
0x18032d27a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x18032d27f  lea     rdx, asc_1803A0C7C; "\r\n"
0x18032d286  mov     rcx, rbx; Src
0x18032d289  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18032d28e  mov     eax, cs:dword_1804543B0
0x18032d294  cmp     eax, 2
0x18032d297  jbe     short loc_18032D2D0
0x18032d299  mov     edx, 4
0x18032d29e  lea     rcx, dword_1804543B0
0x18032d2a5  call    _tlgKeywordOn
0x18032d2aa  test    al, al
0x18032d2ac  jz      short loc_18032D2D0
0x18032d2ae  mov     qword ptr [rsp+148h+var_108], rdi
0x18032d2b3  lea     rax, [rsp+148h+var_108]
0x18032d2b8  mov     qword ptr [rsp+148h+dwCreationDisposition], rax; int
0x18032d2bd  lea     rdx, byte_180403369
0x18032d2c4  lea     rcx, dword_1804543B0
0x18032d2cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18032d2d0  mov     rcx, [rsp+148h]; this
0x18032d2d8  mov     ebx, 87C51041h
0x18032d2dd  mov     r9d, ebx; char *
0x18032d2e0  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032d2e7  mov     edx, 87h; void *
0x18032d2ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d2f1  nop
0x18032d2f2  lea     rcx, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; _Mtx_t
0x18032d2f9  call    cs:__imp__Mtx_unlock
0x18032d2ff  nop
0x18032d300  lea     rcx, [rsp+148h+var_F8]
0x18032d305  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18032d30a  nop
0x18032d30b  lea     rcx, [rsp+148h+lpFileName]
0x18032d313  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032d318  mov     eax, ebx
0x18032d31a  jmp     loc_18032D737
0x18032d31f  lea     rdi, ?m_kernelDumpMutex@GetKernelDumpActionDef@Diagnostics@Microsoft@@0Vrecursive_mutex@std@@A; std::recursive_mutex Microsoft::Diagnostics::GetKernelDumpActionDef::m_kernelDumpMutex
0x18032d326  mov     [rsp+148h+TokenHandle], r13
0x18032d32b  mov     byte ptr [rsp+148h+TokenHandle+8], r13b
0x18032d330  lea     rcx, [rsp+148h+TokenHandle]; TokenHandle
0x18032d335  call    ?UpdatePrivilege@ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAAJK_N@Z; Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(ulong,bool)
0x18032d33a  mov     ebx, eax
0x18032d33c  test    eax, eax
0x18032d33e  jns     short loc_18032D391
0x18032d340  mov     rcx, [rsp+148h]; this
0x18032d348  mov     r9d, eax; char *
0x18032d34b  lea     r8, aOnecoreBaseTel_67; "onecore\\base\\telemetry\\utc\\service"...
0x18032d352  mov     edx, 8Eh; void *
0x18032d357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032d35c  nop
0x18032d35d  lea     rcx, [rsp+148h+TokenHandle]; this
0x18032d362  call    ??1ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager(void)
0x18032d367  nop
0x18032d368  mov     rcx, rdi; _Mtx_t
0x18032d36b  call    cs:__imp__Mtx_unlock
  ... truncated ...
```
