# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800513f0`
- end: `0x18005162f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180050c8c`

## callees

- `0x18002568c`
- `0x180025dd4`
- `0x180050f30`
- `0x180050f4c`
- `0x1800513c4`
- `0x1800513f0`
- `0x180051638`
- `0x1800627fc`
- `0x180068dfc`
- `0x18006946c`
- `0x18006c38c`
- `0x18006ed20`
- `0x180072868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051470`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180051470`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800514ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800514ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005142b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005142b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v17 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v17;
      ++*v17;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v19;
      }
      v6 = (wil::details *)hHandle;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v21);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
}

```

## disassembly

```asm
0x1800513f0  mov     [rsp-8+arg_10], rbx
0x1800513f5  mov     [rsp-8+arg_18], rsi
0x1800513fa  push    rbp
0x1800513fb  push    rdi
0x1800513fc  push    r14
0x1800513fe  lea     rbp, [rsp-170h]
0x180051406  sub     rsp, 270h
0x18005140d  mov     rax, cs:__security_cookie
0x180051414  xor     rax, rsp
0x180051417  mov     [rbp+180h+var_20], rax
0x18005141e  mov     r14, rdx
0x180051421  mov     qword ptr [rdx], 0
0x180051428  mov     rbx, rcx
0x18005142b  call    cs:__imp_GetCurrentProcessId
0x180051431  mov     [rsp+280h+var_258], rbx
0x180051436  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005143d  mov     r9d, eax
0x180051440  mov     [rsp+280h+var_260], 130h; int
0x180051448  mov     edx, 104h; unsigned __int64
0x18005144d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180051452  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051457  mov     r9d, 1F0001h; dwDesiredAccess
0x18005145d  mov     [rsp+280h+hHandle], 0
0x180051466  xor     r8d, r8d; dwFlags
0x180051469  lea     rdx, [rsp+280h+Name]; lpName
0x18005146e  xor     ecx, ecx; lpMutexAttributes
0x180051470  call    cs:__imp_CreateMutexExW
0x180051476  mov     rdx, rax
0x180051479  lea     rcx, [rsp+280h+hHandle]
0x18005147e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051483  mov     rbx, [rsp+280h+hHandle]
0x180051488  test    rbx, rbx
0x18005148b  jnz     short loc_1800514C5
0x18005148d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180051492  jmp     short loc_18005149E
0x180051494  mov     rcx, rbx; this
0x180051497  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005149c  xor     eax, eax
0x18005149e  mov     rcx, [rbp+180h+var_20]
0x1800514a5  xor     rcx, rsp; StackCookie
0x1800514a8  call    __security_check_cookie
0x1800514ad  lea     r11, [rsp+280h+var_10]
0x1800514b5  mov     rbx, [r11+30h]
0x1800514b9  mov     rsi, [r11+38h]
0x1800514bd  mov     rsp, r11
0x1800514c0  pop     r14
0x1800514c2  pop     rdi
0x1800514c3  pop     rbp
0x1800514c4  retn
0x1800514c5  xor     r8d, r8d; bAlertable
0x1800514c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800514cb  mov     rcx, rbx; hHandle
0x1800514ce  call    cs:__imp_WaitForSingleObjectEx
0x1800514d4  cmp     eax, 102h
0x1800514d9  jz      loc_180051575
0x1800514df  test    eax, 0FFFFFF7Fh
0x1800514e4  jnz     loc_1800515AE
0x1800514ea  mov     rdi, rbx
0x1800514ed  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800514f2  mov     [rsp+280h+var_240], rdi
0x1800514f7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800514fc  mov     [rsp+280h+var_248], 0
0x180051505  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18005150a  mov     esi, eax
0x18005150c  test    eax, eax
0x18005150e  jns     short loc_18005157C
0x180051510  mov     rcx, [rbp+188h]; this
0x180051517  lea     r8, aWil; "wil"
0x18005151e  mov     r9d, eax; char *
0x180051521  mov     edx, 66h ; 'f'; void *
0x180051526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005152b  mov     rcx, [rbp+188h]; this
0x180051532  lea     r8, aWil; "wil"
0x180051539  mov     r9d, esi; char *
0x18005153c  mov     edx, 6Fh ; 'o'; void *
0x180051541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051546  mov     rcx, [rbp+188h]; this
0x18005154d  lea     r8, aWil; "wil"
0x180051554  mov     r9d, esi; char *
0x180051557  mov     edx, 12Eh; void *
0x18005155c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051561  test    rdi, rdi
0x180051564  jnz     short loc_1800515C0
0x180051566  mov     rcx, rbx; this
0x180051569  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005156e  mov     eax, esi
0x180051570  jmp     loc_18005149E
0x180051575  xor     edi, edi
0x180051577  jmp     loc_1800514ED
0x18005157c  mov     rax, [rsp+280h+var_248]
0x180051581  lea     rcx, ds:0[rax*4]
0x180051589  test    rcx, rcx
0x18005158c  jz      short loc_1800515CA
0x18005158e  mov     [r14], rcx
0x180051591  mov     eax, [rcx]
0x180051593  inc     eax
0x180051595  mov     [rcx], eax
0x180051597  test    rdi, rdi
0x18005159a  jnz     loc_180051622
0x1800515a0  test    rbx, rbx
0x1800515a3  jz      loc_18005149C
0x1800515a9  jmp     loc_180051494
0x1800515ae  mov     rcx, [rbp+188h]; this
0x1800515b5  mov     edx, 0E01h; void *
0x1800515ba  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800515c0  mov     rcx, rdi; this
0x1800515c3  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800515c8  jmp     short loc_180051566
0x1800515ca  mov     r8, r14
0x1800515cd  lea     rdx, [rsp+280h+hHandle]
0x1800515d2  lea     rcx, [rsp+280h+Name]
0x1800515d7  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800515dc  mov     ebx, eax
0x1800515de  test    eax, eax
0x1800515e0  jns     short loc_180051618
0x1800515e2  mov     rcx, [rbp+188h]; this
0x1800515e9  lea     r8, aWil; "wil"
0x1800515f0  mov     r9d, eax; char *
0x1800515f3  mov     edx, 137h; void *
0x1800515f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800515fd  lea     rcx, [rsp+280h+var_240]
0x180051602  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051607  lea     rcx, [rsp+280h+hHandle]
0x18005160c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051611  mov     eax, ebx
0x180051613  jmp     loc_18005149E
0x180051618  mov     rbx, [rsp+280h+hHandle]
0x18005161d  jmp     loc_180051597
0x180051622  mov     rcx, rdi; this
0x180051625  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005162a  jmp     loc_1800515A0
```
