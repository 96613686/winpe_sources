# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007460`
- end: `0x1800076a6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800164a8`

## callees

- `0x180006538`
- `0x180006620`
- `0x180007460`
- `0x1800085b0`
- `0x180008610`
- `0x180008ee4`
- `0x1800187b0`
- `0x1800303b8`
- `0x180030570`
- `0x180031878`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007529`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007529`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800074c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800074c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e2`

## string_xrefs

- `0x180007694`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  const char *v8; // r9
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  wil::details *v13; // rdi
  int ValueInternal; // eax
  void *v15; // rdx
  unsigned int v16; // esi
  void *v17; // rdx
  _DWORD *v18; // rax
  void *v19; // rdx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-258h]
  int v23; // [rsp+20h] [rbp-258h]
  wil::details *v24; // [rsp+30h] [rbp-248h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v24 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v6;
  }
  v25 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (__int64)v10, &v25, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v16, v22);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v16, v23);
    if ( v13 )
      wil::details::ReleaseMutex(v13, v17);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    return v16;
  }
  v18 = (_DWORD *)(4 * v25);
  if ( 4 * v25 )
  {
    *a2 = v18;
    ++*v18;
LABEL_13:
    if ( v13 )
      wil::details::ReleaseMutex(v13, v15);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v8);
    return 0;
  }
  v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v6 = v24;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v20, 120);
  if ( v13 )
    wil::details::ReleaseMutex(v13, v19);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
  return v21;
}

```

## disassembly

```asm
0x180007460  push    rbx
0x180007462  push    rsi
0x180007463  push    r14
0x180007465  sub     rsp, 260h
0x18000746c  mov     rax, cs:__security_cookie
0x180007473  xor     rax, rsp
0x180007476  mov     [rsp+278h+var_28], rax
0x18000747e  xor     esi, esi
0x180007480  mov     r14, rdx
0x180007483  mov     [rdx], rsi
0x180007486  mov     rbx, rcx
0x180007489  call    cs:__imp_GetCurrentProcessId
0x18000748f  mov     [rsp+278h+var_250], rbx
0x180007494  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000749b  mov     r9d, eax
0x18000749e  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x1800074a6  mov     edx, 104h; unsigned __int64
0x1800074ab  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800074b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074b5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800074bb  lea     rdx, [rsp+278h+Name]; lpName
0x1800074c0  xor     r8d, r8d; dwFlags
0x1800074c3  xor     ecx, ecx; lpMutexAttributes
0x1800074c5  call    cs:__imp_CreateMutexExW
0x1800074cb  mov     [rsp+278h+var_248], rax
0x1800074d0  mov     rbx, rax
0x1800074d3  test    rax, rax
0x1800074d6  jnz     short loc_180007516
0x1800074d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800074dd  jmp     short loc_1800074FA
0x1800074df  mov     rcx, rbx; hObject
0x1800074e2  call    cs:__imp_CloseHandle
0x1800074e8  test    eax, eax
0x1800074ea  jz      loc_18000768C
0x1800074f0  xor     eax, eax
0x1800074f2  mov     rdi, [rsp+278h+arg_10]
0x1800074fa  mov     rcx, [rsp+278h+var_28]
0x180007502  xor     rcx, rsp; StackCookie
0x180007505  call    __security_check_cookie
0x18000750a  add     rsp, 260h
0x180007511  pop     r14
0x180007513  pop     rsi
0x180007514  pop     rbx
0x180007515  retn
0x180007516  xor     r8d, r8d; bAlertable
0x180007519  mov     [rsp+278h+arg_10], rdi
0x180007521  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180007526  mov     rcx, rbx; hHandle
0x180007529  call    cs:__imp_WaitForSingleObjectEx
0x18000752f  cmp     eax, 102h
0x180007534  jnz     loc_180007629
0x18000753a  mov     rdi, rsi
0x18000753d  lea     r8, [rsp+278h+var_240]; unsigned __int64 *
0x180007542  mov     [rsp+278h+var_240], rsi
0x180007547  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000754c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007551  mov     esi, eax
0x180007553  test    eax, eax
0x180007555  jns     short loc_1800075C5
0x180007557  mov     rcx, [rsp+278h]; this
0x18000755f  lea     r8, aWil; "wil"
0x180007566  mov     r9d, eax; char *
0x180007569  mov     edx, 66h ; 'f'; void *
0x18000756e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007573  mov     rcx, [rsp+278h]; this
0x18000757b  lea     r8, aWil; "wil"
0x180007582  mov     r9d, esi; char *
0x180007585  mov     edx, 6Fh ; 'o'; void *
0x18000758a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000758f  mov     rcx, [rsp+278h]; this
0x180007597  lea     r8, aWil; "wil"
0x18000759e  mov     r9d, esi; char *
0x1800075a1  mov     edx, 12Eh; void *
0x1800075a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075ab  test    rdi, rdi
0x1800075ae  jnz     loc_180007646
0x1800075b4  lea     rcx, [rsp+278h+var_248]
0x1800075b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800075be  mov     eax, esi
0x1800075c0  jmp     loc_1800074F2
0x1800075c5  mov     rax, [rsp+278h+var_240]
0x1800075ca  lea     rax, ds:0[rax*4]
0x1800075d2  test    rax, rax
0x1800075d5  jz      short loc_180007653
0x1800075d7  mov     [r14], rax
0x1800075da  mov     ecx, [rax]
0x1800075dc  inc     ecx
0x1800075de  mov     [rax], ecx
0x1800075e0  test    rdi, rdi
0x1800075e3  jnz     loc_18000767F
0x1800075e9  test    rbx, rbx
0x1800075ec  jz      loc_1800074F0
0x1800075f2  jmp     loc_1800074DF
0x1800075f7  mov     rcx, [rsp+278h]; this
0x1800075ff  lea     r8, aWil; "wil"
0x180007606  mov     r9d, ebx; char *
0x180007609  mov     edx, 137h; void *
0x18000760e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007613  test    rdi, rdi
0x180007616  jnz     short loc_180007675
0x180007618  lea     rcx, [rsp+278h+var_248]
0x18000761d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007622  mov     eax, ebx
0x180007624  jmp     loc_1800074F2
0x180007629  test    eax, 0FFFFFF7Fh
0x18000762e  jz      short loc_18000763E
0x180007630  mov     rcx, [rsp+278h]; this
0x180007638  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000763e  mov     rdi, rbx
0x180007641  jmp     loc_18000753D
0x180007646  mov     rcx, rdi; this
0x180007649  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000764e  jmp     loc_1800075B4
0x180007653  mov     r8, r14
0x180007656  lea     rdx, [rsp+278h+var_248]
0x18000765b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007660  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180007665  mov     ebx, eax
0x180007667  test    eax, eax
0x180007669  js      short loc_1800075F7
0x18000766b  mov     rbx, [rsp+278h+var_248]
0x180007670  jmp     loc_1800075E0
0x180007675  mov     rcx, rdi; this
0x180007678  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000767d  jmp     short loc_180007618
0x18000767f  mov     rcx, rdi; this
0x180007682  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180007687  jmp     loc_1800075E9
0x18000768c  mov     rcx, [rsp+278h]; this
0x180007694  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000769b  mov     edx, 0A0Bh; void *
0x1800076a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
