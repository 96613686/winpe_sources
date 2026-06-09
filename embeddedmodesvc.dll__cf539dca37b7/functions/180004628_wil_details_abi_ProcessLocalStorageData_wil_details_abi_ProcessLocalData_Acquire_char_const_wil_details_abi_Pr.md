# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004628`
- end: `0x1800047d2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800051b0`

## callees

- `0x180002b10`
- `0x1800044e0`
- `0x1800044fc`
- `0x180004628`
- `0x180004ec8`
- `0x180005924`
- `0x180005fc4`
- `0x18000655c`
- `0x1800066c8`
- `0x180006b10`
- `0x180006c14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800046a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800046a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004660`

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
0x180004628  mov     [rsp-8+arg_10], rbx
0x18000462d  mov     [rsp-8+arg_18], rdi
0x180004632  push    rbp
0x180004633  lea     rbp, [rsp-170h]
0x18000463b  sub     rsp, 270h
0x180004642  mov     rax, cs:__security_cookie
0x180004649  xor     rax, rsp
0x18000464c  mov     [rbp+170h+var_10], rax
0x180004653  mov     rdi, rdx
0x180004656  mov     qword ptr [rdx], 0
0x18000465d  mov     rbx, rcx
0x180004660  call    cs:__imp_GetCurrentProcessId
0x180004666  mov     [rsp+270h+var_248], rbx
0x18000466b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004672  mov     r9d, eax
0x180004675  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000467d  mov     edx, 104h; unsigned __int64
0x180004682  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004687  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000468c  mov     r9d, 1F0001h; dwDesiredAccess
0x180004692  mov     [rsp+270h+var_240], 0
0x18000469b  xor     r8d, r8d; dwFlags
0x18000469e  lea     rdx, [rsp+270h+Name]; lpName
0x1800046a3  xor     ecx, ecx; lpMutexAttributes
0x1800046a5  call    cs:__imp_CreateMutexExW
0x1800046ab  mov     rdx, rax
0x1800046ae  lea     rcx, [rsp+270h+var_240]
0x1800046b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800046b8  cmp     [rsp+270h+var_240], 0
0x1800046be  jnz     short loc_1800046CC
0x1800046c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800046c5  mov     ebx, eax
0x1800046c7  jmp     loc_18000477D
0x1800046cc  lea     rdx, [rsp+270h+var_238]
0x1800046d1  lea     rcx, [rsp+270h+var_240]
0x1800046d6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800046db  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800046e0  mov     [rsp+270h+var_230], 0
0x1800046e9  lea     rcx, [rsp+270h+Name]; pszSrc
0x1800046ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800046f3  mov     ebx, eax
0x1800046f5  test    eax, eax
0x1800046f7  jns     short loc_180004756
0x1800046f9  mov     rcx, [rbp+178h]; this
0x180004700  lea     r8, aWil; "wil"
0x180004707  mov     r9d, eax; char *
0x18000470a  mov     edx, 66h ; 'f'; void *
0x18000470f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004714  mov     rcx, [rbp+178h]; this
0x18000471b  lea     r8, aWil; "wil"
0x180004722  mov     r9d, ebx; char *
0x180004725  mov     edx, 6Fh ; 'o'; void *
0x18000472a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000472f  mov     r9d, ebx; char *
0x180004732  mov     edx, 12Eh; void *
0x180004737  mov     rcx, [rbp+178h]; this
0x18000473e  lea     r8, aWil; "wil"
0x180004745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000474a  lea     rcx, [rsp+270h+var_238]
0x18000474f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004754  jmp     short loc_18000477D
0x180004756  mov     rax, [rsp+270h+var_230]
0x18000475b  lea     rcx, ds:0[rax*4]
0x180004763  test    rcx, rcx
0x180004766  jz      short loc_1800047AD
0x180004768  mov     [rdi], rcx
0x18000476b  mov     eax, [rcx]
0x18000476d  inc     eax
0x18000476f  mov     [rcx], eax
0x180004771  lea     rcx, [rsp+270h+var_238]
0x180004776  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000477b  xor     ebx, ebx
0x18000477d  lea     rcx, [rsp+270h+var_240]
0x180004782  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004787  mov     eax, ebx
0x180004789  mov     rcx, [rbp+170h+var_10]
0x180004790  xor     rcx, rsp; StackCookie
0x180004793  call    __security_check_cookie
0x180004798  lea     r11, [rsp+270h+var_s0]
0x1800047a0  mov     rbx, [r11+20h]
0x1800047a4  mov     rdi, [r11+28h]
0x1800047a8  mov     rsp, r11
0x1800047ab  pop     rbp
0x1800047ac  retn
0x1800047ad  mov     r8, rdi
0x1800047b0  lea     rdx, [rsp+270h+var_240]
0x1800047b5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800047ba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800047bf  mov     ebx, eax
0x1800047c1  test    eax, eax
0x1800047c3  jns     short loc_180004771
0x1800047c5  mov     r9d, eax
0x1800047c8  mov     edx, 137h
0x1800047cd  jmp     loc_180004737
```
