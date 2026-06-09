# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180044574`
- end: `0x1800446da`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180044cc0`

## callees

- `0x18003a598`
- `0x18003bf28`
- `0x180042410`
- `0x180044224`
- `0x180044240`
- `0x180044574`
- `0x1800453b4`
- `0x180045bc4`
- `0x180045f28`
- `0x1800465c4`
- `0x18004667c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800445f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800445f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800445ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800445ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180044574  mov     [rsp-8+arg_10], rbx
0x180044579  mov     [rsp-8+arg_18], rdi
0x18004457e  push    rbp
0x18004457f  lea     rbp, [rsp-170h]
0x180044587  sub     rsp, 270h
0x18004458e  mov     rax, cs:__security_cookie
0x180044595  xor     rax, rsp
0x180044598  mov     [rbp+170h+var_10], rax
0x18004459f  mov     rdi, rdx
0x1800445a2  mov     qword ptr [rdx], 0
0x1800445a9  mov     rbx, rcx
0x1800445ac  call    cs:__imp_GetCurrentProcessId
0x1800445b2  mov     [rsp+270h+var_248], rbx
0x1800445b7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800445be  mov     r9d, eax
0x1800445c1  mov     [rsp+270h+var_250], 130h; int
0x1800445c9  mov     edx, 104h; unsigned __int64
0x1800445ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800445d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800445d8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800445de  mov     [rsp+270h+var_240], 0
0x1800445e7  xor     r8d, r8d; dwFlags
0x1800445ea  lea     rdx, [rsp+270h+Name]; lpName
0x1800445ef  xor     ecx, ecx; lpMutexAttributes
0x1800445f1  call    cs:__imp_CreateMutexExW
0x1800445f7  mov     rdx, rax
0x1800445fa  lea     rcx, [rsp+270h+var_240]
0x1800445ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180044604  cmp     [rsp+270h+var_240], 0
0x18004460a  jnz     short loc_180044615
0x18004460c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180044611  mov     ebx, eax
0x180044613  jmp     short loc_180044688
0x180044615  lea     rdx, [rsp+270h+var_238]
0x18004461a  lea     rcx, [rsp+270h+var_240]
0x18004461f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180044624  lea     rdx, [rsp+270h+var_230]; void **
0x180044629  mov     [rsp+270h+var_230], 0
0x180044632  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180044637  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004463c  mov     ebx, eax
0x18004463e  test    eax, eax
0x180044640  jns     short loc_180044669
0x180044642  mov     edx, 12Eh; void *
0x180044647  mov     rcx, [rbp+178h]; this
0x18004464e  lea     r8, aWil; "wil"
0x180044655  mov     r9d, eax; char *
0x180044658  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004465d  lea     rcx, [rsp+270h+var_238]
0x180044662  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044667  jmp     short loc_180044688
0x180044669  mov     rcx, [rsp+270h+var_230]
0x18004466e  test    rcx, rcx
0x180044671  jz      short loc_1800446B8
0x180044673  mov     [rdi], rcx
0x180044676  mov     eax, [rcx]
0x180044678  inc     eax
0x18004467a  mov     [rcx], eax
0x18004467c  lea     rcx, [rsp+270h+var_238]
0x180044681  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044686  xor     ebx, ebx
0x180044688  lea     rcx, [rsp+270h+var_240]
0x18004468d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044692  mov     eax, ebx
0x180044694  mov     rcx, [rbp+170h+var_10]
0x18004469b  xor     rcx, rsp; StackCookie
0x18004469e  call    __security_check_cookie
0x1800446a3  lea     r11, [rsp+270h+var_s0]
0x1800446ab  mov     rbx, [r11+20h]
0x1800446af  mov     rdi, [r11+28h]
0x1800446b3  mov     rsp, r11
0x1800446b6  pop     rbp
0x1800446b7  retn
0x1800446b8  mov     r8, rdi
0x1800446bb  lea     rdx, [rsp+270h+var_240]
0x1800446c0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800446c5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800446ca  mov     ebx, eax
0x1800446cc  test    eax, eax
0x1800446ce  jns     short loc_18004467C
0x1800446d0  mov     edx, 137h
0x1800446d5  jmp     loc_180044647
```
