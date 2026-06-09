# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800cdc6c`
- end: `0x1800cddcb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800cdf88`

## callees

- `0x1800c9dd8`
- `0x1800cac00`
- `0x1800cada0`
- `0x1800cd96c`
- `0x1800cd988`
- `0x1800cdc6c`
- `0x1800cf35c`
- `0x1800cfeec`
- `0x1800d0614`
- `0x1800d0df4`
- `0x1800d0f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cdce9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cdce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cdca4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cdca4`

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
0x1800cdc6c  mov     [rsp-8+arg_10], rbx
0x1800cdc71  mov     [rsp-8+arg_18], rdi
0x1800cdc76  push    rbp
0x1800cdc77  lea     rbp, [rsp-170h]
0x1800cdc7f  sub     rsp, 270h
0x1800cdc86  mov     rax, cs:__security_cookie
0x1800cdc8d  xor     rax, rsp
0x1800cdc90  mov     [rbp+170h+var_10], rax
0x1800cdc97  mov     rdi, data
0x1800cdc9a  mov     qword ptr [data], 0
0x1800cdca1  mov     rbx, staticNameWithVersion
0x1800cdca4  call    cs:__imp_GetCurrentProcessId
0x1800cdcaa  mov     [rsp+270h+var_248], rbx
0x1800cdcaf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800cdcb6  mov     r9d, eax
0x1800cdcb9  mov     [rsp+270h+bAlertable], 130h; bAlertable
0x1800cdcc1  mov     edx, 104h; cchDest
0x1800cdcc6  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x1800cdccb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cdcd0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800cdcd6  mov     [rsp+270h+mutex.m_ptr], 0
0x1800cdcdf  xor     r8d, r8d; dwFlags
0x1800cdce2  lea     data, [rsp+270h+name]; lpName
0x1800cdce7  xor     ecx, ecx; lpMutexAttributes
0x1800cdce9  call    cs:__imp_CreateMutexExW
0x1800cdcef  mov     data, rax; ptr
0x1800cdcf2  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdcf7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800cdcfc  cmp     [rsp+270h+mutex.m_ptr], 0
0x1800cdd02  jnz     short loc_1800CDD0D
0x1800cdd04  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800cdd09  mov     ebx, eax
0x1800cdd0b  jmp     short loc_1800CDD79
0x1800cdd0d  lea     data, [rsp+270h+lock]; result
0x1800cdd12  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdd17  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800cdd1c  lea     data, [rsp+270h+pointer]; pointer
0x1800cdd21  mov     [rsp+270h+pointer], 0
0x1800cdd2a  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cdd2f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800cdd34  mov     ebx, eax
0x1800cdd36  test    eax, eax
0x1800cdd38  jns     short loc_1800CDD5A
0x1800cdd3a  mov     edx, 12Eh; lineNumber
0x1800cdd3f  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x1800cdd46  mov     r9d, eax; callerReturnAddress
0x1800cdd49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdd4e  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cdd53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdd58  jmp     short loc_1800CDD79
0x1800cdd5a  mov     staticNameWithVersion, [rsp+270h+pointer]
0x1800cdd5f  test    staticNameWithVersion, staticNameWithVersion
0x1800cdd62  jz      short loc_1800CDDA9
0x1800cdd64  mov     [rdi], staticNameWithVersion
0x1800cdd67  mov     eax, [staticNameWithVersion]
0x1800cdd69  inc     eax
0x1800cdd6b  mov     [staticNameWithVersion], eax
0x1800cdd6d  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cdd72  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdd77  xor     ebx, ebx
0x1800cdd79  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdd7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdd83  mov     eax, ebx
0x1800cdd85  mov     staticNameWithVersion, [rbp+170h+var_10]
0x1800cdd8c  xor     staticNameWithVersion, rsp; StackCookie
0x1800cdd8f  call    __security_check_cookie
0x1800cdd94  lea     r11, [rsp+270h+var_s0]
0x1800cdd9c  mov     rbx, [r11+20h]
0x1800cdda0  mov     rdi, [r11+28h]
0x1800cdda4  mov     rsp, r11
0x1800cdda7  pop     rbp
0x1800cdda8  retn
0x1800cdda9  mov     r8, rdi; data
0x1800cddac  lea     data, [rsp+270h+mutex]; mutex
0x1800cddb1  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cddb6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800cddbb  mov     ebx, eax
0x1800cddbd  test    eax, eax
0x1800cddbf  jns     short loc_1800CDD6D
0x1800cddc1  mov     edx, 137h
0x1800cddc6  jmp     loc_1800CDD3F
```
