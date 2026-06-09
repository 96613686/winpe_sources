# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005644`
- end: `0x180005828`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800055e8`

## callees

- `0x180005644`
- `0x180005830`
- `0x180005894`
- `0x180005cbc`
- `0x180008aa8`
- `0x180009d5c`
- `0x18000a3fc`
- `0x18000a600`
- `0x18000a61c`
- `0x18000ac00`
- `0x18000b410`
- `0x18000d450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800056bb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800056bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800056de`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800056de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000567f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000567f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // edi
  _DWORD *v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v27; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v23 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v25 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v27 = v12;
  v26 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v26, (bool *)v11);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v18, (const char *)v16, v24);
    v20 = v16;
    v21 = 302;
    goto LABEL_15;
  }
  v17 = (_DWORD *)(4 * v26);
  if ( !(4 * v26) )
  {
    v22 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v16 = v22;
    if ( v22 >= 0 )
    {
      v6 = v25;
      goto LABEL_9;
    }
    v20 = (unsigned int)v22;
    v21 = 311;
LABEL_15:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v21, v19, (const char *)v20, v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    return v16;
  }
  *a2 = v17;
  ++*v17;
LABEL_9:
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180005644  mov     [rsp-8+arg_10], rbx
0x180005649  mov     [rsp-8+arg_18], rsi
0x18000564e  push    rbp
0x18000564f  push    rdi
0x180005650  push    r14
0x180005652  lea     rbp, [rsp-170h]
0x18000565a  sub     rsp, 270h
0x180005661  mov     rax, cs:__security_cookie
0x180005668  xor     rax, rsp
0x18000566b  mov     [rbp+180h+var_20], rax
0x180005672  mov     r14, rdx
0x180005675  mov     qword ptr [rdx], 0
0x18000567c  mov     rbx, rcx
0x18000567f  call    cs:__imp_GetCurrentProcessId
0x180005685  mov     [rsp+280h+var_258], rbx
0x18000568a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005691  mov     r9d, eax
0x180005694  mov     [rsp+280h+var_260], 130h; int
0x18000569c  mov     edx, 104h; unsigned __int64
0x1800056a1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800056a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800056ab  mov     r9d, 1F0001h; dwDesiredAccess
0x1800056b1  lea     rdx, [rsp+280h+Name]; lpName
0x1800056b6  xor     r8d, r8d; dwFlags
0x1800056b9  xor     ecx, ecx; lpMutexAttributes
0x1800056bb  call    cs:__imp_CreateMutexExW
0x1800056c1  mov     [rsp+280h+var_250], rax
0x1800056c6  mov     rbx, rax
0x1800056c9  test    rax, rax
0x1800056cc  jnz     short loc_1800056D5
0x1800056ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800056d3  jmp     short loc_180005753
0x1800056d5  xor     r8d, r8d; bAlertable
0x1800056d8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800056db  mov     rcx, rbx; hHandle
0x1800056de  call    cs:__imp_WaitForSingleObjectEx
0x1800056e4  cmp     eax, 102h
0x1800056e9  jz      loc_1800057DB
0x1800056ef  test    eax, 0FFFFFF7Fh
0x1800056f4  jnz     loc_1800057CE
0x1800056fa  mov     rsi, rbx
0x1800056fd  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180005702  mov     [rsp+280h+var_240], rsi
0x180005707  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000570c  mov     [rsp+280h+var_248], 0
0x180005715  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000571a  mov     edi, eax
0x18000571c  test    eax, eax
0x18000571e  js      short loc_18000577A
0x180005720  mov     rax, [rsp+280h+var_248]
0x180005725  lea     rcx, ds:0[rax*4]
0x18000572d  test    rcx, rcx
0x180005730  jz      loc_1800057E2
0x180005736  mov     [r14], rcx
0x180005739  mov     eax, [rcx]
0x18000573b  inc     eax
0x18000573d  mov     [rcx], eax
0x18000573f  test    rsi, rsi
0x180005742  jnz     loc_18000580E
0x180005748  test    rbx, rbx
0x18000574b  jnz     loc_18000581B
0x180005751  xor     eax, eax
0x180005753  mov     rcx, [rbp+180h+var_20]
0x18000575a  xor     rcx, rsp; StackCookie
0x18000575d  call    __security_check_cookie
0x180005762  lea     r11, [rsp+280h+var_10]
0x18000576a  mov     rbx, [r11+30h]
0x18000576e  mov     rsi, [r11+38h]
0x180005772  mov     rsp, r11
0x180005775  pop     r14
0x180005777  pop     rdi
0x180005778  pop     rbp
0x180005779  retn
0x18000577a  mov     rcx, [rbp+188h]; this
0x180005781  mov     r9d, edi; char *
0x180005784  mov     edx, 66h ; 'f'; void *
0x180005789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000578e  mov     rcx, [rbp+188h]; this
0x180005795  mov     r9d, edi; char *
0x180005798  mov     edx, 6Fh ; 'o'; void *
0x18000579d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057a2  mov     r9d, edi; char *
0x1800057a5  mov     edx, 12Eh; void *
0x1800057aa  mov     rcx, [rbp+188h]; this
0x1800057b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057b6  lea     rcx, [rsp+280h+var_240]
0x1800057bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800057c0  lea     rcx, [rsp+280h+var_250]
0x1800057c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800057ca  mov     eax, edi
0x1800057cc  jmp     short loc_180005753
0x1800057ce  mov     rcx, [rbp+188h]; this
0x1800057d5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800057db  xor     esi, esi
0x1800057dd  jmp     loc_1800056FD
0x1800057e2  mov     r8, r14
0x1800057e5  lea     rdx, [rsp+280h+var_250]
0x1800057ea  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800057ef  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800057f4  mov     edi, eax
0x1800057f6  test    eax, eax
0x1800057f8  jns     short loc_180005804
0x1800057fa  mov     r9d, eax
0x1800057fd  mov     edx, 137h
0x180005802  jmp     short loc_1800057AA
0x180005804  mov     rbx, [rsp+280h+var_250]
0x180005809  jmp     loc_18000573F
0x18000580e  mov     rcx, rsi; this
0x180005811  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005816  jmp     loc_180005748
0x18000581b  mov     rcx, rbx; this
0x18000581e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005823  jmp     loc_180005751
```
