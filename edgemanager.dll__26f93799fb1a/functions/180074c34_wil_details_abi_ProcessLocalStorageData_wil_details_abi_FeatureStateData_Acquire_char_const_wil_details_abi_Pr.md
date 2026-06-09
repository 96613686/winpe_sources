# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180074c34`
- end: `0x180074d9a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180074e10`

## callees

- `0x1800073a0`
- `0x1800154cc`
- `0x1800161fc`
- `0x18002b530`
- `0x180036c18`
- `0x180036c34`
- `0x180037918`
- `0x180037b78`
- `0x180037c30`
- `0x180074c34`
- `0x1800752a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180074cb1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180074cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180074c6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180074c6c`

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
0x180074c34  mov     [rsp-8+arg_10], rbx
0x180074c39  mov     [rsp-8+arg_18], rdi
0x180074c3e  push    rbp
0x180074c3f  lea     rbp, [rsp-170h]
0x180074c47  sub     rsp, 270h
0x180074c4e  mov     rax, cs:__security_cookie
0x180074c55  xor     rax, rsp
0x180074c58  mov     [rbp+170h+var_10], rax
0x180074c5f  mov     rdi, rdx
0x180074c62  mov     qword ptr [rdx], 0
0x180074c69  mov     rbx, rcx
0x180074c6c  call    cs:__imp_GetCurrentProcessId
0x180074c72  mov     [rsp+270h+var_248], rbx
0x180074c77  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180074c7e  mov     r9d, eax
0x180074c81  mov     [rsp+270h+var_250], 130h; int
0x180074c89  mov     edx, 104h; unsigned __int64
0x180074c8e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180074c93  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180074c98  mov     r9d, 1F0001h; dwDesiredAccess
0x180074c9e  mov     [rsp+270h+var_240], 0
0x180074ca7  xor     r8d, r8d; dwFlags
0x180074caa  lea     rdx, [rsp+270h+Name]; lpName
0x180074caf  xor     ecx, ecx; lpMutexAttributes
0x180074cb1  call    cs:__imp_CreateMutexExW
0x180074cb7  mov     rdx, rax
0x180074cba  lea     rcx, [rsp+270h+var_240]
0x180074cbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180074cc4  cmp     [rsp+270h+var_240], 0
0x180074cca  jnz     short loc_180074CD5
0x180074ccc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180074cd1  mov     ebx, eax
0x180074cd3  jmp     short loc_180074D48
0x180074cd5  lea     rdx, [rsp+270h+var_238]
0x180074cda  lea     rcx, [rsp+270h+var_240]
0x180074cdf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180074ce4  lea     rdx, [rsp+270h+var_230]; void **
0x180074ce9  mov     [rsp+270h+var_230], 0
0x180074cf2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180074cf7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180074cfc  mov     ebx, eax
0x180074cfe  test    eax, eax
0x180074d00  jns     short loc_180074D29
0x180074d02  mov     edx, 12Eh; void *
0x180074d07  mov     rcx, [rbp+178h]; this
0x180074d0e  lea     r8, aWil; "wil"
0x180074d15  mov     r9d, eax; char *
0x180074d18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074d1d  lea     rcx, [rsp+270h+var_238]
0x180074d22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180074d27  jmp     short loc_180074D48
0x180074d29  mov     rcx, [rsp+270h+var_230]
0x180074d2e  test    rcx, rcx
0x180074d31  jz      short loc_180074D78
0x180074d33  mov     [rdi], rcx
0x180074d36  mov     eax, [rcx]
0x180074d38  inc     eax
0x180074d3a  mov     [rcx], eax
0x180074d3c  lea     rcx, [rsp+270h+var_238]
0x180074d41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180074d46  xor     ebx, ebx
0x180074d48  lea     rcx, [rsp+270h+var_240]
0x180074d4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180074d52  mov     eax, ebx
0x180074d54  mov     rcx, [rbp+170h+var_10]
0x180074d5b  xor     rcx, rsp; StackCookie
0x180074d5e  call    __security_check_cookie
0x180074d63  lea     r11, [rsp+270h+var_s0]
0x180074d6b  mov     rbx, [r11+20h]
0x180074d6f  mov     rdi, [r11+28h]
0x180074d73  mov     rsp, r11
0x180074d76  pop     rbp
0x180074d77  retn
0x180074d78  mov     r8, rdi
0x180074d7b  lea     rdx, [rsp+270h+var_240]
0x180074d80  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180074d85  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180074d8a  mov     ebx, eax
0x180074d8c  test    eax, eax
0x180074d8e  jns     short loc_180074D3C
0x180074d90  mov     edx, 137h
0x180074d95  jmp     loc_180074D07
```
