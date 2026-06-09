# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e78`
- end: `0x180003fda`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800042a0`

## callees

- `0x180003810`
- `0x18000382c`
- `0x180003e78`
- `0x180004b24`
- `0x180005c34`
- `0x180006e6c`
- `0x1800075ec`
- `0x180007acc`
- `0x1800081d4`
- `0x180008af0`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003eb0`
- `KERNEL32!GetCurrentProcessId` at `0x180003eb0`
- `KERNEL32!CreateMutexExW` at `0x180003ef5`
- `KERNEL32!CreateMutexExW` at `0x180003ef5`

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
0x180003e78  mov     [rsp-8+arg_10], rbx
0x180003e7d  mov     [rsp-8+arg_18], rdi
0x180003e82  push    rbp
0x180003e83  lea     rbp, [rsp-170h]
0x180003e8b  sub     rsp, 270h
0x180003e92  mov     rax, cs:__security_cookie
0x180003e99  xor     rax, rsp
0x180003e9c  mov     [rbp+170h+var_10], rax
0x180003ea3  mov     rdi, rdx
0x180003ea6  mov     rbx, rcx
0x180003ea9  mov     qword ptr [rdx], 0
0x180003eb0  call    cs:__imp_GetCurrentProcessId
0x180003eb6  mov     r9d, eax
0x180003eb9  mov     [rsp+270h+var_248], rbx
0x180003ebe  mov     [rsp+270h+var_250], 130h; int
0x180003ec6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ecd  mov     edx, 104h; unsigned __int64
0x180003ed2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003ed7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003edc  mov     [rsp+270h+var_240], 0
0x180003ee5  mov     r9d, 1F0001h; dwDesiredAccess
0x180003eeb  xor     r8d, r8d; dwFlags
0x180003eee  lea     rdx, [rsp+270h+Name]; lpName
0x180003ef3  xor     ecx, ecx; lpMutexAttributes
0x180003ef5  call    cs:__imp_CreateMutexExW
0x180003efb  mov     rdx, rax
0x180003efe  lea     rcx, [rsp+270h+var_240]
0x180003f03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003f08  cmp     [rsp+270h+var_240], 0
0x180003f0e  jnz     short loc_180003F19
0x180003f10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f15  mov     ebx, eax
0x180003f17  jmp     short loc_180003F87
0x180003f19  lea     rdx, [rsp+270h+var_238]
0x180003f1e  lea     rcx, [rsp+270h+var_240]
0x180003f23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003f28  nop
0x180003f29  mov     [rsp+270h+var_230], 0
0x180003f32  lea     rdx, [rsp+270h+var_230]; void **
0x180003f37  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003f3c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180003f41  mov     ebx, eax
0x180003f43  test    eax, eax
0x180003f45  jns     short loc_180003F68
0x180003f47  mov     edx, 12Eh; void *
0x180003f4c  mov     r9d, eax; char *
0x180003f4f  mov     rcx, [rbp+178h]; this
0x180003f56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f5b  nop
0x180003f5c  lea     rcx, [rsp+270h+var_238]
0x180003f61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f66  jmp     short loc_180003F87
0x180003f68  mov     rcx, [rsp+270h+var_230]
0x180003f6d  test    rcx, rcx
0x180003f70  jz      short loc_180003FB7
0x180003f72  mov     [rdi], rcx
0x180003f75  mov     eax, [rcx]
0x180003f77  inc     eax
0x180003f79  mov     [rcx], eax
0x180003f7b  lea     rcx, [rsp+270h+var_238]
0x180003f80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f85  xor     ebx, ebx
0x180003f87  lea     rcx, [rsp+270h+var_240]
0x180003f8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003f91  mov     eax, ebx
0x180003f93  mov     rcx, [rbp+170h+var_10]
0x180003f9a  xor     rcx, rsp; StackCookie
0x180003f9d  call    __security_check_cookie
0x180003fa2  lea     r11, [rsp+270h+var_s0]
0x180003faa  mov     rbx, [r11+20h]
0x180003fae  mov     rdi, [r11+28h]
0x180003fb2  mov     rsp, r11
0x180003fb5  pop     rbp
0x180003fb6  retn
0x180003fb7  mov     r8, rdi
0x180003fba  lea     rdx, [rsp+270h+var_240]
0x180003fbf  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003fc4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003fc9  mov     ebx, eax
0x180003fcb  test    eax, eax
0x180003fcd  jns     short loc_180003F7B
0x180003fcf  mov     edx, 137h
0x180003fd4  jmp     loc_180003F4C
```
