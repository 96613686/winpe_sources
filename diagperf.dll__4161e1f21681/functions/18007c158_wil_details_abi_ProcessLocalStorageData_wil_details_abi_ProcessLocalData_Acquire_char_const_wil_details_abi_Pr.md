# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18007c158`
- end: `0x18007c2be`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007f1e4`

## callees

- `0x180013870`
- `0x1800546bc`
- `0x18007bd18`
- `0x18007bd34`
- `0x18007c158`
- `0x18007fa80`
- `0x18008166c`
- `0x180082010`
- `0x180082bec`
- `0x18008305c`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007c190`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007c1d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007c1d5`

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
0x18007c158  mov     [rsp-8+arg_10], rbx
0x18007c15d  mov     [rsp-8+arg_18], rdi
0x18007c162  push    rbp
0x18007c163  lea     rbp, [rsp-170h]
0x18007c16b  sub     rsp, 270h
0x18007c172  mov     rax, cs:__security_cookie
0x18007c179  xor     rax, rsp
0x18007c17c  mov     [rbp+170h+var_10], rax
0x18007c183  mov     rdi, rdx
0x18007c186  mov     qword ptr [rdx], 0
0x18007c18d  mov     rbx, rcx
0x18007c190  call    cs:__imp_GetCurrentProcessId
0x18007c196  mov     [rsp+270h+var_248], rbx
0x18007c19b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18007c1a2  mov     r9d, eax
0x18007c1a5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18007c1ad  mov     edx, 104h; unsigned __int64
0x18007c1b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c1b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c1bc  mov     r9d, 1F0001h; dwDesiredAccess
0x18007c1c2  mov     [rsp+270h+var_240], 0
0x18007c1cb  xor     r8d, r8d; dwFlags
0x18007c1ce  lea     rdx, [rsp+270h+Name]; lpName
0x18007c1d3  xor     ecx, ecx; lpMutexAttributes
0x18007c1d5  call    cs:__imp_CreateMutexExW
0x18007c1db  mov     rdx, rax
0x18007c1de  lea     rcx, [rsp+270h+var_240]
0x18007c1e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007c1e8  cmp     [rsp+270h+var_240], 0
0x18007c1ee  jnz     short loc_18007C1F9
0x18007c1f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007c1f5  mov     ebx, eax
0x18007c1f7  jmp     short loc_18007C26C
0x18007c1f9  lea     rdx, [rsp+270h+var_238]
0x18007c1fe  lea     rcx, [rsp+270h+var_240]
0x18007c203  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007c208  lea     rdx, [rsp+270h+var_230]; void **
0x18007c20d  mov     [rsp+270h+var_230], 0
0x18007c216  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c21b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18007c220  mov     ebx, eax
0x18007c222  test    eax, eax
0x18007c224  jns     short loc_18007C24D
0x18007c226  mov     edx, 12Eh; void *
0x18007c22b  mov     rcx, [rbp+178h]; this
0x18007c232  lea     r8, aWil; "wil"
0x18007c239  mov     r9d, eax; char *
0x18007c23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c241  lea     rcx, [rsp+270h+var_238]
0x18007c246  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c24b  jmp     short loc_18007C26C
0x18007c24d  mov     rcx, [rsp+270h+var_230]
0x18007c252  test    rcx, rcx
0x18007c255  jz      short loc_18007C29C
0x18007c257  mov     [rdi], rcx
0x18007c25a  mov     eax, [rcx]
0x18007c25c  inc     eax
0x18007c25e  mov     [rcx], eax
0x18007c260  lea     rcx, [rsp+270h+var_238]
0x18007c265  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c26a  xor     ebx, ebx
0x18007c26c  lea     rcx, [rsp+270h+var_240]
0x18007c271  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007c276  mov     eax, ebx
0x18007c278  mov     rcx, [rbp+170h+var_10]
0x18007c27f  xor     rcx, rsp; StackCookie
0x18007c282  call    __security_check_cookie
0x18007c287  lea     r11, [rsp+270h+var_s0]
0x18007c28f  mov     rbx, [r11+20h]
0x18007c293  mov     rdi, [r11+28h]
0x18007c297  mov     rsp, r11
0x18007c29a  pop     rbp
0x18007c29b  retn
0x18007c29c  mov     r8, rdi
0x18007c29f  lea     rdx, [rsp+270h+var_240]
0x18007c2a4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007c2a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007c2ae  mov     ebx, eax
0x18007c2b0  test    eax, eax
0x18007c2b2  jns     short loc_18007C260
0x18007c2b4  mov     edx, 137h
0x18007c2b9  jmp     loc_18007C22B
```
