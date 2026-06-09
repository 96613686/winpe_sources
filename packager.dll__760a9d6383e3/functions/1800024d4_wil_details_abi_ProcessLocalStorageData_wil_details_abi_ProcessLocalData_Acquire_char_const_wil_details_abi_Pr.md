# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800024d4`
- end: `0x180002872`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000334c`

## callees

- `0x1800024d4`
- `0x180002878`
- `0x180002aa0`
- `0x1800030e8`
- `0x180003bb8`
- `0x180003e74`
- `0x180004248`
- `0x1800042d4`
- `0x18000468c`
- `0x18000469c`
- `0x18000cbbe`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000256d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000256d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000254c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000254c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800025ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002717`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002787`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800025ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002717`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000250d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000250d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000279d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000279d`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1800024d4  mov     [rsp-8+arg_10], rbx
0x1800024d9  push    rbp
0x1800024da  push    rsi
0x1800024db  push    rdi
0x1800024dc  push    r14
0x1800024de  push    r15
0x1800024e0  lea     rbp, [rsp-160h]
0x1800024e8  sub     rsp, 260h
0x1800024ef  mov     rax, cs:__security_cookie
0x1800024f6  xor     rax, rsp
0x1800024f9  mov     [rbp+180h+var_30], rax
0x180002500  mov     r15, rdx
0x180002503  mov     qword ptr [rdx], 0
0x18000250a  mov     rbx, rcx
0x18000250d  call    cs:__imp_GetCurrentProcessId
0x180002513  mov     r14d, 78h ; 'x'
0x180002519  mov     [rsp+280h+var_258], rbx
0x18000251e  mov     r9d, eax
0x180002521  mov     [rsp+280h+var_260], r14d; int
0x180002526  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000252d  mov     edx, 104h; unsigned __int64
0x180002532  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002537  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000253c  mov     r9d, 1F0001h; dwDesiredAccess
0x180002542  lea     rdx, [rsp+280h+Name]; lpName
0x180002547  xor     r8d, r8d; dwFlags
0x18000254a  xor     ecx, ecx; lpMutexAttributes
0x18000254c  call    cs:__imp_CreateMutexExW
0x180002552  mov     rbx, rax
0x180002555  test    rax, rax
0x180002558  jnz     short loc_180002564
0x18000255a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000255f  jmp     loc_1800027A9
0x180002564  xor     r8d, r8d; bAlertable
0x180002567  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000256a  mov     rcx, rbx; hHandle
0x18000256d  call    cs:__imp_WaitForSingleObjectEx
0x180002573  cmp     eax, 102h
0x180002578  jz      short loc_18000258A
0x18000257a  test    eax, 0FFFFFF7Fh
0x18000257f  jnz     loc_1800027E1
0x180002585  mov     rdi, rbx
0x180002588  jmp     short loc_18000258C
0x18000258a  xor     edi, edi
0x18000258c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180002591  mov     [rsp+280h+hObject], 0
0x18000259a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000259f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800025a4  mov     esi, eax
0x1800025a6  test    eax, eax
0x1800025a8  jns     short loc_180002614
0x1800025aa  mov     rcx, [rbp+188h]; this
0x1800025b1  mov     r9d, eax; char *
0x1800025b4  mov     edx, 66h ; 'f'; void *
0x1800025b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800025be  mov     rcx, [rbp+188h]; this
0x1800025c5  mov     r9d, esi; char *
0x1800025c8  mov     edx, 6Fh ; 'o'; void *
0x1800025cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800025d2  mov     rcx, [rbp+188h]; this
0x1800025d9  mov     r9d, esi; char *
0x1800025dc  mov     edx, 12Eh; void *
0x1800025e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800025e6  test    rdi, rdi
0x1800025e9  jz      short loc_1800025FC
0x1800025eb  mov     rcx, rdi; hMutex
0x1800025ee  call    cs:__imp_ReleaseMutex
0x1800025f4  test    eax, eax
0x1800025f6  jz      loc_1800027EE
0x1800025fc  mov     rcx, rbx; hObject
0x1800025ff  call    cs:__imp_CloseHandle
0x180002605  test    eax, eax
0x180002607  jz      loc_180002800
0x18000260d  mov     eax, esi
0x18000260f  jmp     loc_1800027A9
0x180002614  mov     rax, [rsp+280h+hObject]
0x180002619  lea     rcx, ds:0[rax*4]
0x180002621  test    rcx, rcx
0x180002624  jz      short loc_180002634
0x180002626  mov     [r15], rcx
0x180002629  mov     eax, [rcx]
0x18000262b  inc     eax
0x18000262d  mov     [rcx], eax
0x18000262f  jmp     loc_18000277F
0x180002634  mov     rdx, r14; dwBytes
0x180002637  mov     qword ptr [r15], 0
0x18000263e  mov     ecx, 8; dwFlags
0x180002643  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180002648  mov     rsi, rax
0x18000264b  test    rax, rax
0x18000264e  jnz     short loc_18000266F
0x180002650  mov     rcx, [rbp+188h]; this
0x180002657  mov     r14d, 8007000Eh
0x18000265d  mov     r9d, r14d; char *
0x180002660  mov     edx, 14Bh; void *
0x180002665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000266a  jmp     loc_1800026FB
0x18000266f  xorps   xmm0, xmm0
0x180002672  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180002678  test    sil, 3
0x18000267c  jnz     loc_180002812
0x180002682  mov     r9, rsi
0x180002685  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000268a  shr     r9, 2; unsigned __int64
0x18000268e  lea     rcx, [rsp+280h+hObject]; this
0x180002693  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180002698  mov     r14d, eax
0x18000269b  test    eax, eax
0x18000269d  jns     loc_18000273B
0x1800026a3  mov     rcx, [rbp+188h]; this
0x1800026aa  mov     r9d, eax; char *
0x1800026ad  mov     edx, 14Eh; void *
0x1800026b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800026b7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800026bc  test    rcx, rcx
0x1800026bf  jz      short loc_1800026CF
0x1800026c1  call    cs:__imp_CloseHandle
0x1800026c7  test    eax, eax
0x1800026c9  jz      loc_180002818
0x1800026cf  mov     rcx, [rsp+280h+hObject]; hObject
0x1800026d4  test    rcx, rcx
0x1800026d7  jz      short loc_1800026E7
0x1800026d9  call    cs:__imp_CloseHandle
0x1800026df  test    eax, eax
0x1800026e1  jz      loc_18000282A
0x1800026e7  call    cs:__imp_GetProcessHeap
0x1800026ed  mov     r8, rsi; lpMem
0x1800026f0  xor     edx, edx; dwFlags
0x1800026f2  mov     rcx, rax; hHeap
0x1800026f5  call    cs:__imp_HeapFree
0x1800026fb  mov     rcx, [rbp+188h]; this
0x180002702  mov     r9d, r14d; char *
0x180002705  mov     edx, 137h; void *
0x18000270a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000270f  test    rdi, rdi
0x180002712  jz      short loc_180002725
0x180002714  mov     rcx, rdi; hMutex
0x180002717  call    cs:__imp_ReleaseMutex
0x18000271d  test    eax, eax
0x18000271f  jz      loc_18000283C
0x180002725  mov     rcx, rbx; hObject
0x180002728  call    cs:__imp_CloseHandle
0x18000272e  test    eax, eax
0x180002730  jz      loc_18000284E
0x180002736  mov     eax, r14d
0x180002739  jmp     short loc_1800027A9
0x18000273b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180002740  xor     edx, edx; Val
0x180002742  mov     dword ptr [rsi], 1
0x180002748  lea     rcx, [rsi+22h]; void *
0x18000274c  mov     [rsi+8], rbx
0x180002750  movdqu  xmmword ptr [rsi+10h], xmm0
0x180002755  lea     r8d, [rdx+56h]; Size
0x180002759  call    memset_0
0x18000275e  xor     edx, edx; Val
0x180002760  mov     word ptr [rsi+20h], 58h ; 'X'
0x180002766  lea     rcx, [rsi+28h]; void *
0x18000276a  mov     dword ptr [rsi+24h], 1
0x180002771  lea     r8d, [rdx+50h]; Size
0x180002775  call    memset_0
0x18000277a  xor     ebx, ebx
0x18000277c  mov     [r15], rsi
0x18000277f  test    rdi, rdi
0x180002782  jz      short loc_180002795
0x180002784  mov     rcx, rdi; hMutex
0x180002787  call    cs:__imp_ReleaseMutex
0x18000278d  test    eax, eax
0x18000278f  jz      loc_180002860
0x180002795  test    rbx, rbx
0x180002798  jz      short loc_1800027A7
0x18000279a  mov     rcx, rbx; hObject
0x18000279d  call    cs:__imp_CloseHandle
0x1800027a3  test    eax, eax
0x1800027a5  jz      short loc_1800027CF
0x1800027a7  xor     eax, eax
0x1800027a9  mov     rcx, [rbp+180h+var_30]
0x1800027b0  xor     rcx, rsp; StackCookie
0x1800027b3  call    __security_check_cookie
0x1800027b8  mov     rbx, [rsp+280h+arg_10]
0x1800027c0  add     rsp, 260h
0x1800027c7  pop     r15
0x1800027c9  pop     r14
0x1800027cb  pop     rdi
0x1800027cc  pop     rsi
0x1800027cd  pop     rbp
0x1800027ce  retn
0x1800027cf  mov     rcx, [rbp+188h]; this
0x1800027d6  mov     edx, 0A0Bh; void *
0x1800027db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800027e1  mov     rcx, [rbp+188h]; this
0x1800027e8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800027ee  mov     rcx, [rbp+188h]; this
0x1800027f5  mov     edx, 0A15h; void *
0x1800027fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180002800  mov     rcx, [rbp+188h]; this
0x180002807  mov     edx, 0A0Bh; void *
0x18000280c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180002812  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002818  mov     rcx, [rbp+188h]; this
0x18000281f  mov     edx, 0A0Bh; void *
0x180002824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000282a  mov     rcx, [rbp+188h]; this
0x180002831  mov     edx, 0A0Bh; void *
0x180002836  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000283c  mov     rcx, [rbp+188h]; this
0x180002843  mov     edx, 0A15h; void *
0x180002848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000284e  mov     rcx, [rbp+188h]; this
0x180002855  mov     edx, 0A0Bh; void *
0x18000285a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180002860  mov     rcx, [rbp+188h]; this
0x180002867  mov     edx, 0A15h; void *
0x18000286c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
