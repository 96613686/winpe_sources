# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180033b80`
- end: `0x180033cdf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003558c`

## callees

- `0x18000c318`
- `0x18001e4c0`
- `0x1800334c0`
- `0x1800334dc`
- `0x180033b80`
- `0x180034e78`
- `0x18003642c`
- `0x1800378dc`
- `0x18003842c`
- `0x180039f0c`
- `0x18003b090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033bfd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033bb8`

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
0x180033b80  mov     [rsp-8+arg_10], rbx
0x180033b85  mov     [rsp-8+arg_18], rdi
0x180033b8a  push    rbp
0x180033b8b  lea     rbp, [rsp-170h]
0x180033b93  sub     rsp, 270h
0x180033b9a  mov     rax, cs:__security_cookie
0x180033ba1  xor     rax, rsp
0x180033ba4  mov     [rbp+170h+var_10], rax
0x180033bab  mov     rdi, rdx
0x180033bae  mov     qword ptr [rdx], 0
0x180033bb5  mov     rbx, rcx
0x180033bb8  call    cs:__imp_GetCurrentProcessId
0x180033bbe  mov     [rsp+270h+var_248], rbx
0x180033bc3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180033bca  mov     r9d, eax
0x180033bcd  mov     [rsp+270h+var_250], 130h; int
0x180033bd5  mov     edx, 104h; unsigned __int64
0x180033bda  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033bdf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033be4  mov     r9d, 1F0001h; dwDesiredAccess
0x180033bea  mov     [rsp+270h+var_240], 0
0x180033bf3  xor     r8d, r8d; dwFlags
0x180033bf6  lea     rdx, [rsp+270h+Name]; lpName
0x180033bfb  xor     ecx, ecx; lpMutexAttributes
0x180033bfd  call    cs:__imp_CreateMutexExW
0x180033c03  mov     rdx, rax
0x180033c06  lea     rcx, [rsp+270h+var_240]
0x180033c0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180033c10  cmp     [rsp+270h+var_240], 0
0x180033c16  jnz     short loc_180033C21
0x180033c18  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180033c1d  mov     ebx, eax
0x180033c1f  jmp     short loc_180033C8D
0x180033c21  lea     rdx, [rsp+270h+var_238]
0x180033c26  lea     rcx, [rsp+270h+var_240]
0x180033c2b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180033c30  lea     rdx, [rsp+270h+var_230]; void **
0x180033c35  mov     [rsp+270h+var_230], 0
0x180033c3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033c43  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180033c48  mov     ebx, eax
0x180033c4a  test    eax, eax
0x180033c4c  jns     short loc_180033C6E
0x180033c4e  mov     edx, 12Eh; void *
0x180033c53  mov     rcx, [rbp+178h]; this
0x180033c5a  mov     r9d, eax; char *
0x180033c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c62  lea     rcx, [rsp+270h+var_238]
0x180033c67  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033c6c  jmp     short loc_180033C8D
0x180033c6e  mov     rcx, [rsp+270h+var_230]
0x180033c73  test    rcx, rcx
0x180033c76  jz      short loc_180033CBD
0x180033c78  mov     [rdi], rcx
0x180033c7b  mov     eax, [rcx]
0x180033c7d  inc     eax
0x180033c7f  mov     [rcx], eax
0x180033c81  lea     rcx, [rsp+270h+var_238]
0x180033c86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033c8b  xor     ebx, ebx
0x180033c8d  lea     rcx, [rsp+270h+var_240]
0x180033c92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033c97  mov     eax, ebx
0x180033c99  mov     rcx, [rbp+170h+var_10]
0x180033ca0  xor     rcx, rsp; StackCookie
0x180033ca3  call    __security_check_cookie
0x180033ca8  lea     r11, [rsp+270h+var_s0]
0x180033cb0  mov     rbx, [r11+20h]
0x180033cb4  mov     rdi, [r11+28h]
0x180033cb8  mov     rsp, r11
0x180033cbb  pop     rbp
0x180033cbc  retn
0x180033cbd  mov     r8, rdi
0x180033cc0  lea     rdx, [rsp+270h+var_240]
0x180033cc5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033cca  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180033ccf  mov     ebx, eax
0x180033cd1  test    eax, eax
0x180033cd3  jns     short loc_180033C81
0x180033cd5  mov     edx, 137h
0x180033cda  jmp     loc_180033C53
```
