# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000717c`
- end: `0x18000754f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800089d0`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180006bdc`
- `0x18000717c`
- `0x1800079a0`
- `0x180007e5c`
- `0x180008700`
- `0x180009668`
- `0x18000b0f4`
- `0x18000bd7c`
- `0x18000c2cc`
- `0x18000cc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007221`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007221`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007481`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007481`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800071fa`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800071fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000739b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000739b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800071b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800071b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000749d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000749d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x18000717c  mov     [rsp-8+arg_10], rbx
0x180007181  push    rbp
0x180007182  push    rsi
0x180007183  push    rdi
0x180007184  push    r14
0x180007186  push    r15
0x180007188  lea     rbp, [rsp-160h]
0x180007190  sub     rsp, 260h
0x180007197  mov     rax, cs:__security_cookie
0x18000719e  xor     rax, rsp
0x1800071a1  mov     [rbp+180h+var_30], rax
0x1800071a8  mov     r15, rdx
0x1800071ab  mov     qword ptr [rdx], 0
0x1800071b2  mov     rbx, rcx
0x1800071b5  call    cs:__imp_GetCurrentProcessId
0x1800071bc  nop     dword ptr [rax+rax+00h]
0x1800071c1  mov     r14d, 78h ; 'x'
0x1800071c7  mov     [rsp+280h+var_258], rbx
0x1800071cc  mov     r9d, eax
0x1800071cf  mov     [rsp+280h+var_260], r14d; int
0x1800071d4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800071db  mov     edx, 104h; unsigned __int64
0x1800071e0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800071e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800071ea  mov     r9d, 1F0001h; dwDesiredAccess
0x1800071f0  lea     rdx, [rsp+280h+Name]; lpName
0x1800071f5  xor     r8d, r8d; dwFlags
0x1800071f8  xor     ecx, ecx; lpMutexAttributes
0x1800071fa  call    cs:__imp_CreateMutexExW
0x180007201  nop     dword ptr [rax+rax+00h]
0x180007206  mov     rbx, rax
0x180007209  test    rax, rax
0x18000720c  jnz     short loc_180007218
0x18000720e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007213  jmp     loc_1800074AF
0x180007218  xor     r8d, r8d; bAlertable
0x18000721b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000721e  mov     rcx, rbx; hHandle
0x180007221  call    cs:__imp_WaitForSingleObjectEx
0x180007228  nop     dword ptr [rax+rax+00h]
0x18000722d  cmp     eax, 102h
0x180007232  jz      short loc_180007244
0x180007234  test    eax, 0FFFFFF7Fh
0x180007239  jnz     loc_1800074FA
0x18000723f  mov     rdi, rbx
0x180007242  jmp     short loc_180007246
0x180007244  xor     edi, edi
0x180007246  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000724b  mov     [rsp+280h+var_250], 0
0x180007254  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007259  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000725e  mov     esi, eax
0x180007260  test    eax, eax
0x180007262  jns     loc_1800072F3
0x180007268  mov     rcx, [rbp+188h]; this
0x18000726f  lea     r8, aWil; "wil"
0x180007276  mov     r9d, eax; char *
0x180007279  mov     edx, 66h ; 'f'; void *
0x18000727e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007283  mov     rcx, [rbp+188h]; this
0x18000728a  lea     r8, aWil; "wil"
0x180007291  mov     r9d, esi; char *
0x180007294  mov     edx, 6Fh ; 'o'; void *
0x180007299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000729e  mov     rcx, [rbp+188h]; this
0x1800072a5  lea     r8, aWil; "wil"
0x1800072ac  mov     r9d, esi; char *
0x1800072af  mov     edx, 12Eh; void *
0x1800072b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072b9  test    rdi, rdi
0x1800072bc  jz      short loc_1800072D5
0x1800072be  mov     rcx, rdi; hMutex
0x1800072c1  call    cs:__imp_ReleaseMutex
0x1800072c8  nop     dword ptr [rax+rax+00h]
0x1800072cd  test    eax, eax
0x1800072cf  jz      loc_180007507
0x1800072d5  mov     rcx, rbx; hObject
0x1800072d8  call    cs:__imp_CloseHandle
0x1800072df  nop     dword ptr [rax+rax+00h]
0x1800072e4  test    eax, eax
0x1800072e6  jz      loc_180007519
0x1800072ec  mov     eax, esi
0x1800072ee  jmp     loc_1800074AF
0x1800072f3  mov     rax, [rsp+280h+var_250]
0x1800072f8  lea     rcx, ds:0[rax*4]
0x180007300  test    rcx, rcx
0x180007303  jz      short loc_180007313
0x180007305  mov     [r15], rcx
0x180007308  mov     eax, [rcx]
0x18000730a  inc     eax
0x18000730c  mov     [rcx], eax
0x18000730e  jmp     loc_180007479
0x180007313  mov     rdx, r14; dwBytes
0x180007316  mov     qword ptr [r15], 0
0x18000731d  mov     ecx, 8; dwFlags
0x180007322  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007327  mov     r14, rax
0x18000732a  test    rax, rax
0x18000732d  jnz     short loc_180007351
0x18000732f  mov     rcx, [rbp+188h]; this
0x180007336  lea     r8, aWil; "wil"
0x18000733d  mov     esi, 8007000Eh
0x180007342  mov     edx, 14Bh; void *
0x180007347  mov     r9d, esi; char *
0x18000734a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000734f  jmp     short loc_1800073BB
0x180007351  xorps   xmm0, xmm0
0x180007354  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007359  mov     r8, r14; void *
0x18000735c  lea     rcx, [rsp+280h+var_250]; this
0x180007361  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007367  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000736c  mov     esi, eax
0x18000736e  test    eax, eax
0x180007370  jns     loc_18000740E
0x180007376  mov     rcx, [rbp+188h]; this
0x18000737d  lea     r8, aWil; "wil"
0x180007384  mov     r9d, eax; char *
0x180007387  mov     edx, 14Eh; void *
0x18000738c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007391  lea     rcx, [rsp+280h+var_250]; this
0x180007396  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000739b  call    cs:__imp_GetProcessHeap
0x1800073a2  nop     dword ptr [rax+rax+00h]
0x1800073a7  mov     r8, r14; lpMem
0x1800073aa  xor     edx, edx; dwFlags
0x1800073ac  mov     rcx, rax; hHeap
0x1800073af  call    cs:__imp_HeapFree
0x1800073b6  nop     dword ptr [rax+rax+00h]
0x1800073bb  mov     rcx, [rbp+188h]; this
0x1800073c2  lea     r8, aWil; "wil"
0x1800073c9  mov     r9d, esi; char *
0x1800073cc  mov     edx, 137h; void *
0x1800073d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073d6  test    rdi, rdi
0x1800073d9  jz      short loc_1800073F2
0x1800073db  mov     rcx, rdi; hMutex
0x1800073de  call    cs:__imp_ReleaseMutex
0x1800073e5  nop     dword ptr [rax+rax+00h]
0x1800073ea  test    eax, eax
0x1800073ec  jz      loc_18000752B
0x1800073f2  mov     rcx, rbx; hObject
0x1800073f5  call    cs:__imp_CloseHandle
0x1800073fc  nop     dword ptr [rax+rax+00h]
0x180007401  test    eax, eax
0x180007403  jz      loc_1800074E8
0x180007409  jmp     loc_1800072EC
0x18000740e  mov     rax, [rsp+280h+var_250]
0x180007413  lea     rcx, [r14+22h]; void *
0x180007417  xor     edx, edx; Val
0x180007419  mov     [r14+10h], rax
0x18000741d  mov     rax, [rsp+280h+var_250+8]
0x180007422  mov     dword ptr [r14], 1
0x180007429  mov     [r14+8], rbx
0x18000742d  lea     r8d, [rdx+56h]; Size
0x180007431  mov     [rsp+280h+var_250], 0
0x18000743a  mov     [r14+18h], rax
0x18000743e  mov     [rsp+280h+var_250+8], 0
0x180007447  call    memset_0
0x18000744c  xor     edx, edx; Val
0x18000744e  mov     word ptr [r14+20h], 58h ; 'X'
0x180007455  lea     rcx, [r14+28h]; void *
0x180007459  mov     dword ptr [r14+24h], 1
0x180007461  lea     r8d, [rdx+50h]; Size
0x180007465  call    memset_0
0x18000746a  lea     rcx, [rsp+280h+var_250]; this
0x18000746f  mov     [r15], r14
0x180007472  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007477  xor     ebx, ebx
0x180007479  test    rdi, rdi
0x18000747c  jz      short loc_180007495
0x18000747e  mov     rcx, rdi; hMutex
0x180007481  call    cs:__imp_ReleaseMutex
0x180007488  nop     dword ptr [rax+rax+00h]
0x18000748d  test    eax, eax
0x18000748f  jz      loc_18000753D
0x180007495  test    rbx, rbx
0x180007498  jz      short loc_1800074AD
0x18000749a  mov     rcx, rbx; hObject
0x18000749d  call    cs:__imp_CloseHandle
0x1800074a4  nop     dword ptr [rax+rax+00h]
0x1800074a9  test    eax, eax
0x1800074ab  jz      short loc_1800074D6
0x1800074ad  xor     eax, eax
0x1800074af  mov     rcx, [rbp+180h+var_30]
0x1800074b6  xor     rcx, rsp; StackCookie
0x1800074b9  call    __security_check_cookie
0x1800074be  mov     rbx, [rsp+280h+arg_10]
0x1800074c6  add     rsp, 260h
0x1800074cd  pop     r15
0x1800074cf  pop     r14
0x1800074d1  pop     rdi
0x1800074d2  pop     rsi
0x1800074d3  pop     rbp
0x1800074d4  retn
0x1800074d6  mov     rcx, [rbp+188h]; this
0x1800074dd  mov     edx, 0A0Bh; void *
0x1800074e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074e8  mov     rcx, [rbp+188h]; this
0x1800074ef  mov     edx, 0A0Bh; void *
0x1800074f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074fa  mov     rcx, [rbp+188h]; this
0x180007501  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007507  mov     rcx, [rbp+188h]; this
0x18000750e  mov     edx, 0A15h; void *
0x180007513  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007519  mov     rcx, [rbp+188h]; this
0x180007520  mov     edx, 0A0Bh; void *
0x180007525  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000752b  mov     rcx, [rbp+188h]; this
0x180007532  mov     edx, 0A15h; void *
0x180007537  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000753d  mov     rcx, [rbp+188h]; this
0x180007544  mov     edx, 0A15h; void *
0x180007549  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
