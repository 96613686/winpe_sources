# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180018d0c`
- end: `0x180018e7f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019fb4`

## callees

- `0x180011d9c`
- `0x1800136d4`
- `0x180014330`
- `0x180016428`
- `0x18001887c`
- `0x18001889c`
- `0x180018d0c`
- `0x18001a834`
- `0x18001ca98`
- `0x18001d824`
- `0x18001db50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018d8f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018d44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018d44`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180018d0c  mov     [rsp-8+arg_10], rbx
0x180018d11  mov     [rsp-8+arg_18], rdi
0x180018d16  push    rbp
0x180018d17  lea     rbp, [rsp-170h]
0x180018d1f  sub     rsp, 270h
0x180018d26  mov     rax, cs:__security_cookie
0x180018d2d  xor     rax, rsp
0x180018d30  mov     [rbp+170h+var_10], rax
0x180018d37  mov     rdi, rdx
0x180018d3a  mov     qword ptr [rdx], 0
0x180018d41  mov     rbx, rcx
0x180018d44  call    cs:__imp_GetCurrentProcessId
0x180018d4b  nop     dword ptr [rax+rax+00h]
0x180018d50  mov     [rsp+270h+var_248], rbx
0x180018d55  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018d5c  mov     r9d, eax
0x180018d5f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180018d67  mov     edx, 104h; unsigned __int64
0x180018d6c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018d71  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018d76  mov     r9d, 1F0001h; dwDesiredAccess
0x180018d7c  mov     [rsp+270h+var_240], 0
0x180018d85  xor     r8d, r8d; dwFlags
0x180018d88  lea     rdx, [rsp+270h+Name]; lpName
0x180018d8d  xor     ecx, ecx; lpMutexAttributes
0x180018d8f  call    cs:__imp_CreateMutexExW
0x180018d96  nop     dword ptr [rax+rax+00h]
0x180018d9b  mov     rdx, rax
0x180018d9e  lea     rcx, [rsp+270h+var_240]
0x180018da3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018da8  cmp     [rsp+270h+var_240], 0
0x180018dae  jnz     short loc_180018DB9
0x180018db0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018db5  mov     ebx, eax
0x180018db7  jmp     short loc_180018E2C
0x180018db9  lea     rdx, [rsp+270h+var_238]
0x180018dbe  lea     rcx, [rsp+270h+var_240]
0x180018dc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180018dc8  lea     rdx, [rsp+270h+var_230]; void **
0x180018dcd  mov     [rsp+270h+var_230], 0
0x180018dd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018ddb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180018de0  mov     ebx, eax
0x180018de2  test    eax, eax
0x180018de4  jns     short loc_180018E0D
0x180018de6  mov     edx, 12Eh; void *
0x180018deb  mov     rcx, [rbp+178h]; this
0x180018df2  lea     r8, aWil; "wil"
0x180018df9  mov     r9d, eax; char *
0x180018dfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e01  lea     rcx, [rsp+270h+var_238]
0x180018e06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018e0b  jmp     short loc_180018E2C
0x180018e0d  mov     rcx, [rsp+270h+var_230]
0x180018e12  test    rcx, rcx
0x180018e15  jz      short loc_180018E5D
0x180018e17  mov     [rdi], rcx
0x180018e1a  mov     eax, [rcx]
0x180018e1c  inc     eax
0x180018e1e  mov     [rcx], eax
0x180018e20  lea     rcx, [rsp+270h+var_238]
0x180018e25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018e2a  xor     ebx, ebx
0x180018e2c  lea     rcx, [rsp+270h+var_240]
0x180018e31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018e36  mov     eax, ebx
0x180018e38  mov     rcx, [rbp+170h+var_10]
0x180018e3f  xor     rcx, rsp; StackCookie
0x180018e42  call    __security_check_cookie
0x180018e47  lea     r11, [rsp+270h+var_s0]
0x180018e4f  mov     rbx, [r11+20h]
0x180018e53  mov     rdi, [r11+28h]
0x180018e57  mov     rsp, r11
0x180018e5a  pop     rbp
0x180018e5b  retn
0x180018e5d  mov     r8, rdi
0x180018e60  lea     rdx, [rsp+270h+var_240]
0x180018e65  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018e6a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018e6f  mov     ebx, eax
0x180018e71  test    eax, eax
0x180018e73  jns     short loc_180018E20
0x180018e75  mov     edx, 137h
0x180018e7a  jmp     loc_180018DEB
```
