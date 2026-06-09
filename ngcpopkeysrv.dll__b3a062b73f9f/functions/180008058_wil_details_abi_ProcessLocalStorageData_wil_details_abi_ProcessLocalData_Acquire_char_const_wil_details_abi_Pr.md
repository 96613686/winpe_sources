# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008058`
- end: `0x1800081e1`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009164`

## callees

- `0x180004de0`
- `0x180007968`
- `0x180007984`
- `0x180008058`
- `0x180008e38`
- `0x180009b7c`
- `0x18000b0fc`
- `0x18000b898`
- `0x18000bd1c`
- `0x18000c624`
- `0x18000c970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008090`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v8; // rcx
  int v10; // eax
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a2 = v13;
        ++*v8;
      }
      else
      {
        v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v10,
            120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180008058  mov     [rsp-8+arg_10], rbx
0x18000805d  mov     [rsp-8+arg_18], rdi
0x180008062  push    rbp
0x180008063  lea     rbp, [rsp-170h]
0x18000806b  sub     rsp, 270h
0x180008072  mov     rax, cs:__security_cookie
0x180008079  xor     rax, rsp
0x18000807c  mov     [rbp+170h+var_10], rax
0x180008083  mov     rdi, rdx
0x180008086  mov     rbx, rcx
0x180008089  mov     qword ptr [rdx], 0
0x180008090  call    cs:__imp_GetCurrentProcessId
0x180008096  mov     r9d, eax
0x180008099  mov     [rsp+270h+var_248], rbx
0x18000809e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800080a6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800080ad  mov     edx, 104h; unsigned __int64
0x1800080b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800080b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800080bc  mov     [rsp+270h+var_240], 0
0x1800080c5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800080cb  xor     r8d, r8d; dwFlags
0x1800080ce  lea     rdx, [rsp+270h+Name]; lpName
0x1800080d3  xor     ecx, ecx; lpMutexAttributes
0x1800080d5  call    cs:__imp_CreateMutexExW
0x1800080db  mov     rdx, rax
0x1800080de  lea     rcx, [rsp+270h+var_240]
0x1800080e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800080e8  cmp     [rsp+270h+var_240], 0
0x1800080ee  jnz     short loc_1800080F9
0x1800080f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800080f5  mov     ebx, eax
0x1800080f7  jmp     short loc_180008170
0x1800080f9  lea     rdx, [rsp+270h+var_238]
0x1800080fe  lea     rcx, [rsp+270h+var_240]
0x180008103  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008108  nop
0x180008109  mov     [rsp+270h+var_230], 0
0x180008112  lea     rdx, [rsp+270h+var_230]; void **
0x180008117  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000811c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008121  mov     ebx, eax
0x180008123  test    eax, eax
0x180008125  jns     short loc_180008150
0x180008127  mov     rcx, [rbp+178h]; this
0x18000812e  mov     r9d, eax; char *
0x180008131  lea     r8, aWil; "wil"
0x180008138  mov     edx, 12Eh; void *
0x18000813d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008142  nop
0x180008143  lea     rcx, [rsp+270h+var_238]
0x180008148  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000814d  nop
0x18000814e  jmp     short loc_180008170
0x180008150  mov     rcx, [rsp+270h+var_230]
0x180008155  test    rcx, rcx
0x180008158  jz      short loc_1800081A0
0x18000815a  mov     [rdi], rcx
0x18000815d  mov     eax, [rcx]
0x18000815f  inc     eax
0x180008161  mov     [rcx], eax
0x180008163  lea     rcx, [rsp+270h+var_238]
0x180008168  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000816d  nop
0x18000816e  xor     ebx, ebx
0x180008170  lea     rcx, [rsp+270h+var_240]
0x180008175  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000817a  mov     eax, ebx
0x18000817c  mov     rcx, [rbp+170h+var_10]
0x180008183  xor     rcx, rsp; StackCookie
0x180008186  call    __security_check_cookie
0x18000818b  lea     r11, [rsp+270h+var_s0]
0x180008193  mov     rbx, [r11+20h]
0x180008197  mov     rdi, [r11+28h]
0x18000819b  mov     rsp, r11
0x18000819e  pop     rbp
0x18000819f  retn
0x1800081a0  mov     r8, rdi
0x1800081a3  lea     rdx, [rsp+270h+var_240]
0x1800081a8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800081ad  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800081b2  mov     ebx, eax
0x1800081b4  test    eax, eax
0x1800081b6  jns     short loc_180008163
0x1800081b8  mov     rcx, [rbp+178h]; this
0x1800081bf  mov     r9d, eax; char *
0x1800081c2  lea     r8, aWil; "wil"
0x1800081c9  mov     edx, 137h; void *
0x1800081ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081d3  nop
0x1800081d4  lea     rcx, [rsp+270h+var_238]
0x1800081d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081de  nop
0x1800081df  jmp     short loc_180008170
```
