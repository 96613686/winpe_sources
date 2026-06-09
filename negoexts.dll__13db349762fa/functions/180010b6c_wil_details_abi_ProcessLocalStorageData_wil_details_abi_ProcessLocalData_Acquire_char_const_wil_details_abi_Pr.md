# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180010b6c`
- end: `0x180010ccb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180011f9c`

## callees

- `0x1800109dc`
- `0x1800109f8`
- `0x180010b6c`
- `0x180011cf8`
- `0x1800129bc`
- `0x180013ca4`
- `0x18001445c`
- `0x1800148fc`
- `0x18001518c`
- `0x1800152e0`
- `0x18001ed20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010ba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010ba4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010be9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010be9`

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
0x180010b6c  mov     [rsp-8+arg_10], rbx
0x180010b71  mov     [rsp-8+arg_18], rdi
0x180010b76  push    rbp
0x180010b77  lea     rbp, [rsp-170h]
0x180010b7f  sub     rsp, 270h
0x180010b86  mov     rax, cs:__security_cookie
0x180010b8d  xor     rax, rsp
0x180010b90  mov     [rbp+170h+var_10], rax
0x180010b97  mov     rdi, rdx
0x180010b9a  mov     qword ptr [rdx], 0
0x180010ba1  mov     rbx, rcx
0x180010ba4  call    cs:__imp_GetCurrentProcessId
0x180010baa  mov     [rsp+270h+var_248], rbx
0x180010baf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010bb6  mov     r9d, eax
0x180010bb9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180010bc1  mov     edx, 104h; unsigned __int64
0x180010bc6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010bcb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010bd0  mov     r9d, 1F0001h; dwDesiredAccess
0x180010bd6  mov     [rsp+270h+var_240], 0
0x180010bdf  xor     r8d, r8d; dwFlags
0x180010be2  lea     rdx, [rsp+270h+Name]; lpName
0x180010be7  xor     ecx, ecx; lpMutexAttributes
0x180010be9  call    cs:__imp_CreateMutexExW
0x180010bef  mov     rdx, rax
0x180010bf2  lea     rcx, [rsp+270h+var_240]
0x180010bf7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010bfc  cmp     [rsp+270h+var_240], 0
0x180010c02  jnz     short loc_180010C0D
0x180010c04  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010c09  mov     ebx, eax
0x180010c0b  jmp     short loc_180010C79
0x180010c0d  lea     rdx, [rsp+270h+var_238]
0x180010c12  lea     rcx, [rsp+270h+var_240]
0x180010c17  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010c1c  lea     rdx, [rsp+270h+var_230]; void **
0x180010c21  mov     [rsp+270h+var_230], 0
0x180010c2a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010c2f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180010c34  mov     ebx, eax
0x180010c36  test    eax, eax
0x180010c38  jns     short loc_180010C5A
0x180010c3a  mov     edx, 12Eh; void *
0x180010c3f  mov     rcx, [rbp+178h]; this
0x180010c46  mov     r9d, eax; char *
0x180010c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c4e  lea     rcx, [rsp+270h+var_238]
0x180010c53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010c58  jmp     short loc_180010C79
0x180010c5a  mov     rcx, [rsp+270h+var_230]
0x180010c5f  test    rcx, rcx
0x180010c62  jz      short loc_180010CA9
0x180010c64  mov     [rdi], rcx
0x180010c67  mov     eax, [rcx]
0x180010c69  inc     eax
0x180010c6b  mov     [rcx], eax
0x180010c6d  lea     rcx, [rsp+270h+var_238]
0x180010c72  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010c77  xor     ebx, ebx
0x180010c79  lea     rcx, [rsp+270h+var_240]
0x180010c7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010c83  mov     eax, ebx
0x180010c85  mov     rcx, [rbp+170h+var_10]
0x180010c8c  xor     rcx, rsp; StackCookie
0x180010c8f  call    __security_check_cookie
0x180010c94  lea     r11, [rsp+270h+var_s0]
0x180010c9c  mov     rbx, [r11+20h]
0x180010ca0  mov     rdi, [r11+28h]
0x180010ca4  mov     rsp, r11
0x180010ca7  pop     rbp
0x180010ca8  retn
0x180010ca9  mov     r8, rdi
0x180010cac  lea     rdx, [rsp+270h+var_240]
0x180010cb1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010cb6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010cbb  mov     ebx, eax
0x180010cbd  test    eax, eax
0x180010cbf  jns     short loc_180010C6D
0x180010cc1  mov     edx, 137h
0x180010cc6  jmp     loc_180010C3F
```
