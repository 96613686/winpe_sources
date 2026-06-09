# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180037c28`
- end: `0x180037d8a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180038c2c`

## callees

- `0x18002fb50`
- `0x180037954`
- `0x180037970`
- `0x180037c28`
- `0x180038958`
- `0x180039640`
- `0x18003a3ec`
- `0x18003ab7c`
- `0x18003aff8`
- `0x18003b7e4`
- `0x18003b97c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037c60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037c60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180037ca5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180037ca5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180037c28  mov     [rsp-8+arg_10], rbx
0x180037c2d  mov     [rsp-8+arg_18], rdi
0x180037c32  push    rbp
0x180037c33  lea     rbp, [rsp-170h]
0x180037c3b  sub     rsp, 270h
0x180037c42  mov     rax, cs:__security_cookie
0x180037c49  xor     rax, rsp
0x180037c4c  mov     [rbp+170h+var_10], rax
0x180037c53  mov     rdi, rdx
0x180037c56  mov     rbx, rcx
0x180037c59  mov     qword ptr [rdx], 0
0x180037c60  call    cs:__imp_GetCurrentProcessId
0x180037c66  mov     r9d, eax
0x180037c69  mov     [rsp+270h+var_248], rbx
0x180037c6e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180037c76  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180037c7d  mov     edx, 104h; unsigned __int64
0x180037c82  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037c87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037c8c  mov     [rsp+270h+var_240], 0
0x180037c95  mov     r9d, 1F0001h; dwDesiredAccess
0x180037c9b  xor     r8d, r8d; dwFlags
0x180037c9e  lea     rdx, [rsp+270h+Name]; lpName
0x180037ca3  xor     ecx, ecx; lpMutexAttributes
0x180037ca5  call    cs:__imp_CreateMutexExW
0x180037cab  mov     rdx, rax
0x180037cae  lea     rcx, [rsp+270h+var_240]
0x180037cb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180037cb8  cmp     [rsp+270h+var_240], 0
0x180037cbe  jnz     short loc_180037CC9
0x180037cc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180037cc5  mov     ebx, eax
0x180037cc7  jmp     short loc_180037D37
0x180037cc9  lea     rdx, [rsp+270h+var_238]
0x180037cce  lea     rcx, [rsp+270h+var_240]
0x180037cd3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180037cd8  nop
0x180037cd9  mov     [rsp+270h+var_230], 0
0x180037ce2  lea     rdx, [rsp+270h+var_230]; void **
0x180037ce7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037cec  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180037cf1  mov     ebx, eax
0x180037cf3  test    eax, eax
0x180037cf5  jns     short loc_180037D18
0x180037cf7  mov     edx, 12Eh; void *
0x180037cfc  mov     r9d, eax; char *
0x180037cff  mov     rcx, [rbp+178h]; this
0x180037d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d0b  nop
0x180037d0c  lea     rcx, [rsp+270h+var_238]
0x180037d11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037d16  jmp     short loc_180037D37
0x180037d18  mov     rcx, [rsp+270h+var_230]
0x180037d1d  test    rcx, rcx
0x180037d20  jz      short loc_180037D67
0x180037d22  mov     [rdi], rcx
0x180037d25  mov     eax, [rcx]
0x180037d27  inc     eax
0x180037d29  mov     [rcx], eax
0x180037d2b  lea     rcx, [rsp+270h+var_238]
0x180037d30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037d35  xor     ebx, ebx
0x180037d37  lea     rcx, [rsp+270h+var_240]
0x180037d3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037d41  mov     eax, ebx
0x180037d43  mov     rcx, [rbp+170h+var_10]
0x180037d4a  xor     rcx, rsp; StackCookie
0x180037d4d  call    __security_check_cookie
0x180037d52  lea     r11, [rsp+270h+var_s0]
0x180037d5a  mov     rbx, [r11+20h]
0x180037d5e  mov     rdi, [r11+28h]
0x180037d62  mov     rsp, r11
0x180037d65  pop     rbp
0x180037d66  retn
0x180037d67  mov     r8, rdi
0x180037d6a  lea     rdx, [rsp+270h+var_240]
0x180037d6f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037d74  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180037d79  mov     ebx, eax
0x180037d7b  test    eax, eax
0x180037d7d  jns     short loc_180037D2B
0x180037d7f  mov     edx, 137h
0x180037d84  jmp     loc_180037CFC
```
