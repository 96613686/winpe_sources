# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004e48`
- end: `0x180004fa7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005c28`

## callees

- `0x180001e80`
- `0x1800024a4`
- `0x18000499c`
- `0x1800049b8`
- `0x180004e48`
- `0x18000672c`
- `0x180007948`
- `0x1800082e4`
- `0x180008b14`
- `0x180008e10`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ec5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ec5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v13,
      &v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004e48  mov     [rsp-8+arg_10], rbx
0x180004e4d  mov     [rsp-8+arg_18], rdi
0x180004e52  push    rbp
0x180004e53  lea     rbp, [rsp-170h]
0x180004e5b  sub     rsp, 270h
0x180004e62  mov     rax, cs:__security_cookie
0x180004e69  xor     rax, rsp
0x180004e6c  mov     [rbp+170h+var_10], rax
0x180004e73  mov     rdi, rdx
0x180004e76  mov     qword ptr [rdx], 0
0x180004e7d  mov     rbx, rcx
0x180004e80  call    cs:__imp_GetCurrentProcessId
0x180004e86  mov     [rsp+270h+var_248], rbx
0x180004e8b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e92  mov     r9d, eax
0x180004e95  mov     [rsp+270h+var_250], 130h; int
0x180004e9d  mov     edx, 104h; unsigned __int64
0x180004ea2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004ea7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004eac  mov     r9d, 1F0001h; dwDesiredAccess
0x180004eb2  mov     [rsp+270h+var_240], 0
0x180004ebb  xor     r8d, r8d; dwFlags
0x180004ebe  lea     rdx, [rsp+270h+Name]; lpName
0x180004ec3  xor     ecx, ecx; lpMutexAttributes
0x180004ec5  call    cs:__imp_CreateMutexExW
0x180004ecb  mov     rdx, rax
0x180004ece  lea     rcx, [rsp+270h+var_240]
0x180004ed3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004ed8  cmp     [rsp+270h+var_240], 0
0x180004ede  jnz     short loc_180004EE9
0x180004ee0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ee5  mov     ebx, eax
0x180004ee7  jmp     short loc_180004F55
0x180004ee9  lea     rdx, [rsp+270h+var_238]
0x180004eee  lea     rcx, [rsp+270h+var_240]
0x180004ef3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004ef8  lea     rdx, [rsp+270h+var_230]; void **
0x180004efd  mov     [rsp+270h+var_230], 0
0x180004f06  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004f0b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004f10  mov     ebx, eax
0x180004f12  test    eax, eax
0x180004f14  jns     short loc_180004F36
0x180004f16  mov     edx, 12Eh; void *
0x180004f1b  mov     rcx, [rbp+178h]; this
0x180004f22  mov     r9d, eax; char *
0x180004f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f2a  lea     rcx, [rsp+270h+var_238]
0x180004f2f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f34  jmp     short loc_180004F55
0x180004f36  mov     rcx, [rsp+270h+var_230]
0x180004f3b  test    rcx, rcx
0x180004f3e  jz      short loc_180004F85
0x180004f40  mov     [rdi], rcx
0x180004f43  mov     eax, [rcx]
0x180004f45  inc     eax
0x180004f47  mov     [rcx], eax
0x180004f49  lea     rcx, [rsp+270h+var_238]
0x180004f4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f53  xor     ebx, ebx
0x180004f55  lea     rcx, [rsp+270h+var_240]
0x180004f5a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f5f  mov     eax, ebx
0x180004f61  mov     rcx, [rbp+170h+var_10]
0x180004f68  xor     rcx, rsp; StackCookie
0x180004f6b  call    __security_check_cookie
0x180004f70  lea     r11, [rsp+270h+var_s0]
0x180004f78  mov     rbx, [r11+20h]
0x180004f7c  mov     rdi, [r11+28h]
0x180004f80  mov     rsp, r11
0x180004f83  pop     rbp
0x180004f84  retn
0x180004f85  mov     r8, rdi
0x180004f88  lea     rdx, [rsp+270h+var_240]
0x180004f8d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004f92  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004f97  mov     ebx, eax
0x180004f99  test    eax, eax
0x180004f9b  jns     short loc_180004F49
0x180004f9d  mov     edx, 137h
0x180004fa2  jmp     loc_180004F1B
```
