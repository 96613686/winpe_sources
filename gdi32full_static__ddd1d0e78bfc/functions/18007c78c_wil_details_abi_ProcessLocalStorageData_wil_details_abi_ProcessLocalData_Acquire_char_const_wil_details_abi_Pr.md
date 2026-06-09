# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18007c78c`
- end: `0x18007c8fb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800877d0`

## callees

- `0x18006fb6c`
- `0x180074698`
- `0x18007c78c`
- `0x18007c910`
- `0x18007c930`
- `0x18007c964`
- `0x18007cb34`
- `0x18007de00`
- `0x18007e8cc`
- `0x18007f800`
- `0x180087b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c7c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c7c4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007c80f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007c80f`

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
0x18007c78c  mov     [rsp-8+arg_10], rbx
0x18007c791  mov     [rsp-8+arg_18], rdi
0x18007c796  push    rbp
0x18007c797  lea     rbp, [rsp-170h]
0x18007c79f  sub     rsp, 270h
0x18007c7a6  mov     rax, cs:__security_cookie
0x18007c7ad  xor     rax, rsp
0x18007c7b0  mov     [rbp+170h+var_10], rax
0x18007c7b7  mov     rdi, rdx
0x18007c7ba  mov     rbx, rcx
0x18007c7bd  mov     qword ptr [rdx], 0
0x18007c7c4  call    cs:__imp_GetCurrentProcessId
0x18007c7cb  nop     dword ptr [rax+rax+00h]
0x18007c7d0  mov     r9d, eax
0x18007c7d3  mov     [rsp+270h+var_248], rbx
0x18007c7d8  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18007c7e0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18007c7e7  mov     edx, 104h; unsigned __int64
0x18007c7ec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c7f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c7f6  mov     [rsp+270h+var_240], 0
0x18007c7ff  mov     r9d, 1F0001h; dwDesiredAccess
0x18007c805  xor     r8d, r8d; dwFlags
0x18007c808  lea     rdx, [rsp+270h+Name]; lpName
0x18007c80d  xor     ecx, ecx; lpMutexAttributes
0x18007c80f  call    cs:__imp_CreateMutexExW
0x18007c816  nop     dword ptr [rax+rax+00h]
0x18007c81b  mov     rdx, rax
0x18007c81e  lea     rcx, [rsp+270h+var_240]
0x18007c823  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007c828  cmp     [rsp+270h+var_240], 0
0x18007c82e  jnz     short loc_18007C839
0x18007c830  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007c835  mov     ebx, eax
0x18007c837  jmp     short loc_18007C8A7
0x18007c839  lea     rdx, [rsp+270h+var_238]
0x18007c83e  lea     rcx, [rsp+270h+var_240]
0x18007c843  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007c848  nop
0x18007c849  mov     [rsp+270h+var_230], 0
0x18007c852  lea     rdx, [rsp+270h+var_230]; void **
0x18007c857  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c85c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18007c861  mov     ebx, eax
0x18007c863  test    eax, eax
0x18007c865  jns     short loc_18007C888
0x18007c867  mov     edx, 12Eh; void *
0x18007c86c  mov     r9d, eax; char *
0x18007c86f  mov     rcx, [rbp+178h]; this
0x18007c876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c87b  nop
0x18007c87c  lea     rcx, [rsp+270h+var_238]
0x18007c881  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c886  jmp     short loc_18007C8A7
0x18007c888  mov     rcx, [rsp+270h+var_230]
0x18007c88d  test    rcx, rcx
0x18007c890  jz      short loc_18007C8D8
0x18007c892  mov     [rdi], rcx
0x18007c895  mov     eax, [rcx]
0x18007c897  inc     eax
0x18007c899  mov     [rcx], eax
0x18007c89b  lea     rcx, [rsp+270h+var_238]
0x18007c8a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c8a5  xor     ebx, ebx
0x18007c8a7  lea     rcx, [rsp+270h+var_240]
0x18007c8ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c8b1  mov     eax, ebx
0x18007c8b3  mov     rcx, [rbp+170h+var_10]
0x18007c8ba  xor     rcx, rsp; StackCookie
0x18007c8bd  call    __security_check_cookie
0x18007c8c2  lea     r11, [rsp+270h+var_s0]
0x18007c8ca  mov     rbx, [r11+20h]
0x18007c8ce  mov     rdi, [r11+28h]
0x18007c8d2  mov     rsp, r11
0x18007c8d5  pop     rbp
0x18007c8d6  retn
0x18007c8d8  mov     r8, rdi
0x18007c8db  lea     rdx, [rsp+270h+var_240]
0x18007c8e0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c8e5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007c8ea  mov     ebx, eax
0x18007c8ec  test    eax, eax
0x18007c8ee  jns     short loc_18007C89B
0x18007c8f0  mov     edx, 137h
0x18007c8f5  jmp     loc_18007C86C
```
