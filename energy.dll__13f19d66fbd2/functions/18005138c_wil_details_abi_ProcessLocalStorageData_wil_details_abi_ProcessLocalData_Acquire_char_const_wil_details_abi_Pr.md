# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18005138c`
- end: `0x1800514eb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180052848`

## callees

- `0x180030bec`
- `0x18004a958`
- `0x18004ca90`
- `0x180051098`
- `0x1800510b4`
- `0x18005138c`
- `0x1800530a0`
- `0x18005423c`
- `0x180054d88`
- `0x180055564`
- `0x1800556e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051409`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051409`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800513c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800513c4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18005138c  mov     [rsp-8+arg_10], rbx
0x180051391  mov     [rsp-8+arg_18], rdi
0x180051396  push    rbp
0x180051397  lea     rbp, [rsp-170h]
0x18005139f  sub     rsp, 270h
0x1800513a6  mov     rax, cs:__security_cookie
0x1800513ad  xor     rax, rsp
0x1800513b0  mov     [rbp+170h+var_10], rax
0x1800513b7  mov     rdi, rdx
0x1800513ba  mov     qword ptr [rdx], 0
0x1800513c1  mov     rbx, rcx
0x1800513c4  call    cs:__imp_GetCurrentProcessId
0x1800513ca  mov     [rsp+270h+var_248], rbx
0x1800513cf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800513d6  mov     r9d, eax
0x1800513d9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800513e1  mov     edx, 104h; unsigned __int64
0x1800513e6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800513eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800513f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800513f6  mov     [rsp+270h+var_240], 0
0x1800513ff  xor     r8d, r8d; dwFlags
0x180051402  lea     rdx, [rsp+270h+Name]; lpName
0x180051407  xor     ecx, ecx; lpMutexAttributes
0x180051409  call    cs:__imp_CreateMutexExW
0x18005140f  mov     rdx, rax
0x180051412  lea     rcx, [rsp+270h+var_240]
0x180051417  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005141c  cmp     [rsp+270h+var_240], 0
0x180051422  jnz     short loc_18005142D
0x180051424  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180051429  mov     ebx, eax
0x18005142b  jmp     short loc_180051499
0x18005142d  lea     rdx, [rsp+270h+var_238]
0x180051432  lea     rcx, [rsp+270h+var_240]
0x180051437  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18005143c  lea     rdx, [rsp+270h+var_230]; void **
0x180051441  mov     [rsp+270h+var_230], 0
0x18005144a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005144f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180051454  mov     ebx, eax
0x180051456  test    eax, eax
0x180051458  jns     short loc_18005147A
0x18005145a  mov     edx, 12Eh; void *
0x18005145f  mov     rcx, [rbp+178h]; this
0x180051466  mov     r9d, eax; char *
0x180051469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005146e  lea     rcx, [rsp+270h+var_238]
0x180051473  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051478  jmp     short loc_180051499
0x18005147a  mov     rcx, [rsp+270h+var_230]
0x18005147f  test    rcx, rcx
0x180051482  jz      short loc_1800514C9
0x180051484  mov     [rdi], rcx
0x180051487  mov     eax, [rcx]
0x180051489  inc     eax
0x18005148b  mov     [rcx], eax
0x18005148d  lea     rcx, [rsp+270h+var_238]
0x180051492  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051497  xor     ebx, ebx
0x180051499  lea     rcx, [rsp+270h+var_240]
0x18005149e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800514a3  mov     eax, ebx
0x1800514a5  mov     rcx, [rbp+170h+var_10]
0x1800514ac  xor     rcx, rsp; StackCookie
0x1800514af  call    __security_check_cookie
0x1800514b4  lea     r11, [rsp+270h+var_s0]
0x1800514bc  mov     rbx, [r11+20h]
0x1800514c0  mov     rdi, [r11+28h]
0x1800514c4  mov     rsp, r11
0x1800514c7  pop     rbp
0x1800514c8  retn
0x1800514c9  mov     r8, rdi
0x1800514cc  lea     rdx, [rsp+270h+var_240]
0x1800514d1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800514d6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800514db  mov     ebx, eax
0x1800514dd  test    eax, eax
0x1800514df  jns     short loc_18005148D
0x1800514e1  mov     edx, 137h
0x1800514e6  jmp     loc_18005145F
```
