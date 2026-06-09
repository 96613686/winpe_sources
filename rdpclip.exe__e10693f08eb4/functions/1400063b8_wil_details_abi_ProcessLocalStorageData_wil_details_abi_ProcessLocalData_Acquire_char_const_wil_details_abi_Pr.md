# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400063b8`
- end: `0x140006562`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400073d0`

## callees

- `0x140006210`
- `0x14000622c`
- `0x1400063b8`
- `0x14000725c`
- `0x140007ba0`
- `0x140008188`
- `0x140008ce0`
- `0x140008f00`
- `0x1400091fc`
- `0x1400092a8`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006435`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400063f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400063f0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1400063b8  mov     [rsp-8+arg_10], rbx
0x1400063bd  mov     [rsp-8+arg_18], rdi
0x1400063c2  push    rbp
0x1400063c3  lea     rbp, [rsp-170h]
0x1400063cb  sub     rsp, 270h
0x1400063d2  mov     rax, cs:__security_cookie
0x1400063d9  xor     rax, rsp
0x1400063dc  mov     [rbp+170h+var_10], rax
0x1400063e3  mov     rdi, rdx
0x1400063e6  mov     qword ptr [rdx], 0
0x1400063ed  mov     rbx, rcx
0x1400063f0  call    cs:__imp_GetCurrentProcessId
0x1400063f6  mov     [rsp+270h+var_248], rbx
0x1400063fb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006402  mov     r9d, eax
0x140006405  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000640d  mov     edx, 104h; unsigned __int64
0x140006412  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140006417  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000641c  mov     r9d, 1F0001h; dwDesiredAccess
0x140006422  mov     [rsp+270h+var_240], 0
0x14000642b  xor     r8d, r8d; dwFlags
0x14000642e  lea     rdx, [rsp+270h+Name]; lpName
0x140006433  xor     ecx, ecx; lpMutexAttributes
0x140006435  call    cs:__imp_CreateMutexExW
0x14000643b  mov     rdx, rax
0x14000643e  lea     rcx, [rsp+270h+var_240]
0x140006443  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140006448  cmp     [rsp+270h+var_240], 0
0x14000644e  jnz     short loc_14000645C
0x140006450  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006455  mov     ebx, eax
0x140006457  jmp     loc_14000650D
0x14000645c  lea     rdx, [rsp+270h+var_238]
0x140006461  lea     rcx, [rsp+270h+var_240]
0x140006466  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000646b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140006470  mov     [rsp+270h+var_230], 0
0x140006479  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000647e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140006483  mov     ebx, eax
0x140006485  test    eax, eax
0x140006487  jns     short loc_1400064E6
0x140006489  mov     rcx, [rbp+178h]; this
0x140006490  lea     r8, aWil; "wil"
0x140006497  mov     r9d, eax; char *
0x14000649a  mov     edx, 66h ; 'f'; void *
0x14000649f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064a4  mov     rcx, [rbp+178h]; this
0x1400064ab  lea     r8, aWil; "wil"
0x1400064b2  mov     r9d, ebx; char *
0x1400064b5  mov     edx, 6Fh ; 'o'; void *
0x1400064ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064bf  mov     r9d, ebx; char *
0x1400064c2  mov     edx, 12Eh; void *
0x1400064c7  mov     rcx, [rbp+178h]; this
0x1400064ce  lea     r8, aWil; "wil"
0x1400064d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064da  lea     rcx, [rsp+270h+var_238]
0x1400064df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400064e4  jmp     short loc_14000650D
0x1400064e6  mov     rax, [rsp+270h+var_230]
0x1400064eb  lea     rcx, ds:0[rax*4]
0x1400064f3  test    rcx, rcx
0x1400064f6  jz      short loc_14000653D
0x1400064f8  mov     [rdi], rcx
0x1400064fb  mov     eax, [rcx]
0x1400064fd  inc     eax
0x1400064ff  mov     [rcx], eax
0x140006501  lea     rcx, [rsp+270h+var_238]
0x140006506  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000650b  xor     ebx, ebx
0x14000650d  lea     rcx, [rsp+270h+var_240]
0x140006512  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006517  mov     eax, ebx
0x140006519  mov     rcx, [rbp+170h+var_10]
0x140006520  xor     rcx, rsp; StackCookie
0x140006523  call    __security_check_cookie
0x140006528  lea     r11, [rsp+270h+var_s0]
0x140006530  mov     rbx, [r11+20h]
0x140006534  mov     rdi, [r11+28h]
0x140006538  mov     rsp, r11
0x14000653b  pop     rbp
0x14000653c  retn
0x14000653d  mov     r8, rdi
0x140006540  lea     rdx, [rsp+270h+var_240]
0x140006545  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000654a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000654f  mov     ebx, eax
0x140006551  test    eax, eax
0x140006553  jns     short loc_140006501
0x140006555  mov     r9d, eax
0x140006558  mov     edx, 137h
0x14000655d  jmp     loc_1400064C7
```
