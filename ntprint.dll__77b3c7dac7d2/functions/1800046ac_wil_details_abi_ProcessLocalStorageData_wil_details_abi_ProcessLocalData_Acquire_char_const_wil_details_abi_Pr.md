# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800046ac`
- end: `0x180004812`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800056c4`

## callees

- `0x180002300`
- `0x1800042bc`
- `0x1800042d8`
- `0x1800046ac`
- `0x1800053c8`
- `0x180006000`
- `0x180007478`
- `0x18000797c`
- `0x180007d98`
- `0x180008564`
- `0x1800088f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004729`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800046e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800046e4`

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
0x1800046ac  mov     [rsp-8+arg_10], rbx
0x1800046b1  mov     [rsp-8+arg_18], rdi
0x1800046b6  push    rbp
0x1800046b7  lea     rbp, [rsp-170h]
0x1800046bf  sub     rsp, 270h
0x1800046c6  mov     rax, cs:__security_cookie
0x1800046cd  xor     rax, rsp
0x1800046d0  mov     [rbp+170h+var_10], rax
0x1800046d7  mov     rdi, rdx
0x1800046da  mov     qword ptr [rdx], 0
0x1800046e1  mov     rbx, rcx
0x1800046e4  call    cs:__imp_GetCurrentProcessId
0x1800046ea  mov     [rsp+270h+var_248], rbx
0x1800046ef  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800046f6  mov     r9d, eax
0x1800046f9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004701  mov     edx, 104h; unsigned __int64
0x180004706  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000470b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004710  mov     r9d, 1F0001h; dwDesiredAccess
0x180004716  mov     [rsp+270h+var_240], 0
0x18000471f  xor     r8d, r8d; dwFlags
0x180004722  lea     rdx, [rsp+270h+Name]; lpName
0x180004727  xor     ecx, ecx; lpMutexAttributes
0x180004729  call    cs:__imp_CreateMutexExW
0x18000472f  mov     rdx, rax
0x180004732  lea     rcx, [rsp+270h+var_240]
0x180004737  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000473c  cmp     [rsp+270h+var_240], 0
0x180004742  jnz     short loc_18000474D
0x180004744  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004749  mov     ebx, eax
0x18000474b  jmp     short loc_1800047C0
0x18000474d  lea     rdx, [rsp+270h+var_238]
0x180004752  lea     rcx, [rsp+270h+var_240]
0x180004757  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000475c  lea     rdx, [rsp+270h+var_230]; void **
0x180004761  mov     [rsp+270h+var_230], 0
0x18000476a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000476f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004774  mov     ebx, eax
0x180004776  test    eax, eax
0x180004778  jns     short loc_1800047A1
0x18000477a  mov     edx, 12Eh; void *
0x18000477f  mov     rcx, [rbp+178h]; this
0x180004786  lea     r8, aWil; "wil"
0x18000478d  mov     r9d, eax; char *
0x180004790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004795  lea     rcx, [rsp+270h+var_238]
0x18000479a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000479f  jmp     short loc_1800047C0
0x1800047a1  mov     rcx, [rsp+270h+var_230]
0x1800047a6  test    rcx, rcx
0x1800047a9  jz      short loc_1800047F0
0x1800047ab  mov     [rdi], rcx
0x1800047ae  mov     eax, [rcx]
0x1800047b0  inc     eax
0x1800047b2  mov     [rcx], eax
0x1800047b4  lea     rcx, [rsp+270h+var_238]
0x1800047b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800047be  xor     ebx, ebx
0x1800047c0  lea     rcx, [rsp+270h+var_240]
0x1800047c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800047ca  mov     eax, ebx
0x1800047cc  mov     rcx, [rbp+170h+var_10]
0x1800047d3  xor     rcx, rsp; StackCookie
0x1800047d6  call    __security_check_cookie
0x1800047db  lea     r11, [rsp+270h+var_s0]
0x1800047e3  mov     rbx, [r11+20h]
0x1800047e7  mov     rdi, [r11+28h]
0x1800047eb  mov     rsp, r11
0x1800047ee  pop     rbp
0x1800047ef  retn
0x1800047f0  mov     r8, rdi
0x1800047f3  lea     rdx, [rsp+270h+var_240]
0x1800047f8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800047fd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004802  mov     ebx, eax
0x180004804  test    eax, eax
0x180004806  jns     short loc_1800047B4
0x180004808  mov     edx, 137h
0x18000480d  jmp     loc_18000477F
```
