# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800182ac`
- end: `0x180018456`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001afd0`

## callees

- `0x1800035a8`
- `0x180017e20`
- `0x180017e3c`
- `0x1800182ac`
- `0x18001a914`
- `0x18001b47c`
- `0x18001bf9c`
- `0x18001caa4`
- `0x18001d594`
- `0x18001deec`
- `0x18002c840`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800182e4`
- `KERNEL32!GetCurrentProcessId` at `0x1800182e4`
- `KERNEL32!CreateMutexExW` at `0x180018329`
- `KERNEL32!CreateMutexExW` at `0x180018329`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800182ac  mov     [rsp-8+arg_10], rbx
0x1800182b1  mov     [rsp-8+arg_18], rdi
0x1800182b6  push    rbp
0x1800182b7  lea     rbp, [rsp-170h]
0x1800182bf  sub     rsp, 270h
0x1800182c6  mov     rax, cs:__security_cookie
0x1800182cd  xor     rax, rsp
0x1800182d0  mov     [rbp+170h+var_10], rax
0x1800182d7  mov     rdi, rdx
0x1800182da  mov     qword ptr [rdx], 0
0x1800182e1  mov     rbx, rcx
0x1800182e4  call    cs:__imp_GetCurrentProcessId
0x1800182ea  mov     [rsp+270h+var_248], rbx
0x1800182ef  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800182f6  mov     r9d, eax
0x1800182f9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180018301  mov     edx, 104h; unsigned __int64
0x180018306  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001830b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018310  mov     r9d, 1F0001h; dwDesiredAccess
0x180018316  mov     [rsp+270h+var_240], 0
0x18001831f  xor     r8d, r8d; dwFlags
0x180018322  lea     rdx, [rsp+270h+Name]; lpName
0x180018327  xor     ecx, ecx; lpMutexAttributes
0x180018329  call    cs:__imp_CreateMutexExW
0x18001832f  mov     rdx, rax
0x180018332  lea     rcx, [rsp+270h+var_240]
0x180018337  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001833c  cmp     [rsp+270h+var_240], 0
0x180018342  jnz     short loc_180018350
0x180018344  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018349  mov     ebx, eax
0x18001834b  jmp     loc_180018401
0x180018350  lea     rdx, [rsp+270h+var_238]
0x180018355  lea     rcx, [rsp+270h+var_240]
0x18001835a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001835f  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180018364  mov     [rsp+270h+var_230], 0
0x18001836d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018372  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180018377  mov     ebx, eax
0x180018379  test    eax, eax
0x18001837b  jns     short loc_1800183DA
0x18001837d  mov     rcx, [rbp+178h]; this
0x180018384  lea     r8, aWil; "wil"
0x18001838b  mov     r9d, eax; char *
0x18001838e  mov     edx, 66h ; 'f'; void *
0x180018393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018398  mov     rcx, [rbp+178h]; this
0x18001839f  lea     r8, aWil; "wil"
0x1800183a6  mov     r9d, ebx; char *
0x1800183a9  mov     edx, 6Fh ; 'o'; void *
0x1800183ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800183b3  mov     r9d, ebx; char *
0x1800183b6  mov     edx, 12Eh; void *
0x1800183bb  mov     rcx, [rbp+178h]; this
0x1800183c2  lea     r8, aWil; "wil"
0x1800183c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800183ce  lea     rcx, [rsp+270h+var_238]
0x1800183d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800183d8  jmp     short loc_180018401
0x1800183da  mov     rax, [rsp+270h+var_230]
0x1800183df  lea     rcx, ds:0[rax*4]
0x1800183e7  test    rcx, rcx
0x1800183ea  jz      short loc_180018431
0x1800183ec  mov     [rdi], rcx
0x1800183ef  mov     eax, [rcx]
0x1800183f1  inc     eax
0x1800183f3  mov     [rcx], eax
0x1800183f5  lea     rcx, [rsp+270h+var_238]
0x1800183fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800183ff  xor     ebx, ebx
0x180018401  lea     rcx, [rsp+270h+var_240]
0x180018406  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001840b  mov     eax, ebx
0x18001840d  mov     rcx, [rbp+170h+var_10]
0x180018414  xor     rcx, rsp; StackCookie
0x180018417  call    __security_check_cookie
0x18001841c  lea     r11, [rsp+270h+var_s0]
0x180018424  mov     rbx, [r11+20h]
0x180018428  mov     rdi, [r11+28h]
0x18001842c  mov     rsp, r11
0x18001842f  pop     rbp
0x180018430  retn
0x180018431  mov     r8, rdi
0x180018434  lea     rdx, [rsp+270h+var_240]
0x180018439  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001843e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018443  mov     ebx, eax
0x180018445  test    eax, eax
0x180018447  jns     short loc_1800183F5
0x180018449  mov     r9d, eax
0x18001844c  mov     edx, 137h
0x180018451  jmp     loc_1800183BB
```
