# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b058`
- end: `0x18000b1be`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000db8c`

## callees

- `0x180005b8c`
- `0x180006270`
- `0x180008a74`
- `0x18000a610`
- `0x18000a62c`
- `0x18000b058`
- `0x18000e7f4`
- `0x180011374`
- `0x180011cfc`
- `0x180012b34`
- `0x1800130f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b090`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b0d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b0d5`

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
0x18000b058  mov     [rsp-8+arg_10], rbx
0x18000b05d  mov     [rsp-8+arg_18], rdi
0x18000b062  push    rbp
0x18000b063  lea     rbp, [rsp-170h]
0x18000b06b  sub     rsp, 270h
0x18000b072  mov     rax, cs:__security_cookie
0x18000b079  xor     rax, rsp
0x18000b07c  mov     [rbp+170h+var_10], rax
0x18000b083  mov     rdi, rdx
0x18000b086  mov     qword ptr [rdx], 0
0x18000b08d  mov     rbx, rcx
0x18000b090  call    cs:__imp_GetCurrentProcessId
0x18000b096  mov     [rsp+270h+var_248], rbx
0x18000b09b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b0a2  mov     r9d, eax
0x18000b0a5  mov     [rsp+270h+var_250], 130h; int
0x18000b0ad  mov     edx, 104h; unsigned __int64
0x18000b0b2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b0b7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000b0bc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b0c2  mov     [rsp+270h+var_240], 0
0x18000b0cb  xor     r8d, r8d; dwFlags
0x18000b0ce  lea     rdx, [rsp+270h+Name]; lpName
0x18000b0d3  xor     ecx, ecx; lpMutexAttributes
0x18000b0d5  call    cs:__imp_CreateMutexExW
0x18000b0db  mov     rdx, rax
0x18000b0de  lea     rcx, [rsp+270h+var_240]
0x18000b0e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b0e8  cmp     [rsp+270h+var_240], 0
0x18000b0ee  jnz     short loc_18000B0F9
0x18000b0f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b0f5  mov     ebx, eax
0x18000b0f7  jmp     short loc_18000B16C
0x18000b0f9  lea     rdx, [rsp+270h+var_238]
0x18000b0fe  lea     rcx, [rsp+270h+var_240]
0x18000b103  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b108  lea     rdx, [rsp+270h+var_230]; void **
0x18000b10d  mov     [rsp+270h+var_230], 0
0x18000b116  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b11b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000b120  mov     ebx, eax
0x18000b122  test    eax, eax
0x18000b124  jns     short loc_18000B14D
0x18000b126  mov     edx, 12Eh; void *
0x18000b12b  mov     rcx, [rbp+178h]; this
0x18000b132  lea     r8, aWil; "wil"
0x18000b139  mov     r9d, eax; char *
0x18000b13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b141  lea     rcx, [rsp+270h+var_238]
0x18000b146  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b14b  jmp     short loc_18000B16C
0x18000b14d  mov     rcx, [rsp+270h+var_230]
0x18000b152  test    rcx, rcx
0x18000b155  jz      short loc_18000B19C
0x18000b157  mov     [rdi], rcx
0x18000b15a  mov     eax, [rcx]
0x18000b15c  inc     eax
0x18000b15e  mov     [rcx], eax
0x18000b160  lea     rcx, [rsp+270h+var_238]
0x18000b165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b16a  xor     ebx, ebx
0x18000b16c  lea     rcx, [rsp+270h+var_240]
0x18000b171  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b176  mov     eax, ebx
0x18000b178  mov     rcx, [rbp+170h+var_10]
0x18000b17f  xor     rcx, rsp; StackCookie
0x18000b182  call    __security_check_cookie
0x18000b187  lea     r11, [rsp+270h+var_s0]
0x18000b18f  mov     rbx, [r11+20h]
0x18000b193  mov     rdi, [r11+28h]
0x18000b197  mov     rsp, r11
0x18000b19a  pop     rbp
0x18000b19b  retn
0x18000b19c  mov     r8, rdi
0x18000b19f  lea     rdx, [rsp+270h+var_240]
0x18000b1a4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b1a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b1ae  mov     ebx, eax
0x18000b1b0  test    eax, eax
0x18000b1b2  jns     short loc_18000B160
0x18000b1b4  mov     edx, 137h
0x18000b1b9  jmp     loc_18000B12B
```
