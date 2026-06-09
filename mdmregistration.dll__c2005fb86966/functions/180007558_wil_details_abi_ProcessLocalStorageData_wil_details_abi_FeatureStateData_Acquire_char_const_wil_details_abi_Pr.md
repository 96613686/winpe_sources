# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007558`
- end: `0x180007958`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007c04`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180006410`
- `0x180006bdc`
- `0x180007558`
- `0x1800079a0`
- `0x180007e5c`
- `0x180008700`
- `0x180009668`
- `0x18000b0f4`
- `0x18000bd7c`
- `0x18000c2cc`
- `0x18000cc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000769c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000788a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000769c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000788a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007847`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007847`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800075d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800075d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000778a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000778a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007776`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007776`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078a6`

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
0x180007558  mov     [rsp-8+arg_10], rbx
0x18000755d  push    rbp
0x18000755e  push    rsi
0x18000755f  push    rdi
0x180007560  push    r14
0x180007562  push    r15
0x180007564  lea     rbp, [rsp-160h]
0x18000756c  sub     rsp, 260h
0x180007573  mov     rax, cs:__security_cookie
0x18000757a  xor     rax, rsp
0x18000757d  mov     [rbp+180h+var_30], rax
0x180007584  mov     r15, rdx
0x180007587  mov     qword ptr [rdx], 0
0x18000758e  mov     rbx, rcx
0x180007591  call    cs:__imp_GetCurrentProcessId
0x180007598  nop     dword ptr [rax+rax+00h]
0x18000759d  mov     r14d, 130h
0x1800075a3  mov     [rsp+280h+var_258], rbx
0x1800075a8  mov     r9d, eax
0x1800075ab  mov     [rsp+280h+var_260], r14d; int
0x1800075b0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800075b7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800075bc  lea     edx, [r14-2Ch]; unsigned __int64
0x1800075c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800075c5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800075cb  lea     rdx, [rsp+280h+Name]; lpName
0x1800075d0  xor     r8d, r8d; dwFlags
0x1800075d3  xor     ecx, ecx; lpMutexAttributes
0x1800075d5  call    cs:__imp_CreateMutexExW
0x1800075dc  nop     dword ptr [rax+rax+00h]
0x1800075e1  mov     rbx, rax
0x1800075e4  test    rax, rax
0x1800075e7  jnz     short loc_1800075F3
0x1800075e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800075ee  jmp     loc_1800078B8
0x1800075f3  xor     r8d, r8d; bAlertable
0x1800075f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800075f9  mov     rcx, rbx; hHandle
0x1800075fc  call    cs:__imp_WaitForSingleObjectEx
0x180007603  nop     dword ptr [rax+rax+00h]
0x180007608  cmp     eax, 102h
0x18000760d  jz      short loc_18000761F
0x18000760f  test    eax, 0FFFFFF7Fh
0x180007614  jnz     loc_180007903
0x18000761a  mov     rdi, rbx
0x18000761d  jmp     short loc_180007621
0x18000761f  xor     edi, edi
0x180007621  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180007626  mov     [rsp+280h+var_250], 0
0x18000762f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007634  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007639  mov     esi, eax
0x18000763b  test    eax, eax
0x18000763d  jns     loc_1800076CE
0x180007643  mov     rcx, [rbp+188h]; this
0x18000764a  lea     r8, aWil; "wil"
0x180007651  mov     r9d, eax; char *
0x180007654  mov     edx, 66h ; 'f'; void *
0x180007659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000765e  mov     rcx, [rbp+188h]; this
0x180007665  lea     r8, aWil; "wil"
0x18000766c  mov     r9d, esi; char *
0x18000766f  mov     edx, 6Fh ; 'o'; void *
0x180007674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007679  mov     rcx, [rbp+188h]; this
0x180007680  lea     r8, aWil; "wil"
0x180007687  mov     r9d, esi; char *
0x18000768a  mov     edx, 12Eh; void *
0x18000768f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007694  test    rdi, rdi
0x180007697  jz      short loc_1800076B0
0x180007699  mov     rcx, rdi; hMutex
0x18000769c  call    cs:__imp_ReleaseMutex
0x1800076a3  nop     dword ptr [rax+rax+00h]
0x1800076a8  test    eax, eax
0x1800076aa  jz      loc_180007910
0x1800076b0  mov     rcx, rbx; hObject
0x1800076b3  call    cs:__imp_CloseHandle
0x1800076ba  nop     dword ptr [rax+rax+00h]
0x1800076bf  test    eax, eax
0x1800076c1  jz      loc_180007922
0x1800076c7  mov     eax, esi
0x1800076c9  jmp     loc_1800078B8
0x1800076ce  mov     rax, [rsp+280h+var_250]
0x1800076d3  lea     rcx, ds:0[rax*4]
0x1800076db  test    rcx, rcx
0x1800076de  jz      short loc_1800076EE
0x1800076e0  mov     [r15], rcx
0x1800076e3  mov     eax, [rcx]
0x1800076e5  inc     eax
0x1800076e7  mov     [rcx], eax
0x1800076e9  jmp     loc_180007882
0x1800076ee  mov     rdx, r14; dwBytes
0x1800076f1  mov     qword ptr [r15], 0
0x1800076f8  mov     ecx, 8; dwFlags
0x1800076fd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007702  mov     r14, rax
0x180007705  test    rax, rax
0x180007708  jnz     short loc_18000772C
0x18000770a  mov     rcx, [rbp+188h]; this
0x180007711  lea     r8, aWil; "wil"
0x180007718  mov     esi, 8007000Eh
0x18000771d  mov     edx, 14Bh; void *
0x180007722  mov     r9d, esi; char *
0x180007725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000772a  jmp     short loc_180007796
0x18000772c  xorps   xmm0, xmm0
0x18000772f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007734  mov     r8, r14; void *
0x180007737  lea     rcx, [rsp+280h+var_250]; this
0x18000773c  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007742  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180007747  mov     esi, eax
0x180007749  test    eax, eax
0x18000774b  jns     loc_1800077E9
0x180007751  mov     rcx, [rbp+188h]; this
0x180007758  lea     r8, aWil; "wil"
0x18000775f  mov     r9d, eax; char *
0x180007762  mov     edx, 14Eh; void *
0x180007767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000776c  lea     rcx, [rsp+280h+var_250]; this
0x180007771  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007776  call    cs:__imp_GetProcessHeap
0x18000777d  nop     dword ptr [rax+rax+00h]
0x180007782  mov     r8, r14; lpMem
0x180007785  xor     edx, edx; dwFlags
0x180007787  mov     rcx, rax; hHeap
0x18000778a  call    cs:__imp_HeapFree
0x180007791  nop     dword ptr [rax+rax+00h]
0x180007796  mov     rcx, [rbp+188h]; this
0x18000779d  lea     r8, aWil; "wil"
0x1800077a4  mov     r9d, esi; char *
0x1800077a7  mov     edx, 137h; void *
0x1800077ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077b1  test    rdi, rdi
0x1800077b4  jz      short loc_1800077CD
0x1800077b6  mov     rcx, rdi; hMutex
0x1800077b9  call    cs:__imp_ReleaseMutex
0x1800077c0  nop     dword ptr [rax+rax+00h]
0x1800077c5  test    eax, eax
0x1800077c7  jz      loc_180007934
0x1800077cd  mov     rcx, rbx; hObject
0x1800077d0  call    cs:__imp_CloseHandle
0x1800077d7  nop     dword ptr [rax+rax+00h]
0x1800077dc  test    eax, eax
0x1800077de  jz      loc_1800078F1
0x1800077e4  jmp     loc_1800076C7
0x1800077e9  mov     rax, [rsp+280h+var_250]
0x1800077ee  lea     rcx, [r14+28h]; void *
0x1800077f2  mov     [r14+10h], rax
0x1800077f6  xor     edx, edx; Val
0x1800077f8  mov     rax, [rsp+280h+var_250+8]
0x1800077fd  mov     r8d, 108h; Size
0x180007803  mov     [r14+18h], rax
0x180007807  mov     dword ptr [r14], 1
0x18000780e  mov     [r14+8], rbx
0x180007812  mov     [rsp+280h+var_250], 0
0x18000781b  mov     [rsp+280h+var_250+8], 0
0x180007824  call    memset_0
0x180007829  xor     eax, eax
0x18000782b  lea     rcx, [r14+28h]; this
0x18000782f  mov     [r14+20h], rax
0x180007833  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007838  lea     rbx, [r14+0E8h]
0x18000783f  xor     r8d, r8d; Flags
0x180007842  mov     rcx, rbx; lpCriticalSection
0x180007845  xor     edx, edx; dwSpinCount
0x180007847  call    cs:__imp_InitializeCriticalSectionEx
0x18000784e  nop     dword ptr [rax+rax+00h]
0x180007853  mov     qword ptr [rbx+28h], 0
0x18000785b  lea     rcx, [rsp+280h+var_250]; this
0x180007860  mov     qword ptr [rbx+30h], 0
0x180007868  mov     qword ptr [rbx+38h], 0
0x180007870  mov     qword ptr [rbx+40h], 0
0x180007878  mov     [r15], r14
0x18000787b  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007880  xor     ebx, ebx
0x180007882  test    rdi, rdi
0x180007885  jz      short loc_18000789E
0x180007887  mov     rcx, rdi; hMutex
0x18000788a  call    cs:__imp_ReleaseMutex
0x180007891  nop     dword ptr [rax+rax+00h]
0x180007896  test    eax, eax
0x180007898  jz      loc_180007946
0x18000789e  test    rbx, rbx
0x1800078a1  jz      short loc_1800078B6
0x1800078a3  mov     rcx, rbx; hObject
0x1800078a6  call    cs:__imp_CloseHandle
0x1800078ad  nop     dword ptr [rax+rax+00h]
0x1800078b2  test    eax, eax
0x1800078b4  jz      short loc_1800078DF
0x1800078b6  xor     eax, eax
0x1800078b8  mov     rcx, [rbp+180h+var_30]
0x1800078bf  xor     rcx, rsp; StackCookie
0x1800078c2  call    __security_check_cookie
0x1800078c7  mov     rbx, [rsp+280h+arg_10]
0x1800078cf  add     rsp, 260h
0x1800078d6  pop     r15
0x1800078d8  pop     r14
0x1800078da  pop     rdi
0x1800078db  pop     rsi
0x1800078dc  pop     rbp
0x1800078dd  retn
0x1800078df  mov     rcx, [rbp+188h]; this
0x1800078e6  mov     edx, 0A0Bh; void *
0x1800078eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078f1  mov     rcx, [rbp+188h]; this
0x1800078f8  mov     edx, 0A0Bh; void *
0x1800078fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007903  mov     rcx, [rbp+188h]; this
0x18000790a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007910  mov     rcx, [rbp+188h]; this
0x180007917  mov     edx, 0A15h; void *
0x18000791c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007922  mov     rcx, [rbp+188h]; this
0x180007929  mov     edx, 0A0Bh; void *
0x18000792e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007934  mov     rcx, [rbp+188h]; this
0x18000793b  mov     edx, 0A15h; void *
0x180007940  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007946  mov     rcx, [rbp+188h]; this
0x18000794d  mov     edx, 0A15h; void *
0x180007952  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
