# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003ce0`
- end: `0x180003e42`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004c80`

## callees

- `0x180003900`
- `0x18000391c`
- `0x180003ce0`
- `0x1800049a8`
- `0x180005754`
- `0x18000685c`
- `0x180007014`
- `0x180007460`
- `0x180007c04`
- `0x180007fb8`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003d18`
- `KERNEL32!GetCurrentProcessId` at `0x180003d18`
- `KERNEL32!CreateMutexExW` at `0x180003d5d`
- `KERNEL32!CreateMutexExW` at `0x180003d5d`

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
0x180003ce0  mov     [rsp-8+arg_10], rbx
0x180003ce5  mov     [rsp-8+arg_18], rdi
0x180003cea  push    rbp
0x180003ceb  lea     rbp, [rsp-170h]
0x180003cf3  sub     rsp, 270h
0x180003cfa  mov     rax, cs:__security_cookie
0x180003d01  xor     rax, rsp
0x180003d04  mov     [rbp+170h+var_10], rax
0x180003d0b  mov     rdi, rdx
0x180003d0e  mov     rbx, rcx
0x180003d11  mov     qword ptr [rdx], 0
0x180003d18  call    cs:__imp_GetCurrentProcessId
0x180003d1e  mov     r9d, eax
0x180003d21  mov     [rsp+270h+var_248], rbx
0x180003d26  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003d2e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d35  mov     edx, 104h; unsigned __int64
0x180003d3a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003d3f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003d44  mov     [rsp+270h+var_240], 0
0x180003d4d  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d53  xor     r8d, r8d; dwFlags
0x180003d56  lea     rdx, [rsp+270h+Name]; lpName
0x180003d5b  xor     ecx, ecx; lpMutexAttributes
0x180003d5d  call    cs:__imp_CreateMutexExW
0x180003d63  mov     rdx, rax
0x180003d66  lea     rcx, [rsp+270h+var_240]
0x180003d6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003d70  cmp     [rsp+270h+var_240], 0
0x180003d76  jnz     short loc_180003D81
0x180003d78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003d7d  mov     ebx, eax
0x180003d7f  jmp     short loc_180003DEF
0x180003d81  lea     rdx, [rsp+270h+var_238]
0x180003d86  lea     rcx, [rsp+270h+var_240]
0x180003d8b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003d90  nop
0x180003d91  mov     [rsp+270h+var_230], 0
0x180003d9a  lea     rdx, [rsp+270h+var_230]; void **
0x180003d9f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003da4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180003da9  mov     ebx, eax
0x180003dab  test    eax, eax
0x180003dad  jns     short loc_180003DD0
0x180003daf  mov     edx, 12Eh; void *
0x180003db4  mov     r9d, eax; char *
0x180003db7  mov     rcx, [rbp+178h]; this
0x180003dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dc3  nop
0x180003dc4  lea     rcx, [rsp+270h+var_238]
0x180003dc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003dce  jmp     short loc_180003DEF
0x180003dd0  mov     rcx, [rsp+270h+var_230]
0x180003dd5  test    rcx, rcx
0x180003dd8  jz      short loc_180003E1F
0x180003dda  mov     [rdi], rcx
0x180003ddd  mov     eax, [rcx]
0x180003ddf  inc     eax
0x180003de1  mov     [rcx], eax
0x180003de3  lea     rcx, [rsp+270h+var_238]
0x180003de8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003ded  xor     ebx, ebx
0x180003def  lea     rcx, [rsp+270h+var_240]
0x180003df4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003df9  mov     eax, ebx
0x180003dfb  mov     rcx, [rbp+170h+var_10]
0x180003e02  xor     rcx, rsp; StackCookie
0x180003e05  call    __security_check_cookie
0x180003e0a  lea     r11, [rsp+270h+var_s0]
0x180003e12  mov     rbx, [r11+20h]
0x180003e16  mov     rdi, [r11+28h]
0x180003e1a  mov     rsp, r11
0x180003e1d  pop     rbp
0x180003e1e  retn
0x180003e1f  mov     r8, rdi
0x180003e22  lea     rdx, [rsp+270h+var_240]
0x180003e27  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003e2c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003e31  mov     ebx, eax
0x180003e33  test    eax, eax
0x180003e35  jns     short loc_180003DE3
0x180003e37  mov     edx, 137h
0x180003e3c  jmp     loc_180003DB4
```
