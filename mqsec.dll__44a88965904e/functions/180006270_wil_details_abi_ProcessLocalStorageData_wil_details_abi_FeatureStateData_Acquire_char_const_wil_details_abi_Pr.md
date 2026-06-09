# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006270`
- end: `0x1800063d2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007084`

## callees

- `0x180005d10`
- `0x180005d2c`
- `0x180006270`
- `0x180006e58`
- `0x18000875c`
- `0x18000989c`
- `0x18000a174`
- `0x18000a58c`
- `0x18000ac64`
- `0x18000afc8`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800062ed`
- `KERNEL32!CreateMutexExW` at `0x1800062ed`
- `KERNEL32!GetCurrentProcessId` at `0x1800062a8`
- `KERNEL32!GetCurrentProcessId` at `0x1800062a8`

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
0x180006270  mov     [rsp-8+arg_10], rbx
0x180006275  mov     [rsp-8+arg_18], rdi
0x18000627a  push    rbp
0x18000627b  lea     rbp, [rsp-170h]
0x180006283  sub     rsp, 270h
0x18000628a  mov     rax, cs:__security_cookie
0x180006291  xor     rax, rsp
0x180006294  mov     [rbp+170h+var_10], rax
0x18000629b  mov     rdi, rdx
0x18000629e  mov     rbx, rcx
0x1800062a1  mov     qword ptr [rdx], 0
0x1800062a8  call    cs:__imp_GetCurrentProcessId
0x1800062ae  mov     r9d, eax
0x1800062b1  mov     [rsp+270h+var_248], rbx
0x1800062b6  mov     [rsp+270h+var_250], 130h; int
0x1800062be  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800062c5  mov     edx, 104h; unsigned __int64
0x1800062ca  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800062cf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800062d4  mov     [rsp+270h+var_240], 0
0x1800062dd  mov     r9d, 1F0001h; dwDesiredAccess
0x1800062e3  xor     r8d, r8d; dwFlags
0x1800062e6  lea     rdx, [rsp+270h+Name]; lpName
0x1800062eb  xor     ecx, ecx; lpMutexAttributes
0x1800062ed  call    cs:__imp_CreateMutexExW
0x1800062f3  mov     rdx, rax
0x1800062f6  lea     rcx, [rsp+270h+var_240]
0x1800062fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006300  cmp     [rsp+270h+var_240], 0
0x180006306  jnz     short loc_180006311
0x180006308  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000630d  mov     ebx, eax
0x18000630f  jmp     short loc_18000637F
0x180006311  lea     rdx, [rsp+270h+var_238]
0x180006316  lea     rcx, [rsp+270h+var_240]
0x18000631b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006320  nop
0x180006321  mov     [rsp+270h+var_230], 0
0x18000632a  lea     rdx, [rsp+270h+var_230]; void **
0x18000632f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006334  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006339  mov     ebx, eax
0x18000633b  test    eax, eax
0x18000633d  jns     short loc_180006360
0x18000633f  mov     edx, 12Eh; void *
0x180006344  mov     r9d, eax; char *
0x180006347  mov     rcx, [rbp+178h]; this
0x18000634e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006353  nop
0x180006354  lea     rcx, [rsp+270h+var_238]
0x180006359  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000635e  jmp     short loc_18000637F
0x180006360  mov     rcx, [rsp+270h+var_230]
0x180006365  test    rcx, rcx
0x180006368  jz      short loc_1800063AF
0x18000636a  mov     [rdi], rcx
0x18000636d  mov     eax, [rcx]
0x18000636f  inc     eax
0x180006371  mov     [rcx], eax
0x180006373  lea     rcx, [rsp+270h+var_238]
0x180006378  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000637d  xor     ebx, ebx
0x18000637f  lea     rcx, [rsp+270h+var_240]
0x180006384  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006389  mov     eax, ebx
0x18000638b  mov     rcx, [rbp+170h+var_10]
0x180006392  xor     rcx, rsp; StackCookie
0x180006395  call    __security_check_cookie
0x18000639a  lea     r11, [rsp+270h+var_s0]
0x1800063a2  mov     rbx, [r11+20h]
0x1800063a6  mov     rdi, [r11+28h]
0x1800063aa  mov     rsp, r11
0x1800063ad  pop     rbp
0x1800063ae  retn
0x1800063af  mov     r8, rdi
0x1800063b2  lea     rdx, [rsp+270h+var_240]
0x1800063b7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800063bc  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800063c1  mov     ebx, eax
0x1800063c3  test    eax, eax
0x1800063c5  jns     short loc_180006373
0x1800063c7  mov     edx, 137h
0x1800063cc  jmp     loc_180006344
```
