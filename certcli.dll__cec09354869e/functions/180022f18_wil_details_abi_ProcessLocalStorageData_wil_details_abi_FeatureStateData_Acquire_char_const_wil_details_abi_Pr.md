# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180022f18`
- end: `0x180023093`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800238a0`

## callees

- `0x18000ba10`
- `0x180022918`
- `0x180022934`
- `0x180022f18`
- `0x180023754`
- `0x1800242c8`
- `0x180025254`
- `0x1800258a4`
- `0x180026554`
- `0x180027018`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022f95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022f95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022f50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022f50`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v13, (const char *)(unsigned int)v12, 304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v9, (const char *)(unsigned int)Pointer, 304);
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
0x180022f18  mov     [rsp-8+arg_10], rbx
0x180022f1d  mov     [rsp-8+arg_18], rdi
0x180022f22  push    rbp
0x180022f23  lea     rbp, [rsp-170h]
0x180022f2b  sub     rsp, 270h
0x180022f32  mov     rax, cs:__security_cookie
0x180022f39  xor     rax, rsp
0x180022f3c  mov     [rbp+170h+var_10], rax
0x180022f43  mov     rdi, rdx
0x180022f46  mov     rbx, rcx
0x180022f49  mov     qword ptr [rdx], 0
0x180022f50  call    cs:__imp_GetCurrentProcessId
0x180022f56  mov     r9d, eax
0x180022f59  mov     [rsp+270h+var_248], rbx
0x180022f5e  mov     [rsp+270h+var_250], 130h; int
0x180022f66  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022f6d  mov     edx, 104h; unsigned __int64
0x180022f72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022f77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022f7c  mov     [rsp+270h+var_240], 0
0x180022f85  mov     r9d, 1F0001h; dwDesiredAccess
0x180022f8b  xor     r8d, r8d; dwFlags
0x180022f8e  lea     rdx, [rsp+270h+Name]; lpName
0x180022f93  xor     ecx, ecx; lpMutexAttributes
0x180022f95  call    cs:__imp_CreateMutexExW
0x180022f9b  mov     rdx, rax
0x180022f9e  lea     rcx, [rsp+270h+var_240]
0x180022fa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022fa8  cmp     [rsp+270h+var_240], 0
0x180022fae  jnz     short loc_180022FB9
0x180022fb0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022fb5  mov     ebx, eax
0x180022fb7  jmp     short loc_180023029
0x180022fb9  lea     rdx, [rsp+270h+var_238]
0x180022fbe  lea     rcx, [rsp+270h+var_240]
0x180022fc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180022fc8  nop
0x180022fc9  mov     [rsp+270h+var_230], 0
0x180022fd2  lea     rdx, [rsp+270h+var_230]; void **
0x180022fd7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022fdc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180022fe1  mov     ebx, eax
0x180022fe3  test    eax, eax
0x180022fe5  jns     short loc_180023009
0x180022fe7  mov     rcx, [rbp+178h]; this
0x180022fee  mov     r9d, eax; char *
0x180022ff1  mov     edx, 12Eh; void *
0x180022ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ffb  nop
0x180022ffc  lea     rcx, [rsp+270h+var_238]
0x180023001  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023006  nop
0x180023007  jmp     short loc_180023029
0x180023009  mov     rcx, [rsp+270h+var_230]
0x18002300e  test    rcx, rcx
0x180023011  jz      short loc_180023059
0x180023013  mov     [rdi], rcx
0x180023016  mov     eax, [rcx]
0x180023018  inc     eax
0x18002301a  mov     [rcx], eax
0x18002301c  lea     rcx, [rsp+270h+var_238]
0x180023021  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023026  nop
0x180023027  xor     ebx, ebx
0x180023029  lea     rcx, [rsp+270h+var_240]
0x18002302e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023033  mov     eax, ebx
0x180023035  mov     rcx, [rbp+170h+var_10]
0x18002303c  xor     rcx, rsp; StackCookie
0x18002303f  call    __security_check_cookie
0x180023044  lea     r11, [rsp+270h+var_s0]
0x18002304c  mov     rbx, [r11+20h]
0x180023050  mov     rdi, [r11+28h]
0x180023054  mov     rsp, r11
0x180023057  pop     rbp
0x180023058  retn
0x180023059  mov     r8, rdi
0x18002305c  lea     rdx, [rsp+270h+var_240]
0x180023061  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023066  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002306b  mov     ebx, eax
0x18002306d  test    eax, eax
0x18002306f  jns     short loc_18002301C
0x180023071  mov     rcx, [rbp+178h]; this
0x180023078  mov     r9d, eax; char *
0x18002307b  mov     edx, 137h; void *
0x180023080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023085  nop
0x180023086  lea     rcx, [rsp+270h+var_238]
0x18002308b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023090  nop
0x180023091  jmp     short loc_180023029
```
