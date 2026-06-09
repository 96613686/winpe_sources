# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006858`
- end: `0x180006a02`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800072c8`

## callees

- `0x180003290`
- `0x180005020`
- `0x180006704`
- `0x180006720`
- `0x180006858`
- `0x180007090`
- `0x180007534`
- `0x180007f7c`
- `0x180008138`
- `0x180008468`
- `0x180008558`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800068d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800068d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006890`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006858  mov     [rsp-8+arg_10], rbx
0x18000685d  mov     [rsp-8+arg_18], rdi
0x180006862  push    rbp
0x180006863  lea     rbp, [rsp-170h]
0x18000686b  sub     rsp, 270h
0x180006872  mov     rax, cs:__security_cookie
0x180006879  xor     rax, rsp
0x18000687c  mov     [rbp+170h+var_10], rax
0x180006883  mov     rdi, rdx
0x180006886  mov     qword ptr [rdx], 0
0x18000688d  mov     rbx, rcx
0x180006890  call    cs:__imp_GetCurrentProcessId
0x180006896  mov     [rsp+270h+var_248], rbx
0x18000689b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800068a2  mov     r9d, eax
0x1800068a5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800068ad  mov     edx, 104h; unsigned __int64
0x1800068b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800068b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800068bc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800068c2  mov     [rsp+270h+var_240], 0
0x1800068cb  xor     r8d, r8d; dwFlags
0x1800068ce  lea     rdx, [rsp+270h+Name]; lpName
0x1800068d3  xor     ecx, ecx; lpMutexAttributes
0x1800068d5  call    cs:__imp_CreateMutexExW
0x1800068db  mov     rdx, rax
0x1800068de  lea     rcx, [rsp+270h+var_240]
0x1800068e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800068e8  cmp     [rsp+270h+var_240], 0
0x1800068ee  jnz     short loc_1800068FC
0x1800068f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800068f5  mov     ebx, eax
0x1800068f7  jmp     loc_1800069AD
0x1800068fc  lea     rdx, [rsp+270h+var_238]
0x180006901  lea     rcx, [rsp+270h+var_240]
0x180006906  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000690b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180006910  mov     [rsp+270h+var_230], 0
0x180006919  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000691e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006923  mov     ebx, eax
0x180006925  test    eax, eax
0x180006927  jns     short loc_180006986
0x180006929  mov     rcx, [rbp+178h]; this
0x180006930  lea     r8, aWil; "wil"
0x180006937  mov     r9d, eax; char *
0x18000693a  mov     edx, 66h ; 'f'; void *
0x18000693f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006944  mov     rcx, [rbp+178h]; this
0x18000694b  lea     r8, aWil; "wil"
0x180006952  mov     r9d, ebx; char *
0x180006955  mov     edx, 6Fh ; 'o'; void *
0x18000695a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000695f  mov     r9d, ebx; char *
0x180006962  mov     edx, 12Eh; void *
0x180006967  mov     rcx, [rbp+178h]; this
0x18000696e  lea     r8, aWil; "wil"
0x180006975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000697a  lea     rcx, [rsp+270h+var_238]
0x18000697f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006984  jmp     short loc_1800069AD
0x180006986  mov     rax, [rsp+270h+var_230]
0x18000698b  lea     rcx, ds:0[rax*4]
0x180006993  test    rcx, rcx
0x180006996  jz      short loc_1800069DD
0x180006998  mov     [rdi], rcx
0x18000699b  mov     eax, [rcx]
0x18000699d  inc     eax
0x18000699f  mov     [rcx], eax
0x1800069a1  lea     rcx, [rsp+270h+var_238]
0x1800069a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800069ab  xor     ebx, ebx
0x1800069ad  lea     rcx, [rsp+270h+var_240]
0x1800069b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800069b7  mov     eax, ebx
0x1800069b9  mov     rcx, [rbp+170h+var_10]
0x1800069c0  xor     rcx, rsp; StackCookie
0x1800069c3  call    __security_check_cookie
0x1800069c8  lea     r11, [rsp+270h+var_s0]
0x1800069d0  mov     rbx, [r11+20h]
0x1800069d4  mov     rdi, [r11+28h]
0x1800069d8  mov     rsp, r11
0x1800069db  pop     rbp
0x1800069dc  retn
0x1800069dd  mov     r8, rdi
0x1800069e0  lea     rdx, [rsp+270h+var_240]
0x1800069e5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800069ea  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800069ef  mov     ebx, eax
0x1800069f1  test    eax, eax
0x1800069f3  jns     short loc_1800069A1
0x1800069f5  mov     r9d, eax
0x1800069f8  mov     edx, 137h
0x1800069fd  jmp     loc_180006967
```
