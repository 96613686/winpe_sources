# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180014978`
- end: `0x180014b0d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001562c`

## callees

- `0x180010e64`
- `0x180014774`
- `0x180014790`
- `0x180014978`
- `0x180015388`
- `0x180015e40`
- `0x180016bd4`
- `0x1800177c0`
- `0x180017c10`
- `0x180017e28`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800149f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800149f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800149b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800149b0`

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
0x180014978  mov     [rsp-8+arg_10], rbx
0x18001497d  mov     [rsp-8+arg_18], rdi
0x180014982  push    rbp
0x180014983  lea     rbp, [rsp-170h]
0x18001498b  sub     rsp, 270h
0x180014992  mov     rax, cs:__security_cookie
0x180014999  xor     rax, rsp
0x18001499c  mov     [rbp+170h+var_10], rax
0x1800149a3  mov     rdi, rdx
0x1800149a6  mov     qword ptr [rdx], 0
0x1800149ad  mov     rbx, rcx
0x1800149b0  call    cs:__imp_GetCurrentProcessId
0x1800149b6  mov     [rsp+270h+var_248], rbx
0x1800149bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800149c2  mov     r9d, eax
0x1800149c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800149cd  mov     edx, 104h; unsigned __int64
0x1800149d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800149d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800149dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800149e2  mov     [rsp+270h+var_240], 0
0x1800149eb  xor     r8d, r8d; dwFlags
0x1800149ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800149f3  xor     ecx, ecx; lpMutexAttributes
0x1800149f5  call    cs:__imp_CreateMutexExW
0x1800149fb  mov     rdx, rax
0x1800149fe  lea     rcx, [rsp+270h+var_240]
0x180014a03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180014a08  cmp     [rsp+270h+var_240], 0
0x180014a0e  jnz     short loc_180014A1C
0x180014a10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014a15  mov     ebx, eax
0x180014a17  jmp     loc_180014AB8
0x180014a1c  lea     rdx, [rsp+270h+var_238]
0x180014a21  lea     rcx, [rsp+270h+var_240]
0x180014a26  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180014a2b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180014a30  mov     [rsp+270h+var_230], 0
0x180014a39  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014a3e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180014a43  mov     ebx, eax
0x180014a45  test    eax, eax
0x180014a47  jns     short loc_180014A91
0x180014a49  mov     rcx, [rbp+178h]; this
0x180014a50  mov     r9d, eax; char *
0x180014a53  mov     edx, 66h ; 'f'; void *
0x180014a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a5d  mov     rcx, [rbp+178h]; this
0x180014a64  mov     r9d, ebx; char *
0x180014a67  mov     edx, 6Fh ; 'o'; void *
0x180014a6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a71  mov     r9d, ebx; char *
0x180014a74  mov     edx, 12Eh; void *
0x180014a79  mov     rcx, [rbp+178h]; this
0x180014a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a85  lea     rcx, [rsp+270h+var_238]
0x180014a8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014a8f  jmp     short loc_180014AB8
0x180014a91  mov     rax, [rsp+270h+var_230]
0x180014a96  lea     rcx, ds:0[rax*4]
0x180014a9e  test    rcx, rcx
0x180014aa1  jz      short loc_180014AE8
0x180014aa3  mov     [rdi], rcx
0x180014aa6  mov     eax, [rcx]
0x180014aa8  inc     eax
0x180014aaa  mov     [rcx], eax
0x180014aac  lea     rcx, [rsp+270h+var_238]
0x180014ab1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014ab6  xor     ebx, ebx
0x180014ab8  lea     rcx, [rsp+270h+var_240]
0x180014abd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180014ac2  mov     eax, ebx
0x180014ac4  mov     rcx, [rbp+170h+var_10]
0x180014acb  xor     rcx, rsp; StackCookie
0x180014ace  call    __security_check_cookie
0x180014ad3  lea     r11, [rsp+270h+var_s0]
0x180014adb  mov     rbx, [r11+20h]
0x180014adf  mov     rdi, [r11+28h]
0x180014ae3  mov     rsp, r11
0x180014ae6  pop     rbp
0x180014ae7  retn
0x180014ae8  mov     r8, rdi
0x180014aeb  lea     rdx, [rsp+270h+var_240]
0x180014af0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014af5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180014afa  mov     ebx, eax
0x180014afc  test    eax, eax
0x180014afe  jns     short loc_180014AAC
0x180014b00  mov     r9d, eax
0x180014b03  mov     edx, 137h
0x180014b08  jmp     loc_180014A79
```
