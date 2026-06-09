# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004548`
- end: `0x1800046a7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005130`

## callees

- `0x1800043e4`
- `0x180004400`
- `0x180004548`
- `0x180004e48`
- `0x1800058fc`
- `0x18000604c`
- `0x1800065e8`
- `0x180006740`
- `0x180006cd8`
- `0x1800070c8`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004580`

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
0x180004548  mov     [rsp-8+arg_10], rbx
0x18000454d  mov     [rsp-8+arg_18], rdi
0x180004552  push    rbp
0x180004553  lea     rbp, [rsp-170h]
0x18000455b  sub     rsp, 270h
0x180004562  mov     rax, cs:__security_cookie
0x180004569  xor     rax, rsp
0x18000456c  mov     [rbp+170h+var_10], rax
0x180004573  mov     rdi, rdx
0x180004576  mov     qword ptr [rdx], 0
0x18000457d  mov     rbx, rcx
0x180004580  call    cs:__imp_GetCurrentProcessId
0x180004586  mov     [rsp+270h+var_248], rbx
0x18000458b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004592  mov     r9d, eax
0x180004595  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000459d  mov     edx, 104h; unsigned __int64
0x1800045a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800045a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800045ac  mov     r9d, 1F0001h; dwDesiredAccess
0x1800045b2  mov     [rsp+270h+var_240], 0
0x1800045bb  xor     r8d, r8d; dwFlags
0x1800045be  lea     rdx, [rsp+270h+Name]; lpName
0x1800045c3  xor     ecx, ecx; lpMutexAttributes
0x1800045c5  call    cs:__imp_CreateMutexExW
0x1800045cb  mov     rdx, rax
0x1800045ce  lea     rcx, [rsp+270h+var_240]
0x1800045d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800045d8  cmp     [rsp+270h+var_240], 0
0x1800045de  jnz     short loc_1800045E9
0x1800045e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800045e5  mov     ebx, eax
0x1800045e7  jmp     short loc_180004655
0x1800045e9  lea     rdx, [rsp+270h+var_238]
0x1800045ee  lea     rcx, [rsp+270h+var_240]
0x1800045f3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800045f8  lea     rdx, [rsp+270h+var_230]; void **
0x1800045fd  mov     [rsp+270h+var_230], 0
0x180004606  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000460b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004610  mov     ebx, eax
0x180004612  test    eax, eax
0x180004614  jns     short loc_180004636
0x180004616  mov     edx, 12Eh; void *
0x18000461b  mov     rcx, [rbp+178h]; this
0x180004622  mov     r9d, eax; char *
0x180004625  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000462a  lea     rcx, [rsp+270h+var_238]
0x18000462f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004634  jmp     short loc_180004655
0x180004636  mov     rcx, [rsp+270h+var_230]
0x18000463b  test    rcx, rcx
0x18000463e  jz      short loc_180004685
0x180004640  mov     [rdi], rcx
0x180004643  mov     eax, [rcx]
0x180004645  inc     eax
0x180004647  mov     [rcx], eax
0x180004649  lea     rcx, [rsp+270h+var_238]
0x18000464e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004653  xor     ebx, ebx
0x180004655  lea     rcx, [rsp+270h+var_240]
0x18000465a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000465f  mov     eax, ebx
0x180004661  mov     rcx, [rbp+170h+var_10]
0x180004668  xor     rcx, rsp; StackCookie
0x18000466b  call    __security_check_cookie
0x180004670  lea     r11, [rsp+270h+var_s0]
0x180004678  mov     rbx, [r11+20h]
0x18000467c  mov     rdi, [r11+28h]
0x180004680  mov     rsp, r11
0x180004683  pop     rbp
0x180004684  retn
0x180004685  mov     r8, rdi
0x180004688  lea     rdx, [rsp+270h+var_240]
0x18000468d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004692  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004697  mov     ebx, eax
0x180004699  test    eax, eax
0x18000469b  jns     short loc_180004649
0x18000469d  mov     edx, 137h
0x1800046a2  jmp     loc_18000461B
```
