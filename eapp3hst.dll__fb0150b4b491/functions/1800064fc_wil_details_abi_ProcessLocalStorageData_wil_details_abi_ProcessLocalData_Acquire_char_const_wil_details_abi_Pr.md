# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800064fc`
- end: `0x18000665b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008590`

## callees

- `0x1800017a0`
- `0x1800034ec`
- `0x180005fcc`
- `0x180005fe8`
- `0x1800064fc`
- `0x180007d08`
- `0x180008ff4`
- `0x18000a76c`
- `0x18000b16c`
- `0x18000ba30`
- `0x18000bd1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006534`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006579`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006579`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800064fc  mov     [rsp-8+arg_10], rbx
0x180006501  mov     [rsp-8+arg_18], rdi
0x180006506  push    rbp
0x180006507  lea     rbp, [rsp-170h]
0x18000650f  sub     rsp, 270h
0x180006516  mov     rax, cs:__security_cookie
0x18000651d  xor     rax, rsp
0x180006520  mov     [rbp+170h+var_10], rax
0x180006527  mov     rdi, rdx
0x18000652a  mov     qword ptr [rdx], 0
0x180006531  mov     rbx, rcx
0x180006534  call    cs:__imp_GetCurrentProcessId
0x18000653a  mov     [rsp+270h+var_248], rbx
0x18000653f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006546  mov     r9d, eax
0x180006549  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006551  mov     edx, 104h; unsigned __int64
0x180006556  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000655b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006560  mov     r9d, 1F0001h; dwDesiredAccess
0x180006566  mov     [rsp+270h+var_240], 0
0x18000656f  xor     r8d, r8d; dwFlags
0x180006572  lea     rdx, [rsp+270h+Name]; lpName
0x180006577  xor     ecx, ecx; lpMutexAttributes
0x180006579  call    cs:__imp_CreateMutexExW
0x18000657f  mov     rdx, rax
0x180006582  lea     rcx, [rsp+270h+var_240]
0x180006587  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000658c  cmp     [rsp+270h+var_240], 0
0x180006592  jnz     short loc_18000659D
0x180006594  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006599  mov     ebx, eax
0x18000659b  jmp     short loc_180006609
0x18000659d  lea     rdx, [rsp+270h+var_238]
0x1800065a2  lea     rcx, [rsp+270h+var_240]
0x1800065a7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800065ac  lea     rdx, [rsp+270h+var_230]; void **
0x1800065b1  mov     [rsp+270h+var_230], 0
0x1800065ba  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800065bf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800065c4  mov     ebx, eax
0x1800065c6  test    eax, eax
0x1800065c8  jns     short loc_1800065EA
0x1800065ca  mov     edx, 12Eh; void *
0x1800065cf  mov     rcx, [rbp+178h]; this
0x1800065d6  mov     r9d, eax; char *
0x1800065d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065de  lea     rcx, [rsp+270h+var_238]
0x1800065e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800065e8  jmp     short loc_180006609
0x1800065ea  mov     rcx, [rsp+270h+var_230]
0x1800065ef  test    rcx, rcx
0x1800065f2  jz      short loc_180006639
0x1800065f4  mov     [rdi], rcx
0x1800065f7  mov     eax, [rcx]
0x1800065f9  inc     eax
0x1800065fb  mov     [rcx], eax
0x1800065fd  lea     rcx, [rsp+270h+var_238]
0x180006602  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006607  xor     ebx, ebx
0x180006609  lea     rcx, [rsp+270h+var_240]
0x18000660e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006613  mov     eax, ebx
0x180006615  mov     rcx, [rbp+170h+var_10]
0x18000661c  xor     rcx, rsp; StackCookie
0x18000661f  call    __security_check_cookie
0x180006624  lea     r11, [rsp+270h+var_s0]
0x18000662c  mov     rbx, [r11+20h]
0x180006630  mov     rdi, [r11+28h]
0x180006634  mov     rsp, r11
0x180006637  pop     rbp
0x180006638  retn
0x180006639  mov     r8, rdi
0x18000663c  lea     rdx, [rsp+270h+var_240]
0x180006641  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006646  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000664b  mov     ebx, eax
0x18000664d  test    eax, eax
0x18000664f  jns     short loc_1800065FD
0x180006651  mov     edx, 137h
0x180006656  jmp     loc_1800065CF
```
