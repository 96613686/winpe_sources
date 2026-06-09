# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800197d4`
- end: `0x180019933`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001abf4`

## callees

- `0x180019330`
- `0x18001934c`
- `0x1800197d4`
- `0x18001aa38`
- `0x18001b7f0`
- `0x18001c8b4`
- `0x18001ce20`
- `0x18001d214`
- `0x18001da54`
- `0x18001dedc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019851`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001980c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001980c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800197d4  mov     [rsp-8+arg_10], rbx
0x1800197d9  mov     [rsp-8+arg_18], rdi
0x1800197de  push    rbp
0x1800197df  lea     rbp, [rsp-170h]
0x1800197e7  sub     rsp, 270h
0x1800197ee  mov     rax, cs:__security_cookie
0x1800197f5  xor     rax, rsp
0x1800197f8  mov     [rbp+170h+var_10], rax
0x1800197ff  mov     rdi, rdx
0x180019802  mov     qword ptr [rdx], 0
0x180019809  mov     rbx, rcx
0x18001980c  call    cs:__imp_GetCurrentProcessId
0x180019812  mov     [rsp+270h+var_248], rbx
0x180019817  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001981e  mov     r9d, eax
0x180019821  mov     [rsp+270h+var_250], 130h; int
0x180019829  mov     edx, 104h; unsigned __int64
0x18001982e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019833  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019838  mov     r9d, 1F0001h; dwDesiredAccess
0x18001983e  mov     [rsp+270h+var_240], 0
0x180019847  xor     r8d, r8d; dwFlags
0x18001984a  lea     rdx, [rsp+270h+Name]; lpName
0x18001984f  xor     ecx, ecx; lpMutexAttributes
0x180019851  call    cs:__imp_CreateMutexExW
0x180019857  mov     rdx, rax
0x18001985a  lea     rcx, [rsp+270h+var_240]
0x18001985f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019864  cmp     [rsp+270h+var_240], 0
0x18001986a  jnz     short loc_180019875
0x18001986c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019871  mov     ebx, eax
0x180019873  jmp     short loc_1800198E1
0x180019875  lea     rdx, [rsp+270h+var_238]
0x18001987a  lea     rcx, [rsp+270h+var_240]
0x18001987f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180019884  lea     rdx, [rsp+270h+var_230]; void **
0x180019889  mov     [rsp+270h+var_230], 0
0x180019892  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019897  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001989c  mov     ebx, eax
0x18001989e  test    eax, eax
0x1800198a0  jns     short loc_1800198C2
0x1800198a2  mov     edx, 12Eh; void *
0x1800198a7  mov     rcx, [rbp+178h]; this
0x1800198ae  mov     r9d, eax; char *
0x1800198b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198b6  lea     rcx, [rsp+270h+var_238]
0x1800198bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800198c0  jmp     short loc_1800198E1
0x1800198c2  mov     rcx, [rsp+270h+var_230]
0x1800198c7  test    rcx, rcx
0x1800198ca  jz      short loc_180019911
0x1800198cc  mov     [rdi], rcx
0x1800198cf  mov     eax, [rcx]
0x1800198d1  inc     eax
0x1800198d3  mov     [rcx], eax
0x1800198d5  lea     rcx, [rsp+270h+var_238]
0x1800198da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800198df  xor     ebx, ebx
0x1800198e1  lea     rcx, [rsp+270h+var_240]
0x1800198e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800198eb  mov     eax, ebx
0x1800198ed  mov     rcx, [rbp+170h+var_10]
0x1800198f4  xor     rcx, rsp; StackCookie
0x1800198f7  call    __security_check_cookie
0x1800198fc  lea     r11, [rsp+270h+var_s0]
0x180019904  mov     rbx, [r11+20h]
0x180019908  mov     rdi, [r11+28h]
0x18001990c  mov     rsp, r11
0x18001990f  pop     rbp
0x180019910  retn
0x180019911  mov     r8, rdi
0x180019914  lea     rdx, [rsp+270h+var_240]
0x180019919  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001991e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180019923  mov     ebx, eax
0x180019925  test    eax, eax
0x180019927  jns     short loc_1800198D5
0x180019929  mov     edx, 137h
0x18001992e  jmp     loc_1800198A7
```
