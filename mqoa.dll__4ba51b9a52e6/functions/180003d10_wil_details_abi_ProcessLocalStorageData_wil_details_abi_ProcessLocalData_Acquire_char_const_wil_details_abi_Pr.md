# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d10`
- end: `0x180003e72`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004edc`

## callees

- `0x180003810`
- `0x18000382c`
- `0x180003d10`
- `0x180004b24`
- `0x180005b08`
- `0x180006e6c`
- `0x1800075ec`
- `0x180007acc`
- `0x1800081d4`
- `0x180008af0`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003d48`
- `KERNEL32!GetCurrentProcessId` at `0x180003d48`
- `KERNEL32!CreateMutexExW` at `0x180003d8d`
- `KERNEL32!CreateMutexExW` at `0x180003d8d`

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
0x180003d10  mov     [rsp-8+arg_10], rbx
0x180003d15  mov     [rsp-8+arg_18], rdi
0x180003d1a  push    rbp
0x180003d1b  lea     rbp, [rsp-170h]
0x180003d23  sub     rsp, 270h
0x180003d2a  mov     rax, cs:__security_cookie
0x180003d31  xor     rax, rsp
0x180003d34  mov     [rbp+170h+var_10], rax
0x180003d3b  mov     rdi, rdx
0x180003d3e  mov     rbx, rcx
0x180003d41  mov     qword ptr [rdx], 0
0x180003d48  call    cs:__imp_GetCurrentProcessId
0x180003d4e  mov     r9d, eax
0x180003d51  mov     [rsp+270h+var_248], rbx
0x180003d56  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003d5e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d65  mov     edx, 104h; unsigned __int64
0x180003d6a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003d6f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003d74  mov     [rsp+270h+var_240], 0
0x180003d7d  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d83  xor     r8d, r8d; dwFlags
0x180003d86  lea     rdx, [rsp+270h+Name]; lpName
0x180003d8b  xor     ecx, ecx; lpMutexAttributes
0x180003d8d  call    cs:__imp_CreateMutexExW
0x180003d93  mov     rdx, rax
0x180003d96  lea     rcx, [rsp+270h+var_240]
0x180003d9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003da0  cmp     [rsp+270h+var_240], 0
0x180003da6  jnz     short loc_180003DB1
0x180003da8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003dad  mov     ebx, eax
0x180003daf  jmp     short loc_180003E1F
0x180003db1  lea     rdx, [rsp+270h+var_238]
0x180003db6  lea     rcx, [rsp+270h+var_240]
0x180003dbb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003dc0  nop
0x180003dc1  mov     [rsp+270h+var_230], 0
0x180003dca  lea     rdx, [rsp+270h+var_230]; void **
0x180003dcf  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003dd4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180003dd9  mov     ebx, eax
0x180003ddb  test    eax, eax
0x180003ddd  jns     short loc_180003E00
0x180003ddf  mov     edx, 12Eh; void *
0x180003de4  mov     r9d, eax; char *
0x180003de7  mov     rcx, [rbp+178h]; this
0x180003dee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003df3  nop
0x180003df4  lea     rcx, [rsp+270h+var_238]
0x180003df9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003dfe  jmp     short loc_180003E1F
0x180003e00  mov     rcx, [rsp+270h+var_230]
0x180003e05  test    rcx, rcx
0x180003e08  jz      short loc_180003E4F
0x180003e0a  mov     [rdi], rcx
0x180003e0d  mov     eax, [rcx]
0x180003e0f  inc     eax
0x180003e11  mov     [rcx], eax
0x180003e13  lea     rcx, [rsp+270h+var_238]
0x180003e18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e1d  xor     ebx, ebx
0x180003e1f  lea     rcx, [rsp+270h+var_240]
0x180003e24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003e29  mov     eax, ebx
0x180003e2b  mov     rcx, [rbp+170h+var_10]
0x180003e32  xor     rcx, rsp; StackCookie
0x180003e35  call    __security_check_cookie
0x180003e3a  lea     r11, [rsp+270h+var_s0]
0x180003e42  mov     rbx, [r11+20h]
0x180003e46  mov     rdi, [r11+28h]
0x180003e4a  mov     rsp, r11
0x180003e4d  pop     rbp
0x180003e4e  retn
0x180003e4f  mov     r8, rdi
0x180003e52  lea     rdx, [rsp+270h+var_240]
0x180003e57  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003e5c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003e61  mov     ebx, eax
0x180003e63  test    eax, eax
0x180003e65  jns     short loc_180003E13
0x180003e67  mov     edx, 137h
0x180003e6c  jmp     loc_180003DE4
```
