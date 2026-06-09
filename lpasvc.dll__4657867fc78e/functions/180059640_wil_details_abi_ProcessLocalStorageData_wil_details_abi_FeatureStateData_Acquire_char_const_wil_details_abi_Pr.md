# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180059640`
- end: `0x18005979f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005a550`

## callees

- `0x18000df90`
- `0x180058f90`
- `0x180058fac`
- `0x180059640`
- `0x18005a2d8`
- `0x18005b1cc`
- `0x18005c5dc`
- `0x18005cd64`
- `0x18005d1d8`
- `0x18005da14`
- `0x18005dd38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800596bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800596bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180059678`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180059678`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180059640  mov     [rsp-8+arg_10], rbx
0x180059645  mov     [rsp-8+arg_18], rdi
0x18005964a  push    rbp
0x18005964b  lea     rbp, [rsp-170h]
0x180059653  sub     rsp, 270h
0x18005965a  mov     rax, cs:__security_cookie
0x180059661  xor     rax, rsp
0x180059664  mov     [rbp+170h+var_10], rax
0x18005966b  mov     rdi, rdx
0x18005966e  mov     qword ptr [rdx], 0
0x180059675  mov     rbx, rcx
0x180059678  call    cs:__imp_GetCurrentProcessId
0x18005967e  mov     [rsp+270h+var_248], rbx
0x180059683  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005968a  mov     r9d, eax
0x18005968d  mov     [rsp+270h+var_250], 130h; int
0x180059695  mov     edx, 104h; unsigned __int64
0x18005969a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005969f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800596a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800596aa  mov     [rsp+270h+var_240], 0
0x1800596b3  xor     r8d, r8d; dwFlags
0x1800596b6  lea     rdx, [rsp+270h+Name]; lpName
0x1800596bb  xor     ecx, ecx; lpMutexAttributes
0x1800596bd  call    cs:__imp_CreateMutexExW
0x1800596c3  mov     rdx, rax
0x1800596c6  lea     rcx, [rsp+270h+var_240]
0x1800596cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800596d0  cmp     [rsp+270h+var_240], 0
0x1800596d6  jnz     short loc_1800596E1
0x1800596d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800596dd  mov     ebx, eax
0x1800596df  jmp     short loc_18005974D
0x1800596e1  lea     rdx, [rsp+270h+var_238]
0x1800596e6  lea     rcx, [rsp+270h+var_240]
0x1800596eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800596f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800596f5  mov     [rsp+270h+var_230], 0
0x1800596fe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180059703  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180059708  mov     ebx, eax
0x18005970a  test    eax, eax
0x18005970c  jns     short loc_18005972E
0x18005970e  mov     edx, 12Eh; void *
0x180059713  mov     rcx, [rbp+178h]; this
0x18005971a  mov     r9d, eax; char *
0x18005971d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059722  lea     rcx, [rsp+270h+var_238]
0x180059727  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005972c  jmp     short loc_18005974D
0x18005972e  mov     rcx, [rsp+270h+var_230]
0x180059733  test    rcx, rcx
0x180059736  jz      short loc_18005977D
0x180059738  mov     [rdi], rcx
0x18005973b  mov     eax, [rcx]
0x18005973d  inc     eax
0x18005973f  mov     [rcx], eax
0x180059741  lea     rcx, [rsp+270h+var_238]
0x180059746  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005974b  xor     ebx, ebx
0x18005974d  lea     rcx, [rsp+270h+var_240]
0x180059752  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180059757  mov     eax, ebx
0x180059759  mov     rcx, [rbp+170h+var_10]
0x180059760  xor     rcx, rsp; StackCookie
0x180059763  call    __security_check_cookie
0x180059768  lea     r11, [rsp+270h+var_s0]
0x180059770  mov     rbx, [r11+20h]
0x180059774  mov     rdi, [r11+28h]
0x180059778  mov     rsp, r11
0x18005977b  pop     rbp
0x18005977c  retn
0x18005977d  mov     r8, rdi
0x180059780  lea     rdx, [rsp+270h+var_240]
0x180059785  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005978a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005978f  mov     ebx, eax
0x180059791  test    eax, eax
0x180059793  jns     short loc_180059741
0x180059795  mov     edx, 137h
0x18005979a  jmp     loc_180059713
```
