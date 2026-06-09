# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003b258`
- end: `0x18003b3cb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003b60c`

## callees

- `0x18002d898`
- `0x18002dc28`
- `0x180038270`
- `0x18003ae60`
- `0x18003ae80`
- `0x18003b258`
- `0x18003c698`
- `0x18003dbb8`
- `0x18003df78`
- `0x18003e694`
- `0x18003eb10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003b2db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003b2db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b290`

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
      v12);
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
0x18003b258  mov     [rsp-8+arg_10], rbx
0x18003b25d  mov     [rsp-8+arg_18], rdi
0x18003b262  push    rbp
0x18003b263  lea     rbp, [rsp-170h]
0x18003b26b  sub     rsp, 270h
0x18003b272  mov     rax, cs:__security_cookie
0x18003b279  xor     rax, rsp
0x18003b27c  mov     [rbp+170h+var_10], rax
0x18003b283  mov     rdi, rdx
0x18003b286  mov     qword ptr [rdx], 0
0x18003b28d  mov     rbx, rcx
0x18003b290  call    cs:__imp_GetCurrentProcessId
0x18003b297  nop     dword ptr [rax+rax+00h]
0x18003b29c  mov     [rsp+270h+var_248], rbx
0x18003b2a1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003b2a8  mov     r9d, eax
0x18003b2ab  mov     [rsp+270h+var_250], 130h; int
0x18003b2b3  mov     edx, 104h; unsigned __int64
0x18003b2b8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b2bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b2c2  mov     r9d, 1F0001h; dwDesiredAccess
0x18003b2c8  mov     [rsp+270h+var_240], 0
0x18003b2d1  xor     r8d, r8d; dwFlags
0x18003b2d4  lea     rdx, [rsp+270h+Name]; lpName
0x18003b2d9  xor     ecx, ecx; lpMutexAttributes
0x18003b2db  call    cs:__imp_CreateMutexExW
0x18003b2e2  nop     dword ptr [rax+rax+00h]
0x18003b2e7  mov     rdx, rax
0x18003b2ea  lea     rcx, [rsp+270h+var_240]
0x18003b2ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003b2f4  cmp     [rsp+270h+var_240], 0
0x18003b2fa  jnz     short loc_18003B305
0x18003b2fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003b301  mov     ebx, eax
0x18003b303  jmp     short loc_18003B378
0x18003b305  lea     rdx, [rsp+270h+var_238]
0x18003b30a  lea     rcx, [rsp+270h+var_240]
0x18003b30f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003b314  lea     rdx, [rsp+270h+var_230]; void **
0x18003b319  mov     [rsp+270h+var_230], 0
0x18003b322  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b327  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003b32c  mov     ebx, eax
0x18003b32e  test    eax, eax
0x18003b330  jns     short loc_18003B359
0x18003b332  mov     edx, 12Eh; void *
0x18003b337  mov     rcx, [rbp+178h]; this
0x18003b33e  lea     r8, aWil; "wil"
0x18003b345  mov     r9d, eax; char *
0x18003b348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b34d  lea     rcx, [rsp+270h+var_238]
0x18003b352  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b357  jmp     short loc_18003B378
0x18003b359  mov     rcx, [rsp+270h+var_230]
0x18003b35e  test    rcx, rcx
0x18003b361  jz      short loc_18003B3A9
0x18003b363  mov     [rdi], rcx
0x18003b366  mov     eax, [rcx]
0x18003b368  inc     eax
0x18003b36a  mov     [rcx], eax
0x18003b36c  lea     rcx, [rsp+270h+var_238]
0x18003b371  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b376  xor     ebx, ebx
0x18003b378  lea     rcx, [rsp+270h+var_240]
0x18003b37d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b382  mov     eax, ebx
0x18003b384  mov     rcx, [rbp+170h+var_10]
0x18003b38b  xor     rcx, rsp; StackCookie
0x18003b38e  call    __security_check_cookie
0x18003b393  lea     r11, [rsp+270h+var_s0]
0x18003b39b  mov     rbx, [r11+20h]
0x18003b39f  mov     rdi, [r11+28h]
0x18003b3a3  mov     rsp, r11
0x18003b3a6  pop     rbp
0x18003b3a7  retn
0x18003b3a9  mov     r8, rdi
0x18003b3ac  lea     rdx, [rsp+270h+var_240]
0x18003b3b1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b3b6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003b3bb  mov     ebx, eax
0x18003b3bd  test    eax, eax
0x18003b3bf  jns     short loc_18003B36C
0x18003b3c1  mov     edx, 137h
0x18003b3c6  jmp     loc_18003B337
```
