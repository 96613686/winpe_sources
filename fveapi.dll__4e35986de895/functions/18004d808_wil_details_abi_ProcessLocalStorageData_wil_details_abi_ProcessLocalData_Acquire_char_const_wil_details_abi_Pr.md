# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004d808`
- end: `0x18004d97b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180061c10`

## callees

- `0x18000aae0`
- `0x18003fd18`
- `0x180046db8`
- `0x18004c678`
- `0x18004d808`
- `0x18004d984`
- `0x18004d9a4`
- `0x18004da48`
- `0x18004f1b8`
- `0x180061d4c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004d88b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004d88b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d840`

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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18004d808  mov     [rsp-8+arg_10], rbx
0x18004d80d  mov     [rsp-8+arg_18], rdi
0x18004d812  push    rbp
0x18004d813  lea     rbp, [rsp-170h]
0x18004d81b  sub     rsp, 270h
0x18004d822  mov     rax, cs:__security_cookie
0x18004d829  xor     rax, rsp
0x18004d82c  mov     [rbp+170h+var_10], rax
0x18004d833  mov     rdi, rdx
0x18004d836  mov     qword ptr [rdx], 0
0x18004d83d  mov     rbx, rcx
0x18004d840  call    cs:__imp_GetCurrentProcessId
0x18004d847  nop     dword ptr [rax+rax+00h]
0x18004d84c  mov     [rsp+270h+var_248], rbx
0x18004d851  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004d858  mov     r9d, eax
0x18004d85b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18004d863  mov     edx, 104h; unsigned __int64
0x18004d868  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004d86d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d872  mov     r9d, 1F0001h; dwDesiredAccess
0x18004d878  mov     [rsp+270h+var_240], 0
0x18004d881  xor     r8d, r8d; dwFlags
0x18004d884  lea     rdx, [rsp+270h+Name]; lpName
0x18004d889  xor     ecx, ecx; lpMutexAttributes
0x18004d88b  call    cs:__imp_CreateMutexExW
0x18004d892  nop     dword ptr [rax+rax+00h]
0x18004d897  mov     rdx, rax
0x18004d89a  lea     rcx, [rsp+270h+var_240]
0x18004d89f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004d8a4  cmp     [rsp+270h+var_240], 0
0x18004d8aa  jnz     short loc_18004D8B5
0x18004d8ac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004d8b1  mov     ebx, eax
0x18004d8b3  jmp     short loc_18004D928
0x18004d8b5  lea     rdx, [rsp+270h+var_238]
0x18004d8ba  lea     rcx, [rsp+270h+var_240]
0x18004d8bf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004d8c4  lea     rdx, [rsp+270h+var_230]; void **
0x18004d8c9  mov     [rsp+270h+var_230], 0
0x18004d8d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004d8d7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004d8dc  mov     ebx, eax
0x18004d8de  test    eax, eax
0x18004d8e0  jns     short loc_18004D909
0x18004d8e2  mov     edx, 12Eh; void *
0x18004d8e7  mov     rcx, [rbp+178h]; this
0x18004d8ee  lea     r8, aWil; "wil"
0x18004d8f5  mov     r9d, eax; char *
0x18004d8f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d8fd  lea     rcx, [rsp+270h+var_238]
0x18004d902  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d907  jmp     short loc_18004D928
0x18004d909  mov     rcx, [rsp+270h+var_230]
0x18004d90e  test    rcx, rcx
0x18004d911  jz      short loc_18004D959
0x18004d913  mov     [rdi], rcx
0x18004d916  mov     eax, [rcx]
0x18004d918  inc     eax
0x18004d91a  mov     [rcx], eax
0x18004d91c  lea     rcx, [rsp+270h+var_238]
0x18004d921  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d926  xor     ebx, ebx
0x18004d928  lea     rcx, [rsp+270h+var_240]
0x18004d92d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d932  mov     eax, ebx
0x18004d934  mov     rcx, [rbp+170h+var_10]
0x18004d93b  xor     rcx, rsp; StackCookie
0x18004d93e  call    __security_check_cookie
0x18004d943  lea     r11, [rsp+270h+var_s0]
0x18004d94b  mov     rbx, [r11+20h]
0x18004d94f  mov     rdi, [r11+28h]
0x18004d953  mov     rsp, r11
0x18004d956  pop     rbp
0x18004d957  retn
0x18004d959  mov     r8, rdi
0x18004d95c  lea     rdx, [rsp+270h+var_240]
0x18004d961  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004d966  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004d96b  mov     ebx, eax
0x18004d96d  test    eax, eax
0x18004d96f  jns     short loc_18004D91C
0x18004d971  mov     edx, 137h
0x18004d976  jmp     loc_18004D8E7
```
