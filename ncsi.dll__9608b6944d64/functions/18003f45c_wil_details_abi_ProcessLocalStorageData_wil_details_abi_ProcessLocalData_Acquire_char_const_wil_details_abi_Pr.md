# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003f45c`
- end: `0x18003f5cb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005b610`

## callees

- `0x180017f68`
- `0x180026790`
- `0x18003f45c`
- `0x18003f958`
- `0x18003f9e4`
- `0x180047240`
- `0x18004c520`
- `0x18004eaa4`
- `0x18004efac`
- `0x18004f6dc`
- `0x18005b79c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f494`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f494`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003f4d9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003f4d9`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18003f45c  mov     [rsp-8+arg_10], rbx
0x18003f461  mov     [rsp-8+arg_18], rdi
0x18003f466  push    rbp
0x18003f467  lea     rbp, [rsp-170h]
0x18003f46f  sub     rsp, 270h
0x18003f476  mov     rax, cs:__security_cookie
0x18003f47d  xor     rax, rsp
0x18003f480  mov     [rbp+170h+var_10], rax
0x18003f487  mov     rdi, rdx
0x18003f48a  mov     qword ptr [rdx], 0
0x18003f491  mov     rbx, rcx
0x18003f494  call    cs:__imp_GetCurrentProcessId
0x18003f49a  mov     [rsp+270h+var_248], rbx
0x18003f49f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003f4a6  mov     r9d, eax
0x18003f4a9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003f4b1  mov     edx, 104h; unsigned __int64
0x18003f4b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003f4bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f4c0  mov     r9d, 1F0001h; dwDesiredAccess
0x18003f4c6  mov     [rsp+270h+var_240], 0
0x18003f4cf  xor     r8d, r8d; dwFlags
0x18003f4d2  lea     rdx, [rsp+270h+Name]; lpName
0x18003f4d7  xor     ecx, ecx; lpMutexAttributes
0x18003f4d9  call    cs:__imp_CreateMutexExW
0x18003f4df  mov     rdx, rax
0x18003f4e2  lea     rcx, [rsp+270h+var_240]
0x18003f4e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003f4ec  cmp     [rsp+270h+var_240], 0
0x18003f4f2  jnz     short loc_18003F4FD
0x18003f4f4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003f4f9  mov     ebx, eax
0x18003f4fb  jmp     short loc_18003F579
0x18003f4fd  lea     rdx, [rsp+270h+var_238]
0x18003f502  mov     [rsp+270h+var_238], 0
0x18003f50b  lea     rcx, [rsp+270h+var_240]
0x18003f510  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003f515  lea     rdx, [rsp+270h+var_230]; void **
0x18003f51a  mov     [rsp+270h+var_230], 0
0x18003f523  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003f528  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003f52d  mov     ebx, eax
0x18003f52f  test    eax, eax
0x18003f531  jns     short loc_18003F55A
0x18003f533  mov     edx, 12Eh; void *
0x18003f538  mov     rcx, [rbp+178h]; this
0x18003f53f  lea     r8, aWil; "wil"
0x18003f546  mov     r9d, eax; char *
0x18003f549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f54e  lea     rcx, [rsp+270h+var_238]
0x18003f553  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f558  jmp     short loc_18003F579
0x18003f55a  mov     rcx, [rsp+270h+var_230]
0x18003f55f  test    rcx, rcx
0x18003f562  jz      short loc_18003F5A9
0x18003f564  mov     [rdi], rcx
0x18003f567  mov     eax, [rcx]
0x18003f569  inc     eax
0x18003f56b  mov     [rcx], eax
0x18003f56d  lea     rcx, [rsp+270h+var_238]
0x18003f572  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f577  xor     ebx, ebx
0x18003f579  lea     rcx, [rsp+270h+var_240]
0x18003f57e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f583  mov     eax, ebx
0x18003f585  mov     rcx, [rbp+170h+var_10]
0x18003f58c  xor     rcx, rsp; StackCookie
0x18003f58f  call    __security_check_cookie
0x18003f594  lea     r11, [rsp+270h+var_s0]
0x18003f59c  mov     rbx, [r11+20h]
0x18003f5a0  mov     rdi, [r11+28h]
0x18003f5a4  mov     rsp, r11
0x18003f5a7  pop     rbp
0x18003f5a8  retn
0x18003f5a9  mov     r8, rdi
0x18003f5ac  lea     rdx, [rsp+270h+var_240]
0x18003f5b1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003f5b6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003f5bb  mov     ebx, eax
0x18003f5bd  test    eax, eax
0x18003f5bf  jns     short loc_18003F56D
0x18003f5c1  mov     edx, 137h
0x18003f5c6  jmp     loc_18003F538
```
