# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800c69c0`
- end: `0x1800c6b35`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c79ec`

## callees

- `0x18003ce84`
- `0x18008a7e8`
- `0x18008b5f0`
- `0x1800c681c`
- `0x1800c683c`
- `0x1800c69c0`
- `0x1800c81f4`
- `0x1800c9030`
- `0x1800c9618`
- `0x1800ca294`
- `0x1800ca36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c6a43`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c6a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c69f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c69f8`

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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x1800c69c0  mov     [rsp-8+arg_10], rbx
0x1800c69c5  mov     [rsp-8+arg_18], rdi
0x1800c69ca  push    rbp
0x1800c69cb  lea     rbp, [rsp-170h]
0x1800c69d3  sub     rsp, 270h
0x1800c69da  mov     rax, cs:__security_cookie
0x1800c69e1  xor     rax, rsp
0x1800c69e4  mov     [rbp+170h+var_10], rax
0x1800c69eb  mov     rdi, rdx
0x1800c69ee  mov     qword ptr [rdx], 0
0x1800c69f5  mov     rbx, rcx
0x1800c69f8  call    cs:__imp_GetCurrentProcessId
0x1800c69ff  nop     dword ptr [rax+rax+00h]
0x1800c6a04  mov     [rsp+270h+var_248], rbx
0x1800c6a09  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800c6a10  mov     r9d, eax
0x1800c6a13  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800c6a1b  mov     edx, 104h; cchDest
0x1800c6a20  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800c6a25  call    StringCchPrintfW
0x1800c6a2a  mov     r9d, 1F0001h; dwDesiredAccess
0x1800c6a30  mov     [rsp+270h+var_240], 0
0x1800c6a39  xor     r8d, r8d; dwFlags
0x1800c6a3c  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800c6a41  xor     ecx, ecx; lpMutexAttributes
0x1800c6a43  call    cs:__imp_CreateMutexExW
0x1800c6a4a  nop     dword ptr [rax+rax+00h]
0x1800c6a4f  mov     rdx, rax
0x1800c6a52  lea     rcx, [rsp+270h+var_240]
0x1800c6a57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c6a5c  cmp     [rsp+270h+var_240], 0
0x1800c6a62  jnz     short loc_1800C6A6D
0x1800c6a64  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800c6a69  mov     ebx, eax
0x1800c6a6b  jmp     short loc_1800C6AE2
0x1800c6a6d  lea     rdx, [rsp+270h+var_238]
0x1800c6a72  mov     [rsp+270h+var_238], 0
0x1800c6a7b  lea     rcx, [rsp+270h+var_240]
0x1800c6a80  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800c6a85  lea     rdx, [rsp+270h+var_230]; void **
0x1800c6a8a  mov     [rsp+270h+var_230], 0
0x1800c6a93  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800c6a98  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800c6a9d  mov     ebx, eax
0x1800c6a9f  test    eax, eax
0x1800c6aa1  jns     short loc_1800C6AC3
0x1800c6aa3  mov     edx, 12Eh; void *
0x1800c6aa8  mov     rcx, [rbp+178h]; this
0x1800c6aaf  mov     r9d, eax; char *
0x1800c6ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6ab7  lea     rcx, [rsp+270h+var_238]
0x1800c6abc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6ac1  jmp     short loc_1800C6AE2
0x1800c6ac3  mov     rcx, [rsp+270h+var_230]
0x1800c6ac8  test    rcx, rcx
0x1800c6acb  jz      short loc_1800C6B13
0x1800c6acd  mov     [rdi], rcx
0x1800c6ad0  mov     eax, [rcx]
0x1800c6ad2  inc     eax
0x1800c6ad4  mov     [rcx], eax
0x1800c6ad6  lea     rcx, [rsp+270h+var_238]
0x1800c6adb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6ae0  xor     ebx, ebx
0x1800c6ae2  lea     rcx, [rsp+270h+var_240]
0x1800c6ae7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6aec  mov     eax, ebx
0x1800c6aee  mov     rcx, [rbp+170h+var_10]
0x1800c6af5  xor     rcx, rsp; StackCookie
0x1800c6af8  call    __security_check_cookie
0x1800c6afd  lea     r11, [rsp+270h+var_s0]
0x1800c6b05  mov     rbx, [r11+20h]
0x1800c6b09  mov     rdi, [r11+28h]
0x1800c6b0d  mov     rsp, r11
0x1800c6b10  pop     rbp
0x1800c6b11  retn
0x1800c6b13  mov     r8, rdi
0x1800c6b16  lea     rdx, [rsp+270h+var_240]
0x1800c6b1b  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800c6b20  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800c6b25  mov     ebx, eax
0x1800c6b27  test    eax, eax
0x1800c6b29  jns     short loc_1800C6AD6
0x1800c6b2b  mov     edx, 137h
0x1800c6b30  jmp     loc_1800C6AA8
```
