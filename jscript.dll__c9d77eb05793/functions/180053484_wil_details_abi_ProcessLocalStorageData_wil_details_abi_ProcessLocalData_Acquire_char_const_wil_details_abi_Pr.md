# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180053484`
- end: `0x1800535e3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005978c`

## callees

- `0x180042814`
- `0x180042a84`
- `0x180042ad8`
- `0x180042fb8`
- `0x180050c78`
- `0x18005252c`
- `0x180052c44`
- `0x180052ef4`
- `0x180053484`
- `0x1800535ec`
- `0x1800942d0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180053501`
- `KERNEL32!CreateMutexExW` at `0x180053501`
- `KERNEL32!GetCurrentProcessId` at `0x1800534bc`
- `KERNEL32!GetCurrentProcessId` at `0x1800534bc`

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
0x180053484  mov     [rsp-8+arg_10], rbx
0x180053489  mov     [rsp-8+arg_18], rdi
0x18005348e  push    rbp
0x18005348f  lea     rbp, [rsp-170h]
0x180053497  sub     rsp, 270h
0x18005349e  mov     rax, cs:__security_cookie
0x1800534a5  xor     rax, rsp
0x1800534a8  mov     [rbp+170h+var_10], rax
0x1800534af  mov     rdi, rdx
0x1800534b2  mov     qword ptr [rdx], 0
0x1800534b9  mov     rbx, rcx
0x1800534bc  call    cs:__imp_GetCurrentProcessId
0x1800534c2  mov     [rsp+270h+var_248], rbx
0x1800534c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800534ce  mov     r9d, eax
0x1800534d1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800534d9  mov     edx, 104h; unsigned __int64
0x1800534de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800534e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800534e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800534ee  mov     [rsp+270h+var_240], 0
0x1800534f7  xor     r8d, r8d; dwFlags
0x1800534fa  lea     rdx, [rsp+270h+Name]; lpName
0x1800534ff  xor     ecx, ecx; lpMutexAttributes
0x180053501  call    cs:__imp_CreateMutexExW
0x180053507  mov     rdx, rax
0x18005350a  lea     rcx, [rsp+270h+var_240]
0x18005350f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180053514  cmp     [rsp+270h+var_240], 0
0x18005351a  jnz     short loc_180053525
0x18005351c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180053521  mov     ebx, eax
0x180053523  jmp     short loc_180053591
0x180053525  lea     rdx, [rsp+270h+var_238]
0x18005352a  lea     rcx, [rsp+270h+var_240]
0x18005352f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180053534  lea     rdx, [rsp+270h+var_230]; void **
0x180053539  mov     [rsp+270h+var_230], 0
0x180053542  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180053547  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18005354c  mov     ebx, eax
0x18005354e  test    eax, eax
0x180053550  jns     short loc_180053572
0x180053552  mov     edx, 12Eh; void *
0x180053557  mov     rcx, [rbp+178h]; this
0x18005355e  mov     r9d, eax; char *
0x180053561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053566  lea     rcx, [rsp+270h+var_238]
0x18005356b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180053570  jmp     short loc_180053591
0x180053572  mov     rcx, [rsp+270h+var_230]
0x180053577  test    rcx, rcx
0x18005357a  jz      short loc_1800535C1
0x18005357c  mov     [rdi], rcx
0x18005357f  mov     eax, [rcx]
0x180053581  inc     eax
0x180053583  mov     [rcx], eax
0x180053585  lea     rcx, [rsp+270h+var_238]
0x18005358a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005358f  xor     ebx, ebx
0x180053591  lea     rcx, [rsp+270h+var_240]
0x180053596  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005359b  mov     eax, ebx
0x18005359d  mov     rcx, [rbp+170h+var_10]
0x1800535a4  xor     rcx, rsp; StackCookie
0x1800535a7  call    __security_check_cookie
0x1800535ac  lea     r11, [rsp+270h+var_s0]
0x1800535b4  mov     rbx, [r11+20h]
0x1800535b8  mov     rdi, [r11+28h]
0x1800535bc  mov     rsp, r11
0x1800535bf  pop     rbp
0x1800535c0  retn
0x1800535c1  mov     r8, rdi
0x1800535c4  lea     rdx, [rsp+270h+var_240]
0x1800535c9  lea     rcx, [rsp+270h+Name]
0x1800535ce  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800535d3  mov     ebx, eax
0x1800535d5  test    eax, eax
0x1800535d7  jns     short loc_180053585
0x1800535d9  mov     edx, 137h
0x1800535de  jmp     loc_180053557
```
