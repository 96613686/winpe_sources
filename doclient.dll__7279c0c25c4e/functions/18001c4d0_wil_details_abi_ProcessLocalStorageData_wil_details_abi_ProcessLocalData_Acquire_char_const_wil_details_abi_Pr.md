# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001c4d0`
- end: `0x18001c6d2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `514`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b518`

## callees

- `0x180008450`
- `0x180008a54`
- `0x180008d44`
- `0x18000933c`
- `0x18000a4e0`
- `0x18001b034`
- `0x18001c4d0`
- `0x18001c928`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c569`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c50b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c50b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c5a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c5a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c547`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c547`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c64c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c64c`

## string_xrefs

- `0x18001c69c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  unsigned int LastErrorFailHr; // edi
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD v11; // eax
  bool v12; // dl
  char *v13; // r9
  void *v14; // rsi
  int ValueInternal; // eax
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  unsigned int v18; // r8d
  const char *v19; // r9
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v11 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v14 = 0;
  }
  else
  {
    if ( (v11 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC2D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    v14 = v6;
  }
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v12, &v24, (bool *)v13);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
    v16 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)LastErrorFailHr, v21);
    goto LABEL_15;
  }
  v17 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            Name,
            &v23,
            a2);
    v6 = v23;
    LastErrorFailHr = v20;
    if ( v20 < 0 )
    {
      v16 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v14 && !ReleaseMutex(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DB, v18, v19);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v8, v9);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001c4d0  mov     [rsp-8+arg_10], rbx
0x18001c4d5  mov     [rsp-8+arg_18], rsi
0x18001c4da  push    rbp
0x18001c4db  push    rdi
0x18001c4dc  push    r14
0x18001c4de  lea     rbp, [rsp-160h]
0x18001c4e6  sub     rsp, 260h
0x18001c4ed  mov     rax, cs:__security_cookie
0x18001c4f4  xor     rax, rsp
0x18001c4f7  mov     [rbp+170h+var_20], rax
0x18001c4fe  mov     r14, rdx
0x18001c501  mov     qword ptr [rdx], 0
0x18001c508  mov     rbx, rcx
0x18001c50b  call    cs:__imp_GetCurrentProcessId
0x18001c511  mov     [rsp+270h+var_248], rbx
0x18001c516  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001c51d  mov     r9d, eax
0x18001c520  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001c528  mov     edx, 104h; unsigned __int64
0x18001c52d  lea     rcx, [rsp+270h+Name]; Buffer
0x18001c532  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001c537  mov     r9d, 1F0001h; dwDesiredAccess
0x18001c53d  lea     rdx, [rsp+270h+Name]; lpName
0x18001c542  xor     r8d, r8d; dwFlags
0x18001c545  xor     ecx, ecx; lpMutexAttributes
0x18001c547  call    cs:__imp_CreateMutexExW
0x18001c54d  mov     [rsp+270h+var_240], rax
0x18001c552  mov     rbx, rax
0x18001c555  test    rax, rax
0x18001c558  jnz     short loc_18001C5A0
0x18001c55a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c55f  mov     edi, eax
0x18001c561  test    rbx, rbx
0x18001c564  jz      short loc_18001C577
0x18001c566  mov     rcx, rbx; hObject
0x18001c569  call    cs:__imp_CloseHandle
0x18001c56f  test    eax, eax
0x18001c571  jz      loc_18001C6C0
0x18001c577  mov     eax, edi
0x18001c579  mov     rcx, [rbp+170h+var_20]
0x18001c580  xor     rcx, rsp; StackCookie
0x18001c583  call    __security_check_cookie
0x18001c588  lea     r11, [rsp+270h+var_10]
0x18001c590  mov     rbx, [r11+30h]
0x18001c594  mov     rsi, [r11+38h]
0x18001c598  mov     rsp, r11
0x18001c59b  pop     r14
0x18001c59d  pop     rdi
0x18001c59e  pop     rbp
0x18001c59f  retn
0x18001c5a0  xor     r8d, r8d; bAlertable
0x18001c5a3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c5a6  mov     rcx, rbx; hHandle
0x18001c5a9  call    cs:__imp_WaitForSingleObjectEx
0x18001c5af  cmp     eax, 102h
0x18001c5b4  jz      short loc_18001C5C6
0x18001c5b6  test    eax, 0FFFFFF7Fh
0x18001c5bb  jnz     loc_18001C695
0x18001c5c1  mov     rsi, rbx
0x18001c5c4  jmp     short loc_18001C5C8
0x18001c5c6  xor     esi, esi
0x18001c5c8  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18001c5cd  mov     [rsp+270h+var_238], 0
0x18001c5d6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001c5db  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18001c5e0  mov     edi, eax
0x18001c5e2  test    eax, eax
0x18001c5e4  jns     short loc_18001C623
0x18001c5e6  mov     rcx, [rbp+178h]; this
0x18001c5ed  lea     r8, aWil; "wil"
0x18001c5f4  mov     r9d, eax; char *
0x18001c5f7  mov     edx, 64h ; 'd'; void *
0x18001c5fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c601  mov     rcx, [rbp+178h]; this
0x18001c608  lea     r8, aWil; "wil"
0x18001c60f  mov     r9d, edi; char *
0x18001c612  mov     edx, 6Dh ; 'm'; void *
0x18001c617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c61c  mov     edx, 12Bh
0x18001c621  jmp     short loc_18001C67D
0x18001c623  mov     rax, [rsp+270h+var_238]
0x18001c628  lea     rcx, ds:0[rax*4]
0x18001c630  test    rcx, rcx
0x18001c633  jz      short loc_18001C65B
0x18001c635  mov     [r14], rcx
0x18001c638  mov     eax, [rcx]
0x18001c63a  inc     eax
0x18001c63c  mov     [rcx], eax
0x18001c63e  xor     edi, edi
0x18001c640  test    rsi, rsi
0x18001c643  jz      loc_18001C561
0x18001c649  mov     rcx, rsi; hMutex
0x18001c64c  call    cs:__imp_ReleaseMutex
0x18001c652  test    eax, eax
0x18001c654  jz      short loc_18001C6AE
0x18001c656  jmp     loc_18001C561
0x18001c65b  mov     r8, r14
0x18001c65e  lea     rdx, [rsp+270h+var_240]
0x18001c663  lea     rcx, [rsp+270h+Name]
0x18001c668  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001c66d  mov     rbx, [rsp+270h+var_240]
0x18001c672  mov     edi, eax
0x18001c674  test    eax, eax
0x18001c676  jns     short loc_18001C63E
0x18001c678  mov     edx, 134h; void *
0x18001c67d  mov     rcx, [rbp+178h]; this
0x18001c684  lea     r8, aWil; "wil"
0x18001c68b  mov     r9d, edi; char *
0x18001c68e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c693  jmp     short loc_18001C640
0x18001c695  mov     rcx, [rbp+178h]; this
0x18001c69c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001c6a3  mov     edx, 0C2Dh; void *
0x18001c6a8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001c6ae  mov     rcx, [rbp+178h]; this
0x18001c6b5  mov     edx, 9DBh; void *
0x18001c6ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c6c0  mov     rcx, [rbp+178h]; this
0x18001c6c7  mov     edx, 9D1h; void *
0x18001c6cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
