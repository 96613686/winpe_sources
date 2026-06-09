# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001217c`
- end: `0x1800122db`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013550`

## callees

- `0x18000c798`
- `0x18000ca10`
- `0x18000d7a4`
- `0x18000da54`
- `0x18000e2f0`
- `0x18001204c`
- `0x180012068`
- `0x18001217c`
- `0x180013248`
- `0x180014fd4`
- `0x180015924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800121f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800121f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800121b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800121b4`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18001217c  mov     [rsp-8+arg_10], rbx
0x180012181  mov     [rsp-8+arg_18], rdi
0x180012186  push    rbp
0x180012187  lea     rbp, [rsp-170h]
0x18001218f  sub     rsp, 270h
0x180012196  mov     rax, cs:__security_cookie
0x18001219d  xor     rax, rsp
0x1800121a0  mov     [rbp+170h+var_10], rax
0x1800121a7  mov     rdi, rdx
0x1800121aa  mov     qword ptr [rdx], 0
0x1800121b1  mov     rbx, rcx
0x1800121b4  call    cs:__imp_GetCurrentProcessId
0x1800121ba  mov     [rsp+270h+var_248], rbx
0x1800121bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800121c6  mov     r9d, eax
0x1800121c9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800121d1  mov     edx, 104h; unsigned __int64
0x1800121d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800121db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800121e0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800121e6  mov     [rsp+270h+var_240], 0
0x1800121ef  xor     r8d, r8d; dwFlags
0x1800121f2  lea     rdx, [rsp+270h+Name]; lpName
0x1800121f7  xor     ecx, ecx; lpMutexAttributes
0x1800121f9  call    cs:__imp_CreateMutexExW
0x1800121ff  mov     rdx, rax
0x180012202  lea     rcx, [rsp+270h+var_240]
0x180012207  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001220c  cmp     [rsp+270h+var_240], 0
0x180012212  jnz     short loc_18001221D
0x180012214  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012219  mov     ebx, eax
0x18001221b  jmp     short loc_180012289
0x18001221d  lea     rdx, [rsp+270h+var_238]
0x180012222  lea     rcx, [rsp+270h+var_240]
0x180012227  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001222c  lea     rdx, [rsp+270h+var_230]; void **
0x180012231  mov     [rsp+270h+var_230], 0
0x18001223a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001223f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180012244  mov     ebx, eax
0x180012246  test    eax, eax
0x180012248  jns     short loc_18001226A
0x18001224a  mov     edx, 12Eh; void *
0x18001224f  mov     rcx, [rbp+178h]; this
0x180012256  mov     r9d, eax; char *
0x180012259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001225e  lea     rcx, [rsp+270h+var_238]
0x180012263  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012268  jmp     short loc_180012289
0x18001226a  mov     rcx, [rsp+270h+var_230]
0x18001226f  test    rcx, rcx
0x180012272  jz      short loc_1800122B9
0x180012274  mov     [rdi], rcx
0x180012277  mov     eax, [rcx]
0x180012279  inc     eax
0x18001227b  mov     [rcx], eax
0x18001227d  lea     rcx, [rsp+270h+var_238]
0x180012282  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012287  xor     ebx, ebx
0x180012289  lea     rcx, [rsp+270h+var_240]
0x18001228e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012293  mov     eax, ebx
0x180012295  mov     rcx, [rbp+170h+var_10]
0x18001229c  xor     rcx, rsp; StackCookie
0x18001229f  call    __security_check_cookie
0x1800122a4  lea     r11, [rsp+270h+var_s0]
0x1800122ac  mov     rbx, [r11+20h]
0x1800122b0  mov     rdi, [r11+28h]
0x1800122b4  mov     rsp, r11
0x1800122b7  pop     rbp
0x1800122b8  retn
0x1800122b9  mov     r8, rdi
0x1800122bc  lea     rdx, [rsp+270h+var_240]
0x1800122c1  lea     rcx, [rsp+270h+Name]
0x1800122c6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800122cb  mov     ebx, eax
0x1800122cd  test    eax, eax
0x1800122cf  jns     short loc_18001227D
0x1800122d1  mov     edx, 137h
0x1800122d6  jmp     loc_18001224F
```
