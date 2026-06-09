# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000fb50`
- end: `0x18000fce5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010818`

## callees

- `0x18000a3f8`
- `0x18000a590`
- `0x18000ab30`
- `0x18000ee64`
- `0x18000faf8`
- `0x18000fb14`
- `0x18000fb50`
- `0x180010578`
- `0x180013b68`
- `0x1800146e4`
- `0x180014998`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fbcd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb88`

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
0x18000fb50  mov     [rsp-8+arg_10], rbx
0x18000fb55  mov     [rsp-8+arg_18], rdi
0x18000fb5a  push    rbp
0x18000fb5b  lea     rbp, [rsp-170h]
0x18000fb63  sub     rsp, 270h
0x18000fb6a  mov     rax, cs:__security_cookie
0x18000fb71  xor     rax, rsp
0x18000fb74  mov     [rbp+170h+var_10], rax
0x18000fb7b  mov     rdi, rdx
0x18000fb7e  mov     qword ptr [rdx], 0
0x18000fb85  mov     rbx, rcx
0x18000fb88  call    cs:__imp_GetCurrentProcessId
0x18000fb8e  mov     [rsp+270h+var_248], rbx
0x18000fb93  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000fb9a  mov     r9d, eax
0x18000fb9d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000fba5  mov     edx, 104h; unsigned __int64
0x18000fbaa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000fbaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fbb4  mov     r9d, 1F0001h; dwDesiredAccess
0x18000fbba  mov     [rsp+270h+var_240], 0
0x18000fbc3  xor     r8d, r8d; dwFlags
0x18000fbc6  lea     rdx, [rsp+270h+Name]; lpName
0x18000fbcb  xor     ecx, ecx; lpMutexAttributes
0x18000fbcd  call    cs:__imp_CreateMutexExW
0x18000fbd3  mov     rdx, rax
0x18000fbd6  lea     rcx, [rsp+270h+var_240]
0x18000fbdb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000fbe0  cmp     [rsp+270h+var_240], 0
0x18000fbe6  jnz     short loc_18000FBF4
0x18000fbe8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000fbed  mov     ebx, eax
0x18000fbef  jmp     loc_18000FC90
0x18000fbf4  lea     rdx, [rsp+270h+var_238]
0x18000fbf9  lea     rcx, [rsp+270h+var_240]
0x18000fbfe  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000fc03  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000fc08  mov     [rsp+270h+var_230], 0
0x18000fc11  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000fc16  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000fc1b  mov     ebx, eax
0x18000fc1d  test    eax, eax
0x18000fc1f  jns     short loc_18000FC69
0x18000fc21  mov     rcx, [rbp+178h]; this
0x18000fc28  mov     r9d, eax; char *
0x18000fc2b  mov     edx, 66h ; 'f'; void *
0x18000fc30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc35  mov     rcx, [rbp+178h]; this
0x18000fc3c  mov     r9d, ebx; char *
0x18000fc3f  mov     edx, 6Fh ; 'o'; void *
0x18000fc44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc49  mov     r9d, ebx; char *
0x18000fc4c  mov     edx, 12Eh; void *
0x18000fc51  mov     rcx, [rbp+178h]; this
0x18000fc58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc5d  lea     rcx, [rsp+270h+var_238]
0x18000fc62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fc67  jmp     short loc_18000FC90
0x18000fc69  mov     rax, [rsp+270h+var_230]
0x18000fc6e  lea     rcx, ds:0[rax*4]
0x18000fc76  test    rcx, rcx
0x18000fc79  jz      short loc_18000FCC0
0x18000fc7b  mov     [rdi], rcx
0x18000fc7e  mov     eax, [rcx]
0x18000fc80  inc     eax
0x18000fc82  mov     [rcx], eax
0x18000fc84  lea     rcx, [rsp+270h+var_238]
0x18000fc89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fc8e  xor     ebx, ebx
0x18000fc90  lea     rcx, [rsp+270h+var_240]
0x18000fc95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fc9a  mov     eax, ebx
0x18000fc9c  mov     rcx, [rbp+170h+var_10]
0x18000fca3  xor     rcx, rsp; StackCookie
0x18000fca6  call    __security_check_cookie
0x18000fcab  lea     r11, [rsp+270h+var_s0]
0x18000fcb3  mov     rbx, [r11+20h]
0x18000fcb7  mov     rdi, [r11+28h]
0x18000fcbb  mov     rsp, r11
0x18000fcbe  pop     rbp
0x18000fcbf  retn
0x18000fcc0  mov     r8, rdi
0x18000fcc3  lea     rdx, [rsp+270h+var_240]
0x18000fcc8  lea     rcx, [rsp+270h+Name]
0x18000fccd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000fcd2  mov     ebx, eax
0x18000fcd4  test    eax, eax
0x18000fcd6  jns     short loc_18000FC84
0x18000fcd8  mov     r9d, eax
0x18000fcdb  mov     edx, 137h
0x18000fce0  jmp     loc_18000FC51
```
