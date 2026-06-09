# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800066b8`
- end: `0x18000685a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007228`

## callees

- `0x180002d90`
- `0x180004cd0`
- `0x180006568`
- `0x180006588`
- `0x1800066b8`
- `0x1800077f0`
- `0x180007c44`
- `0x180008098`
- `0x180008640`
- `0x180008714`
- `0x180009e40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800066f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800066f0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000673b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000673b`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800066b8  mov     [rsp-8+arg_10], rbx
0x1800066bd  mov     [rsp-8+arg_18], rdi
0x1800066c2  push    rbp
0x1800066c3  lea     rbp, [rsp-170h]
0x1800066cb  sub     rsp, 270h
0x1800066d2  mov     rax, cs:__security_cookie
0x1800066d9  xor     rax, rsp
0x1800066dc  mov     [rbp+170h+var_10], rax
0x1800066e3  mov     rdi, rdx
0x1800066e6  mov     qword ptr [rdx], 0
0x1800066ed  mov     rbx, rcx
0x1800066f0  call    cs:__imp_GetCurrentProcessId
0x1800066f7  nop     dword ptr [rax+rax+00h]
0x1800066fc  mov     [rsp+270h+var_248], rbx
0x180006701  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006708  mov     r9d, eax
0x18000670b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006713  mov     edx, 104h; unsigned __int64
0x180006718  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000671d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006722  mov     r9d, 1F0001h; dwDesiredAccess
0x180006728  mov     [rsp+270h+var_240], 0
0x180006731  xor     r8d, r8d; dwFlags
0x180006734  lea     rdx, [rsp+270h+Name]; lpName
0x180006739  xor     ecx, ecx; lpMutexAttributes
0x18000673b  call    cs:__imp_CreateMutexExW
0x180006742  nop     dword ptr [rax+rax+00h]
0x180006747  mov     rdx, rax
0x18000674a  lea     rcx, [rsp+270h+var_240]
0x18000674f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006754  cmp     [rsp+270h+var_240], 0
0x18000675a  jnz     short loc_180006768
0x18000675c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006761  mov     ebx, eax
0x180006763  jmp     loc_180006804
0x180006768  lea     rdx, [rsp+270h+var_238]
0x18000676d  lea     rcx, [rsp+270h+var_240]
0x180006772  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006777  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000677c  mov     [rsp+270h+var_230], 0
0x180006785  lea     rcx, [rsp+270h+Name]; pszSrc
0x18000678a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000678f  mov     ebx, eax
0x180006791  test    eax, eax
0x180006793  jns     short loc_1800067DD
0x180006795  mov     rcx, [rbp+178h]; this
0x18000679c  mov     r9d, eax; char *
0x18000679f  mov     edx, 66h ; 'f'; void *
0x1800067a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067a9  mov     rcx, [rbp+178h]; this
0x1800067b0  mov     r9d, ebx; char *
0x1800067b3  mov     edx, 6Fh ; 'o'; void *
0x1800067b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067bd  mov     r9d, ebx; char *
0x1800067c0  mov     edx, 12Eh; void *
0x1800067c5  mov     rcx, [rbp+178h]; this
0x1800067cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067d1  lea     rcx, [rsp+270h+var_238]
0x1800067d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800067db  jmp     short loc_180006804
0x1800067dd  mov     rax, [rsp+270h+var_230]
0x1800067e2  lea     rcx, ds:0[rax*4]
0x1800067ea  test    rcx, rcx
0x1800067ed  jz      short loc_180006835
0x1800067ef  mov     [rdi], rcx
0x1800067f2  mov     eax, [rcx]
0x1800067f4  inc     eax
0x1800067f6  mov     [rcx], eax
0x1800067f8  lea     rcx, [rsp+270h+var_238]
0x1800067fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006802  xor     ebx, ebx
0x180006804  lea     rcx, [rsp+270h+var_240]
0x180006809  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000680e  mov     eax, ebx
0x180006810  mov     rcx, [rbp+170h+var_10]
0x180006817  xor     rcx, rsp; StackCookie
0x18000681a  call    __security_check_cookie
0x18000681f  lea     r11, [rsp+270h+var_s0]
0x180006827  mov     rbx, [r11+20h]
0x18000682b  mov     rdi, [r11+28h]
0x18000682f  mov     rsp, r11
0x180006832  pop     rbp
0x180006833  retn
0x180006835  mov     r8, rdi
0x180006838  lea     rdx, [rsp+270h+var_240]
0x18000683d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006842  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006847  mov     ebx, eax
0x180006849  test    eax, eax
0x18000684b  jns     short loc_1800067F8
0x18000684d  mov     r9d, eax
0x180006850  mov     edx, 137h
0x180006855  jmp     loc_1800067C5
```
