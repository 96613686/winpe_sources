# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180022d94`
- end: `0x180022f0f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180023840`

## callees

- `0x18000ba10`
- `0x180022918`
- `0x180022934`
- `0x180022d94`
- `0x180023754`
- `0x180024130`
- `0x180025254`
- `0x1800258a4`
- `0x180026554`
- `0x180027018`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022e11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022dcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022dcc`

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
  unsigned int v9; // r8d
  _DWORD *v10; // rcx
  int v12; // eax
  unsigned int v13; // r8d
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v14 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    Mutex);
  if ( v14 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v14,
      v15);
    v16 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v16);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v10 = v16;
      if ( v16 )
      {
        *a2 = v16;
        ++*v10;
      }
      else
      {
        v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v13, (const char *)(unsigned int)v12, 120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v14,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180022d94  mov     [rsp-8+arg_10], rbx
0x180022d99  mov     [rsp-8+arg_18], rdi
0x180022d9e  push    rbp
0x180022d9f  lea     rbp, [rsp-170h]
0x180022da7  sub     rsp, 270h
0x180022dae  mov     rax, cs:__security_cookie
0x180022db5  xor     rax, rsp
0x180022db8  mov     [rbp+170h+var_10], rax
0x180022dbf  mov     rdi, rdx
0x180022dc2  mov     rbx, rcx
0x180022dc5  mov     qword ptr [rdx], 0
0x180022dcc  call    cs:__imp_GetCurrentProcessId
0x180022dd2  mov     r9d, eax
0x180022dd5  mov     [rsp+270h+var_248], rbx
0x180022dda  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180022de2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022de9  mov     edx, 104h; unsigned __int64
0x180022dee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022df3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022df8  mov     [rsp+270h+var_240], 0
0x180022e01  mov     r9d, 1F0001h; dwDesiredAccess
0x180022e07  xor     r8d, r8d; dwFlags
0x180022e0a  lea     rdx, [rsp+270h+Name]; lpName
0x180022e0f  xor     ecx, ecx; lpMutexAttributes
0x180022e11  call    cs:__imp_CreateMutexExW
0x180022e17  mov     rdx, rax
0x180022e1a  lea     rcx, [rsp+270h+var_240]
0x180022e1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022e24  cmp     [rsp+270h+var_240], 0
0x180022e2a  jnz     short loc_180022E35
0x180022e2c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022e31  mov     ebx, eax
0x180022e33  jmp     short loc_180022EA5
0x180022e35  lea     rdx, [rsp+270h+var_238]
0x180022e3a  lea     rcx, [rsp+270h+var_240]
0x180022e3f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180022e44  nop
0x180022e45  mov     [rsp+270h+var_230], 0
0x180022e4e  lea     rdx, [rsp+270h+var_230]; void **
0x180022e53  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022e58  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180022e5d  mov     ebx, eax
0x180022e5f  test    eax, eax
0x180022e61  jns     short loc_180022E85
0x180022e63  mov     rcx, [rbp+178h]; this
0x180022e6a  mov     r9d, eax; char *
0x180022e6d  mov     edx, 12Eh; void *
0x180022e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e77  nop
0x180022e78  lea     rcx, [rsp+270h+var_238]
0x180022e7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022e82  nop
0x180022e83  jmp     short loc_180022EA5
0x180022e85  mov     rcx, [rsp+270h+var_230]
0x180022e8a  test    rcx, rcx
0x180022e8d  jz      short loc_180022ED5
0x180022e8f  mov     [rdi], rcx
0x180022e92  mov     eax, [rcx]
0x180022e94  inc     eax
0x180022e96  mov     [rcx], eax
0x180022e98  lea     rcx, [rsp+270h+var_238]
0x180022e9d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022ea2  nop
0x180022ea3  xor     ebx, ebx
0x180022ea5  lea     rcx, [rsp+270h+var_240]
0x180022eaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022eaf  mov     eax, ebx
0x180022eb1  mov     rcx, [rbp+170h+var_10]
0x180022eb8  xor     rcx, rsp; StackCookie
0x180022ebb  call    __security_check_cookie
0x180022ec0  lea     r11, [rsp+270h+var_s0]
0x180022ec8  mov     rbx, [r11+20h]
0x180022ecc  mov     rdi, [r11+28h]
0x180022ed0  mov     rsp, r11
0x180022ed3  pop     rbp
0x180022ed4  retn
0x180022ed5  mov     r8, rdi
0x180022ed8  lea     rdx, [rsp+270h+var_240]
0x180022edd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022ee2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180022ee7  mov     ebx, eax
0x180022ee9  test    eax, eax
0x180022eeb  jns     short loc_180022E98
0x180022eed  mov     rcx, [rbp+178h]; this
0x180022ef4  mov     r9d, eax; char *
0x180022ef7  mov     edx, 137h; void *
0x180022efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f01  nop
0x180022f02  lea     rcx, [rsp+270h+var_238]
0x180022f07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022f0c  nop
0x180022f0d  jmp     short loc_180022EA5
```
