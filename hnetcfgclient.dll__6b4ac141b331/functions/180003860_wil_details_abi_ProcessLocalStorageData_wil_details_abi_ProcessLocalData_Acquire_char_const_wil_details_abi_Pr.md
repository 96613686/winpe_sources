# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003860`
- end: `0x1800039f5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004378`

## callees

- `0x180003738`
- `0x180003754`
- `0x180003860`
- `0x1800040d8`
- `0x180004ab4`
- `0x180005144`
- `0x1800056dc`
- `0x180005850`
- `0x180005dec`
- `0x180006344`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800038dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800038dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003898`

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
0x180003860  mov     [rsp-8+arg_10], rbx
0x180003865  mov     [rsp-8+arg_18], rdi
0x18000386a  push    rbp
0x18000386b  lea     rbp, [rsp-170h]
0x180003873  sub     rsp, 270h
0x18000387a  mov     rax, cs:__security_cookie
0x180003881  xor     rax, rsp
0x180003884  mov     [rbp+170h+var_10], rax
0x18000388b  mov     rdi, rdx
0x18000388e  mov     qword ptr [rdx], 0
0x180003895  mov     rbx, rcx
0x180003898  call    cs:__imp_GetCurrentProcessId
0x18000389e  mov     [rsp+270h+var_248], rbx
0x1800038a3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800038aa  mov     r9d, eax
0x1800038ad  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800038b5  mov     edx, 104h; unsigned __int64
0x1800038ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800038bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800038c4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800038ca  mov     [rsp+270h+var_240], 0
0x1800038d3  xor     r8d, r8d; dwFlags
0x1800038d6  lea     rdx, [rsp+270h+Name]; lpName
0x1800038db  xor     ecx, ecx; lpMutexAttributes
0x1800038dd  call    cs:__imp_CreateMutexExW
0x1800038e3  mov     rdx, rax
0x1800038e6  lea     rcx, [rsp+270h+var_240]
0x1800038eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800038f0  cmp     [rsp+270h+var_240], 0
0x1800038f6  jnz     short loc_180003904
0x1800038f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800038fd  mov     ebx, eax
0x1800038ff  jmp     loc_1800039A0
0x180003904  lea     rdx, [rsp+270h+var_238]
0x180003909  lea     rcx, [rsp+270h+var_240]
0x18000390e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003913  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003918  mov     [rsp+270h+var_230], 0
0x180003921  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003926  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000392b  mov     ebx, eax
0x18000392d  test    eax, eax
0x18000392f  jns     short loc_180003979
0x180003931  mov     rcx, [rbp+178h]; this
0x180003938  mov     r9d, eax; char *
0x18000393b  mov     edx, 66h ; 'f'; void *
0x180003940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003945  mov     rcx, [rbp+178h]; this
0x18000394c  mov     r9d, ebx; char *
0x18000394f  mov     edx, 6Fh ; 'o'; void *
0x180003954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003959  mov     r9d, ebx; char *
0x18000395c  mov     edx, 12Eh; void *
0x180003961  mov     rcx, [rbp+178h]; this
0x180003968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000396d  lea     rcx, [rsp+270h+var_238]
0x180003972  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003977  jmp     short loc_1800039A0
0x180003979  mov     rax, [rsp+270h+var_230]
0x18000397e  lea     rcx, ds:0[rax*4]
0x180003986  test    rcx, rcx
0x180003989  jz      short loc_1800039D0
0x18000398b  mov     [rdi], rcx
0x18000398e  mov     eax, [rcx]
0x180003990  inc     eax
0x180003992  mov     [rcx], eax
0x180003994  lea     rcx, [rsp+270h+var_238]
0x180003999  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000399e  xor     ebx, ebx
0x1800039a0  lea     rcx, [rsp+270h+var_240]
0x1800039a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800039aa  mov     eax, ebx
0x1800039ac  mov     rcx, [rbp+170h+var_10]
0x1800039b3  xor     rcx, rsp; StackCookie
0x1800039b6  call    __security_check_cookie
0x1800039bb  lea     r11, [rsp+270h+var_s0]
0x1800039c3  mov     rbx, [r11+20h]
0x1800039c7  mov     rdi, [r11+28h]
0x1800039cb  mov     rsp, r11
0x1800039ce  pop     rbp
0x1800039cf  retn
0x1800039d0  mov     r8, rdi
0x1800039d3  lea     rdx, [rsp+270h+var_240]
0x1800039d8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800039dd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800039e2  mov     ebx, eax
0x1800039e4  test    eax, eax
0x1800039e6  jns     short loc_180003994
0x1800039e8  mov     r9d, eax
0x1800039eb  mov     edx, 137h
0x1800039f0  jmp     loc_180003961
```
