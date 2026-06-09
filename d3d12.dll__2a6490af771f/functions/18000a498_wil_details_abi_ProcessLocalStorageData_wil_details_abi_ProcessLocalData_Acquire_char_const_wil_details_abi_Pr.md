# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a498`
- end: `0x18000a5f7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d130`

## callees

- `0x18000310c`
- `0x180005520`
- `0x180005830`
- `0x180008ce4`
- `0x180009d5c`
- `0x18000a498`
- `0x18000a600`
- `0x18000a61c`
- `0x18000ac00`
- `0x18000b410`
- `0x18000d32c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a515`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a4d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a4d0`

## pseudocode

```c
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
0x18000a498  mov     [rsp-8+arg_10], rbx
0x18000a49d  mov     [rsp-8+arg_18], rdi
0x18000a4a2  push    rbp
0x18000a4a3  lea     rbp, [rsp-170h]
0x18000a4ab  sub     rsp, 270h
0x18000a4b2  mov     rax, cs:__security_cookie
0x18000a4b9  xor     rax, rsp
0x18000a4bc  mov     [rbp+170h+var_10], rax
0x18000a4c3  mov     rdi, rdx
0x18000a4c6  mov     qword ptr [rdx], 0
0x18000a4cd  mov     rbx, rcx
0x18000a4d0  call    cs:__imp_GetCurrentProcessId
0x18000a4d6  mov     [rsp+270h+var_248], rbx
0x18000a4db  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a4e2  mov     r9d, eax
0x18000a4e5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a4ed  mov     edx, 104h; unsigned __int64
0x18000a4f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a4f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a4fc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a502  mov     [rsp+270h+var_240], 0
0x18000a50b  xor     r8d, r8d; dwFlags
0x18000a50e  lea     rdx, [rsp+270h+Name]; lpName
0x18000a513  xor     ecx, ecx; lpMutexAttributes
0x18000a515  call    cs:__imp_CreateMutexExW
0x18000a51b  mov     rdx, rax
0x18000a51e  lea     rcx, [rsp+270h+var_240]
0x18000a523  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a528  cmp     [rsp+270h+var_240], 0
0x18000a52e  jnz     short loc_18000A539
0x18000a530  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a535  mov     ebx, eax
0x18000a537  jmp     short loc_18000A5A5
0x18000a539  lea     rdx, [rsp+270h+var_238]
0x18000a53e  lea     rcx, [rsp+270h+var_240]
0x18000a543  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a548  lea     rdx, [rsp+270h+var_230]; void **
0x18000a54d  mov     [rsp+270h+var_230], 0
0x18000a556  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a55b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a560  mov     ebx, eax
0x18000a562  test    eax, eax
0x18000a564  jns     short loc_18000A586
0x18000a566  mov     edx, 12Eh; void *
0x18000a56b  mov     rcx, [rbp+178h]; this
0x18000a572  mov     r9d, eax; char *
0x18000a575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a57a  lea     rcx, [rsp+270h+var_238]
0x18000a57f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a584  jmp     short loc_18000A5A5
0x18000a586  mov     rcx, [rsp+270h+var_230]
0x18000a58b  test    rcx, rcx
0x18000a58e  jz      short loc_18000A5D5
0x18000a590  mov     [rdi], rcx
0x18000a593  mov     eax, [rcx]
0x18000a595  inc     eax
0x18000a597  mov     [rcx], eax
0x18000a599  lea     rcx, [rsp+270h+var_238]
0x18000a59e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5a3  xor     ebx, ebx
0x18000a5a5  lea     rcx, [rsp+270h+var_240]
0x18000a5aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5af  mov     eax, ebx
0x18000a5b1  mov     rcx, [rbp+170h+var_10]
0x18000a5b8  xor     rcx, rsp; StackCookie
0x18000a5bb  call    __security_check_cookie
0x18000a5c0  lea     r11, [rsp+270h+var_s0]
0x18000a5c8  mov     rbx, [r11+20h]
0x18000a5cc  mov     rdi, [r11+28h]
0x18000a5d0  mov     rsp, r11
0x18000a5d3  pop     rbp
0x18000a5d4  retn
0x18000a5d5  mov     r8, rdi
0x18000a5d8  lea     rdx, [rsp+270h+var_240]
0x18000a5dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a5e2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a5e7  mov     ebx, eax
0x18000a5e9  test    eax, eax
0x18000a5eb  jns     short loc_18000A599
0x18000a5ed  mov     edx, 137h
0x18000a5f2  jmp     loc_18000A56B
```
