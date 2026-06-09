# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180043ab0`
- end: `0x180043cb8`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004ebfc`

## callees

- `0x180043ab0`
- `0x180043cc0`
- `0x180043d14`
- `0x180043dd4`
- `0x180044240`
- `0x180044274`
- `0x1800532d0`
- `0x180053bf4`
- `0x180053d50`
- `0x180054428`
- `0x18005a008`
- `0x18005b118`
- `0x1800966e0`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180043b66`
- `KERNEL32!WaitForSingleObjectEx` at `0x180043b66`
- `KERNEL32!CreateMutexExW` at `0x180043b36`
- `KERNEL32!CreateMutexExW` at `0x180043b36`
- `KERNEL32!GetCurrentProcessId` at `0x180043aeb`
- `KERNEL32!GetCurrentProcessId` at `0x180043aeb`

## string_xrefs

- `0x180043c5e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rdi
  DWORD v7; // eax
  bool v8; // dl
  char *v9; // r9
  wil::details *v10; // rsi
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // ebx
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  _DWORD *v20; // rcx
  int v21; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v22 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = v6;
  }
  v26 = v10;
  v25 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v25, (bool *)v9);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v23);
    v17 = v14;
    v18 = 302;
LABEL_6:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v16, (const char *)v17, v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return v14;
  }
  v20 = (_DWORD *)(4 * v25);
  if ( 4 * v25 )
  {
    *a2 = v20;
    ++*v20;
  }
  else
  {
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v14 = v21;
    if ( v21 < 0 )
    {
      v17 = (unsigned int)v21;
      v18 = 311;
      goto LABEL_6;
    }
    v6 = (wil::details *)hHandle;
  }
  if ( v10 )
    wil::details::ReleaseMutex(v10, v12);
  if ( v6 )
    wil::details::CloseHandle(v6, v12);
  return 0;
}

```

## disassembly

```asm
0x180043ab0  mov     [rsp-8+arg_10], rbx
0x180043ab5  mov     [rsp-8+arg_18], rsi
0x180043aba  push    rbp
0x180043abb  push    rdi
0x180043abc  push    r14
0x180043abe  lea     rbp, [rsp-170h]
0x180043ac6  sub     rsp, 270h
0x180043acd  mov     rax, cs:__security_cookie
0x180043ad4  xor     rax, rsp
0x180043ad7  mov     [rbp+180h+var_20], rax
0x180043ade  mov     r14, rdx
0x180043ae1  mov     qword ptr [rdx], 0
0x180043ae8  mov     rbx, rcx
0x180043aeb  call    cs:__imp_GetCurrentProcessId
0x180043af2  nop     dword ptr [rax+rax+00h]
0x180043af7  mov     [rsp+280h+var_258], rbx
0x180043afc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180043b03  mov     r9d, eax
0x180043b06  mov     [rsp+280h+var_260], 130h; int
0x180043b0e  mov     edx, 104h; unsigned __int64
0x180043b13  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180043b18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043b1d  mov     r9d, 1F0001h; dwDesiredAccess
0x180043b23  mov     [rsp+280h+hHandle], 0
0x180043b2c  xor     r8d, r8d; dwFlags
0x180043b2f  lea     rdx, [rsp+280h+Name]; lpName
0x180043b34  xor     ecx, ecx; lpMutexAttributes
0x180043b36  call    cs:__imp_CreateMutexExW
0x180043b3d  nop     dword ptr [rax+rax+00h]
0x180043b42  mov     rdx, rax
0x180043b45  lea     rcx, [rsp+280h+hHandle]
0x180043b4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180043b4f  mov     rdi, [rsp+280h+hHandle]
0x180043b54  test    rdi, rdi
0x180043b57  jz      loc_180043C20
0x180043b5d  xor     r8d, r8d; bAlertable
0x180043b60  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180043b63  mov     rcx, rdi; hHandle
0x180043b66  call    cs:__imp_WaitForSingleObjectEx
0x180043b6d  nop     dword ptr [rax+rax+00h]
0x180043b72  cmp     eax, 102h
0x180043b77  jnz     loc_180043C50
0x180043b7d  xor     esi, esi
0x180043b7f  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180043b84  mov     [rsp+280h+var_240], rsi
0x180043b89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180043b8e  mov     [rsp+280h+var_248], 0
0x180043b97  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180043b9c  mov     ebx, eax
0x180043b9e  test    eax, eax
0x180043ba0  jns     loc_180043C27
0x180043ba6  mov     rcx, [rbp+188h]; this
0x180043bad  mov     r9d, eax; char *
0x180043bb0  mov     edx, 66h ; 'f'; void *
0x180043bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043bba  mov     rcx, [rbp+188h]; this
0x180043bc1  mov     r9d, ebx; char *
0x180043bc4  mov     edx, 6Fh ; 'o'; void *
0x180043bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043bce  mov     r9d, ebx; char *
0x180043bd1  mov     edx, 12Eh; void *
0x180043bd6  mov     rcx, [rbp+188h]; this
0x180043bdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043be2  lea     rcx, [rsp+280h+var_240]
0x180043be7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043bec  lea     rcx, [rsp+280h+hHandle]
0x180043bf1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043bf6  mov     eax, ebx
0x180043bf8  mov     rcx, [rbp+180h+var_20]
0x180043bff  xor     rcx, rsp; StackCookie
0x180043c02  call    __security_check_cookie
0x180043c07  lea     r11, [rsp+280h+var_10]
0x180043c0f  mov     rbx, [r11+30h]
0x180043c13  mov     rsi, [r11+38h]
0x180043c17  mov     rsp, r11
0x180043c1a  pop     r14
0x180043c1c  pop     rdi
0x180043c1d  pop     rbp
0x180043c1e  retn
0x180043c20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043c25  jmp     short loc_180043BF8
0x180043c27  mov     rax, [rsp+280h+var_248]
0x180043c2c  lea     rcx, ds:0[rax*4]
0x180043c34  test    rcx, rcx
0x180043c37  jz      short loc_180043C78
0x180043c39  mov     [r14], rcx
0x180043c3c  mov     eax, [rcx]
0x180043c3e  inc     eax
0x180043c40  mov     [rcx], eax
0x180043c42  test    rsi, rsi
0x180043c45  jnz     short loc_180043CA4
0x180043c47  test    rdi, rdi
0x180043c4a  jnz     short loc_180043CAE
0x180043c4c  xor     eax, eax
0x180043c4e  jmp     short loc_180043BF8
0x180043c50  test    eax, 0FFFFFF7Fh
0x180043c55  jz      short loc_180043C70
0x180043c57  mov     rcx, [rbp+188h]; this
0x180043c5e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180043c65  mov     edx, 0E01h; void *
0x180043c6a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180043c70  mov     rsi, rdi
0x180043c73  jmp     loc_180043B7F
0x180043c78  mov     r8, r14
0x180043c7b  lea     rdx, [rsp+280h+hHandle]
0x180043c80  lea     rcx, [rsp+280h+Name]
0x180043c85  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180043c8a  mov     ebx, eax
0x180043c8c  test    eax, eax
0x180043c8e  jns     short loc_180043C9D
0x180043c90  mov     r9d, eax
0x180043c93  mov     edx, 137h
0x180043c98  jmp     loc_180043BD6
0x180043c9d  mov     rdi, [rsp+280h+hHandle]
0x180043ca2  jmp     short loc_180043C42
0x180043ca4  mov     rcx, rsi; this
0x180043ca7  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180043cac  jmp     short loc_180043C47
0x180043cae  mov     rcx, rdi; this
0x180043cb1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180043cb6  jmp     short loc_180043C4C
```
