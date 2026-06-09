# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007ee0`
- end: `0x180008046`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008e80`

## callees

- `0x180001a70`
- `0x180005aec`
- `0x180007a28`
- `0x180007a44`
- `0x180007ee0`
- `0x180008c04`
- `0x1800097dc`
- `0x18000af78`
- `0x18000bab4`
- `0x18000c524`
- `0x18000cc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007f5d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007f18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007f18`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180007ee0  mov     [rsp-8+arg_10], rbx
0x180007ee5  mov     [rsp-8+arg_18], rdi
0x180007eea  push    rbp
0x180007eeb  lea     rbp, [rsp-170h]
0x180007ef3  sub     rsp, 270h
0x180007efa  mov     rax, cs:__security_cookie
0x180007f01  xor     rax, rsp
0x180007f04  mov     [rbp+170h+var_10], rax
0x180007f0b  mov     rdi, rdx
0x180007f0e  mov     qword ptr [rdx], 0
0x180007f15  mov     rbx, rcx
0x180007f18  call    cs:__imp_GetCurrentProcessId
0x180007f1e  mov     [rsp+270h+var_248], rbx
0x180007f23  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007f2a  mov     r9d, eax
0x180007f2d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180007f35  mov     edx, 104h; unsigned __int64
0x180007f3a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007f3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007f44  mov     r9d, 1F0001h; dwDesiredAccess
0x180007f4a  mov     [rsp+270h+var_240], 0
0x180007f53  xor     r8d, r8d; dwFlags
0x180007f56  lea     rdx, [rsp+270h+Name]; lpName
0x180007f5b  xor     ecx, ecx; lpMutexAttributes
0x180007f5d  call    cs:__imp_CreateMutexExW
0x180007f63  mov     rdx, rax
0x180007f66  lea     rcx, [rsp+270h+var_240]
0x180007f6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007f70  cmp     [rsp+270h+var_240], 0
0x180007f76  jnz     short loc_180007F81
0x180007f78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007f7d  mov     ebx, eax
0x180007f7f  jmp     short loc_180007FF4
0x180007f81  lea     rdx, [rsp+270h+var_238]
0x180007f86  lea     rcx, [rsp+270h+var_240]
0x180007f8b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007f90  lea     rdx, [rsp+270h+var_230]; void **
0x180007f95  mov     [rsp+270h+var_230], 0
0x180007f9e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007fa3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007fa8  mov     ebx, eax
0x180007faa  test    eax, eax
0x180007fac  jns     short loc_180007FD5
0x180007fae  mov     edx, 12Eh; void *
0x180007fb3  mov     rcx, [rbp+178h]; this
0x180007fba  lea     r8, aWil; "wil"
0x180007fc1  mov     r9d, eax; char *
0x180007fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fc9  lea     rcx, [rsp+270h+var_238]
0x180007fce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007fd3  jmp     short loc_180007FF4
0x180007fd5  mov     rcx, [rsp+270h+var_230]
0x180007fda  test    rcx, rcx
0x180007fdd  jz      short loc_180008024
0x180007fdf  mov     [rdi], rcx
0x180007fe2  mov     eax, [rcx]
0x180007fe4  inc     eax
0x180007fe6  mov     [rcx], eax
0x180007fe8  lea     rcx, [rsp+270h+var_238]
0x180007fed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ff2  xor     ebx, ebx
0x180007ff4  lea     rcx, [rsp+270h+var_240]
0x180007ff9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ffe  mov     eax, ebx
0x180008000  mov     rcx, [rbp+170h+var_10]
0x180008007  xor     rcx, rsp; StackCookie
0x18000800a  call    __security_check_cookie
0x18000800f  lea     r11, [rsp+270h+var_s0]
0x180008017  mov     rbx, [r11+20h]
0x18000801b  mov     rdi, [r11+28h]
0x18000801f  mov     rsp, r11
0x180008022  pop     rbp
0x180008023  retn
0x180008024  mov     r8, rdi
0x180008027  lea     rdx, [rsp+270h+var_240]
0x18000802c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008031  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008036  mov     ebx, eax
0x180008038  test    eax, eax
0x18000803a  jns     short loc_180007FE8
0x18000803c  mov     edx, 137h
0x180008041  jmp     loc_180007FB3
```
