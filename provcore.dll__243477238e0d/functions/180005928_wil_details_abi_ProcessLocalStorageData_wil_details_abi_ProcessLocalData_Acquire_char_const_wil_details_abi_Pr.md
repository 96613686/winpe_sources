# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005928`
- end: `0x180005a97`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006448`

## callees

- `0x180002790`
- `0x1800057c4`
- `0x1800057e0`
- `0x180005928`
- `0x1800061a8`
- `0x180006bc8`
- `0x1800071f4`
- `0x180007790`
- `0x180007918`
- `0x180007d14`
- `0x180007e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005960`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        const char *staticNameWithVersion,
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  unsigned int *v5; // r8
  unsigned int v6; // r9d
  unsigned int LastErrorFailHr; // ebx
  HRESULT v8; // eax
  unsigned int v9; // edx
  _DWORD *v10; // rcx
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > mutex; // [rsp+30h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > lock; // [rsp+38h] [rbp-C8h] BYREF
  void *pointer; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR name[264]; // [rsp+50h] [rbp-B0h] BYREF
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
    lock.m_ptr = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &mutex,
      &lock,
      v5,
      v6,
      120);
    pointer = 0;
    v8 = wil::details_abi::SemaphoreValue::TryGetPointer(name, &pointer);
    LastErrorFailHr = v8;
    if ( v8 < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, v9, "wil", v8);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&lock);
      goto LABEL_9;
    }
    v10 = pointer;
    if ( pointer )
    {
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *)pointer;
      ++*v10;
    }
    else
    {
      v8 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
             name,
             &mutex,
             data);
      LastErrorFailHr = v8;
      if ( v8 < 0 )
      {
        v9 = 311;
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
0x180005928  mov     [rsp-8+arg_10], rbx
0x18000592d  mov     [rsp-8+arg_18], rdi
0x180005932  push    rbp
0x180005933  lea     rbp, [rsp-170h]
0x18000593b  sub     rsp, 270h
0x180005942  mov     rax, cs:__security_cookie
0x180005949  xor     rax, rsp
0x18000594c  mov     [rbp+170h+var_10], rax
0x180005953  mov     rdi, data
0x180005956  mov     qword ptr [data], 0
0x18000595d  mov     rbx, staticNameWithVersion
0x180005960  call    cs:__imp_GetCurrentProcessId
0x180005966  mov     [rsp+270h+var_248], rbx
0x18000596b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005972  mov     r9d, eax
0x180005975  mov     [rsp+270h+bAlertable], 78h ; 'x'; bAlertable
0x18000597d  mov     edx, 104h; cchDest
0x180005982  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x180005987  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000598c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005992  mov     [rsp+270h+mutex.m_ptr], 0
0x18000599b  xor     r8d, r8d; dwFlags
0x18000599e  lea     data, [rsp+270h+name]; lpName
0x1800059a3  xor     ecx, ecx; lpMutexAttributes
0x1800059a5  call    cs:__imp_CreateMutexExW
0x1800059ab  mov     data, rax; ptr
0x1800059ae  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800059b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800059b8  cmp     [rsp+270h+mutex.m_ptr], 0
0x1800059be  jnz     short loc_1800059C9
0x1800059c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800059c5  mov     ebx, eax
0x1800059c7  jmp     short loc_180005A45
0x1800059c9  lea     data, [rsp+270h+lock]; result
0x1800059ce  mov     [rsp+270h+lock.m_ptr], 0
0x1800059d7  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800059dc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800059e1  lea     data, [rsp+270h+pointer]; pointer
0x1800059e6  mov     [rsp+270h+pointer], 0
0x1800059ef  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800059f4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800059f9  mov     ebx, eax
0x1800059fb  test    eax, eax
0x1800059fd  jns     short loc_180005A26
0x1800059ff  mov     edx, 12Eh; lineNumber
0x180005a04  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x180005a0b  lea     r8, aWil; "wil"
0x180005a12  mov     r9d, eax; hr
0x180005a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a1a  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x180005a1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a24  jmp     short loc_180005A45
0x180005a26  mov     staticNameWithVersion, [rsp+270h+pointer]
0x180005a2b  test    staticNameWithVersion, staticNameWithVersion
0x180005a2e  jz      short loc_180005A75
0x180005a30  mov     [rdi], staticNameWithVersion
0x180005a33  mov     eax, [staticNameWithVersion]
0x180005a35  inc     eax
0x180005a37  mov     [staticNameWithVersion], eax
0x180005a39  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x180005a3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a43  xor     ebx, ebx
0x180005a45  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x180005a4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005a4f  mov     eax, ebx
0x180005a51  mov     staticNameWithVersion, [rbp+170h+var_10]
0x180005a58  xor     staticNameWithVersion, rsp; StackCookie
0x180005a5b  call    __security_check_cookie
0x180005a60  lea     r11, [rsp+270h+var_s0]
0x180005a68  mov     rbx, [r11+20h]
0x180005a6c  mov     rdi, [r11+28h]
0x180005a70  mov     rsp, r11
0x180005a73  pop     rbp
0x180005a74  retn
0x180005a75  mov     r8, rdi; data
0x180005a78  lea     data, [rsp+270h+mutex]; mutex
0x180005a7d  lea     staticNameWithVersion, [rsp+270h+name]; name
0x180005a82  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005a87  mov     ebx, eax
0x180005a89  test    eax, eax
0x180005a8b  jns     short loc_180005A39
0x180005a8d  mov     edx, 137h
0x180005a92  jmp     loc_180005A04
```
