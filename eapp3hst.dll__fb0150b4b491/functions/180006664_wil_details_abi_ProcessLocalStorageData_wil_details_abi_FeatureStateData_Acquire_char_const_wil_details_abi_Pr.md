# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006664`
- end: `0x1800067c3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008420`

## callees

- `0x1800017a0`
- `0x1800034ec`
- `0x180005fcc`
- `0x180005fe8`
- `0x180006664`
- `0x180007d08`
- `0x180009148`
- `0x18000a76c`
- `0x18000b16c`
- `0x18000ba30`
- `0x18000bd1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000669c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000669c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800066e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800066e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180006664  mov     [rsp-8+arg_10], rbx
0x180006669  mov     [rsp-8+arg_18], rdi
0x18000666e  push    rbp
0x18000666f  lea     rbp, [rsp-170h]
0x180006677  sub     rsp, 270h
0x18000667e  mov     rax, cs:__security_cookie
0x180006685  xor     rax, rsp
0x180006688  mov     [rbp+170h+var_10], rax
0x18000668f  mov     rdi, rdx
0x180006692  mov     qword ptr [rdx], 0
0x180006699  mov     rbx, rcx
0x18000669c  call    cs:__imp_GetCurrentProcessId
0x1800066a2  mov     [rsp+270h+var_248], rbx
0x1800066a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800066ae  mov     r9d, eax
0x1800066b1  mov     [rsp+270h+var_250], 130h; int
0x1800066b9  mov     edx, 104h; unsigned __int64
0x1800066be  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800066c3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800066c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800066ce  mov     [rsp+270h+var_240], 0
0x1800066d7  xor     r8d, r8d; dwFlags
0x1800066da  lea     rdx, [rsp+270h+Name]; lpName
0x1800066df  xor     ecx, ecx; lpMutexAttributes
0x1800066e1  call    cs:__imp_CreateMutexExW
0x1800066e7  mov     rdx, rax
0x1800066ea  lea     rcx, [rsp+270h+var_240]
0x1800066ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800066f4  cmp     [rsp+270h+var_240], 0
0x1800066fa  jnz     short loc_180006705
0x1800066fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006701  mov     ebx, eax
0x180006703  jmp     short loc_180006771
0x180006705  lea     rdx, [rsp+270h+var_238]
0x18000670a  lea     rcx, [rsp+270h+var_240]
0x18000670f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006714  lea     rdx, [rsp+270h+var_230]; void **
0x180006719  mov     [rsp+270h+var_230], 0
0x180006722  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006727  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000672c  mov     ebx, eax
0x18000672e  test    eax, eax
0x180006730  jns     short loc_180006752
0x180006732  mov     edx, 12Eh; void *
0x180006737  mov     rcx, [rbp+178h]; this
0x18000673e  mov     r9d, eax; char *
0x180006741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006746  lea     rcx, [rsp+270h+var_238]
0x18000674b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006750  jmp     short loc_180006771
0x180006752  mov     rcx, [rsp+270h+var_230]
0x180006757  test    rcx, rcx
0x18000675a  jz      short loc_1800067A1
0x18000675c  mov     [rdi], rcx
0x18000675f  mov     eax, [rcx]
0x180006761  inc     eax
0x180006763  mov     [rcx], eax
0x180006765  lea     rcx, [rsp+270h+var_238]
0x18000676a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000676f  xor     ebx, ebx
0x180006771  lea     rcx, [rsp+270h+var_240]
0x180006776  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000677b  mov     eax, ebx
0x18000677d  mov     rcx, [rbp+170h+var_10]
0x180006784  xor     rcx, rsp; StackCookie
0x180006787  call    __security_check_cookie
0x18000678c  lea     r11, [rsp+270h+var_s0]
0x180006794  mov     rbx, [r11+20h]
0x180006798  mov     rdi, [r11+28h]
0x18000679c  mov     rsp, r11
0x18000679f  pop     rbp
0x1800067a0  retn
0x1800067a1  mov     r8, rdi
0x1800067a4  lea     rdx, [rsp+270h+var_240]
0x1800067a9  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800067ae  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800067b3  mov     ebx, eax
0x1800067b5  test    eax, eax
0x1800067b7  jns     short loc_180006765
0x1800067b9  mov     edx, 137h
0x1800067be  jmp     loc_180006737
```
