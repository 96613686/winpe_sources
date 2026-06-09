# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800065b4`
- end: `0x18000671a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000741c`

## callees

- `0x180003220`
- `0x180005fcc`
- `0x180005fe8`
- `0x1800065b4`
- `0x180007218`
- `0x180008134`
- `0x18000949c`
- `0x180009c28`
- `0x18000a09c`
- `0x18000aa84`
- `0x18000adb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006631`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065ec`

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
0x1800065b4  mov     [rsp-8+arg_10], rbx
0x1800065b9  mov     [rsp-8+arg_18], rdi
0x1800065be  push    rbp
0x1800065bf  lea     rbp, [rsp-170h]
0x1800065c7  sub     rsp, 270h
0x1800065ce  mov     rax, cs:__security_cookie
0x1800065d5  xor     rax, rsp
0x1800065d8  mov     [rbp+170h+var_10], rax
0x1800065df  mov     rdi, rdx
0x1800065e2  mov     qword ptr [rdx], 0
0x1800065e9  mov     rbx, rcx
0x1800065ec  call    cs:__imp_GetCurrentProcessId
0x1800065f2  mov     [rsp+270h+var_248], rbx
0x1800065f7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800065fe  mov     r9d, eax
0x180006601  mov     [rsp+270h+var_250], 130h; int
0x180006609  mov     edx, 104h; unsigned __int64
0x18000660e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006613  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006618  mov     r9d, 1F0001h; dwDesiredAccess
0x18000661e  mov     [rsp+270h+var_240], 0
0x180006627  xor     r8d, r8d; dwFlags
0x18000662a  lea     rdx, [rsp+270h+Name]; lpName
0x18000662f  xor     ecx, ecx; lpMutexAttributes
0x180006631  call    cs:__imp_CreateMutexExW
0x180006637  mov     rdx, rax
0x18000663a  lea     rcx, [rsp+270h+var_240]
0x18000663f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006644  cmp     [rsp+270h+var_240], 0
0x18000664a  jnz     short loc_180006655
0x18000664c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006651  mov     ebx, eax
0x180006653  jmp     short loc_1800066C8
0x180006655  lea     rdx, [rsp+270h+var_238]
0x18000665a  lea     rcx, [rsp+270h+var_240]
0x18000665f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006664  lea     rdx, [rsp+270h+var_230]; void **
0x180006669  mov     [rsp+270h+var_230], 0
0x180006672  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006677  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000667c  mov     ebx, eax
0x18000667e  test    eax, eax
0x180006680  jns     short loc_1800066A9
0x180006682  mov     edx, 12Eh; void *
0x180006687  mov     rcx, [rbp+178h]; this
0x18000668e  lea     r8, aWil; "wil"
0x180006695  mov     r9d, eax; char *
0x180006698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000669d  lea     rcx, [rsp+270h+var_238]
0x1800066a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066a7  jmp     short loc_1800066C8
0x1800066a9  mov     rcx, [rsp+270h+var_230]
0x1800066ae  test    rcx, rcx
0x1800066b1  jz      short loc_1800066F8
0x1800066b3  mov     [rdi], rcx
0x1800066b6  mov     eax, [rcx]
0x1800066b8  inc     eax
0x1800066ba  mov     [rcx], eax
0x1800066bc  lea     rcx, [rsp+270h+var_238]
0x1800066c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066c6  xor     ebx, ebx
0x1800066c8  lea     rcx, [rsp+270h+var_240]
0x1800066cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066d2  mov     eax, ebx
0x1800066d4  mov     rcx, [rbp+170h+var_10]
0x1800066db  xor     rcx, rsp; StackCookie
0x1800066de  call    __security_check_cookie
0x1800066e3  lea     r11, [rsp+270h+var_s0]
0x1800066eb  mov     rbx, [r11+20h]
0x1800066ef  mov     rdi, [r11+28h]
0x1800066f3  mov     rsp, r11
0x1800066f6  pop     rbp
0x1800066f7  retn
0x1800066f8  mov     r8, rdi
0x1800066fb  lea     rdx, [rsp+270h+var_240]
0x180006700  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006705  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000670a  mov     ebx, eax
0x18000670c  test    eax, eax
0x18000670e  jns     short loc_1800066BC
0x180006710  mov     edx, 137h
0x180006715  jmp     loc_180006687
```
