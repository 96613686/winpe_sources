# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010cd4`
- end: `0x180010e33`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011024`

## callees

- `0x1800109dc`
- `0x1800109f8`
- `0x180010cd4`
- `0x180011cf8`
- `0x180012ae0`
- `0x180013ca4`
- `0x18001445c`
- `0x1800148fc`
- `0x18001518c`
- `0x1800152e0`
- `0x18001ed20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010d0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010d0c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010d51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010d51`

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
0x180010cd4  mov     [rsp-8+arg_10], rbx
0x180010cd9  mov     [rsp-8+arg_18], rdi
0x180010cde  push    rbp
0x180010cdf  lea     rbp, [rsp-170h]
0x180010ce7  sub     rsp, 270h
0x180010cee  mov     rax, cs:__security_cookie
0x180010cf5  xor     rax, rsp
0x180010cf8  mov     [rbp+170h+var_10], rax
0x180010cff  mov     rdi, rdx
0x180010d02  mov     qword ptr [rdx], 0
0x180010d09  mov     rbx, rcx
0x180010d0c  call    cs:__imp_GetCurrentProcessId
0x180010d12  mov     [rsp+270h+var_248], rbx
0x180010d17  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010d1e  mov     r9d, eax
0x180010d21  mov     [rsp+270h+var_250], 130h; int
0x180010d29  mov     edx, 104h; unsigned __int64
0x180010d2e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010d33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d38  mov     r9d, 1F0001h; dwDesiredAccess
0x180010d3e  mov     [rsp+270h+var_240], 0
0x180010d47  xor     r8d, r8d; dwFlags
0x180010d4a  lea     rdx, [rsp+270h+Name]; lpName
0x180010d4f  xor     ecx, ecx; lpMutexAttributes
0x180010d51  call    cs:__imp_CreateMutexExW
0x180010d57  mov     rdx, rax
0x180010d5a  lea     rcx, [rsp+270h+var_240]
0x180010d5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010d64  cmp     [rsp+270h+var_240], 0
0x180010d6a  jnz     short loc_180010D75
0x180010d6c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010d71  mov     ebx, eax
0x180010d73  jmp     short loc_180010DE1
0x180010d75  lea     rdx, [rsp+270h+var_238]
0x180010d7a  lea     rcx, [rsp+270h+var_240]
0x180010d7f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010d84  lea     rdx, [rsp+270h+var_230]; void **
0x180010d89  mov     [rsp+270h+var_230], 0
0x180010d92  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010d97  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010d9c  mov     ebx, eax
0x180010d9e  test    eax, eax
0x180010da0  jns     short loc_180010DC2
0x180010da2  mov     edx, 12Eh; void *
0x180010da7  mov     rcx, [rbp+178h]; this
0x180010dae  mov     r9d, eax; char *
0x180010db1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010db6  lea     rcx, [rsp+270h+var_238]
0x180010dbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010dc0  jmp     short loc_180010DE1
0x180010dc2  mov     rcx, [rsp+270h+var_230]
0x180010dc7  test    rcx, rcx
0x180010dca  jz      short loc_180010E11
0x180010dcc  mov     [rdi], rcx
0x180010dcf  mov     eax, [rcx]
0x180010dd1  inc     eax
0x180010dd3  mov     [rcx], eax
0x180010dd5  lea     rcx, [rsp+270h+var_238]
0x180010dda  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010ddf  xor     ebx, ebx
0x180010de1  lea     rcx, [rsp+270h+var_240]
0x180010de6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010deb  mov     eax, ebx
0x180010ded  mov     rcx, [rbp+170h+var_10]
0x180010df4  xor     rcx, rsp; StackCookie
0x180010df7  call    __security_check_cookie
0x180010dfc  lea     r11, [rsp+270h+var_s0]
0x180010e04  mov     rbx, [r11+20h]
0x180010e08  mov     rdi, [r11+28h]
0x180010e0c  mov     rsp, r11
0x180010e0f  pop     rbp
0x180010e10  retn
0x180010e11  mov     r8, rdi
0x180010e14  lea     rdx, [rsp+270h+var_240]
0x180010e19  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010e1e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010e23  mov     ebx, eax
0x180010e25  test    eax, eax
0x180010e27  jns     short loc_180010DD5
0x180010e29  mov     edx, 137h
0x180010e2e  jmp     loc_180010DA7
```
