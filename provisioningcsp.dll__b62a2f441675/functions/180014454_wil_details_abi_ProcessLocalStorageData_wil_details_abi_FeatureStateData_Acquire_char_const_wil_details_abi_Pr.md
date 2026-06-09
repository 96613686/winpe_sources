# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180014454`
- end: `0x180014860`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1036`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180016c58`

## callees

- `0x180004988`
- `0x180004fbc`
- `0x18000526c`
- `0x180005870`
- `0x1800064c4`
- `0x180006974`
- `0x180007268`
- `0x18000734c`
- `0x180007834`
- `0x180013c58`
- `0x180014454`
- `0x18003586a`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001448d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001448d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180014743`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180014743`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800144f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800144f8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800144d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800144d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014598`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800146b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014786`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014598`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800146b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014672`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147a2`

## string_xrefs

- `0x180014806`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v35[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v35[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v35, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v32);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v33);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v35[0]);
  if ( 4 * v35[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_23;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v35 = 0;
  v22 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v35, Name, v20);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v35);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v34);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v35[0];
  *((_QWORD *)v21 + 3) = v35[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v35[0] = 0;
  v35[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v35);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v28, v29);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
  return 0;
}

```

## disassembly

```asm
0x180014454  mov     [rsp-8+arg_10], rbx
0x180014459  push    rbp
0x18001445a  push    rsi
0x18001445b  push    rdi
0x18001445c  push    r14
0x18001445e  push    r15
0x180014460  lea     rbp, [rsp-160h]
0x180014468  sub     rsp, 260h
0x18001446f  mov     rax, cs:__security_cookie
0x180014476  xor     rax, rsp
0x180014479  mov     [rbp+180h+var_30], rax
0x180014480  mov     r15, rdx
0x180014483  mov     qword ptr [rdx], 0
0x18001448a  mov     rbx, rcx
0x18001448d  call    cs:__imp_GetCurrentProcessId
0x180014494  nop     dword ptr [rax+rax+00h]
0x180014499  mov     r14d, 130h
0x18001449f  mov     [rsp+280h+var_258], rbx
0x1800144a4  mov     r9d, eax
0x1800144a7  mov     [rsp+280h+var_260], r14d; int
0x1800144ac  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800144b3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800144b8  lea     edx, [r14-2Ch]; unsigned __int64
0x1800144bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800144c1  mov     r9d, 1F0001h; dwDesiredAccess
0x1800144c7  lea     rdx, [rsp+280h+Name]; lpName
0x1800144cc  xor     r8d, r8d; dwFlags
0x1800144cf  xor     ecx, ecx; lpMutexAttributes
0x1800144d1  call    cs:__imp_CreateMutexExW
0x1800144d8  nop     dword ptr [rax+rax+00h]
0x1800144dd  mov     rbx, rax
0x1800144e0  test    rax, rax
0x1800144e3  jnz     short loc_1800144EF
0x1800144e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800144ea  jmp     loc_1800147B4
0x1800144ef  xor     r8d, r8d; bAlertable
0x1800144f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800144f5  mov     rcx, rbx; hHandle
0x1800144f8  call    cs:__imp_WaitForSingleObjectEx
0x1800144ff  nop     dword ptr [rax+rax+00h]
0x180014504  cmp     eax, 102h
0x180014509  jz      short loc_18001451B
0x18001450b  test    eax, 0FFFFFF7Fh
0x180014510  jnz     loc_1800147FF
0x180014516  mov     rdi, rbx
0x180014519  jmp     short loc_18001451D
0x18001451b  xor     edi, edi
0x18001451d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180014522  mov     [rsp+280h+var_250], 0
0x18001452b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014530  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180014535  mov     esi, eax
0x180014537  test    eax, eax
0x180014539  jns     loc_1800145CA
0x18001453f  mov     rcx, [rbp+188h]; this
0x180014546  lea     r8, aWil; "wil"
0x18001454d  mov     r9d, eax; char *
0x180014550  mov     edx, 66h ; 'f'; void *
0x180014555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001455a  mov     rcx, [rbp+188h]; this
0x180014561  lea     r8, aWil; "wil"
0x180014568  mov     r9d, esi; char *
0x18001456b  mov     edx, 6Fh ; 'o'; void *
0x180014570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014575  mov     rcx, [rbp+188h]; this
0x18001457c  lea     r8, aWil; "wil"
0x180014583  mov     r9d, esi; char *
0x180014586  mov     edx, 12Eh; void *
0x18001458b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014590  test    rdi, rdi
0x180014593  jz      short loc_1800145AC
0x180014595  mov     rcx, rdi; hMutex
0x180014598  call    cs:__imp_ReleaseMutex
0x18001459f  nop     dword ptr [rax+rax+00h]
0x1800145a4  test    eax, eax
0x1800145a6  jz      loc_180014818
0x1800145ac  mov     rcx, rbx; hObject
0x1800145af  call    cs:__imp_CloseHandle
0x1800145b6  nop     dword ptr [rax+rax+00h]
0x1800145bb  test    eax, eax
0x1800145bd  jz      loc_18001482A
0x1800145c3  mov     eax, esi
0x1800145c5  jmp     loc_1800147B4
0x1800145ca  mov     rax, [rsp+280h+var_250]
0x1800145cf  lea     rcx, ds:0[rax*4]
0x1800145d7  test    rcx, rcx
0x1800145da  jz      short loc_1800145EA
0x1800145dc  mov     [r15], rcx
0x1800145df  mov     eax, [rcx]
0x1800145e1  inc     eax
0x1800145e3  mov     [rcx], eax
0x1800145e5  jmp     loc_18001477E
0x1800145ea  mov     rdx, r14; dwBytes
0x1800145ed  mov     qword ptr [r15], 0
0x1800145f4  mov     ecx, 8; dwFlags
0x1800145f9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800145fe  mov     r14, rax
0x180014601  test    rax, rax
0x180014604  jnz     short loc_180014628
0x180014606  mov     rcx, [rbp+188h]; this
0x18001460d  lea     r8, aWil; "wil"
0x180014614  mov     esi, 8007000Eh
0x180014619  mov     edx, 14Bh; void *
0x18001461e  mov     r9d, esi; char *
0x180014621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014626  jmp     short loc_180014692
0x180014628  xorps   xmm0, xmm0
0x18001462b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180014630  mov     r8, r14; void *
0x180014633  lea     rcx, [rsp+280h+var_250]; this
0x180014638  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18001463e  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180014643  mov     esi, eax
0x180014645  test    eax, eax
0x180014647  jns     loc_1800146E5
0x18001464d  mov     rcx, [rbp+188h]; this
0x180014654  lea     r8, aWil; "wil"
0x18001465b  mov     r9d, eax; char *
0x18001465e  mov     edx, 14Eh; void *
0x180014663  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014668  lea     rcx, [rsp+280h+var_250]; this
0x18001466d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180014672  call    cs:__imp_GetProcessHeap
0x180014679  nop     dword ptr [rax+rax+00h]
0x18001467e  mov     r8, r14; lpMem
0x180014681  xor     edx, edx; dwFlags
0x180014683  mov     rcx, rax; hHeap
0x180014686  call    cs:__imp_HeapFree
0x18001468d  nop     dword ptr [rax+rax+00h]
0x180014692  mov     rcx, [rbp+188h]; this
0x180014699  lea     r8, aWil; "wil"
0x1800146a0  mov     r9d, esi; char *
0x1800146a3  mov     edx, 137h; void *
0x1800146a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146ad  test    rdi, rdi
0x1800146b0  jz      short loc_1800146C9
0x1800146b2  mov     rcx, rdi; hMutex
0x1800146b5  call    cs:__imp_ReleaseMutex
0x1800146bc  nop     dword ptr [rax+rax+00h]
0x1800146c1  test    eax, eax
0x1800146c3  jz      loc_18001483C
0x1800146c9  mov     rcx, rbx; hObject
0x1800146cc  call    cs:__imp_CloseHandle
0x1800146d3  nop     dword ptr [rax+rax+00h]
0x1800146d8  test    eax, eax
0x1800146da  jz      loc_1800147ED
0x1800146e0  jmp     loc_1800145C3
0x1800146e5  mov     rax, [rsp+280h+var_250]
0x1800146ea  lea     rcx, [r14+28h]; void *
0x1800146ee  mov     [r14+10h], rax
0x1800146f2  xor     edx, edx; Val
0x1800146f4  mov     rax, [rsp+280h+var_250+8]
0x1800146f9  mov     r8d, 108h; Size
0x1800146ff  mov     [r14+18h], rax
0x180014703  mov     dword ptr [r14], 1
0x18001470a  mov     [r14+8], rbx
0x18001470e  mov     [rsp+280h+var_250], 0
0x180014717  mov     [rsp+280h+var_250+8], 0
0x180014720  call    memset_0
0x180014725  xor     eax, eax
0x180014727  lea     rcx, [r14+28h]; this
0x18001472b  mov     [r14+20h], rax
0x18001472f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180014734  lea     rbx, [r14+0E8h]
0x18001473b  xor     r8d, r8d; Flags
0x18001473e  mov     rcx, rbx; lpCriticalSection
0x180014741  xor     edx, edx; dwSpinCount
0x180014743  call    cs:__imp_InitializeCriticalSectionEx
0x18001474a  nop     dword ptr [rax+rax+00h]
0x18001474f  mov     qword ptr [rbx+28h], 0
0x180014757  lea     rcx, [rsp+280h+var_250]; this
0x18001475c  mov     qword ptr [rbx+30h], 0
0x180014764  mov     qword ptr [rbx+38h], 0
0x18001476c  mov     qword ptr [rbx+40h], 0
0x180014774  mov     [r15], r14
0x180014777  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001477c  xor     ebx, ebx
0x18001477e  test    rdi, rdi
0x180014781  jz      short loc_18001479A
0x180014783  mov     rcx, rdi; hMutex
0x180014786  call    cs:__imp_ReleaseMutex
0x18001478d  nop     dword ptr [rax+rax+00h]
0x180014792  test    eax, eax
0x180014794  jz      loc_18001484E
0x18001479a  test    rbx, rbx
0x18001479d  jz      short loc_1800147B2
0x18001479f  mov     rcx, rbx; hObject
0x1800147a2  call    cs:__imp_CloseHandle
0x1800147a9  nop     dword ptr [rax+rax+00h]
0x1800147ae  test    eax, eax
0x1800147b0  jz      short loc_1800147DB
0x1800147b2  xor     eax, eax
0x1800147b4  mov     rcx, [rbp+180h+var_30]
0x1800147bb  xor     rcx, rsp; StackCookie
0x1800147be  call    __security_check_cookie
0x1800147c3  mov     rbx, [rsp+280h+arg_10]
0x1800147cb  add     rsp, 260h
0x1800147d2  pop     r15
0x1800147d4  pop     r14
0x1800147d6  pop     rdi
0x1800147d7  pop     rsi
0x1800147d8  pop     rbp
0x1800147d9  retn
0x1800147db  mov     rcx, [rbp+188h]; this
0x1800147e2  mov     edx, 0A0Bh; void *
0x1800147e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147ed  mov     rcx, [rbp+188h]; this
0x1800147f4  mov     edx, 0A0Bh; void *
0x1800147f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147ff  mov     rcx, [rbp+188h]; this
0x180014806  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001480d  mov     edx, 0E01h; void *
0x180014812  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180014818  mov     rcx, [rbp+188h]; this
0x18001481f  mov     edx, 0A15h; void *
0x180014824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001482a  mov     rcx, [rbp+188h]; this
0x180014831  mov     edx, 0A0Bh; void *
0x180014836  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001483c  mov     rcx, [rbp+188h]; this
0x180014843  mov     edx, 0A15h; void *
0x180014848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001484e  mov     rcx, [rbp+188h]; this
0x180014855  mov     edx, 0A15h; void *
0x18001485a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
