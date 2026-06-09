# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140027f2c`
- end: `0x140028092`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140029fd4`

## callees

- `0x14000aed8`
- `0x140027a34`
- `0x140027a54`
- `0x140027f2c`
- `0x14002b118`
- `0x14002cb90`
- `0x14002f044`
- `0x14003081c`
- `0x140031c84`
- `0x140031f00`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140027fa9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140027fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140027f61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140027f61`

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
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
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
0x140027f2c  mov     [rsp-8+arg_10], rbx
0x140027f31  mov     [rsp-8+arg_18], rdi
0x140027f36  push    rbp
0x140027f37  lea     rbp, [rsp-170h]
0x140027f3f  sub     rsp, 270h
0x140027f46  mov     rax, cs:__security_cookie
0x140027f4d  xor     rax, rsp
0x140027f50  mov     [rbp+170h+var_10], rax
0x140027f57  and     qword ptr [rdx], 0
0x140027f5b  mov     rdi, rdx
0x140027f5e  mov     rbx, rcx
0x140027f61  call    cs:__imp_GetCurrentProcessId
0x140027f68  nop     dword ptr [rax+rax+00h]
0x140027f6d  mov     [rsp+270h+var_248], rbx
0x140027f72  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140027f79  mov     r9d, eax
0x140027f7c  mov     [rsp+270h+var_250], 130h; int
0x140027f84  mov     edx, 104h; unsigned __int64
0x140027f89  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140027f8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140027f93  and     [rsp+270h+var_240], 0
0x140027f99  lea     rdx, [rsp+270h+Name]; lpName
0x140027f9e  mov     r9d, 1F0001h; dwDesiredAccess
0x140027fa4  xor     r8d, r8d; dwFlags
0x140027fa7  xor     ecx, ecx; lpMutexAttributes
0x140027fa9  call    cs:__imp_CreateMutexExW
0x140027fb0  nop     dword ptr [rax+rax+00h]
0x140027fb5  mov     rdx, rax
0x140027fb8  lea     rcx, [rsp+270h+var_240]
0x140027fbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140027fc2  cmp     [rsp+270h+var_240], 0
0x140027fc8  jnz     short loc_140027FD3
0x140027fca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140027fcf  mov     ebx, eax
0x140027fd1  jmp     short loc_14002803F
0x140027fd3  lea     rdx, [rsp+270h+var_238]
0x140027fd8  lea     rcx, [rsp+270h+var_240]
0x140027fdd  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140027fe2  and     [rsp+270h+var_230], 0
0x140027fe8  lea     rdx, [rsp+270h+var_230]; void **
0x140027fed  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140027ff2  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140027ff7  mov     ebx, eax
0x140027ff9  test    eax, eax
0x140027ffb  jns     short loc_14002801D
0x140027ffd  mov     edx, 12Bh; void *
0x140028002  mov     rcx, [rbp+178h]; this
0x140028009  mov     r9d, eax; char *
0x14002800c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140028011  lea     rcx, [rsp+270h+var_238]
0x140028016  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002801b  jmp     short loc_14002803F
0x14002801d  mov     rcx, [rsp+270h+var_230]
0x140028022  test    rcx, rcx
0x140028025  jz      short loc_140028070
0x140028027  mov     [rdi], rcx
0x14002802a  mov     ecx, [rcx]
0x14002802c  mov     rax, [rdi]
0x14002802f  inc     ecx
0x140028031  mov     [rax], ecx
0x140028033  lea     rcx, [rsp+270h+var_238]
0x140028038  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002803d  xor     ebx, ebx
0x14002803f  lea     rcx, [rsp+270h+var_240]
0x140028044  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140028049  mov     eax, ebx
0x14002804b  mov     rcx, [rbp+170h+var_10]
0x140028052  xor     rcx, rsp; StackCookie
0x140028055  call    __security_check_cookie
0x14002805a  lea     r11, [rsp+270h+var_s0]
0x140028062  mov     rbx, [r11+20h]
0x140028066  mov     rdi, [r11+28h]
0x14002806a  mov     rsp, r11
0x14002806d  pop     rbp
0x14002806e  retn
0x140028070  mov     r8, rdi
0x140028073  lea     rdx, [rsp+270h+var_240]
0x140028078  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14002807d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140028082  mov     ebx, eax
0x140028084  test    eax, eax
0x140028086  jns     short loc_140028033
0x140028088  mov     edx, 134h
0x14002808d  jmp     loc_140028002
```
