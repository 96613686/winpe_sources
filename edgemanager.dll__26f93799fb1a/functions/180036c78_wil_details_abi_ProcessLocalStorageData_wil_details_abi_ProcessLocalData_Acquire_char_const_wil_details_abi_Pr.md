# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180036c78`
- end: `0x180036dde`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180037244`

## callees

- `0x1800073a0`
- `0x1800154cc`
- `0x1800161fc`
- `0x18002b530`
- `0x180036c18`
- `0x180036c34`
- `0x180036c78`
- `0x180037460`
- `0x180037918`
- `0x180037b78`
- `0x180037c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036cf5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180036cf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036cb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036cb0`

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
0x180036c78  mov     [rsp-8+arg_10], rbx
0x180036c7d  mov     [rsp-8+arg_18], rdi
0x180036c82  push    rbp
0x180036c83  lea     rbp, [rsp-170h]
0x180036c8b  sub     rsp, 270h
0x180036c92  mov     rax, cs:__security_cookie
0x180036c99  xor     rax, rsp
0x180036c9c  mov     [rbp+170h+var_10], rax
0x180036ca3  mov     rdi, rdx
0x180036ca6  mov     qword ptr [rdx], 0
0x180036cad  mov     rbx, rcx
0x180036cb0  call    cs:__imp_GetCurrentProcessId
0x180036cb6  mov     [rsp+270h+var_248], rbx
0x180036cbb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180036cc2  mov     r9d, eax
0x180036cc5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180036ccd  mov     edx, 104h; unsigned __int64
0x180036cd2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036cd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036cdc  mov     r9d, 1F0001h; dwDesiredAccess
0x180036ce2  mov     [rsp+270h+var_240], 0
0x180036ceb  xor     r8d, r8d; dwFlags
0x180036cee  lea     rdx, [rsp+270h+Name]; lpName
0x180036cf3  xor     ecx, ecx; lpMutexAttributes
0x180036cf5  call    cs:__imp_CreateMutexExW
0x180036cfb  mov     rdx, rax
0x180036cfe  lea     rcx, [rsp+270h+var_240]
0x180036d03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036d08  cmp     [rsp+270h+var_240], 0
0x180036d0e  jnz     short loc_180036D19
0x180036d10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036d15  mov     ebx, eax
0x180036d17  jmp     short loc_180036D8C
0x180036d19  lea     rdx, [rsp+270h+var_238]
0x180036d1e  lea     rcx, [rsp+270h+var_240]
0x180036d23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180036d28  lea     rdx, [rsp+270h+var_230]; void **
0x180036d2d  mov     [rsp+270h+var_230], 0
0x180036d36  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036d3b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180036d40  mov     ebx, eax
0x180036d42  test    eax, eax
0x180036d44  jns     short loc_180036D6D
0x180036d46  mov     edx, 12Eh; void *
0x180036d4b  mov     rcx, [rbp+178h]; this
0x180036d52  lea     r8, aWil; "wil"
0x180036d59  mov     r9d, eax; char *
0x180036d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d61  lea     rcx, [rsp+270h+var_238]
0x180036d66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036d6b  jmp     short loc_180036D8C
0x180036d6d  mov     rcx, [rsp+270h+var_230]
0x180036d72  test    rcx, rcx
0x180036d75  jz      short loc_180036DBC
0x180036d77  mov     [rdi], rcx
0x180036d7a  mov     eax, [rcx]
0x180036d7c  inc     eax
0x180036d7e  mov     [rcx], eax
0x180036d80  lea     rcx, [rsp+270h+var_238]
0x180036d85  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036d8a  xor     ebx, ebx
0x180036d8c  lea     rcx, [rsp+270h+var_240]
0x180036d91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036d96  mov     eax, ebx
0x180036d98  mov     rcx, [rbp+170h+var_10]
0x180036d9f  xor     rcx, rsp; StackCookie
0x180036da2  call    __security_check_cookie
0x180036da7  lea     r11, [rsp+270h+var_s0]
0x180036daf  mov     rbx, [r11+20h]
0x180036db3  mov     rdi, [r11+28h]
0x180036db7  mov     rsp, r11
0x180036dba  pop     rbp
0x180036dbb  retn
0x180036dbc  mov     r8, rdi
0x180036dbf  lea     rdx, [rsp+270h+var_240]
0x180036dc4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180036dc9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180036dce  mov     ebx, eax
0x180036dd0  test    eax, eax
0x180036dd2  jns     short loc_180036D80
0x180036dd4  mov     edx, 137h
0x180036dd9  jmp     loc_180036D4B
```
