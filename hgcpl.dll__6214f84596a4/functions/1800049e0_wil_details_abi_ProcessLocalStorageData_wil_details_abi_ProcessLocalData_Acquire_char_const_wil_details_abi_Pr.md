# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800049e0`
- end: `0x180004b3f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005530`

## callees

- `0x180004960`
- `0x18000497c`
- `0x1800049e0`
- `0x180005248`
- `0x180005c98`
- `0x180006070`
- `0x180006408`
- `0x180006518`
- `0x180006980`
- `0x180006a40`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a5d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a18`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800049e0  mov     [rsp-8+arg_10], rbx
0x1800049e5  mov     [rsp-8+arg_18], rdi
0x1800049ea  push    rbp
0x1800049eb  lea     rbp, [rsp-170h]
0x1800049f3  sub     rsp, 270h
0x1800049fa  mov     rax, cs:__security_cookie
0x180004a01  xor     rax, rsp
0x180004a04  mov     [rbp+170h+var_10], rax
0x180004a0b  mov     rdi, rdx
0x180004a0e  mov     qword ptr [rdx], 0
0x180004a15  mov     rbx, rcx
0x180004a18  call    cs:__imp_GetCurrentProcessId
0x180004a1e  mov     [rsp+270h+var_248], rbx
0x180004a23  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004a2a  mov     r9d, eax
0x180004a2d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004a35  mov     edx, 104h; unsigned __int64
0x180004a3a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004a3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004a44  mov     r9d, 1F0001h; dwDesiredAccess
0x180004a4a  mov     [rsp+270h+var_240], 0
0x180004a53  xor     r8d, r8d; dwFlags
0x180004a56  lea     rdx, [rsp+270h+Name]; lpName
0x180004a5b  xor     ecx, ecx; lpMutexAttributes
0x180004a5d  call    cs:__imp_CreateMutexExW
0x180004a63  mov     rdx, rax
0x180004a66  lea     rcx, [rsp+270h+var_240]
0x180004a6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004a70  cmp     [rsp+270h+var_240], 0
0x180004a76  jnz     short loc_180004A81
0x180004a78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a7d  mov     ebx, eax
0x180004a7f  jmp     short loc_180004AED
0x180004a81  lea     rdx, [rsp+270h+var_238]
0x180004a86  lea     rcx, [rsp+270h+var_240]
0x180004a8b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004a90  lea     rdx, [rsp+270h+var_230]; void **
0x180004a95  mov     [rsp+270h+var_230], 0
0x180004a9e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004aa3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004aa8  mov     ebx, eax
0x180004aaa  test    eax, eax
0x180004aac  jns     short loc_180004ACE
0x180004aae  mov     edx, 12Eh; void *
0x180004ab3  mov     rcx, [rbp+178h]; this
0x180004aba  mov     r9d, eax; char *
0x180004abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ac2  lea     rcx, [rsp+270h+var_238]
0x180004ac7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004acc  jmp     short loc_180004AED
0x180004ace  mov     rcx, [rsp+270h+var_230]
0x180004ad3  test    rcx, rcx
0x180004ad6  jz      short loc_180004B1D
0x180004ad8  mov     [rdi], rcx
0x180004adb  mov     eax, [rcx]
0x180004add  inc     eax
0x180004adf  mov     [rcx], eax
0x180004ae1  lea     rcx, [rsp+270h+var_238]
0x180004ae6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004aeb  xor     ebx, ebx
0x180004aed  lea     rcx, [rsp+270h+var_240]
0x180004af2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004af7  mov     eax, ebx
0x180004af9  mov     rcx, [rbp+170h+var_10]
0x180004b00  xor     rcx, rsp; StackCookie
0x180004b03  call    __security_check_cookie
0x180004b08  lea     r11, [rsp+270h+var_s0]
0x180004b10  mov     rbx, [r11+20h]
0x180004b14  mov     rdi, [r11+28h]
0x180004b18  mov     rsp, r11
0x180004b1b  pop     rbp
0x180004b1c  retn
0x180004b1d  mov     r8, rdi
0x180004b20  lea     rdx, [rsp+270h+var_240]
0x180004b25  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004b2a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004b2f  mov     ebx, eax
0x180004b31  test    eax, eax
0x180004b33  jns     short loc_180004AE1
0x180004b35  mov     edx, 137h
0x180004b3a  jmp     loc_180004AB3
```
