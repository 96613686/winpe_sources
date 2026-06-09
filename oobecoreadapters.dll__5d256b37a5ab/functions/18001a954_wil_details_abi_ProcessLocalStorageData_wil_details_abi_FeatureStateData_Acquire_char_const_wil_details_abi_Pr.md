# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001a954`
- end: `0x18001aaba`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001b2c0`

## callees

- `0x180002b60`
- `0x180005378`
- `0x180005394`
- `0x180006148`
- `0x1800076d4`
- `0x180007d34`
- `0x180008018`
- `0x180008414`
- `0x18000890c`
- `0x18001a954`
- `0x18001b634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001a9d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001a9d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a98c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a98c`

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
0x18001a954  mov     [rsp-8+arg_10], rbx
0x18001a959  mov     [rsp-8+arg_18], rdi
0x18001a95e  push    rbp
0x18001a95f  lea     rbp, [rsp-170h]
0x18001a967  sub     rsp, 270h
0x18001a96e  mov     rax, cs:__security_cookie
0x18001a975  xor     rax, rsp
0x18001a978  mov     [rbp+170h+var_10], rax
0x18001a97f  mov     rdi, rdx
0x18001a982  mov     qword ptr [rdx], 0
0x18001a989  mov     rbx, rcx
0x18001a98c  call    cs:__imp_GetCurrentProcessId
0x18001a992  mov     [rsp+270h+var_248], rbx
0x18001a997  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001a99e  mov     r9d, eax
0x18001a9a1  mov     [rsp+270h+var_250], 130h; int
0x18001a9a9  mov     edx, 104h; unsigned __int64
0x18001a9ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001a9b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a9b8  mov     r9d, 1F0001h; dwDesiredAccess
0x18001a9be  mov     [rsp+270h+var_240], 0
0x18001a9c7  xor     r8d, r8d; dwFlags
0x18001a9ca  lea     rdx, [rsp+270h+Name]; lpName
0x18001a9cf  xor     ecx, ecx; lpMutexAttributes
0x18001a9d1  call    cs:__imp_CreateMutexExW
0x18001a9d7  mov     rdx, rax
0x18001a9da  lea     rcx, [rsp+270h+var_240]
0x18001a9df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001a9e4  cmp     [rsp+270h+var_240], 0
0x18001a9ea  jnz     short loc_18001A9F5
0x18001a9ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a9f1  mov     ebx, eax
0x18001a9f3  jmp     short loc_18001AA68
0x18001a9f5  lea     rdx, [rsp+270h+var_238]
0x18001a9fa  lea     rcx, [rsp+270h+var_240]
0x18001a9ff  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001aa04  lea     rdx, [rsp+270h+var_230]; void **
0x18001aa09  mov     [rsp+270h+var_230], 0
0x18001aa12  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001aa17  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001aa1c  mov     ebx, eax
0x18001aa1e  test    eax, eax
0x18001aa20  jns     short loc_18001AA49
0x18001aa22  mov     edx, 12Eh; void *
0x18001aa27  mov     rcx, [rbp+178h]; this
0x18001aa2e  lea     r8, aWil; "wil"
0x18001aa35  mov     r9d, eax; char *
0x18001aa38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa3d  lea     rcx, [rsp+270h+var_238]
0x18001aa42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aa47  jmp     short loc_18001AA68
0x18001aa49  mov     rcx, [rsp+270h+var_230]
0x18001aa4e  test    rcx, rcx
0x18001aa51  jz      short loc_18001AA98
0x18001aa53  mov     [rdi], rcx
0x18001aa56  mov     eax, [rcx]
0x18001aa58  inc     eax
0x18001aa5a  mov     [rcx], eax
0x18001aa5c  lea     rcx, [rsp+270h+var_238]
0x18001aa61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aa66  xor     ebx, ebx
0x18001aa68  lea     rcx, [rsp+270h+var_240]
0x18001aa6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aa72  mov     eax, ebx
0x18001aa74  mov     rcx, [rbp+170h+var_10]
0x18001aa7b  xor     rcx, rsp; StackCookie
0x18001aa7e  call    __security_check_cookie
0x18001aa83  lea     r11, [rsp+270h+var_s0]
0x18001aa8b  mov     rbx, [r11+20h]
0x18001aa8f  mov     rdi, [r11+28h]
0x18001aa93  mov     rsp, r11
0x18001aa96  pop     rbp
0x18001aa97  retn
0x18001aa98  mov     r8, rdi
0x18001aa9b  lea     rdx, [rsp+270h+var_240]
0x18001aaa0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001aaa5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001aaaa  mov     ebx, eax
0x18001aaac  test    eax, eax
0x18001aaae  jns     short loc_18001AA5C
0x18001aab0  mov     edx, 137h
0x18001aab5  jmp     loc_18001AA27
```
