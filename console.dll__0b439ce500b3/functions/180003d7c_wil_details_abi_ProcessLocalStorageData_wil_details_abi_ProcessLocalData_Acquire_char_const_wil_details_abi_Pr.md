# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d7c`
- end: `0x180003f33`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800049b4`

## callees

- `0x1800015b0`
- `0x180003c24`
- `0x180003c44`
- `0x180003d7c`
- `0x180004700`
- `0x180005178`
- `0x1800058a4`
- `0x180005ea4`
- `0x180006038`
- `0x180006368`
- `0x18000646c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003dff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003dff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003db4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003d7c  mov     [rsp-8+arg_10], rbx
0x180003d81  mov     [rsp-8+arg_18], rdi
0x180003d86  push    rbp
0x180003d87  lea     rbp, [rsp-170h]
0x180003d8f  sub     rsp, 270h
0x180003d96  mov     rax, cs:__security_cookie
0x180003d9d  xor     rax, rsp
0x180003da0  mov     [rbp+170h+var_10], rax
0x180003da7  mov     rdi, rdx
0x180003daa  mov     qword ptr [rdx], 0
0x180003db1  mov     rbx, rcx
0x180003db4  call    cs:__imp_GetCurrentProcessId
0x180003dbb  nop     dword ptr [rax+rax+00h]
0x180003dc0  mov     [rsp+270h+var_248], rbx
0x180003dc5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003dcc  mov     r9d, eax
0x180003dcf  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003dd7  mov     edx, 104h; unsigned __int64
0x180003ddc  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003de1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003de6  mov     r9d, 1F0001h; dwDesiredAccess
0x180003dec  mov     [rsp+270h+var_240], 0
0x180003df5  xor     r8d, r8d; dwFlags
0x180003df8  lea     rdx, [rsp+270h+Name]; lpName
0x180003dfd  xor     ecx, ecx; lpMutexAttributes
0x180003dff  call    cs:__imp_CreateMutexExW
0x180003e06  nop     dword ptr [rax+rax+00h]
0x180003e0b  mov     rdx, rax
0x180003e0e  lea     rcx, [rsp+270h+var_240]
0x180003e13  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003e18  cmp     [rsp+270h+var_240], 0
0x180003e1e  jnz     short loc_180003E2C
0x180003e20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e25  mov     ebx, eax
0x180003e27  jmp     loc_180003EDD
0x180003e2c  lea     rdx, [rsp+270h+var_238]
0x180003e31  lea     rcx, [rsp+270h+var_240]
0x180003e36  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003e3b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003e40  mov     [rsp+270h+var_230], 0
0x180003e49  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003e4e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180003e53  mov     ebx, eax
0x180003e55  test    eax, eax
0x180003e57  jns     short loc_180003EB6
0x180003e59  mov     rcx, [rbp+178h]; this
0x180003e60  lea     r8, aWil; "wil"
0x180003e67  mov     r9d, eax; char *
0x180003e6a  mov     edx, 66h ; 'f'; void *
0x180003e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e74  mov     rcx, [rbp+178h]; this
0x180003e7b  lea     r8, aWil; "wil"
0x180003e82  mov     r9d, ebx; char *
0x180003e85  mov     edx, 6Fh ; 'o'; void *
0x180003e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e8f  mov     r9d, ebx; char *
0x180003e92  mov     edx, 12Eh; void *
0x180003e97  mov     rcx, [rbp+178h]; this
0x180003e9e  lea     r8, aWil; "wil"
0x180003ea5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003eaa  lea     rcx, [rsp+270h+var_238]
0x180003eaf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003eb4  jmp     short loc_180003EDD
0x180003eb6  mov     rax, [rsp+270h+var_230]
0x180003ebb  lea     rcx, ds:0[rax*4]
0x180003ec3  test    rcx, rcx
0x180003ec6  jz      short loc_180003F0E
0x180003ec8  mov     [rdi], rcx
0x180003ecb  mov     eax, [rcx]
0x180003ecd  inc     eax
0x180003ecf  mov     [rcx], eax
0x180003ed1  lea     rcx, [rsp+270h+var_238]
0x180003ed6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003edb  xor     ebx, ebx
0x180003edd  lea     rcx, [rsp+270h+var_240]
0x180003ee2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003ee7  mov     eax, ebx
0x180003ee9  mov     rcx, [rbp+170h+var_10]
0x180003ef0  xor     rcx, rsp; StackCookie
0x180003ef3  call    __security_check_cookie
0x180003ef8  lea     r11, [rsp+270h+var_s0]
0x180003f00  mov     rbx, [r11+20h]
0x180003f04  mov     rdi, [r11+28h]
0x180003f08  mov     rsp, r11
0x180003f0b  pop     rbp
0x180003f0c  retn
0x180003f0e  mov     r8, rdi
0x180003f11  lea     rdx, [rsp+270h+var_240]
0x180003f16  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180003f1b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003f20  mov     ebx, eax
0x180003f22  test    eax, eax
0x180003f24  jns     short loc_180003ED1
0x180003f26  mov     r9d, eax
0x180003f29  mov     edx, 137h
0x180003f2e  jmp     loc_180003E97
```
