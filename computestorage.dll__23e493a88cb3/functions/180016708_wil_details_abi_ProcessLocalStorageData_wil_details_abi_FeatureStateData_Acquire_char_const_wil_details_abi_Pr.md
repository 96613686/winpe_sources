# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180016708`
- end: `0x180016ae6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `990`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180016c88`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180009640`
- `0x18000a80c`
- `0x18000ad80`
- `0x18000b398`
- `0x18000db5c`
- `0x18000e414`
- `0x180012640`
- `0x180012870`
- `0x1800134a0`
- `0x1800160f8`
- `0x180016708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016833`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001693b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016833`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001693b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016a0c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800169c9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800169c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016785`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016785`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800167ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800167ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001684a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001684a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a28`

## string_xrefs

- `0x180016a8c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  _DWORD *v21; // rcx
  _DWORD *v22; // rax
  unsigned int v23; // r8d
  _DWORD *v24; // r14
  unsigned int v25; // r8d
  int v26; // eax
  unsigned int v27; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v40[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v40[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v40, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v37);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v38);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * v40[0]);
  if ( 4 * v40[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_23;
  }
  *a2 = 0;
  v22 = wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v24 = v22;
  if ( !v22 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v23, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v40 = 0;
  v26 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v40, Name, v22);
  v14 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v27, (const char *)(unsigned int)v26, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v40);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v25, (const char *)v14, v39);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return v14;
  }
  *((_QWORD *)v24 + 2) = v40[0];
  *((_QWORD *)v24 + 3) = v40[1];
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v40[0] = 0;
  v40[1] = 0;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  *a2 = v24;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v40);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v33, v34);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
  return 0;
}

