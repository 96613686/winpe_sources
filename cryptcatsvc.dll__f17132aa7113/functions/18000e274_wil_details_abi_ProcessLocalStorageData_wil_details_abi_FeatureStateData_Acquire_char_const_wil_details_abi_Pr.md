# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000e274`
- end: `0x18000e3da`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000efe0`

## callees

- `0x180005640`
- `0x18000b0d0`
- `0x18000b238`
- `0x18000b290`
- `0x18000be40`
- `0x18000de20`
- `0x18000de3c`
- `0x18000e274`
- `0x18001160c`
- `0x180011ed4`
- `0x180012124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e2f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e2f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e2ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e2ac`

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
      v13,
      0,
      0xFFFFFFFFLL);
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
0x18000e274  mov     [rsp-8+arg_10], rbx
0x18000e279  mov     [rsp-8+arg_18], rdi
0x18000e27e  push    rbp
0x18000e27f  lea     rbp, [rsp-170h]
0x18000e287  sub     rsp, 270h
0x18000e28e  mov     rax, cs:__security_cookie
0x18000e295  xor     rax, rsp
0x18000e298  mov     [rbp+170h+var_10], rax
0x18000e29f  mov     rdi, rdx
0x18000e2a2  mov     qword ptr [rdx], 0
0x18000e2a9  mov     rbx, rcx
0x18000e2ac  call    cs:__imp_GetCurrentProcessId
0x18000e2b2  mov     [rsp+270h+var_248], rbx
0x18000e2b7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000e2be  mov     r9d, eax
0x18000e2c1  mov     [rsp+270h+var_250], 130h; int
0x18000e2c9  mov     edx, 104h; unsigned __int64
0x18000e2ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e2d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e2d8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000e2de  mov     [rsp+270h+var_240], 0
0x18000e2e7  xor     r8d, r8d; dwFlags
0x18000e2ea  lea     rdx, [rsp+270h+Name]; lpName
0x18000e2ef  xor     ecx, ecx; lpMutexAttributes
0x18000e2f1  call    cs:__imp_CreateMutexExW
0x18000e2f7  mov     rdx, rax
0x18000e2fa  lea     rcx, [rsp+270h+var_240]
0x18000e2ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e304  cmp     [rsp+270h+var_240], 0
0x18000e30a  jnz     short loc_18000E315
0x18000e30c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e311  mov     ebx, eax
0x18000e313  jmp     short loc_18000E388
0x18000e315  or      r9d, 0FFFFFFFFh
0x18000e319  lea     rdx, [rsp+270h+var_238]
0x18000e31e  xor     r8d, r8d
0x18000e321  lea     rcx, [rsp+270h+var_240]
0x18000e326  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000e32b  lea     rdx, [rsp+270h+var_230]; void **
0x18000e330  mov     [rsp+270h+var_230], 0
0x18000e339  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e33e  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000e343  mov     ebx, eax
0x18000e345  test    eax, eax
0x18000e347  jns     short loc_18000E369
0x18000e349  mov     edx, 12Eh; void *
0x18000e34e  mov     rcx, [rbp+178h]; this
0x18000e355  mov     r9d, eax; char *
0x18000e358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e35d  lea     rcx, [rsp+270h+var_238]
0x18000e362  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e367  jmp     short loc_18000E388
0x18000e369  mov     rcx, [rsp+270h+var_230]
0x18000e36e  test    rcx, rcx
0x18000e371  jz      short loc_18000E3B8
0x18000e373  mov     [rdi], rcx
0x18000e376  mov     eax, [rcx]
0x18000e378  inc     eax
0x18000e37a  mov     [rcx], eax
0x18000e37c  lea     rcx, [rsp+270h+var_238]
0x18000e381  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e386  xor     ebx, ebx
0x18000e388  lea     rcx, [rsp+270h+var_240]
0x18000e38d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e392  mov     eax, ebx
0x18000e394  mov     rcx, [rbp+170h+var_10]
0x18000e39b  xor     rcx, rsp; StackCookie
0x18000e39e  call    __security_check_cookie
0x18000e3a3  lea     r11, [rsp+270h+var_s0]
0x18000e3ab  mov     rbx, [r11+20h]
0x18000e3af  mov     rdi, [r11+28h]
0x18000e3b3  mov     rsp, r11
0x18000e3b6  pop     rbp
0x18000e3b7  retn
0x18000e3b8  mov     r8, rdi
0x18000e3bb  lea     rdx, [rsp+270h+var_240]
0x18000e3c0  lea     rcx, [rsp+270h+Name]
0x18000e3c5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000e3ca  mov     ebx, eax
0x18000e3cc  test    eax, eax
0x18000e3ce  jns     short loc_18000E37C
0x18000e3d0  mov     edx, 137h
0x18000e3d5  jmp     loc_18000E34E
```
