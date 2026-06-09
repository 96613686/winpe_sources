# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003a3c`
- end: `0x180003ba2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004790`

## callees

- `0x180003528`
- `0x180003544`
- `0x180003a3c`
- `0x180004618`
- `0x180005370`
- `0x18000635c`
- `0x180006b48`
- `0x180006f30`
- `0x1800078a4`
- `0x180008010`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003a74`
- `KERNEL32!GetCurrentProcessId` at `0x180003a74`
- `KERNEL32!CreateMutexExW` at `0x180003ab9`
- `KERNEL32!CreateMutexExW` at `0x180003ab9`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003a3c  mov     [rsp-8+arg_10], rbx
0x180003a41  mov     [rsp-8+arg_18], rdi
0x180003a46  push    rbp
0x180003a47  lea     rbp, [rsp-170h]
0x180003a4f  sub     rsp, 270h
0x180003a56  mov     rax, cs:__security_cookie
0x180003a5d  xor     rax, rsp
0x180003a60  mov     [rbp+170h+var_10], rax
0x180003a67  mov     rdi, rdx
0x180003a6a  mov     qword ptr [rdx], 0
0x180003a71  mov     rbx, rcx
0x180003a74  call    cs:__imp_GetCurrentProcessId
0x180003a7a  mov     [rsp+270h+var_248], rbx
0x180003a7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003a86  mov     r9d, eax
0x180003a89  mov     [rsp+270h+var_250], 130h; int
0x180003a91  mov     edx, 104h; unsigned __int64
0x180003a96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003a9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003aa0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003aa6  mov     [rsp+270h+var_240], 0
0x180003aaf  xor     r8d, r8d; dwFlags
0x180003ab2  lea     rdx, [rsp+270h+Name]; lpName
0x180003ab7  xor     ecx, ecx; lpMutexAttributes
0x180003ab9  call    cs:__imp_CreateMutexExW
0x180003abf  mov     rdx, rax
0x180003ac2  lea     rcx, [rsp+270h+var_240]
0x180003ac7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003acc  cmp     [rsp+270h+var_240], 0
0x180003ad2  jnz     short loc_180003ADD
0x180003ad4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ad9  mov     ebx, eax
0x180003adb  jmp     short loc_180003B50
0x180003add  lea     rdx, [rsp+270h+var_238]
0x180003ae2  lea     rcx, [rsp+270h+var_240]
0x180003ae7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003aec  lea     rdx, [rsp+270h+var_230]; void **
0x180003af1  mov     [rsp+270h+var_230], 0
0x180003afa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003aff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003b04  mov     ebx, eax
0x180003b06  test    eax, eax
0x180003b08  jns     short loc_180003B31
0x180003b0a  mov     edx, 12Eh; void *
0x180003b0f  mov     rcx, [rbp+178h]; this
0x180003b16  lea     r8, aWil; "wil"
0x180003b1d  mov     r9d, eax; char *
0x180003b20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b25  lea     rcx, [rsp+270h+var_238]
0x180003b2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b2f  jmp     short loc_180003B50
0x180003b31  mov     rcx, [rsp+270h+var_230]
0x180003b36  test    rcx, rcx
0x180003b39  jz      short loc_180003B80
0x180003b3b  mov     [rdi], rcx
0x180003b3e  mov     eax, [rcx]
0x180003b40  inc     eax
0x180003b42  mov     [rcx], eax
0x180003b44  lea     rcx, [rsp+270h+var_238]
0x180003b49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b4e  xor     ebx, ebx
0x180003b50  lea     rcx, [rsp+270h+var_240]
0x180003b55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b5a  mov     eax, ebx
0x180003b5c  mov     rcx, [rbp+170h+var_10]
0x180003b63  xor     rcx, rsp; StackCookie
0x180003b66  call    __security_check_cookie
0x180003b6b  lea     r11, [rsp+270h+var_s0]
0x180003b73  mov     rbx, [r11+20h]
0x180003b77  mov     rdi, [r11+28h]
0x180003b7b  mov     rsp, r11
0x180003b7e  pop     rbp
0x180003b7f  retn
0x180003b80  mov     r8, rdi
0x180003b83  lea     rdx, [rsp+270h+var_240]
0x180003b88  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003b8d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003b92  mov     ebx, eax
0x180003b94  test    eax, eax
0x180003b96  jns     short loc_180003B44
0x180003b98  mov     edx, 137h
0x180003b9d  jmp     loc_180003B0F
```
