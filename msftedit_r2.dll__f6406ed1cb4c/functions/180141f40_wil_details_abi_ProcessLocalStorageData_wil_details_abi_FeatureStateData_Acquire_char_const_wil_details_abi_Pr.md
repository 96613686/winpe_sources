# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180141f40`
- end: `0x1801420b3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180142e3c`

## callees

- `0x180138d24`
- `0x18013ce80`
- `0x180141a30`
- `0x180141a50`
- `0x180141f40`
- `0x180143a30`
- `0x180144c50`
- `0x180145168`
- `0x180145544`
- `0x180145dc4`
- `0x180146028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180141fc3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180141fc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180141f78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180141f78`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      v12);
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
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
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
0x180141f40  mov     [rsp-8+arg_10], rbx
0x180141f45  mov     [rsp-8+arg_18], rdi
0x180141f4a  push    rbp
0x180141f4b  lea     rbp, [rsp-170h]
0x180141f53  sub     rsp, 270h
0x180141f5a  mov     rax, cs:__security_cookie
0x180141f61  xor     rax, rsp
0x180141f64  mov     [rbp+170h+var_10], rax
0x180141f6b  mov     rdi, rdx
0x180141f6e  mov     qword ptr [rdx], 0
0x180141f75  mov     rbx, rcx
0x180141f78  call    cs:__imp_GetCurrentProcessId
0x180141f7f  nop     dword ptr [rax+rax+00h]
0x180141f84  mov     [rsp+270h+var_248], rbx
0x180141f89  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180141f90  mov     r9d, eax
0x180141f93  mov     [rsp+270h+var_250], 130h; int
0x180141f9b  mov     edx, 104h; unsigned __int64
0x180141fa0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180141fa5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180141faa  mov     r9d, 1F0001h; dwDesiredAccess
0x180141fb0  mov     [rsp+270h+var_240], 0
0x180141fb9  xor     r8d, r8d; dwFlags
0x180141fbc  lea     rdx, [rsp+270h+Name]; lpName
0x180141fc1  xor     ecx, ecx; lpMutexAttributes
0x180141fc3  call    cs:__imp_CreateMutexExW
0x180141fca  nop     dword ptr [rax+rax+00h]
0x180141fcf  mov     rdx, rax
0x180141fd2  lea     rcx, [rsp+270h+var_240]
0x180141fd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180141fdc  cmp     [rsp+270h+var_240], 0
0x180141fe2  jnz     short loc_180141FED
0x180141fe4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180141fe9  mov     ebx, eax
0x180141feb  jmp     short loc_180142060
0x180141fed  lea     rdx, [rsp+270h+var_238]
0x180141ff2  lea     rcx, [rsp+270h+var_240]
0x180141ff7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180141ffc  lea     rdx, [rsp+270h+var_230]; void **
0x180142001  mov     [rsp+270h+var_230], 0
0x18014200a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18014200f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180142014  mov     ebx, eax
0x180142016  test    eax, eax
0x180142018  jns     short loc_180142041
0x18014201a  mov     edx, 12Eh; void *
0x18014201f  mov     rcx, [rbp+178h]; this
0x180142026  lea     r8, aWil; "wil"
0x18014202d  mov     r9d, eax; char *
0x180142030  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180142035  lea     rcx, [rsp+270h+var_238]
0x18014203a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014203f  jmp     short loc_180142060
0x180142041  mov     rcx, [rsp+270h+var_230]
0x180142046  test    rcx, rcx
0x180142049  jz      short loc_180142091
0x18014204b  mov     [rdi], rcx
0x18014204e  mov     eax, [rcx]
0x180142050  inc     eax
0x180142052  mov     [rcx], eax
0x180142054  lea     rcx, [rsp+270h+var_238]
0x180142059  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014205e  xor     ebx, ebx
0x180142060  lea     rcx, [rsp+270h+var_240]
0x180142065  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014206a  mov     eax, ebx
0x18014206c  mov     rcx, [rbp+170h+var_10]
0x180142073  xor     rcx, rsp; StackCookie
0x180142076  call    __security_check_cookie
0x18014207b  lea     r11, [rsp+270h+var_s0]
0x180142083  mov     rbx, [r11+20h]
0x180142087  mov     rdi, [r11+28h]
0x18014208b  mov     rsp, r11
0x18014208e  pop     rbp
0x18014208f  retn
0x180142091  mov     r8, rdi
0x180142094  lea     rdx, [rsp+270h+var_240]
0x180142099  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18014209e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1801420a3  mov     ebx, eax
0x1801420a5  test    eax, eax
0x1801420a7  jns     short loc_180142054
0x1801420a9  mov     edx, 137h
0x1801420ae  jmp     loc_18014201F
```
