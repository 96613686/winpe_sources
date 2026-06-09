# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180042888`
- end: `0x180042a7d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004dfdc`

## callees

- `0x180042888`
- `0x180042a84`
- `0x180042ad8`
- `0x180042b90`
- `0x180042fb8`
- `0x180042fec`
- `0x18005252c`
- `0x180052d98`
- `0x180052ef4`
- `0x1800535ec`
- `0x18005902c`
- `0x18005a08c`
- `0x1800942d0`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180042932`
- `KERNEL32!WaitForSingleObjectEx` at `0x180042932`
- `KERNEL32!CreateMutexExW` at `0x180042908`
- `KERNEL32!CreateMutexExW` at `0x180042908`
- `KERNEL32!GetCurrentProcessId` at `0x1800428c3`
- `KERNEL32!GetCurrentProcessId` at `0x1800428c3`

## string_xrefs

- `0x180042a23`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180042888  mov     [rsp-8+arg_10], rbx
0x18004288d  mov     [rsp-8+arg_18], rsi
0x180042892  push    rbp
0x180042893  push    rdi
0x180042894  push    r14
0x180042896  lea     rbp, [rsp-170h]
0x18004289e  sub     rsp, 270h
0x1800428a5  mov     rax, cs:__security_cookie
0x1800428ac  xor     rax, rsp
0x1800428af  mov     [rbp+180h+var_20], rax
0x1800428b6  mov     r14, rdx
0x1800428b9  mov     qword ptr [rdx], 0
0x1800428c0  mov     rbx, rcx
0x1800428c3  call    cs:__imp_GetCurrentProcessId
0x1800428c9  mov     [rsp+280h+var_258], rbx
0x1800428ce  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800428d5  mov     r9d, eax
0x1800428d8  mov     [rsp+280h+var_260], 130h; int
0x1800428e0  mov     edx, 104h; unsigned __int64
0x1800428e5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800428ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800428ef  mov     r9d, 1F0001h; dwDesiredAccess
0x1800428f5  mov     [rsp+280h+hHandle], 0
0x1800428fe  xor     r8d, r8d; dwFlags
0x180042901  lea     rdx, [rsp+280h+Name]; lpName
0x180042906  xor     ecx, ecx; lpMutexAttributes
0x180042908  call    cs:__imp_CreateMutexExW
0x18004290e  mov     rdx, rax
0x180042911  lea     rcx, [rsp+280h+hHandle]
0x180042916  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004291b  mov     rdi, [rsp+280h+hHandle]
0x180042920  test    rdi, rdi
0x180042923  jz      loc_1800429E5
0x180042929  xor     r8d, r8d; bAlertable
0x18004292c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004292f  mov     rcx, rdi; hHandle
0x180042932  call    cs:__imp_WaitForSingleObjectEx
0x180042938  cmp     eax, 102h
0x18004293d  jnz     loc_180042A15
0x180042943  xor     esi, esi
0x180042945  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004294a  mov     [rsp+280h+var_240], rsi
0x18004294f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180042954  mov     [rsp+280h+var_248], 0
0x18004295d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180042962  mov     ebx, eax
0x180042964  test    eax, eax
0x180042966  jns     loc_1800429EC
0x18004296c  mov     rcx, [rbp+188h]; this
0x180042973  mov     r9d, eax; char *
0x180042976  mov     edx, 66h ; 'f'; void *
0x18004297b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042980  mov     rcx, [rbp+188h]; this
0x180042987  mov     r9d, ebx; char *
0x18004298a  mov     edx, 6Fh ; 'o'; void *
0x18004298f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042994  mov     r9d, ebx; char *
0x180042997  mov     edx, 12Eh; void *
0x18004299c  mov     rcx, [rbp+188h]; this
0x1800429a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429a8  lea     rcx, [rsp+280h+var_240]
0x1800429ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800429b2  lea     rcx, [rsp+280h+hHandle]
0x1800429b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800429bc  mov     eax, ebx
0x1800429be  mov     rcx, [rbp+180h+var_20]
0x1800429c5  xor     rcx, rsp; StackCookie
0x1800429c8  call    __security_check_cookie
0x1800429cd  lea     r11, [rsp+280h+var_10]
0x1800429d5  mov     rbx, [r11+30h]
0x1800429d9  mov     rsi, [r11+38h]
0x1800429dd  mov     rsp, r11
0x1800429e0  pop     r14
0x1800429e2  pop     rdi
0x1800429e3  pop     rbp
0x1800429e4  retn
0x1800429e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800429ea  jmp     short loc_1800429BE
0x1800429ec  mov     rax, [rsp+280h+var_248]
0x1800429f1  lea     rcx, ds:0[rax*4]
0x1800429f9  test    rcx, rcx
0x1800429fc  jz      short loc_180042A3D
0x1800429fe  mov     [r14], rcx
0x180042a01  mov     eax, [rcx]
0x180042a03  inc     eax
0x180042a05  mov     [rcx], eax
0x180042a07  test    rsi, rsi
0x180042a0a  jnz     short loc_180042A69
0x180042a0c  test    rdi, rdi
0x180042a0f  jnz     short loc_180042A73
0x180042a11  xor     eax, eax
0x180042a13  jmp     short loc_1800429BE
0x180042a15  test    eax, 0FFFFFF7Fh
0x180042a1a  jz      short loc_180042A35
0x180042a1c  mov     rcx, [rbp+188h]; this
0x180042a23  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180042a2a  mov     edx, 0E01h; void *
0x180042a2f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180042a35  mov     rsi, rdi
0x180042a38  jmp     loc_180042945
0x180042a3d  mov     r8, r14
0x180042a40  lea     rdx, [rsp+280h+hHandle]
0x180042a45  lea     rcx, [rsp+280h+Name]
0x180042a4a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180042a4f  mov     ebx, eax
0x180042a51  test    eax, eax
0x180042a53  jns     short loc_180042A62
0x180042a55  mov     r9d, eax
0x180042a58  mov     edx, 137h
0x180042a5d  jmp     loc_18004299C
0x180042a62  mov     rdi, [rsp+280h+hHandle]
0x180042a67  jmp     short loc_180042A07
0x180042a69  mov     rcx, rsi; this
0x180042a6c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180042a71  jmp     short loc_180042A0C
0x180042a73  mov     rcx, rdi; this
0x180042a76  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180042a7b  jmp     short loc_180042A11
```
