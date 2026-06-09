# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800167d4`
- end: `0x18001693a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180017568`

## callees

- `0x1800138ec`
- `0x1800139fc`
- `0x180013b94`
- `0x180014130`
- `0x1800161c4`
- `0x1800161e0`
- `0x1800167d4`
- `0x180018030`
- `0x180019e68`
- `0x18001a694`
- `0x18001a9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016851`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001680c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001680c`

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
0x1800167d4  mov     [rsp-8+arg_10], rbx
0x1800167d9  mov     [rsp-8+arg_18], rdi
0x1800167de  push    rbp
0x1800167df  lea     rbp, [rsp-170h]
0x1800167e7  sub     rsp, 270h
0x1800167ee  mov     rax, cs:__security_cookie
0x1800167f5  xor     rax, rsp
0x1800167f8  mov     [rbp+170h+var_10], rax
0x1800167ff  mov     rdi, rdx
0x180016802  mov     qword ptr [rdx], 0
0x180016809  mov     rbx, rcx
0x18001680c  call    cs:__imp_GetCurrentProcessId
0x180016812  mov     [rsp+270h+var_248], rbx
0x180016817  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001681e  mov     r9d, eax
0x180016821  mov     [rsp+270h+var_250], 130h; int
0x180016829  mov     edx, 104h; unsigned __int64
0x18001682e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016833  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016838  mov     r9d, 1F0001h; dwDesiredAccess
0x18001683e  mov     [rsp+270h+var_240], 0
0x180016847  xor     r8d, r8d; dwFlags
0x18001684a  lea     rdx, [rsp+270h+Name]; lpName
0x18001684f  xor     ecx, ecx; lpMutexAttributes
0x180016851  call    cs:__imp_CreateMutexExW
0x180016857  mov     rdx, rax
0x18001685a  lea     rcx, [rsp+270h+var_240]
0x18001685f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016864  cmp     [rsp+270h+var_240], 0
0x18001686a  jnz     short loc_180016875
0x18001686c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016871  mov     ebx, eax
0x180016873  jmp     short loc_1800168E8
0x180016875  lea     rdx, [rsp+270h+var_238]
0x18001687a  lea     rcx, [rsp+270h+var_240]
0x18001687f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180016884  lea     rdx, [rsp+270h+var_230]; void **
0x180016889  mov     [rsp+270h+var_230], 0
0x180016892  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180016897  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18001689c  mov     ebx, eax
0x18001689e  test    eax, eax
0x1800168a0  jns     short loc_1800168C9
0x1800168a2  mov     edx, 12Eh; void *
0x1800168a7  mov     rcx, [rbp+178h]; this
0x1800168ae  lea     r8, aWil; "wil"
0x1800168b5  mov     r9d, eax; char *
0x1800168b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168bd  lea     rcx, [rsp+270h+var_238]
0x1800168c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168c7  jmp     short loc_1800168E8
0x1800168c9  mov     rcx, [rsp+270h+var_230]
0x1800168ce  test    rcx, rcx
0x1800168d1  jz      short loc_180016918
0x1800168d3  mov     [rdi], rcx
0x1800168d6  mov     eax, [rcx]
0x1800168d8  inc     eax
0x1800168da  mov     [rcx], eax
0x1800168dc  lea     rcx, [rsp+270h+var_238]
0x1800168e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168e6  xor     ebx, ebx
0x1800168e8  lea     rcx, [rsp+270h+var_240]
0x1800168ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168f2  mov     eax, ebx
0x1800168f4  mov     rcx, [rbp+170h+var_10]
0x1800168fb  xor     rcx, rsp; StackCookie
0x1800168fe  call    __security_check_cookie
0x180016903  lea     r11, [rsp+270h+var_s0]
0x18001690b  mov     rbx, [r11+20h]
0x18001690f  mov     rdi, [r11+28h]
0x180016913  mov     rsp, r11
0x180016916  pop     rbp
0x180016917  retn
0x180016918  mov     r8, rdi
0x18001691b  lea     rdx, [rsp+270h+var_240]
0x180016920  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180016925  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001692a  mov     ebx, eax
0x18001692c  test    eax, eax
0x18001692e  jns     short loc_1800168DC
0x180016930  mov     edx, 137h
0x180016935  jmp     loc_1800168A7
```
