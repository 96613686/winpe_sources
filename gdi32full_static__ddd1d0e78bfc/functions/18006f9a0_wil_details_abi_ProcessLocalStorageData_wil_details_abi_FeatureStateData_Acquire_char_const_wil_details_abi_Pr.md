# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18006f9a0`
- end: `0x18006fb66`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180086d18`

## callees

- `0x18006f9a0`
- `0x18006fb6c`
- `0x18006fbd0`
- `0x18007c910`
- `0x18007c930`
- `0x18007c964`
- `0x18007cb34`
- `0x18007de00`
- `0x18007e8cc`
- `0x18007f800`
- `0x180086b08`
- `0x180087c7c`
- `0x180088754`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f9d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f9d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18006fa20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18006fa20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  void *v15; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // r8d
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v22 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v22,
    Mutex);
  v6 = v22;
  if ( !v22 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_10;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v22,
    &v23);
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v24, v9);
  v12 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v17 = (_DWORD *)(4 * v24);
    if ( 4 * v24 )
    {
      *a2 = v17;
      ++*v17;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v19, (const char *)(unsigned int)v18, 304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        goto LABEL_10;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    LastErrorFailHr = 0;
LABEL_10:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return LastErrorFailHr;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v11, (const char *)(unsigned int)ValueInternal, 304);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v13, (const char *)v12, v20);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v14, (const char *)v12, v21);
  if ( v23 )
    wil::details::ReleaseMutex(v23, v15);
  wil::details::CloseHandle(v6, v15);
  return v12;
}

```

## disassembly

```asm
0x18006f9a0  mov     [rsp-8+arg_10], rbx
0x18006f9a5  push    rbp
0x18006f9a6  push    rsi
0x18006f9a7  push    rdi
0x18006f9a8  lea     rbp, [rsp-170h]
0x18006f9b0  sub     rsp, 270h
0x18006f9b7  mov     rax, cs:__security_cookie
0x18006f9be  xor     rax, rsp
0x18006f9c1  mov     [rbp+180h+var_20], rax
0x18006f9c8  mov     rsi, rdx
0x18006f9cb  mov     rbx, rcx
0x18006f9ce  mov     qword ptr [rdx], 0
0x18006f9d5  call    cs:__imp_GetCurrentProcessId
0x18006f9dc  nop     dword ptr [rax+rax+00h]
0x18006f9e1  mov     r9d, eax
0x18006f9e4  mov     [rsp+280h+var_258], rbx
0x18006f9e9  mov     [rsp+280h+var_260], 130h; int
0x18006f9f1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18006f9f8  mov     edx, 104h; unsigned __int64
0x18006f9fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18006fa02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006fa07  mov     [rsp+280h+var_250], 0
0x18006fa10  mov     r9d, 1F0001h; dwDesiredAccess
0x18006fa16  xor     r8d, r8d; dwFlags
0x18006fa19  lea     rdx, [rsp+280h+Name]; lpName
0x18006fa1e  xor     ecx, ecx; lpMutexAttributes
0x18006fa20  call    cs:__imp_CreateMutexExW
0x18006fa27  nop     dword ptr [rax+rax+00h]
0x18006fa2c  mov     rdx, rax
0x18006fa2f  lea     rcx, [rsp+280h+var_250]
0x18006fa34  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006fa39  mov     rbx, [rsp+280h+var_250]
0x18006fa3e  test    rbx, rbx
0x18006fa41  jnz     short loc_18006FA4F
0x18006fa43  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18006fa48  mov     ebx, eax
0x18006fa4a  jmp     loc_18006FAFD
0x18006fa4f  lea     rdx, [rsp+280h+var_248]
0x18006fa54  lea     rcx, [rsp+280h+var_250]
0x18006fa59  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18006fa5e  nop
0x18006fa5f  mov     [rsp+280h+var_240], 0
0x18006fa68  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x18006fa6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18006fa72  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18006fa77  mov     edi, eax
0x18006fa79  test    eax, eax
0x18006fa7b  jns     short loc_18006FAD6
0x18006fa7d  mov     rcx, [rbp+188h]; this
0x18006fa84  mov     r9d, eax; char *
0x18006fa87  mov     edx, 66h ; 'f'; void *
0x18006fa8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fa91  mov     rcx, [rbp+188h]; this
0x18006fa98  mov     r9d, edi; char *
0x18006fa9b  mov     edx, 6Fh ; 'o'; void *
0x18006faa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006faa5  mov     rcx, [rbp+188h]; this
0x18006faac  mov     r9d, edi; char *
0x18006faaf  mov     edx, 12Eh; void *
0x18006fab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fab9  nop
0x18006faba  mov     rcx, [rsp+280h+var_248]; this
0x18006fabf  test    rcx, rcx
0x18006fac2  jz      short loc_18006FACA
0x18006fac4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18006fac9  nop
0x18006faca  mov     rcx, rbx; this
0x18006facd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18006fad2  mov     eax, edi
0x18006fad4  jmp     short loc_18006FB09
0x18006fad6  mov     rax, [rsp+280h+var_240]
0x18006fadb  lea     rcx, ds:0[rax*4]
0x18006fae3  test    rcx, rcx
0x18006fae6  jz      short loc_18006FB2C
0x18006fae8  mov     [rsi], rcx
0x18006faeb  mov     eax, [rcx]
0x18006faed  inc     eax
0x18006faef  mov     [rcx], eax
0x18006faf1  lea     rcx, [rsp+280h+var_248]
0x18006faf6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fafb  xor     ebx, ebx
0x18006fafd  lea     rcx, [rsp+280h+var_250]
0x18006fb02  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fb07  mov     eax, ebx
0x18006fb09  mov     rcx, [rbp+180h+var_20]
0x18006fb10  xor     rcx, rsp; StackCookie
0x18006fb13  call    __security_check_cookie
0x18006fb18  mov     rbx, [rsp+280h+arg_10]
0x18006fb20  add     rsp, 270h
0x18006fb27  pop     rdi
0x18006fb28  pop     rsi
0x18006fb29  pop     rbp
0x18006fb2a  retn
0x18006fb2c  mov     r8, rsi
0x18006fb2f  lea     rdx, [rsp+280h+var_250]
0x18006fb34  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18006fb39  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18006fb3e  mov     ebx, eax
0x18006fb40  test    eax, eax
0x18006fb42  jns     short loc_18006FAF1
0x18006fb44  mov     rcx, [rbp+188h]; this
0x18006fb4b  mov     r9d, eax; char *
0x18006fb4e  mov     edx, 137h; void *
0x18006fb53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb58  nop
0x18006fb59  lea     rcx, [rsp+280h+var_248]
0x18006fb5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fb63  jmp     short loc_18006FAFD
```
