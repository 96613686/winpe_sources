# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007260`
- end: `0x1400073bf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140007994`

## callees

- `0x1400029a0`
- `0x1400040ec`
- `0x140004108`
- `0x140004ab8`
- `0x1400059c4`
- `0x140005fe4`
- `0x14000612c`
- `0x140006590`
- `0x140006694`
- `0x140007260`
- `0x140007dd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007298`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400072dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400072dd`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140007260  mov     [rsp-8+arg_10], rbx
0x140007265  mov     [rsp-8+arg_18], rdi
0x14000726a  push    rbp
0x14000726b  lea     rbp, [rsp-170h]
0x140007273  sub     rsp, 270h
0x14000727a  mov     rax, cs:__security_cookie
0x140007281  xor     rax, rsp
0x140007284  mov     [rbp+170h+var_10], rax
0x14000728b  mov     rdi, rdx
0x14000728e  mov     qword ptr [rdx], 0
0x140007295  mov     rbx, rcx
0x140007298  call    cs:__imp_GetCurrentProcessId
0x14000729e  mov     [rsp+270h+var_248], rbx
0x1400072a3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400072aa  mov     r9d, eax
0x1400072ad  mov     [rsp+270h+var_250], 130h; int
0x1400072b5  mov     edx, 104h; unsigned __int64
0x1400072ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400072bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400072c4  mov     r9d, 1F0001h; dwDesiredAccess
0x1400072ca  mov     [rsp+270h+var_240], 0
0x1400072d3  xor     r8d, r8d; dwFlags
0x1400072d6  lea     rdx, [rsp+270h+Name]; lpName
0x1400072db  xor     ecx, ecx; lpMutexAttributes
0x1400072dd  call    cs:__imp_CreateMutexExW
0x1400072e3  mov     rdx, rax
0x1400072e6  lea     rcx, [rsp+270h+var_240]
0x1400072eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400072f0  cmp     [rsp+270h+var_240], 0
0x1400072f6  jnz     short loc_140007301
0x1400072f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400072fd  mov     ebx, eax
0x1400072ff  jmp     short loc_14000736D
0x140007301  lea     rdx, [rsp+270h+var_238]
0x140007306  lea     rcx, [rsp+270h+var_240]
0x14000730b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140007310  lea     rdx, [rsp+270h+var_230]; void **
0x140007315  mov     [rsp+270h+var_230], 0
0x14000731e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007323  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140007328  mov     ebx, eax
0x14000732a  test    eax, eax
0x14000732c  jns     short loc_14000734E
0x14000732e  mov     edx, 12Eh; void *
0x140007333  mov     rcx, [rbp+178h]; this
0x14000733a  mov     r9d, eax; char *
0x14000733d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007342  lea     rcx, [rsp+270h+var_238]
0x140007347  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000734c  jmp     short loc_14000736D
0x14000734e  mov     rcx, [rsp+270h+var_230]
0x140007353  test    rcx, rcx
0x140007356  jz      short loc_14000739D
0x140007358  mov     [rdi], rcx
0x14000735b  mov     eax, [rcx]
0x14000735d  inc     eax
0x14000735f  mov     [rcx], eax
0x140007361  lea     rcx, [rsp+270h+var_238]
0x140007366  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000736b  xor     ebx, ebx
0x14000736d  lea     rcx, [rsp+270h+var_240]
0x140007372  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007377  mov     eax, ebx
0x140007379  mov     rcx, [rbp+170h+var_10]
0x140007380  xor     rcx, rsp; StackCookie
0x140007383  call    __security_check_cookie
0x140007388  lea     r11, [rsp+270h+var_s0]
0x140007390  mov     rbx, [r11+20h]
0x140007394  mov     rdi, [r11+28h]
0x140007398  mov     rsp, r11
0x14000739b  pop     rbp
0x14000739c  retn
0x14000739d  mov     r8, rdi
0x1400073a0  lea     rdx, [rsp+270h+var_240]
0x1400073a5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400073aa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400073af  mov     ebx, eax
0x1400073b1  test    eax, eax
0x1400073b3  jns     short loc_140007361
0x1400073b5  mov     edx, 137h
0x1400073ba  jmp     loc_140007333
```
