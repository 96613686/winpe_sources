# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008358`
- end: `0x180008530`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008f1c`

## callees

- `0x180006538`
- `0x180006620`
- `0x180008358`
- `0x1800085b0`
- `0x180008610`
- `0x180008a84`
- `0x180008ee4`
- `0x1800187b0`
- `0x18002cf58`
- `0x1800303b8`
- `0x1800306a0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800083f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800083f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800083cf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800083cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008393`

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
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (__int64)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = v22;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180008358  mov     [rsp-8+arg_10], rbx
0x18000835d  mov     [rsp-8+arg_18], rsi
0x180008362  push    rbp
0x180008363  push    rdi
0x180008364  push    r14
0x180008366  lea     rbp, [rsp-170h]
0x18000836e  sub     rsp, 270h
0x180008375  mov     rax, cs:__security_cookie
0x18000837c  xor     rax, rsp
0x18000837f  mov     [rbp+180h+var_20], rax
0x180008386  mov     r14, rdx
0x180008389  mov     qword ptr [rdx], 0
0x180008390  mov     rbx, rcx
0x180008393  call    cs:__imp_GetCurrentProcessId
0x180008399  mov     [rsp+280h+var_258], rbx
0x18000839e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800083a5  mov     r9d, eax
0x1800083a8  mov     [rsp+280h+var_260], 130h; int
0x1800083b0  mov     edx, 104h; unsigned __int64
0x1800083b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800083ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800083bf  mov     r9d, 1F0001h; dwDesiredAccess
0x1800083c5  lea     rdx, [rsp+280h+Name]; lpName
0x1800083ca  xor     r8d, r8d; dwFlags
0x1800083cd  xor     ecx, ecx; lpMutexAttributes
0x1800083cf  call    cs:__imp_CreateMutexExW
0x1800083d5  mov     [rsp+280h+var_250], rax
0x1800083da  mov     rbx, rax
0x1800083dd  test    rax, rax
0x1800083e0  jnz     short loc_1800083EC
0x1800083e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800083e7  jmp     loc_180008509
0x1800083ec  xor     r8d, r8d; bAlertable
0x1800083ef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800083f2  mov     rcx, rbx; hHandle
0x1800083f5  call    cs:__imp_WaitForSingleObjectEx
0x1800083fb  cmp     eax, 102h
0x180008400  jz      short loc_18000841B
0x180008402  test    eax, 0FFFFFF7Fh
0x180008407  jz      short loc_180008416
0x180008409  mov     rcx, [rbp+188h]; this
0x180008410  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008416  mov     rsi, rbx
0x180008419  jmp     short loc_18000841D
0x18000841b  xor     esi, esi
0x18000841d  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180008422  mov     [rsp+280h+var_240], rsi
0x180008427  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000842c  mov     [rsp+280h+var_248], 0
0x180008435  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000843a  mov     edi, eax
0x18000843c  test    eax, eax
0x18000843e  jns     short loc_180008480
0x180008440  mov     rcx, [rbp+188h]; this
0x180008447  lea     r8, aWil; "wil"
0x18000844e  mov     r9d, eax; char *
0x180008451  mov     edx, 66h ; 'f'; void *
0x180008456  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000845b  mov     rcx, [rbp+188h]; this
0x180008462  lea     r8, aWil; "wil"
0x180008469  mov     r9d, edi; char *
0x18000846c  mov     edx, 6Fh ; 'o'; void *
0x180008471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008476  mov     r9d, edi
0x180008479  mov     edx, 12Eh
0x18000847e  jmp     short loc_1800084BD
0x180008480  mov     rax, [rsp+280h+var_248]
0x180008485  lea     rcx, ds:0[rax*4]
0x18000848d  test    rcx, rcx
0x180008490  jz      short loc_18000849D
0x180008492  mov     [r14], rcx
0x180008495  mov     eax, [rcx]
0x180008497  inc     eax
0x180008499  mov     [rcx], eax
0x18000849b  jmp     short loc_1800084ED
0x18000849d  mov     r8, r14
0x1800084a0  lea     rdx, [rsp+280h+var_250]
0x1800084a5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800084aa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800084af  mov     edi, eax
0x1800084b1  test    eax, eax
0x1800084b3  jns     short loc_1800084E8
0x1800084b5  mov     r9d, eax; char *
0x1800084b8  mov     edx, 137h; void *
0x1800084bd  mov     rcx, [rbp+188h]; this
0x1800084c4  lea     r8, aWil; "wil"
0x1800084cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084d0  lea     rcx, [rsp+280h+var_240]
0x1800084d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084da  lea     rcx, [rsp+280h+var_250]
0x1800084df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084e4  mov     eax, edi
0x1800084e6  jmp     short loc_180008509
0x1800084e8  mov     rbx, [rsp+280h+var_250]
0x1800084ed  test    rsi, rsi
0x1800084f0  jz      short loc_1800084FA
0x1800084f2  mov     rcx, rsi; this
0x1800084f5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800084fa  test    rbx, rbx
0x1800084fd  jz      short loc_180008507
0x1800084ff  mov     rcx, rbx; this
0x180008502  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008507  xor     eax, eax
0x180008509  mov     rcx, [rbp+180h+var_20]
0x180008510  xor     rcx, rsp; StackCookie
0x180008513  call    __security_check_cookie
0x180008518  lea     r11, [rsp+280h+var_10]
0x180008520  mov     rbx, [r11+30h]
0x180008524  mov     rsi, [r11+38h]
0x180008528  mov     rsp, r11
0x18000852b  pop     r14
0x18000852d  pop     rdi
0x18000852e  pop     rbp
0x18000852f  retn
```
