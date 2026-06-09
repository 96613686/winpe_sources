# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800080dc`
- end: `0x180008242`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800091a4`

## callees

- `0x180001640`
- `0x180007ca0`
- `0x180007cbc`
- `0x1800080dc`
- `0x180008e78`
- `0x180009bd0`
- `0x18000b18c`
- `0x18000b8c8`
- `0x18000bcf8`
- `0x18000c5c4`
- `0x18000ca8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008114`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008114`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008159`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008159`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800080dc  mov     [rsp-8+arg_10], rbx
0x1800080e1  mov     [rsp-8+arg_18], rdi
0x1800080e6  push    rbp
0x1800080e7  lea     rbp, [rsp-170h]
0x1800080ef  sub     rsp, 270h
0x1800080f6  mov     rax, cs:__security_cookie
0x1800080fd  xor     rax, rsp
0x180008100  mov     [rbp+170h+var_10], rax
0x180008107  mov     rdi, rdx
0x18000810a  mov     qword ptr [rdx], 0
0x180008111  mov     rbx, rcx
0x180008114  call    cs:__imp_GetCurrentProcessId
0x18000811a  mov     [rsp+270h+var_248], rbx
0x18000811f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008126  mov     r9d, eax
0x180008129  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180008131  mov     edx, 104h; unsigned __int64
0x180008136  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000813b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008140  mov     r9d, 1F0001h; dwDesiredAccess
0x180008146  mov     [rsp+270h+var_240], 0
0x18000814f  xor     r8d, r8d; dwFlags
0x180008152  lea     rdx, [rsp+270h+Name]; lpName
0x180008157  xor     ecx, ecx; lpMutexAttributes
0x180008159  call    cs:__imp_CreateMutexExW
0x18000815f  mov     rdx, rax
0x180008162  lea     rcx, [rsp+270h+var_240]
0x180008167  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000816c  cmp     [rsp+270h+var_240], 0
0x180008172  jnz     short loc_18000817D
0x180008174  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008179  mov     ebx, eax
0x18000817b  jmp     short loc_1800081F0
0x18000817d  lea     rdx, [rsp+270h+var_238]
0x180008182  lea     rcx, [rsp+270h+var_240]
0x180008187  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000818c  lea     rdx, [rsp+270h+var_230]; void **
0x180008191  mov     [rsp+270h+var_230], 0
0x18000819a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000819f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800081a4  mov     ebx, eax
0x1800081a6  test    eax, eax
0x1800081a8  jns     short loc_1800081D1
0x1800081aa  mov     edx, 12Eh; void *
0x1800081af  mov     rcx, [rbp+178h]; this
0x1800081b6  lea     r8, aWil; "wil"
0x1800081bd  mov     r9d, eax; char *
0x1800081c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081c5  lea     rcx, [rsp+270h+var_238]
0x1800081ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081cf  jmp     short loc_1800081F0
0x1800081d1  mov     rcx, [rsp+270h+var_230]
0x1800081d6  test    rcx, rcx
0x1800081d9  jz      short loc_180008220
0x1800081db  mov     [rdi], rcx
0x1800081de  mov     eax, [rcx]
0x1800081e0  inc     eax
0x1800081e2  mov     [rcx], eax
0x1800081e4  lea     rcx, [rsp+270h+var_238]
0x1800081e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081ee  xor     ebx, ebx
0x1800081f0  lea     rcx, [rsp+270h+var_240]
0x1800081f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081fa  mov     eax, ebx
0x1800081fc  mov     rcx, [rbp+170h+var_10]
0x180008203  xor     rcx, rsp; StackCookie
0x180008206  call    __security_check_cookie
0x18000820b  lea     r11, [rsp+270h+var_s0]
0x180008213  mov     rbx, [r11+20h]
0x180008217  mov     rdi, [r11+28h]
0x18000821b  mov     rsp, r11
0x18000821e  pop     rbp
0x18000821f  retn
0x180008220  mov     r8, rdi
0x180008223  lea     rdx, [rsp+270h+var_240]
0x180008228  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000822d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008232  mov     ebx, eax
0x180008234  test    eax, eax
0x180008236  jns     short loc_1800081E4
0x180008238  mov     edx, 137h
0x18000823d  jmp     loc_1800081AF
```
