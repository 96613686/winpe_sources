# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002a688`
- end: `0x18002a81d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002c448`

## callees

- `0x180001e80`
- `0x18001b6c0`
- `0x18002a364`
- `0x18002a380`
- `0x18002a688`
- `0x18002bfa0`
- `0x18002d158`
- `0x18002e494`
- `0x18002ef58`
- `0x18002f738`
- `0x18002f83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a705`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a6c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a6c0`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18002a688  mov     [rsp-8+arg_10], rbx
0x18002a68d  mov     [rsp-8+arg_18], rdi
0x18002a692  push    rbp
0x18002a693  lea     rbp, [rsp-170h]
0x18002a69b  sub     rsp, 270h
0x18002a6a2  mov     rax, cs:__security_cookie
0x18002a6a9  xor     rax, rsp
0x18002a6ac  mov     [rbp+170h+var_10], rax
0x18002a6b3  mov     rdi, rdx
0x18002a6b6  mov     qword ptr [rdx], 0
0x18002a6bd  mov     rbx, rcx
0x18002a6c0  call    cs:__imp_GetCurrentProcessId
0x18002a6c6  mov     [rsp+270h+var_248], rbx
0x18002a6cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002a6d2  mov     r9d, eax
0x18002a6d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002a6dd  mov     edx, 104h; unsigned __int64
0x18002a6e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a6e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a6ec  mov     r9d, 1F0001h; dwDesiredAccess
0x18002a6f2  mov     [rsp+270h+var_240], 0
0x18002a6fb  xor     r8d, r8d; dwFlags
0x18002a6fe  lea     rdx, [rsp+270h+Name]; lpName
0x18002a703  xor     ecx, ecx; lpMutexAttributes
0x18002a705  call    cs:__imp_CreateMutexExW
0x18002a70b  mov     rdx, rax
0x18002a70e  lea     rcx, [rsp+270h+var_240]
0x18002a713  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002a718  cmp     [rsp+270h+var_240], 0
0x18002a71e  jnz     short loc_18002A72C
0x18002a720  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a725  mov     ebx, eax
0x18002a727  jmp     loc_18002A7C8
0x18002a72c  lea     rdx, [rsp+270h+var_238]
0x18002a731  lea     rcx, [rsp+270h+var_240]
0x18002a736  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002a73b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18002a740  mov     [rsp+270h+var_230], 0
0x18002a749  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a74e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002a753  mov     ebx, eax
0x18002a755  test    eax, eax
0x18002a757  jns     short loc_18002A7A1
0x18002a759  mov     rcx, [rbp+178h]; this
0x18002a760  mov     r9d, eax; char *
0x18002a763  mov     edx, 66h ; 'f'; void *
0x18002a768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a76d  mov     rcx, [rbp+178h]; this
0x18002a774  mov     r9d, ebx; char *
0x18002a777  mov     edx, 6Fh ; 'o'; void *
0x18002a77c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a781  mov     r9d, ebx; char *
0x18002a784  mov     edx, 12Eh; void *
0x18002a789  mov     rcx, [rbp+178h]; this
0x18002a790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a795  lea     rcx, [rsp+270h+var_238]
0x18002a79a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a79f  jmp     short loc_18002A7C8
0x18002a7a1  mov     rax, [rsp+270h+var_230]
0x18002a7a6  lea     rcx, ds:0[rax*4]
0x18002a7ae  test    rcx, rcx
0x18002a7b1  jz      short loc_18002A7F8
0x18002a7b3  mov     [rdi], rcx
0x18002a7b6  mov     eax, [rcx]
0x18002a7b8  inc     eax
0x18002a7ba  mov     [rcx], eax
0x18002a7bc  lea     rcx, [rsp+270h+var_238]
0x18002a7c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a7c6  xor     ebx, ebx
0x18002a7c8  lea     rcx, [rsp+270h+var_240]
0x18002a7cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a7d2  mov     eax, ebx
0x18002a7d4  mov     rcx, [rbp+170h+var_10]
0x18002a7db  xor     rcx, rsp; StackCookie
0x18002a7de  call    __security_check_cookie
0x18002a7e3  lea     r11, [rsp+270h+var_s0]
0x18002a7eb  mov     rbx, [r11+20h]
0x18002a7ef  mov     rdi, [r11+28h]
0x18002a7f3  mov     rsp, r11
0x18002a7f6  pop     rbp
0x18002a7f7  retn
0x18002a7f8  mov     r8, rdi
0x18002a7fb  lea     rdx, [rsp+270h+var_240]
0x18002a800  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a805  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002a80a  mov     ebx, eax
0x18002a80c  test    eax, eax
0x18002a80e  jns     short loc_18002A7BC
0x18002a810  mov     r9d, eax
0x18002a813  mov     edx, 137h
0x18002a818  jmp     loc_18002A789
```
