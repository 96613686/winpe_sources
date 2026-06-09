# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005ca8`
- end: `0x180005e07`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006c7c`

## callees

- `0x180005a7c`
- `0x180005a98`
- `0x180005ca8`
- `0x1800069a8`
- `0x1800075a8`
- `0x1800087fc`
- `0x180008f38`
- `0x180009300`
- `0x1800099d4`
- `0x180009e80`
- `0x18000ad30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ce0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d25`

## pseudocode

```c
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180005ca8  mov     [rsp-8+arg_10], rbx
0x180005cad  mov     [rsp-8+arg_18], rdi
0x180005cb2  push    rbp
0x180005cb3  lea     rbp, [rsp-170h]
0x180005cbb  sub     rsp, 270h
0x180005cc2  mov     rax, cs:__security_cookie
0x180005cc9  xor     rax, rsp
0x180005ccc  mov     [rbp+170h+var_10], rax
0x180005cd3  mov     rdi, rdx
0x180005cd6  mov     qword ptr [rdx], 0
0x180005cdd  mov     rbx, rcx
0x180005ce0  call    cs:__imp_GetCurrentProcessId
0x180005ce6  mov     [rsp+270h+var_248], rbx
0x180005ceb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005cf2  mov     r9d, eax
0x180005cf5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005cfd  mov     edx, 104h; unsigned __int64
0x180005d02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005d07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d0c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005d12  mov     [rsp+270h+var_240], 0
0x180005d1b  xor     r8d, r8d; dwFlags
0x180005d1e  lea     rdx, [rsp+270h+Name]; lpName
0x180005d23  xor     ecx, ecx; lpMutexAttributes
0x180005d25  call    cs:__imp_CreateMutexExW
0x180005d2b  mov     rdx, rax
0x180005d2e  lea     rcx, [rsp+270h+var_240]
0x180005d33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005d38  cmp     [rsp+270h+var_240], 0
0x180005d3e  jnz     short loc_180005D49
0x180005d40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005d45  mov     ebx, eax
0x180005d47  jmp     short loc_180005DB5
0x180005d49  lea     rdx, [rsp+270h+var_238]
0x180005d4e  lea     rcx, [rsp+270h+var_240]
0x180005d53  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005d58  lea     rdx, [rsp+270h+var_230]; void **
0x180005d5d  mov     [rsp+270h+var_230], 0
0x180005d66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005d6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005d70  mov     ebx, eax
0x180005d72  test    eax, eax
0x180005d74  jns     short loc_180005D96
0x180005d76  mov     edx, 12Eh; void *
0x180005d7b  mov     rcx, [rbp+178h]; this
0x180005d82  mov     r9d, eax; char *
0x180005d85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d8a  lea     rcx, [rsp+270h+var_238]
0x180005d8f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005d94  jmp     short loc_180005DB5
0x180005d96  mov     rcx, [rsp+270h+var_230]
0x180005d9b  test    rcx, rcx
0x180005d9e  jz      short loc_180005DE5
0x180005da0  mov     [rdi], rcx
0x180005da3  mov     eax, [rcx]
0x180005da5  inc     eax
0x180005da7  mov     [rcx], eax
0x180005da9  lea     rcx, [rsp+270h+var_238]
0x180005dae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005db3  xor     ebx, ebx
0x180005db5  lea     rcx, [rsp+270h+var_240]
0x180005dba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005dbf  mov     eax, ebx
0x180005dc1  mov     rcx, [rbp+170h+var_10]
0x180005dc8  xor     rcx, rsp; StackCookie
0x180005dcb  call    __security_check_cookie
0x180005dd0  lea     r11, [rsp+270h+var_s0]
0x180005dd8  mov     rbx, [r11+20h]
0x180005ddc  mov     rdi, [r11+28h]
0x180005de0  mov     rsp, r11
0x180005de3  pop     rbp
0x180005de4  retn
0x180005de5  mov     r8, rdi
0x180005de8  lea     rdx, [rsp+270h+var_240]
0x180005ded  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005df2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005df7  mov     ebx, eax
0x180005df9  test    eax, eax
0x180005dfb  jns     short loc_180005DA9
0x180005dfd  mov     edx, 137h
0x180005e02  jmp     loc_180005D7B
```
