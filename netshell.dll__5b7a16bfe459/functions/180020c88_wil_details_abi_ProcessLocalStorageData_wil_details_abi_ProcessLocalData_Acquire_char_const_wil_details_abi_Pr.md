# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180020c88`
- end: `0x180020dee`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800216b0`

## callees

- `0x18001c020`
- `0x18001e1e0`
- `0x180020b58`
- `0x180020b74`
- `0x180020c88`
- `0x180021c30`
- `0x180022294`
- `0x1800228e8`
- `0x1800229f8`
- `0x180022e30`
- `0x180022f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020d05`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020d05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020cc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020cc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180020c88  mov     [rsp-8+arg_10], rbx
0x180020c8d  mov     [rsp-8+arg_18], rdi
0x180020c92  push    rbp
0x180020c93  lea     rbp, [rsp-170h]
0x180020c9b  sub     rsp, 270h
0x180020ca2  mov     rax, cs:__security_cookie
0x180020ca9  xor     rax, rsp
0x180020cac  mov     [rbp+170h+var_10], rax
0x180020cb3  mov     rdi, rdx
0x180020cb6  mov     qword ptr [rdx], 0
0x180020cbd  mov     rbx, rcx
0x180020cc0  call    cs:__imp_GetCurrentProcessId
0x180020cc6  mov     [rsp+270h+var_248], rbx
0x180020ccb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180020cd2  mov     r9d, eax
0x180020cd5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180020cdd  mov     edx, 104h; unsigned __int64
0x180020ce2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180020ce7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020cec  mov     r9d, 1F0001h; dwDesiredAccess
0x180020cf2  mov     [rsp+270h+var_240], 0
0x180020cfb  xor     r8d, r8d; dwFlags
0x180020cfe  lea     rdx, [rsp+270h+Name]; lpName
0x180020d03  xor     ecx, ecx; lpMutexAttributes
0x180020d05  call    cs:__imp_CreateMutexExW
0x180020d0b  mov     rdx, rax
0x180020d0e  lea     rcx, [rsp+270h+var_240]
0x180020d13  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020d18  cmp     [rsp+270h+var_240], 0
0x180020d1e  jnz     short loc_180020D29
0x180020d20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020d25  mov     ebx, eax
0x180020d27  jmp     short loc_180020D9C
0x180020d29  lea     rdx, [rsp+270h+var_238]
0x180020d2e  lea     rcx, [rsp+270h+var_240]
0x180020d33  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180020d38  lea     rdx, [rsp+270h+var_230]; void **
0x180020d3d  mov     [rsp+270h+var_230], 0
0x180020d46  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180020d4b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180020d50  mov     ebx, eax
0x180020d52  test    eax, eax
0x180020d54  jns     short loc_180020D7D
0x180020d56  mov     edx, 12Eh; void *
0x180020d5b  mov     rcx, [rbp+178h]; this
0x180020d62  lea     r8, aWil; "wil"
0x180020d69  mov     r9d, eax; char *
0x180020d6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d71  lea     rcx, [rsp+270h+var_238]
0x180020d76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020d7b  jmp     short loc_180020D9C
0x180020d7d  mov     rcx, [rsp+270h+var_230]
0x180020d82  test    rcx, rcx
0x180020d85  jz      short loc_180020DCC
0x180020d87  mov     [rdi], rcx
0x180020d8a  mov     eax, [rcx]
0x180020d8c  inc     eax
0x180020d8e  mov     [rcx], eax
0x180020d90  lea     rcx, [rsp+270h+var_238]
0x180020d95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020d9a  xor     ebx, ebx
0x180020d9c  lea     rcx, [rsp+270h+var_240]
0x180020da1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020da6  mov     eax, ebx
0x180020da8  mov     rcx, [rbp+170h+var_10]
0x180020daf  xor     rcx, rsp; StackCookie
0x180020db2  call    __security_check_cookie
0x180020db7  lea     r11, [rsp+270h+var_s0]
0x180020dbf  mov     rbx, [r11+20h]
0x180020dc3  mov     rdi, [r11+28h]
0x180020dc7  mov     rsp, r11
0x180020dca  pop     rbp
0x180020dcb  retn
0x180020dcc  mov     r8, rdi
0x180020dcf  lea     rdx, [rsp+270h+var_240]
0x180020dd4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180020dd9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180020dde  mov     ebx, eax
0x180020de0  test    eax, eax
0x180020de2  jns     short loc_180020D90
0x180020de4  mov     edx, 137h
0x180020de9  jmp     loc_180020D5B
```
