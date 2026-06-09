# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180016328`
- end: `0x180016497`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019390`

## callees

- `0x1800095bc`
- `0x180009634`
- `0x18000ba08`
- `0x18000c550`
- `0x18000c5d4`
- `0x18000c7a8`
- `0x18000c818`
- `0x18000c944`
- `0x1800120d0`
- `0x180016328`
- `0x18001a128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800163a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800163a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016360`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180016328  mov     [rsp-8+arg_10], rbx
0x18001632d  mov     [rsp-8+arg_18], rdi
0x180016332  push    rbp
0x180016333  lea     rbp, [rsp-170h]
0x18001633b  sub     rsp, 270h
0x180016342  mov     rax, cs:__security_cookie
0x180016349  xor     rax, rsp
0x18001634c  mov     [rbp+170h+var_10], rax
0x180016353  mov     rdi, rdx
0x180016356  mov     qword ptr [rdx], 0
0x18001635d  mov     rbx, rcx
0x180016360  call    cs:__imp_GetCurrentProcessId
0x180016366  mov     [rsp+270h+var_248], rbx
0x18001636b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180016372  mov     r9d, eax
0x180016375  mov     [rsp+270h+var_250], 130h; int
0x18001637d  mov     edx, 104h; unsigned __int64
0x180016382  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180016387  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001638c  mov     r9d, 1F0001h; dwDesiredAccess
0x180016392  mov     [rsp+270h+var_240], 0
0x18001639b  xor     r8d, r8d; dwFlags
0x18001639e  lea     rdx, [rsp+270h+Name]; lpName
0x1800163a3  xor     ecx, ecx; lpMutexAttributes
0x1800163a5  call    cs:__imp_CreateMutexExW
0x1800163ab  mov     rdx, rax
0x1800163ae  lea     rcx, [rsp+270h+var_240]
0x1800163b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800163b8  cmp     [rsp+270h+var_240], 0
0x1800163be  jnz     short loc_1800163C9
0x1800163c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800163c5  mov     ebx, eax
0x1800163c7  jmp     short loc_180016445
0x1800163c9  lea     rdx, [rsp+270h+var_238]
0x1800163ce  mov     [rsp+270h+var_238], 0
0x1800163d7  lea     rcx, [rsp+270h+var_240]
0x1800163dc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800163e1  lea     rdx, [rsp+270h+var_230]; void **
0x1800163e6  mov     [rsp+270h+var_230], 0
0x1800163ef  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800163f4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800163f9  mov     ebx, eax
0x1800163fb  test    eax, eax
0x1800163fd  jns     short loc_180016426
0x1800163ff  mov     edx, 12Eh; void *
0x180016404  mov     rcx, [rbp+178h]; this
0x18001640b  lea     r8, aWil; "wil"
0x180016412  mov     r9d, eax; char *
0x180016415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001641a  lea     rcx, [rsp+270h+var_238]
0x18001641f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016424  jmp     short loc_180016445
0x180016426  mov     rcx, [rsp+270h+var_230]
0x18001642b  test    rcx, rcx
0x18001642e  jz      short loc_180016475
0x180016430  mov     [rdi], rcx
0x180016433  mov     eax, [rcx]
0x180016435  inc     eax
0x180016437  mov     [rcx], eax
0x180016439  lea     rcx, [rsp+270h+var_238]
0x18001643e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016443  xor     ebx, ebx
0x180016445  lea     rcx, [rsp+270h+var_240]
0x18001644a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001644f  mov     eax, ebx
0x180016451  mov     rcx, [rbp+170h+var_10]
0x180016458  xor     rcx, rsp; StackCookie
0x18001645b  call    __security_check_cookie
0x180016460  lea     r11, [rsp+270h+var_s0]
0x180016468  mov     rbx, [r11+20h]
0x18001646c  mov     rdi, [r11+28h]
0x180016470  mov     rsp, r11
0x180016473  pop     rbp
0x180016474  retn
0x180016475  mov     r8, rdi
0x180016478  lea     rdx, [rsp+270h+var_240]
0x18001647d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180016482  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180016487  mov     ebx, eax
0x180016489  test    eax, eax
0x18001648b  jns     short loc_180016439
0x18001648d  mov     edx, 137h
0x180016492  jmp     loc_180016404
```
