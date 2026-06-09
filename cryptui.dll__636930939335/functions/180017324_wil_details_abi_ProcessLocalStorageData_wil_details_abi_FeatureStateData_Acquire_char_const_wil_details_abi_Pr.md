# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180017324`
- end: `0x18001749f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180017c50`

## callees

- `0x1800153e8`
- `0x180016b50`
- `0x180016b6c`
- `0x180017324`
- `0x180019900`
- `0x18001aa2c`
- `0x18001bbdc`
- `0x18001c630`
- `0x18001cf54`
- `0x18001d714`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800173a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800173a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001735c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001735c`

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
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180017324  mov     [rsp-8+arg_10], rbx
0x180017329  mov     [rsp-8+arg_18], rdi
0x18001732e  push    rbp
0x18001732f  lea     rbp, [rsp-170h]
0x180017337  sub     rsp, 270h
0x18001733e  mov     rax, cs:__security_cookie
0x180017345  xor     rax, rsp
0x180017348  mov     [rbp+170h+var_10], rax
0x18001734f  mov     rdi, rdx
0x180017352  mov     rbx, rcx
0x180017355  mov     qword ptr [rdx], 0
0x18001735c  call    cs:__imp_GetCurrentProcessId
0x180017362  mov     r9d, eax
0x180017365  mov     [rsp+270h+var_248], rbx
0x18001736a  mov     [rsp+270h+var_250], 130h; int
0x180017372  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017379  mov     edx, 104h; unsigned __int64
0x18001737e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017383  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017388  mov     [rsp+270h+var_240], 0
0x180017391  mov     r9d, 1F0001h; dwDesiredAccess
0x180017397  xor     r8d, r8d; dwFlags
0x18001739a  lea     rdx, [rsp+270h+Name]; lpName
0x18001739f  xor     ecx, ecx; lpMutexAttributes
0x1800173a1  call    cs:__imp_CreateMutexExW
0x1800173a7  mov     rdx, rax
0x1800173aa  lea     rcx, [rsp+270h+var_240]
0x1800173af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800173b4  cmp     [rsp+270h+var_240], 0
0x1800173ba  jnz     short loc_1800173C5
0x1800173bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800173c1  mov     ebx, eax
0x1800173c3  jmp     short loc_180017435
0x1800173c5  lea     rdx, [rsp+270h+var_238]
0x1800173ca  lea     rcx, [rsp+270h+var_240]
0x1800173cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800173d4  nop
0x1800173d5  mov     [rsp+270h+var_230], 0
0x1800173de  lea     rdx, [rsp+270h+var_230]; void **
0x1800173e3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800173e8  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800173ed  mov     ebx, eax
0x1800173ef  test    eax, eax
0x1800173f1  jns     short loc_180017415
0x1800173f3  mov     rcx, [rbp+178h]; this
0x1800173fa  mov     r9d, eax; char *
0x1800173fd  mov     edx, 12Eh; void *
0x180017402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017407  nop
0x180017408  lea     rcx, [rsp+270h+var_238]
0x18001740d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017412  nop
0x180017413  jmp     short loc_180017435
0x180017415  mov     rcx, [rsp+270h+var_230]
0x18001741a  test    rcx, rcx
0x18001741d  jz      short loc_180017465
0x18001741f  mov     [rdi], rcx
0x180017422  mov     eax, [rcx]
0x180017424  inc     eax
0x180017426  mov     [rcx], eax
0x180017428  lea     rcx, [rsp+270h+var_238]
0x18001742d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017432  nop
0x180017433  xor     ebx, ebx
0x180017435  lea     rcx, [rsp+270h+var_240]
0x18001743a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001743f  mov     eax, ebx
0x180017441  mov     rcx, [rbp+170h+var_10]
0x180017448  xor     rcx, rsp; StackCookie
0x18001744b  call    __security_check_cookie
0x180017450  lea     r11, [rsp+270h+var_s0]
0x180017458  mov     rbx, [r11+20h]
0x18001745c  mov     rdi, [r11+28h]
0x180017460  mov     rsp, r11
0x180017463  pop     rbp
0x180017464  retn
0x180017465  mov     r8, rdi
0x180017468  lea     rdx, [rsp+270h+var_240]
0x18001746d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017472  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180017477  mov     ebx, eax
0x180017479  test    eax, eax
0x18001747b  jns     short loc_180017428
0x18001747d  mov     rcx, [rbp+178h]; this
0x180017484  mov     r9d, eax; char *
0x180017487  mov     edx, 137h; void *
0x18001748c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017491  nop
0x180017492  lea     rcx, [rsp+270h+var_238]
0x180017497  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001749c  nop
0x18001749d  jmp     short loc_180017435
```
