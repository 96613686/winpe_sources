# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004238`
- end: `0x140004397`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140004da0`

## callees

- `0x1400029a0`
- `0x1400040ec`
- `0x140004108`
- `0x140004238`
- `0x140004ab8`
- `0x1400054dc`
- `0x1400059c4`
- `0x140005fe4`
- `0x14000612c`
- `0x140006590`
- `0x140006694`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004270`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400042b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400042b5`

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
0x140004238  mov     [rsp-8+arg_10], rbx
0x14000423d  mov     [rsp-8+arg_18], rdi
0x140004242  push    rbp
0x140004243  lea     rbp, [rsp-170h]
0x14000424b  sub     rsp, 270h
0x140004252  mov     rax, cs:__security_cookie
0x140004259  xor     rax, rsp
0x14000425c  mov     [rbp+170h+var_10], rax
0x140004263  mov     rdi, rdx
0x140004266  mov     qword ptr [rdx], 0
0x14000426d  mov     rbx, rcx
0x140004270  call    cs:__imp_GetCurrentProcessId
0x140004276  mov     [rsp+270h+var_248], rbx
0x14000427b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004282  mov     r9d, eax
0x140004285  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000428d  mov     edx, 104h; unsigned __int64
0x140004292  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004297  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000429c  mov     r9d, 1F0001h; dwDesiredAccess
0x1400042a2  mov     [rsp+270h+var_240], 0
0x1400042ab  xor     r8d, r8d; dwFlags
0x1400042ae  lea     rdx, [rsp+270h+Name]; lpName
0x1400042b3  xor     ecx, ecx; lpMutexAttributes
0x1400042b5  call    cs:__imp_CreateMutexExW
0x1400042bb  mov     rdx, rax
0x1400042be  lea     rcx, [rsp+270h+var_240]
0x1400042c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400042c8  cmp     [rsp+270h+var_240], 0
0x1400042ce  jnz     short loc_1400042D9
0x1400042d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400042d5  mov     ebx, eax
0x1400042d7  jmp     short loc_140004345
0x1400042d9  lea     rdx, [rsp+270h+var_238]
0x1400042de  lea     rcx, [rsp+270h+var_240]
0x1400042e3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400042e8  lea     rdx, [rsp+270h+var_230]; void **
0x1400042ed  mov     [rsp+270h+var_230], 0
0x1400042f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400042fb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004300  mov     ebx, eax
0x140004302  test    eax, eax
0x140004304  jns     short loc_140004326
0x140004306  mov     edx, 12Eh; void *
0x14000430b  mov     rcx, [rbp+178h]; this
0x140004312  mov     r9d, eax; char *
0x140004315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000431a  lea     rcx, [rsp+270h+var_238]
0x14000431f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004324  jmp     short loc_140004345
0x140004326  mov     rcx, [rsp+270h+var_230]
0x14000432b  test    rcx, rcx
0x14000432e  jz      short loc_140004375
0x140004330  mov     [rdi], rcx
0x140004333  mov     eax, [rcx]
0x140004335  inc     eax
0x140004337  mov     [rcx], eax
0x140004339  lea     rcx, [rsp+270h+var_238]
0x14000433e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004343  xor     ebx, ebx
0x140004345  lea     rcx, [rsp+270h+var_240]
0x14000434a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000434f  mov     eax, ebx
0x140004351  mov     rcx, [rbp+170h+var_10]
0x140004358  xor     rcx, rsp; StackCookie
0x14000435b  call    __security_check_cookie
0x140004360  lea     r11, [rsp+270h+var_s0]
0x140004368  mov     rbx, [r11+20h]
0x14000436c  mov     rdi, [r11+28h]
0x140004370  mov     rsp, r11
0x140004373  pop     rbp
0x140004374  retn
0x140004375  mov     r8, rdi
0x140004378  lea     rdx, [rsp+270h+var_240]
0x14000437d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004382  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004387  mov     ebx, eax
0x140004389  test    eax, eax
0x14000438b  jns     short loc_140004339
0x14000438d  mov     edx, 137h
0x140004392  jmp     loc_14000430B
```
