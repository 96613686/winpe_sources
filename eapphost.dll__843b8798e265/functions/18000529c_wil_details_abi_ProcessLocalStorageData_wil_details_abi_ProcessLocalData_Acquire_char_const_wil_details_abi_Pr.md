# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000529c`
- end: `0x180005408`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007d90`

## callees

- `0x180002af0`
- `0x180005024`
- `0x180005044`
- `0x18000529c`
- `0x180007ad0`
- `0x18000878c`
- `0x180008e34`
- `0x1800094d0`
- `0x1800095b8`
- `0x180009b3c`
- `0x180009c84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800052d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800052d4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000531f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000531f`

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
0x18000529c  mov     [rsp-8+arg_10], rbx
0x1800052a1  mov     [rsp-8+arg_18], rdi
0x1800052a6  push    rbp
0x1800052a7  lea     rbp, [rsp-170h]
0x1800052af  sub     rsp, 270h
0x1800052b6  mov     rax, cs:__security_cookie
0x1800052bd  xor     rax, rsp
0x1800052c0  mov     [rbp+170h+var_10], rax
0x1800052c7  mov     rdi, rdx
0x1800052ca  mov     qword ptr [rdx], 0
0x1800052d1  mov     rbx, rcx
0x1800052d4  call    cs:__imp_GetCurrentProcessId
0x1800052db  nop     dword ptr [rax+rax+00h]
0x1800052e0  mov     [rsp+270h+var_248], rbx
0x1800052e5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800052ec  mov     r9d, eax
0x1800052ef  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800052f7  mov     edx, 104h; unsigned __int64
0x1800052fc  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005301  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005306  mov     r9d, 1F0001h; dwDesiredAccess
0x18000530c  mov     [rsp+270h+var_240], 0
0x180005315  xor     r8d, r8d; dwFlags
0x180005318  lea     rdx, [rsp+270h+Name]; lpName
0x18000531d  xor     ecx, ecx; lpMutexAttributes
0x18000531f  call    cs:__imp_CreateMutexExW
0x180005326  nop     dword ptr [rax+rax+00h]
0x18000532b  mov     rdx, rax
0x18000532e  lea     rcx, [rsp+270h+var_240]
0x180005333  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005338  cmp     [rsp+270h+var_240], 0
0x18000533e  jnz     short loc_180005349
0x180005340  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005345  mov     ebx, eax
0x180005347  jmp     short loc_1800053B5
0x180005349  lea     rdx, [rsp+270h+var_238]
0x18000534e  lea     rcx, [rsp+270h+var_240]
0x180005353  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005358  lea     rdx, [rsp+270h+var_230]; void **
0x18000535d  mov     [rsp+270h+var_230], 0
0x180005366  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000536b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180005370  mov     ebx, eax
0x180005372  test    eax, eax
0x180005374  jns     short loc_180005396
0x180005376  mov     edx, 12Eh; void *
0x18000537b  mov     rcx, [rbp+178h]; this
0x180005382  mov     r9d, eax; char *
0x180005385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000538a  lea     rcx, [rsp+270h+var_238]
0x18000538f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005394  jmp     short loc_1800053B5
0x180005396  mov     rcx, [rsp+270h+var_230]
0x18000539b  test    rcx, rcx
0x18000539e  jz      short loc_1800053E6
0x1800053a0  mov     [rdi], rcx
0x1800053a3  mov     eax, [rcx]
0x1800053a5  inc     eax
0x1800053a7  mov     [rcx], eax
0x1800053a9  lea     rcx, [rsp+270h+var_238]
0x1800053ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800053b3  xor     ebx, ebx
0x1800053b5  lea     rcx, [rsp+270h+var_240]
0x1800053ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800053bf  mov     eax, ebx
0x1800053c1  mov     rcx, [rbp+170h+var_10]
0x1800053c8  xor     rcx, rsp; StackCookie
0x1800053cb  call    __security_check_cookie
0x1800053d0  lea     r11, [rsp+270h+var_s0]
0x1800053d8  mov     rbx, [r11+20h]
0x1800053dc  mov     rdi, [r11+28h]
0x1800053e0  mov     rsp, r11
0x1800053e3  pop     rbp
0x1800053e4  retn
0x1800053e6  mov     r8, rdi
0x1800053e9  lea     rdx, [rsp+270h+var_240]
0x1800053ee  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800053f3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800053f8  mov     ebx, eax
0x1800053fa  test    eax, eax
0x1800053fc  jns     short loc_1800053A9
0x1800053fe  mov     edx, 137h
0x180005403  jmp     loc_18000537B
```
