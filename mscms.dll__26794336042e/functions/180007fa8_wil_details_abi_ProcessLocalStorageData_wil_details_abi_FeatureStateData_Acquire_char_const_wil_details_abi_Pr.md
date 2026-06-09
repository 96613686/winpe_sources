# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007fa8`
- end: `0x180008156`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `430`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007b18`

## callees

- `0x180007b88`
- `0x180007fa8`
- `0x1800089d8`
- `0x1800092c4`
- `0x180009324`
- `0x180009790`
- `0x18000992c`
- `0x180009958`
- `0x1800269d4`
- `0x1800269f8`
- `0x18002e5f0`
- `0x180041ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000801a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000801a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007fdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007fdd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  HANDLE Mutex; // rbx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  void *v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  _DWORD *v14; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  HANDLE v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v18 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v18,
    v20);
  v19 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
  v11 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v11, v17);
    v12 = v11;
    v13 = 302;
LABEL_9:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v13, (unsigned int)"wil", (const char *)v12, v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v18);
    return v11;
  }
  v14 = (_DWORD *)(4 * v19);
  if ( 4 * v19 )
  {
    *a2 = v14;
    ++*v14;
  }
  else
  {
    v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v11 = v15;
    if ( v15 < 0 )
    {
      v12 = (unsigned int)v15;
      v13 = 311;
      goto LABEL_9;
    }
    Mutex = v18;
  }
  if ( v20[0] )
    wil::details::ReleaseMutex(v20[0], v10);
  if ( Mutex )
    wil::details::CloseHandle((wil::details *)Mutex, v10);
  return 0;
}

```

## disassembly

```asm
0x180007fa8  mov     [rsp-8+arg_10], rbx
0x180007fad  push    rbp
0x180007fae  push    rsi
0x180007faf  push    rdi
0x180007fb0  lea     rbp, [rsp-170h]
0x180007fb8  sub     rsp, 270h
0x180007fbf  mov     rax, cs:__security_cookie
0x180007fc6  xor     rax, rsp
0x180007fc9  mov     [rbp+180h+var_20], rax
0x180007fd0  mov     rsi, rdx
0x180007fd3  mov     rbx, rcx
0x180007fd6  mov     qword ptr [rdx], 0
0x180007fdd  call    cs:__imp_GetCurrentProcessId
0x180007fe3  mov     r9d, eax
0x180007fe6  mov     [rsp+280h+var_258], rbx
0x180007feb  mov     [rsp+280h+var_260], 130h; int
0x180007ff3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007ffa  mov     edx, 104h; unsigned __int64
0x180007fff  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008004  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008009  nop
0x18000800a  mov     r9d, 1F0001h; dwDesiredAccess
0x180008010  xor     r8d, r8d; dwFlags
0x180008013  lea     rdx, [rsp+280h+Name]; lpName
0x180008018  xor     ecx, ecx; lpMutexAttributes
0x18000801a  call    cs:__imp_CreateMutexExW
0x180008020  mov     rbx, rax
0x180008023  mov     [rsp+280h+var_250], rax
0x180008028  test    rax, rax
0x18000802b  jnz     short loc_180008038
0x18000802d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008032  nop
0x180008033  jmp     loc_180008134
0x180008038  lea     rdx, [rsp+280h+var_240]
0x18000803d  lea     rcx, [rsp+280h+var_250]
0x180008042  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008047  nop
0x180008048  mov     [rsp+280h+var_248], 0
0x180008051  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180008056  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000805b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008060  mov     edi, eax
0x180008062  test    eax, eax
0x180008064  jns     short loc_1800080A6
0x180008066  mov     rcx, [rbp+188h]; this
0x18000806d  mov     r9d, eax; char *
0x180008070  lea     r8, aWil; "wil"
0x180008077  mov     edx, 66h ; 'f'; void *
0x18000807c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008081  mov     rcx, [rbp+188h]; this
0x180008088  mov     r9d, edi; char *
0x18000808b  lea     r8, aWil; "wil"
0x180008092  mov     edx, 6Fh ; 'o'; void *
0x180008097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000809c  mov     r9d, edi
0x18000809f  mov     edx, 12Eh
0x1800080a4  jmp     short loc_1800080E3
0x1800080a6  mov     rax, [rsp+280h+var_248]
0x1800080ab  lea     rcx, ds:0[rax*4]
0x1800080b3  test    rcx, rcx
0x1800080b6  jz      short loc_1800080C3
0x1800080b8  mov     [rsi], rcx
0x1800080bb  mov     eax, [rcx]
0x1800080bd  inc     eax
0x1800080bf  mov     [rcx], eax
0x1800080c1  jmp     short loc_180008115
0x1800080c3  mov     r8, rsi
0x1800080c6  lea     rdx, [rsp+280h+var_250]
0x1800080cb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800080d0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800080d5  mov     edi, eax
0x1800080d7  test    eax, eax
0x1800080d9  jns     short loc_180008110
0x1800080db  mov     r9d, eax; char *
0x1800080de  mov     edx, 137h; void *
0x1800080e3  lea     r8, aWil; "wil"
0x1800080ea  mov     rcx, [rbp+188h]; this
0x1800080f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080f6  nop
0x1800080f7  lea     rcx, [rsp+280h+var_240]
0x1800080fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008101  nop
0x180008102  lea     rcx, [rsp+280h+var_250]
0x180008107  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18000810c  mov     eax, edi
0x18000810e  jmp     short loc_180008134
0x180008110  mov     rbx, [rsp+280h+var_250]
0x180008115  mov     rcx, [rsp+280h+var_240]; this
0x18000811a  test    rcx, rcx
0x18000811d  jz      short loc_180008125
0x18000811f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180008124  nop
0x180008125  test    rbx, rbx
0x180008128  jz      short loc_180008132
0x18000812a  mov     rcx, rbx; this
0x18000812d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008132  xor     eax, eax
0x180008134  mov     rcx, [rbp+180h+var_20]
0x18000813b  xor     rcx, rsp; StackCookie
0x18000813e  call    __security_check_cookie
0x180008143  mov     rbx, [rsp+280h+arg_10]
0x18000814b  add     rsp, 270h
0x180008152  pop     rdi
0x180008153  pop     rsi
0x180008154  pop     rbp
0x180008155  retn
```
