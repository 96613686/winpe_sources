# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18004f778`
- end: `0x18004f8d7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004fa98`

## callees

- `0x18001b300`
- `0x180041394`
- `0x18004f478`
- `0x18004f494`
- `0x18004f778`
- `0x180050dc0`
- `0x180051948`
- `0x180052008`
- `0x180052754`
- `0x180052800`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f7f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f7f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f7b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f7b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004f778  mov     [rsp-8+arg_10], rbx
0x18004f77d  mov     [rsp-8+arg_18], rdi
0x18004f782  push    rbp
0x18004f783  lea     rbp, [rsp-170h]
0x18004f78b  sub     rsp, 270h
0x18004f792  mov     rax, cs:__security_cookie
0x18004f799  xor     rax, rsp
0x18004f79c  mov     [rbp+170h+var_10], rax
0x18004f7a3  mov     rdi, rdx
0x18004f7a6  mov     qword ptr [rdx], 0
0x18004f7ad  mov     rbx, rcx
0x18004f7b0  call    cs:__imp_GetCurrentProcessId
0x18004f7b6  mov     [rsp+270h+var_248], rbx
0x18004f7bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004f7c2  mov     r9d, eax
0x18004f7c5  mov     [rsp+270h+var_250], 130h; int
0x18004f7cd  mov     edx, 104h; unsigned __int64
0x18004f7d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f7d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f7dc  mov     r9d, 1F0001h; dwDesiredAccess
0x18004f7e2  mov     [rsp+270h+var_240], 0
0x18004f7eb  xor     r8d, r8d; dwFlags
0x18004f7ee  lea     rdx, [rsp+270h+Name]; lpName
0x18004f7f3  xor     ecx, ecx; lpMutexAttributes
0x18004f7f5  call    cs:__imp_CreateMutexExW
0x18004f7fb  mov     rdx, rax
0x18004f7fe  lea     rcx, [rsp+270h+var_240]
0x18004f803  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004f808  cmp     [rsp+270h+var_240], 0
0x18004f80e  jnz     short loc_18004F819
0x18004f810  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004f815  mov     ebx, eax
0x18004f817  jmp     short loc_18004F885
0x18004f819  lea     rdx, [rsp+270h+var_238]
0x18004f81e  lea     rcx, [rsp+270h+var_240]
0x18004f823  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004f828  lea     rdx, [rsp+270h+var_230]; void **
0x18004f82d  mov     [rsp+270h+var_230], 0
0x18004f836  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f83b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004f840  mov     ebx, eax
0x18004f842  test    eax, eax
0x18004f844  jns     short loc_18004F866
0x18004f846  mov     edx, 12Eh; void *
0x18004f84b  mov     rcx, [rbp+178h]; this
0x18004f852  mov     r9d, eax; char *
0x18004f855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f85a  lea     rcx, [rsp+270h+var_238]
0x18004f85f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f864  jmp     short loc_18004F885
0x18004f866  mov     rcx, [rsp+270h+var_230]
0x18004f86b  test    rcx, rcx
0x18004f86e  jz      short loc_18004F8B5
0x18004f870  mov     [rdi], rcx
0x18004f873  mov     eax, [rcx]
0x18004f875  inc     eax
0x18004f877  mov     [rcx], eax
0x18004f879  lea     rcx, [rsp+270h+var_238]
0x18004f87e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f883  xor     ebx, ebx
0x18004f885  lea     rcx, [rsp+270h+var_240]
0x18004f88a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f88f  mov     eax, ebx
0x18004f891  mov     rcx, [rbp+170h+var_10]
0x18004f898  xor     rcx, rsp; StackCookie
0x18004f89b  call    __security_check_cookie
0x18004f8a0  lea     r11, [rsp+270h+var_s0]
0x18004f8a8  mov     rbx, [r11+20h]
0x18004f8ac  mov     rdi, [r11+28h]
0x18004f8b0  mov     rsp, r11
0x18004f8b3  pop     rbp
0x18004f8b4  retn
0x18004f8b5  mov     r8, rdi
0x18004f8b8  lea     rdx, [rsp+270h+var_240]
0x18004f8bd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f8c2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004f8c7  mov     ebx, eax
0x18004f8c9  test    eax, eax
0x18004f8cb  jns     short loc_18004F879
0x18004f8cd  mov     edx, 137h
0x18004f8d2  jmp     loc_18004F84B
```
