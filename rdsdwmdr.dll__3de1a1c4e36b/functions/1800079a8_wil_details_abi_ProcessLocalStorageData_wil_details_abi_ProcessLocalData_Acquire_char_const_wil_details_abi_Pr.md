# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800079a8`
- end: `0x180007b3d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009cd0`

## callees

- `0x180006098`
- `0x180007818`
- `0x180007834`
- `0x1800079a8`
- `0x1800098d4`
- `0x18000a7c8`
- `0x18000bd5c`
- `0x18000c560`
- `0x18000c888`
- `0x18000c934`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007a25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007a25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800079e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800079e0`

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
0x1800079a8  mov     [rsp-8+arg_10], rbx
0x1800079ad  mov     [rsp-8+arg_18], rdi
0x1800079b2  push    rbp
0x1800079b3  lea     rbp, [rsp-170h]
0x1800079bb  sub     rsp, 270h
0x1800079c2  mov     rax, cs:__security_cookie
0x1800079c9  xor     rax, rsp
0x1800079cc  mov     [rbp+170h+var_10], rax
0x1800079d3  mov     rdi, rdx
0x1800079d6  mov     qword ptr [rdx], 0
0x1800079dd  mov     rbx, rcx
0x1800079e0  call    cs:__imp_GetCurrentProcessId
0x1800079e6  mov     [rsp+270h+var_248], rbx
0x1800079eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800079f2  mov     r9d, eax
0x1800079f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800079fd  mov     edx, 104h; unsigned __int64
0x180007a02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007a07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007a0c  mov     r9d, 1F0001h; dwDesiredAccess
0x180007a12  mov     [rsp+270h+var_240], 0
0x180007a1b  xor     r8d, r8d; dwFlags
0x180007a1e  lea     rdx, [rsp+270h+Name]; lpName
0x180007a23  xor     ecx, ecx; lpMutexAttributes
0x180007a25  call    cs:__imp_CreateMutexExW
0x180007a2b  mov     rdx, rax
0x180007a2e  lea     rcx, [rsp+270h+var_240]
0x180007a33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007a38  cmp     [rsp+270h+var_240], 0
0x180007a3e  jnz     short loc_180007A4C
0x180007a40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007a45  mov     ebx, eax
0x180007a47  jmp     loc_180007AE8
0x180007a4c  lea     rdx, [rsp+270h+var_238]
0x180007a51  lea     rcx, [rsp+270h+var_240]
0x180007a56  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007a5b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180007a60  mov     [rsp+270h+var_230], 0
0x180007a69  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007a6e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007a73  mov     ebx, eax
0x180007a75  test    eax, eax
0x180007a77  jns     short loc_180007AC1
0x180007a79  mov     rcx, [rbp+178h]; this
0x180007a80  mov     r9d, eax; char *
0x180007a83  mov     edx, 66h ; 'f'; void *
0x180007a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a8d  mov     rcx, [rbp+178h]; this
0x180007a94  mov     r9d, ebx; char *
0x180007a97  mov     edx, 6Fh ; 'o'; void *
0x180007a9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007aa1  mov     r9d, ebx; char *
0x180007aa4  mov     edx, 12Eh; void *
0x180007aa9  mov     rcx, [rbp+178h]; this
0x180007ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ab5  lea     rcx, [rsp+270h+var_238]
0x180007aba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007abf  jmp     short loc_180007AE8
0x180007ac1  mov     rax, [rsp+270h+var_230]
0x180007ac6  lea     rcx, ds:0[rax*4]
0x180007ace  test    rcx, rcx
0x180007ad1  jz      short loc_180007B18
0x180007ad3  mov     [rdi], rcx
0x180007ad6  mov     eax, [rcx]
0x180007ad8  inc     eax
0x180007ada  mov     [rcx], eax
0x180007adc  lea     rcx, [rsp+270h+var_238]
0x180007ae1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ae6  xor     ebx, ebx
0x180007ae8  lea     rcx, [rsp+270h+var_240]
0x180007aed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007af2  mov     eax, ebx
0x180007af4  mov     rcx, [rbp+170h+var_10]
0x180007afb  xor     rcx, rsp; StackCookie
0x180007afe  call    __security_check_cookie
0x180007b03  lea     r11, [rsp+270h+var_s0]
0x180007b0b  mov     rbx, [r11+20h]
0x180007b0f  mov     rdi, [r11+28h]
0x180007b13  mov     rsp, r11
0x180007b16  pop     rbp
0x180007b17  retn
0x180007b18  mov     r8, rdi
0x180007b1b  lea     rdx, [rsp+270h+var_240]
0x180007b20  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007b25  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180007b2a  mov     ebx, eax
0x180007b2c  test    eax, eax
0x180007b2e  jns     short loc_180007ADC
0x180007b30  mov     r9d, eax
0x180007b33  mov     edx, 137h
0x180007b38  jmp     loc_180007AA9
```
