# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000aba8`
- end: `0x18000ad17`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b6d8`

## callees

- `0x180007c90`
- `0x18000aa54`
- `0x18000aa70`
- `0x18000aba8`
- `0x18000b438`
- `0x18000be40`
- `0x18000c464`
- `0x18000ca44`
- `0x18000cc08`
- `0x18000d004`
- `0x18000d114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ac25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ac25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000abe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000abe0`

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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18000aba8  mov     [rsp-8+arg_10], rbx
0x18000abad  mov     [rsp-8+arg_18], rdi
0x18000abb2  push    rbp
0x18000abb3  lea     rbp, [rsp-170h]
0x18000abbb  sub     rsp, 270h
0x18000abc2  mov     rax, cs:__security_cookie
0x18000abc9  xor     rax, rsp
0x18000abcc  mov     [rbp+170h+var_10], rax
0x18000abd3  mov     rdi, rdx
0x18000abd6  mov     qword ptr [rdx], 0
0x18000abdd  mov     rbx, rcx
0x18000abe0  call    cs:__imp_GetCurrentProcessId
0x18000abe6  mov     [rsp+270h+var_248], rbx
0x18000abeb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000abf2  mov     r9d, eax
0x18000abf5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000abfd  mov     edx, 104h; unsigned __int64
0x18000ac02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ac07  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000ac0c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ac12  mov     [rsp+270h+var_240], 0
0x18000ac1b  xor     r8d, r8d; dwFlags
0x18000ac1e  lea     rdx, [rsp+270h+Name]; lpName
0x18000ac23  xor     ecx, ecx; lpMutexAttributes
0x18000ac25  call    cs:__imp_CreateMutexExW
0x18000ac2b  mov     rdx, rax
0x18000ac2e  lea     rcx, [rsp+270h+var_240]
0x18000ac33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ac38  cmp     [rsp+270h+var_240], 0
0x18000ac3e  jnz     short loc_18000AC49
0x18000ac40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ac45  mov     ebx, eax
0x18000ac47  jmp     short loc_18000ACC5
0x18000ac49  lea     rdx, [rsp+270h+var_238]
0x18000ac4e  mov     [rsp+270h+var_238], 0
0x18000ac57  lea     rcx, [rsp+270h+var_240]
0x18000ac5c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000ac61  lea     rdx, [rsp+270h+var_230]; void **
0x18000ac66  mov     [rsp+270h+var_230], 0
0x18000ac6f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ac74  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000ac79  mov     ebx, eax
0x18000ac7b  test    eax, eax
0x18000ac7d  jns     short loc_18000ACA6
0x18000ac7f  mov     edx, 12Eh; void *
0x18000ac84  mov     rcx, [rbp+178h]; this
0x18000ac8b  lea     r8, aWil; "wil"
0x18000ac92  mov     r9d, eax; char *
0x18000ac95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac9a  lea     rcx, [rsp+270h+var_238]
0x18000ac9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aca4  jmp     short loc_18000ACC5
0x18000aca6  mov     rcx, [rsp+270h+var_230]
0x18000acab  test    rcx, rcx
0x18000acae  jz      short loc_18000ACF5
0x18000acb0  mov     [rdi], rcx
0x18000acb3  mov     eax, [rcx]
0x18000acb5  inc     eax
0x18000acb7  mov     [rcx], eax
0x18000acb9  lea     rcx, [rsp+270h+var_238]
0x18000acbe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000acc3  xor     ebx, ebx
0x18000acc5  lea     rcx, [rsp+270h+var_240]
0x18000acca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000accf  mov     eax, ebx
0x18000acd1  mov     rcx, [rbp+170h+var_10]
0x18000acd8  xor     rcx, rsp; StackCookie
0x18000acdb  call    __security_check_cookie
0x18000ace0  lea     r11, [rsp+270h+var_s0]
0x18000ace8  mov     rbx, [r11+20h]
0x18000acec  mov     rdi, [r11+28h]
0x18000acf0  mov     rsp, r11
0x18000acf3  pop     rbp
0x18000acf4  retn
0x18000acf5  mov     r8, rdi
0x18000acf8  lea     rdx, [rsp+270h+var_240]
0x18000acfd  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000ad02  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ad07  mov     ebx, eax
0x18000ad09  test    eax, eax
0x18000ad0b  jns     short loc_18000ACB9
0x18000ad0d  mov     edx, 137h
0x18000ad12  jmp     loc_18000AC84
```
