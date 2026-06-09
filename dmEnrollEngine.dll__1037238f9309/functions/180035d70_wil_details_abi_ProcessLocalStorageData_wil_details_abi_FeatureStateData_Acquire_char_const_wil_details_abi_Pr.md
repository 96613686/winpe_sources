# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180035d70`
- end: `0x180035edd`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001a204`

## callees

- `0x1800067a0`
- `0x18000fd8c`
- `0x180011938`
- `0x1800212dc`
- `0x18002c648`
- `0x18002c664`
- `0x18002e1a0`
- `0x1800330b8`
- `0x180033468`
- `0x180035d70`
- `0x1800386ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035ded`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035ded`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035da8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035da8`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
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
      v12,
      0,
      0xFFFFFFFFLL);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
0x180035d70  mov     [rsp-8+arg_10], rbx
0x180035d75  mov     [rsp-8+arg_18], rdi
0x180035d7a  push    rbp
0x180035d7b  lea     rbp, [rsp-170h]
0x180035d83  sub     rsp, 270h
0x180035d8a  mov     rax, cs:__security_cookie
0x180035d91  xor     rax, rsp
0x180035d94  mov     [rbp+170h+var_10], rax
0x180035d9b  mov     rdi, rdx
0x180035d9e  mov     qword ptr [rdx], 0
0x180035da5  mov     rbx, rcx
0x180035da8  call    cs:__imp_GetCurrentProcessId
0x180035dae  mov     [rsp+270h+var_248], rbx
0x180035db3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180035dba  mov     r9d, eax
0x180035dbd  mov     [rsp+270h+var_250], 130h; int
0x180035dc5  mov     edx, 104h; unsigned __int64
0x180035dca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035dcf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035dd4  mov     r9d, 1F0001h; dwDesiredAccess
0x180035dda  mov     [rsp+270h+var_240], 0
0x180035de3  xor     r8d, r8d; dwFlags
0x180035de6  lea     rdx, [rsp+270h+Name]; lpName
0x180035deb  xor     ecx, ecx; lpMutexAttributes
0x180035ded  call    cs:__imp_CreateMutexExW
0x180035df3  mov     rdx, rax
0x180035df6  lea     rcx, [rsp+270h+var_240]
0x180035dfb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180035e00  cmp     [rsp+270h+var_240], 0
0x180035e06  jnz     short loc_180035E11
0x180035e08  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180035e0d  mov     ebx, eax
0x180035e0f  jmp     short loc_180035E8B
0x180035e11  or      r9d, 0FFFFFFFFh
0x180035e15  lea     rdx, [rsp+270h+var_238]
0x180035e1a  xor     r8d, r8d
0x180035e1d  lea     rcx, [rsp+270h+var_240]
0x180035e22  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180035e27  lea     rdx, [rsp+270h+var_230]; void **
0x180035e2c  mov     [rsp+270h+var_230], 0
0x180035e35  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035e3a  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180035e3f  mov     ebx, eax
0x180035e41  test    eax, eax
0x180035e43  jns     short loc_180035E6C
0x180035e45  mov     edx, 12Eh; void *
0x180035e4a  mov     rcx, [rbp+178h]; this
0x180035e51  lea     r8, aWil; "wil"
0x180035e58  mov     r9d, eax; char *
0x180035e5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e60  lea     rcx, [rsp+270h+var_238]
0x180035e65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035e6a  jmp     short loc_180035E8B
0x180035e6c  mov     rcx, [rsp+270h+var_230]
0x180035e71  test    rcx, rcx
0x180035e74  jz      short loc_180035EBB
0x180035e76  mov     [rdi], rcx
0x180035e79  mov     eax, [rcx]
0x180035e7b  inc     eax
0x180035e7d  mov     [rcx], eax
0x180035e7f  lea     rcx, [rsp+270h+var_238]
0x180035e84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035e89  xor     ebx, ebx
0x180035e8b  lea     rcx, [rsp+270h+var_240]
0x180035e90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035e95  mov     eax, ebx
0x180035e97  mov     rcx, [rbp+170h+var_10]
0x180035e9e  xor     rcx, rsp; StackCookie
0x180035ea1  call    __security_check_cookie
0x180035ea6  lea     r11, [rsp+270h+var_s0]
0x180035eae  mov     rbx, [r11+20h]
0x180035eb2  mov     rdi, [r11+28h]
0x180035eb6  mov     rsp, r11
0x180035eb9  pop     rbp
0x180035eba  retn
0x180035ebb  mov     r8, rdi
0x180035ebe  lea     rdx, [rsp+270h+var_240]
0x180035ec3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035ec8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180035ecd  mov     ebx, eax
0x180035ecf  test    eax, eax
0x180035ed1  jns     short loc_180035E7F
0x180035ed3  mov     edx, 137h
0x180035ed8  jmp     loc_180035E4A
```
