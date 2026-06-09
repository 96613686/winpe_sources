# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800968a0`
- end: `0x1800969f0`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b362c`

## callees

- `0x1800968a0`
- `0x18009f624`
- `0x18009f6dc`
- `0x18009f6f8`
- `0x18009f794`
- `0x1800a797c`
- `0x1800a7ad8`
- `0x1800a9d20`
- `0x1800b2a28`
- `0x1800b5078`
- `0x1800b5664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800968d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800968d8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009691d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18009691d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  int Pointer; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  void *v13; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-C0h] BYREF
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
  if ( !v12 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v12,
    v14);
  v13 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v13);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    v10 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v8, (const char *)(unsigned int)Pointer, 304);
    goto LABEL_8;
  }
  v11 = v13;
  if ( v13 )
  {
    *a2 = v13;
    ++*v11;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
    v9 = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 311;
      goto LABEL_11;
    }
  }
  v9 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return v9;
}

```

## disassembly

```asm
0x1800968a0  mov     [rsp-8+arg_10], rbx
0x1800968a5  mov     [rsp-8+arg_18], rdi
0x1800968aa  push    rbp
0x1800968ab  lea     rbp, [rsp-170h]
0x1800968b3  sub     rsp, 270h
0x1800968ba  mov     rax, cs:__security_cookie
0x1800968c1  xor     rax, rsp
0x1800968c4  mov     [rbp+170h+var_10], rax
0x1800968cb  mov     rdi, rdx
0x1800968ce  mov     qword ptr [rdx], 0
0x1800968d5  mov     rbx, rcx
0x1800968d8  call    cs:__imp_GetCurrentProcessId
0x1800968de  mov     [rsp+270h+var_248], rbx
0x1800968e3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800968ea  mov     r9d, eax
0x1800968ed  mov     [rsp+270h+var_250], 130h; int
0x1800968f5  mov     edx, 104h; cchDest
0x1800968fa  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800968ff  call    StringCchPrintfW
0x180096904  mov     r9d, 1F0001h; dwDesiredAccess
0x18009690a  mov     [rsp+270h+var_240], 0
0x180096913  xor     r8d, r8d; dwFlags
0x180096916  lea     rdx, [rsp+270h+pszDest]; lpName
0x18009691b  xor     ecx, ecx; lpMutexAttributes
0x18009691d  call    cs:__imp_CreateMutexExW
0x180096923  mov     rdx, rax
0x180096926  lea     rcx, [rsp+270h+var_240]
0x18009692b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180096930  cmp     [rsp+270h+var_240], 0
0x180096936  jnz     short loc_18009693F
0x180096938  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009693d  jmp     short loc_18009699E
0x18009693f  lea     rdx, [rsp+270h+var_230]
0x180096944  lea     rcx, [rsp+270h+var_240]
0x180096949  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18009694e  lea     rdx, [rsp+270h+var_238]; void **
0x180096953  mov     [rsp+270h+var_238], 0
0x18009695c  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180096961  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180096966  mov     ebx, eax
0x180096968  test    eax, eax
0x18009696a  jns     short loc_180096973
0x18009696c  mov     edx, 12Eh
0x180096971  jmp     short loc_1800969DF
0x180096973  mov     rcx, [rsp+270h+var_238]
0x180096978  test    rcx, rcx
0x18009697b  jz      short loc_1800969C2
0x18009697d  mov     [rdi], rcx
0x180096980  mov     eax, [rcx]
0x180096982  inc     eax
0x180096984  mov     [rcx], eax
0x180096986  xor     ebx, ebx
0x180096988  lea     rcx, [rsp+270h+var_230]
0x18009698d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180096992  lea     rcx, [rsp+270h+var_240]
0x180096997  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009699c  mov     eax, ebx
0x18009699e  mov     rcx, [rbp+170h+var_10]
0x1800969a5  xor     rcx, rsp; StackCookie
0x1800969a8  call    __security_check_cookie
0x1800969ad  lea     r11, [rsp+270h+var_s0]
0x1800969b5  mov     rbx, [r11+20h]
0x1800969b9  mov     rdi, [r11+28h]
0x1800969bd  mov     rsp, r11
0x1800969c0  pop     rbp
0x1800969c1  retn
0x1800969c2  mov     r8, rdi
0x1800969c5  lea     rdx, [rsp+270h+var_240]
0x1800969ca  lea     rcx, [rsp+270h+pszDest]
0x1800969cf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800969d4  mov     ebx, eax
0x1800969d6  test    eax, eax
0x1800969d8  jns     short loc_180096986
0x1800969da  mov     edx, 137h; void *
0x1800969df  mov     rcx, [rbp+178h]; this
0x1800969e6  mov     r9d, eax; char *
0x1800969e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800969ee  jmp     short loc_180096988
```
