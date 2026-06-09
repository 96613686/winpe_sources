# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180037d90`
- end: `0x180037ef2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800380f4`

## callees

- `0x18002fb50`
- `0x180037954`
- `0x180037970`
- `0x180037d90`
- `0x180038958`
- `0x18003976c`
- `0x18003a3ec`
- `0x18003ab7c`
- `0x18003aff8`
- `0x18003b7e4`
- `0x18003b97c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037dc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037dc8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180037e0d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180037e0d`

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
0x180037d90  mov     [rsp-8+arg_10], rbx
0x180037d95  mov     [rsp-8+arg_18], rdi
0x180037d9a  push    rbp
0x180037d9b  lea     rbp, [rsp-170h]
0x180037da3  sub     rsp, 270h
0x180037daa  mov     rax, cs:__security_cookie
0x180037db1  xor     rax, rsp
0x180037db4  mov     [rbp+170h+var_10], rax
0x180037dbb  mov     rdi, rdx
0x180037dbe  mov     rbx, rcx
0x180037dc1  mov     qword ptr [rdx], 0
0x180037dc8  call    cs:__imp_GetCurrentProcessId
0x180037dce  mov     r9d, eax
0x180037dd1  mov     [rsp+270h+var_248], rbx
0x180037dd6  mov     [rsp+270h+var_250], 130h; int
0x180037dde  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180037de5  mov     edx, 104h; unsigned __int64
0x180037dea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037def  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037df4  mov     [rsp+270h+var_240], 0
0x180037dfd  mov     r9d, 1F0001h; dwDesiredAccess
0x180037e03  xor     r8d, r8d; dwFlags
0x180037e06  lea     rdx, [rsp+270h+Name]; lpName
0x180037e0b  xor     ecx, ecx; lpMutexAttributes
0x180037e0d  call    cs:__imp_CreateMutexExW
0x180037e13  mov     rdx, rax
0x180037e16  lea     rcx, [rsp+270h+var_240]
0x180037e1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180037e20  cmp     [rsp+270h+var_240], 0
0x180037e26  jnz     short loc_180037E31
0x180037e28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180037e2d  mov     ebx, eax
0x180037e2f  jmp     short loc_180037E9F
0x180037e31  lea     rdx, [rsp+270h+var_238]
0x180037e36  lea     rcx, [rsp+270h+var_240]
0x180037e3b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180037e40  nop
0x180037e41  mov     [rsp+270h+var_230], 0
0x180037e4a  lea     rdx, [rsp+270h+var_230]; void **
0x180037e4f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037e54  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180037e59  mov     ebx, eax
0x180037e5b  test    eax, eax
0x180037e5d  jns     short loc_180037E80
0x180037e5f  mov     edx, 12Eh; void *
0x180037e64  mov     r9d, eax; char *
0x180037e67  mov     rcx, [rbp+178h]; this
0x180037e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e73  nop
0x180037e74  lea     rcx, [rsp+270h+var_238]
0x180037e79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037e7e  jmp     short loc_180037E9F
0x180037e80  mov     rcx, [rsp+270h+var_230]
0x180037e85  test    rcx, rcx
0x180037e88  jz      short loc_180037ECF
0x180037e8a  mov     [rdi], rcx
0x180037e8d  mov     eax, [rcx]
0x180037e8f  inc     eax
0x180037e91  mov     [rcx], eax
0x180037e93  lea     rcx, [rsp+270h+var_238]
0x180037e98  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037e9d  xor     ebx, ebx
0x180037e9f  lea     rcx, [rsp+270h+var_240]
0x180037ea4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180037ea9  mov     eax, ebx
0x180037eab  mov     rcx, [rbp+170h+var_10]
0x180037eb2  xor     rcx, rsp; StackCookie
0x180037eb5  call    __security_check_cookie
0x180037eba  lea     r11, [rsp+270h+var_s0]
0x180037ec2  mov     rbx, [r11+20h]
0x180037ec6  mov     rdi, [r11+28h]
0x180037eca  mov     rsp, r11
0x180037ecd  pop     rbp
0x180037ece  retn
0x180037ecf  mov     r8, rdi
0x180037ed2  lea     rdx, [rsp+270h+var_240]
0x180037ed7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180037edc  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180037ee1  mov     ebx, eax
0x180037ee3  test    eax, eax
0x180037ee5  jns     short loc_180037E93
0x180037ee7  mov     edx, 137h
0x180037eec  jmp     loc_180037E64
```
