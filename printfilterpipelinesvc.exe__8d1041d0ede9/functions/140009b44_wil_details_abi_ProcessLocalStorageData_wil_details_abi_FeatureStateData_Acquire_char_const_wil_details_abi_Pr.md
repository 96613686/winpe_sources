# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009b44`
- end: `0x140009ca3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140009fa8`

## callees

- `0x140002070`
- `0x140007654`
- `0x140009578`
- `0x140009594`
- `0x140009b44`
- `0x14000ae58`
- `0x14000becc`
- `0x14000d5ac`
- `0x14000e1f8`
- `0x14000ea8c`
- `0x14000eda4`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140009bc1`
- `KERNEL32!CreateMutexExW` at `0x140009bc1`
- `KERNEL32!GetCurrentProcessId` at `0x140009b7c`
- `KERNEL32!GetCurrentProcessId` at `0x140009b7c`

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
0x140009b44  mov     [rsp-8+arg_10], rbx
0x140009b49  mov     [rsp-8+arg_18], rdi
0x140009b4e  push    rbp
0x140009b4f  lea     rbp, [rsp-170h]
0x140009b57  sub     rsp, 270h
0x140009b5e  mov     rax, cs:__security_cookie
0x140009b65  xor     rax, rsp
0x140009b68  mov     [rbp+170h+var_10], rax
0x140009b6f  mov     rdi, rdx
0x140009b72  mov     qword ptr [rdx], 0
0x140009b79  mov     rbx, rcx
0x140009b7c  call    cs:__imp_GetCurrentProcessId
0x140009b82  mov     [rsp+270h+var_248], rbx
0x140009b87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009b8e  mov     r9d, eax
0x140009b91  mov     [rsp+270h+var_250], 130h; int
0x140009b99  mov     edx, 104h; unsigned __int64
0x140009b9e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009ba3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140009ba8  mov     r9d, 1F0001h; dwDesiredAccess
0x140009bae  mov     [rsp+270h+var_240], 0
0x140009bb7  xor     r8d, r8d; dwFlags
0x140009bba  lea     rdx, [rsp+270h+Name]; lpName
0x140009bbf  xor     ecx, ecx; lpMutexAttributes
0x140009bc1  call    cs:__imp_CreateMutexExW
0x140009bc7  mov     rdx, rax
0x140009bca  lea     rcx, [rsp+270h+var_240]
0x140009bcf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009bd4  cmp     [rsp+270h+var_240], 0
0x140009bda  jnz     short loc_140009BE5
0x140009bdc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009be1  mov     ebx, eax
0x140009be3  jmp     short loc_140009C51
0x140009be5  lea     rdx, [rsp+270h+var_238]
0x140009bea  lea     rcx, [rsp+270h+var_240]
0x140009bef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140009bf4  lea     rdx, [rsp+270h+var_230]; void **
0x140009bf9  mov     [rsp+270h+var_230], 0
0x140009c02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009c07  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140009c0c  mov     ebx, eax
0x140009c0e  test    eax, eax
0x140009c10  jns     short loc_140009C32
0x140009c12  mov     edx, 12Eh; void *
0x140009c17  mov     rcx, [rbp+178h]; this
0x140009c1e  mov     r9d, eax; char *
0x140009c21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009c26  lea     rcx, [rsp+270h+var_238]
0x140009c2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c30  jmp     short loc_140009C51
0x140009c32  mov     rcx, [rsp+270h+var_230]
0x140009c37  test    rcx, rcx
0x140009c3a  jz      short loc_140009C81
0x140009c3c  mov     [rdi], rcx
0x140009c3f  mov     eax, [rcx]
0x140009c41  inc     eax
0x140009c43  mov     [rcx], eax
0x140009c45  lea     rcx, [rsp+270h+var_238]
0x140009c4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c4f  xor     ebx, ebx
0x140009c51  lea     rcx, [rsp+270h+var_240]
0x140009c56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009c5b  mov     eax, ebx
0x140009c5d  mov     rcx, [rbp+170h+var_10]
0x140009c64  xor     rcx, rsp; StackCookie
0x140009c67  call    __security_check_cookie
0x140009c6c  lea     r11, [rsp+270h+var_s0]
0x140009c74  mov     rbx, [r11+20h]
0x140009c78  mov     rdi, [r11+28h]
0x140009c7c  mov     rsp, r11
0x140009c7f  pop     rbp
0x140009c80  retn
0x140009c81  mov     r8, rdi
0x140009c84  lea     rdx, [rsp+270h+var_240]
0x140009c89  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009c8e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140009c93  mov     ebx, eax
0x140009c95  test    eax, eax
0x140009c97  jns     short loc_140009C45
0x140009c99  mov     edx, 137h
0x140009c9e  jmp     loc_140009C17
```
