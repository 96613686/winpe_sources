# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800088d8`
- end: `0x180008a82`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000afe4`

## callees

- `0x180002270`
- `0x18000817c`
- `0x180008198`
- `0x1800088d8`
- `0x18000ac40`
- `0x18000cd18`
- `0x180010f44`
- `0x180012458`
- `0x1800127c8`
- `0x180013c50`
- `0x180013f78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008955`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008910`

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
0x1800088d8  mov     [rsp-8+arg_10], rbx
0x1800088dd  mov     [rsp-8+arg_18], rdi
0x1800088e2  push    rbp
0x1800088e3  lea     rbp, [rsp-170h]
0x1800088eb  sub     rsp, 270h
0x1800088f2  mov     rax, cs:__security_cookie
0x1800088f9  xor     rax, rsp
0x1800088fc  mov     [rbp+170h+var_10], rax
0x180008903  mov     rdi, rdx
0x180008906  mov     qword ptr [rdx], 0
0x18000890d  mov     rbx, rcx
0x180008910  call    cs:__imp_GetCurrentProcessId
0x180008916  mov     [rsp+270h+var_248], rbx
0x18000891b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008922  mov     r9d, eax
0x180008925  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000892d  mov     edx, 104h; unsigned __int64
0x180008932  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008937  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000893c  mov     r9d, 1F0001h; dwDesiredAccess
0x180008942  mov     [rsp+270h+var_240], 0
0x18000894b  xor     r8d, r8d; dwFlags
0x18000894e  lea     rdx, [rsp+270h+Name]; lpName
0x180008953  xor     ecx, ecx; lpMutexAttributes
0x180008955  call    cs:__imp_CreateMutexExW
0x18000895b  mov     rdx, rax
0x18000895e  lea     rcx, [rsp+270h+var_240]
0x180008963  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008968  cmp     [rsp+270h+var_240], 0
0x18000896e  jnz     short loc_18000897C
0x180008970  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008975  mov     ebx, eax
0x180008977  jmp     loc_180008A2D
0x18000897c  lea     rdx, [rsp+270h+var_238]
0x180008981  lea     rcx, [rsp+270h+var_240]
0x180008986  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000898b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180008990  mov     [rsp+270h+var_230], 0
0x180008999  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000899e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800089a3  mov     ebx, eax
0x1800089a5  test    eax, eax
0x1800089a7  jns     short loc_180008A06
0x1800089a9  mov     rcx, [rbp+178h]; this
0x1800089b0  lea     r8, aWil; "wil"
0x1800089b7  mov     r9d, eax; char *
0x1800089ba  mov     edx, 66h ; 'f'; void *
0x1800089bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089c4  mov     rcx, [rbp+178h]; this
0x1800089cb  lea     r8, aWil; "wil"
0x1800089d2  mov     r9d, ebx; char *
0x1800089d5  mov     edx, 6Fh ; 'o'; void *
0x1800089da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089df  mov     r9d, ebx; char *
0x1800089e2  mov     edx, 12Eh; void *
0x1800089e7  mov     rcx, [rbp+178h]; this
0x1800089ee  lea     r8, aWil; "wil"
0x1800089f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089fa  lea     rcx, [rsp+270h+var_238]
0x1800089ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008a04  jmp     short loc_180008A2D
0x180008a06  mov     rax, [rsp+270h+var_230]
0x180008a0b  lea     rcx, ds:0[rax*4]
0x180008a13  test    rcx, rcx
0x180008a16  jz      short loc_180008A5D
0x180008a18  mov     [rdi], rcx
0x180008a1b  mov     eax, [rcx]
0x180008a1d  inc     eax
0x180008a1f  mov     [rcx], eax
0x180008a21  lea     rcx, [rsp+270h+var_238]
0x180008a26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008a2b  xor     ebx, ebx
0x180008a2d  lea     rcx, [rsp+270h+var_240]
0x180008a32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008a37  mov     eax, ebx
0x180008a39  mov     rcx, [rbp+170h+var_10]
0x180008a40  xor     rcx, rsp; StackCookie
0x180008a43  call    __security_check_cookie
0x180008a48  lea     r11, [rsp+270h+var_s0]
0x180008a50  mov     rbx, [r11+20h]
0x180008a54  mov     rdi, [r11+28h]
0x180008a58  mov     rsp, r11
0x180008a5b  pop     rbp
0x180008a5c  retn
0x180008a5d  mov     r8, rdi
0x180008a60  lea     rdx, [rsp+270h+var_240]
0x180008a65  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008a6a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008a6f  mov     ebx, eax
0x180008a71  test    eax, eax
0x180008a73  jns     short loc_180008A21
0x180008a75  mov     r9d, eax
0x180008a78  mov     edx, 137h
0x180008a7d  jmp     loc_1800089E7
```
