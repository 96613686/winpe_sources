# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d18`
- end: `0x180003ec2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004b78`

## callees

- `0x1800017e0`
- `0x180003ba8`
- `0x180003bc4`
- `0x180003d18`
- `0x1800048d8`
- `0x1800052ec`
- `0x180005a14`
- `0x180006a30`
- `0x180006e88`
- `0x180007260`
- `0x180007410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d50`

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
0x180003d18  mov     [rsp-8+arg_10], rbx
0x180003d1d  mov     [rsp-8+arg_18], rdi
0x180003d22  push    rbp
0x180003d23  lea     rbp, [rsp-170h]
0x180003d2b  sub     rsp, 270h
0x180003d32  mov     rax, cs:__security_cookie
0x180003d39  xor     rax, rsp
0x180003d3c  mov     [rbp+170h+var_10], rax
0x180003d43  mov     rdi, rdx
0x180003d46  mov     qword ptr [rdx], 0
0x180003d4d  mov     rbx, rcx
0x180003d50  call    cs:__imp_GetCurrentProcessId
0x180003d56  mov     [rsp+270h+var_248], rbx
0x180003d5b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d62  mov     r9d, eax
0x180003d65  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003d6d  mov     edx, 104h; unsigned __int64
0x180003d72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003d77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d7c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d82  mov     [rsp+270h+var_240], 0
0x180003d8b  xor     r8d, r8d; dwFlags
0x180003d8e  lea     rdx, [rsp+270h+Name]; lpName
0x180003d93  xor     ecx, ecx; lpMutexAttributes
0x180003d95  call    cs:__imp_CreateMutexExW
0x180003d9b  mov     rdx, rax
0x180003d9e  lea     rcx, [rsp+270h+var_240]
0x180003da3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003da8  cmp     [rsp+270h+var_240], 0
0x180003dae  jnz     short loc_180003DBC
0x180003db0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003db5  mov     ebx, eax
0x180003db7  jmp     loc_180003E6D
0x180003dbc  lea     rdx, [rsp+270h+var_238]
0x180003dc1  lea     rcx, [rsp+270h+var_240]
0x180003dc6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003dcb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003dd0  mov     [rsp+270h+var_230], 0
0x180003dd9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003dde  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003de3  mov     ebx, eax
0x180003de5  test    eax, eax
0x180003de7  jns     short loc_180003E46
0x180003de9  mov     rcx, [rbp+178h]; this
0x180003df0  lea     r8, aWil; "wil"
0x180003df7  mov     r9d, eax; char *
0x180003dfa  mov     edx, 66h ; 'f'; void *
0x180003dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e04  mov     rcx, [rbp+178h]; this
0x180003e0b  lea     r8, aWil; "wil"
0x180003e12  mov     r9d, ebx; char *
0x180003e15  mov     edx, 6Fh ; 'o'; void *
0x180003e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e1f  mov     r9d, ebx; char *
0x180003e22  mov     edx, 12Eh; void *
0x180003e27  mov     rcx, [rbp+178h]; this
0x180003e2e  lea     r8, aWil; "wil"
0x180003e35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e3a  lea     rcx, [rsp+270h+var_238]
0x180003e3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e44  jmp     short loc_180003E6D
0x180003e46  mov     rax, [rsp+270h+var_230]
0x180003e4b  lea     rcx, ds:0[rax*4]
0x180003e53  test    rcx, rcx
0x180003e56  jz      short loc_180003E9D
0x180003e58  mov     [rdi], rcx
0x180003e5b  mov     eax, [rcx]
0x180003e5d  inc     eax
0x180003e5f  mov     [rcx], eax
0x180003e61  lea     rcx, [rsp+270h+var_238]
0x180003e66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e6b  xor     ebx, ebx
0x180003e6d  lea     rcx, [rsp+270h+var_240]
0x180003e72  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e77  mov     eax, ebx
0x180003e79  mov     rcx, [rbp+170h+var_10]
0x180003e80  xor     rcx, rsp; StackCookie
0x180003e83  call    __security_check_cookie
0x180003e88  lea     r11, [rsp+270h+var_s0]
0x180003e90  mov     rbx, [r11+20h]
0x180003e94  mov     rdi, [r11+28h]
0x180003e98  mov     rsp, r11
0x180003e9b  pop     rbp
0x180003e9c  retn
0x180003e9d  mov     r8, rdi
0x180003ea0  lea     rdx, [rsp+270h+var_240]
0x180003ea5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003eaa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003eaf  mov     ebx, eax
0x180003eb1  test    eax, eax
0x180003eb3  jns     short loc_180003E61
0x180003eb5  mov     r9d, eax
0x180003eb8  mov     edx, 137h
0x180003ebd  jmp     loc_180003E27
```
