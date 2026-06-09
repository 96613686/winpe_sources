# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1802650ec`
- end: `0x18026524b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180265e28`

## callees

- `0x1801b0294`
- `0x180237254`
- `0x1802373b0`
- `0x18023ccc8`
- `0x18025b100`
- `0x180264db8`
- `0x180264dd4`
- `0x1802650ec`
- `0x180267b94`
- `0x180268444`
- `0x180268628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180265169`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180265169`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180265124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180265124`

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
0x1802650ec  mov     [rsp-8+arg_10], rbx
0x1802650f1  mov     [rsp-8+arg_18], rdi
0x1802650f6  push    rbp
0x1802650f7  lea     rbp, [rsp-170h]
0x1802650ff  sub     rsp, 270h
0x180265106  mov     rax, cs:__security_cookie
0x18026510d  xor     rax, rsp
0x180265110  mov     [rbp+170h+var_10], rax
0x180265117  mov     rdi, rdx
0x18026511a  mov     qword ptr [rdx], 0
0x180265121  mov     rbx, rcx
0x180265124  call    cs:__imp_GetCurrentProcessId
0x18026512a  mov     [rsp+270h+var_248], rbx
0x18026512f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180265136  mov     r9d, eax
0x180265139  mov     [rsp+270h+var_250], 130h; int
0x180265141  mov     edx, 104h; unsigned __int64
0x180265146  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18026514b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180265150  mov     r9d, 1F0001h; dwDesiredAccess
0x180265156  mov     [rsp+270h+var_240], 0
0x18026515f  xor     r8d, r8d; dwFlags
0x180265162  lea     rdx, [rsp+270h+Name]; lpName
0x180265167  xor     ecx, ecx; lpMutexAttributes
0x180265169  call    cs:__imp_CreateMutexExW
0x18026516f  mov     rdx, rax
0x180265172  lea     rcx, [rsp+270h+var_240]
0x180265177  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18026517c  cmp     [rsp+270h+var_240], 0
0x180265182  jnz     short loc_18026518D
0x180265184  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180265189  mov     ebx, eax
0x18026518b  jmp     short loc_1802651F9
0x18026518d  lea     rdx, [rsp+270h+var_238]
0x180265192  lea     rcx, [rsp+270h+var_240]
0x180265197  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18026519c  lea     rdx, [rsp+270h+var_230]; void **
0x1802651a1  mov     [rsp+270h+var_230], 0
0x1802651aa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1802651af  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1802651b4  mov     ebx, eax
0x1802651b6  test    eax, eax
0x1802651b8  jns     short loc_1802651DA
0x1802651ba  mov     edx, 12Eh; void *
0x1802651bf  mov     rcx, [rbp+178h]; this
0x1802651c6  mov     r9d, eax; char *
0x1802651c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802651ce  lea     rcx, [rsp+270h+var_238]
0x1802651d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802651d8  jmp     short loc_1802651F9
0x1802651da  mov     rcx, [rsp+270h+var_230]
0x1802651df  test    rcx, rcx
0x1802651e2  jz      short loc_180265229
0x1802651e4  mov     [rdi], rcx
0x1802651e7  mov     eax, [rcx]
0x1802651e9  inc     eax
0x1802651eb  mov     [rcx], eax
0x1802651ed  lea     rcx, [rsp+270h+var_238]
0x1802651f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802651f7  xor     ebx, ebx
0x1802651f9  lea     rcx, [rsp+270h+var_240]
0x1802651fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180265203  mov     eax, ebx
0x180265205  mov     rcx, [rbp+170h+var_10]
0x18026520c  xor     rcx, rsp; StackCookie
0x18026520f  call    __security_check_cookie
0x180265214  lea     r11, [rsp+270h+var_s0]
0x18026521c  mov     rbx, [r11+20h]
0x180265220  mov     rdi, [r11+28h]
0x180265224  mov     rsp, r11
0x180265227  pop     rbp
0x180265228  retn
0x180265229  mov     r8, rdi
0x18026522c  lea     rdx, [rsp+270h+var_240]
0x180265231  lea     rcx, [rsp+270h+Name]
0x180265236  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18026523b  mov     ebx, eax
0x18026523d  test    eax, eax
0x18026523f  jns     short loc_1802651ED
0x180265241  mov     edx, 137h
0x180265246  jmp     loc_1802651BF
```
