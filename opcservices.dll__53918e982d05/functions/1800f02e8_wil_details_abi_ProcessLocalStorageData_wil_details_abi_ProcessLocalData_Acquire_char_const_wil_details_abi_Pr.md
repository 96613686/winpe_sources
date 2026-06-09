# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800f02e8`
- end: `0x1800f047d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800f0d70`

## callees

- `0x180012468`
- `0x1800c6c88`
- `0x1800f01b0`
- `0x1800f01cc`
- `0x1800f02e8`
- `0x1800f1404`
- `0x1800f187c`
- `0x1800f1e8c`
- `0x1800f2288`
- `0x1800f238c`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f0320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f0320`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800f0365`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800f0365`

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
0x1800f02e8  mov     [rsp-8+arg_10], rbx
0x1800f02ed  mov     [rsp-8+arg_18], rdi
0x1800f02f2  push    rbp
0x1800f02f3  lea     rbp, [rsp-170h]
0x1800f02fb  sub     rsp, 270h
0x1800f0302  mov     rax, cs:__security_cookie
0x1800f0309  xor     rax, rsp
0x1800f030c  mov     [rbp+170h+var_10], rax
0x1800f0313  mov     rdi, rdx
0x1800f0316  mov     qword ptr [rdx], 0
0x1800f031d  mov     rbx, rcx
0x1800f0320  call    cs:__imp_GetCurrentProcessId
0x1800f0326  mov     [rsp+270h+var_248], rbx
0x1800f032b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800f0332  mov     r9d, eax
0x1800f0335  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800f033d  mov     edx, 104h; unsigned __int64
0x1800f0342  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800f0347  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f034c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800f0352  mov     [rsp+270h+var_240], 0
0x1800f035b  xor     r8d, r8d; dwFlags
0x1800f035e  lea     rdx, [rsp+270h+Name]; lpName
0x1800f0363  xor     ecx, ecx; lpMutexAttributes
0x1800f0365  call    cs:__imp_CreateMutexExW
0x1800f036b  mov     rdx, rax
0x1800f036e  lea     rcx, [rsp+270h+var_240]
0x1800f0373  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800f0378  cmp     [rsp+270h+var_240], 0
0x1800f037e  jnz     short loc_1800F038C
0x1800f0380  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800f0385  mov     ebx, eax
0x1800f0387  jmp     loc_1800F0428
0x1800f038c  lea     rdx, [rsp+270h+var_238]
0x1800f0391  lea     rcx, [rsp+270h+var_240]
0x1800f0396  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800f039b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800f03a0  mov     [rsp+270h+var_230], 0
0x1800f03a9  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800f03ae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800f03b3  mov     ebx, eax
0x1800f03b5  test    eax, eax
0x1800f03b7  jns     short loc_1800F0401
0x1800f03b9  mov     rcx, [rbp+178h]; this
0x1800f03c0  mov     r9d, eax; char *
0x1800f03c3  mov     edx, 66h ; 'f'; void *
0x1800f03c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f03cd  mov     rcx, [rbp+178h]; this
0x1800f03d4  mov     r9d, ebx; char *
0x1800f03d7  mov     edx, 6Fh ; 'o'; void *
0x1800f03dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f03e1  mov     r9d, ebx; char *
0x1800f03e4  mov     edx, 12Eh; void *
0x1800f03e9  mov     rcx, [rbp+178h]; this
0x1800f03f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f03f5  lea     rcx, [rsp+270h+var_238]
0x1800f03fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f03ff  jmp     short loc_1800F0428
0x1800f0401  mov     rax, [rsp+270h+var_230]
0x1800f0406  lea     rcx, ds:0[rax*4]
0x1800f040e  test    rcx, rcx
0x1800f0411  jz      short loc_1800F0458
0x1800f0413  mov     [rdi], rcx
0x1800f0416  mov     eax, [rcx]
0x1800f0418  inc     eax
0x1800f041a  mov     [rcx], eax
0x1800f041c  lea     rcx, [rsp+270h+var_238]
0x1800f0421  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f0426  xor     ebx, ebx
0x1800f0428  lea     rcx, [rsp+270h+var_240]
0x1800f042d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f0432  mov     eax, ebx
0x1800f0434  mov     rcx, [rbp+170h+var_10]
0x1800f043b  xor     rcx, rsp; StackCookie
0x1800f043e  call    __security_check_cookie
0x1800f0443  lea     r11, [rsp+270h+var_s0]
0x1800f044b  mov     rbx, [r11+20h]
0x1800f044f  mov     rdi, [r11+28h]
0x1800f0453  mov     rsp, r11
0x1800f0456  pop     rbp
0x1800f0457  retn
0x1800f0458  mov     r8, rdi
0x1800f045b  lea     rdx, [rsp+270h+var_240]
0x1800f0460  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800f0465  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800f046a  mov     ebx, eax
0x1800f046c  test    eax, eax
0x1800f046e  jns     short loc_1800F041C
0x1800f0470  mov     r9d, eax
0x1800f0473  mov     edx, 137h
0x1800f0478  jmp     loc_1800F03E9
```
