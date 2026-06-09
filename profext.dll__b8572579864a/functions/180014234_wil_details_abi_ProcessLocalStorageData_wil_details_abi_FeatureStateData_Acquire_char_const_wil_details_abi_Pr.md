# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180014234`
- end: `0x1800143a7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018c10`

## callees

- `0x180004030`
- `0x180004594`
- `0x18000637c`
- `0x180009190`
- `0x18000c618`
- `0x18000d540`
- `0x18000f114`
- `0x18000f968`
- `0x180014234`
- `0x1800193cc`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800142b7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800142b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001426c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001426c`

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
0x180014234  mov     [rsp-8+arg_10], rbx
0x180014239  mov     [rsp-8+arg_18], rdi
0x18001423e  push    rbp
0x18001423f  lea     rbp, [rsp-170h]
0x180014247  sub     rsp, 270h
0x18001424e  mov     rax, cs:__security_cookie
0x180014255  xor     rax, rsp
0x180014258  mov     [rbp+170h+var_10], rax
0x18001425f  mov     rdi, rdx
0x180014262  mov     qword ptr [rdx], 0
0x180014269  mov     rbx, rcx
0x18001426c  call    cs:__imp_GetCurrentProcessId
0x180014273  nop     dword ptr [rax+rax+00h]
0x180014278  mov     [rsp+270h+var_248], rbx
0x18001427d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014284  mov     r9d, eax
0x180014287  mov     [rsp+270h+var_250], 130h; int
0x18001428f  mov     edx, 104h; unsigned __int64
0x180014294  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014299  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001429e  mov     r9d, 1F0001h; dwDesiredAccess
0x1800142a4  mov     [rsp+270h+var_240], 0
0x1800142ad  xor     r8d, r8d; dwFlags
0x1800142b0  lea     rdx, [rsp+270h+Name]; lpName
0x1800142b5  xor     ecx, ecx; lpMutexAttributes
0x1800142b7  call    cs:__imp_CreateMutexExW
0x1800142be  nop     dword ptr [rax+rax+00h]
0x1800142c3  mov     rdx, rax
0x1800142c6  lea     rcx, [rsp+270h+var_240]
0x1800142cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800142d0  cmp     [rsp+270h+var_240], 0
0x1800142d6  jnz     short loc_1800142E1
0x1800142d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800142dd  mov     ebx, eax
0x1800142df  jmp     short loc_180014354
0x1800142e1  lea     rdx, [rsp+270h+var_238]
0x1800142e6  lea     rcx, [rsp+270h+var_240]
0x1800142eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800142f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800142f5  mov     [rsp+270h+var_230], 0
0x1800142fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014303  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180014308  mov     ebx, eax
0x18001430a  test    eax, eax
0x18001430c  jns     short loc_180014335
0x18001430e  mov     edx, 12Eh; void *
0x180014313  mov     rcx, [rbp+178h]; this
0x18001431a  lea     r8, aWil; "wil"
0x180014321  mov     r9d, eax; char *
0x180014324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014329  lea     rcx, [rsp+270h+var_238]
0x18001432e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014333  jmp     short loc_180014354
0x180014335  mov     rcx, [rsp+270h+var_230]
0x18001433a  test    rcx, rcx
0x18001433d  jz      short loc_180014385
0x18001433f  mov     [rdi], rcx
0x180014342  mov     eax, [rcx]
0x180014344  inc     eax
0x180014346  mov     [rcx], eax
0x180014348  lea     rcx, [rsp+270h+var_238]
0x18001434d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014352  xor     ebx, ebx
0x180014354  lea     rcx, [rsp+270h+var_240]
0x180014359  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001435e  mov     eax, ebx
0x180014360  mov     rcx, [rbp+170h+var_10]
0x180014367  xor     rcx, rsp; StackCookie
0x18001436a  call    __security_check_cookie
0x18001436f  lea     r11, [rsp+270h+var_s0]
0x180014377  mov     rbx, [r11+20h]
0x18001437b  mov     rdi, [r11+28h]
0x18001437f  mov     rsp, r11
0x180014382  pop     rbp
0x180014383  retn
0x180014385  mov     r8, rdi
0x180014388  lea     rdx, [rsp+270h+var_240]
0x18001438d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014392  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180014397  mov     ebx, eax
0x180014399  test    eax, eax
0x18001439b  jns     short loc_180014348
0x18001439d  mov     edx, 137h
0x1800143a2  jmp     loc_180014313
```
