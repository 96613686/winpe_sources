# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006308`
- end: `0x180006492`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `394`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800072b0`

## callees

- `0x180003adc`
- `0x180004310`
- `0x180005fc0`
- `0x180005fdc`
- `0x180006308`
- `0x180007c9c`
- `0x180008b68`
- `0x18000935c`
- `0x180009758`
- `0x180009f04`
- `0x18000a09c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006385`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006340`

## string_xrefs

- `0x180006486`: `MakeAndInitialize( name, wistd::move(mutex), data)`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  __int64 v12; // rdx
  const char *v13; // rax
  void *v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  wil::details *v18; // [rsp+28h] [rbp-D8h]
  int v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v20; // [rsp+38h] [rbp-C8h] BYREF
  void *v21; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  *(_QWORD *)v19 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v19,
    Mutex);
  if ( *(_QWORD *)v19 )
  {
    v20 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)v19,
      &v20);
    v21 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v21);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      LODWORD(v18) = Pointer;
      v12 = 302;
      v13 = "SemaphoreValue::TryGetPointer(name, &pointer)";
LABEL_5:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v12,
        v11,
        "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
        v13,
        v18,
        v19[0]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v20,
        v14);
      goto LABEL_9;
    }
    v15 = v21;
    if ( v21 )
    {
      *a2 = v21;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        LODWORD(v18) = v17;
        v12 = 311;
        v13 = "MakeAndInitialize( name, wistd::move(mutex), data)";
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v10);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)v19,
    v7);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006308  mov     [rsp-8+arg_10], rbx
0x18000630d  mov     [rsp-8+arg_18], rdi
0x180006312  push    rbp
0x180006313  lea     rbp, [rsp-170h]
0x18000631b  sub     rsp, 270h
0x180006322  mov     rax, cs:__security_cookie
0x180006329  xor     rax, rsp
0x18000632c  mov     [rbp+170h+var_10], rax
0x180006333  mov     rdi, rdx
0x180006336  mov     qword ptr [rdx], 0
0x18000633d  mov     rbx, rcx
0x180006340  call    cs:__imp_GetCurrentProcessId
0x180006346  mov     [rsp+270h+var_248], rbx
0x18000634b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006352  mov     r9d, eax
0x180006355  mov     dword ptr [rsp+270h+var_250], 78h ; 'x'
0x18000635d  mov     edx, 104h; unsigned __int64
0x180006362  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006367  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000636c  mov     r9d, 1F0001h; dwDesiredAccess
0x180006372  mov     qword ptr [rsp+270h+var_240], 0; int
0x18000637b  xor     r8d, r8d; dwFlags
0x18000637e  lea     rdx, [rsp+270h+Name]; lpName
0x180006383  xor     ecx, ecx; lpMutexAttributes
0x180006385  call    cs:__imp_CreateMutexExW
0x18000638b  mov     rdx, rax
0x18000638e  lea     rcx, [rsp+270h+var_240]
0x180006393  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006398  cmp     qword ptr [rsp+270h+var_240], 0
0x18000639e  jnz     short loc_1800063AC
0x1800063a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800063a5  mov     ebx, eax
0x1800063a7  jmp     loc_180006435
0x1800063ac  lea     rdx, [rsp+270h+var_238]
0x1800063b1  mov     [rsp+270h+var_238], 0
0x1800063ba  lea     rcx, [rsp+270h+var_240]
0x1800063bf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800063c4  lea     rdx, [rsp+270h+var_230]; void **
0x1800063c9  mov     [rsp+270h+var_230], 0
0x1800063d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800063d7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800063dc  mov     ebx, eax
0x1800063de  test    eax, eax
0x1800063e0  jns     short loc_180006416
0x1800063e2  mov     dword ptr [rsp+270h+var_248], eax; wil::details *
0x1800063e6  mov     edx, 12Eh; void *
0x1800063eb  lea     rax, aSemaphorevalue_0; "SemaphoreValue::TryGetPointer(name, &po"...
0x1800063f2  mov     rcx, [rbp+178h]; this
0x1800063f9  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x180006400  mov     [rsp+270h+var_250], rax; char *
0x180006405  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18000640a  lea     rcx, [rsp+270h+var_238]
0x18000640f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006414  jmp     short loc_180006435
0x180006416  mov     rcx, [rsp+270h+var_230]
0x18000641b  test    rcx, rcx
0x18000641e  jz      short loc_180006465
0x180006420  mov     [rdi], rcx
0x180006423  mov     eax, [rcx]
0x180006425  inc     eax
0x180006427  mov     [rcx], eax
0x180006429  lea     rcx, [rsp+270h+var_238]
0x18000642e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006433  xor     ebx, ebx
0x180006435  lea     rcx, [rsp+270h+var_240]
0x18000643a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000643f  mov     eax, ebx
0x180006441  mov     rcx, [rbp+170h+var_10]
0x180006448  xor     rcx, rsp; StackCookie
0x18000644b  call    __security_check_cookie
0x180006450  lea     r11, [rsp+270h+var_s0]
0x180006458  mov     rbx, [r11+20h]
0x18000645c  mov     rdi, [r11+28h]
0x180006460  mov     rsp, r11
0x180006463  pop     rbp
0x180006464  retn
0x180006465  mov     r8, rdi
0x180006468  lea     rdx, [rsp+270h+var_240]
0x18000646d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006472  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006477  mov     ebx, eax
0x180006479  test    eax, eax
0x18000647b  jns     short loc_180006429
0x18000647d  mov     dword ptr [rsp+270h+var_248], eax
0x180006481  mov     edx, 137h
0x180006486  lea     rax, aMakeandinitial; "MakeAndInitialize( name, wistd::move(mu"...
0x18000648d  jmp     loc_1800063F2
```
