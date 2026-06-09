# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008d68`
- end: `0x180008f61`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002e648`

## callees

- `0x18000892c`
- `0x180008d68`
- `0x180009340`
- `0x180020914`
- `0x1800214cc`
- `0x180021e70`
- `0x1800222a0`
- `0x1800234e0`
- `0x180023908`
- `0x1800254e0`
- `0x180029258`
- `0x180029c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008e07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008e07`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ddf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ddf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008da3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008da3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v23[0] = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v22, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    LastErrorFailHr = v15;
    goto LABEL_14;
  }
  v16 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v16;
    ++*v16;
  }
  else
  {
    v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v17,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x180008d68  mov     [rsp-8+arg_10], rbx
0x180008d6d  mov     [rsp-8+arg_18], rsi
0x180008d72  push    rbp
0x180008d73  push    rdi
0x180008d74  push    r14
0x180008d76  lea     rbp, [rsp-170h]
0x180008d7e  sub     rsp, 270h
0x180008d85  mov     rax, cs:__security_cookie
0x180008d8c  xor     rax, rsp
0x180008d8f  mov     [rbp+180h+var_20], rax
0x180008d96  mov     r14, rdx
0x180008d99  mov     qword ptr [rdx], 0
0x180008da0  mov     rbx, rcx
0x180008da3  call    cs:__imp_GetCurrentProcessId
0x180008da9  mov     [rsp+280h+var_258], rbx
0x180008dae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008db5  mov     r9d, eax
0x180008db8  mov     [rsp+280h+var_260], 130h; int
0x180008dc0  mov     edx, 104h; unsigned __int64
0x180008dc5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008dca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008dcf  mov     r9d, 1F0001h; dwDesiredAccess
0x180008dd5  lea     rdx, [rsp+280h+Name]; lpName
0x180008dda  xor     r8d, r8d; dwFlags
0x180008ddd  xor     ecx, ecx; lpMutexAttributes
0x180008ddf  call    cs:__imp_CreateMutexExW
0x180008de5  mov     [rsp+280h+var_250], rax
0x180008dea  mov     rbx, rax
0x180008ded  test    rax, rax
0x180008df0  jnz     short loc_180008DFE
0x180008df2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008df7  mov     ebx, eax
0x180008df9  jmp     loc_180008F0B
0x180008dfe  xor     r8d, r8d; bAlertable
0x180008e01  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008e04  mov     rcx, rbx; hHandle
0x180008e07  call    cs:__imp_WaitForSingleObjectEx
0x180008e0d  cmp     eax, 102h
0x180008e12  jz      short loc_180008E2D
0x180008e14  test    eax, 0FFFFFF7Fh
0x180008e19  jz      short loc_180008E28
0x180008e1b  mov     rcx, [rbp+188h]; this
0x180008e22  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008e28  mov     rdi, rbx
0x180008e2b  jmp     short loc_180008E2F
0x180008e2d  xor     edi, edi
0x180008e2f  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180008e34  mov     [rsp+280h+var_240], rdi
0x180008e39  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008e3e  mov     [rsp+280h+var_248], 0
0x180008e47  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008e4c  mov     esi, eax
0x180008e4e  test    eax, eax
0x180008e50  jns     short loc_180008EB1
0x180008e52  mov     rcx, [rbp+188h]; this
0x180008e59  lea     r8, aWil; "wil"
0x180008e60  mov     r9d, eax; char *
0x180008e63  mov     edx, 66h ; 'f'; void *
0x180008e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e6d  mov     rcx, [rbp+188h]; this
0x180008e74  lea     r8, aWil; "wil"
0x180008e7b  mov     r9d, esi; char *
0x180008e7e  mov     edx, 6Fh ; 'o'; void *
0x180008e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e88  mov     rcx, [rbp+188h]; this
0x180008e8f  lea     r8, aWil; "wil"
0x180008e96  mov     r9d, esi; char *
0x180008e99  mov     edx, 12Eh; void *
0x180008e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ea3  lea     rcx, [rsp+280h+var_240]
0x180008ea8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008ead  mov     ebx, esi
0x180008eaf  jmp     short loc_180008F0B
0x180008eb1  mov     rax, [rsp+280h+var_248]
0x180008eb6  lea     rcx, ds:0[rax*4]
0x180008ebe  test    rcx, rcx
0x180008ec1  jz      short loc_180008ECE
0x180008ec3  mov     [r14], rcx
0x180008ec6  mov     eax, [rcx]
0x180008ec8  inc     eax
0x180008eca  mov     [rcx], eax
0x180008ecc  jmp     short loc_180008F1E
0x180008ece  mov     r8, r14
0x180008ed1  lea     rdx, [rsp+280h+var_250]
0x180008ed6  lea     rcx, [rsp+280h+Name]
0x180008edb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008ee0  mov     ebx, eax
0x180008ee2  test    eax, eax
0x180008ee4  jns     short loc_180008F19
0x180008ee6  mov     rcx, [rbp+188h]; this
0x180008eed  lea     r8, aWil; "wil"
0x180008ef4  mov     r9d, eax; char *
0x180008ef7  mov     edx, 137h; void *
0x180008efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f01  lea     rcx, [rsp+280h+var_240]
0x180008f06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008f0b  lea     rcx, [rsp+280h+var_250]
0x180008f10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008f15  mov     eax, ebx
0x180008f17  jmp     short loc_180008F3A
0x180008f19  mov     rbx, [rsp+280h+var_250]
0x180008f1e  test    rdi, rdi
0x180008f21  jz      short loc_180008F2B
0x180008f23  mov     rcx, rdi; this
0x180008f26  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180008f2b  test    rbx, rbx
0x180008f2e  jz      short loc_180008F38
0x180008f30  mov     rcx, rbx; this
0x180008f33  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008f38  xor     eax, eax
0x180008f3a  mov     rcx, [rbp+180h+var_20]
0x180008f41  xor     rcx, rsp; StackCookie
0x180008f44  call    __security_check_cookie
0x180008f49  lea     r11, [rsp+280h+var_10]
0x180008f51  mov     rbx, [r11+30h]
0x180008f55  mov     rsi, [r11+38h]
0x180008f59  mov     rsp, r11
0x180008f5c  pop     r14
0x180008f5e  pop     rdi
0x180008f5f  pop     rbp
0x180008f60  retn
```
