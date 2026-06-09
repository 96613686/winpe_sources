# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800115c4`
- end: `0x180011723`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012680`

## callees

- `0x180007660`
- `0x18000ee58`
- `0x18000f970`
- `0x18001119c`
- `0x1800111b8`
- `0x1800115c4`
- `0x18001407c`
- `0x180015fd0`
- `0x180016968`
- `0x1800174f0`
- `0x18001764c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800115fc`
- `KERNEL32!GetCurrentProcessId` at `0x1800115fc`
- `KERNEL32!CreateMutexExW` at `0x180011641`
- `KERNEL32!CreateMutexExW` at `0x180011641`

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
0x1800115c4  mov     [rsp-8+arg_10], rbx
0x1800115c9  mov     [rsp-8+arg_18], rdi
0x1800115ce  push    rbp
0x1800115cf  lea     rbp, [rsp-170h]
0x1800115d7  sub     rsp, 270h
0x1800115de  mov     rax, cs:__security_cookie
0x1800115e5  xor     rax, rsp
0x1800115e8  mov     [rbp+170h+var_10], rax
0x1800115ef  mov     rdi, rdx
0x1800115f2  mov     qword ptr [rdx], 0
0x1800115f9  mov     rbx, rcx
0x1800115fc  call    cs:__imp_GetCurrentProcessId
0x180011602  mov     [rsp+270h+var_248], rbx
0x180011607  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001160e  mov     r9d, eax
0x180011611  mov     [rsp+270h+var_250], 130h; int
0x180011619  mov     edx, 104h; unsigned __int64
0x18001161e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011623  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011628  mov     r9d, 1F0001h; dwDesiredAccess
0x18001162e  mov     [rsp+270h+var_240], 0
0x180011637  xor     r8d, r8d; dwFlags
0x18001163a  lea     rdx, [rsp+270h+Name]; lpName
0x18001163f  xor     ecx, ecx; lpMutexAttributes
0x180011641  call    cs:__imp_CreateMutexExW
0x180011647  mov     rdx, rax
0x18001164a  lea     rcx, [rsp+270h+var_240]
0x18001164f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011654  cmp     [rsp+270h+var_240], 0
0x18001165a  jnz     short loc_180011665
0x18001165c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011661  mov     ebx, eax
0x180011663  jmp     short loc_1800116D1
0x180011665  lea     rdx, [rsp+270h+var_238]
0x18001166a  lea     rcx, [rsp+270h+var_240]
0x18001166f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180011674  lea     rdx, [rsp+270h+var_230]; void **
0x180011679  mov     [rsp+270h+var_230], 0
0x180011682  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011687  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001168c  mov     ebx, eax
0x18001168e  test    eax, eax
0x180011690  jns     short loc_1800116B2
0x180011692  mov     edx, 12Eh; void *
0x180011697  mov     rcx, [rbp+178h]; this
0x18001169e  mov     r9d, eax; char *
0x1800116a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116a6  lea     rcx, [rsp+270h+var_238]
0x1800116ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800116b0  jmp     short loc_1800116D1
0x1800116b2  mov     rcx, [rsp+270h+var_230]
0x1800116b7  test    rcx, rcx
0x1800116ba  jz      short loc_180011701
0x1800116bc  mov     [rdi], rcx
0x1800116bf  mov     eax, [rcx]
0x1800116c1  inc     eax
0x1800116c3  mov     [rcx], eax
0x1800116c5  lea     rcx, [rsp+270h+var_238]
0x1800116ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800116cf  xor     ebx, ebx
0x1800116d1  lea     rcx, [rsp+270h+var_240]
0x1800116d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800116db  mov     eax, ebx
0x1800116dd  mov     rcx, [rbp+170h+var_10]
0x1800116e4  xor     rcx, rsp; StackCookie
0x1800116e7  call    __security_check_cookie
0x1800116ec  lea     r11, [rsp+270h+var_s0]
0x1800116f4  mov     rbx, [r11+20h]
0x1800116f8  mov     rdi, [r11+28h]
0x1800116fc  mov     rsp, r11
0x1800116ff  pop     rbp
0x180011700  retn
0x180011701  mov     r8, rdi
0x180011704  lea     rdx, [rsp+270h+var_240]
0x180011709  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001170e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180011713  mov     ebx, eax
0x180011715  test    eax, eax
0x180011717  jns     short loc_1800116C5
0x180011719  mov     edx, 137h
0x18001171e  jmp     loc_180011697
```
