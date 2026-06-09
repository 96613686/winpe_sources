# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180050ce4`
- end: `0x180050f27`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180050998`

## callees

- `0x18002568c`
- `0x180025dd4`
- `0x180050ce4`
- `0x180050f30`
- `0x180050f4c`
- `0x1800513c4`
- `0x180051638`
- `0x1800627fc`
- `0x180068c78`
- `0x18006946c`
- `0x18006c38c`
- `0x18006ed20`
- `0x180072868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180050d64`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180050d64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180050d96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180050d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050d1f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rdi
  unsigned int LastErrorFailHr; // esi
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rbx
  int ValueInternal; // eax
  void *v14; // rdx
  _DWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // edi
  void *v19; // rdx
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
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_8:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return LastErrorFailHr;
  }
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
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)LastErrorFailHr, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    goto LABEL_8;
  }
  v16 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v16;
    ++*v16;
LABEL_12:
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v6 = (wil::details *)hHandle;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 120);
  if ( v12 )
    wil::details::ReleaseMutex(v12, v19);
  if ( hHandle )
    wil::details::CloseHandle((wil::details *)hHandle, v19);
  return v18;
}

```

## disassembly

```asm
0x180050ce4  mov     [rsp-8+arg_10], rbx
0x180050ce9  mov     [rsp-8+arg_18], rsi
0x180050cee  push    rbp
0x180050cef  push    rdi
0x180050cf0  push    r14
0x180050cf2  lea     rbp, [rsp-170h]
0x180050cfa  sub     rsp, 270h
0x180050d01  mov     rax, cs:__security_cookie
0x180050d08  xor     rax, rsp
0x180050d0b  mov     [rbp+180h+var_20], rax
0x180050d12  mov     r14, rdx
0x180050d15  mov     qword ptr [rdx], 0
0x180050d1c  mov     rbx, rcx
0x180050d1f  call    cs:__imp_GetCurrentProcessId
0x180050d25  mov     [rsp+280h+var_258], rbx
0x180050d2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180050d31  mov     r9d, eax
0x180050d34  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180050d3c  mov     edx, 104h; unsigned __int64
0x180050d41  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180050d46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180050d4b  mov     r9d, 1F0001h; dwDesiredAccess
0x180050d51  mov     [rsp+280h+hHandle], 0
0x180050d5a  xor     r8d, r8d; dwFlags
0x180050d5d  lea     rdx, [rsp+280h+Name]; lpName
0x180050d62  xor     ecx, ecx; lpMutexAttributes
0x180050d64  call    cs:__imp_CreateMutexExW
0x180050d6a  mov     rdx, rax
0x180050d6d  lea     rcx, [rsp+280h+hHandle]
0x180050d72  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180050d77  mov     rdi, [rsp+280h+hHandle]
0x180050d7c  test    rdi, rdi
0x180050d7f  jnz     short loc_180050D8D
0x180050d81  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180050d86  mov     esi, eax
0x180050d88  jmp     loc_180050E37
0x180050d8d  xor     r8d, r8d; bAlertable
0x180050d90  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180050d93  mov     rcx, rdi; hHandle
0x180050d96  call    cs:__imp_WaitForSingleObjectEx
0x180050d9c  cmp     eax, 102h
0x180050da1  jz      loc_180050E6A
0x180050da7  test    eax, 0FFFFFF7Fh
0x180050dac  jnz     loc_180050EF4
0x180050db2  mov     rbx, rdi
0x180050db5  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180050dba  mov     [rsp+280h+var_240], rbx
0x180050dbf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180050dc4  mov     [rsp+280h+var_248], 0
0x180050dcd  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180050dd2  mov     esi, eax
0x180050dd4  test    eax, eax
0x180050dd6  jns     loc_180050E71
0x180050ddc  mov     rcx, [rbp+188h]; this
0x180050de3  lea     r8, aWil; "wil"
0x180050dea  mov     r9d, eax; char *
0x180050ded  mov     edx, 66h ; 'f'; void *
0x180050df2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050df7  mov     rcx, [rbp+188h]; this
0x180050dfe  lea     r8, aWil; "wil"
0x180050e05  mov     r9d, esi; char *
0x180050e08  mov     edx, 6Fh ; 'o'; void *
0x180050e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e12  mov     rcx, [rbp+188h]; this
0x180050e19  lea     r8, aWil; "wil"
0x180050e20  mov     r9d, esi; char *
0x180050e23  mov     edx, 12Eh; void *
0x180050e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e2d  lea     rcx, [rsp+280h+var_240]
0x180050e32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050e37  lea     rcx, [rsp+280h+hHandle]
0x180050e3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050e41  mov     eax, esi
0x180050e43  mov     rcx, [rbp+180h+var_20]
0x180050e4a  xor     rcx, rsp; StackCookie
0x180050e4d  call    __security_check_cookie
0x180050e52  lea     r11, [rsp+280h+var_10]
0x180050e5a  mov     rbx, [r11+30h]
0x180050e5e  mov     rsi, [r11+38h]
0x180050e62  mov     rsp, r11
0x180050e65  pop     r14
0x180050e67  pop     rdi
0x180050e68  pop     rbp
0x180050e69  retn
0x180050e6a  xor     ebx, ebx
0x180050e6c  jmp     loc_180050DB5
0x180050e71  mov     rax, [rsp+280h+var_248]
0x180050e76  lea     rcx, ds:0[rax*4]
0x180050e7e  test    rcx, rcx
0x180050e81  jz      short loc_180050EA6
0x180050e83  mov     [r14], rcx
0x180050e86  mov     eax, [rcx]
0x180050e88  inc     eax
0x180050e8a  mov     [rcx], eax
0x180050e8c  test    rbx, rbx
0x180050e8f  jnz     loc_180050F1A
0x180050e95  test    rdi, rdi
0x180050e98  jz      short loc_180050EA2
0x180050e9a  mov     rcx, rdi; this
0x180050e9d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180050ea2  xor     eax, eax
0x180050ea4  jmp     short loc_180050E43
0x180050ea6  mov     r8, r14
0x180050ea9  lea     rdx, [rsp+280h+hHandle]
0x180050eae  lea     rcx, [rsp+280h+Name]
0x180050eb3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180050eb8  mov     edi, eax
0x180050eba  test    eax, eax
0x180050ebc  jns     short loc_180050F10
0x180050ebe  mov     rcx, [rbp+188h]; this
0x180050ec5  lea     r8, aWil; "wil"
0x180050ecc  mov     r9d, eax; char *
0x180050ecf  mov     edx, 137h; void *
0x180050ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ed9  test    rbx, rbx
0x180050edc  jnz     short loc_180050F06
0x180050ede  mov     rcx, [rsp+280h+hHandle]; this
0x180050ee3  test    rcx, rcx
0x180050ee6  jz      short loc_180050EED
0x180050ee8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180050eed  mov     eax, edi
0x180050eef  jmp     loc_180050E43
0x180050ef4  mov     rcx, [rbp+188h]; this
0x180050efb  mov     edx, 0E01h; void *
0x180050f00  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180050f06  mov     rcx, rbx; this
0x180050f09  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180050f0e  jmp     short loc_180050EDE
0x180050f10  mov     rdi, [rsp+280h+hHandle]
0x180050f15  jmp     loc_180050E8C
0x180050f1a  mov     rcx, rbx; this
0x180050f1d  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180050f22  jmp     loc_180050E95
```
