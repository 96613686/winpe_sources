# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b084`
- end: `0x18000b1f0`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000bbac`

## callees

- `0x180002af0`
- `0x180005024`
- `0x180005044`
- `0x180007ad0`
- `0x180008e34`
- `0x1800094d0`
- `0x1800095b8`
- `0x180009b3c`
- `0x180009c84`
- `0x18000b084`
- `0x18000bff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b0bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b0bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b107`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b107`

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
0x18000b084  mov     [rsp-8+arg_10], rbx
0x18000b089  mov     [rsp-8+arg_18], rdi
0x18000b08e  push    rbp
0x18000b08f  lea     rbp, [rsp-170h]
0x18000b097  sub     rsp, 270h
0x18000b09e  mov     rax, cs:__security_cookie
0x18000b0a5  xor     rax, rsp
0x18000b0a8  mov     [rbp+170h+var_10], rax
0x18000b0af  mov     rdi, rdx
0x18000b0b2  mov     qword ptr [rdx], 0
0x18000b0b9  mov     rbx, rcx
0x18000b0bc  call    cs:__imp_GetCurrentProcessId
0x18000b0c3  nop     dword ptr [rax+rax+00h]
0x18000b0c8  mov     [rsp+270h+var_248], rbx
0x18000b0cd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b0d4  mov     r9d, eax
0x18000b0d7  mov     [rsp+270h+var_250], 130h; int
0x18000b0df  mov     edx, 104h; unsigned __int64
0x18000b0e4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b0e9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000b0ee  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b0f4  mov     [rsp+270h+var_240], 0
0x18000b0fd  xor     r8d, r8d; dwFlags
0x18000b100  lea     rdx, [rsp+270h+Name]; lpName
0x18000b105  xor     ecx, ecx; lpMutexAttributes
0x18000b107  call    cs:__imp_CreateMutexExW
0x18000b10e  nop     dword ptr [rax+rax+00h]
0x18000b113  mov     rdx, rax
0x18000b116  lea     rcx, [rsp+270h+var_240]
0x18000b11b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b120  cmp     [rsp+270h+var_240], 0
0x18000b126  jnz     short loc_18000B131
0x18000b128  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b12d  mov     ebx, eax
0x18000b12f  jmp     short loc_18000B19D
0x18000b131  lea     rdx, [rsp+270h+var_238]
0x18000b136  lea     rcx, [rsp+270h+var_240]
0x18000b13b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000b140  lea     rdx, [rsp+270h+var_230]; void **
0x18000b145  mov     [rsp+270h+var_230], 0
0x18000b14e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b153  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000b158  mov     ebx, eax
0x18000b15a  test    eax, eax
0x18000b15c  jns     short loc_18000B17E
0x18000b15e  mov     edx, 12Eh; void *
0x18000b163  mov     rcx, [rbp+178h]; this
0x18000b16a  mov     r9d, eax; char *
0x18000b16d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b172  lea     rcx, [rsp+270h+var_238]
0x18000b177  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b17c  jmp     short loc_18000B19D
0x18000b17e  mov     rcx, [rsp+270h+var_230]
0x18000b183  test    rcx, rcx
0x18000b186  jz      short loc_18000B1CE
0x18000b188  mov     [rdi], rcx
0x18000b18b  mov     eax, [rcx]
0x18000b18d  inc     eax
0x18000b18f  mov     [rcx], eax
0x18000b191  lea     rcx, [rsp+270h+var_238]
0x18000b196  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b19b  xor     ebx, ebx
0x18000b19d  lea     rcx, [rsp+270h+var_240]
0x18000b1a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b1a7  mov     eax, ebx
0x18000b1a9  mov     rcx, [rbp+170h+var_10]
0x18000b1b0  xor     rcx, rsp; StackCookie
0x18000b1b3  call    __security_check_cookie
0x18000b1b8  lea     r11, [rsp+270h+var_s0]
0x18000b1c0  mov     rbx, [r11+20h]
0x18000b1c4  mov     rdi, [r11+28h]
0x18000b1c8  mov     rsp, r11
0x18000b1cb  pop     rbp
0x18000b1cc  retn
0x18000b1ce  mov     r8, rdi
0x18000b1d1  lea     rdx, [rsp+270h+var_240]
0x18000b1d6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b1db  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b1e0  mov     ebx, eax
0x18000b1e2  test    eax, eax
0x18000b1e4  jns     short loc_18000B191
0x18000b1e6  mov     edx, 137h
0x18000b1eb  jmp     loc_18000B163
```
