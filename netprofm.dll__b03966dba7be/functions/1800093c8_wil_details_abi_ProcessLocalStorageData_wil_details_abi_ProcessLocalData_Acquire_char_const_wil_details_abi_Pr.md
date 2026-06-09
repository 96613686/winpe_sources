# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800093c8`
- end: `0x1800095b3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `491`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a33c`

## callees

- `0x1800093c8`
- `0x1800095bc`
- `0x180009634`
- `0x180009688`
- `0x180009af0`
- `0x18000ba8c`
- `0x18000c5d4`
- `0x18000c7a8`
- `0x18000c818`
- `0x18000c944`
- `0x1800120d0`
- `0x180018804`
- `0x180019fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009448`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009448`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009478`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009403`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
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
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
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
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = (wil::details *)hHandle;
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
0x1800093c8  mov     [rsp-8+arg_10], rbx
0x1800093cd  mov     [rsp-8+arg_18], rsi
0x1800093d2  push    rbp
0x1800093d3  push    rdi
0x1800093d4  push    r14
0x1800093d6  lea     rbp, [rsp-170h]
0x1800093de  sub     rsp, 270h
0x1800093e5  mov     rax, cs:__security_cookie
0x1800093ec  xor     rax, rsp
0x1800093ef  mov     [rbp+180h+var_20], rax
0x1800093f6  mov     r14, rdx
0x1800093f9  mov     qword ptr [rdx], 0
0x180009400  mov     rbx, rcx
0x180009403  call    cs:__imp_GetCurrentProcessId
0x180009409  mov     [rsp+280h+var_258], rbx
0x18000940e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009415  mov     r9d, eax
0x180009418  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180009420  mov     edx, 104h; unsigned __int64
0x180009425  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000942a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000942f  mov     r9d, 1F0001h; dwDesiredAccess
0x180009435  mov     [rsp+280h+hHandle], 0
0x18000943e  xor     r8d, r8d; dwFlags
0x180009441  lea     rdx, [rsp+280h+Name]; lpName
0x180009446  xor     ecx, ecx; lpMutexAttributes
0x180009448  call    cs:__imp_CreateMutexExW
0x18000944e  mov     rdx, rax
0x180009451  lea     rcx, [rsp+280h+hHandle]
0x180009456  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000945b  mov     rbx, [rsp+280h+hHandle]
0x180009460  test    rbx, rbx
0x180009463  jnz     short loc_18000946F
0x180009465  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000946a  jmp     loc_18000958C
0x18000946f  xor     r8d, r8d; bAlertable
0x180009472  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009475  mov     rcx, rbx; hHandle
0x180009478  call    cs:__imp_WaitForSingleObjectEx
0x18000947e  cmp     eax, 102h
0x180009483  jz      short loc_18000949E
0x180009485  test    eax, 0FFFFFF7Fh
0x18000948a  jz      short loc_180009499
0x18000948c  mov     rcx, [rbp+188h]; this
0x180009493  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009499  mov     rsi, rbx
0x18000949c  jmp     short loc_1800094A0
0x18000949e  xor     esi, esi
0x1800094a0  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800094a5  mov     [rsp+280h+var_240], rsi
0x1800094aa  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800094af  mov     [rsp+280h+var_248], 0
0x1800094b8  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800094bd  mov     edi, eax
0x1800094bf  test    eax, eax
0x1800094c1  jns     short loc_180009503
0x1800094c3  mov     rcx, [rbp+188h]; this
0x1800094ca  lea     r8, aWil; "wil"
0x1800094d1  mov     r9d, eax; char *
0x1800094d4  mov     edx, 66h ; 'f'; void *
0x1800094d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094de  mov     rcx, [rbp+188h]; this
0x1800094e5  lea     r8, aWil; "wil"
0x1800094ec  mov     r9d, edi; char *
0x1800094ef  mov     edx, 6Fh ; 'o'; void *
0x1800094f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094f9  mov     r9d, edi
0x1800094fc  mov     edx, 12Eh
0x180009501  jmp     short loc_180009540
0x180009503  mov     rax, [rsp+280h+var_248]
0x180009508  lea     rcx, ds:0[rax*4]
0x180009510  test    rcx, rcx
0x180009513  jz      short loc_180009520
0x180009515  mov     [r14], rcx
0x180009518  mov     eax, [rcx]
0x18000951a  inc     eax
0x18000951c  mov     [rcx], eax
0x18000951e  jmp     short loc_180009570
0x180009520  mov     r8, r14
0x180009523  lea     rdx, [rsp+280h+hHandle]
0x180009528  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000952d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009532  mov     edi, eax
0x180009534  test    eax, eax
0x180009536  jns     short loc_18000956B
0x180009538  mov     r9d, eax; char *
0x18000953b  mov     edx, 137h; void *
0x180009540  mov     rcx, [rbp+188h]; this
0x180009547  lea     r8, aWil; "wil"
0x18000954e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009553  lea     rcx, [rsp+280h+var_240]
0x180009558  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000955d  lea     rcx, [rsp+280h+hHandle]
0x180009562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009567  mov     eax, edi
0x180009569  jmp     short loc_18000958C
0x18000956b  mov     rbx, [rsp+280h+hHandle]
0x180009570  test    rsi, rsi
0x180009573  jz      short loc_18000957D
0x180009575  mov     rcx, rsi; this
0x180009578  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000957d  test    rbx, rbx
0x180009580  jz      short loc_18000958A
0x180009582  mov     rcx, rbx; this
0x180009585  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000958a  xor     eax, eax
0x18000958c  mov     rcx, [rbp+180h+var_20]
0x180009593  xor     rcx, rsp; StackCookie
0x180009596  call    __security_check_cookie
0x18000959b  lea     r11, [rsp+280h+var_10]
0x1800095a3  mov     rbx, [r11+30h]
0x1800095a7  mov     rsi, [r11+38h]
0x1800095ab  mov     rsp, r11
0x1800095ae  pop     r14
0x1800095b0  pop     rdi
0x1800095b1  pop     rbp
0x1800095b2  retn
```
