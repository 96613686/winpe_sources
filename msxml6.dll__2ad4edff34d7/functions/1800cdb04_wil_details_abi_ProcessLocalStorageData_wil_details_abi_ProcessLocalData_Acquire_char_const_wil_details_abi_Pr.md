# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800cdb04`
- end: `0x1800cdc63`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `HRESULT __fastcall(const char *staticNameWithVersion, wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> **data)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800cea50`

## callees

- `0x1800c9dd8`
- `0x1800cac00`
- `0x1800cada0`
- `0x1800cd96c`
- `0x1800cd988`
- `0x1800cdb04`
- `0x1800cf238`
- `0x1800cfeec`
- `0x1800d0614`
- `0x1800d0df4`
- `0x1800d0f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cdb81`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800cdb81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cdb3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cdb3c`

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
      120);
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
      *data = (wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *)pointer;
      ++*v11;
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
0x1800cdb04  mov     [rsp-8+arg_10], rbx
0x1800cdb09  mov     [rsp-8+arg_18], rdi
0x1800cdb0e  push    rbp
0x1800cdb0f  lea     rbp, [rsp-170h]
0x1800cdb17  sub     rsp, 270h
0x1800cdb1e  mov     rax, cs:__security_cookie
0x1800cdb25  xor     rax, rsp
0x1800cdb28  mov     [rbp+170h+var_10], rax
0x1800cdb2f  mov     rdi, data
0x1800cdb32  mov     qword ptr [data], 0
0x1800cdb39  mov     rbx, staticNameWithVersion
0x1800cdb3c  call    cs:__imp_GetCurrentProcessId
0x1800cdb42  mov     [rsp+270h+var_248], rbx
0x1800cdb47  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800cdb4e  mov     r9d, eax
0x1800cdb51  mov     [rsp+270h+bAlertable], 78h ; 'x'; bAlertable
0x1800cdb59  mov     edx, 104h; cchDest
0x1800cdb5e  lea     staticNameWithVersion, [rsp+270h+name]; pszDest
0x1800cdb63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cdb68  mov     r9d, 1F0001h; dwDesiredAccess
0x1800cdb6e  mov     [rsp+270h+mutex.m_ptr], 0
0x1800cdb77  xor     r8d, r8d; dwFlags
0x1800cdb7a  lea     data, [rsp+270h+name]; lpName
0x1800cdb7f  xor     ecx, ecx; lpMutexAttributes
0x1800cdb81  call    cs:__imp_CreateMutexExW
0x1800cdb87  mov     data, rax; ptr
0x1800cdb8a  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdb8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800cdb94  cmp     [rsp+270h+mutex.m_ptr], 0
0x1800cdb9a  jnz     short loc_1800CDBA5
0x1800cdb9c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800cdba1  mov     ebx, eax
0x1800cdba3  jmp     short loc_1800CDC11
0x1800cdba5  lea     data, [rsp+270h+lock]; result
0x1800cdbaa  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdbaf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800cdbb4  lea     data, [rsp+270h+pointer]; pointer
0x1800cdbb9  mov     [rsp+270h+pointer], 0
0x1800cdbc2  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cdbc7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800cdbcc  mov     ebx, eax
0x1800cdbce  test    eax, eax
0x1800cdbd0  jns     short loc_1800CDBF2
0x1800cdbd2  mov     edx, 12Eh; lineNumber
0x1800cdbd7  mov     staticNameWithVersion, [rbp+178h]; callerReturnAddress
0x1800cdbde  mov     r9d, eax; callerReturnAddress
0x1800cdbe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdbe6  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cdbeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdbf0  jmp     short loc_1800CDC11
0x1800cdbf2  mov     staticNameWithVersion, [rsp+270h+pointer]
0x1800cdbf7  test    staticNameWithVersion, staticNameWithVersion
0x1800cdbfa  jz      short loc_1800CDC41
0x1800cdbfc  mov     [rdi], staticNameWithVersion
0x1800cdbff  mov     eax, [staticNameWithVersion]
0x1800cdc01  inc     eax
0x1800cdc03  mov     [staticNameWithVersion], eax
0x1800cdc05  lea     staticNameWithVersion, [rsp+270h+lock]; this
0x1800cdc0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdc0f  xor     ebx, ebx
0x1800cdc11  lea     staticNameWithVersion, [rsp+270h+mutex]; this
0x1800cdc16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800cdc1b  mov     eax, ebx
0x1800cdc1d  mov     staticNameWithVersion, [rbp+170h+var_10]
0x1800cdc24  xor     staticNameWithVersion, rsp; StackCookie
0x1800cdc27  call    __security_check_cookie
0x1800cdc2c  lea     r11, [rsp+270h+var_s0]
0x1800cdc34  mov     rbx, [r11+20h]
0x1800cdc38  mov     rdi, [r11+28h]
0x1800cdc3c  mov     rsp, r11
0x1800cdc3f  pop     rbp
0x1800cdc40  retn
0x1800cdc41  mov     r8, rdi; data
0x1800cdc44  lea     data, [rsp+270h+mutex]; mutex
0x1800cdc49  lea     staticNameWithVersion, [rsp+270h+name]; name
0x1800cdc4e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800cdc53  mov     ebx, eax
0x1800cdc55  test    eax, eax
0x1800cdc57  jns     short loc_1800CDC05
0x1800cdc59  mov     edx, 137h
0x1800cdc5e  jmp     loc_1800CDBD7
```
