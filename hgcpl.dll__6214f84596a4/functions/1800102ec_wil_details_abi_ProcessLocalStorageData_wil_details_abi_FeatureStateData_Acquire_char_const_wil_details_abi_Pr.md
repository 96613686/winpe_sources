# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800102ec`
- end: `0x18001044b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010c74`

## callees

- `0x180004960`
- `0x18000497c`
- `0x180005248`
- `0x180006070`
- `0x180006408`
- `0x180006518`
- `0x180006980`
- `0x180006a40`
- `0x1800102ec`
- `0x180010f04`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010369`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010324`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800102ec  mov     [rsp-8+arg_10], rbx
0x1800102f1  mov     [rsp-8+arg_18], rdi
0x1800102f6  push    rbp
0x1800102f7  lea     rbp, [rsp-170h]
0x1800102ff  sub     rsp, 270h
0x180010306  mov     rax, cs:__security_cookie
0x18001030d  xor     rax, rsp
0x180010310  mov     [rbp+170h+var_10], rax
0x180010317  mov     rdi, rdx
0x18001031a  mov     qword ptr [rdx], 0
0x180010321  mov     rbx, rcx
0x180010324  call    cs:__imp_GetCurrentProcessId
0x18001032a  mov     [rsp+270h+var_248], rbx
0x18001032f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010336  mov     r9d, eax
0x180010339  mov     [rsp+270h+var_250], 130h; int
0x180010341  mov     edx, 104h; unsigned __int64
0x180010346  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001034b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010350  mov     r9d, 1F0001h; dwDesiredAccess
0x180010356  mov     [rsp+270h+var_240], 0
0x18001035f  xor     r8d, r8d; dwFlags
0x180010362  lea     rdx, [rsp+270h+Name]; lpName
0x180010367  xor     ecx, ecx; lpMutexAttributes
0x180010369  call    cs:__imp_CreateMutexExW
0x18001036f  mov     rdx, rax
0x180010372  lea     rcx, [rsp+270h+var_240]
0x180010377  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001037c  cmp     [rsp+270h+var_240], 0
0x180010382  jnz     short loc_18001038D
0x180010384  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010389  mov     ebx, eax
0x18001038b  jmp     short loc_1800103F9
0x18001038d  lea     rdx, [rsp+270h+var_238]
0x180010392  lea     rcx, [rsp+270h+var_240]
0x180010397  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001039c  lea     rdx, [rsp+270h+var_230]; void **
0x1800103a1  mov     [rsp+270h+var_230], 0
0x1800103aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800103af  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800103b4  mov     ebx, eax
0x1800103b6  test    eax, eax
0x1800103b8  jns     short loc_1800103DA
0x1800103ba  mov     edx, 12Eh; void *
0x1800103bf  mov     rcx, [rbp+178h]; this
0x1800103c6  mov     r9d, eax; char *
0x1800103c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103ce  lea     rcx, [rsp+270h+var_238]
0x1800103d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800103d8  jmp     short loc_1800103F9
0x1800103da  mov     rcx, [rsp+270h+var_230]
0x1800103df  test    rcx, rcx
0x1800103e2  jz      short loc_180010429
0x1800103e4  mov     [rdi], rcx
0x1800103e7  mov     eax, [rcx]
0x1800103e9  inc     eax
0x1800103eb  mov     [rcx], eax
0x1800103ed  lea     rcx, [rsp+270h+var_238]
0x1800103f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800103f7  xor     ebx, ebx
0x1800103f9  lea     rcx, [rsp+270h+var_240]
0x1800103fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010403  mov     eax, ebx
0x180010405  mov     rcx, [rbp+170h+var_10]
0x18001040c  xor     rcx, rsp; StackCookie
0x18001040f  call    __security_check_cookie
0x180010414  lea     r11, [rsp+270h+var_s0]
0x18001041c  mov     rbx, [r11+20h]
0x180010420  mov     rdi, [r11+28h]
0x180010424  mov     rsp, r11
0x180010427  pop     rbp
0x180010428  retn
0x180010429  mov     r8, rdi
0x18001042c  lea     rdx, [rsp+270h+var_240]
0x180010431  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010436  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001043b  mov     ebx, eax
0x18001043d  test    eax, eax
0x18001043f  jns     short loc_1800103ED
0x180010441  mov     edx, 137h
0x180010446  jmp     loc_1800103BF
```
