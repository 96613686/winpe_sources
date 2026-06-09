# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004120`
- end: `0x1400044f2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000474c`

## callees

- `0x140002463`
- `0x1400033cc`
- `0x140003a18`
- `0x140004120`
- `0x140004520`
- `0x1400049a4`
- `0x140005240`
- `0x140006068`
- `0x1400076e4`
- `0x1400080fc`
- `0x14000865c`
- `0x140009040`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000432b`
- `KERNEL32!HeapFree` at `0x14000432b`
- `KERNEL32!GetProcessHeap` at `0x140004317`
- `KERNEL32!GetProcessHeap` at `0x140004317`
- `KERNEL32!GetCurrentProcessId` at `0x140004159`
- `KERNEL32!GetCurrentProcessId` at `0x140004159`
- `KERNEL32!CreateMutexExW` at `0x14000419d`
- `KERNEL32!CreateMutexExW` at `0x14000419d`
- `KERNEL32!CloseHandle` at `0x140004262`
- `KERNEL32!CloseHandle` at `0x14000436a`
- `KERNEL32!CloseHandle` at `0x140004440`
- `KERNEL32!CloseHandle` at `0x140004262`
- `KERNEL32!CloseHandle` at `0x14000436a`
- `KERNEL32!CloseHandle` at `0x140004440`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400041c4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400041c4`
- `KERNEL32!ReleaseMutex` at `0x14000424b`
- `KERNEL32!ReleaseMutex` at `0x140004353`
- `KERNEL32!ReleaseMutex` at `0x140004424`
- `KERNEL32!ReleaseMutex` at `0x14000424b`
- `KERNEL32!ReleaseMutex` at `0x140004353`
- `KERNEL32!ReleaseMutex` at `0x140004424`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400043e1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400043e1`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x140004120  mov     [rsp-8+arg_10], rbx
0x140004125  push    rbp
0x140004126  push    rsi
0x140004127  push    rdi
0x140004128  push    r14
0x14000412a  push    r15
0x14000412c  lea     rbp, [rsp-160h]
0x140004134  sub     rsp, 260h
0x14000413b  mov     rax, cs:__security_cookie
0x140004142  xor     rax, rsp
0x140004145  mov     [rbp+180h+var_30], rax
0x14000414c  mov     r15, rdx
0x14000414f  mov     qword ptr [rdx], 0
0x140004156  mov     rbx, rcx
0x140004159  call    cs:__imp_GetCurrentProcessId
0x140004160  nop     dword ptr [rax+rax+00h]
0x140004165  mov     r14d, 130h
0x14000416b  mov     [rsp+280h+var_258], rbx
0x140004170  mov     r9d, eax
0x140004173  mov     [rsp+280h+var_260], r14d; int
0x140004178  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000417f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004184  lea     edx, [r14-2Ch]; unsigned __int64
0x140004188  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000418d  mov     r9d, 1F0001h; dwDesiredAccess
0x140004193  lea     rdx, [rsp+280h+Name]; lpName
0x140004198  xor     r8d, r8d; dwFlags
0x14000419b  xor     ecx, ecx; lpMutexAttributes
0x14000419d  call    cs:__imp_CreateMutexExW
0x1400041a4  nop     dword ptr [rax+rax+00h]
0x1400041a9  mov     rbx, rax
0x1400041ac  test    rax, rax
0x1400041af  jnz     short loc_1400041BB
0x1400041b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400041b6  jmp     loc_140004452
0x1400041bb  xor     r8d, r8d; bAlertable
0x1400041be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400041c1  mov     rcx, rbx; hHandle
0x1400041c4  call    cs:__imp_WaitForSingleObjectEx
0x1400041cb  nop     dword ptr [rax+rax+00h]
0x1400041d0  cmp     eax, 102h
0x1400041d5  jz      short loc_1400041E7
0x1400041d7  test    eax, 0FFFFFF7Fh
0x1400041dc  jnz     loc_14000449D
0x1400041e2  mov     rdi, rbx
0x1400041e5  jmp     short loc_1400041E9
0x1400041e7  xor     edi, edi
0x1400041e9  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1400041ee  mov     [rsp+280h+var_250], 0
0x1400041f7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400041fc  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004201  mov     esi, eax
0x140004203  test    eax, eax
0x140004205  jns     short loc_14000427D
0x140004207  mov     rcx, [rbp+188h]; this
0x14000420e  mov     r9d, eax; char *
0x140004211  mov     edx, 66h ; 'f'; void *
0x140004216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000421b  mov     rcx, [rbp+188h]; this
0x140004222  mov     r9d, esi; char *
0x140004225  mov     edx, 6Fh ; 'o'; void *
0x14000422a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000422f  mov     rcx, [rbp+188h]; this
0x140004236  mov     r9d, esi; char *
0x140004239  mov     edx, 12Eh; void *
0x14000423e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004243  test    rdi, rdi
0x140004246  jz      short loc_14000425F
0x140004248  mov     rcx, rdi; hMutex
0x14000424b  call    cs:__imp_ReleaseMutex
0x140004252  nop     dword ptr [rax+rax+00h]
0x140004257  test    eax, eax
0x140004259  jz      loc_1400044AA
0x14000425f  mov     rcx, rbx; hObject
0x140004262  call    cs:__imp_CloseHandle
0x140004269  nop     dword ptr [rax+rax+00h]
0x14000426e  test    eax, eax
0x140004270  jz      loc_1400044BC
0x140004276  mov     eax, esi
0x140004278  jmp     loc_140004452
0x14000427d  mov     rax, [rsp+280h+var_250]
0x140004282  lea     rcx, ds:0[rax*4]
0x14000428a  test    rcx, rcx
0x14000428d  jz      short loc_14000429D
0x14000428f  mov     [r15], rcx
0x140004292  mov     eax, [rcx]
0x140004294  inc     eax
0x140004296  mov     [rcx], eax
0x140004298  jmp     loc_14000441C
0x14000429d  mov     rdx, r14; dwBytes
0x1400042a0  mov     qword ptr [r15], 0
0x1400042a7  mov     ecx, 8; dwFlags
0x1400042ac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400042b1  mov     r14, rax
0x1400042b4  test    rax, rax
0x1400042b7  jnz     short loc_1400042D4
0x1400042b9  mov     rcx, [rbp+188h]; this
0x1400042c0  mov     esi, 8007000Eh
0x1400042c5  mov     r9d, esi; char *
0x1400042c8  mov     edx, 14Bh; void *
0x1400042cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042d2  jmp     short loc_140004337
0x1400042d4  xorps   xmm0, xmm0
0x1400042d7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400042dc  mov     r8, r14; void *
0x1400042df  lea     rcx, [rsp+280h+var_250]; this
0x1400042e4  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1400042ea  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1400042ef  mov     esi, eax
0x1400042f1  test    eax, eax
0x1400042f3  jns     loc_140004383
0x1400042f9  mov     rcx, [rbp+188h]; this
0x140004300  mov     r9d, eax; char *
0x140004303  mov     edx, 14Eh; void *
0x140004308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000430d  lea     rcx, [rsp+280h+var_250]; this
0x140004312  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140004317  call    cs:__imp_GetProcessHeap
0x14000431e  nop     dword ptr [rax+rax+00h]
0x140004323  mov     r8, r14; lpMem
0x140004326  xor     edx, edx; dwFlags
0x140004328  mov     rcx, rax; hHeap
0x14000432b  call    cs:__imp_HeapFree
0x140004332  nop     dword ptr [rax+rax+00h]
0x140004337  mov     rcx, [rbp+188h]; this
0x14000433e  mov     r9d, esi; char *
0x140004341  mov     edx, 137h; void *
0x140004346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000434b  test    rdi, rdi
0x14000434e  jz      short loc_140004367
0x140004350  mov     rcx, rdi; hMutex
0x140004353  call    cs:__imp_ReleaseMutex
0x14000435a  nop     dword ptr [rax+rax+00h]
0x14000435f  test    eax, eax
0x140004361  jz      loc_1400044CE
0x140004367  mov     rcx, rbx; hObject
0x14000436a  call    cs:__imp_CloseHandle
0x140004371  nop     dword ptr [rax+rax+00h]
0x140004376  test    eax, eax
0x140004378  jz      loc_14000448B
0x14000437e  jmp     loc_140004276
0x140004383  mov     rax, [rsp+280h+var_250]
0x140004388  lea     rcx, [r14+28h]; void *
0x14000438c  mov     [r14+10h], rax
0x140004390  xor     edx, edx; Val
0x140004392  mov     rax, [rsp+280h+var_250+8]
0x140004397  mov     r8d, 108h; Size
0x14000439d  mov     [r14+18h], rax
0x1400043a1  mov     dword ptr [r14], 1
0x1400043a8  mov     [r14+8], rbx
0x1400043ac  mov     [rsp+280h+var_250], 0
0x1400043b5  mov     [rsp+280h+var_250+8], 0
0x1400043be  call    memset_0
0x1400043c3  xor     eax, eax
0x1400043c5  lea     rcx, [r14+28h]; this
0x1400043c9  mov     [r14+20h], rax
0x1400043cd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400043d2  lea     rbx, [r14+0E8h]
0x1400043d9  xor     r8d, r8d; Flags
0x1400043dc  mov     rcx, rbx; lpCriticalSection
0x1400043df  xor     edx, edx; dwSpinCount
0x1400043e1  call    cs:__imp_InitializeCriticalSectionEx
0x1400043e8  nop     dword ptr [rax+rax+00h]
0x1400043ed  mov     qword ptr [rbx+28h], 0
0x1400043f5  lea     rcx, [rsp+280h+var_250]; this
0x1400043fa  mov     qword ptr [rbx+30h], 0
0x140004402  mov     qword ptr [rbx+38h], 0
0x14000440a  mov     qword ptr [rbx+40h], 0
0x140004412  mov     [r15], r14
0x140004415  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000441a  xor     ebx, ebx
0x14000441c  test    rdi, rdi
0x14000441f  jz      short loc_140004438
0x140004421  mov     rcx, rdi; hMutex
0x140004424  call    cs:__imp_ReleaseMutex
0x14000442b  nop     dword ptr [rax+rax+00h]
0x140004430  test    eax, eax
0x140004432  jz      loc_1400044E0
0x140004438  test    rbx, rbx
0x14000443b  jz      short loc_140004450
0x14000443d  mov     rcx, rbx; hObject
0x140004440  call    cs:__imp_CloseHandle
0x140004447  nop     dword ptr [rax+rax+00h]
0x14000444c  test    eax, eax
0x14000444e  jz      short loc_140004479
0x140004450  xor     eax, eax
0x140004452  mov     rcx, [rbp+180h+var_30]
0x140004459  xor     rcx, rsp; StackCookie
0x14000445c  call    __security_check_cookie
0x140004461  mov     rbx, [rsp+280h+arg_10]
0x140004469  add     rsp, 260h
0x140004470  pop     r15
0x140004472  pop     r14
0x140004474  pop     rdi
0x140004475  pop     rsi
0x140004476  pop     rbp
0x140004477  retn
0x140004479  mov     rcx, [rbp+188h]; this
0x140004480  mov     edx, 0A0Bh; void *
0x140004485  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000448b  mov     rcx, [rbp+188h]; this
0x140004492  mov     edx, 0A0Bh; void *
0x140004497  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000449d  mov     rcx, [rbp+188h]; this
0x1400044a4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400044aa  mov     rcx, [rbp+188h]; this
0x1400044b1  mov     edx, 0A15h; void *
0x1400044b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400044bc  mov     rcx, [rbp+188h]; this
0x1400044c3  mov     edx, 0A0Bh; void *
0x1400044c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400044ce  mov     rcx, [rbp+188h]; this
0x1400044d5  mov     edx, 0A15h; void *
0x1400044da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400044e0  mov     rcx, [rbp+188h]; this
0x1400044e7  mov     edx, 0A15h; void *
0x1400044ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
