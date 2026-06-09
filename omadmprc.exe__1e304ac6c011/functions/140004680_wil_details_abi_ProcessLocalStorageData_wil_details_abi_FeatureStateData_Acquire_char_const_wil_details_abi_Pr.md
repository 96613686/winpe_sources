# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004680`
- end: `0x140004a80`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140004cbc`

## callees

- `0x14000271f`
- `0x1400038d8`
- `0x140003f50`
- `0x140004680`
- `0x140004a88`
- `0x140004f14`
- `0x140005940`
- `0x1400067f8`
- `0x140008504`
- `0x140008ea0`
- `0x14000942c`
- `0x140009e20`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000489e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000489e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400048b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400048b2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400046fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400046fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000496f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000496f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004724`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004724`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400047c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400048e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400049b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400047c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400048e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400049b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400048f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400048f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049ce`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x140004680  mov     [rsp-8+arg_10], rbx
0x140004685  push    rbp
0x140004686  push    rsi
0x140004687  push    rdi
0x140004688  push    r14
0x14000468a  push    r15
0x14000468c  lea     rbp, [rsp-160h]
0x140004694  sub     rsp, 260h
0x14000469b  mov     rax, cs:__security_cookie
0x1400046a2  xor     rax, rsp
0x1400046a5  mov     [rbp+180h+var_30], rax
0x1400046ac  mov     r15, rdx
0x1400046af  mov     qword ptr [rdx], 0
0x1400046b6  mov     rbx, rcx
0x1400046b9  call    cs:__imp_GetCurrentProcessId
0x1400046c0  nop     dword ptr [rax+rax+00h]
0x1400046c5  mov     r14d, 130h
0x1400046cb  mov     [rsp+280h+var_258], rbx
0x1400046d0  mov     r9d, eax
0x1400046d3  mov     [rsp+280h+var_260], r14d; int
0x1400046d8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400046df  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400046e4  lea     edx, [r14-2Ch]; unsigned __int64
0x1400046e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400046ed  mov     r9d, 1F0001h; dwDesiredAccess
0x1400046f3  lea     rdx, [rsp+280h+Name]; lpName
0x1400046f8  xor     r8d, r8d; dwFlags
0x1400046fb  xor     ecx, ecx; lpMutexAttributes
0x1400046fd  call    cs:__imp_CreateMutexExW
0x140004704  nop     dword ptr [rax+rax+00h]
0x140004709  mov     rbx, rax
0x14000470c  test    rax, rax
0x14000470f  jnz     short loc_14000471B
0x140004711  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004716  jmp     loc_1400049E0
0x14000471b  xor     r8d, r8d; bAlertable
0x14000471e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004721  mov     rcx, rbx; hHandle
0x140004724  call    cs:__imp_WaitForSingleObjectEx
0x14000472b  nop     dword ptr [rax+rax+00h]
0x140004730  cmp     eax, 102h
0x140004735  jz      short loc_140004747
0x140004737  test    eax, 0FFFFFF7Fh
0x14000473c  jnz     loc_140004A2B
0x140004742  mov     rdi, rbx
0x140004745  jmp     short loc_140004749
0x140004747  xor     edi, edi
0x140004749  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14000474e  mov     [rsp+280h+var_250], 0
0x140004757  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000475c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004761  mov     esi, eax
0x140004763  test    eax, eax
0x140004765  jns     loc_1400047F6
0x14000476b  mov     rcx, [rbp+188h]; this
0x140004772  lea     r8, aWil; "wil"
0x140004779  mov     r9d, eax; char *
0x14000477c  mov     edx, 66h ; 'f'; void *
0x140004781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004786  mov     rcx, [rbp+188h]; this
0x14000478d  lea     r8, aWil; "wil"
0x140004794  mov     r9d, esi; char *
0x140004797  mov     edx, 6Fh ; 'o'; void *
0x14000479c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400047a1  mov     rcx, [rbp+188h]; this
0x1400047a8  lea     r8, aWil; "wil"
0x1400047af  mov     r9d, esi; char *
0x1400047b2  mov     edx, 12Eh; void *
0x1400047b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400047bc  test    rdi, rdi
0x1400047bf  jz      short loc_1400047D8
0x1400047c1  mov     rcx, rdi; hMutex
0x1400047c4  call    cs:__imp_ReleaseMutex
0x1400047cb  nop     dword ptr [rax+rax+00h]
0x1400047d0  test    eax, eax
0x1400047d2  jz      loc_140004A38
0x1400047d8  mov     rcx, rbx; hObject
0x1400047db  call    cs:__imp_CloseHandle
0x1400047e2  nop     dword ptr [rax+rax+00h]
0x1400047e7  test    eax, eax
0x1400047e9  jz      loc_140004A4A
0x1400047ef  mov     eax, esi
0x1400047f1  jmp     loc_1400049E0
0x1400047f6  mov     rax, [rsp+280h+var_250]
0x1400047fb  lea     rcx, ds:0[rax*4]
0x140004803  test    rcx, rcx
0x140004806  jz      short loc_140004816
0x140004808  mov     [r15], rcx
0x14000480b  mov     eax, [rcx]
0x14000480d  inc     eax
0x14000480f  mov     [rcx], eax
0x140004811  jmp     loc_1400049AA
0x140004816  mov     rdx, r14; dwBytes
0x140004819  mov     qword ptr [r15], 0
0x140004820  mov     ecx, 8; dwFlags
0x140004825  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000482a  mov     r14, rax
0x14000482d  test    rax, rax
0x140004830  jnz     short loc_140004854
0x140004832  mov     rcx, [rbp+188h]; this
0x140004839  lea     r8, aWil; "wil"
0x140004840  mov     esi, 8007000Eh
0x140004845  mov     edx, 14Bh; void *
0x14000484a  mov     r9d, esi; char *
0x14000484d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004852  jmp     short loc_1400048BE
0x140004854  xorps   xmm0, xmm0
0x140004857  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000485c  mov     r8, r14; void *
0x14000485f  lea     rcx, [rsp+280h+var_250]; this
0x140004864  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14000486a  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x14000486f  mov     esi, eax
0x140004871  test    eax, eax
0x140004873  jns     loc_140004911
0x140004879  mov     rcx, [rbp+188h]; this
0x140004880  lea     r8, aWil; "wil"
0x140004887  mov     r9d, eax; char *
0x14000488a  mov     edx, 14Eh; void *
0x14000488f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004894  lea     rcx, [rsp+280h+var_250]; this
0x140004899  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000489e  call    cs:__imp_GetProcessHeap
0x1400048a5  nop     dword ptr [rax+rax+00h]
0x1400048aa  mov     r8, r14; lpMem
0x1400048ad  xor     edx, edx; dwFlags
0x1400048af  mov     rcx, rax; hHeap
0x1400048b2  call    cs:__imp_HeapFree
0x1400048b9  nop     dword ptr [rax+rax+00h]
0x1400048be  mov     rcx, [rbp+188h]; this
0x1400048c5  lea     r8, aWil; "wil"
0x1400048cc  mov     r9d, esi; char *
0x1400048cf  mov     edx, 137h; void *
0x1400048d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400048d9  test    rdi, rdi
0x1400048dc  jz      short loc_1400048F5
0x1400048de  mov     rcx, rdi; hMutex
0x1400048e1  call    cs:__imp_ReleaseMutex
0x1400048e8  nop     dword ptr [rax+rax+00h]
0x1400048ed  test    eax, eax
0x1400048ef  jz      loc_140004A5C
0x1400048f5  mov     rcx, rbx; hObject
0x1400048f8  call    cs:__imp_CloseHandle
0x1400048ff  nop     dword ptr [rax+rax+00h]
0x140004904  test    eax, eax
0x140004906  jz      loc_140004A19
0x14000490c  jmp     loc_1400047EF
0x140004911  mov     rax, [rsp+280h+var_250]
0x140004916  lea     rcx, [r14+28h]; void *
0x14000491a  mov     [r14+10h], rax
0x14000491e  xor     edx, edx; Val
0x140004920  mov     rax, [rsp+280h+var_250+8]
0x140004925  mov     r8d, 108h; Size
0x14000492b  mov     [r14+18h], rax
0x14000492f  mov     dword ptr [r14], 1
0x140004936  mov     [r14+8], rbx
0x14000493a  mov     [rsp+280h+var_250], 0
0x140004943  mov     [rsp+280h+var_250+8], 0
0x14000494c  call    memset_0
0x140004951  xor     eax, eax
0x140004953  lea     rcx, [r14+28h]; this
0x140004957  mov     [r14+20h], rax
0x14000495b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140004960  lea     rbx, [r14+0E8h]
0x140004967  xor     r8d, r8d; Flags
0x14000496a  mov     rcx, rbx; lpCriticalSection
0x14000496d  xor     edx, edx; dwSpinCount
0x14000496f  call    cs:__imp_InitializeCriticalSectionEx
0x140004976  nop     dword ptr [rax+rax+00h]
0x14000497b  mov     qword ptr [rbx+28h], 0
0x140004983  lea     rcx, [rsp+280h+var_250]; this
0x140004988  mov     qword ptr [rbx+30h], 0
0x140004990  mov     qword ptr [rbx+38h], 0
0x140004998  mov     qword ptr [rbx+40h], 0
0x1400049a0  mov     [r15], r14
0x1400049a3  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400049a8  xor     ebx, ebx
0x1400049aa  test    rdi, rdi
0x1400049ad  jz      short loc_1400049C6
0x1400049af  mov     rcx, rdi; hMutex
0x1400049b2  call    cs:__imp_ReleaseMutex
0x1400049b9  nop     dword ptr [rax+rax+00h]
0x1400049be  test    eax, eax
0x1400049c0  jz      loc_140004A6E
0x1400049c6  test    rbx, rbx
0x1400049c9  jz      short loc_1400049DE
0x1400049cb  mov     rcx, rbx; hObject
0x1400049ce  call    cs:__imp_CloseHandle
0x1400049d5  nop     dword ptr [rax+rax+00h]
0x1400049da  test    eax, eax
0x1400049dc  jz      short loc_140004A07
0x1400049de  xor     eax, eax
0x1400049e0  mov     rcx, [rbp+180h+var_30]
0x1400049e7  xor     rcx, rsp; StackCookie
0x1400049ea  call    __security_check_cookie
0x1400049ef  mov     rbx, [rsp+280h+arg_10]
0x1400049f7  add     rsp, 260h
0x1400049fe  pop     r15
0x140004a00  pop     r14
0x140004a02  pop     rdi
0x140004a03  pop     rsi
0x140004a04  pop     rbp
0x140004a05  retn
0x140004a07  mov     rcx, [rbp+188h]; this
0x140004a0e  mov     edx, 0A0Bh; void *
0x140004a13  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a19  mov     rcx, [rbp+188h]; this
0x140004a20  mov     edx, 0A0Bh; void *
0x140004a25  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a2b  mov     rcx, [rbp+188h]; this
0x140004a32  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004a38  mov     rcx, [rbp+188h]; this
0x140004a3f  mov     edx, 0A15h; void *
0x140004a44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a4a  mov     rcx, [rbp+188h]; this
0x140004a51  mov     edx, 0A0Bh; void *
0x140004a56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a5c  mov     rcx, [rbp+188h]; this
0x140004a63  mov     edx, 0A15h; void *
0x140004a68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a6e  mov     rcx, [rbp+188h]; this
0x140004a75  mov     edx, 0A15h; void *
0x140004a7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
