# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003a38`
- end: `0x180003be2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004548`

## callees

- `0x180002100`
- `0x1800038ec`
- `0x180003908`
- `0x180003a38`
- `0x1800042d8`
- `0x180004e4c`
- `0x180005524`
- `0x180005a80`
- `0x180005cc8`
- `0x180005ff0`
- `0x1800060e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ab5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a70`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003a38  mov     [rsp-8+arg_10], rbx
0x180003a3d  mov     [rsp-8+arg_18], rdi
0x180003a42  push    rbp
0x180003a43  lea     rbp, [rsp-170h]
0x180003a4b  sub     rsp, 270h
0x180003a52  mov     rax, cs:__security_cookie
0x180003a59  xor     rax, rsp
0x180003a5c  mov     [rbp+170h+var_10], rax
0x180003a63  mov     rdi, rdx
0x180003a66  mov     qword ptr [rdx], 0
0x180003a6d  mov     rbx, rcx
0x180003a70  call    cs:__imp_GetCurrentProcessId
0x180003a76  mov     [rsp+270h+var_248], rbx
0x180003a7b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003a82  mov     r9d, eax
0x180003a85  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003a8d  mov     edx, 104h; unsigned __int64
0x180003a92  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003a97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003a9c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003aa2  mov     [rsp+270h+var_240], 0
0x180003aab  xor     r8d, r8d; dwFlags
0x180003aae  lea     rdx, [rsp+270h+Name]; lpName
0x180003ab3  xor     ecx, ecx; lpMutexAttributes
0x180003ab5  call    cs:__imp_CreateMutexExW
0x180003abb  mov     rdx, rax
0x180003abe  lea     rcx, [rsp+270h+var_240]
0x180003ac3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003ac8  cmp     [rsp+270h+var_240], 0
0x180003ace  jnz     short loc_180003ADC
0x180003ad0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ad5  mov     ebx, eax
0x180003ad7  jmp     loc_180003B8D
0x180003adc  lea     rdx, [rsp+270h+var_238]
0x180003ae1  lea     rcx, [rsp+270h+var_240]
0x180003ae6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003aeb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180003af0  mov     [rsp+270h+var_230], 0
0x180003af9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003afe  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b03  mov     ebx, eax
0x180003b05  test    eax, eax
0x180003b07  jns     short loc_180003B66
0x180003b09  mov     rcx, [rbp+178h]; this
0x180003b10  lea     r8, aWil; "wil"
0x180003b17  mov     r9d, eax; char *
0x180003b1a  mov     edx, 66h ; 'f'; void *
0x180003b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b24  mov     rcx, [rbp+178h]; this
0x180003b2b  lea     r8, aWil; "wil"
0x180003b32  mov     r9d, ebx; char *
0x180003b35  mov     edx, 6Fh ; 'o'; void *
0x180003b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b3f  mov     r9d, ebx; char *
0x180003b42  mov     edx, 12Eh; void *
0x180003b47  mov     rcx, [rbp+178h]; this
0x180003b4e  lea     r8, aWil; "wil"
0x180003b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b5a  lea     rcx, [rsp+270h+var_238]
0x180003b5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b64  jmp     short loc_180003B8D
0x180003b66  mov     rax, [rsp+270h+var_230]
0x180003b6b  lea     rcx, ds:0[rax*4]
0x180003b73  test    rcx, rcx
0x180003b76  jz      short loc_180003BBD
0x180003b78  mov     [rdi], rcx
0x180003b7b  mov     eax, [rcx]
0x180003b7d  inc     eax
0x180003b7f  mov     [rcx], eax
0x180003b81  lea     rcx, [rsp+270h+var_238]
0x180003b86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b8b  xor     ebx, ebx
0x180003b8d  lea     rcx, [rsp+270h+var_240]
0x180003b92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003b97  mov     eax, ebx
0x180003b99  mov     rcx, [rbp+170h+var_10]
0x180003ba0  xor     rcx, rsp; StackCookie
0x180003ba3  call    __security_check_cookie
0x180003ba8  lea     r11, [rsp+270h+var_s0]
0x180003bb0  mov     rbx, [r11+20h]
0x180003bb4  mov     rdi, [r11+28h]
0x180003bb8  mov     rsp, r11
0x180003bbb  pop     rbp
0x180003bbc  retn
0x180003bbd  mov     r8, rdi
0x180003bc0  lea     rdx, [rsp+270h+var_240]
0x180003bc5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003bca  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003bcf  mov     ebx, eax
0x180003bd1  test    eax, eax
0x180003bd3  jns     short loc_180003B81
0x180003bd5  mov     r9d, eax
0x180003bd8  mov     edx, 137h
0x180003bdd  jmp     loc_180003B47
```
