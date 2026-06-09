# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004d28`
- end: `0x180004ed2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005cf4`

## callees

- `0x180001a50`
- `0x1800044e0`
- `0x1800044fc`
- `0x180004d28`
- `0x1800059c8`
- `0x1800065a0`
- `0x180006d14`
- `0x1800075dc`
- `0x1800078c8`
- `0x18000804c`
- `0x1800081a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004da5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004da5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d60`

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
0x180004d28  mov     [rsp-8+arg_10], rbx
0x180004d2d  mov     [rsp-8+arg_18], rdi
0x180004d32  push    rbp
0x180004d33  lea     rbp, [rsp-170h]
0x180004d3b  sub     rsp, 270h
0x180004d42  mov     rax, cs:__security_cookie
0x180004d49  xor     rax, rsp
0x180004d4c  mov     [rbp+170h+var_10], rax
0x180004d53  mov     rdi, rdx
0x180004d56  mov     qword ptr [rdx], 0
0x180004d5d  mov     rbx, rcx
0x180004d60  call    cs:__imp_GetCurrentProcessId
0x180004d66  mov     [rsp+270h+var_248], rbx
0x180004d6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d72  mov     r9d, eax
0x180004d75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004d7d  mov     edx, 104h; unsigned __int64
0x180004d82  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d8c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d92  mov     [rsp+270h+var_240], 0
0x180004d9b  xor     r8d, r8d; dwFlags
0x180004d9e  lea     rdx, [rsp+270h+Name]; lpName
0x180004da3  xor     ecx, ecx; lpMutexAttributes
0x180004da5  call    cs:__imp_CreateMutexExW
0x180004dab  mov     rdx, rax
0x180004dae  lea     rcx, [rsp+270h+var_240]
0x180004db3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004db8  cmp     [rsp+270h+var_240], 0
0x180004dbe  jnz     short loc_180004DCC
0x180004dc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004dc5  mov     ebx, eax
0x180004dc7  jmp     loc_180004E7D
0x180004dcc  lea     rdx, [rsp+270h+var_238]
0x180004dd1  lea     rcx, [rsp+270h+var_240]
0x180004dd6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004ddb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004de0  mov     [rsp+270h+var_230], 0
0x180004de9  lea     rcx, [rsp+270h+Name]; pszSrc
0x180004dee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004df3  mov     ebx, eax
0x180004df5  test    eax, eax
0x180004df7  jns     short loc_180004E56
0x180004df9  mov     rcx, [rbp+178h]; this
0x180004e00  lea     r8, aWil; "wil"
0x180004e07  mov     r9d, eax; char *
0x180004e0a  mov     edx, 66h ; 'f'; void *
0x180004e0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e14  mov     rcx, [rbp+178h]; this
0x180004e1b  lea     r8, aWil; "wil"
0x180004e22  mov     r9d, ebx; char *
0x180004e25  mov     edx, 6Fh ; 'o'; void *
0x180004e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e2f  mov     r9d, ebx; char *
0x180004e32  mov     edx, 12Eh; void *
0x180004e37  mov     rcx, [rbp+178h]; this
0x180004e3e  lea     r8, aWil; "wil"
0x180004e45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e4a  lea     rcx, [rsp+270h+var_238]
0x180004e4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e54  jmp     short loc_180004E7D
0x180004e56  mov     rax, [rsp+270h+var_230]
0x180004e5b  lea     rcx, ds:0[rax*4]
0x180004e63  test    rcx, rcx
0x180004e66  jz      short loc_180004EAD
0x180004e68  mov     [rdi], rcx
0x180004e6b  mov     eax, [rcx]
0x180004e6d  inc     eax
0x180004e6f  mov     [rcx], eax
0x180004e71  lea     rcx, [rsp+270h+var_238]
0x180004e76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e7b  xor     ebx, ebx
0x180004e7d  lea     rcx, [rsp+270h+var_240]
0x180004e82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004e87  mov     eax, ebx
0x180004e89  mov     rcx, [rbp+170h+var_10]
0x180004e90  xor     rcx, rsp; StackCookie
0x180004e93  call    __security_check_cookie
0x180004e98  lea     r11, [rsp+270h+var_s0]
0x180004ea0  mov     rbx, [r11+20h]
0x180004ea4  mov     rdi, [r11+28h]
0x180004ea8  mov     rsp, r11
0x180004eab  pop     rbp
0x180004eac  retn
0x180004ead  mov     r8, rdi
0x180004eb0  lea     rdx, [rsp+270h+var_240]
0x180004eb5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004eba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004ebf  mov     ebx, eax
0x180004ec1  test    eax, eax
0x180004ec3  jns     short loc_180004E71
0x180004ec5  mov     r9d, eax
0x180004ec8  mov     edx, 137h
0x180004ecd  jmp     loc_180004E37
```
