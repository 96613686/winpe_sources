# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800048cc`
- end: `0x180004a6e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005834`

## callees

- `0x180002400`
- `0x1800046bc`
- `0x1800046dc`
- `0x1800048cc`
- `0x1800055e0`
- `0x180006098`
- `0x180006834`
- `0x180006eb4`
- `0x180007198`
- `0x1800074c4`
- `0x1800075c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000494f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000494f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004904`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004904`

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
0x1800048cc  mov     [rsp-8+arg_10], rbx
0x1800048d1  mov     [rsp-8+arg_18], rdi
0x1800048d6  push    rbp
0x1800048d7  lea     rbp, [rsp-170h]
0x1800048df  sub     rsp, 270h
0x1800048e6  mov     rax, cs:__security_cookie
0x1800048ed  xor     rax, rsp
0x1800048f0  mov     [rbp+170h+var_10], rax
0x1800048f7  mov     rdi, rdx
0x1800048fa  mov     qword ptr [rdx], 0
0x180004901  mov     rbx, rcx
0x180004904  call    cs:__imp_GetCurrentProcessId
0x18000490b  nop     dword ptr [rax+rax+00h]
0x180004910  mov     [rsp+270h+var_248], rbx
0x180004915  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000491c  mov     r9d, eax
0x18000491f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004927  mov     edx, 104h; unsigned __int64
0x18000492c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004931  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004936  mov     r9d, 1F0001h; dwDesiredAccess
0x18000493c  mov     [rsp+270h+var_240], 0
0x180004945  xor     r8d, r8d; dwFlags
0x180004948  lea     rdx, [rsp+270h+Name]; lpName
0x18000494d  xor     ecx, ecx; lpMutexAttributes
0x18000494f  call    cs:__imp_CreateMutexExW
0x180004956  nop     dword ptr [rax+rax+00h]
0x18000495b  mov     rdx, rax
0x18000495e  lea     rcx, [rsp+270h+var_240]
0x180004963  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004968  cmp     [rsp+270h+var_240], 0
0x18000496e  jnz     short loc_18000497C
0x180004970  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004975  mov     ebx, eax
0x180004977  jmp     loc_180004A18
0x18000497c  lea     rdx, [rsp+270h+var_238]
0x180004981  lea     rcx, [rsp+270h+var_240]
0x180004986  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000498b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004990  mov     [rsp+270h+var_230], 0
0x180004999  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000499e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800049a3  mov     ebx, eax
0x1800049a5  test    eax, eax
0x1800049a7  jns     short loc_1800049F1
0x1800049a9  mov     rcx, [rbp+178h]; this
0x1800049b0  mov     r9d, eax; char *
0x1800049b3  mov     edx, 66h ; 'f'; void *
0x1800049b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049bd  mov     rcx, [rbp+178h]; this
0x1800049c4  mov     r9d, ebx; char *
0x1800049c7  mov     edx, 6Fh ; 'o'; void *
0x1800049cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049d1  mov     r9d, ebx; char *
0x1800049d4  mov     edx, 12Eh; void *
0x1800049d9  mov     rcx, [rbp+178h]; this
0x1800049e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049e5  lea     rcx, [rsp+270h+var_238]
0x1800049ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800049ef  jmp     short loc_180004A18
0x1800049f1  mov     rax, [rsp+270h+var_230]
0x1800049f6  lea     rcx, ds:0[rax*4]
0x1800049fe  test    rcx, rcx
0x180004a01  jz      short loc_180004A49
0x180004a03  mov     [rdi], rcx
0x180004a06  mov     eax, [rcx]
0x180004a08  inc     eax
0x180004a0a  mov     [rcx], eax
0x180004a0c  lea     rcx, [rsp+270h+var_238]
0x180004a11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004a16  xor     ebx, ebx
0x180004a18  lea     rcx, [rsp+270h+var_240]
0x180004a1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004a22  mov     eax, ebx
0x180004a24  mov     rcx, [rbp+170h+var_10]
0x180004a2b  xor     rcx, rsp; StackCookie
0x180004a2e  call    __security_check_cookie
0x180004a33  lea     r11, [rsp+270h+var_s0]
0x180004a3b  mov     rbx, [r11+20h]
0x180004a3f  mov     rdi, [r11+28h]
0x180004a43  mov     rsp, r11
0x180004a46  pop     rbp
0x180004a47  retn
0x180004a49  mov     r8, rdi
0x180004a4c  lea     rdx, [rsp+270h+var_240]
0x180004a51  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004a56  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004a5b  mov     ebx, eax
0x180004a5d  test    eax, eax
0x180004a5f  jns     short loc_180004A0C
0x180004a61  mov     r9d, eax
0x180004a64  mov     edx, 137h
0x180004a69  jmp     loc_1800049D9
```
