# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180017fdc`
- end: `0x18001840b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800195b4`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000e36c`
- `0x18000e994`
- `0x18000ebdc`
- `0x18000f1a0`
- `0x18000fa94`
- `0x18000ff24`
- `0x18001079c`
- `0x18001087c`
- `0x180010d94`
- `0x18001694c`
- `0x180017fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800182cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800182cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018080`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018080`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018059`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018059`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018120`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001823d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001830e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018120`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001823d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001830e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001820e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001820e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800181fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800181fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018137`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001832a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018137`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001832a`

## string_xrefs

- `0x18001836a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180018383`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800183ae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800183c7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800183e0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800183f9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  _DWORD *v19; // rax
  _DWORD *v20; // r14
  int v21; // eax
  HANDLE ProcessHeap; // rax
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v30[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v30, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v27);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v28);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v30[0]);
  if ( 4 * v30[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_23;
  }
  *a2 = 0;
  v19 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v20 = v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v30 = 0;
  v21 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v30, Name, v19);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v21, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v29);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return v15;
  }
  *((_QWORD *)v20 + 2) = v30[0];
  *((_QWORD *)v20 + 3) = v30[1];
  *v20 = 1;
  *((_QWORD *)v20 + 1) = v6;
  v30[0] = 0;
  v30[1] = 0;
  memset_0(v20 + 10, 0, 0x108u);
  *((_QWORD *)v20 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v20 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v20 + 58), 0, 0);
  *((_QWORD *)v20 + 34) = 0;
  *((_QWORD *)v20 + 35) = 0;
  *((_QWORD *)v20 + 36) = 0;
  *((_QWORD *)v20 + 37) = 0;
  *a2 = v20;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v30);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return 0;
}

```

## disassembly

