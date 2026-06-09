# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800129b4`
- end: `0x180012b1a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012b90`

## callees

- `0x180001fb8`
- `0x1800023bc`
- `0x1800024c4`
- `0x18000261c`
- `0x180003244`
- `0x180003330`
- `0x180005b60`
- `0x18000bb6c`
- `0x18000d410`
- `0x18000fa10`
- `0x1800129b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012a31`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012a31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800129ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800129ec`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800129b4  mov     [rsp-8+arg_10], rbx
0x1800129b9  mov     [rsp-8+arg_18], rdi
0x1800129be  push    rbp
0x1800129bf  lea     rbp, [rsp-170h]
0x1800129c7  sub     rsp, 270h
0x1800129ce  mov     rax, cs:__security_cookie
0x1800129d5  xor     rax, rsp
0x1800129d8  mov     [rbp+170h+var_10], rax
0x1800129df  mov     rdi, rdx
0x1800129e2  mov     qword ptr [rdx], 0
0x1800129e9  mov     rbx, rcx
0x1800129ec  call    cs:__imp_GetCurrentProcessId
0x1800129f2  mov     [rsp+270h+var_248], rbx
0x1800129f7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800129fe  mov     r9d, eax
0x180012a01  mov     [rsp+270h+var_250], 130h; int
0x180012a09  mov     edx, 104h; unsigned __int64
0x180012a0e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012a13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012a18  mov     r9d, 1F0001h; dwDesiredAccess
0x180012a1e  mov     [rsp+270h+var_240], 0
0x180012a27  xor     r8d, r8d; dwFlags
0x180012a2a  lea     rdx, [rsp+270h+Name]; lpName
0x180012a2f  xor     ecx, ecx; lpMutexAttributes
0x180012a31  call    cs:__imp_CreateMutexExW
0x180012a37  mov     rdx, rax
0x180012a3a  lea     rcx, [rsp+270h+var_240]
0x180012a3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012a44  cmp     [rsp+270h+var_240], 0
0x180012a4a  jnz     short loc_180012A55
0x180012a4c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012a51  mov     ebx, eax
0x180012a53  jmp     short loc_180012AC8
0x180012a55  lea     rdx, [rsp+270h+var_238]
0x180012a5a  lea     rcx, [rsp+270h+var_240]
0x180012a5f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012a64  lea     rdx, [rsp+270h+var_230]; void **
0x180012a69  mov     [rsp+270h+var_230], 0
0x180012a72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180012a77  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180012a7c  mov     ebx, eax
0x180012a7e  test    eax, eax
0x180012a80  jns     short loc_180012AA9
0x180012a82  mov     edx, 12Eh; void *
0x180012a87  mov     rcx, [rbp+178h]; this
0x180012a8e  lea     r8, aWil; "wil"
0x180012a95  mov     r9d, eax; char *
0x180012a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a9d  lea     rcx, [rsp+270h+var_238]
0x180012aa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012aa7  jmp     short loc_180012AC8
0x180012aa9  mov     rcx, [rsp+270h+var_230]
0x180012aae  test    rcx, rcx
0x180012ab1  jz      short loc_180012AF8
0x180012ab3  mov     [rdi], rcx
0x180012ab6  mov     eax, [rcx]
0x180012ab8  inc     eax
0x180012aba  mov     [rcx], eax
0x180012abc  lea     rcx, [rsp+270h+var_238]
0x180012ac1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012ac6  xor     ebx, ebx
0x180012ac8  lea     rcx, [rsp+270h+var_240]
0x180012acd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012ad2  mov     eax, ebx
0x180012ad4  mov     rcx, [rbp+170h+var_10]
0x180012adb  xor     rcx, rsp; StackCookie
0x180012ade  call    __security_check_cookie
0x180012ae3  lea     r11, [rsp+270h+var_s0]
0x180012aeb  mov     rbx, [r11+20h]
0x180012aef  mov     rdi, [r11+28h]
0x180012af3  mov     rsp, r11
0x180012af6  pop     rbp
0x180012af7  retn
0x180012af8  mov     r8, rdi
0x180012afb  lea     rdx, [rsp+270h+var_240]
0x180012b00  lea     rcx, [rsp+270h+Name]
0x180012b05  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180012b0a  mov     ebx, eax
0x180012b0c  test    eax, eax
0x180012b0e  jns     short loc_180012ABC
0x180012b10  mov     edx, 137h
0x180012b15  jmp     loc_180012A87
```