```

## disassembly

```asm
0x180016708  mov     [rsp-8+arg_10], rbx
0x18001670d  push    rbp
0x18001670e  push    rsi
0x18001670f  push    rdi
0x180016710  push    r14
0x180016712  push    r15
0x180016714  lea     rbp, [rsp-160h]
0x18001671c  sub     rsp, 260h
0x180016723  mov     rax, cs:__security_cookie
0x18001672a  xor     rax, rsp
0x18001672d  mov     [rbp+180h+var_30], rax
0x180016734  mov     r15, rdx
0x180016737  mov     qword ptr [rdx], 0
0x18001673e  mov     rbx, rcx
0x180016741  call    cs:__imp_GetCurrentProcessId
0x180016748  nop     dword ptr [rax+rax+00h]
0x18001674d  mov     r14d, 130h
0x180016753  mov     [rsp+280h+var_258], rbx
0x180016758  mov     r9d, eax
0x18001675b  mov     [rsp+280h+var_260], r14d; int
0x180016760  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180016767  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001676c  lea     edx, [r14-2Ch]; unsigned __int64
0x180016770  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016775  mov     r9d, 1F0001h; dwDesiredAccess
0x18001677b  lea     rdx, [rsp+280h+Name]; lpName
0x180016780  xor     r8d, r8d; dwFlags
0x180016783  xor     ecx, ecx; lpMutexAttributes
0x180016785  call    cs:__imp_CreateMutexExW
0x18001678c  nop     dword ptr [rax+rax+00h]
0x180016791  mov     rbx, rax
0x180016794  test    rax, rax
0x180016797  jnz     short loc_1800167A3
0x180016799  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001679e  jmp     loc_180016A3A
0x1800167a3  xor     r8d, r8d; bAlertable
0x1800167a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800167a9  mov     rcx, rbx; hHandle
0x1800167ac  call    cs:__imp_WaitForSingleObjectEx
0x1800167b3  nop     dword ptr [rax+rax+00h]
0x1800167b8  cmp     eax, 102h
0x1800167bd  jz      short loc_1800167CF
0x1800167bf  test    eax, 0FFFFFF7Fh
0x1800167c4  jnz     loc_180016A85
0x1800167ca  mov     rdi, rbx
0x1800167cd  jmp     short loc_1800167D1
0x1800167cf  xor     edi, edi
0x1800167d1  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800167d6  mov     [rsp+280h+var_250], 0
0x1800167df  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800167e4  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800167e9  mov     esi, eax
0x1800167eb  test    eax, eax
0x1800167ed  jns     short loc_180016865
0x1800167ef  mov     rcx, [rbp+188h]; this
0x1800167f6  mov     r9d, eax; char *
0x1800167f9  mov     edx, 66h ; 'f'; void *
0x1800167fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016803  mov     rcx, [rbp+188h]; this
0x18001680a  mov     r9d, esi; char *
0x18001680d  mov     edx, 6Fh ; 'o'; void *
0x180016812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016817  mov     rcx, [rbp+188h]; this
0x18001681e  mov     r9d, esi; char *
0x180016821  mov     edx, 12Eh; void *
0x180016826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001682b  test    rdi, rdi
0x18001682e  jz      short loc_180016847
0x180016830  mov     rcx, rdi; hMutex
0x180016833  call    cs:__imp_ReleaseMutex
0x18001683a  nop     dword ptr [rax+rax+00h]
0x18001683f  test    eax, eax
0x180016841  jz      loc_180016A9E
0x180016847  mov     rcx, rbx; hObject
0x18001684a  call    cs:__imp_CloseHandle
0x180016851  nop     dword ptr [rax+rax+00h]
0x180016856  test    eax, eax
0x180016858  jz      loc_180016AB0
0x18001685e  mov     eax, esi
0x180016860  jmp     loc_180016A3A
0x180016865  mov     rax, [rsp+280h+var_250]
0x18001686a  lea     rcx, ds:0[rax*4]
0x180016872  test    rcx, rcx
0x180016875  jz      short loc_180016885
0x180016877  mov     [r15], rcx
0x18001687a  mov     eax, [rcx]
0x18001687c  inc     eax
0x18001687e  mov     [rcx], eax
0x180016880  jmp     loc_180016A04
0x180016885  mov     rdx, r14; dwBytes
0x180016888  mov     qword ptr [r15], 0
0x18001688f  mov     ecx, 8; dwFlags
0x180016894  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016899  mov     r14, rax
0x18001689c  test    rax, rax
0x18001689f  jnz     short loc_1800168BC
0x1800168a1  mov     rcx, [rbp+188h]; this
0x1800168a8  mov     esi, 8007000Eh
0x1800168ad  mov     r9d, esi; char *
0x1800168b0  mov     edx, 14Bh; void *
0x1800168b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168ba  jmp     short loc_18001691F
0x1800168bc  xorps   xmm0, xmm0
0x1800168bf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800168c4  mov     r8, r14; void *
0x1800168c7  lea     rcx, [rsp+280h+var_250]; this
0x1800168cc  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800168d2  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800168d7  mov     esi, eax
0x1800168d9  test    eax, eax
0x1800168db  jns     loc_18001696B
0x1800168e1  mov     rcx, [rbp+188h]; this
0x1800168e8  mov     r9d, eax; char *
0x1800168eb  mov     edx, 14Eh; void *
0x1800168f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168f5  lea     rcx, [rsp+280h+var_250]; this
0x1800168fa  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800168ff  call    cs:__imp_GetProcessHeap
0x180016906  nop     dword ptr [rax+rax+00h]
0x18001690b  mov     r8, r14; lpMem
0x18001690e  xor     edx, edx; dwFlags
0x180016910  mov     rcx, rax; hHeap
0x180016913  call    cs:__imp_HeapFree
0x18001691a  nop     dword ptr [rax+rax+00h]
0x18001691f  mov     rcx, [rbp+188h]; this
0x180016926  mov     r9d, esi; char *
0x180016929  mov     edx, 137h; void *
0x18001692e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016933  test    rdi, rdi
0x180016936  jz      short loc_18001694F
0x180016938  mov     rcx, rdi; hMutex
0x18001693b  call    cs:__imp_ReleaseMutex
0x180016942  nop     dword ptr [rax+rax+00h]
0x180016947  test    eax, eax
0x180016949  jz      loc_180016AC2
0x18001694f  mov     rcx, rbx; hObject
0x180016952  call    cs:__imp_CloseHandle
0x180016959  nop     dword ptr [rax+rax+00h]
0x18001695e  test    eax, eax
0x180016960  jz      loc_180016A73
0x180016966  jmp     loc_18001685E
0x18001696b  mov     rax, [rsp+280h+var_250]
0x180016970  lea     rcx, [r14+28h]; void *
0x180016974  mov     [r14+10h], rax
0x180016978  xor     edx, edx; Val
0x18001697a  mov     rax, [rsp+280h+var_250+8]
0x18001697f  mov     r8d, 108h; Size
0x180016985  mov     [r14+18h], rax
0x180016989  mov     dword ptr [r14], 1
0x180016990  mov     [r14+8], rbx
0x180016994  mov     [rsp+280h+var_250], 0
0x18001699d  mov     [rsp+280h+var_250+8], 0
0x1800169a6  call    memset_0
0x1800169ab  xor     eax, eax
0x1800169ad  lea     rcx, [r14+28h]; this
0x1800169b1  mov     [r14+20h], rax
0x1800169b5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800169ba  lea     rbx, [r14+0E8h]
0x1800169c1  xor     r8d, r8d; Flags
0x1800169c4  mov     rcx, rbx; lpCriticalSection
0x1800169c7  xor     edx, edx; dwSpinCount
0x1800169c9  call    cs:__imp_InitializeCriticalSectionEx
0x1800169d0  nop     dword ptr [rax+rax+00h]
0x1800169d5  mov     qword ptr [rbx+28h], 0
0x1800169dd  lea     rcx, [rsp+280h+var_250]; this
0x1800169e2  mov     qword ptr [rbx+30h], 0
0x1800169ea  mov     qword ptr [rbx+38h], 0
0x1800169f2  mov     qword ptr [rbx+40h], 0
0x1800169fa  mov     [r15], r14
0x1800169fd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180016a02  xor     ebx, ebx
0x180016a04  test    rdi, rdi
0x180016a07  jz      short loc_180016A20
0x180016a09  mov     rcx, rdi; hMutex
0x180016a0c  call    cs:__imp_ReleaseMutex
0x180016a13  nop     dword ptr [rax+rax+00h]
0x180016a18  test    eax, eax
0x180016a1a  jz      loc_180016AD4
0x180016a20  test    rbx, rbx
0x180016a23  jz      short loc_180016A38
0x180016a25  mov     rcx, rbx; hObject
0x180016a28  call    cs:__imp_CloseHandle
0x180016a2f  nop     dword ptr [rax+rax+00h]
0x180016a34  test    eax, eax
0x180016a36  jz      short loc_180016A61
0x180016a38  xor     eax, eax
0x180016a3a  mov     rcx, [rbp+180h+var_30]
0x180016a41  xor     rcx, rsp; StackCookie
0x180016a44  call    __security_check_cookie
0x180016a49  mov     rbx, [rsp+280h+arg_10]
0x180016a51  add     rsp, 260h
0x180016a58  pop     r15
0x180016a5a  pop     r14
0x180016a5c  pop     rdi
0x180016a5d  pop     rsi
0x180016a5e  pop     rbp
0x180016a5f  retn
0x180016a61  mov     rcx, [rbp+188h]; this
0x180016a68  mov     edx, 0A0Bh; void *
0x180016a6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016a73  mov     rcx, [rbp+188h]; this
0x180016a7a  mov     edx, 0A0Bh; void *
0x180016a7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016a85  mov     rcx, [rbp+188h]; this
0x180016a8c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016a93  mov     edx, 0E01h; void *
0x180016a98  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016a9e  mov     rcx, [rbp+188h]; this
0x180016aa5  mov     edx, 0A15h; void *
0x180016aaa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016ab0  mov     rcx, [rbp+188h]; this
0x180016ab7  mov     edx, 0A0Bh; void *
0x180016abc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016ac2  mov     rcx, [rbp+188h]; this
0x180016ac9  mov     edx, 0A15h; void *
0x180016ace  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016ad4  mov     rcx, [rbp+188h]; this
0x180016adb  mov     edx, 0A15h; void *
0x180016ae0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
