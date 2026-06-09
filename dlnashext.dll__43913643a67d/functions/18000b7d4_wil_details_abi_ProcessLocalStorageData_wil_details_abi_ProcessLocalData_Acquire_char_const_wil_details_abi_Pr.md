# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b7d4`
- end: `0x18000b97d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180031bb4`

## callees

- `0x180009eb0`
- `0x18000b7d4`
- `0x18000b984`
- `0x18000bba8`
- `0x18000bbc4`
- `0x18000bc18`
- `0x18000bde0`
- `0x18000c548`
- `0x180011930`
- `0x180012722`
- `0x1800314c0`
- `0x1800328a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b850`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b850`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId_0; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  __int64 v7; // rdx
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
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId_0);
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
0x18000b7d4  mov     [rsp-8+arg_10], rbx
0x18000b7d9  mov     [rsp-8+arg_18], rdi
0x18000b7de  push    rbp
0x18000b7df  lea     rbp, [rsp-170h]
0x18000b7e7  sub     rsp, 270h
0x18000b7ee  mov     rax, cs:__security_cookie
0x18000b7f5  xor     rax, rsp
0x18000b7f8  mov     [rbp+170h+var_10], rax
0x18000b7ff  mov     rdi, rdx
0x18000b802  mov     qword ptr [rdx], 0
0x18000b809  mov     rbx, rcx
0x18000b80c  call    GetCurrentProcessId_0
0x18000b811  mov     r9d, eax
0x18000b814  mov     [rsp+270h+var_248], rbx
0x18000b819  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b820  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000b828  mov     edx, 104h; unsigned __int64
0x18000b82d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b832  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b837  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b83d  mov     [rsp+270h+var_240], 0
0x18000b846  xor     r8d, r8d; dwFlags
0x18000b849  lea     rdx, [rsp+270h+Name]; lpName
0x18000b84e  xor     ecx, ecx; lpMutexAttributes
0x18000b850  call    cs:__imp_CreateMutexExW
0x18000b856  mov     rdx, rax
0x18000b859  lea     rcx, [rsp+270h+var_240]
0x18000b85e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b863  cmp     [rsp+270h+var_240], 0
0x18000b869  jnz     short loc_18000B877
0x18000b86b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b870  mov     ebx, eax
0x18000b872  jmp     loc_18000B928
0x18000b877  lea     rdx, [rsp+270h+var_238]
0x18000b87c  lea     rcx, [rsp+270h+var_240]
0x18000b881  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b886  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000b88b  mov     [rsp+270h+var_230], 0
0x18000b894  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b899  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b89e  mov     ebx, eax
0x18000b8a0  test    eax, eax
0x18000b8a2  jns     short loc_18000B901
0x18000b8a4  mov     rcx, [rbp+178h]; this
0x18000b8ab  lea     r8, aWil; "wil"
0x18000b8b2  mov     r9d, eax; char *
0x18000b8b5  mov     edx, 66h ; 'f'; void *
0x18000b8ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8bf  mov     rcx, [rbp+178h]; this
0x18000b8c6  lea     r8, aWil; "wil"
0x18000b8cd  mov     r9d, ebx; char *
0x18000b8d0  mov     edx, 6Fh ; 'o'; void *
0x18000b8d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8da  mov     r9d, ebx; char *
0x18000b8dd  mov     edx, 12Eh; void *
0x18000b8e2  mov     rcx, [rbp+178h]; this
0x18000b8e9  lea     r8, aWil; "wil"
0x18000b8f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8f5  lea     rcx, [rsp+270h+var_238]
0x18000b8fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b8ff  jmp     short loc_18000B928
0x18000b901  mov     rax, [rsp+270h+var_230]
0x18000b906  lea     rcx, ds:0[rax*4]
0x18000b90e  test    rcx, rcx
0x18000b911  jz      short loc_18000B958
0x18000b913  mov     [rdi], rcx
0x18000b916  mov     eax, [rcx]
0x18000b918  inc     eax
0x18000b91a  mov     [rcx], eax
0x18000b91c  lea     rcx, [rsp+270h+var_238]
0x18000b921  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b926  xor     ebx, ebx
0x18000b928  lea     rcx, [rsp+270h+var_240]
0x18000b92d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b932  mov     eax, ebx
0x18000b934  mov     rcx, [rbp+170h+var_10]
0x18000b93b  xor     rcx, rsp; StackCookie
0x18000b93e  call    __security_check_cookie
0x18000b943  lea     r11, [rsp+270h+var_s0]
0x18000b94b  mov     rbx, [r11+20h]
0x18000b94f  mov     rdi, [r11+28h]
0x18000b953  mov     rsp, r11
0x18000b956  pop     rbp
0x18000b957  retn
0x18000b958  mov     r8, rdi
0x18000b95b  lea     rdx, [rsp+270h+var_240]
0x18000b960  lea     rcx, [rsp+270h+Name]
0x18000b965  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b96a  mov     ebx, eax
0x18000b96c  test    eax, eax
0x18000b96e  jns     short loc_18000B91C
0x18000b970  mov     r9d, eax
0x18000b973  mov     edx, 137h
0x18000b978  jmp     loc_18000B8E2
```
