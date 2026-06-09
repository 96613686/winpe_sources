# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000804c`
- end: `0x1800081b2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800083e4`

## callees

- `0x180001a70`
- `0x180005aec`
- `0x180007a28`
- `0x180007a44`
- `0x18000804c`
- `0x180008c04`
- `0x18000990c`
- `0x18000af78`
- `0x18000bab4`
- `0x18000c524`
- `0x18000cc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008084`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18000804c  mov     [rsp-8+arg_10], rbx
0x180008051  mov     [rsp-8+arg_18], rdi
0x180008056  push    rbp
0x180008057  lea     rbp, [rsp-170h]
0x18000805f  sub     rsp, 270h
0x180008066  mov     rax, cs:__security_cookie
0x18000806d  xor     rax, rsp
0x180008070  mov     [rbp+170h+var_10], rax
0x180008077  mov     rdi, rdx
0x18000807a  mov     qword ptr [rdx], 0
0x180008081  mov     rbx, rcx
0x180008084  call    cs:__imp_GetCurrentProcessId
0x18000808a  mov     [rsp+270h+var_248], rbx
0x18000808f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008096  mov     r9d, eax
0x180008099  mov     [rsp+270h+var_250], 130h; int
0x1800080a1  mov     edx, 104h; unsigned __int64
0x1800080a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800080ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800080b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800080b6  mov     [rsp+270h+var_240], 0
0x1800080bf  xor     r8d, r8d; dwFlags
0x1800080c2  lea     rdx, [rsp+270h+Name]; lpName
0x1800080c7  xor     ecx, ecx; lpMutexAttributes
0x1800080c9  call    cs:__imp_CreateMutexExW
0x1800080cf  mov     rdx, rax
0x1800080d2  lea     rcx, [rsp+270h+var_240]
0x1800080d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800080dc  cmp     [rsp+270h+var_240], 0
0x1800080e2  jnz     short loc_1800080ED
0x1800080e4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800080e9  mov     ebx, eax
0x1800080eb  jmp     short loc_180008160
0x1800080ed  lea     rdx, [rsp+270h+var_238]
0x1800080f2  lea     rcx, [rsp+270h+var_240]
0x1800080f7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800080fc  lea     rdx, [rsp+270h+var_230]; void **
0x180008101  mov     [rsp+270h+var_230], 0
0x18000810a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000810f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008114  mov     ebx, eax
0x180008116  test    eax, eax
0x180008118  jns     short loc_180008141
0x18000811a  mov     edx, 12Eh; void *
0x18000811f  mov     rcx, [rbp+178h]; this
0x180008126  lea     r8, aWil; "wil"
0x18000812d  mov     r9d, eax; char *
0x180008130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008135  lea     rcx, [rsp+270h+var_238]
0x18000813a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000813f  jmp     short loc_180008160
0x180008141  mov     rcx, [rsp+270h+var_230]
0x180008146  test    rcx, rcx
0x180008149  jz      short loc_180008190
0x18000814b  mov     [rdi], rcx
0x18000814e  mov     eax, [rcx]
0x180008150  inc     eax
0x180008152  mov     [rcx], eax
0x180008154  lea     rcx, [rsp+270h+var_238]
0x180008159  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000815e  xor     ebx, ebx
0x180008160  lea     rcx, [rsp+270h+var_240]
0x180008165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000816a  mov     eax, ebx
0x18000816c  mov     rcx, [rbp+170h+var_10]
0x180008173  xor     rcx, rsp; StackCookie
0x180008176  call    __security_check_cookie
0x18000817b  lea     r11, [rsp+270h+var_s0]
0x180008183  mov     rbx, [r11+20h]
0x180008187  mov     rdi, [r11+28h]
0x18000818b  mov     rsp, r11
0x18000818e  pop     rbp
0x18000818f  retn
0x180008190  mov     r8, rdi
0x180008193  lea     rdx, [rsp+270h+var_240]
0x180008198  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000819d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800081a2  mov     ebx, eax
0x1800081a4  test    eax, eax
0x1800081a6  jns     short loc_180008154
0x1800081a8  mov     edx, 137h
0x1800081ad  jmp     loc_18000811F
```
