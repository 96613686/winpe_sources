# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800098f4`
- end: `0x180009a5c`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001128c`

## callees

- `0x180001710`
- `0x180003d5c`
- `0x1800085c0`
- `0x1800085dc`
- `0x1800098f4`
- `0x180011134`
- `0x180012090`
- `0x180016664`
- `0x1800179b8`
- `0x180018bb4`
- `0x180018f60`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180009971`
- `KERNEL32!CreateMutexExW` at `0x180009971`
- `KERNEL32!GetCurrentProcessId` at `0x18000992c`
- `KERNEL32!GetCurrentProcessId` at `0x18000992c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x1800098f4  mov     [rsp-8+arg_10], rbx
0x1800098f9  mov     [rsp-8+arg_18], rdi
0x1800098fe  push    rbp
0x1800098ff  lea     rbp, [rsp-170h]
0x180009907  sub     rsp, 270h
0x18000990e  mov     rax, cs:__security_cookie
0x180009915  xor     rax, rsp
0x180009918  mov     [rbp+170h+var_10], rax
0x18000991f  mov     rdi, rdx
0x180009922  mov     qword ptr [rdx], 0
0x180009929  mov     rbx, rcx
0x18000992c  call    cs:__imp_GetCurrentProcessId
0x180009932  mov     [rsp+270h+var_248], rbx
0x180009937  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000993e  mov     r9d, eax
0x180009941  mov     [rsp+270h+var_250], 130h; int
0x180009949  mov     edx, 104h; unsigned __int64
0x18000994e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009953  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009958  mov     r9d, 1F0001h; dwDesiredAccess
0x18000995e  mov     [rsp+270h+var_240], 0
0x180009967  xor     r8d, r8d; dwFlags
0x18000996a  lea     rdx, [rsp+270h+Name]; lpName
0x18000996f  xor     ecx, ecx; lpMutexAttributes
0x180009971  call    cs:__imp_CreateMutexExW
0x180009977  mov     rdx, rax
0x18000997a  lea     rcx, [rsp+270h+var_240]
0x18000997f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009984  cmp     [rsp+270h+var_240], 0
0x18000998a  jnz     short loc_180009995
0x18000998c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009991  mov     ebx, eax
0x180009993  jmp     short loc_180009A0A
0x180009995  lea     rdx, [rsp+270h+var_238]
0x18000999a  mov     [rsp+270h+var_238], 0
0x1800099a3  lea     rcx, [rsp+270h+var_240]
0x1800099a8  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800099ad  lea     rdx, [rsp+270h+var_230]; void **
0x1800099b2  mov     [rsp+270h+var_230], 0
0x1800099bb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800099c0  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800099c5  mov     ebx, eax
0x1800099c7  test    eax, eax
0x1800099c9  jns     short loc_1800099EB
0x1800099cb  mov     edx, 12Eh; void *
0x1800099d0  mov     rcx, [rbp+178h]; this
0x1800099d7  mov     r9d, eax; char *
0x1800099da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099df  lea     rcx, [rsp+270h+var_238]
0x1800099e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099e9  jmp     short loc_180009A0A
0x1800099eb  mov     rcx, [rsp+270h+var_230]
0x1800099f0  test    rcx, rcx
0x1800099f3  jz      short loc_180009A3A
0x1800099f5  mov     [rdi], rcx
0x1800099f8  mov     eax, [rcx]
0x1800099fa  inc     eax
0x1800099fc  mov     [rcx], eax
0x1800099fe  lea     rcx, [rsp+270h+var_238]
0x180009a03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a08  xor     ebx, ebx
0x180009a0a  lea     rcx, [rsp+270h+var_240]
0x180009a0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a14  mov     eax, ebx
0x180009a16  mov     rcx, [rbp+170h+var_10]
0x180009a1d  xor     rcx, rsp; StackCookie
0x180009a20  call    __security_check_cookie
0x180009a25  lea     r11, [rsp+270h+var_s0]
0x180009a2d  mov     rbx, [r11+20h]
0x180009a31  mov     rdi, [r11+28h]
0x180009a35  mov     rsp, r11
0x180009a38  pop     rbp
0x180009a39  retn
0x180009a3a  mov     r8, rdi
0x180009a3d  lea     rdx, [rsp+270h+var_240]
0x180009a42  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009a47  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009a4c  mov     ebx, eax
0x180009a4e  test    eax, eax
0x180009a50  jns     short loc_1800099FE
0x180009a52  mov     edx, 137h
0x180009a57  jmp     loc_1800099D0
```
