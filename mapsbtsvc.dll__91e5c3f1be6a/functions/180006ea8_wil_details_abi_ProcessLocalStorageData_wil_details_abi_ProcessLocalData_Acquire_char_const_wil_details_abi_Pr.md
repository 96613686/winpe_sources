# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006ea8`
- end: `0x180007040`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `408`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800079c8`

## callees

- `0x180001e70`
- `0x180006dc4`
- `0x180006de0`
- `0x180006ea8`
- `0x180007728`
- `0x180008104`
- `0x180008794`
- `0x180008d3c`
- `0x180008ea8`
- `0x18000923c`
- `0x180009344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006f25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ee0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  _DWORD *v16; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v21 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v21,
    Mutex);
  if ( v21 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v21,
      v22);
    v23 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v23, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v11, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v12, (const char *)LastErrorFailHr, v20);
      v14 = LastErrorFailHr;
      v15 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v15, v13, (const char *)v14, v19);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_9;
    }
    v16 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v16;
      ++*v16;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v18;
      if ( v18 < 0 )
      {
        v14 = (unsigned int)v18;
        v15 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006ea8  mov     [rsp-8+arg_10], rbx
0x180006ead  mov     [rsp-8+arg_18], rdi
0x180006eb2  push    rbp
0x180006eb3  lea     rbp, [rsp-170h]
0x180006ebb  sub     rsp, 270h
0x180006ec2  mov     rax, cs:__security_cookie
0x180006ec9  xor     rax, rsp
0x180006ecc  mov     [rbp+170h+var_10], rax
0x180006ed3  mov     rdi, rdx
0x180006ed6  mov     rbx, rcx
0x180006ed9  mov     qword ptr [rdx], 0
0x180006ee0  call    cs:__imp_GetCurrentProcessId
0x180006ee6  mov     r9d, eax
0x180006ee9  mov     [rsp+270h+var_248], rbx
0x180006eee  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006ef6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006efd  mov     edx, 104h; unsigned __int64
0x180006f02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006f07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f0c  mov     [rsp+270h+var_240], 0
0x180006f15  mov     r9d, 1F0001h; dwDesiredAccess
0x180006f1b  xor     r8d, r8d; dwFlags
0x180006f1e  lea     rdx, [rsp+270h+Name]; lpName
0x180006f23  xor     ecx, ecx; lpMutexAttributes
0x180006f25  call    cs:__imp_CreateMutexExW
0x180006f2b  mov     rdx, rax
0x180006f2e  lea     rcx, [rsp+270h+var_240]
0x180006f33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006f38  cmp     [rsp+270h+var_240], 0
0x180006f3e  jnz     short loc_180006F4C
0x180006f40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006f45  mov     ebx, eax
0x180006f47  jmp     loc_180006FEA
0x180006f4c  lea     rdx, [rsp+270h+var_238]
0x180006f51  lea     rcx, [rsp+270h+var_240]
0x180006f56  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006f5b  nop
0x180006f5c  mov     [rsp+270h+var_230], 0
0x180006f65  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180006f6a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006f6f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006f74  mov     ebx, eax
0x180006f76  test    eax, eax
0x180006f78  jns     short loc_180006FC3
0x180006f7a  mov     rcx, [rbp+178h]; this
0x180006f81  mov     r9d, eax; char *
0x180006f84  mov     edx, 66h ; 'f'; void *
0x180006f89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f8e  mov     rcx, [rbp+178h]; this
0x180006f95  mov     r9d, ebx; char *
0x180006f98  mov     edx, 6Fh ; 'o'; void *
0x180006f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fa2  mov     r9d, ebx; char *
0x180006fa5  mov     edx, 12Eh; void *
0x180006faa  mov     rcx, [rbp+178h]; this
0x180006fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fb6  nop
0x180006fb7  lea     rcx, [rsp+270h+var_238]
0x180006fbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006fc1  jmp     short loc_180006FEA
0x180006fc3  mov     rax, [rsp+270h+var_230]
0x180006fc8  lea     rcx, ds:0[rax*4]
0x180006fd0  test    rcx, rcx
0x180006fd3  jz      short loc_18000701A
0x180006fd5  mov     [rdi], rcx
0x180006fd8  mov     eax, [rcx]
0x180006fda  inc     eax
0x180006fdc  mov     [rcx], eax
0x180006fde  lea     rcx, [rsp+270h+var_238]
0x180006fe3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006fe8  xor     ebx, ebx
0x180006fea  lea     rcx, [rsp+270h+var_240]
0x180006fef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006ff4  mov     eax, ebx
0x180006ff6  mov     rcx, [rbp+170h+var_10]
0x180006ffd  xor     rcx, rsp; StackCookie
0x180007000  call    __security_check_cookie
0x180007005  lea     r11, [rsp+270h+var_s0]
0x18000700d  mov     rbx, [r11+20h]
0x180007011  mov     rdi, [r11+28h]
0x180007015  mov     rsp, r11
0x180007018  pop     rbp
0x180007019  retn
0x18000701a  mov     r8, rdi
0x18000701d  lea     rdx, [rsp+270h+var_240]
0x180007022  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007027  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000702c  mov     ebx, eax
0x18000702e  test    eax, eax
0x180007030  jns     short loc_180006FDE
0x180007032  mov     r9d, eax
0x180007035  mov     edx, 137h
0x18000703a  jmp     loc_180006FAA
```
