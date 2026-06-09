# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003a94c`
- end: `0x18003aabb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003bf94`

## callees

- `0x180037378`
- `0x18003a668`
- `0x18003a688`
- `0x18003a94c`
- `0x18003ca24`
- `0x18003dadc`
- `0x18003e25c`
- `0x18003e3e8`
- `0x18003edd0`
- `0x18003eed4`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a984`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003a9cf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003a9cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18003a94c  mov     [rsp-8+arg_10], rbx
0x18003a951  mov     [rsp-8+arg_18], rdi
0x18003a956  push    rbp
0x18003a957  lea     rbp, [rsp-170h]
0x18003a95f  sub     rsp, 270h
0x18003a966  mov     rax, cs:__security_cookie
0x18003a96d  xor     rax, rsp
0x18003a970  mov     [rbp+170h+var_10], rax
0x18003a977  mov     rdi, rdx
0x18003a97a  mov     rbx, rcx
0x18003a97d  mov     qword ptr [rdx], 0
0x18003a984  call    cs:__imp_GetCurrentProcessId
0x18003a98b  nop     dword ptr [rax+rax+00h]
0x18003a990  mov     r9d, eax
0x18003a993  mov     [rsp+270h+var_248], rbx
0x18003a998  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003a9a0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003a9a7  mov     edx, 104h; unsigned __int64
0x18003a9ac  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003a9b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a9b6  mov     [rsp+270h+var_240], 0
0x18003a9bf  mov     r9d, 1F0001h; dwDesiredAccess
0x18003a9c5  xor     r8d, r8d; dwFlags
0x18003a9c8  lea     rdx, [rsp+270h+Name]; lpName
0x18003a9cd  xor     ecx, ecx; lpMutexAttributes
0x18003a9cf  call    cs:__imp_CreateMutexExW
0x18003a9d6  nop     dword ptr [rax+rax+00h]
0x18003a9db  mov     rdx, rax
0x18003a9de  lea     rcx, [rsp+270h+var_240]
0x18003a9e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003a9e8  cmp     [rsp+270h+var_240], 0
0x18003a9ee  jnz     short loc_18003A9F9
0x18003a9f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003a9f5  mov     ebx, eax
0x18003a9f7  jmp     short loc_18003AA67
0x18003a9f9  lea     rdx, [rsp+270h+var_238]
0x18003a9fe  lea     rcx, [rsp+270h+var_240]
0x18003aa03  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003aa08  nop
0x18003aa09  mov     [rsp+270h+var_230], 0
0x18003aa12  lea     rdx, [rsp+270h+var_230]; void **
0x18003aa17  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003aa1c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003aa21  mov     ebx, eax
0x18003aa23  test    eax, eax
0x18003aa25  jns     short loc_18003AA48
0x18003aa27  mov     edx, 12Eh; void *
0x18003aa2c  mov     r9d, eax; char *
0x18003aa2f  mov     rcx, [rbp+178h]; this
0x18003aa36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa3b  nop
0x18003aa3c  lea     rcx, [rsp+270h+var_238]
0x18003aa41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003aa46  jmp     short loc_18003AA67
0x18003aa48  mov     rcx, [rsp+270h+var_230]
0x18003aa4d  test    rcx, rcx
0x18003aa50  jz      short loc_18003AA98
0x18003aa52  mov     [rdi], rcx
0x18003aa55  mov     eax, [rcx]
0x18003aa57  inc     eax
0x18003aa59  mov     [rcx], eax
0x18003aa5b  lea     rcx, [rsp+270h+var_238]
0x18003aa60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003aa65  xor     ebx, ebx
0x18003aa67  lea     rcx, [rsp+270h+var_240]
0x18003aa6c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003aa71  mov     eax, ebx
0x18003aa73  mov     rcx, [rbp+170h+var_10]
0x18003aa7a  xor     rcx, rsp; StackCookie
0x18003aa7d  call    __security_check_cookie
0x18003aa82  lea     r11, [rsp+270h+var_s0]
0x18003aa8a  mov     rbx, [r11+20h]
0x18003aa8e  mov     rdi, [r11+28h]
0x18003aa92  mov     rsp, r11
0x18003aa95  pop     rbp
0x18003aa96  retn
0x18003aa98  mov     r8, rdi
0x18003aa9b  lea     rdx, [rsp+270h+var_240]
0x18003aaa0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003aaa5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003aaaa  mov     ebx, eax
0x18003aaac  test    eax, eax
0x18003aaae  jns     short loc_18003AA5B
0x18003aab0  mov     edx, 137h
0x18003aab5  jmp     loc_18003AA2C
```
