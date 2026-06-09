# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001f540`
- end: `0x18001f6a2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001fb50`

## callees

- `0x180012690`
- `0x180013b20`
- `0x18001f100`
- `0x18001f11c`
- `0x18001f540`
- `0x180020e98`
- `0x180021b7c`
- `0x180022588`
- `0x180022d74`
- `0x180022f0c`
- `0x1800234f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f5bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f578`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f578`

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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
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
0x18001f540  mov     [rsp-8+arg_10], rbx
0x18001f545  mov     [rsp-8+arg_18], rdi
0x18001f54a  push    rbp
0x18001f54b  lea     rbp, [rsp-170h]
0x18001f553  sub     rsp, 270h
0x18001f55a  mov     rax, cs:__security_cookie
0x18001f561  xor     rax, rsp
0x18001f564  mov     [rbp+170h+var_10], rax
0x18001f56b  mov     rdi, rdx
0x18001f56e  mov     rbx, rcx
0x18001f571  mov     qword ptr [rdx], 0
0x18001f578  call    cs:__imp_GetCurrentProcessId
0x18001f57e  mov     r9d, eax
0x18001f581  mov     [rsp+270h+var_248], rbx
0x18001f586  mov     [rsp+270h+var_250], 130h; int
0x18001f58e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f595  mov     edx, 104h; cchDest
0x18001f59a  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001f59f  call    StringCchPrintfW
0x18001f5a4  mov     [rsp+270h+var_240], 0
0x18001f5ad  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f5b3  xor     r8d, r8d; dwFlags
0x18001f5b6  lea     rdx, [rsp+270h+pszDest]; lpName
0x18001f5bb  xor     ecx, ecx; lpMutexAttributes
0x18001f5bd  call    cs:__imp_CreateMutexExW
0x18001f5c3  mov     rdx, rax
0x18001f5c6  lea     rcx, [rsp+270h+var_240]
0x18001f5cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f5d0  cmp     [rsp+270h+var_240], 0
0x18001f5d6  jnz     short loc_18001F5E1
0x18001f5d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f5dd  mov     ebx, eax
0x18001f5df  jmp     short loc_18001F64F
0x18001f5e1  lea     rdx, [rsp+270h+var_238]
0x18001f5e6  lea     rcx, [rsp+270h+var_240]
0x18001f5eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f5f0  nop
0x18001f5f1  mov     [rsp+270h+var_230], 0
0x18001f5fa  lea     rdx, [rsp+270h+var_230]; void **
0x18001f5ff  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001f604  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001f609  mov     ebx, eax
0x18001f60b  test    eax, eax
0x18001f60d  jns     short loc_18001F630
0x18001f60f  mov     edx, 12Eh; void *
0x18001f614  mov     r9d, eax; char *
0x18001f617  mov     rcx, [rbp+178h]; this
0x18001f61e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f623  nop
0x18001f624  lea     rcx, [rsp+270h+var_238]
0x18001f629  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f62e  jmp     short loc_18001F64F
0x18001f630  mov     rcx, [rsp+270h+var_230]
0x18001f635  test    rcx, rcx
0x18001f638  jz      short loc_18001F67F
0x18001f63a  mov     [rdi], rcx
0x18001f63d  mov     eax, [rcx]
0x18001f63f  inc     eax
0x18001f641  mov     [rcx], eax
0x18001f643  lea     rcx, [rsp+270h+var_238]
0x18001f648  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f64d  xor     ebx, ebx
0x18001f64f  lea     rcx, [rsp+270h+var_240]
0x18001f654  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f659  mov     eax, ebx
0x18001f65b  mov     rcx, [rbp+170h+var_10]
0x18001f662  xor     rcx, rsp; StackCookie
0x18001f665  call    __security_check_cookie
0x18001f66a  lea     r11, [rsp+270h+var_s0]
0x18001f672  mov     rbx, [r11+20h]
0x18001f676  mov     rdi, [r11+28h]
0x18001f67a  mov     rsp, r11
0x18001f67d  pop     rbp
0x18001f67e  retn
0x18001f67f  mov     r8, rdi
0x18001f682  lea     rdx, [rsp+270h+var_240]
0x18001f687  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001f68c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001f691  mov     ebx, eax
0x18001f693  test    eax, eax
0x18001f695  jns     short loc_18001F643
0x18001f697  mov     edx, 137h
0x18001f69c  jmp     loc_18001F614
```
