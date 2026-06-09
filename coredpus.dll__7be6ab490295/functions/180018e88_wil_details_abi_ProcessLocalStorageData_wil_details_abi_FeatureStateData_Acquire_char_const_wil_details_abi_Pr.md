# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180018e88`
- end: `0x180018ffb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001951c`

## callees

- `0x180011d9c`
- `0x1800136d4`
- `0x180014330`
- `0x180016428`
- `0x18001887c`
- `0x18001889c`
- `0x180018e88`
- `0x18001a968`
- `0x18001ca98`
- `0x18001d824`
- `0x18001db50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018f0b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018ec0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018ec0`

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
0x180018e88  mov     [rsp-8+arg_10], rbx
0x180018e8d  mov     [rsp-8+arg_18], rdi
0x180018e92  push    rbp
0x180018e93  lea     rbp, [rsp-170h]
0x180018e9b  sub     rsp, 270h
0x180018ea2  mov     rax, cs:__security_cookie
0x180018ea9  xor     rax, rsp
0x180018eac  mov     [rbp+170h+var_10], rax
0x180018eb3  mov     rdi, rdx
0x180018eb6  mov     qword ptr [rdx], 0
0x180018ebd  mov     rbx, rcx
0x180018ec0  call    cs:__imp_GetCurrentProcessId
0x180018ec7  nop     dword ptr [rax+rax+00h]
0x180018ecc  mov     [rsp+270h+var_248], rbx
0x180018ed1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018ed8  mov     r9d, eax
0x180018edb  mov     [rsp+270h+var_250], 130h; int
0x180018ee3  mov     edx, 104h; unsigned __int64
0x180018ee8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018eed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018ef2  mov     r9d, 1F0001h; dwDesiredAccess
0x180018ef8  mov     [rsp+270h+var_240], 0
0x180018f01  xor     r8d, r8d; dwFlags
0x180018f04  lea     rdx, [rsp+270h+Name]; lpName
0x180018f09  xor     ecx, ecx; lpMutexAttributes
0x180018f0b  call    cs:__imp_CreateMutexExW
0x180018f12  nop     dword ptr [rax+rax+00h]
0x180018f17  mov     rdx, rax
0x180018f1a  lea     rcx, [rsp+270h+var_240]
0x180018f1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018f24  cmp     [rsp+270h+var_240], 0
0x180018f2a  jnz     short loc_180018F35
0x180018f2c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018f31  mov     ebx, eax
0x180018f33  jmp     short loc_180018FA8
0x180018f35  lea     rdx, [rsp+270h+var_238]
0x180018f3a  lea     rcx, [rsp+270h+var_240]
0x180018f3f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180018f44  lea     rdx, [rsp+270h+var_230]; void **
0x180018f49  mov     [rsp+270h+var_230], 0
0x180018f52  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018f57  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180018f5c  mov     ebx, eax
0x180018f5e  test    eax, eax
0x180018f60  jns     short loc_180018F89
0x180018f62  mov     edx, 12Eh; void *
0x180018f67  mov     rcx, [rbp+178h]; this
0x180018f6e  lea     r8, aWil; "wil"
0x180018f75  mov     r9d, eax; char *
0x180018f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f7d  lea     rcx, [rsp+270h+var_238]
0x180018f82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018f87  jmp     short loc_180018FA8
0x180018f89  mov     rcx, [rsp+270h+var_230]
0x180018f8e  test    rcx, rcx
0x180018f91  jz      short loc_180018FD9
0x180018f93  mov     [rdi], rcx
0x180018f96  mov     eax, [rcx]
0x180018f98  inc     eax
0x180018f9a  mov     [rcx], eax
0x180018f9c  lea     rcx, [rsp+270h+var_238]
0x180018fa1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018fa6  xor     ebx, ebx
0x180018fa8  lea     rcx, [rsp+270h+var_240]
0x180018fad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018fb2  mov     eax, ebx
0x180018fb4  mov     rcx, [rbp+170h+var_10]
0x180018fbb  xor     rcx, rsp; StackCookie
0x180018fbe  call    __security_check_cookie
0x180018fc3  lea     r11, [rsp+270h+var_s0]
0x180018fcb  mov     rbx, [r11+20h]
0x180018fcf  mov     rdi, [r11+28h]
0x180018fd3  mov     rsp, r11
0x180018fd6  pop     rbp
0x180018fd7  retn
0x180018fd9  mov     r8, rdi
0x180018fdc  lea     rdx, [rsp+270h+var_240]
0x180018fe1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018fe6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018feb  mov     ebx, eax
0x180018fed  test    eax, eax
0x180018fef  jns     short loc_180018F9C
0x180018ff1  mov     edx, 137h
0x180018ff6  jmp     loc_180018F67
```
