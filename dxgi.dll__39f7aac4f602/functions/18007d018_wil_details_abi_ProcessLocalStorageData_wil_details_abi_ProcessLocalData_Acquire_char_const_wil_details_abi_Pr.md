# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18007d018`
- end: `0x18007d17e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007d77c`

## callees

- `0x18003e0f4`
- `0x18003e5fc`
- `0x18003e630`
- `0x18003e710`
- `0x18003e8f8`
- `0x18003e920`
- `0x1800593f0`
- `0x180067d2c`
- `0x180075fa0`
- `0x18007d018`
- `0x18007d978`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007d095`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007d095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d050`

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
0x18007d018  mov     [rsp-8+arg_10], rbx
0x18007d01d  mov     [rsp-8+arg_18], rdi
0x18007d022  push    rbp
0x18007d023  lea     rbp, [rsp-170h]
0x18007d02b  sub     rsp, 270h
0x18007d032  mov     rax, cs:__security_cookie
0x18007d039  xor     rax, rsp
0x18007d03c  mov     [rbp+170h+var_10], rax
0x18007d043  mov     rdi, rdx
0x18007d046  mov     qword ptr [rdx], 0
0x18007d04d  mov     rbx, rcx
0x18007d050  call    cs:__imp_GetCurrentProcessId
0x18007d056  mov     [rsp+270h+var_248], rbx
0x18007d05b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18007d062  mov     r9d, eax
0x18007d065  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18007d06d  mov     edx, 104h; unsigned __int64
0x18007d072  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007d077  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d07c  mov     r9d, 1F0001h; dwDesiredAccess
0x18007d082  mov     [rsp+270h+var_240], 0
0x18007d08b  xor     r8d, r8d; dwFlags
0x18007d08e  lea     rdx, [rsp+270h+Name]; lpName
0x18007d093  xor     ecx, ecx; lpMutexAttributes
0x18007d095  call    cs:__imp_CreateMutexExW
0x18007d09b  mov     rdx, rax
0x18007d09e  lea     rcx, [rsp+270h+var_240]
0x18007d0a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007d0a8  cmp     [rsp+270h+var_240], 0
0x18007d0ae  jnz     short loc_18007D0B9
0x18007d0b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007d0b5  mov     ebx, eax
0x18007d0b7  jmp     short loc_18007D12C
0x18007d0b9  lea     rdx, [rsp+270h+var_238]
0x18007d0be  lea     rcx, [rsp+270h+var_240]
0x18007d0c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007d0c8  lea     rdx, [rsp+270h+var_230]; void **
0x18007d0cd  mov     [rsp+270h+var_230], 0
0x18007d0d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007d0db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18007d0e0  mov     ebx, eax
0x18007d0e2  test    eax, eax
0x18007d0e4  jns     short loc_18007D10D
0x18007d0e6  mov     edx, 12Eh; void *
0x18007d0eb  mov     rcx, [rbp+178h]; this
0x18007d0f2  lea     r8, aWil; "wil"
0x18007d0f9  mov     r9d, eax; char *
0x18007d0fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d101  lea     rcx, [rsp+270h+var_238]
0x18007d106  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007d10b  jmp     short loc_18007D12C
0x18007d10d  mov     rcx, [rsp+270h+var_230]
0x18007d112  test    rcx, rcx
0x18007d115  jz      short loc_18007D15C
0x18007d117  mov     [rdi], rcx
0x18007d11a  mov     eax, [rcx]
0x18007d11c  inc     eax
0x18007d11e  mov     [rcx], eax
0x18007d120  lea     rcx, [rsp+270h+var_238]
0x18007d125  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007d12a  xor     ebx, ebx
0x18007d12c  lea     rcx, [rsp+270h+var_240]
0x18007d131  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007d136  mov     eax, ebx
0x18007d138  mov     rcx, [rbp+170h+var_10]
0x18007d13f  xor     rcx, rsp; StackCookie
0x18007d142  call    __security_check_cookie
0x18007d147  lea     r11, [rsp+270h+var_s0]
0x18007d14f  mov     rbx, [r11+20h]
0x18007d153  mov     rdi, [r11+28h]
0x18007d157  mov     rsp, r11
0x18007d15a  pop     rbp
0x18007d15b  retn
0x18007d15c  mov     r8, rdi
0x18007d15f  lea     rdx, [rsp+270h+var_240]
0x18007d164  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007d169  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007d16e  mov     ebx, eax
0x18007d170  test    eax, eax
0x18007d172  jns     short loc_18007D120
0x18007d174  mov     edx, 137h
0x18007d179  jmp     loc_18007D0EB
```
