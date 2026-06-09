# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001966c`
- end: `0x1800197cb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ad64`

## callees

- `0x180019330`
- `0x18001934c`
- `0x18001966c`
- `0x18001aa38`
- `0x18001b69c`
- `0x18001c8b4`
- `0x18001ce20`
- `0x18001d214`
- `0x18001da54`
- `0x18001dedc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800196e9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800196e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800196a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800196a4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001966c  mov     [rsp-8+arg_10], rbx
0x180019671  mov     [rsp-8+arg_18], rdi
0x180019676  push    rbp
0x180019677  lea     rbp, [rsp-170h]
0x18001967f  sub     rsp, 270h
0x180019686  mov     rax, cs:__security_cookie
0x18001968d  xor     rax, rsp
0x180019690  mov     [rbp+170h+var_10], rax
0x180019697  mov     rdi, rdx
0x18001969a  mov     qword ptr [rdx], 0
0x1800196a1  mov     rbx, rcx
0x1800196a4  call    cs:__imp_GetCurrentProcessId
0x1800196aa  mov     [rsp+270h+var_248], rbx
0x1800196af  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800196b6  mov     r9d, eax
0x1800196b9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800196c1  mov     edx, 104h; unsigned __int64
0x1800196c6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800196cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800196d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800196d6  mov     [rsp+270h+var_240], 0
0x1800196df  xor     r8d, r8d; dwFlags
0x1800196e2  lea     rdx, [rsp+270h+Name]; lpName
0x1800196e7  xor     ecx, ecx; lpMutexAttributes
0x1800196e9  call    cs:__imp_CreateMutexExW
0x1800196ef  mov     rdx, rax
0x1800196f2  lea     rcx, [rsp+270h+var_240]
0x1800196f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800196fc  cmp     [rsp+270h+var_240], 0
0x180019702  jnz     short loc_18001970D
0x180019704  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019709  mov     ebx, eax
0x18001970b  jmp     short loc_180019779
0x18001970d  lea     rdx, [rsp+270h+var_238]
0x180019712  lea     rcx, [rsp+270h+var_240]
0x180019717  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001971c  lea     rdx, [rsp+270h+var_230]; void **
0x180019721  mov     [rsp+270h+var_230], 0
0x18001972a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001972f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180019734  mov     ebx, eax
0x180019736  test    eax, eax
0x180019738  jns     short loc_18001975A
0x18001973a  mov     edx, 12Eh; void *
0x18001973f  mov     rcx, [rbp+178h]; this
0x180019746  mov     r9d, eax; char *
0x180019749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001974e  lea     rcx, [rsp+270h+var_238]
0x180019753  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019758  jmp     short loc_180019779
0x18001975a  mov     rcx, [rsp+270h+var_230]
0x18001975f  test    rcx, rcx
0x180019762  jz      short loc_1800197A9
0x180019764  mov     [rdi], rcx
0x180019767  mov     eax, [rcx]
0x180019769  inc     eax
0x18001976b  mov     [rcx], eax
0x18001976d  lea     rcx, [rsp+270h+var_238]
0x180019772  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019777  xor     ebx, ebx
0x180019779  lea     rcx, [rsp+270h+var_240]
0x18001977e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019783  mov     eax, ebx
0x180019785  mov     rcx, [rbp+170h+var_10]
0x18001978c  xor     rcx, rsp; StackCookie
0x18001978f  call    __security_check_cookie
0x180019794  lea     r11, [rsp+270h+var_s0]
0x18001979c  mov     rbx, [r11+20h]
0x1800197a0  mov     rdi, [r11+28h]
0x1800197a4  mov     rsp, r11
0x1800197a7  pop     rbp
0x1800197a8  retn
0x1800197a9  mov     r8, rdi
0x1800197ac  lea     rdx, [rsp+270h+var_240]
0x1800197b1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800197b6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800197bb  mov     ebx, eax
0x1800197bd  test    eax, eax
0x1800197bf  jns     short loc_18001976D
0x1800197c1  mov     edx, 137h
0x1800197c6  jmp     loc_18001973F
```
