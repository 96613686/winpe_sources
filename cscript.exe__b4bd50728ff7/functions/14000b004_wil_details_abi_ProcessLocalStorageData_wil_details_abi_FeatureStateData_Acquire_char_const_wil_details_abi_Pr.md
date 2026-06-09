# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000b004`
- end: `0x14000b1ca`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000b7f4`

## callees

- `0x14000af84`
- `0x14000afa0`
- `0x14000b004`
- `0x14000b41c`
- `0x14000b7c0`
- `0x14000bee0`
- `0x14000c208`
- `0x14000c2ec`
- `0x14000c5f8`
- `0x14000cb84`
- `0x1400161d0`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x14000b0b3`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000b0b3`
- `KERNEL32!CreateMutexExW` at `0x14000b081`
- `KERNEL32!CreateMutexExW` at `0x14000b081`
- `KERNEL32!GetCurrentProcessId` at `0x14000b03c`
- `KERNEL32!GetCurrentProcessId` at `0x14000b03c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  int ValueInternal; // eax
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( hHandle )
  {
    v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
    if ( v8 == 258 )
    {
      v6 = 0;
    }
    else if ( (v8 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    }
    v24 = v6;
    v25 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v25, (bool *)v11);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v14, (const char *)LastErrorFailHr, v22);
      v16 = LastErrorFailHr;
      v17 = 302;
LABEL_14:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, v15, (const char *)v16, v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
      goto LABEL_15;
    }
    v18 = (_DWORD *)(4 * v25);
    if ( 4 * v25 )
    {
      *a2 = v18;
      ++*v18;
    }
    else
    {
      v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = v20;
      if ( v20 < 0 )
      {
        v16 = (unsigned int)v20;
        v17 = 311;
        goto LABEL_14;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_15:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x14000b004  mov     [rsp-8+arg_10], rbx
0x14000b009  mov     [rsp-8+arg_18], rdi
0x14000b00e  push    rbp
0x14000b00f  lea     rbp, [rsp-170h]
0x14000b017  sub     rsp, 270h
0x14000b01e  mov     rax, cs:__security_cookie
0x14000b025  xor     rax, rsp
0x14000b028  mov     [rbp+170h+var_10], rax
0x14000b02f  mov     rdi, rdx
0x14000b032  mov     qword ptr [rdx], 0
0x14000b039  mov     rbx, rcx
0x14000b03c  call    cs:__imp_GetCurrentProcessId
0x14000b042  mov     [rsp+270h+var_248], rbx
0x14000b047  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000b04e  mov     r9d, eax
0x14000b051  mov     [rsp+270h+var_250], 130h; int
0x14000b059  mov     edx, 104h; unsigned __int64
0x14000b05e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000b063  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b068  mov     r9d, 1F0001h; dwDesiredAccess
0x14000b06e  mov     [rsp+270h+hHandle], 0
0x14000b077  xor     r8d, r8d; dwFlags
0x14000b07a  lea     rdx, [rsp+270h+Name]; lpName
0x14000b07f  xor     ecx, ecx; lpMutexAttributes
0x14000b081  call    cs:__imp_CreateMutexExW
0x14000b087  mov     rdx, rax
0x14000b08a  lea     rcx, [rsp+270h+hHandle]
0x14000b08f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000b094  mov     rbx, [rsp+270h+hHandle]
0x14000b099  test    rbx, rbx
0x14000b09c  jnz     short loc_14000B0AA
0x14000b09e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000b0a3  mov     ebx, eax
0x14000b0a5  jmp     loc_14000B1AF
0x14000b0aa  xor     r8d, r8d; bAlertable
0x14000b0ad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000b0b0  mov     rcx, rbx; hHandle
0x14000b0b3  call    cs:__imp_WaitForSingleObjectEx
0x14000b0b9  cmp     eax, 102h
0x14000b0be  jz      short loc_14000B0CD
0x14000b0c0  test    eax, 0FFFFFF7Fh
0x14000b0c5  jnz     loc_14000B1BD
0x14000b0cb  jmp     short loc_14000B0CF
0x14000b0cd  xor     ebx, ebx
0x14000b0cf  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x14000b0d4  mov     [rsp+270h+var_238], rbx
0x14000b0d9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000b0de  mov     [rsp+270h+var_230], 0
0x14000b0e7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000b0ec  mov     ebx, eax
0x14000b0ee  test    eax, eax
0x14000b0f0  jns     short loc_14000B124
0x14000b0f2  mov     rcx, [rbp+178h]; this
0x14000b0f9  mov     r9d, eax; char *
0x14000b0fc  mov     edx, 66h ; 'f'; void *
0x14000b101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b106  mov     rcx, [rbp+178h]; this
0x14000b10d  mov     r9d, ebx; char *
0x14000b110  mov     edx, 6Fh ; 'o'; void *
0x14000b115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b11a  mov     r9d, ebx
0x14000b11d  mov     edx, 12Eh
0x14000b122  jmp     short loc_14000B199
0x14000b124  mov     rax, [rsp+270h+var_230]
0x14000b129  lea     rcx, ds:0[rax*4]
0x14000b131  test    rcx, rcx
0x14000b134  jz      short loc_14000B179
0x14000b136  mov     [rdi], rcx
0x14000b139  mov     eax, [rcx]
0x14000b13b  inc     eax
0x14000b13d  mov     [rcx], eax
0x14000b13f  lea     rcx, [rsp+270h+var_238]
0x14000b144  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b149  lea     rcx, [rsp+270h+hHandle]
0x14000b14e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b153  xor     eax, eax
0x14000b155  mov     rcx, [rbp+170h+var_10]
0x14000b15c  xor     rcx, rsp; StackCookie
0x14000b15f  call    __security_check_cookie
0x14000b164  lea     r11, [rsp+270h+var_s0]
0x14000b16c  mov     rbx, [r11+20h]
0x14000b170  mov     rdi, [r11+28h]
0x14000b174  mov     rsp, r11
0x14000b177  pop     rbp
0x14000b178  retn
0x14000b179  mov     r8, rdi
0x14000b17c  lea     rdx, [rsp+270h+hHandle]
0x14000b181  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000b186  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000b18b  mov     ebx, eax
0x14000b18d  test    eax, eax
0x14000b18f  jns     short loc_14000B13F
0x14000b191  mov     r9d, eax; char *
0x14000b194  mov     edx, 137h; void *
0x14000b199  mov     rcx, [rbp+178h]; this
0x14000b1a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b1a5  lea     rcx, [rsp+270h+var_238]
0x14000b1aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b1af  lea     rcx, [rsp+270h+hHandle]
0x14000b1b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b1b9  mov     eax, ebx
0x14000b1bb  jmp     short loc_14000B155
0x14000b1bd  mov     rcx, [rbp+178h]; this
0x14000b1c4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
