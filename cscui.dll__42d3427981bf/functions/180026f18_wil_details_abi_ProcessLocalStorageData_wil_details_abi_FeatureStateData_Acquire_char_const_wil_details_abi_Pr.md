# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180026f18`
- end: `0x180027077`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180027e14`

## callees

- `0x18000a560`
- `0x18000a6bc`
- `0x18000a708`
- `0x18000ee0c`
- `0x18000ee28`
- `0x1800104c4`
- `0x18001057c`
- `0x180010954`
- `0x180010a00`
- `0x180026f18`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026f50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026f50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026f95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026f95`

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
0x180026f18  mov     [rsp-8+arg_10], rbx
0x180026f1d  mov     [rsp-8+arg_18], rdi
0x180026f22  push    rbp
0x180026f23  lea     rbp, [rsp-170h]
0x180026f2b  sub     rsp, 270h
0x180026f32  mov     rax, cs:__security_cookie
0x180026f39  xor     rax, rsp
0x180026f3c  mov     [rbp+170h+var_10], rax
0x180026f43  mov     rdi, rdx
0x180026f46  mov     qword ptr [rdx], 0
0x180026f4d  mov     rbx, rcx
0x180026f50  call    cs:__imp_GetCurrentProcessId
0x180026f56  mov     [rsp+270h+var_248], rbx
0x180026f5b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180026f62  mov     r9d, eax
0x180026f65  mov     [rsp+270h+var_250], 130h; int
0x180026f6d  mov     edx, 104h; unsigned __int64
0x180026f72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026f77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026f7c  mov     r9d, 1F0001h; dwDesiredAccess
0x180026f82  mov     [rsp+270h+var_240], 0
0x180026f8b  xor     r8d, r8d; dwFlags
0x180026f8e  lea     rdx, [rsp+270h+Name]; lpName
0x180026f93  xor     ecx, ecx; lpMutexAttributes
0x180026f95  call    cs:__imp_CreateMutexExW
0x180026f9b  mov     rdx, rax
0x180026f9e  lea     rcx, [rsp+270h+var_240]
0x180026fa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180026fa8  cmp     [rsp+270h+var_240], 0
0x180026fae  jnz     short loc_180026FB9
0x180026fb0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180026fb5  mov     ebx, eax
0x180026fb7  jmp     short loc_180027025
0x180026fb9  lea     rdx, [rsp+270h+var_238]
0x180026fbe  lea     rcx, [rsp+270h+var_240]
0x180026fc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180026fc8  lea     rdx, [rsp+270h+var_230]; void **
0x180026fcd  mov     [rsp+270h+var_230], 0
0x180026fd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026fdb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180026fe0  mov     ebx, eax
0x180026fe2  test    eax, eax
0x180026fe4  jns     short loc_180027006
0x180026fe6  mov     edx, 12Eh; void *
0x180026feb  mov     rcx, [rbp+178h]; this
0x180026ff2  mov     r9d, eax; char *
0x180026ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ffa  lea     rcx, [rsp+270h+var_238]
0x180026fff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027004  jmp     short loc_180027025
0x180027006  mov     rcx, [rsp+270h+var_230]
0x18002700b  test    rcx, rcx
0x18002700e  jz      short loc_180027055
0x180027010  mov     [rdi], rcx
0x180027013  mov     eax, [rcx]
0x180027015  inc     eax
0x180027017  mov     [rcx], eax
0x180027019  lea     rcx, [rsp+270h+var_238]
0x18002701e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027023  xor     ebx, ebx
0x180027025  lea     rcx, [rsp+270h+var_240]
0x18002702a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002702f  mov     eax, ebx
0x180027031  mov     rcx, [rbp+170h+var_10]
0x180027038  xor     rcx, rsp; StackCookie
0x18002703b  call    __security_check_cookie
0x180027040  lea     r11, [rsp+270h+var_s0]
0x180027048  mov     rbx, [r11+20h]
0x18002704c  mov     rdi, [r11+28h]
0x180027050  mov     rsp, r11
0x180027053  pop     rbp
0x180027054  retn
0x180027055  mov     r8, rdi
0x180027058  lea     rdx, [rsp+270h+var_240]
0x18002705d  lea     rcx, [rsp+270h+Name]
0x180027062  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180027067  mov     ebx, eax
0x180027069  test    eax, eax
0x18002706b  jns     short loc_180027019
0x18002706d  mov     edx, 137h
0x180027072  jmp     loc_180026FEB
```