```asm
0x180017fdc  mov     [rsp-8+arg_10], rbx
0x180017fe1  push    rbp
0x180017fe2  push    rsi
0x180017fe3  push    rdi
0x180017fe4  push    r14
0x180017fe6  push    r15
0x180017fe8  lea     rbp, [rsp-160h]
0x180017ff0  sub     rsp, 260h
0x180017ff7  mov     rax, cs:__security_cookie
0x180017ffe  xor     rax, rsp
0x180018001  mov     [rbp+180h+var_30], rax
0x180018008  mov     r15, rdx
0x18001800b  mov     qword ptr [rdx], 0
0x180018012  mov     rbx, rcx
0x180018015  call    cs:__imp_GetCurrentProcessId
0x18001801c  nop     dword ptr [rax+rax+00h]
0x180018021  mov     r14d, 130h
0x180018027  mov     [rsp+280h+var_258], rbx
0x18001802c  mov     r9d, eax
0x18001802f  mov     [rsp+280h+var_260], r14d; int
0x180018034  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001803b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018040  lea     edx, [r14-2Ch]; unsigned __int64
0x180018044  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018049  mov     r9d, 1F0001h; dwDesiredAccess
0x18001804f  lea     rdx, [rsp+280h+Name]; lpName
0x180018054  xor     r8d, r8d; dwFlags
0x180018057  xor     ecx, ecx; lpMutexAttributes
0x180018059  call    cs:__imp_CreateMutexExW
0x180018060  nop     dword ptr [rax+rax+00h]
0x180018065  mov     rbx, rax
0x180018068  test    rax, rax
0x18001806b  jnz     short loc_180018077
0x18001806d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018072  jmp     loc_18001833C
0x180018077  xor     r8d, r8d; bAlertable
0x18001807a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001807d  mov     rcx, rbx; hHandle
0x180018080  call    cs:__imp_WaitForSingleObjectEx
0x180018087  nop     dword ptr [rax+rax+00h]
0x18001808c  cmp     eax, 102h
0x180018091  jz      short loc_1800180A3
0x180018093  test    eax, 0FFFFFF7Fh
0x180018098  jnz     loc_180018395
0x18001809e  mov     rdi, rbx
0x1800180a1  jmp     short loc_1800180A5
0x1800180a3  xor     edi, edi
0x1800180a5  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800180aa  mov     [rsp+280h+var_250], 0
0x1800180b3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800180b8  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800180bd  mov     esi, eax
0x1800180bf  test    eax, eax
0x1800180c1  jns     loc_180018152
0x1800180c7  mov     rcx, [rbp+188h]; this
0x1800180ce  lea     r8, aWil; "wil"
0x1800180d5  mov     r9d, eax; char *
0x1800180d8  mov     edx, 66h ; 'f'; void *
0x1800180dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180e2  mov     rcx, [rbp+188h]; this
0x1800180e9  lea     r8, aWil; "wil"
0x1800180f0  mov     r9d, esi; char *
0x1800180f3  mov     edx, 6Fh ; 'o'; void *
0x1800180f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180fd  mov     rcx, [rbp+188h]; this
0x180018104  lea     r8, aWil; "wil"
0x18001810b  mov     r9d, esi; char *
0x18001810e  mov     edx, 12Eh; void *
0x180018113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018118  test    rdi, rdi
0x18001811b  jz      short loc_180018134
0x18001811d  mov     rcx, rdi; hMutex
0x180018120  call    cs:__imp_ReleaseMutex
0x180018127  nop     dword ptr [rax+rax+00h]
0x18001812c  test    eax, eax
0x18001812e  jz      loc_1800183A7
0x180018134  mov     rcx, rbx; hObject
0x180018137  call    cs:__imp_CloseHandle
0x18001813e  nop     dword ptr [rax+rax+00h]
0x180018143  test    eax, eax
0x180018145  jz      loc_1800183C0
0x18001814b  mov     eax, esi
0x18001814d  jmp     loc_18001833C
0x180018152  mov     rax, [rsp+280h+var_250]
0x180018157  lea     rcx, ds:0[rax*4]
0x18001815f  test    rcx, rcx
0x180018162  jz      short loc_180018172
0x180018164  mov     [r15], rcx
0x180018167  mov     eax, [rcx]
0x180018169  inc     eax
0x18001816b  mov     [rcx], eax
0x18001816d  jmp     loc_180018306
0x180018172  mov     rdx, r14; dwBytes
0x180018175  mov     qword ptr [r15], 0
0x18001817c  mov     ecx, 8; dwFlags
0x180018181  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180018186  mov     r14, rax
0x180018189  test    rax, rax
0x18001818c  jnz     short loc_1800181B0
0x18001818e  mov     rcx, [rbp+188h]; this
0x180018195  lea     r8, aWil; "wil"
0x18001819c  mov     esi, 8007000Eh
0x1800181a1  mov     edx, 14Bh; void *
0x1800181a6  mov     r9d, esi; char *
0x1800181a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181ae  jmp     short loc_18001821A
0x1800181b0  xorps   xmm0, xmm0
0x1800181b3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800181b8  mov     r8, r14; void *
0x1800181bb  lea     rcx, [rsp+280h+var_250]; this
0x1800181c0  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800181c6  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800181cb  mov     esi, eax
0x1800181cd  test    eax, eax
0x1800181cf  jns     loc_18001826D
0x1800181d5  mov     rcx, [rbp+188h]; this
0x1800181dc  lea     r8, aWil; "wil"
0x1800181e3  mov     r9d, eax; char *
0x1800181e6  mov     edx, 14Eh; void *
0x1800181eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181f0  lea     rcx, [rsp+280h+var_250]; this
0x1800181f5  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800181fa  call    cs:__imp_GetProcessHeap
0x180018201  nop     dword ptr [rax+rax+00h]
0x180018206  mov     r8, r14; lpMem
0x180018209  xor     edx, edx; dwFlags
0x18001820b  mov     rcx, rax; hHeap
0x18001820e  call    cs:__imp_HeapFree
0x180018215  nop     dword ptr [rax+rax+00h]
0x18001821a  mov     rcx, [rbp+188h]; this
0x180018221  lea     r8, aWil; "wil"
0x180018228  mov     r9d, esi; char *
0x18001822b  mov     edx, 137h; void *
0x180018230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018235  test    rdi, rdi
0x180018238  jz      short loc_180018251
0x18001823a  mov     rcx, rdi; hMutex
0x18001823d  call    cs:__imp_ReleaseMutex
0x180018244  nop     dword ptr [rax+rax+00h]
0x180018249  test    eax, eax
0x18001824b  jz      loc_1800183D9
0x180018251  mov     rcx, rbx; hObject
0x180018254  call    cs:__imp_CloseHandle
0x18001825b  nop     dword ptr [rax+rax+00h]
0x180018260  test    eax, eax
0x180018262  jz      loc_18001837C
0x180018268  jmp     loc_18001814B
0x18001826d  mov     rax, [rsp+280h+var_250]
0x180018272  lea     rcx, [r14+28h]; void *
0x180018276  mov     [r14+10h], rax
0x18001827a  xor     edx, edx; Val
0x18001827c  mov     rax, [rsp+280h+var_250+8]
0x180018281  mov     r8d, 108h; Size
0x180018287  mov     [r14+18h], rax
0x18001828b  mov     dword ptr [r14], 1
0x180018292  mov     [r14+8], rbx
0x180018296  mov     [rsp+280h+var_250], 0
0x18001829f  mov     [rsp+280h+var_250+8], 0
0x1800182a8  call    memset_0
0x1800182ad  xor     eax, eax
0x1800182af  lea     rcx, [r14+28h]; this
0x1800182b3  mov     [r14+20h], rax
0x1800182b7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800182bc  lea     rbx, [r14+0E8h]
0x1800182c3  xor     r8d, r8d; Flags
0x1800182c6  mov     rcx, rbx; lpCriticalSection
0x1800182c9  xor     edx, edx; dwSpinCount
0x1800182cb  call    cs:__imp_InitializeCriticalSectionEx
0x1800182d2  nop     dword ptr [rax+rax+00h]
0x1800182d7  mov     qword ptr [rbx+28h], 0
0x1800182df  lea     rcx, [rsp+280h+var_250]; this
0x1800182e4  mov     qword ptr [rbx+30h], 0
0x1800182ec  mov     qword ptr [rbx+38h], 0
0x1800182f4  mov     qword ptr [rbx+40h], 0
0x1800182fc  mov     [r15], r14
0x1800182ff  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180018304  xor     ebx, ebx
0x180018306  test    rdi, rdi
0x180018309  jz      short loc_180018322
0x18001830b  mov     rcx, rdi; hMutex
0x18001830e  call    cs:__imp_ReleaseMutex
0x180018315  nop     dword ptr [rax+rax+00h]
0x18001831a  test    eax, eax
0x18001831c  jz      loc_1800183F2
0x180018322  test    rbx, rbx
0x180018325  jz      short loc_18001833A
0x180018327  mov     rcx, rbx; hObject
0x18001832a  call    cs:__imp_CloseHandle
0x180018331  nop     dword ptr [rax+rax+00h]
0x180018336  test    eax, eax
0x180018338  jz      short loc_180018363
0x18001833a  xor     eax, eax
0x18001833c  mov     rcx, [rbp+180h+var_30]
0x180018343  xor     rcx, rsp; StackCookie
0x180018346  call    __security_check_cookie
0x18001834b  mov     rbx, [rsp+280h+arg_10]
0x180018353  add     rsp, 260h
0x18001835a  pop     r15
0x18001835c  pop     r14
0x18001835e  pop     rdi
0x18001835f  pop     rsi
0x180018360  pop     rbp
0x180018361  retn
0x180018363  mov     rcx, [rbp+188h]; this
0x18001836a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018371  mov     edx, 0A0Bh; void *
0x180018376  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001837c  mov     rcx, [rbp+188h]; this
0x180018383  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001838a  mov     edx, 0A0Bh; void *
0x18001838f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018395  mov     rcx, [rbp+188h]; this
0x18001839c  mov     edx, 0E01h; void *
0x1800183a1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800183a7  mov     rcx, [rbp+188h]; this
0x1800183ae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183b5  mov     edx, 0A15h; void *
0x1800183ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800183c0  mov     rcx, [rbp+188h]; this
0x1800183c7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183ce  mov     edx, 0A0Bh; void *
0x1800183d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800183d9  mov     rcx, [rbp+188h]; this
0x1800183e0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183e7  mov     edx, 0A15h; void *
0x1800183ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800183f2  mov     rcx, [rbp+188h]; this
0x1800183f9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018400  mov     edx, 0A15h; void *
0x180018405  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
