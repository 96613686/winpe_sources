# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800048a8`
- end: `0x180004a3d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800056c4`

## callees

- `0x1800023e0`
- `0x1800046b0`
- `0x1800046cc`
- `0x1800048a8`
- `0x180005488`
- `0x180005ecc`
- `0x180006614`
- `0x180006c68`
- `0x180006f08`
- `0x180007218`
- `0x180007308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004925`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800048e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800048e0`

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
0x1800048a8  mov     [rsp-8+arg_10], rbx
0x1800048ad  mov     [rsp-8+arg_18], rdi
0x1800048b2  push    rbp
0x1800048b3  lea     rbp, [rsp-170h]
0x1800048bb  sub     rsp, 270h
0x1800048c2  mov     rax, cs:__security_cookie
0x1800048c9  xor     rax, rsp
0x1800048cc  mov     [rbp+170h+var_10], rax
0x1800048d3  mov     rdi, rdx
0x1800048d6  mov     qword ptr [rdx], 0
0x1800048dd  mov     rbx, rcx
0x1800048e0  call    cs:__imp_GetCurrentProcessId
0x1800048e6  mov     [rsp+270h+var_248], rbx
0x1800048eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800048f2  mov     r9d, eax
0x1800048f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800048fd  mov     edx, 104h; unsigned __int64
0x180004902  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004907  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000490c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004912  mov     [rsp+270h+var_240], 0
0x18000491b  xor     r8d, r8d; dwFlags
0x18000491e  lea     rdx, [rsp+270h+Name]; lpName
0x180004923  xor     ecx, ecx; lpMutexAttributes
0x180004925  call    cs:__imp_CreateMutexExW
0x18000492b  mov     rdx, rax
0x18000492e  lea     rcx, [rsp+270h+var_240]
0x180004933  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004938  cmp     [rsp+270h+var_240], 0
0x18000493e  jnz     short loc_18000494C
0x180004940  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004945  mov     ebx, eax
0x180004947  jmp     loc_1800049E8
0x18000494c  lea     rdx, [rsp+270h+var_238]
0x180004951  lea     rcx, [rsp+270h+var_240]
0x180004956  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000495b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180004960  mov     [rsp+270h+var_230], 0
0x180004969  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000496e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004973  mov     ebx, eax
0x180004975  test    eax, eax
0x180004977  jns     short loc_1800049C1
0x180004979  mov     rcx, [rbp+178h]; this
0x180004980  mov     r9d, eax; char *
0x180004983  mov     edx, 66h ; 'f'; void *
0x180004988  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000498d  mov     rcx, [rbp+178h]; this
0x180004994  mov     r9d, ebx; char *
0x180004997  mov     edx, 6Fh ; 'o'; void *
0x18000499c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049a1  mov     r9d, ebx; char *
0x1800049a4  mov     edx, 12Eh; void *
0x1800049a9  mov     rcx, [rbp+178h]; this
0x1800049b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049b5  lea     rcx, [rsp+270h+var_238]
0x1800049ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800049bf  jmp     short loc_1800049E8
0x1800049c1  mov     rax, [rsp+270h+var_230]
0x1800049c6  lea     rcx, ds:0[rax*4]
0x1800049ce  test    rcx, rcx
0x1800049d1  jz      short loc_180004A18
0x1800049d3  mov     [rdi], rcx
0x1800049d6  mov     eax, [rcx]
0x1800049d8  inc     eax
0x1800049da  mov     [rcx], eax
0x1800049dc  lea     rcx, [rsp+270h+var_238]
0x1800049e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800049e6  xor     ebx, ebx
0x1800049e8  lea     rcx, [rsp+270h+var_240]
0x1800049ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800049f2  mov     eax, ebx
0x1800049f4  mov     rcx, [rbp+170h+var_10]
0x1800049fb  xor     rcx, rsp; StackCookie
0x1800049fe  call    __security_check_cookie
0x180004a03  lea     r11, [rsp+270h+var_s0]
0x180004a0b  mov     rbx, [r11+20h]
0x180004a0f  mov     rdi, [r11+28h]
0x180004a13  mov     rsp, r11
0x180004a16  pop     rbp
0x180004a17  retn
0x180004a18  mov     r8, rdi
0x180004a1b  lea     rdx, [rsp+270h+var_240]
0x180004a20  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004a25  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004a2a  mov     ebx, eax
0x180004a2c  test    eax, eax
0x180004a2e  jns     short loc_1800049DC
0x180004a30  mov     r9d, eax
0x180004a33  mov     edx, 137h
0x180004a38  jmp     loc_1800049A9
```
