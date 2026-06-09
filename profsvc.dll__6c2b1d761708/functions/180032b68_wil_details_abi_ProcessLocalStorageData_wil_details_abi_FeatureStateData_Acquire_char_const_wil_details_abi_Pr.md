# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180032b68`
- end: `0x180032cdb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180041110`

## callees

- `0x1800172e0`
- `0x18001a9d0`
- `0x180030ad0`
- `0x180032b68`
- `0x180032e60`
- `0x180032fd8`
- `0x18003bc70`
- `0x18003e12c`
- `0x18003f8ac`
- `0x18003fa54`
- `0x18004129c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180032beb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180032beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032ba0`

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
0x180032b68  mov     [rsp-8+arg_10], rbx
0x180032b6d  mov     [rsp-8+arg_18], rdi
0x180032b72  push    rbp
0x180032b73  lea     rbp, [rsp-170h]
0x180032b7b  sub     rsp, 270h
0x180032b82  mov     rax, cs:__security_cookie
0x180032b89  xor     rax, rsp
0x180032b8c  mov     [rbp+170h+var_10], rax
0x180032b93  mov     rdi, rdx
0x180032b96  mov     qword ptr [rdx], 0
0x180032b9d  mov     rbx, rcx
0x180032ba0  call    cs:__imp_GetCurrentProcessId
0x180032ba7  nop     dword ptr [rax+rax+00h]
0x180032bac  mov     [rsp+270h+var_248], rbx
0x180032bb1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180032bb8  mov     r9d, eax
0x180032bbb  mov     [rsp+270h+var_250], 130h; int
0x180032bc3  mov     edx, 104h; unsigned __int64
0x180032bc8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180032bcd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032bd2  mov     r9d, 1F0001h; dwDesiredAccess
0x180032bd8  mov     [rsp+270h+var_240], 0
0x180032be1  xor     r8d, r8d; dwFlags
0x180032be4  lea     rdx, [rsp+270h+Name]; lpName
0x180032be9  xor     ecx, ecx; lpMutexAttributes
0x180032beb  call    cs:__imp_CreateMutexExW
0x180032bf2  nop     dword ptr [rax+rax+00h]
0x180032bf7  mov     rdx, rax
0x180032bfa  lea     rcx, [rsp+270h+var_240]
0x180032bff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180032c04  cmp     [rsp+270h+var_240], 0
0x180032c0a  jnz     short loc_180032C15
0x180032c0c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032c11  mov     ebx, eax
0x180032c13  jmp     short loc_180032C88
0x180032c15  lea     rdx, [rsp+270h+var_238]
0x180032c1a  lea     rcx, [rsp+270h+var_240]
0x180032c1f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180032c24  lea     rdx, [rsp+270h+var_230]; void **
0x180032c29  mov     [rsp+270h+var_230], 0
0x180032c32  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180032c37  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180032c3c  mov     ebx, eax
0x180032c3e  test    eax, eax
0x180032c40  jns     short loc_180032C69
0x180032c42  mov     edx, 12Eh; void *
0x180032c47  mov     rcx, [rbp+178h]; this
0x180032c4e  lea     r8, aWil; "wil"
0x180032c55  mov     r9d, eax; char *
0x180032c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c5d  lea     rcx, [rsp+270h+var_238]
0x180032c62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032c67  jmp     short loc_180032C88
0x180032c69  mov     rcx, [rsp+270h+var_230]
0x180032c6e  test    rcx, rcx
0x180032c71  jz      short loc_180032CB9
0x180032c73  mov     [rdi], rcx
0x180032c76  mov     eax, [rcx]
0x180032c78  inc     eax
0x180032c7a  mov     [rcx], eax
0x180032c7c  lea     rcx, [rsp+270h+var_238]
0x180032c81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032c86  xor     ebx, ebx
0x180032c88  lea     rcx, [rsp+270h+var_240]
0x180032c8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032c92  mov     eax, ebx
0x180032c94  mov     rcx, [rbp+170h+var_10]
0x180032c9b  xor     rcx, rsp; StackCookie
0x180032c9e  call    __security_check_cookie
0x180032ca3  lea     r11, [rsp+270h+var_s0]
0x180032cab  mov     rbx, [r11+20h]
0x180032caf  mov     rdi, [r11+28h]
0x180032cb3  mov     rsp, r11
0x180032cb6  pop     rbp
0x180032cb7  retn
0x180032cb9  mov     r8, rdi
0x180032cbc  lea     rdx, [rsp+270h+var_240]
0x180032cc1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180032cc6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180032ccb  mov     ebx, eax
0x180032ccd  test    eax, eax
0x180032ccf  jns     short loc_180032C7C
0x180032cd1  mov     edx, 137h
0x180032cd6  jmp     loc_180032C47
```
