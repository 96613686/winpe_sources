# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800c6b3c`
- end: `0x1800c6cb1`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c6f68`

## callees

- `0x18003ce84`
- `0x18008a7e8`
- `0x18008b5f0`
- `0x1800c681c`
- `0x1800c683c`
- `0x1800c6b3c`
- `0x1800c8320`
- `0x1800c9030`
- `0x1800c9618`
- `0x1800ca294`
- `0x1800ca36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c6bbf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800c6bbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c6b74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c6b74`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
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
0x1800c6b3c  mov     [rsp-8+arg_10], rbx
0x1800c6b41  mov     [rsp-8+arg_18], rdi
0x1800c6b46  push    rbp
0x1800c6b47  lea     rbp, [rsp-170h]
0x1800c6b4f  sub     rsp, 270h
0x1800c6b56  mov     rax, cs:__security_cookie
0x1800c6b5d  xor     rax, rsp
0x1800c6b60  mov     [rbp+170h+var_10], rax
0x1800c6b67  mov     rdi, rdx
0x1800c6b6a  mov     qword ptr [rdx], 0
0x1800c6b71  mov     rbx, rcx
0x1800c6b74  call    cs:__imp_GetCurrentProcessId
0x1800c6b7b  nop     dword ptr [rax+rax+00h]
0x1800c6b80  mov     [rsp+270h+var_248], rbx
0x1800c6b85  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800c6b8c  mov     r9d, eax
0x1800c6b8f  mov     [rsp+270h+var_250], 130h; int
0x1800c6b97  mov     edx, 104h; cchDest
0x1800c6b9c  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800c6ba1  call    StringCchPrintfW
0x1800c6ba6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800c6bac  mov     [rsp+270h+var_240], 0
0x1800c6bb5  xor     r8d, r8d; dwFlags
0x1800c6bb8  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800c6bbd  xor     ecx, ecx; lpMutexAttributes
0x1800c6bbf  call    cs:__imp_CreateMutexExW
0x1800c6bc6  nop     dword ptr [rax+rax+00h]
0x1800c6bcb  mov     rdx, rax
0x1800c6bce  lea     rcx, [rsp+270h+var_240]
0x1800c6bd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c6bd8  cmp     [rsp+270h+var_240], 0
0x1800c6bde  jnz     short loc_1800C6BE9
0x1800c6be0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800c6be5  mov     ebx, eax
0x1800c6be7  jmp     short loc_1800C6C5E
0x1800c6be9  lea     rdx, [rsp+270h+var_238]
0x1800c6bee  mov     [rsp+270h+var_238], 0
0x1800c6bf7  lea     rcx, [rsp+270h+var_240]
0x1800c6bfc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800c6c01  lea     rdx, [rsp+270h+var_230]; void **
0x1800c6c06  mov     [rsp+270h+var_230], 0
0x1800c6c0f  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800c6c14  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800c6c19  mov     ebx, eax
0x1800c6c1b  test    eax, eax
0x1800c6c1d  jns     short loc_1800C6C3F
0x1800c6c1f  mov     edx, 12Eh; void *
0x1800c6c24  mov     rcx, [rbp+178h]; this
0x1800c6c2b  mov     r9d, eax; char *
0x1800c6c2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6c33  lea     rcx, [rsp+270h+var_238]
0x1800c6c38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6c3d  jmp     short loc_1800C6C5E
0x1800c6c3f  mov     rcx, [rsp+270h+var_230]
0x1800c6c44  test    rcx, rcx
0x1800c6c47  jz      short loc_1800C6C8F
0x1800c6c49  mov     [rdi], rcx
0x1800c6c4c  mov     eax, [rcx]
0x1800c6c4e  inc     eax
0x1800c6c50  mov     [rcx], eax
0x1800c6c52  lea     rcx, [rsp+270h+var_238]
0x1800c6c57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6c5c  xor     ebx, ebx
0x1800c6c5e  lea     rcx, [rsp+270h+var_240]
0x1800c6c63  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c6c68  mov     eax, ebx
0x1800c6c6a  mov     rcx, [rbp+170h+var_10]
0x1800c6c71  xor     rcx, rsp; StackCookie
0x1800c6c74  call    __security_check_cookie
0x1800c6c79  lea     r11, [rsp+270h+var_s0]
0x1800c6c81  mov     rbx, [r11+20h]
0x1800c6c85  mov     rdi, [r11+28h]
0x1800c6c89  mov     rsp, r11
0x1800c6c8c  pop     rbp
0x1800c6c8d  retn
0x1800c6c8f  mov     r8, rdi
0x1800c6c92  lea     rdx, [rsp+270h+var_240]
0x1800c6c97  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800c6c9c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800c6ca1  mov     ebx, eax
0x1800c6ca3  test    eax, eax
0x1800c6ca5  jns     short loc_1800C6C52
0x1800c6ca7  mov     edx, 137h
0x1800c6cac  jmp     loc_1800C6C24
```
