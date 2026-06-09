# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001fbe8`
- end: `0x18001fd5b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020e60`

## callees

- `0x18000c450`
- `0x18001be38`
- `0x18001c5f4`
- `0x18001c760`
- `0x18001d810`
- `0x18001f810`
- `0x18001f830`
- `0x18001fbe8`
- `0x180023488`
- `0x180023dc0`
- `0x180023f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001fc6b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001fc6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fc20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fc20`

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
0x18001fbe8  mov     [rsp-8+arg_10], rbx
0x18001fbed  mov     [rsp-8+arg_18], rdi
0x18001fbf2  push    rbp
0x18001fbf3  lea     rbp, [rsp-170h]
0x18001fbfb  sub     rsp, 270h
0x18001fc02  mov     rax, cs:__security_cookie
0x18001fc09  xor     rax, rsp
0x18001fc0c  mov     [rbp+170h+var_10], rax
0x18001fc13  mov     rdi, rdx
0x18001fc16  mov     qword ptr [rdx], 0
0x18001fc1d  mov     rbx, rcx
0x18001fc20  call    cs:__imp_GetCurrentProcessId
0x18001fc27  nop     dword ptr [rax+rax+00h]
0x18001fc2c  mov     [rsp+270h+var_248], rbx
0x18001fc31  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001fc38  mov     r9d, eax
0x18001fc3b  mov     [rsp+270h+var_250], 130h; int
0x18001fc43  mov     edx, 104h; unsigned __int64
0x18001fc48  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fc4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fc52  mov     r9d, 1F0001h; dwDesiredAccess
0x18001fc58  mov     [rsp+270h+var_240], 0
0x18001fc61  xor     r8d, r8d; dwFlags
0x18001fc64  lea     rdx, [rsp+270h+Name]; lpName
0x18001fc69  xor     ecx, ecx; lpMutexAttributes
0x18001fc6b  call    cs:__imp_CreateMutexExW
0x18001fc72  nop     dword ptr [rax+rax+00h]
0x18001fc77  mov     rdx, rax
0x18001fc7a  lea     rcx, [rsp+270h+var_240]
0x18001fc7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fc84  cmp     [rsp+270h+var_240], 0
0x18001fc8a  jnz     short loc_18001FC95
0x18001fc8c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001fc91  mov     ebx, eax
0x18001fc93  jmp     short loc_18001FD08
0x18001fc95  lea     rdx, [rsp+270h+var_238]
0x18001fc9a  lea     rcx, [rsp+270h+var_240]
0x18001fc9f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001fca4  lea     rdx, [rsp+270h+var_230]; void **
0x18001fca9  mov     [rsp+270h+var_230], 0
0x18001fcb2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fcb7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001fcbc  mov     ebx, eax
0x18001fcbe  test    eax, eax
0x18001fcc0  jns     short loc_18001FCE9
0x18001fcc2  mov     edx, 12Eh; void *
0x18001fcc7  mov     rcx, [rbp+178h]; this
0x18001fcce  lea     r8, aWil; "wil"
0x18001fcd5  mov     r9d, eax; char *
0x18001fcd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fcdd  lea     rcx, [rsp+270h+var_238]
0x18001fce2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fce7  jmp     short loc_18001FD08
0x18001fce9  mov     rcx, [rsp+270h+var_230]
0x18001fcee  test    rcx, rcx
0x18001fcf1  jz      short loc_18001FD39
0x18001fcf3  mov     [rdi], rcx
0x18001fcf6  mov     eax, [rcx]
0x18001fcf8  inc     eax
0x18001fcfa  mov     [rcx], eax
0x18001fcfc  lea     rcx, [rsp+270h+var_238]
0x18001fd01  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fd06  xor     ebx, ebx
0x18001fd08  lea     rcx, [rsp+270h+var_240]
0x18001fd0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fd12  mov     eax, ebx
0x18001fd14  mov     rcx, [rbp+170h+var_10]
0x18001fd1b  xor     rcx, rsp; StackCookie
0x18001fd1e  call    __security_check_cookie
0x18001fd23  lea     r11, [rsp+270h+var_s0]
0x18001fd2b  mov     rbx, [r11+20h]
0x18001fd2f  mov     rdi, [r11+28h]
0x18001fd33  mov     rsp, r11
0x18001fd36  pop     rbp
0x18001fd37  retn
0x18001fd39  mov     r8, rdi
0x18001fd3c  lea     rdx, [rsp+270h+var_240]
0x18001fd41  lea     rcx, [rsp+270h+Name]
0x18001fd46  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001fd4b  mov     ebx, eax
0x18001fd4d  test    eax, eax
0x18001fd4f  jns     short loc_18001FCFC
0x18001fd51  mov     edx, 137h
0x18001fd56  jmp     loc_18001FCC7
```
