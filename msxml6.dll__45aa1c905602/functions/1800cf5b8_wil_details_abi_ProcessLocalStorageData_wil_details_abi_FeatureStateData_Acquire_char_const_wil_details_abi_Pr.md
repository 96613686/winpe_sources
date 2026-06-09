# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800cf5b8`
- end: `0x1800cf724`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800cf98c`

## callees

- `0x1800cb6e0`
- `0x1800cc51c`
- `0x1800cc6c0`
- `0x1800cf2a0`
- `0x1800cf2c0`
- `0x1800cf5b8`
- `0x1800d0df4`
- `0x1800d19ec`
- `0x1800d2140`
- `0x1800d29c4`
- `0x1800d2b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cf63b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cf63b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cf5f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cf5f0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  unsigned int *v5; // r8
  unsigned int v6; // r9d
  unsigned int LastErrorFailHr; // ebx
  HRESULT v8; // eax
  const char *v9; // r8
  unsigned int v10; // edx
  _DWORD *v11; // rcx
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [rsp+30h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > lock; // [rsp+38h] [rbp-C8h] BYREF
  void *pointer; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t name[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  *data = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  mutex.m_ptr = 0;
  v4 = CreateMutexExW(0, name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &mutex,
    v4);
  if ( mutex.m_ptr )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &mutex,
      &lock,
      v5,
      v6,
      304);
    pointer = 0;
    v8 = wil::details_abi::SemaphoreValue::TryGetPointer(name, &pointer);
    LastErrorFailHr = v8;
    if ( v8 < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, v10, v9, v8);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
      goto LABEL_9;
    }
    v11 = pointer;
    if ( pointer )
    {
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> *)pointer;
      ++*v11;
    }
    else
    {
      v8 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
             name,
             &mutex,
             data);
      LastErrorFailHr = v8;
      if ( v8 < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr();
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&mutex);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800cf5b8  mov     [rsp-8+arg_10], rbx
0x1800cf5bd  mov     [rsp-8+arg_18], rdi
0x1800cf5c2  push    rbp
0x1800cf5c3  lea     rbp, [rsp-170h]
0x1800cf5cb  sub     rsp, 270h
0x1800cf5d2  mov     rax, cs:__security_cookie
0x1800cf5d9  xor     rax, rsp
0x1800cf5dc  mov     [rbp+170h+var_10], rax
0x1800cf5e3  mov     rdi, data
0x1800cf5e6  mov     qword ptr [data], 0
0x1800cf5ed  mov     rbx, staticNameWithVersion
0x1800cf5f0  call    cs:__imp_GetCurrentProcessId
0x1800cf5f7  nop     dword ptr [rax+rax+00h]
0x1800cf5fc  mov     [rsp+270h+var_248], rbx
0x1800cf601  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800cf608  mov     r9d, eax
0x1800cf60b  mov     [rsp+270h+bAlertable], 130h; bAlertable
0x1800cf613  mov     edx, 104h; cchDest
0x1800cf618  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x1800cf61d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cf622  mov     r9d, 1F0001h; dwDesiredAccess
0x1800cf628  mov     [rsp+270h+mutex.m_ptr], 0
0x1800cf631  xor     r8d, r8d; dwFlags
0x1800cf634  lea     data, [rsp+270h+name]; lpName
0x1800cf639  xor     ecx, ecx; lpMutexAttributes
0x1800cf63b  call    cs:__imp_CreateMutexExW
0x1800cf642  nop     dword ptr [rax+rax+00h]
0x1800cf647  mov     data, rax; ptr
0x1800cf64a  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cf64f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800cf654  cmp     [rsp+270h+mutex.m_ptr], 0
0x1800cf65a  jnz     short loc_1800CF665
0x1800cf65c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800cf661  mov     ebx, eax
0x1800cf663  jmp     short loc_1800CF6D1
0x1800cf665  lea     data, [rsp+270h+lock]; result
0x1800cf66a  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cf66f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800cf674  lea     data, [rsp+270h+pointer]; pointer
0x1800cf679  mov     [rsp+270h+pointer], 0
0x1800cf682  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cf687  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800cf68c  mov     ebx, eax
0x1800cf68e  test    eax, eax
0x1800cf690  jns     short loc_1800CF6B2
0x1800cf692  mov     edx, 12Eh; lineNumber
0x1800cf697  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x1800cf69e  mov     r9d, eax; callerReturnAddress
0x1800cf6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf6a6  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cf6ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cf6b0  jmp     short loc_1800CF6D1
0x1800cf6b2  mov     staticNameWithVersion, [rsp+270h+pointer]
0x1800cf6b7  test    staticNameWithVersion, staticNameWithVersion
0x1800cf6ba  jz      short loc_1800CF702
0x1800cf6bc  mov     [rdi], staticNameWithVersion
0x1800cf6bf  mov     eax, [staticNameWithVersion]
0x1800cf6c1  inc     eax
0x1800cf6c3  mov     [staticNameWithVersion], eax
0x1800cf6c5  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cf6ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cf6cf  xor     ebx, ebx
0x1800cf6d1  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cf6d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cf6db  mov     eax, ebx
0x1800cf6dd  mov     staticNameWithVersion, [rbp+170h+var_10]
0x1800cf6e4  xor     staticNameWithVersion, rsp; StackCookie
0x1800cf6e7  call    __security_check_cookie
0x1800cf6ec  lea     r11, [rsp+270h+var_s0]
0x1800cf6f4  mov     rbx, [r11+20h]
0x1800cf6f8  mov     rdi, [r11+28h]
0x1800cf6fc  mov     rsp, r11
0x1800cf6ff  pop     rbp
0x1800cf700  retn
0x1800cf702  mov     r8, rdi; data
0x1800cf705  lea     data, [rsp+270h+mutex]; mutex
0x1800cf70a  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cf70f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800cf714  mov     ebx, eax
0x1800cf716  test    eax, eax
0x1800cf718  jns     short loc_1800CF6C5
0x1800cf71a  mov     edx, 137h
0x1800cf71f  jmp     loc_1800CF697
```
