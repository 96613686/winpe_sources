# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180058f3c`
- end: `0x1800590ab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005b110`

## callees

- `0x180002790`
- `0x1800057c4`
- `0x1800057e0`
- `0x1800061a8`
- `0x1800071f4`
- `0x180007790`
- `0x180007918`
- `0x180007d14`
- `0x180007e18`
- `0x180058f3c`
- `0x18005b7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058fb9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180058fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058f74`

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
      304);
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
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> *)pointer;
      ++*v10;
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
0x180058f3c  mov     [rsp-8+arg_10], rbx
0x180058f41  mov     [rsp-8+arg_18], rdi
0x180058f46  push    rbp
0x180058f47  lea     rbp, [rsp-170h]
0x180058f4f  sub     rsp, 270h
0x180058f56  mov     rax, cs:__security_cookie
0x180058f5d  xor     rax, rsp
0x180058f60  mov     [rbp+170h+var_10], rax
0x180058f67  mov     rdi, data
0x180058f6a  mov     qword ptr [data], 0
0x180058f71  mov     rbx, staticNameWithVersion
0x180058f74  call    cs:__imp_GetCurrentProcessId
0x180058f7a  mov     [rsp+270h+var_248], rbx
0x180058f7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180058f86  mov     r9d, eax
0x180058f89  mov     [rsp+270h+bAlertable], 130h; bAlertable
0x180058f91  mov     edx, 104h; cchDest
0x180058f96  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x180058f9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058fa0  mov     r9d, 1F0001h; dwDesiredAccess
0x180058fa6  mov     [rsp+270h+mutex.m_ptr], 0
0x180058faf  xor     r8d, r8d; dwFlags
0x180058fb2  lea     data, [rsp+270h+name]; lpName
0x180058fb7  xor     ecx, ecx; lpMutexAttributes
0x180058fb9  call    cs:__imp_CreateMutexExW
0x180058fbf  mov     data, rax; ptr
0x180058fc2  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x180058fc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180058fcc  cmp     [rsp+270h+mutex.m_ptr], 0
0x180058fd2  jnz     short loc_180058FDD
0x180058fd4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180058fd9  mov     ebx, eax
0x180058fdb  jmp     short loc_180059059
0x180058fdd  lea     data, [rsp+270h+lock]; result
0x180058fe2  mov     [rsp+270h+lock.m_ptr], 0
0x180058feb  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x180058ff0  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180058ff5  lea     data, [rsp+270h+pointer]; pointer
0x180058ffa  mov     [rsp+270h+pointer], 0
0x180059003  lea     staticNameWithVersion, [rsp+270h+name]; name
0x180059008  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18005900d  mov     ebx, eax
0x18005900f  test    eax, eax
0x180059011  jns     short loc_18005903A
0x180059013  mov     edx, 12Eh; lineNumber
0x180059018  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x18005901f  lea     r8, aWil; "wil"
0x180059026  mov     r9d, eax; hr
0x180059029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005902e  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x180059033  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059038  jmp     short loc_180059059
0x18005903a  mov     staticNameWithVersion, [rsp+270h+pointer]
0x18005903f  test    staticNameWithVersion, staticNameWithVersion
0x180059042  jz      short loc_180059089
0x180059044  mov     [rdi], staticNameWithVersion
0x180059047  mov     eax, [staticNameWithVersion]
0x180059049  inc     eax
0x18005904b  mov     [staticNameWithVersion], eax
0x18005904d  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x180059052  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059057  xor     ebx, ebx
0x180059059  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x18005905e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059063  mov     eax, ebx
0x180059065  mov     staticNameWithVersion, [rbp+170h+var_10]
0x18005906c  xor     staticNameWithVersion, rsp; StackCookie
0x18005906f  call    __security_check_cookie
0x180059074  lea     r11, [rsp+270h+var_s0]
0x18005907c  mov     rbx, [r11+20h]
0x180059080  mov     rdi, [r11+28h]
0x180059084  mov     rsp, r11
0x180059087  pop     rbp
0x180059088  retn
0x180059089  mov     r8, rdi; data
0x18005908c  lea     data, [rsp+270h+mutex]; mutex
0x180059091  lea     staticNameWithVersion, [rsp+270h+name]; name
0x180059096  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005909b  mov     ebx, eax
0x18005909d  test    eax, eax
0x18005909f  jns     short loc_18005904D
0x1800590a1  mov     edx, 137h
0x1800590a6  jmp     loc_180059018
```
