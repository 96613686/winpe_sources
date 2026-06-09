# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c928`
- end: `0x18000ca8e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d3f4`

## callees

- `0x180006a9c`
- `0x180006b3c`
- `0x18000a074`
- `0x18000a520`
- `0x18000c6e8`
- `0x18000c928`
- `0x18000d160`
- `0x18000d960`
- `0x18000e838`
- `0x18000ec34`
- `0x18000ed38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c9a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c9a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c960`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000c928  mov     [rsp-8+arg_10], rbx
0x18000c92d  mov     [rsp-8+arg_18], rdi
0x18000c932  push    rbp
0x18000c933  lea     rbp, [rsp-170h]
0x18000c93b  sub     rsp, 270h
0x18000c942  mov     rax, cs:__security_cookie
0x18000c949  xor     rax, rsp
0x18000c94c  mov     [rbp+170h+var_10], rax
0x18000c953  mov     rdi, rdx
0x18000c956  mov     qword ptr [rdx], 0
0x18000c95d  mov     rbx, rcx
0x18000c960  call    cs:__imp_GetCurrentProcessId
0x18000c966  mov     [rsp+270h+var_248], rbx
0x18000c96b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c972  mov     r9d, eax
0x18000c975  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000c97d  mov     edx, 104h; unsigned __int64
0x18000c982  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c987  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c98c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c992  mov     [rsp+270h+var_240], 0
0x18000c99b  xor     r8d, r8d; dwFlags
0x18000c99e  lea     rdx, [rsp+270h+Name]; lpName
0x18000c9a3  xor     ecx, ecx; lpMutexAttributes
0x18000c9a5  call    cs:__imp_CreateMutexExW
0x18000c9ab  mov     rdx, rax
0x18000c9ae  lea     rcx, [rsp+270h+var_240]
0x18000c9b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c9b8  cmp     [rsp+270h+var_240], 0
0x18000c9be  jnz     short loc_18000C9C9
0x18000c9c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c9c5  mov     ebx, eax
0x18000c9c7  jmp     short loc_18000CA3C
0x18000c9c9  lea     rdx, [rsp+270h+var_238]
0x18000c9ce  lea     rcx, [rsp+270h+var_240]
0x18000c9d3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c9d8  lea     rdx, [rsp+270h+var_230]; void **
0x18000c9dd  mov     [rsp+270h+var_230], 0
0x18000c9e6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c9eb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c9f0  mov     ebx, eax
0x18000c9f2  test    eax, eax
0x18000c9f4  jns     short loc_18000CA1D
0x18000c9f6  mov     edx, 12Eh; void *
0x18000c9fb  mov     rcx, [rbp+178h]; this
0x18000ca02  lea     r8, aWil; "wil"
0x18000ca09  mov     r9d, eax; char *
0x18000ca0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca11  lea     rcx, [rsp+270h+var_238]
0x18000ca16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca1b  jmp     short loc_18000CA3C
0x18000ca1d  mov     rcx, [rsp+270h+var_230]
0x18000ca22  test    rcx, rcx
0x18000ca25  jz      short loc_18000CA6C
0x18000ca27  mov     [rdi], rcx
0x18000ca2a  mov     eax, [rcx]
0x18000ca2c  inc     eax
0x18000ca2e  mov     [rcx], eax
0x18000ca30  lea     rcx, [rsp+270h+var_238]
0x18000ca35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca3a  xor     ebx, ebx
0x18000ca3c  lea     rcx, [rsp+270h+var_240]
0x18000ca41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ca46  mov     eax, ebx
0x18000ca48  mov     rcx, [rbp+170h+var_10]
0x18000ca4f  xor     rcx, rsp; StackCookie
0x18000ca52  call    __security_check_cookie
0x18000ca57  lea     r11, [rsp+270h+var_s0]
0x18000ca5f  mov     rbx, [r11+20h]
0x18000ca63  mov     rdi, [r11+28h]
0x18000ca67  mov     rsp, r11
0x18000ca6a  pop     rbp
0x18000ca6b  retn
0x18000ca6c  mov     r8, rdi
0x18000ca6f  lea     rdx, [rsp+270h+var_240]
0x18000ca74  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ca79  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ca7e  mov     ebx, eax
0x18000ca80  test    eax, eax
0x18000ca82  jns     short loc_18000CA30
0x18000ca84  mov     edx, 137h
0x18000ca89  jmp     loc_18000C9FB
```
