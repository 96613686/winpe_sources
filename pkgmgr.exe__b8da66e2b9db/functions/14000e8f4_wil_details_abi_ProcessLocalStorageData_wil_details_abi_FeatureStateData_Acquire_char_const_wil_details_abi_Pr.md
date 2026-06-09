# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000e8f4`
- end: `0x14000eaae`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000eec8`

## callees

- `0x140002360`
- `0x140003ea8`
- `0x140003ec4`
- `0x1400048a0`
- `0x1400056ac`
- `0x140005c7c`
- `0x140005ebc`
- `0x1400062d8`
- `0x1400063c8`
- `0x14000e8f4`
- `0x14000f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000e97b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000e97b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e935`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e935`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  void *v7; // rdx
  int Pointer; // eax
  void *v10; // rdx
  _DWORD *v11; // rcx
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  wil::details *v15; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C8h] BYREF
  void *v17[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v17[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( !v15 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v7);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v15,
    &v16);
  v17[0] = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v17);
  LastErrorFailHr = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v15,
      v10);
    return LastErrorFailHr;
  }
  v11 = v17[0];
  if ( v17[0] )
  {
    *a2 = v17[0];
    ++*v11;
  }
  else
  {
    v13 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v15,
        v14);
      return LastErrorFailHr;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v12);
  return 0;
}

```

## disassembly

```asm
0x14000e8f4  mov     rax, rsp
0x14000e8f7  push    rbp
0x14000e8f8  lea     rbp, [rax-178h]
0x14000e8ff  sub     rsp, 270h
0x14000e906  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x14000e90f  mov     [rax+18h], rbx
0x14000e913  mov     [rax+20h], rdi
0x14000e917  mov     rax, cs:__security_cookie
0x14000e91e  xor     rax, rsp
0x14000e921  mov     [rbp+170h+var_10], rax
0x14000e928  mov     rdi, rdx
0x14000e92b  mov     rbx, rcx
0x14000e92e  mov     qword ptr [rdx], 0
0x14000e935  call    cs:__imp_GetCurrentProcessId
0x14000e93b  mov     r9d, eax
0x14000e93e  mov     [rsp+270h+var_248], rbx
0x14000e943  mov     [rsp+270h+var_250], 130h; int
0x14000e94b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000e952  mov     edx, 104h; unsigned __int64
0x14000e957  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14000e95c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000e961  nop
0x14000e962  mov     [rsp+270h+var_240], 0
0x14000e96b  mov     r9d, 1F0001h; dwDesiredAccess
0x14000e971  xor     r8d, r8d; dwFlags
0x14000e974  lea     rdx, [rsp+270h+Name]; lpName
0x14000e979  xor     ecx, ecx; lpMutexAttributes
0x14000e97b  call    cs:__imp_CreateMutexExW
0x14000e981  mov     rdx, rax
0x14000e984  lea     rcx, [rsp+270h+var_240]
0x14000e989  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000e98e  cmp     [rsp+270h+var_240], 0
0x14000e994  jnz     short loc_14000E9AF
0x14000e996  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000e99b  mov     ebx, eax
0x14000e99d  lea     rcx, [rsp+270h+var_240]
0x14000e9a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e9a7  nop
0x14000e9a8  mov     eax, ebx
0x14000e9aa  jmp     loc_14000EA3B
0x14000e9af  lea     rdx, [rsp+270h+var_238]
0x14000e9b4  lea     rcx, [rsp+270h+var_240]
0x14000e9b9  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000e9be  mov     [rsp+270h+var_230], 0
0x14000e9c7  lea     rdx, [rsp+270h+var_230]; void **
0x14000e9cc  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14000e9d1  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x14000e9d6  mov     ebx, eax
0x14000e9d8  test    eax, eax
0x14000e9da  jns     short loc_14000EA10
0x14000e9dc  mov     rcx, [rbp+178h]; this
0x14000e9e3  mov     r9d, eax; char *
0x14000e9e6  lea     r8, aWil; "wil"
0x14000e9ed  mov     edx, 12Eh; void *
0x14000e9f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e9f7  nop
0x14000e9f8  lea     rcx, [rsp+270h+var_238]
0x14000e9fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea02  nop
0x14000ea03  lea     rcx, [rsp+270h+var_240]
0x14000ea08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea0d  nop
0x14000ea0e  jmp     short loc_14000E9A8
0x14000ea10  mov     rcx, [rsp+270h+var_230]
0x14000ea15  test    rcx, rcx
0x14000ea18  jz      short loc_14000EA5F
0x14000ea1a  mov     [rdi], rcx
0x14000ea1d  mov     eax, [rcx]
0x14000ea1f  inc     eax
0x14000ea21  mov     [rcx], eax
0x14000ea23  lea     rcx, [rsp+270h+var_238]
0x14000ea28  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea2d  nop
0x14000ea2e  lea     rcx, [rsp+270h+var_240]
0x14000ea33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea38  nop
0x14000ea39  xor     eax, eax
0x14000ea3b  mov     rcx, [rbp+170h+var_10]
0x14000ea42  xor     rcx, rsp; StackCookie
0x14000ea45  call    __security_check_cookie
0x14000ea4a  lea     r11, [rsp+270h+var_s0]
0x14000ea52  mov     rbx, [r11+20h]
0x14000ea56  mov     rdi, [r11+28h]
0x14000ea5a  mov     rsp, r11
0x14000ea5d  pop     rbp
0x14000ea5e  retn
0x14000ea5f  mov     r8, rdi
0x14000ea62  lea     rdx, [rsp+270h+var_240]
0x14000ea67  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14000ea6c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000ea71  mov     ebx, eax
0x14000ea73  test    eax, eax
0x14000ea75  jns     short loc_14000EA23
0x14000ea77  mov     rcx, [rbp+178h]; this
0x14000ea7e  mov     r9d, eax; char *
0x14000ea81  lea     r8, aWil; "wil"
0x14000ea88  mov     edx, 137h; void *
0x14000ea8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ea92  nop
0x14000ea93  lea     rcx, [rsp+270h+var_238]
0x14000ea98  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea9d  nop
0x14000ea9e  lea     rcx, [rsp+270h+var_240]
0x14000eaa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000eaa8  nop
0x14000eaa9  jmp     loc_14000E9A8
```
