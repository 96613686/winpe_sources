# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000931c`
- end: `0x180009728`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1036`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009ea8`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x180007d0c`
- `0x1800089c0`
- `0x18000931c`
- `0x180009730`
- `0x18000a10c`
- `0x18000a9f0`
- `0x18000c0a4`
- `0x18000da88`
- `0x180015370`
- `0x1800158b4`
- `0x180016658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009460`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000957d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000964e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009460`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000957d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000964e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000960b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000960b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009399`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000953a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000953a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000954e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000954e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000966a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000966a`

## string_xrefs

- `0x1800096ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x18000931c  mov     [rsp-8+arg_10], rbx
0x180009321  push    rbp
0x180009322  push    rsi
0x180009323  push    rdi
0x180009324  push    r14
0x180009326  push    r15
0x180009328  lea     rbp, [rsp-160h]
0x180009330  sub     rsp, 260h
0x180009337  mov     rax, cs:__security_cookie
0x18000933e  xor     rax, rsp
0x180009341  mov     [rbp+180h+var_30], rax
0x180009348  mov     r15, rdx
0x18000934b  mov     qword ptr [rdx], 0
0x180009352  mov     rbx, rcx
0x180009355  call    cs:__imp_GetCurrentProcessId
0x18000935c  nop     dword ptr [rax+rax+00h]
0x180009361  mov     r14d, 130h
0x180009367  mov     [rsp+280h+var_258], rbx
0x18000936c  mov     r9d, eax
0x18000936f  mov     [rsp+280h+var_260], r14d; int
0x180009374  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000937b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009380  lea     edx, [r14-2Ch]; unsigned __int64
0x180009384  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009389  mov     r9d, 1F0001h; dwDesiredAccess
0x18000938f  lea     rdx, [rsp+280h+Name]; lpName
0x180009394  xor     r8d, r8d; dwFlags
0x180009397  xor     ecx, ecx; lpMutexAttributes
0x180009399  call    cs:__imp_CreateMutexExW
0x1800093a0  nop     dword ptr [rax+rax+00h]
0x1800093a5  mov     rbx, rax
0x1800093a8  test    rax, rax
0x1800093ab  jnz     short loc_1800093B7
0x1800093ad  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800093b2  jmp     loc_18000967C
0x1800093b7  xor     r8d, r8d; bAlertable
0x1800093ba  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800093bd  mov     rcx, rbx; hHandle
0x1800093c0  call    cs:__imp_WaitForSingleObjectEx
0x1800093c7  nop     dword ptr [rax+rax+00h]
0x1800093cc  cmp     eax, 102h
0x1800093d1  jz      short loc_1800093E3
0x1800093d3  test    eax, 0FFFFFF7Fh
0x1800093d8  jnz     loc_1800096C7
0x1800093de  mov     rdi, rbx
0x1800093e1  jmp     short loc_1800093E5
0x1800093e3  xor     edi, edi
0x1800093e5  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800093ea  mov     [rsp+280h+var_250], 0
0x1800093f3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800093f8  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800093fd  mov     esi, eax
0x1800093ff  test    eax, eax
0x180009401  jns     loc_180009492
0x180009407  mov     rcx, [rbp+188h]; this
0x18000940e  lea     r8, aWil; "wil"
0x180009415  mov     r9d, eax; char *
0x180009418  mov     edx, 66h ; 'f'; void *
0x18000941d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009422  mov     rcx, [rbp+188h]; this
0x180009429  lea     r8, aWil; "wil"
0x180009430  mov     r9d, esi; char *
0x180009433  mov     edx, 6Fh ; 'o'; void *
0x180009438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000943d  mov     rcx, [rbp+188h]; this
0x180009444  lea     r8, aWil; "wil"
0x18000944b  mov     r9d, esi; char *
0x18000944e  mov     edx, 12Eh; void *
0x180009453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009458  test    rdi, rdi
0x18000945b  jz      short loc_180009474
0x18000945d  mov     rcx, rdi; hMutex
0x180009460  call    cs:__imp_ReleaseMutex
0x180009467  nop     dword ptr [rax+rax+00h]
0x18000946c  test    eax, eax
0x18000946e  jz      loc_1800096E0
0x180009474  mov     rcx, rbx; hObject
0x180009477  call    cs:__imp_CloseHandle
0x18000947e  nop     dword ptr [rax+rax+00h]
0x180009483  test    eax, eax
0x180009485  jz      loc_1800096F2
0x18000948b  mov     eax, esi
0x18000948d  jmp     loc_18000967C
0x180009492  mov     rax, [rsp+280h+var_250]
0x180009497  lea     rcx, ds:0[rax*4]
0x18000949f  test    rcx, rcx
0x1800094a2  jz      short loc_1800094B2
0x1800094a4  mov     [r15], rcx
0x1800094a7  mov     eax, [rcx]
0x1800094a9  inc     eax
0x1800094ab  mov     [rcx], eax
0x1800094ad  jmp     loc_180009646
0x1800094b2  mov     rdx, r14; dwBytes
0x1800094b5  mov     qword ptr [r15], 0
0x1800094bc  mov     ecx, 8; dwFlags
0x1800094c1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800094c6  mov     r14, rax
0x1800094c9  test    rax, rax
0x1800094cc  jnz     short loc_1800094F0
0x1800094ce  mov     rcx, [rbp+188h]; this
0x1800094d5  lea     r8, aWil; "wil"
0x1800094dc  mov     esi, 8007000Eh
0x1800094e1  mov     edx, 14Bh; void *
0x1800094e6  mov     r9d, esi; char *
0x1800094e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094ee  jmp     short loc_18000955A
0x1800094f0  xorps   xmm0, xmm0
0x1800094f3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800094f8  mov     r8, r14; void *
0x1800094fb  lea     rcx, [rsp+280h+var_250]; this
0x180009500  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180009506  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000950b  mov     esi, eax
0x18000950d  test    eax, eax
0x18000950f  jns     loc_1800095AD
0x180009515  mov     rcx, [rbp+188h]; this
0x18000951c  lea     r8, aWil; "wil"
0x180009523  mov     r9d, eax; char *
0x180009526  mov     edx, 14Eh; void *
0x18000952b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009530  lea     rcx, [rsp+280h+var_250]; this
0x180009535  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000953a  call    cs:__imp_GetProcessHeap
0x180009541  nop     dword ptr [rax+rax+00h]
0x180009546  mov     r8, r14; lpMem
0x180009549  xor     edx, edx; dwFlags
0x18000954b  mov     rcx, rax; hHeap
0x18000954e  call    cs:__imp_HeapFree
0x180009555  nop     dword ptr [rax+rax+00h]
0x18000955a  mov     rcx, [rbp+188h]; this
0x180009561  lea     r8, aWil; "wil"
0x180009568  mov     r9d, esi; char *
0x18000956b  mov     edx, 137h; void *
0x180009570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009575  test    rdi, rdi
0x180009578  jz      short loc_180009591
0x18000957a  mov     rcx, rdi; hMutex
0x18000957d  call    cs:__imp_ReleaseMutex
0x180009584  nop     dword ptr [rax+rax+00h]
0x180009589  test    eax, eax
0x18000958b  jz      loc_180009704
0x180009591  mov     rcx, rbx; hObject
0x180009594  call    cs:__imp_CloseHandle
0x18000959b  nop     dword ptr [rax+rax+00h]
0x1800095a0  test    eax, eax
0x1800095a2  jz      loc_1800096B5
0x1800095a8  jmp     loc_18000948B
0x1800095ad  mov     rax, [rsp+280h+var_250]
0x1800095b2  lea     rcx, [r14+28h]; void *
0x1800095b6  mov     [r14+10h], rax
0x1800095ba  xor     edx, edx; Val
0x1800095bc  mov     rax, [rsp+280h+var_250+8]
0x1800095c1  mov     r8d, 108h; Size
0x1800095c7  mov     [r14+18h], rax
0x1800095cb  mov     dword ptr [r14], 1
0x1800095d2  mov     [r14+8], rbx
0x1800095d6  mov     [rsp+280h+var_250], 0
0x1800095df  mov     [rsp+280h+var_250+8], 0
0x1800095e8  call    memset_0
0x1800095ed  xor     eax, eax
0x1800095ef  lea     rcx, [r14+28h]; this
0x1800095f3  mov     [r14+20h], rax
0x1800095f7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800095fc  lea     rbx, [r14+0E8h]
0x180009603  xor     r8d, r8d; Flags
0x180009606  mov     rcx, rbx; lpCriticalSection
0x180009609  xor     edx, edx; dwSpinCount
0x18000960b  call    cs:__imp_InitializeCriticalSectionEx
0x180009612  nop     dword ptr [rax+rax+00h]
0x180009617  mov     qword ptr [rbx+28h], 0
0x18000961f  lea     rcx, [rsp+280h+var_250]; this
0x180009624  mov     qword ptr [rbx+30h], 0
0x18000962c  mov     qword ptr [rbx+38h], 0
0x180009634  mov     qword ptr [rbx+40h], 0
0x18000963c  mov     [r15], r14
0x18000963f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009644  xor     ebx, ebx
0x180009646  test    rdi, rdi
0x180009649  jz      short loc_180009662
0x18000964b  mov     rcx, rdi; hMutex
0x18000964e  call    cs:__imp_ReleaseMutex
0x180009655  nop     dword ptr [rax+rax+00h]
0x18000965a  test    eax, eax
0x18000965c  jz      loc_180009716
0x180009662  test    rbx, rbx
0x180009665  jz      short loc_18000967A
0x180009667  mov     rcx, rbx; hObject
0x18000966a  call    cs:__imp_CloseHandle
0x180009671  nop     dword ptr [rax+rax+00h]
0x180009676  test    eax, eax
0x180009678  jz      short loc_1800096A3
0x18000967a  xor     eax, eax
0x18000967c  mov     rcx, [rbp+180h+var_30]
0x180009683  xor     rcx, rsp; StackCookie
0x180009686  call    __security_check_cookie
0x18000968b  mov     rbx, [rsp+280h+arg_10]
0x180009693  add     rsp, 260h
0x18000969a  pop     r15
0x18000969c  pop     r14
0x18000969e  pop     rdi
0x18000969f  pop     rsi
0x1800096a0  pop     rbp
0x1800096a1  retn
0x1800096a3  mov     rcx, [rbp+188h]; this
0x1800096aa  mov     edx, 0A0Bh; void *
0x1800096af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096b5  mov     rcx, [rbp+188h]; this
0x1800096bc  mov     edx, 0A0Bh; void *
0x1800096c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096c7  mov     rcx, [rbp+188h]; this
0x1800096ce  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800096d5  mov     edx, 0E01h; void *
0x1800096da  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800096e0  mov     rcx, [rbp+188h]; this
0x1800096e7  mov     edx, 0A15h; void *
0x1800096ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800096f2  mov     rcx, [rbp+188h]; this
0x1800096f9  mov     edx, 0A0Bh; void *
0x1800096fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009704  mov     rcx, [rbp+188h]; this
0x18000970b  mov     edx, 0A15h; void *
0x180009710  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009716  mov     rcx, [rbp+188h]; this
0x18000971d  mov     edx, 0A15h; void *
0x180009722  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
