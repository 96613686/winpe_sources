# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008248`
- end: `0x1800083ae`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009034`

## callees

- `0x180001640`
- `0x180007ca0`
- `0x180007cbc`
- `0x180008248`
- `0x180008e78`
- `0x180009d34`
- `0x18000b18c`
- `0x18000b8c8`
- `0x18000bcf8`
- `0x18000c5c4`
- `0x18000ca8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008280`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008280`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800082c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800082c5`

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
0x180008248  mov     [rsp-8+arg_10], rbx
0x18000824d  mov     [rsp-8+arg_18], rdi
0x180008252  push    rbp
0x180008253  lea     rbp, [rsp-170h]
0x18000825b  sub     rsp, 270h
0x180008262  mov     rax, cs:__security_cookie
0x180008269  xor     rax, rsp
0x18000826c  mov     [rbp+170h+var_10], rax
0x180008273  mov     rdi, rdx
0x180008276  mov     qword ptr [rdx], 0
0x18000827d  mov     rbx, rcx
0x180008280  call    cs:__imp_GetCurrentProcessId
0x180008286  mov     [rsp+270h+var_248], rbx
0x18000828b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008292  mov     r9d, eax
0x180008295  mov     [rsp+270h+var_250], 130h; int
0x18000829d  mov     edx, 104h; unsigned __int64
0x1800082a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800082a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800082ac  mov     r9d, 1F0001h; dwDesiredAccess
0x1800082b2  mov     [rsp+270h+var_240], 0
0x1800082bb  xor     r8d, r8d; dwFlags
0x1800082be  lea     rdx, [rsp+270h+Name]; lpName
0x1800082c3  xor     ecx, ecx; lpMutexAttributes
0x1800082c5  call    cs:__imp_CreateMutexExW
0x1800082cb  mov     rdx, rax
0x1800082ce  lea     rcx, [rsp+270h+var_240]
0x1800082d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800082d8  cmp     [rsp+270h+var_240], 0
0x1800082de  jnz     short loc_1800082E9
0x1800082e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800082e5  mov     ebx, eax
0x1800082e7  jmp     short loc_18000835C
0x1800082e9  lea     rdx, [rsp+270h+var_238]
0x1800082ee  lea     rcx, [rsp+270h+var_240]
0x1800082f3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800082f8  lea     rdx, [rsp+270h+var_230]; void **
0x1800082fd  mov     [rsp+270h+var_230], 0
0x180008306  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000830b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008310  mov     ebx, eax
0x180008312  test    eax, eax
0x180008314  jns     short loc_18000833D
0x180008316  mov     edx, 12Eh; void *
0x18000831b  mov     rcx, [rbp+178h]; this
0x180008322  lea     r8, aWil; "wil"
0x180008329  mov     r9d, eax; char *
0x18000832c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008331  lea     rcx, [rsp+270h+var_238]
0x180008336  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000833b  jmp     short loc_18000835C
0x18000833d  mov     rcx, [rsp+270h+var_230]
0x180008342  test    rcx, rcx
0x180008345  jz      short loc_18000838C
0x180008347  mov     [rdi], rcx
0x18000834a  mov     eax, [rcx]
0x18000834c  inc     eax
0x18000834e  mov     [rcx], eax
0x180008350  lea     rcx, [rsp+270h+var_238]
0x180008355  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000835a  xor     ebx, ebx
0x18000835c  lea     rcx, [rsp+270h+var_240]
0x180008361  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008366  mov     eax, ebx
0x180008368  mov     rcx, [rbp+170h+var_10]
0x18000836f  xor     rcx, rsp; StackCookie
0x180008372  call    __security_check_cookie
0x180008377  lea     r11, [rsp+270h+var_s0]
0x18000837f  mov     rbx, [r11+20h]
0x180008383  mov     rdi, [r11+28h]
0x180008387  mov     rsp, r11
0x18000838a  pop     rbp
0x18000838b  retn
0x18000838c  mov     r8, rdi
0x18000838f  lea     rdx, [rsp+270h+var_240]
0x180008394  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008399  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000839e  mov     ebx, eax
0x1800083a0  test    eax, eax
0x1800083a2  jns     short loc_180008350
0x1800083a4  mov     edx, 137h
0x1800083a9  jmp     loc_18000831B
```
