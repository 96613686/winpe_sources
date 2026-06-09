# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007c48`
- end: `0x140007dae`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140008e88`

## callees

- `0x14000492c`
- `0x140004a94`
- `0x140004ae0`
- `0x140005530`
- `0x1400076d0`
- `0x1400076ec`
- `0x140007c48`
- `0x14000ad9c`
- `0x14000afdc`
- `0x14000b8f4`
- `0x14000bb94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007cc5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007c80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007c80`

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
0x140007c48  mov     [rsp-8+arg_10], rbx
0x140007c4d  mov     [rsp-8+arg_18], rdi
0x140007c52  push    rbp
0x140007c53  lea     rbp, [rsp-170h]
0x140007c5b  sub     rsp, 270h
0x140007c62  mov     rax, cs:__security_cookie
0x140007c69  xor     rax, rsp
0x140007c6c  mov     [rbp+170h+var_10], rax
0x140007c73  mov     rdi, rdx
0x140007c76  mov     qword ptr [rdx], 0
0x140007c7d  mov     rbx, rcx
0x140007c80  call    cs:__imp_GetCurrentProcessId
0x140007c86  mov     [rsp+270h+var_248], rbx
0x140007c8b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007c92  mov     r9d, eax
0x140007c95  mov     [rsp+270h+var_250], 130h; int
0x140007c9d  mov     edx, 104h; unsigned __int64
0x140007ca2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007ca7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007cac  mov     r9d, 1F0001h; dwDesiredAccess
0x140007cb2  mov     [rsp+270h+var_240], 0
0x140007cbb  xor     r8d, r8d; dwFlags
0x140007cbe  lea     rdx, [rsp+270h+Name]; lpName
0x140007cc3  xor     ecx, ecx; lpMutexAttributes
0x140007cc5  call    cs:__imp_CreateMutexExW
0x140007ccb  mov     rdx, rax
0x140007cce  lea     rcx, [rsp+270h+var_240]
0x140007cd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140007cd8  cmp     [rsp+270h+var_240], 0
0x140007cde  jnz     short loc_140007CE9
0x140007ce0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007ce5  mov     ebx, eax
0x140007ce7  jmp     short loc_140007D5C
0x140007ce9  lea     rdx, [rsp+270h+var_238]
0x140007cee  lea     rcx, [rsp+270h+var_240]
0x140007cf3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140007cf8  lea     rdx, [rsp+270h+var_230]; void **
0x140007cfd  mov     [rsp+270h+var_230], 0
0x140007d06  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007d0b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140007d10  mov     ebx, eax
0x140007d12  test    eax, eax
0x140007d14  jns     short loc_140007D3D
0x140007d16  mov     edx, 12Eh; void *
0x140007d1b  mov     rcx, [rbp+178h]; this
0x140007d22  lea     r8, aWil; "wil"
0x140007d29  mov     r9d, eax; char *
0x140007d2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007d31  lea     rcx, [rsp+270h+var_238]
0x140007d36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007d3b  jmp     short loc_140007D5C
0x140007d3d  mov     rcx, [rsp+270h+var_230]
0x140007d42  test    rcx, rcx
0x140007d45  jz      short loc_140007D8C
0x140007d47  mov     [rdi], rcx
0x140007d4a  mov     eax, [rcx]
0x140007d4c  inc     eax
0x140007d4e  mov     [rcx], eax
0x140007d50  lea     rcx, [rsp+270h+var_238]
0x140007d55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007d5a  xor     ebx, ebx
0x140007d5c  lea     rcx, [rsp+270h+var_240]
0x140007d61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007d66  mov     eax, ebx
0x140007d68  mov     rcx, [rbp+170h+var_10]
0x140007d6f  xor     rcx, rsp; StackCookie
0x140007d72  call    __security_check_cookie
0x140007d77  lea     r11, [rsp+270h+var_s0]
0x140007d7f  mov     rbx, [r11+20h]
0x140007d83  mov     rdi, [r11+28h]
0x140007d87  mov     rsp, r11
0x140007d8a  pop     rbp
0x140007d8b  retn
0x140007d8c  mov     r8, rdi
0x140007d8f  lea     rdx, [rsp+270h+var_240]
0x140007d94  lea     rcx, [rsp+270h+Name]
0x140007d99  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140007d9e  mov     ebx, eax
0x140007da0  test    eax, eax
0x140007da2  jns     short loc_140007D50
0x140007da4  mov     edx, 137h
0x140007da9  jmp     loc_140007D1B
```
