# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003afa0`
- end: `0x18003b135`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003c20c`

## callees

- `0x180024220`
- `0x18003af40`
- `0x18003af5c`
- `0x18003afa0`
- `0x18003bf6c`
- `0x18003c944`
- `0x18003d29c`
- `0x18003d58c`
- `0x18003d73c`
- `0x18003dba0`
- `0x18003dcd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003b01d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003b01d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003afd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003afd8`

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
0x18003afa0  mov     [rsp-8+arg_10], rbx
0x18003afa5  mov     [rsp-8+arg_18], rdi
0x18003afaa  push    rbp
0x18003afab  lea     rbp, [rsp-170h]
0x18003afb3  sub     rsp, 270h
0x18003afba  mov     rax, cs:__security_cookie
0x18003afc1  xor     rax, rsp
0x18003afc4  mov     [rbp+170h+var_10], rax
0x18003afcb  mov     rdi, rdx
0x18003afce  mov     qword ptr [rdx], 0
0x18003afd5  mov     rbx, rcx
0x18003afd8  call    cs:__imp_GetCurrentProcessId
0x18003afde  mov     [rsp+270h+var_248], rbx
0x18003afe3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003afea  mov     r9d, eax
0x18003afed  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003aff5  mov     edx, 104h; unsigned __int64
0x18003affa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003afff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b004  mov     r9d, 1F0001h; dwDesiredAccess
0x18003b00a  mov     [rsp+270h+var_240], 0
0x18003b013  xor     r8d, r8d; dwFlags
0x18003b016  lea     rdx, [rsp+270h+Name]; lpName
0x18003b01b  xor     ecx, ecx; lpMutexAttributes
0x18003b01d  call    cs:__imp_CreateMutexExW
0x18003b023  mov     rdx, rax
0x18003b026  lea     rcx, [rsp+270h+var_240]
0x18003b02b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003b030  cmp     [rsp+270h+var_240], 0
0x18003b036  jnz     short loc_18003B044
0x18003b038  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003b03d  mov     ebx, eax
0x18003b03f  jmp     loc_18003B0E0
0x18003b044  lea     rdx, [rsp+270h+var_238]
0x18003b049  lea     rcx, [rsp+270h+var_240]
0x18003b04e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003b053  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18003b058  mov     [rsp+270h+var_230], 0
0x18003b061  lea     rcx, [rsp+270h+Name]; pszSrc
0x18003b066  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18003b06b  mov     ebx, eax
0x18003b06d  test    eax, eax
0x18003b06f  jns     short loc_18003B0B9
0x18003b071  mov     rcx, [rbp+178h]; this
0x18003b078  mov     r9d, eax; char *
0x18003b07b  mov     edx, 66h ; 'f'; void *
0x18003b080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b085  mov     rcx, [rbp+178h]; this
0x18003b08c  mov     r9d, ebx; char *
0x18003b08f  mov     edx, 6Fh ; 'o'; void *
0x18003b094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b099  mov     r9d, ebx; char *
0x18003b09c  mov     edx, 12Eh; void *
0x18003b0a1  mov     rcx, [rbp+178h]; this
0x18003b0a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b0ad  lea     rcx, [rsp+270h+var_238]
0x18003b0b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b0b7  jmp     short loc_18003B0E0
0x18003b0b9  mov     rax, [rsp+270h+var_230]
0x18003b0be  lea     rcx, ds:0[rax*4]
0x18003b0c6  test    rcx, rcx
0x18003b0c9  jz      short loc_18003B110
0x18003b0cb  mov     [rdi], rcx
0x18003b0ce  mov     eax, [rcx]
0x18003b0d0  inc     eax
0x18003b0d2  mov     [rcx], eax
0x18003b0d4  lea     rcx, [rsp+270h+var_238]
0x18003b0d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b0de  xor     ebx, ebx
0x18003b0e0  lea     rcx, [rsp+270h+var_240]
0x18003b0e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b0ea  mov     eax, ebx
0x18003b0ec  mov     rcx, [rbp+170h+var_10]
0x18003b0f3  xor     rcx, rsp; StackCookie
0x18003b0f6  call    __security_check_cookie
0x18003b0fb  lea     r11, [rsp+270h+var_s0]
0x18003b103  mov     rbx, [r11+20h]
0x18003b107  mov     rdi, [r11+28h]
0x18003b10b  mov     rsp, r11
0x18003b10e  pop     rbp
0x18003b10f  retn
0x18003b110  mov     r8, rdi
0x18003b113  lea     rdx, [rsp+270h+var_240]
0x18003b118  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b11d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003b122  mov     ebx, eax
0x18003b124  test    eax, eax
0x18003b126  jns     short loc_18003B0D4
0x18003b128  mov     r9d, eax
0x18003b12b  mov     edx, 137h
0x18003b130  jmp     loc_18003B0A1
```
