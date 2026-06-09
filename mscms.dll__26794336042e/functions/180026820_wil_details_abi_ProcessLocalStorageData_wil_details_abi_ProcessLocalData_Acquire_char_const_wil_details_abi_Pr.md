# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180026820`
- end: `0x180026989`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002b350`

## callees

- `0x180007a94`
- `0x180007b88`
- `0x1800089d8`
- `0x1800092c4`
- `0x180009958`
- `0x1800204cc`
- `0x180026820`
- `0x1800269d4`
- `0x1800269f8`
- `0x18002e5f0`
- `0x180041974`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002689d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002689d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026858`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12);
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
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180026820  mov     [rsp-8+arg_10], rbx
0x180026825  mov     [rsp-8+arg_18], rdi
0x18002682a  push    rbp
0x18002682b  lea     rbp, [rsp-170h]
0x180026833  sub     rsp, 270h
0x18002683a  mov     rax, cs:__security_cookie
0x180026841  xor     rax, rsp
0x180026844  mov     [rbp+170h+var_10], rax
0x18002684b  mov     rdi, rdx
0x18002684e  mov     rbx, rcx
0x180026851  mov     qword ptr [rdx], 0
0x180026858  call    cs:__imp_GetCurrentProcessId
0x18002685e  mov     r9d, eax
0x180026861  mov     [rsp+270h+var_248], rbx
0x180026866  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002686e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180026875  mov     edx, 104h; unsigned __int64
0x18002687a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002687f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026884  mov     [rsp+270h+var_240], 0
0x18002688d  mov     r9d, 1F0001h; dwDesiredAccess
0x180026893  xor     r8d, r8d; dwFlags
0x180026896  lea     rdx, [rsp+270h+Name]; lpName
0x18002689b  xor     ecx, ecx; lpMutexAttributes
0x18002689d  call    cs:__imp_CreateMutexExW
0x1800268a3  mov     rdx, rax
0x1800268a6  lea     rcx, [rsp+270h+var_240]
0x1800268ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800268b0  cmp     [rsp+270h+var_240], 0
0x1800268b6  jnz     short loc_1800268C1
0x1800268b8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800268bd  mov     ebx, eax
0x1800268bf  jmp     short loc_180026936
0x1800268c1  lea     rdx, [rsp+270h+var_238]
0x1800268c6  lea     rcx, [rsp+270h+var_240]
0x1800268cb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800268d0  nop
0x1800268d1  mov     [rsp+270h+var_230], 0
0x1800268da  lea     rdx, [rsp+270h+var_230]; void **
0x1800268df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800268e4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800268e9  mov     ebx, eax
0x1800268eb  test    eax, eax
0x1800268ed  jns     short loc_180026917
0x1800268ef  mov     edx, 12Eh; void *
0x1800268f4  lea     r8, aWil; "wil"
0x1800268fb  mov     r9d, eax; char *
0x1800268fe  mov     rcx, [rbp+178h]; this
0x180026905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002690a  nop
0x18002690b  lea     rcx, [rsp+270h+var_238]
0x180026910  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026915  jmp     short loc_180026936
0x180026917  mov     rcx, [rsp+270h+var_230]
0x18002691c  test    rcx, rcx
0x18002691f  jz      short loc_180026966
0x180026921  mov     [rdi], rcx
0x180026924  mov     eax, [rcx]
0x180026926  inc     eax
0x180026928  mov     [rcx], eax
0x18002692a  lea     rcx, [rsp+270h+var_238]
0x18002692f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026934  xor     ebx, ebx
0x180026936  lea     rcx, [rsp+270h+var_240]
0x18002693b  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180026940  mov     eax, ebx
0x180026942  mov     rcx, [rbp+170h+var_10]
0x180026949  xor     rcx, rsp; StackCookie
0x18002694c  call    __security_check_cookie
0x180026951  lea     r11, [rsp+270h+var_s0]
0x180026959  mov     rbx, [r11+20h]
0x18002695d  mov     rdi, [r11+28h]
0x180026961  mov     rsp, r11
0x180026964  pop     rbp
0x180026965  retn
0x180026966  mov     r8, rdi
0x180026969  lea     rdx, [rsp+270h+var_240]
0x18002696e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026973  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180026978  mov     ebx, eax
0x18002697a  test    eax, eax
0x18002697c  jns     short loc_18002692A
0x18002697e  mov     edx, 137h
0x180026983  jmp     loc_1800268F4
```
