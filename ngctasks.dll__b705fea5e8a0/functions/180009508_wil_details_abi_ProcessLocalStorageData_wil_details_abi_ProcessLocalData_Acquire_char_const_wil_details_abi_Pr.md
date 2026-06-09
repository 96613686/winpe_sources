# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009508`
- end: `0x180009691`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000aae8`

## callees

- `0x180006330`
- `0x180008cb4`
- `0x180008cd0`
- `0x180009508`
- `0x18000a750`
- `0x18000b7d4`
- `0x18000cc34`
- `0x18000df4c`
- `0x18000e498`
- `0x18000ec4c`
- `0x18000eff4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009585`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009540`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009540`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
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
  void *v9; // rdx
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v13; // eax
  void *v14; // rdx
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
      &v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v11 = v17;
      if ( v17 )
      {
        *a2 = v17;
        ++*v11;
      }
      else
      {
        v13 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v13,
            120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
            &v16,
            v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v9);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v10);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180009508  mov     [rsp-8+arg_10], rbx
0x18000950d  mov     [rsp-8+arg_18], rdi
0x180009512  push    rbp
0x180009513  lea     rbp, [rsp-170h]
0x18000951b  sub     rsp, 270h
0x180009522  mov     rax, cs:__security_cookie
0x180009529  xor     rax, rsp
0x18000952c  mov     [rbp+170h+var_10], rax
0x180009533  mov     rdi, rdx
0x180009536  mov     rbx, rcx
0x180009539  mov     qword ptr [rdx], 0
0x180009540  call    cs:__imp_GetCurrentProcessId
0x180009546  mov     r9d, eax
0x180009549  mov     [rsp+270h+var_248], rbx
0x18000954e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009556  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000955d  mov     edx, 104h; unsigned __int64
0x180009562  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009567  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000956c  mov     [rsp+270h+var_240], 0
0x180009575  mov     r9d, 1F0001h; dwDesiredAccess
0x18000957b  xor     r8d, r8d; dwFlags
0x18000957e  lea     rdx, [rsp+270h+Name]; lpName
0x180009583  xor     ecx, ecx; lpMutexAttributes
0x180009585  call    cs:__imp_CreateMutexExW
0x18000958b  mov     rdx, rax
0x18000958e  lea     rcx, [rsp+270h+var_240]
0x180009593  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009598  cmp     [rsp+270h+var_240], 0
0x18000959e  jnz     short loc_1800095A9
0x1800095a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800095a5  mov     ebx, eax
0x1800095a7  jmp     short loc_180009620
0x1800095a9  lea     rdx, [rsp+270h+var_238]
0x1800095ae  lea     rcx, [rsp+270h+var_240]
0x1800095b3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800095b8  nop
0x1800095b9  mov     [rsp+270h+var_230], 0
0x1800095c2  lea     rdx, [rsp+270h+var_230]; void **
0x1800095c7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800095cc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800095d1  mov     ebx, eax
0x1800095d3  test    eax, eax
0x1800095d5  jns     short loc_180009600
0x1800095d7  mov     rcx, [rbp+178h]; this
0x1800095de  mov     r9d, eax; char *
0x1800095e1  lea     r8, aWil; "wil"
0x1800095e8  mov     edx, 12Eh; void *
0x1800095ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095f2  nop
0x1800095f3  lea     rcx, [rsp+270h+var_238]
0x1800095f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800095fd  nop
0x1800095fe  jmp     short loc_180009620
0x180009600  mov     rcx, [rsp+270h+var_230]
0x180009605  test    rcx, rcx
0x180009608  jz      short loc_180009650
0x18000960a  mov     [rdi], rcx
0x18000960d  mov     eax, [rcx]
0x18000960f  inc     eax
0x180009611  mov     [rcx], eax
0x180009613  lea     rcx, [rsp+270h+var_238]
0x180009618  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000961d  nop
0x18000961e  xor     ebx, ebx
0x180009620  lea     rcx, [rsp+270h+var_240]
0x180009625  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000962a  mov     eax, ebx
0x18000962c  mov     rcx, [rbp+170h+var_10]
0x180009633  xor     rcx, rsp; StackCookie
0x180009636  call    __security_check_cookie
0x18000963b  lea     r11, [rsp+270h+var_s0]
0x180009643  mov     rbx, [r11+20h]
0x180009647  mov     rdi, [r11+28h]
0x18000964b  mov     rsp, r11
0x18000964e  pop     rbp
0x18000964f  retn
0x180009650  mov     r8, rdi
0x180009653  lea     rdx, [rsp+270h+var_240]
0x180009658  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000965d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009662  mov     ebx, eax
0x180009664  test    eax, eax
0x180009666  jns     short loc_180009613
0x180009668  mov     rcx, [rbp+178h]; this
0x18000966f  mov     r9d, eax; char *
0x180009672  lea     r8, aWil; "wil"
0x180009679  mov     edx, 137h; void *
0x18000967e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009683  nop
0x180009684  lea     rcx, [rsp+270h+var_238]
0x180009689  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000968e  nop
0x18000968f  jmp     short loc_180009620
```
