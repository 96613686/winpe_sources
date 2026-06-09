# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800122e4`
- end: `0x180012443`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013404`

## callees

- `0x18000c798`
- `0x18000ca10`
- `0x18000d8f8`
- `0x18000da54`
- `0x18000e2f0`
- `0x18001204c`
- `0x180012068`
- `0x1800122e4`
- `0x180013248`
- `0x180014fd4`
- `0x180015924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012361`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001231c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001231c`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800122e4  mov     [rsp-8+arg_10], rbx
0x1800122e9  mov     [rsp-8+arg_18], rdi
0x1800122ee  push    rbp
0x1800122ef  lea     rbp, [rsp-170h]
0x1800122f7  sub     rsp, 270h
0x1800122fe  mov     rax, cs:__security_cookie
0x180012305  xor     rax, rsp
0x180012308  mov     [rbp+170h+var_10], rax
0x18001230f  mov     rdi, rdx
0x180012312  mov     qword ptr [rdx], 0
0x180012319  mov     rbx, rcx
0x18001231c  call    cs:__imp_GetCurrentProcessId
0x180012322  mov     [rsp+270h+var_248], rbx
0x180012327  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001232e  mov     r9d, eax
0x180012331  mov     [rsp+270h+var_250], 130h; int
0x180012339  mov     edx, 104h; unsigned __int64
0x18001233e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012343  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012348  mov     r9d, 1F0001h; dwDesiredAccess
0x18001234e  mov     [rsp+270h+var_240], 0
0x180012357  xor     r8d, r8d; dwFlags
0x18001235a  lea     rdx, [rsp+270h+Name]; lpName
0x18001235f  xor     ecx, ecx; lpMutexAttributes
0x180012361  call    cs:__imp_CreateMutexExW
0x180012367  mov     rdx, rax
0x18001236a  lea     rcx, [rsp+270h+var_240]
0x18001236f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012374  cmp     [rsp+270h+var_240], 0
0x18001237a  jnz     short loc_180012385
0x18001237c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012381  mov     ebx, eax
0x180012383  jmp     short loc_1800123F1
0x180012385  lea     rdx, [rsp+270h+var_238]
0x18001238a  lea     rcx, [rsp+270h+var_240]
0x18001238f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012394  lea     rdx, [rsp+270h+var_230]; void **
0x180012399  mov     [rsp+270h+var_230], 0
0x1800123a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800123a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800123ac  mov     ebx, eax
0x1800123ae  test    eax, eax
0x1800123b0  jns     short loc_1800123D2
0x1800123b2  mov     edx, 12Eh; void *
0x1800123b7  mov     rcx, [rbp+178h]; this
0x1800123be  mov     r9d, eax; char *
0x1800123c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123c6  lea     rcx, [rsp+270h+var_238]
0x1800123cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800123d0  jmp     short loc_1800123F1
0x1800123d2  mov     rcx, [rsp+270h+var_230]
0x1800123d7  test    rcx, rcx
0x1800123da  jz      short loc_180012421
0x1800123dc  mov     [rdi], rcx
0x1800123df  mov     eax, [rcx]
0x1800123e1  inc     eax
0x1800123e3  mov     [rcx], eax
0x1800123e5  lea     rcx, [rsp+270h+var_238]
0x1800123ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800123ef  xor     ebx, ebx
0x1800123f1  lea     rcx, [rsp+270h+var_240]
0x1800123f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800123fb  mov     eax, ebx
0x1800123fd  mov     rcx, [rbp+170h+var_10]
0x180012404  xor     rcx, rsp; StackCookie
0x180012407  call    __security_check_cookie
0x18001240c  lea     r11, [rsp+270h+var_s0]
0x180012414  mov     rbx, [r11+20h]
0x180012418  mov     rdi, [r11+28h]
0x18001241c  mov     rsp, r11
0x18001241f  pop     rbp
0x180012420  retn
0x180012421  mov     r8, rdi
0x180012424  lea     rdx, [rsp+270h+var_240]
0x180012429  lea     rcx, [rsp+270h+Name]
0x18001242e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180012433  mov     ebx, eax
0x180012435  test    eax, eax
0x180012437  jns     short loc_1800123E5
0x180012439  mov     edx, 137h
0x18001243e  jmp     loc_1800123B7
```
