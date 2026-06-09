# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800038d0`
- end: `0x180003a36`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004900`

## callees

- `0x180003528`
- `0x180003544`
- `0x1800038d0`
- `0x180004618`
- `0x180005240`
- `0x18000635c`
- `0x180006b48`
- `0x180006f30`
- `0x1800078a4`
- `0x180008010`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003908`
- `KERNEL32!GetCurrentProcessId` at `0x180003908`
- `KERNEL32!CreateMutexExW` at `0x18000394d`
- `KERNEL32!CreateMutexExW` at `0x18000394d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp-8+arg_10], rbx
0x1800038d5  mov     [rsp-8+arg_18], rdi
0x1800038da  push    rbp
0x1800038db  lea     rbp, [rsp-170h]
0x1800038e3  sub     rsp, 270h
0x1800038ea  mov     rax, cs:__security_cookie
0x1800038f1  xor     rax, rsp
0x1800038f4  mov     [rbp+170h+var_10], rax
0x1800038fb  mov     rdi, rdx
0x1800038fe  mov     qword ptr [rdx], 0
0x180003905  mov     rbx, rcx
0x180003908  call    cs:__imp_GetCurrentProcessId
0x18000390e  mov     [rsp+270h+var_248], rbx
0x180003913  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000391a  mov     r9d, eax
0x18000391d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003925  mov     edx, 104h; unsigned __int64
0x18000392a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000392f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003934  mov     r9d, 1F0001h; dwDesiredAccess
0x18000393a  mov     [rsp+270h+var_240], 0
0x180003943  xor     r8d, r8d; dwFlags
0x180003946  lea     rdx, [rsp+270h+Name]; lpName
0x18000394b  xor     ecx, ecx; lpMutexAttributes
0x18000394d  call    cs:__imp_CreateMutexExW
0x180003953  mov     rdx, rax
0x180003956  lea     rcx, [rsp+270h+var_240]
0x18000395b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003960  cmp     [rsp+270h+var_240], 0
0x180003966  jnz     short loc_180003971
0x180003968  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000396d  mov     ebx, eax
0x18000396f  jmp     short loc_1800039E4
0x180003971  lea     rdx, [rsp+270h+var_238]
0x180003976  lea     rcx, [rsp+270h+var_240]
0x18000397b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003980  lea     rdx, [rsp+270h+var_230]; void **
0x180003985  mov     [rsp+270h+var_230], 0
0x18000398e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003993  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003998  mov     ebx, eax
0x18000399a  test    eax, eax
0x18000399c  jns     short loc_1800039C5
0x18000399e  mov     edx, 12Eh; void *
0x1800039a3  mov     rcx, [rbp+178h]; this
0x1800039aa  lea     r8, aWil; "wil"
0x1800039b1  mov     r9d, eax; char *
0x1800039b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039b9  lea     rcx, [rsp+270h+var_238]
0x1800039be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800039c3  jmp     short loc_1800039E4
0x1800039c5  mov     rcx, [rsp+270h+var_230]
0x1800039ca  test    rcx, rcx
0x1800039cd  jz      short loc_180003A14
0x1800039cf  mov     [rdi], rcx
0x1800039d2  mov     eax, [rcx]
0x1800039d4  inc     eax
0x1800039d6  mov     [rcx], eax
0x1800039d8  lea     rcx, [rsp+270h+var_238]
0x1800039dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800039e2  xor     ebx, ebx
0x1800039e4  lea     rcx, [rsp+270h+var_240]
0x1800039e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800039ee  mov     eax, ebx
0x1800039f0  mov     rcx, [rbp+170h+var_10]
0x1800039f7  xor     rcx, rsp; StackCookie
0x1800039fa  call    __security_check_cookie
0x1800039ff  lea     r11, [rsp+270h+var_s0]
0x180003a07  mov     rbx, [r11+20h]
0x180003a0b  mov     rdi, [r11+28h]
0x180003a0f  mov     rsp, r11
0x180003a12  pop     rbp
0x180003a13  retn
0x180003a14  mov     r8, rdi
0x180003a17  lea     rdx, [rsp+270h+var_240]
0x180003a1c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003a21  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003a26  mov     ebx, eax
0x180003a28  test    eax, eax
0x180003a2a  jns     short loc_1800039D8
0x180003a2c  mov     edx, 137h
0x180003a31  jmp     loc_1800039A3
```
