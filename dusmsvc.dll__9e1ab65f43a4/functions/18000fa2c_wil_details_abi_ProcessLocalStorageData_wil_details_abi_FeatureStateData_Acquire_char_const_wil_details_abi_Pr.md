# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000fa2c`
- end: `0x18000fb9b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010450`

## callees

- `0x180007c90`
- `0x18000aa54`
- `0x18000aa70`
- `0x18000b438`
- `0x18000c464`
- `0x18000ca44`
- `0x18000cc08`
- `0x18000d004`
- `0x18000d114`
- `0x18000fa2c`
- `0x1800109a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000faa9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000faa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fa64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fa64`

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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18000fa2c  mov     [rsp-8+arg_10], rbx
0x18000fa31  mov     [rsp-8+arg_18], rdi
0x18000fa36  push    rbp
0x18000fa37  lea     rbp, [rsp-170h]
0x18000fa3f  sub     rsp, 270h
0x18000fa46  mov     rax, cs:__security_cookie
0x18000fa4d  xor     rax, rsp
0x18000fa50  mov     [rbp+170h+var_10], rax
0x18000fa57  mov     rdi, rdx
0x18000fa5a  mov     qword ptr [rdx], 0
0x18000fa61  mov     rbx, rcx
0x18000fa64  call    cs:__imp_GetCurrentProcessId
0x18000fa6a  mov     [rsp+270h+var_248], rbx
0x18000fa6f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000fa76  mov     r9d, eax
0x18000fa79  mov     [rsp+270h+var_250], 130h; int
0x18000fa81  mov     edx, 104h; unsigned __int64
0x18000fa86  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000fa8b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000fa90  mov     r9d, 1F0001h; dwDesiredAccess
0x18000fa96  mov     [rsp+270h+var_240], 0
0x18000fa9f  xor     r8d, r8d; dwFlags
0x18000faa2  lea     rdx, [rsp+270h+Name]; lpName
0x18000faa7  xor     ecx, ecx; lpMutexAttributes
0x18000faa9  call    cs:__imp_CreateMutexExW
0x18000faaf  mov     rdx, rax
0x18000fab2  lea     rcx, [rsp+270h+var_240]
0x18000fab7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000fabc  cmp     [rsp+270h+var_240], 0
0x18000fac2  jnz     short loc_18000FACD
0x18000fac4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000fac9  mov     ebx, eax
0x18000facb  jmp     short loc_18000FB49
0x18000facd  lea     rdx, [rsp+270h+var_238]
0x18000fad2  mov     [rsp+270h+var_238], 0
0x18000fadb  lea     rcx, [rsp+270h+var_240]
0x18000fae0  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000fae5  lea     rdx, [rsp+270h+var_230]; void **
0x18000faea  mov     [rsp+270h+var_230], 0
0x18000faf3  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000faf8  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000fafd  mov     ebx, eax
0x18000faff  test    eax, eax
0x18000fb01  jns     short loc_18000FB2A
0x18000fb03  mov     edx, 12Eh; void *
0x18000fb08  mov     rcx, [rbp+178h]; this
0x18000fb0f  lea     r8, aWil; "wil"
0x18000fb16  mov     r9d, eax; char *
0x18000fb19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb1e  lea     rcx, [rsp+270h+var_238]
0x18000fb23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fb28  jmp     short loc_18000FB49
0x18000fb2a  mov     rcx, [rsp+270h+var_230]
0x18000fb2f  test    rcx, rcx
0x18000fb32  jz      short loc_18000FB79
0x18000fb34  mov     [rdi], rcx
0x18000fb37  mov     eax, [rcx]
0x18000fb39  inc     eax
0x18000fb3b  mov     [rcx], eax
0x18000fb3d  lea     rcx, [rsp+270h+var_238]
0x18000fb42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fb47  xor     ebx, ebx
0x18000fb49  lea     rcx, [rsp+270h+var_240]
0x18000fb4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fb53  mov     eax, ebx
0x18000fb55  mov     rcx, [rbp+170h+var_10]
0x18000fb5c  xor     rcx, rsp; StackCookie
0x18000fb5f  call    __security_check_cookie
0x18000fb64  lea     r11, [rsp+270h+var_s0]
0x18000fb6c  mov     rbx, [r11+20h]
0x18000fb70  mov     rdi, [r11+28h]
0x18000fb74  mov     rsp, r11
0x18000fb77  pop     rbp
0x18000fb78  retn
0x18000fb79  mov     r8, rdi
0x18000fb7c  lea     rdx, [rsp+270h+var_240]
0x18000fb81  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000fb86  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000fb8b  mov     ebx, eax
0x18000fb8d  test    eax, eax
0x18000fb8f  jns     short loc_18000FB3D
0x18000fb91  mov     edx, 137h
0x18000fb96  jmp     loc_18000FB08
```
