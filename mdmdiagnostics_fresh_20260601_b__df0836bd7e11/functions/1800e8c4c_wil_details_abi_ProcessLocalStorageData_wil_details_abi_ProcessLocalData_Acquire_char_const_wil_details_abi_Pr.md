# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800e8c4c`
- end: `0x1800e8db2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ea934`

## callees

- `0x180019000`
- `0x1800e7cc0`
- `0x1800e7cdc`
- `0x1800e8c4c`
- `0x1800ea608`
- `0x1800eb46c`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800edbc8`
- `0x1800ef854`
- `0x1800f12c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e8cc9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e8cc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e8c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e8c84`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800e8c4c  mov     [rsp-8+arg_10], rbx
0x1800e8c51  mov     [rsp-8+arg_18], rdi
0x1800e8c56  push    rbp
0x1800e8c57  lea     rbp, [rsp-170h]
0x1800e8c5f  sub     rsp, 270h
0x1800e8c66  mov     rax, cs:__security_cookie
0x1800e8c6d  xor     rax, rsp
0x1800e8c70  mov     [rbp+170h+var_10], rax
0x1800e8c77  mov     rdi, rdx
0x1800e8c7a  mov     qword ptr [rdx], 0
0x1800e8c81  mov     rbx, rcx
0x1800e8c84  call    cs:__imp_GetCurrentProcessId
0x1800e8c8a  mov     [rsp+270h+var_248], rbx
0x1800e8c8f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800e8c96  mov     r9d, eax
0x1800e8c99  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800e8ca1  mov     edx, 104h; unsigned __int64
0x1800e8ca6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e8cab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e8cb0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800e8cb6  mov     [rsp+270h+var_240], 0
0x1800e8cbf  xor     r8d, r8d; dwFlags
0x1800e8cc2  lea     rdx, [rsp+270h+Name]; lpName
0x1800e8cc7  xor     ecx, ecx; lpMutexAttributes
0x1800e8cc9  call    cs:__imp_CreateMutexExW
0x1800e8ccf  mov     rdx, rax
0x1800e8cd2  lea     rcx, [rsp+270h+var_240]
0x1800e8cd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800e8cdc  cmp     [rsp+270h+var_240], 0
0x1800e8ce2  jnz     short loc_1800E8CED
0x1800e8ce4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e8ce9  mov     ebx, eax
0x1800e8ceb  jmp     short loc_1800E8D60
0x1800e8ced  lea     rdx, [rsp+270h+var_238]
0x1800e8cf2  lea     rcx, [rsp+270h+var_240]
0x1800e8cf7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800e8cfc  lea     rdx, [rsp+270h+var_230]; void **
0x1800e8d01  mov     [rsp+270h+var_230], 0
0x1800e8d0a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e8d0f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800e8d14  mov     ebx, eax
0x1800e8d16  test    eax, eax
0x1800e8d18  jns     short loc_1800E8D41
0x1800e8d1a  mov     edx, 12Eh; void *
0x1800e8d1f  mov     rcx, [rbp+178h]; this
0x1800e8d26  lea     r8, aWil; "wil"
0x1800e8d2d  mov     r9d, eax; char *
0x1800e8d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e8d35  lea     rcx, [rsp+270h+var_238]
0x1800e8d3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e8d3f  jmp     short loc_1800E8D60
0x1800e8d41  mov     rcx, [rsp+270h+var_230]
0x1800e8d46  test    rcx, rcx
0x1800e8d49  jz      short loc_1800E8D90
0x1800e8d4b  mov     [rdi], rcx
0x1800e8d4e  mov     eax, [rcx]
0x1800e8d50  inc     eax
0x1800e8d52  mov     [rcx], eax
0x1800e8d54  lea     rcx, [rsp+270h+var_238]
0x1800e8d59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e8d5e  xor     ebx, ebx
0x1800e8d60  lea     rcx, [rsp+270h+var_240]
0x1800e8d65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e8d6a  mov     eax, ebx
0x1800e8d6c  mov     rcx, [rbp+170h+var_10]
0x1800e8d73  xor     rcx, rsp; StackCookie
0x1800e8d76  call    __security_check_cookie
0x1800e8d7b  lea     r11, [rsp+270h+var_s0]
0x1800e8d83  mov     rbx, [r11+20h]
0x1800e8d87  mov     rdi, [r11+28h]
0x1800e8d8b  mov     rsp, r11
0x1800e8d8e  pop     rbp
0x1800e8d8f  retn
0x1800e8d90  mov     r8, rdi
0x1800e8d93  lea     rdx, [rsp+270h+var_240]
0x1800e8d98  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e8d9d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800e8da2  mov     ebx, eax
0x1800e8da4  test    eax, eax
0x1800e8da6  jns     short loc_1800E8D54
0x1800e8da8  mov     edx, 137h
0x1800e8dad  jmp     loc_1800E8D1F
```
