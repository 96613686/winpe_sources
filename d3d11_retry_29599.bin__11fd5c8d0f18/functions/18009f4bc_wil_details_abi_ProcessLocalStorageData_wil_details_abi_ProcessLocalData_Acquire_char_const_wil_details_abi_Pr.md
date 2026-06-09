# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18009f4bc`
- end: `0x18009f61b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b3794`

## callees

- `0x18009f4bc`
- `0x18009f624`
- `0x18009f6dc`
- `0x18009f6f8`
- `0x18009f794`
- `0x1800a7828`
- `0x1800a7ad8`
- `0x1800a9d20`
- `0x1800b2a28`
- `0x1800b5078`
- `0x1800b5664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f4f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009f4f4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f539`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009f539`

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
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
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
0x18009f4bc  mov     [rsp-8+arg_10], rbx
0x18009f4c1  mov     [rsp-8+arg_18], rdi
0x18009f4c6  push    rbp
0x18009f4c7  lea     rbp, [rsp-170h]
0x18009f4cf  sub     rsp, 270h
0x18009f4d6  mov     rax, cs:__security_cookie
0x18009f4dd  xor     rax, rsp
0x18009f4e0  mov     [rbp+170h+var_10], rax
0x18009f4e7  mov     rdi, rdx
0x18009f4ea  mov     qword ptr [rdx], 0
0x18009f4f1  mov     rbx, rcx
0x18009f4f4  call    cs:__imp_GetCurrentProcessId
0x18009f4fa  mov     [rsp+270h+var_248], rbx
0x18009f4ff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18009f506  mov     r9d, eax
0x18009f509  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18009f511  mov     edx, 104h; cchDest
0x18009f516  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18009f51b  call    StringCchPrintfW
0x18009f520  mov     r9d, 1F0001h; dwDesiredAccess
0x18009f526  mov     [rsp+270h+var_240], 0
0x18009f52f  xor     r8d, r8d; dwFlags
0x18009f532  lea     rdx, [rsp+270h+pszDest]; lpName
0x18009f537  xor     ecx, ecx; lpMutexAttributes
0x18009f539  call    cs:__imp_CreateMutexExW
0x18009f53f  mov     rdx, rax
0x18009f542  lea     rcx, [rsp+270h+var_240]
0x18009f547  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009f54c  cmp     [rsp+270h+var_240], 0
0x18009f552  jnz     short loc_18009F55D
0x18009f554  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009f559  mov     ebx, eax
0x18009f55b  jmp     short loc_18009F5C9
0x18009f55d  lea     rdx, [rsp+270h+var_238]
0x18009f562  lea     rcx, [rsp+270h+var_240]
0x18009f567  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18009f56c  lea     rdx, [rsp+270h+var_230]; void **
0x18009f571  mov     [rsp+270h+var_230], 0
0x18009f57a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18009f57f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18009f584  mov     ebx, eax
0x18009f586  test    eax, eax
0x18009f588  jns     short loc_18009F5AA
0x18009f58a  mov     edx, 12Eh; void *
0x18009f58f  mov     rcx, [rbp+178h]; this
0x18009f596  mov     r9d, eax; char *
0x18009f599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f59e  lea     rcx, [rsp+270h+var_238]
0x18009f5a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f5a8  jmp     short loc_18009F5C9
0x18009f5aa  mov     rcx, [rsp+270h+var_230]
0x18009f5af  test    rcx, rcx
0x18009f5b2  jz      short loc_18009F5F9
0x18009f5b4  mov     [rdi], rcx
0x18009f5b7  mov     eax, [rcx]
0x18009f5b9  inc     eax
0x18009f5bb  mov     [rcx], eax
0x18009f5bd  lea     rcx, [rsp+270h+var_238]
0x18009f5c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f5c7  xor     ebx, ebx
0x18009f5c9  lea     rcx, [rsp+270h+var_240]
0x18009f5ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009f5d3  mov     eax, ebx
0x18009f5d5  mov     rcx, [rbp+170h+var_10]
0x18009f5dc  xor     rcx, rsp; StackCookie
0x18009f5df  call    __security_check_cookie
0x18009f5e4  lea     r11, [rsp+270h+var_s0]
0x18009f5ec  mov     rbx, [r11+20h]
0x18009f5f0  mov     rdi, [r11+28h]
0x18009f5f4  mov     rsp, r11
0x18009f5f7  pop     rbp
0x18009f5f8  retn
0x18009f5f9  mov     r8, rdi
0x18009f5fc  lea     rdx, [rsp+270h+var_240]
0x18009f601  lea     rcx, [rsp+270h+pszDest]
0x18009f606  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18009f60b  mov     ebx, eax
0x18009f60d  test    eax, eax
0x18009f60f  jns     short loc_18009F5BD
0x18009f611  mov     edx, 137h
0x18009f616  jmp     loc_18009F58F
```
