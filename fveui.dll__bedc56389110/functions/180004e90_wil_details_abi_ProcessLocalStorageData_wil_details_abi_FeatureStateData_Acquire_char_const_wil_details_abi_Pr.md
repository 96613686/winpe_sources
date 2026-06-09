# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004e90`
- end: `0x180004fef`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008634`

## callees

- `0x180001bb0`
- `0x1800047f0`
- `0x18000480c`
- `0x180004e90`
- `0x180008f04`
- `0x180009f30`
- `0x18000b18c`
- `0x18000b9f8`
- `0x18000bf88`
- `0x18000d764`
- `0x18000da88`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180004f0d`
- `KERNEL32!CreateMutexExW` at `0x180004f0d`
- `KERNEL32!GetCurrentProcessId` at `0x180004ec8`
- `KERNEL32!GetCurrentProcessId` at `0x180004ec8`

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
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004e90  mov     [rsp-8+arg_10], rbx
0x180004e95  mov     [rsp-8+arg_18], rdi
0x180004e9a  push    rbp
0x180004e9b  lea     rbp, [rsp-170h]
0x180004ea3  sub     rsp, 270h
0x180004eaa  mov     rax, cs:__security_cookie
0x180004eb1  xor     rax, rsp
0x180004eb4  mov     [rbp+170h+var_10], rax
0x180004ebb  mov     rdi, rdx
0x180004ebe  mov     qword ptr [rdx], 0
0x180004ec5  mov     rbx, rcx
0x180004ec8  call    cs:__imp_GetCurrentProcessId
0x180004ece  mov     [rsp+270h+var_248], rbx
0x180004ed3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004eda  mov     r9d, eax
0x180004edd  mov     [rsp+270h+var_250], 130h; int
0x180004ee5  mov     edx, 104h; unsigned __int64
0x180004eea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004eef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ef4  mov     r9d, 1F0001h; dwDesiredAccess
0x180004efa  mov     [rsp+270h+var_240], 0
0x180004f03  xor     r8d, r8d; dwFlags
0x180004f06  lea     rdx, [rsp+270h+Name]; lpName
0x180004f0b  xor     ecx, ecx; lpMutexAttributes
0x180004f0d  call    cs:__imp_CreateMutexExW
0x180004f13  mov     rdx, rax
0x180004f16  lea     rcx, [rsp+270h+var_240]
0x180004f1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004f20  cmp     [rsp+270h+var_240], 0
0x180004f26  jnz     short loc_180004F31
0x180004f28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004f2d  mov     ebx, eax
0x180004f2f  jmp     short loc_180004F9D
0x180004f31  lea     rdx, [rsp+270h+var_238]
0x180004f36  lea     rcx, [rsp+270h+var_240]
0x180004f3b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004f40  lea     rdx, [rsp+270h+var_230]; void **
0x180004f45  mov     [rsp+270h+var_230], 0
0x180004f4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004f53  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004f58  mov     ebx, eax
0x180004f5a  test    eax, eax
0x180004f5c  jns     short loc_180004F7E
0x180004f5e  mov     edx, 12Eh; void *
0x180004f63  mov     rcx, [rbp+178h]; this
0x180004f6a  mov     r9d, eax; char *
0x180004f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f72  lea     rcx, [rsp+270h+var_238]
0x180004f77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f7c  jmp     short loc_180004F9D
0x180004f7e  mov     rcx, [rsp+270h+var_230]
0x180004f83  test    rcx, rcx
0x180004f86  jz      short loc_180004FCD
0x180004f88  mov     [rdi], rcx
0x180004f8b  mov     eax, [rcx]
0x180004f8d  inc     eax
0x180004f8f  mov     [rcx], eax
0x180004f91  lea     rcx, [rsp+270h+var_238]
0x180004f96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f9b  xor     ebx, ebx
0x180004f9d  lea     rcx, [rsp+270h+var_240]
0x180004fa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004fa7  mov     eax, ebx
0x180004fa9  mov     rcx, [rbp+170h+var_10]
0x180004fb0  xor     rcx, rsp; StackCookie
0x180004fb3  call    __security_check_cookie
0x180004fb8  lea     r11, [rsp+270h+var_s0]
0x180004fc0  mov     rbx, [r11+20h]
0x180004fc4  mov     rdi, [r11+28h]
0x180004fc8  mov     rsp, r11
0x180004fcb  pop     rbp
0x180004fcc  retn
0x180004fcd  mov     r8, rdi
0x180004fd0  lea     rdx, [rsp+270h+var_240]
0x180004fd5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004fda  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004fdf  mov     ebx, eax
0x180004fe1  test    eax, eax
0x180004fe3  jns     short loc_180004F91
0x180004fe5  mov     edx, 137h
0x180004fea  jmp     loc_180004F63
```
