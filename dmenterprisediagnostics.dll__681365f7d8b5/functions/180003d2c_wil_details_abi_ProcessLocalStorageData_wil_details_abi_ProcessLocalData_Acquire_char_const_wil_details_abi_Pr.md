# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d2c`
- end: `0x180003ee3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004cc4`

## callees

- `0x180001800`
- `0x180003bb8`
- `0x180003bd8`
- `0x180003d2c`
- `0x180004a10`
- `0x18000548c`
- `0x180005c14`
- `0x180006cb0`
- `0x180007118`
- `0x180007514`
- `0x1800076e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003daf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d64`

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
0x180003d2c  mov     [rsp-8+arg_10], rbx
0x180003d31  mov     [rsp-8+arg_18], rdi
0x180003d36  push    rbp
0x180003d37  lea     rbp, [rsp-170h]
0x180003d3f  sub     rsp, 270h
0x180003d46  mov     rax, cs:__security_cookie
0x180003d4d  xor     rax, rsp
0x180003d50  mov     [rbp+170h+var_10], rax
0x180003d57  mov     rdi, rdx
0x180003d5a  mov     qword ptr [rdx], 0
0x180003d61  mov     rbx, rcx
0x180003d64  call    cs:__imp_GetCurrentProcessId
0x180003d6b  nop     dword ptr [rax+rax+00h]
0x180003d70  mov     [rsp+270h+var_248], rbx
0x180003d75  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d7c  mov     r9d, eax
0x180003d7f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003d87  mov     edx, 104h; unsigned __int64
0x180003d8c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003d91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d96  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d9c  mov     [rsp+270h+var_240], 0
0x180003da5  xor     r8d, r8d; dwFlags
0x180003da8  lea     rdx, [rsp+270h+Name]; lpName
0x180003dad  xor     ecx, ecx; lpMutexAttributes
0x180003daf  call    cs:__imp_CreateMutexExW
0x180003db6  nop     dword ptr [rax+rax+00h]
0x180003dbb  mov     rdx, rax
0x180003dbe  lea     rcx, [rsp+270h+var_240]
0x180003dc3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003dc8  cmp     [rsp+270h+var_240], 0
0x180003dce  jnz     short loc_180003DDC
0x180003dd0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003dd5  mov     ebx, eax
0x180003dd7  jmp     loc_180003E8D
0x180003ddc  lea     rdx, [rsp+270h+var_238]
0x180003de1  lea     rcx, [rsp+270h+var_240]
0x180003de6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003deb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003df0  mov     [rsp+270h+var_230], 0
0x180003df9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003dfe  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003e03  mov     ebx, eax
0x180003e05  test    eax, eax
0x180003e07  jns     short loc_180003E66
0x180003e09  mov     rcx, [rbp+178h]; this
0x180003e10  lea     r8, aWil; "wil"
0x180003e17  mov     r9d, eax; char *
0x180003e1a  mov     edx, 66h ; 'f'; void *
0x180003e1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e24  mov     rcx, [rbp+178h]; this
0x180003e2b  lea     r8, aWil; "wil"
0x180003e32  mov     r9d, ebx; char *
0x180003e35  mov     edx, 6Fh ; 'o'; void *
0x180003e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e3f  mov     r9d, ebx; char *
0x180003e42  mov     edx, 12Eh; void *
0x180003e47  mov     rcx, [rbp+178h]; this
0x180003e4e  lea     r8, aWil; "wil"
0x180003e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e5a  lea     rcx, [rsp+270h+var_238]
0x180003e5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e64  jmp     short loc_180003E8D
0x180003e66  mov     rax, [rsp+270h+var_230]
0x180003e6b  lea     rcx, ds:0[rax*4]
0x180003e73  test    rcx, rcx
0x180003e76  jz      short loc_180003EBE
0x180003e78  mov     [rdi], rcx
0x180003e7b  mov     eax, [rcx]
0x180003e7d  inc     eax
0x180003e7f  mov     [rcx], eax
0x180003e81  lea     rcx, [rsp+270h+var_238]
0x180003e86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e8b  xor     ebx, ebx
0x180003e8d  lea     rcx, [rsp+270h+var_240]
0x180003e92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e97  mov     eax, ebx
0x180003e99  mov     rcx, [rbp+170h+var_10]
0x180003ea0  xor     rcx, rsp; StackCookie
0x180003ea3  call    __security_check_cookie
0x180003ea8  lea     r11, [rsp+270h+var_s0]
0x180003eb0  mov     rbx, [r11+20h]
0x180003eb4  mov     rdi, [r11+28h]
0x180003eb8  mov     rsp, r11
0x180003ebb  pop     rbp
0x180003ebc  retn
0x180003ebe  mov     r8, rdi
0x180003ec1  lea     rdx, [rsp+270h+var_240]
0x180003ec6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003ecb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003ed0  mov     ebx, eax
0x180003ed2  test    eax, eax
0x180003ed4  jns     short loc_180003E81
0x180003ed6  mov     r9d, eax
0x180003ed9  mov     edx, 137h
0x180003ede  jmp     loc_180003E47
```
