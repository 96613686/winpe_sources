# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18007858c`
- end: `0x1800786f8`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800799b0`

## callees

- `0x180078090`
- `0x1800780b0`
- `0x18007858c`
- `0x180079760`
- `0x18007a7f4`
- `0x18007c104`
- `0x18007c744`
- `0x18007ca74`
- `0x18007d2f0`
- `0x18007d554`
- `0x180093c00`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800785c4`
- `KERNEL32!GetCurrentProcessId` at `0x1800785c4`
- `KERNEL32!CreateMutexExW` at `0x18007860f`
- `KERNEL32!CreateMutexExW` at `0x18007860f`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18007858c  mov     [rsp-8+arg_10], rbx
0x180078591  mov     [rsp-8+arg_18], rdi
0x180078596  push    rbp
0x180078597  lea     rbp, [rsp-170h]
0x18007859f  sub     rsp, 270h
0x1800785a6  mov     rax, cs:__security_cookie
0x1800785ad  xor     rax, rsp
0x1800785b0  mov     [rbp+170h+var_10], rax
0x1800785b7  mov     rdi, rdx
0x1800785ba  mov     qword ptr [rdx], 0
0x1800785c1  mov     rbx, rcx
0x1800785c4  call    cs:__imp_GetCurrentProcessId
0x1800785cb  nop     dword ptr [rax+rax+00h]
0x1800785d0  mov     [rsp+270h+var_248], rbx
0x1800785d5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800785dc  mov     r9d, eax
0x1800785df  mov     [rsp+270h+var_250], 130h; int
0x1800785e7  mov     edx, 104h; unsigned __int64
0x1800785ec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800785f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800785f6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800785fc  mov     [rsp+270h+var_240], 0
0x180078605  xor     r8d, r8d; dwFlags
0x180078608  lea     rdx, [rsp+270h+Name]; lpName
0x18007860d  xor     ecx, ecx; lpMutexAttributes
0x18007860f  call    cs:__imp_CreateMutexExW
0x180078616  nop     dword ptr [rax+rax+00h]
0x18007861b  mov     rdx, rax
0x18007861e  lea     rcx, [rsp+270h+var_240]
0x180078623  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180078628  cmp     [rsp+270h+var_240], 0
0x18007862e  jnz     short loc_180078639
0x180078630  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180078635  mov     ebx, eax
0x180078637  jmp     short loc_1800786A5
0x180078639  lea     rdx, [rsp+270h+var_238]
0x18007863e  lea     rcx, [rsp+270h+var_240]
0x180078643  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180078648  lea     rdx, [rsp+270h+var_230]; void **
0x18007864d  mov     [rsp+270h+var_230], 0
0x180078656  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007865b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180078660  mov     ebx, eax
0x180078662  test    eax, eax
0x180078664  jns     short loc_180078686
0x180078666  mov     edx, 12Eh; void *
0x18007866b  mov     rcx, [rbp+178h]; this
0x180078672  mov     r9d, eax; char *
0x180078675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007867a  lea     rcx, [rsp+270h+var_238]
0x18007867f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180078684  jmp     short loc_1800786A5
0x180078686  mov     rcx, [rsp+270h+var_230]
0x18007868b  test    rcx, rcx
0x18007868e  jz      short loc_1800786D6
0x180078690  mov     [rdi], rcx
0x180078693  mov     eax, [rcx]
0x180078695  inc     eax
0x180078697  mov     [rcx], eax
0x180078699  lea     rcx, [rsp+270h+var_238]
0x18007869e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800786a3  xor     ebx, ebx
0x1800786a5  lea     rcx, [rsp+270h+var_240]
0x1800786aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800786af  mov     eax, ebx
0x1800786b1  mov     rcx, [rbp+170h+var_10]
0x1800786b8  xor     rcx, rsp; StackCookie
0x1800786bb  call    __security_check_cookie
0x1800786c0  lea     r11, [rsp+270h+var_s0]
0x1800786c8  mov     rbx, [r11+20h]
0x1800786cc  mov     rdi, [r11+28h]
0x1800786d0  mov     rsp, r11
0x1800786d3  pop     rbp
0x1800786d4  retn
0x1800786d6  mov     r8, rdi
0x1800786d9  lea     rdx, [rsp+270h+var_240]
0x1800786de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800786e3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800786e8  mov     ebx, eax
0x1800786ea  test    eax, eax
0x1800786ec  jns     short loc_180078699
0x1800786ee  mov     edx, 137h
0x1800786f3  jmp     loc_18007866B
```
