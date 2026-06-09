# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e48`
- end: `0x180003faa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004b18`

## callees

- `0x180003900`
- `0x18000391c`
- `0x180003e48`
- `0x1800049a8`
- `0x1800058b0`
- `0x18000685c`
- `0x180007014`
- `0x180007460`
- `0x180007c04`
- `0x180007fb8`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003e80`
- `KERNEL32!GetCurrentProcessId` at `0x180003e80`
- `KERNEL32!CreateMutexExW` at `0x180003ec5`
- `KERNEL32!CreateMutexExW` at `0x180003ec5`

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
0x180003e48  mov     [rsp-8+arg_10], rbx
0x180003e4d  mov     [rsp-8+arg_18], rdi
0x180003e52  push    rbp
0x180003e53  lea     rbp, [rsp-170h]
0x180003e5b  sub     rsp, 270h
0x180003e62  mov     rax, cs:__security_cookie
0x180003e69  xor     rax, rsp
0x180003e6c  mov     [rbp+170h+var_10], rax
0x180003e73  mov     rdi, rdx
0x180003e76  mov     rbx, rcx
0x180003e79  mov     qword ptr [rdx], 0
0x180003e80  call    cs:__imp_GetCurrentProcessId
0x180003e86  mov     r9d, eax
0x180003e89  mov     [rsp+270h+var_248], rbx
0x180003e8e  mov     [rsp+270h+var_250], 130h; int
0x180003e96  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e9d  mov     edx, 104h; unsigned __int64
0x180003ea2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003ea7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003eac  mov     [rsp+270h+var_240], 0
0x180003eb5  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ebb  xor     r8d, r8d; dwFlags
0x180003ebe  lea     rdx, [rsp+270h+Name]; lpName
0x180003ec3  xor     ecx, ecx; lpMutexAttributes
0x180003ec5  call    cs:__imp_CreateMutexExW
0x180003ecb  mov     rdx, rax
0x180003ece  lea     rcx, [rsp+270h+var_240]
0x180003ed3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003ed8  cmp     [rsp+270h+var_240], 0
0x180003ede  jnz     short loc_180003EE9
0x180003ee0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ee5  mov     ebx, eax
0x180003ee7  jmp     short loc_180003F57
0x180003ee9  lea     rdx, [rsp+270h+var_238]
0x180003eee  lea     rcx, [rsp+270h+var_240]
0x180003ef3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003ef8  nop
0x180003ef9  mov     [rsp+270h+var_230], 0
0x180003f02  lea     rdx, [rsp+270h+var_230]; void **
0x180003f07  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003f0c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180003f11  mov     ebx, eax
0x180003f13  test    eax, eax
0x180003f15  jns     short loc_180003F38
0x180003f17  mov     edx, 12Eh; void *
0x180003f1c  mov     r9d, eax; char *
0x180003f1f  mov     rcx, [rbp+178h]; this
0x180003f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f2b  nop
0x180003f2c  lea     rcx, [rsp+270h+var_238]
0x180003f31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f36  jmp     short loc_180003F57
0x180003f38  mov     rcx, [rsp+270h+var_230]
0x180003f3d  test    rcx, rcx
0x180003f40  jz      short loc_180003F87
0x180003f42  mov     [rdi], rcx
0x180003f45  mov     eax, [rcx]
0x180003f47  inc     eax
0x180003f49  mov     [rcx], eax
0x180003f4b  lea     rcx, [rsp+270h+var_238]
0x180003f50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f55  xor     ebx, ebx
0x180003f57  lea     rcx, [rsp+270h+var_240]
0x180003f5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f61  mov     eax, ebx
0x180003f63  mov     rcx, [rbp+170h+var_10]
0x180003f6a  xor     rcx, rsp; StackCookie
0x180003f6d  call    __security_check_cookie
0x180003f72  lea     r11, [rsp+270h+var_s0]
0x180003f7a  mov     rbx, [r11+20h]
0x180003f7e  mov     rdi, [r11+28h]
0x180003f82  mov     rsp, r11
0x180003f85  pop     rbp
0x180003f86  retn
0x180003f87  mov     r8, rdi
0x180003f8a  lea     rdx, [rsp+270h+var_240]
0x180003f8f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003f94  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003f99  mov     ebx, eax
0x180003f9b  test    eax, eax
0x180003f9d  jns     short loc_180003F4B
0x180003f9f  mov     edx, 137h
0x180003fa4  jmp     loc_180003F1C
```
