# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004818`
- end: `0x18000497e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005554`

## callees

- `0x180002300`
- `0x1800042bc`
- `0x1800042d8`
- `0x180004818`
- `0x1800053c8`
- `0x180006164`
- `0x180007478`
- `0x18000797c`
- `0x180007d98`
- `0x180008564`
- `0x1800088f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004895`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004850`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004818  mov     [rsp-8+arg_10], rbx
0x18000481d  mov     [rsp-8+arg_18], rdi
0x180004822  push    rbp
0x180004823  lea     rbp, [rsp-170h]
0x18000482b  sub     rsp, 270h
0x180004832  mov     rax, cs:__security_cookie
0x180004839  xor     rax, rsp
0x18000483c  mov     [rbp+170h+var_10], rax
0x180004843  mov     rdi, rdx
0x180004846  mov     qword ptr [rdx], 0
0x18000484d  mov     rbx, rcx
0x180004850  call    cs:__imp_GetCurrentProcessId
0x180004856  mov     [rsp+270h+var_248], rbx
0x18000485b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004862  mov     r9d, eax
0x180004865  mov     [rsp+270h+var_250], 130h; int
0x18000486d  mov     edx, 104h; unsigned __int64
0x180004872  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004877  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000487c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004882  mov     [rsp+270h+var_240], 0
0x18000488b  xor     r8d, r8d; dwFlags
0x18000488e  lea     rdx, [rsp+270h+Name]; lpName
0x180004893  xor     ecx, ecx; lpMutexAttributes
0x180004895  call    cs:__imp_CreateMutexExW
0x18000489b  mov     rdx, rax
0x18000489e  lea     rcx, [rsp+270h+var_240]
0x1800048a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800048a8  cmp     [rsp+270h+var_240], 0
0x1800048ae  jnz     short loc_1800048B9
0x1800048b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800048b5  mov     ebx, eax
0x1800048b7  jmp     short loc_18000492C
0x1800048b9  lea     rdx, [rsp+270h+var_238]
0x1800048be  lea     rcx, [rsp+270h+var_240]
0x1800048c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800048c8  lea     rdx, [rsp+270h+var_230]; void **
0x1800048cd  mov     [rsp+270h+var_230], 0
0x1800048d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800048db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800048e0  mov     ebx, eax
0x1800048e2  test    eax, eax
0x1800048e4  jns     short loc_18000490D
0x1800048e6  mov     edx, 12Eh; void *
0x1800048eb  mov     rcx, [rbp+178h]; this
0x1800048f2  lea     r8, aWil; "wil"
0x1800048f9  mov     r9d, eax; char *
0x1800048fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004901  lea     rcx, [rsp+270h+var_238]
0x180004906  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000490b  jmp     short loc_18000492C
0x18000490d  mov     rcx, [rsp+270h+var_230]
0x180004912  test    rcx, rcx
0x180004915  jz      short loc_18000495C
0x180004917  mov     [rdi], rcx
0x18000491a  mov     eax, [rcx]
0x18000491c  inc     eax
0x18000491e  mov     [rcx], eax
0x180004920  lea     rcx, [rsp+270h+var_238]
0x180004925  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000492a  xor     ebx, ebx
0x18000492c  lea     rcx, [rsp+270h+var_240]
0x180004931  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004936  mov     eax, ebx
0x180004938  mov     rcx, [rbp+170h+var_10]
0x18000493f  xor     rcx, rsp; StackCookie
0x180004942  call    __security_check_cookie
0x180004947  lea     r11, [rsp+270h+var_s0]
0x18000494f  mov     rbx, [r11+20h]
0x180004953  mov     rdi, [r11+28h]
0x180004957  mov     rsp, r11
0x18000495a  pop     rbp
0x18000495b  retn
0x18000495c  mov     r8, rdi
0x18000495f  lea     rdx, [rsp+270h+var_240]
0x180004964  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004969  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000496e  mov     ebx, eax
0x180004970  test    eax, eax
0x180004972  jns     short loc_180004920
0x180004974  mov     edx, 137h
0x180004979  jmp     loc_1800048EB
```
