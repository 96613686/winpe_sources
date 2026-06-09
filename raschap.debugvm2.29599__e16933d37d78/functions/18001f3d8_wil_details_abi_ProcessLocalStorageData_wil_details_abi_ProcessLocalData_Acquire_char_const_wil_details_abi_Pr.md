# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001f3d8`
- end: `0x18001f53a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020520`

## callees

- `0x180012690`
- `0x180013b20`
- `0x18001f100`
- `0x18001f11c`
- `0x18001f3d8`
- `0x180020d6c`
- `0x180021b7c`
- `0x180022588`
- `0x180022d74`
- `0x180022f0c`
- `0x1800234f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f455`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f455`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f410`

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
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
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
0x18001f3d8  mov     [rsp-8+arg_10], rbx
0x18001f3dd  mov     [rsp-8+arg_18], rdi
0x18001f3e2  push    rbp
0x18001f3e3  lea     rbp, [rsp-170h]
0x18001f3eb  sub     rsp, 270h
0x18001f3f2  mov     rax, cs:__security_cookie
0x18001f3f9  xor     rax, rsp
0x18001f3fc  mov     [rbp+170h+var_10], rax
0x18001f403  mov     rdi, rdx
0x18001f406  mov     rbx, rcx
0x18001f409  mov     qword ptr [rdx], 0
0x18001f410  call    cs:__imp_GetCurrentProcessId
0x18001f416  mov     r9d, eax
0x18001f419  mov     [rsp+270h+var_248], rbx
0x18001f41e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001f426  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f42d  mov     edx, 104h; cchDest
0x18001f432  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001f437  call    StringCchPrintfW
0x18001f43c  mov     [rsp+270h+var_240], 0
0x18001f445  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f44b  xor     r8d, r8d; dwFlags
0x18001f44e  lea     rdx, [rsp+270h+pszDest]; lpName
0x18001f453  xor     ecx, ecx; lpMutexAttributes
0x18001f455  call    cs:__imp_CreateMutexExW
0x18001f45b  mov     rdx, rax
0x18001f45e  lea     rcx, [rsp+270h+var_240]
0x18001f463  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f468  cmp     [rsp+270h+var_240], 0
0x18001f46e  jnz     short loc_18001F479
0x18001f470  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f475  mov     ebx, eax
0x18001f477  jmp     short loc_18001F4E7
0x18001f479  lea     rdx, [rsp+270h+var_238]
0x18001f47e  lea     rcx, [rsp+270h+var_240]
0x18001f483  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f488  nop
0x18001f489  mov     [rsp+270h+var_230], 0
0x18001f492  lea     rdx, [rsp+270h+var_230]; void **
0x18001f497  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001f49c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001f4a1  mov     ebx, eax
0x18001f4a3  test    eax, eax
0x18001f4a5  jns     short loc_18001F4C8
0x18001f4a7  mov     edx, 12Eh; void *
0x18001f4ac  mov     r9d, eax; char *
0x18001f4af  mov     rcx, [rbp+178h]; this
0x18001f4b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4bb  nop
0x18001f4bc  lea     rcx, [rsp+270h+var_238]
0x18001f4c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4c6  jmp     short loc_18001F4E7
0x18001f4c8  mov     rcx, [rsp+270h+var_230]
0x18001f4cd  test    rcx, rcx
0x18001f4d0  jz      short loc_18001F517
0x18001f4d2  mov     [rdi], rcx
0x18001f4d5  mov     eax, [rcx]
0x18001f4d7  inc     eax
0x18001f4d9  mov     [rcx], eax
0x18001f4db  lea     rcx, [rsp+270h+var_238]
0x18001f4e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4e5  xor     ebx, ebx
0x18001f4e7  lea     rcx, [rsp+270h+var_240]
0x18001f4ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4f1  mov     eax, ebx
0x18001f4f3  mov     rcx, [rbp+170h+var_10]
0x18001f4fa  xor     rcx, rsp; StackCookie
0x18001f4fd  call    __security_check_cookie
0x18001f502  lea     r11, [rsp+270h+var_s0]
0x18001f50a  mov     rbx, [r11+20h]
0x18001f50e  mov     rdi, [r11+28h]
0x18001f512  mov     rsp, r11
0x18001f515  pop     rbp
0x18001f516  retn
0x18001f517  mov     r8, rdi
0x18001f51a  lea     rdx, [rsp+270h+var_240]
0x18001f51f  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001f524  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001f529  mov     ebx, eax
0x18001f52b  test    eax, eax
0x18001f52d  jns     short loc_18001F4DB
0x18001f52f  mov     edx, 137h
0x18001f534  jmp     loc_18001F4AC
```
