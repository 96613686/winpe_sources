# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003aac4`
- end: `0x18003ac33`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003b238`

## callees

- `0x180037378`
- `0x18003a668`
- `0x18003a688`
- `0x18003aac4`
- `0x18003cb50`
- `0x18003dadc`
- `0x18003e25c`
- `0x18003e3e8`
- `0x18003edd0`
- `0x18003eed4`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003aafc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003aafc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003ab47`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003ab47`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18003aac4  mov     [rsp-8+arg_10], rbx
0x18003aac9  mov     [rsp-8+arg_18], rdi
0x18003aace  push    rbp
0x18003aacf  lea     rbp, [rsp-170h]
0x18003aad7  sub     rsp, 270h
0x18003aade  mov     rax, cs:__security_cookie
0x18003aae5  xor     rax, rsp
0x18003aae8  mov     [rbp+170h+var_10], rax
0x18003aaef  mov     rdi, rdx
0x18003aaf2  mov     rbx, rcx
0x18003aaf5  mov     qword ptr [rdx], 0
0x18003aafc  call    cs:__imp_GetCurrentProcessId
0x18003ab03  nop     dword ptr [rax+rax+00h]
0x18003ab08  mov     r9d, eax
0x18003ab0b  mov     [rsp+270h+var_248], rbx
0x18003ab10  mov     [rsp+270h+var_250], 130h; int
0x18003ab18  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003ab1f  mov     edx, 104h; unsigned __int64
0x18003ab24  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003ab29  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ab2e  mov     [rsp+270h+var_240], 0
0x18003ab37  mov     r9d, 1F0001h; dwDesiredAccess
0x18003ab3d  xor     r8d, r8d; dwFlags
0x18003ab40  lea     rdx, [rsp+270h+Name]; lpName
0x18003ab45  xor     ecx, ecx; lpMutexAttributes
0x18003ab47  call    cs:__imp_CreateMutexExW
0x18003ab4e  nop     dword ptr [rax+rax+00h]
0x18003ab53  mov     rdx, rax
0x18003ab56  lea     rcx, [rsp+270h+var_240]
0x18003ab5b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003ab60  cmp     [rsp+270h+var_240], 0
0x18003ab66  jnz     short loc_18003AB71
0x18003ab68  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003ab6d  mov     ebx, eax
0x18003ab6f  jmp     short loc_18003ABDF
0x18003ab71  lea     rdx, [rsp+270h+var_238]
0x18003ab76  lea     rcx, [rsp+270h+var_240]
0x18003ab7b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003ab80  nop
0x18003ab81  mov     [rsp+270h+var_230], 0
0x18003ab8a  lea     rdx, [rsp+270h+var_230]; void **
0x18003ab8f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003ab94  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003ab99  mov     ebx, eax
0x18003ab9b  test    eax, eax
0x18003ab9d  jns     short loc_18003ABC0
0x18003ab9f  mov     edx, 12Eh; void *
0x18003aba4  mov     r9d, eax; char *
0x18003aba7  mov     rcx, [rbp+178h]; this
0x18003abae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abb3  nop
0x18003abb4  lea     rcx, [rsp+270h+var_238]
0x18003abb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003abbe  jmp     short loc_18003ABDF
0x18003abc0  mov     rcx, [rsp+270h+var_230]
0x18003abc5  test    rcx, rcx
0x18003abc8  jz      short loc_18003AC10
0x18003abca  mov     [rdi], rcx
0x18003abcd  mov     eax, [rcx]
0x18003abcf  inc     eax
0x18003abd1  mov     [rcx], eax
0x18003abd3  lea     rcx, [rsp+270h+var_238]
0x18003abd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003abdd  xor     ebx, ebx
0x18003abdf  lea     rcx, [rsp+270h+var_240]
0x18003abe4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003abe9  mov     eax, ebx
0x18003abeb  mov     rcx, [rbp+170h+var_10]
0x18003abf2  xor     rcx, rsp; StackCookie
0x18003abf5  call    __security_check_cookie
0x18003abfa  lea     r11, [rsp+270h+var_s0]
0x18003ac02  mov     rbx, [r11+20h]
0x18003ac06  mov     rdi, [r11+28h]
0x18003ac0a  mov     rsp, r11
0x18003ac0d  pop     rbp
0x18003ac0e  retn
0x18003ac10  mov     r8, rdi
0x18003ac13  lea     rdx, [rsp+270h+var_240]
0x18003ac18  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003ac1d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003ac22  mov     ebx, eax
0x18003ac24  test    eax, eax
0x18003ac26  jns     short loc_18003ABD3
0x18003ac28  mov     edx, 137h
0x18003ac2d  jmp     loc_18003ABA4
```
