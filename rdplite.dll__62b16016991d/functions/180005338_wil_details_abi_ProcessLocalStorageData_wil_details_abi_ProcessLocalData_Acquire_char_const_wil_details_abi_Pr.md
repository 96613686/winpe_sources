# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005338`
- end: `0x1800054e2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005d88`

## callees

- `0x1800036f0`
- `0x180005130`
- `0x18000514c`
- `0x180005338`
- `0x180005b88`
- `0x1800064b4`
- `0x180006a74`
- `0x180007074`
- `0x180007228`
- `0x1800075c0`
- `0x1800076bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800053b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800053b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005370`

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
0x180005338  mov     [rsp-8+arg_10], rbx
0x18000533d  mov     [rsp-8+arg_18], rdi
0x180005342  push    rbp
0x180005343  lea     rbp, [rsp-170h]
0x18000534b  sub     rsp, 270h
0x180005352  mov     rax, cs:__security_cookie
0x180005359  xor     rax, rsp
0x18000535c  mov     [rbp+170h+var_10], rax
0x180005363  mov     rdi, rdx
0x180005366  mov     qword ptr [rdx], 0
0x18000536d  mov     rbx, rcx
0x180005370  call    cs:__imp_GetCurrentProcessId
0x180005376  mov     [rsp+270h+var_248], rbx
0x18000537b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005382  mov     r9d, eax
0x180005385  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000538d  mov     edx, 104h; unsigned __int64
0x180005392  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005397  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000539c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800053a2  mov     [rsp+270h+var_240], 0
0x1800053ab  xor     r8d, r8d; dwFlags
0x1800053ae  lea     rdx, [rsp+270h+Name]; lpName
0x1800053b3  xor     ecx, ecx; lpMutexAttributes
0x1800053b5  call    cs:__imp_CreateMutexExW
0x1800053bb  mov     rdx, rax
0x1800053be  lea     rcx, [rsp+270h+var_240]
0x1800053c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800053c8  cmp     [rsp+270h+var_240], 0
0x1800053ce  jnz     short loc_1800053DC
0x1800053d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800053d5  mov     ebx, eax
0x1800053d7  jmp     loc_18000548D
0x1800053dc  lea     rdx, [rsp+270h+var_238]
0x1800053e1  lea     rcx, [rsp+270h+var_240]
0x1800053e6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800053eb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800053f0  mov     [rsp+270h+var_230], 0
0x1800053f9  lea     rcx, [rsp+270h+Name]; pszSrc
0x1800053fe  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005403  mov     ebx, eax
0x180005405  test    eax, eax
0x180005407  jns     short loc_180005466
0x180005409  mov     rcx, [rbp+178h]; this
0x180005410  lea     r8, aWil; "wil"
0x180005417  mov     r9d, eax; char *
0x18000541a  mov     edx, 66h ; 'f'; void *
0x18000541f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005424  mov     rcx, [rbp+178h]; this
0x18000542b  lea     r8, aWil; "wil"
0x180005432  mov     r9d, ebx; char *
0x180005435  mov     edx, 6Fh ; 'o'; void *
0x18000543a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000543f  mov     r9d, ebx; char *
0x180005442  mov     edx, 12Eh; void *
0x180005447  mov     rcx, [rbp+178h]; this
0x18000544e  lea     r8, aWil; "wil"
0x180005455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000545a  lea     rcx, [rsp+270h+var_238]
0x18000545f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005464  jmp     short loc_18000548D
0x180005466  mov     rax, [rsp+270h+var_230]
0x18000546b  lea     rcx, ds:0[rax*4]
0x180005473  test    rcx, rcx
0x180005476  jz      short loc_1800054BD
0x180005478  mov     [rdi], rcx
0x18000547b  mov     eax, [rcx]
0x18000547d  inc     eax
0x18000547f  mov     [rcx], eax
0x180005481  lea     rcx, [rsp+270h+var_238]
0x180005486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000548b  xor     ebx, ebx
0x18000548d  lea     rcx, [rsp+270h+var_240]
0x180005492  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005497  mov     eax, ebx
0x180005499  mov     rcx, [rbp+170h+var_10]
0x1800054a0  xor     rcx, rsp; StackCookie
0x1800054a3  call    __security_check_cookie
0x1800054a8  lea     r11, [rsp+270h+var_s0]
0x1800054b0  mov     rbx, [r11+20h]
0x1800054b4  mov     rdi, [r11+28h]
0x1800054b8  mov     rsp, r11
0x1800054bb  pop     rbp
0x1800054bc  retn
0x1800054bd  mov     r8, rdi
0x1800054c0  lea     rdx, [rsp+270h+var_240]
0x1800054c5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800054ca  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800054cf  mov     ebx, eax
0x1800054d1  test    eax, eax
0x1800054d3  jns     short loc_180005481
0x1800054d5  mov     r9d, eax
0x1800054d8  mov     edx, 137h
0x1800054dd  jmp     loc_180005447
```
