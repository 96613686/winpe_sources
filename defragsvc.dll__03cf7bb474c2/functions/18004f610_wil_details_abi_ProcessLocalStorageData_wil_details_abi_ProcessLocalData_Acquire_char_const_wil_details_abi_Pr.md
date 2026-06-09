# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004f610`
- end: `0x18004f76f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180050460`

## callees

- `0x18001b300`
- `0x180041394`
- `0x18004f478`
- `0x18004f494`
- `0x18004f610`
- `0x180050c9c`
- `0x180051948`
- `0x180052008`
- `0x180052754`
- `0x180052800`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f68d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004f68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f648`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004f610  mov     [rsp-8+arg_10], rbx
0x18004f615  mov     [rsp-8+arg_18], rdi
0x18004f61a  push    rbp
0x18004f61b  lea     rbp, [rsp-170h]
0x18004f623  sub     rsp, 270h
0x18004f62a  mov     rax, cs:__security_cookie
0x18004f631  xor     rax, rsp
0x18004f634  mov     [rbp+170h+var_10], rax
0x18004f63b  mov     rdi, rdx
0x18004f63e  mov     qword ptr [rdx], 0
0x18004f645  mov     rbx, rcx
0x18004f648  call    cs:__imp_GetCurrentProcessId
0x18004f64e  mov     [rsp+270h+var_248], rbx
0x18004f653  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004f65a  mov     r9d, eax
0x18004f65d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18004f665  mov     edx, 104h; unsigned __int64
0x18004f66a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f66f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f674  mov     r9d, 1F0001h; dwDesiredAccess
0x18004f67a  mov     [rsp+270h+var_240], 0
0x18004f683  xor     r8d, r8d; dwFlags
0x18004f686  lea     rdx, [rsp+270h+Name]; lpName
0x18004f68b  xor     ecx, ecx; lpMutexAttributes
0x18004f68d  call    cs:__imp_CreateMutexExW
0x18004f693  mov     rdx, rax
0x18004f696  lea     rcx, [rsp+270h+var_240]
0x18004f69b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004f6a0  cmp     [rsp+270h+var_240], 0
0x18004f6a6  jnz     short loc_18004F6B1
0x18004f6a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004f6ad  mov     ebx, eax
0x18004f6af  jmp     short loc_18004F71D
0x18004f6b1  lea     rdx, [rsp+270h+var_238]
0x18004f6b6  lea     rcx, [rsp+270h+var_240]
0x18004f6bb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004f6c0  lea     rdx, [rsp+270h+var_230]; void **
0x18004f6c5  mov     [rsp+270h+var_230], 0
0x18004f6ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f6d3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004f6d8  mov     ebx, eax
0x18004f6da  test    eax, eax
0x18004f6dc  jns     short loc_18004F6FE
0x18004f6de  mov     edx, 12Eh; void *
0x18004f6e3  mov     rcx, [rbp+178h]; this
0x18004f6ea  mov     r9d, eax; char *
0x18004f6ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f6f2  lea     rcx, [rsp+270h+var_238]
0x18004f6f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f6fc  jmp     short loc_18004F71D
0x18004f6fe  mov     rcx, [rsp+270h+var_230]
0x18004f703  test    rcx, rcx
0x18004f706  jz      short loc_18004F74D
0x18004f708  mov     [rdi], rcx
0x18004f70b  mov     eax, [rcx]
0x18004f70d  inc     eax
0x18004f70f  mov     [rcx], eax
0x18004f711  lea     rcx, [rsp+270h+var_238]
0x18004f716  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f71b  xor     ebx, ebx
0x18004f71d  lea     rcx, [rsp+270h+var_240]
0x18004f722  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f727  mov     eax, ebx
0x18004f729  mov     rcx, [rbp+170h+var_10]
0x18004f730  xor     rcx, rsp; StackCookie
0x18004f733  call    __security_check_cookie
0x18004f738  lea     r11, [rsp+270h+var_s0]
0x18004f740  mov     rbx, [r11+20h]
0x18004f744  mov     rdi, [r11+28h]
0x18004f748  mov     rsp, r11
0x18004f74b  pop     rbp
0x18004f74c  retn
0x18004f74d  mov     r8, rdi
0x18004f750  lea     rdx, [rsp+270h+var_240]
0x18004f755  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004f75a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004f75f  mov     ebx, eax
0x18004f761  test    eax, eax
0x18004f763  jns     short loc_18004F711
0x18004f765  mov     edx, 137h
0x18004f76a  jmp     loc_18004F6E3
```
