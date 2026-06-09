# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180012b94`
- end: `0x180012cfa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800138ac`

## callees

- `0x180006a9c`
- `0x180006b3c`
- `0x18000a074`
- `0x18000a520`
- `0x18000c6e8`
- `0x18000d160`
- `0x18000e838`
- `0x18000ec34`
- `0x18000ed38`
- `0x180012b94`
- `0x180013ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012c11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012bcc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180012b94  mov     [rsp-8+arg_10], rbx
0x180012b99  mov     [rsp-8+arg_18], rdi
0x180012b9e  push    rbp
0x180012b9f  lea     rbp, [rsp-170h]
0x180012ba7  sub     rsp, 270h
0x180012bae  mov     rax, cs:__security_cookie
0x180012bb5  xor     rax, rsp
0x180012bb8  mov     [rbp+170h+var_10], rax
0x180012bbf  mov     rdi, rdx
0x180012bc2  mov     qword ptr [rdx], 0
0x180012bc9  mov     rbx, rcx
0x180012bcc  call    cs:__imp_GetCurrentProcessId
0x180012bd2  mov     [rsp+270h+var_248], rbx
0x180012bd7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180012bde  mov     r9d, eax
0x180012be1  mov     [rsp+270h+var_250], 130h; int
0x180012be9  mov     edx, 104h; unsigned __int64
0x180012bee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012bf3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012bf8  mov     r9d, 1F0001h; dwDesiredAccess
0x180012bfe  mov     [rsp+270h+var_240], 0
0x180012c07  xor     r8d, r8d; dwFlags
0x180012c0a  lea     rdx, [rsp+270h+Name]; lpName
0x180012c0f  xor     ecx, ecx; lpMutexAttributes
0x180012c11  call    cs:__imp_CreateMutexExW
0x180012c17  mov     rdx, rax
0x180012c1a  lea     rcx, [rsp+270h+var_240]
0x180012c1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012c24  cmp     [rsp+270h+var_240], 0
0x180012c2a  jnz     short loc_180012C35
0x180012c2c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012c31  mov     ebx, eax
0x180012c33  jmp     short loc_180012CA8
0x180012c35  lea     rdx, [rsp+270h+var_238]
0x180012c3a  lea     rcx, [rsp+270h+var_240]
0x180012c3f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012c44  lea     rdx, [rsp+270h+var_230]; void **
0x180012c49  mov     [rsp+270h+var_230], 0
0x180012c52  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012c57  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180012c5c  mov     ebx, eax
0x180012c5e  test    eax, eax
0x180012c60  jns     short loc_180012C89
0x180012c62  mov     edx, 12Eh; void *
0x180012c67  mov     rcx, [rbp+178h]; this
0x180012c6e  lea     r8, aWil; "wil"
0x180012c75  mov     r9d, eax; char *
0x180012c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c7d  lea     rcx, [rsp+270h+var_238]
0x180012c82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012c87  jmp     short loc_180012CA8
0x180012c89  mov     rcx, [rsp+270h+var_230]
0x180012c8e  test    rcx, rcx
0x180012c91  jz      short loc_180012CD8
0x180012c93  mov     [rdi], rcx
0x180012c96  mov     eax, [rcx]
0x180012c98  inc     eax
0x180012c9a  mov     [rcx], eax
0x180012c9c  lea     rcx, [rsp+270h+var_238]
0x180012ca1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012ca6  xor     ebx, ebx
0x180012ca8  lea     rcx, [rsp+270h+var_240]
0x180012cad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012cb2  mov     eax, ebx
0x180012cb4  mov     rcx, [rbp+170h+var_10]
0x180012cbb  xor     rcx, rsp; StackCookie
0x180012cbe  call    __security_check_cookie
0x180012cc3  lea     r11, [rsp+270h+var_s0]
0x180012ccb  mov     rbx, [r11+20h]
0x180012ccf  mov     rdi, [r11+28h]
0x180012cd3  mov     rsp, r11
0x180012cd6  pop     rbp
0x180012cd7  retn
0x180012cd8  mov     r8, rdi
0x180012cdb  lea     rdx, [rsp+270h+var_240]
0x180012ce0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012ce5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180012cea  mov     ebx, eax
0x180012cec  test    eax, eax
0x180012cee  jns     short loc_180012C9C
0x180012cf0  mov     edx, 137h
0x180012cf5  jmp     loc_180012C67
```
