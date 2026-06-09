# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18005c464`
- end: `0x18005c679`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005c40c`

## callees

- `0x18002c8d0`
- `0x18002eb8c`
- `0x18005c224`
- `0x18005c464`
- `0x18005c680`
- `0x18005c720`
- `0x18005cb08`
- `0x18005e01c`
- `0x1800862f0`
- `0x1800897a4`
- `0x180089c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005c4db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005c4db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005c523`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005c523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005c49f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005c49f`

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
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  void *v17; // rdx
  void *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
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
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v24, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v22);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v17);
    wil::details::CloseHandle(v6, v17);
    return v15;
  }
  else
  {
    v16 = (_DWORD *)(4 * v24);
    if ( 4 * v24 )
    {
      *a2 = v16;
      ++*v16;
LABEL_8:
      if ( v12 )
        wil::details::ReleaseMutex(v12, v14);
      if ( v6 )
        wil::details::CloseHandle(v6, v14);
      return 0;
    }
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v6 = v23;
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v19, 304);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    return v20;
  }
}

```

## disassembly

```asm
0x18005c464  mov     [rsp-8+arg_10], rbx
0x18005c469  mov     [rsp-8+arg_18], rsi
0x18005c46e  push    rbp
0x18005c46f  push    rdi
0x18005c470  push    r14
0x18005c472  lea     rbp, [rsp-160h]
0x18005c47a  sub     rsp, 260h
0x18005c481  mov     rax, cs:__security_cookie
0x18005c488  xor     rax, rsp
0x18005c48b  mov     [rbp+170h+var_20], rax
0x18005c492  mov     r14, rdx
0x18005c495  mov     qword ptr [rdx], 0
0x18005c49c  mov     rbx, rcx
0x18005c49f  call    cs:__imp_GetCurrentProcessId
0x18005c4a5  mov     [rsp+270h+var_248], rbx
0x18005c4aa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005c4b1  mov     r9d, eax
0x18005c4b4  mov     [rsp+270h+var_250], 130h; int
0x18005c4bc  mov     edx, 104h; unsigned __int64
0x18005c4c1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005c4c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005c4cb  mov     r9d, 1F0001h; dwDesiredAccess
0x18005c4d1  lea     rdx, [rsp+270h+Name]; lpName
0x18005c4d6  xor     r8d, r8d; dwFlags
0x18005c4d9  xor     ecx, ecx; lpMutexAttributes
0x18005c4db  call    cs:__imp_CreateMutexExW
0x18005c4e1  mov     [rsp+270h+var_240], rax
0x18005c4e6  mov     rbx, rax
0x18005c4e9  test    rax, rax
0x18005c4ec  jnz     short loc_18005C51A
0x18005c4ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005c4f3  mov     rcx, [rbp+170h+var_20]
0x18005c4fa  xor     rcx, rsp; StackCookie
0x18005c4fd  call    __security_check_cookie
0x18005c502  lea     r11, [rsp+270h+var_10]
0x18005c50a  mov     rbx, [r11+30h]
0x18005c50e  mov     rsi, [r11+38h]
0x18005c512  mov     rsp, r11
0x18005c515  pop     r14
0x18005c517  pop     rdi
0x18005c518  pop     rbp
0x18005c519  retn
0x18005c51a  xor     r8d, r8d; bAlertable
0x18005c51d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005c520  mov     rcx, rbx; hHandle
0x18005c523  call    cs:__imp_WaitForSingleObjectEx
0x18005c529  cmp     eax, 102h
0x18005c52e  jnz     short loc_18005C588
0x18005c530  xor     edi, edi
0x18005c532  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18005c537  mov     [rsp+270h+var_238], 0
0x18005c540  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005c545  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18005c54a  mov     esi, eax
0x18005c54c  test    eax, eax
0x18005c54e  js      short loc_18005C5A2
0x18005c550  mov     rax, [rsp+270h+var_238]
0x18005c555  lea     rcx, ds:0[rax*4]
0x18005c55d  test    rcx, rcx
0x18005c560  jz      loc_18005C657
0x18005c566  mov     [r14], rcx
0x18005c569  mov     eax, [rcx]
0x18005c56b  inc     eax
0x18005c56d  mov     [rcx], eax
0x18005c56f  test    rdi, rdi
0x18005c572  jnz     short loc_18005C598
0x18005c574  test    rbx, rbx
0x18005c577  jz      short loc_18005C581
0x18005c579  mov     rcx, rbx; this
0x18005c57c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c581  xor     eax, eax
0x18005c583  jmp     loc_18005C4F3
0x18005c588  test    eax, 0FFFFFF7Fh
0x18005c58d  jnz     loc_18005C64A
0x18005c593  mov     rdi, rbx
0x18005c596  jmp     short loc_18005C532
0x18005c598  mov     rcx, rdi; this
0x18005c59b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005c5a0  jmp     short loc_18005C574
0x18005c5a2  mov     rcx, [rbp+178h]; this
0x18005c5a9  lea     r8, aWil; "wil"
0x18005c5b0  mov     r9d, esi; char *
0x18005c5b3  mov     edx, 66h ; 'f'; void *
0x18005c5b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5bd  mov     rcx, [rbp+178h]; this
0x18005c5c4  lea     r8, aWil; "wil"
0x18005c5cb  mov     r9d, esi; char *
0x18005c5ce  mov     edx, 6Fh ; 'o'; void *
0x18005c5d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5d8  mov     rcx, [rbp+178h]; this
0x18005c5df  lea     r8, aWil; "wil"
0x18005c5e6  mov     r9d, esi; char *
0x18005c5e9  mov     edx, 12Eh; void *
0x18005c5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5f3  test    rdi, rdi
0x18005c5f6  jnz     short loc_18005C607
0x18005c5f8  mov     rcx, rbx; this
0x18005c5fb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c600  mov     eax, esi
0x18005c602  jmp     loc_18005C4F3
0x18005c607  mov     rcx, rdi; this
0x18005c60a  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005c60f  jmp     short loc_18005C5F8
0x18005c611  mov     rcx, [rbp+178h]; this
0x18005c618  lea     r8, aWil; "wil"
0x18005c61f  mov     r9d, ebx; char *
0x18005c622  mov     edx, 137h; void *
0x18005c627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c62c  test    rdi, rdi
0x18005c62f  jz      short loc_18005C639
0x18005c631  mov     rcx, rdi; this
0x18005c634  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18005c639  lea     rcx, [rsp+270h+var_240]
0x18005c63e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c643  mov     eax, ebx
0x18005c645  jmp     loc_18005C4F3
0x18005c64a  mov     rcx, [rbp+178h]; this
0x18005c651  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18005c657  mov     r8, r14
0x18005c65a  lea     rdx, [rsp+270h+var_240]
0x18005c65f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005c664  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005c669  mov     ebx, eax
0x18005c66b  test    eax, eax
0x18005c66d  js      short loc_18005C611
0x18005c66f  mov     rbx, [rsp+270h+var_240]
0x18005c674  jmp     loc_18005C56F
```
