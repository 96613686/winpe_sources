# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800030c8`
- end: `0x180003466`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003f40`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x1800030c8`
- `0x18000346c`
- `0x180003690`
- `0x180003cd8`
- `0x1800047a8`
- `0x180004a84`
- `0x180005484`
- `0x18000553c`
- `0x1800058ec`
- `0x1800058fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003161`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003161`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003140`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003140`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000330b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000337b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000330b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000337b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000331c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000331c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003391`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x1800030c8  mov     [rsp-8+arg_10], rbx
0x1800030cd  push    rbp
0x1800030ce  push    rsi
0x1800030cf  push    rdi
0x1800030d0  push    r14
0x1800030d2  push    r15
0x1800030d4  lea     rbp, [rsp-160h]
0x1800030dc  sub     rsp, 260h
0x1800030e3  mov     rax, cs:__security_cookie
0x1800030ea  xor     rax, rsp
0x1800030ed  mov     [rbp+180h+var_30], rax
0x1800030f4  mov     r15, rdx
0x1800030f7  mov     qword ptr [rdx], 0
0x1800030fe  mov     rbx, rcx
0x180003101  call    cs:__imp_GetCurrentProcessId
0x180003107  mov     r14d, 78h ; 'x'
0x18000310d  mov     [rsp+280h+var_258], rbx
0x180003112  mov     r9d, eax
0x180003115  mov     [rsp+280h+var_260], r14d; int
0x18000311a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003121  mov     edx, 104h; unsigned __int64
0x180003126  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000312b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003130  mov     r9d, 1F0001h; dwDesiredAccess
0x180003136  lea     rdx, [rsp+280h+Name]; lpName
0x18000313b  xor     r8d, r8d; dwFlags
0x18000313e  xor     ecx, ecx; lpMutexAttributes
0x180003140  call    cs:__imp_CreateMutexExW
0x180003146  mov     rbx, rax
0x180003149  test    rax, rax
0x18000314c  jnz     short loc_180003158
0x18000314e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003153  jmp     loc_18000339D
0x180003158  xor     r8d, r8d; bAlertable
0x18000315b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000315e  mov     rcx, rbx; hHandle
0x180003161  call    cs:__imp_WaitForSingleObjectEx
0x180003167  cmp     eax, 102h
0x18000316c  jz      short loc_18000317E
0x18000316e  test    eax, 0FFFFFF7Fh
0x180003173  jnz     loc_1800033D5
0x180003179  mov     rdi, rbx
0x18000317c  jmp     short loc_180003180
0x18000317e  xor     edi, edi
0x180003180  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003185  mov     [rsp+280h+hObject], 0
0x18000318e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003193  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003198  mov     esi, eax
0x18000319a  test    eax, eax
0x18000319c  jns     short loc_180003208
0x18000319e  mov     rcx, [rbp+188h]; this
0x1800031a5  mov     r9d, eax; char *
0x1800031a8  mov     edx, 66h ; 'f'; void *
0x1800031ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031b2  mov     rcx, [rbp+188h]; this
0x1800031b9  mov     r9d, esi; char *
0x1800031bc  mov     edx, 6Fh ; 'o'; void *
0x1800031c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031c6  mov     rcx, [rbp+188h]; this
0x1800031cd  mov     r9d, esi; char *
0x1800031d0  mov     edx, 12Eh; void *
0x1800031d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031da  test    rdi, rdi
0x1800031dd  jz      short loc_1800031F0
0x1800031df  mov     rcx, rdi; hMutex
0x1800031e2  call    cs:__imp_ReleaseMutex
0x1800031e8  test    eax, eax
0x1800031ea  jz      loc_1800033E2
0x1800031f0  mov     rcx, rbx; hObject
0x1800031f3  call    cs:__imp_CloseHandle
0x1800031f9  test    eax, eax
0x1800031fb  jz      loc_1800033F4
0x180003201  mov     eax, esi
0x180003203  jmp     loc_18000339D
0x180003208  mov     rax, [rsp+280h+hObject]
0x18000320d  lea     rcx, ds:0[rax*4]
0x180003215  test    rcx, rcx
0x180003218  jz      short loc_180003228
0x18000321a  mov     [r15], rcx
0x18000321d  mov     eax, [rcx]
0x18000321f  inc     eax
0x180003221  mov     [rcx], eax
0x180003223  jmp     loc_180003373
0x180003228  mov     rdx, r14; dwBytes
0x18000322b  mov     qword ptr [r15], 0
0x180003232  mov     ecx, 8; dwFlags
0x180003237  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000323c  mov     rsi, rax
0x18000323f  test    rax, rax
0x180003242  jnz     short loc_180003263
0x180003244  mov     rcx, [rbp+188h]; this
0x18000324b  mov     r14d, 8007000Eh
0x180003251  mov     r9d, r14d; char *
0x180003254  mov     edx, 14Bh; void *
0x180003259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000325e  jmp     loc_1800032EF
0x180003263  xorps   xmm0, xmm0
0x180003266  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000326c  test    sil, 3
0x180003270  jnz     loc_180003406
0x180003276  mov     r9, rsi
0x180003279  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000327e  shr     r9, 2; unsigned __int64
0x180003282  lea     rcx, [rsp+280h+hObject]; this
0x180003287  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000328c  mov     r14d, eax
0x18000328f  test    eax, eax
0x180003291  jns     loc_18000332F
0x180003297  mov     rcx, [rbp+188h]; this
0x18000329e  mov     r9d, eax; char *
0x1800032a1  mov     edx, 14Eh; void *
0x1800032a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032ab  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800032b0  test    rcx, rcx
0x1800032b3  jz      short loc_1800032C3
0x1800032b5  call    cs:__imp_CloseHandle
0x1800032bb  test    eax, eax
0x1800032bd  jz      loc_18000340C
0x1800032c3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800032c8  test    rcx, rcx
0x1800032cb  jz      short loc_1800032DB
0x1800032cd  call    cs:__imp_CloseHandle
0x1800032d3  test    eax, eax
0x1800032d5  jz      loc_18000341E
0x1800032db  call    cs:__imp_GetProcessHeap
0x1800032e1  mov     r8, rsi; lpMem
0x1800032e4  xor     edx, edx; dwFlags
0x1800032e6  mov     rcx, rax; hHeap
0x1800032e9  call    cs:__imp_HeapFree
0x1800032ef  mov     rcx, [rbp+188h]; this
0x1800032f6  mov     r9d, r14d; char *
0x1800032f9  mov     edx, 137h; void *
0x1800032fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003303  test    rdi, rdi
0x180003306  jz      short loc_180003319
0x180003308  mov     rcx, rdi; hMutex
0x18000330b  call    cs:__imp_ReleaseMutex
0x180003311  test    eax, eax
0x180003313  jz      loc_180003430
0x180003319  mov     rcx, rbx; hObject
0x18000331c  call    cs:__imp_CloseHandle
0x180003322  test    eax, eax
0x180003324  jz      loc_180003442
0x18000332a  mov     eax, r14d
0x18000332d  jmp     short loc_18000339D
0x18000332f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003334  xor     edx, edx; Val
0x180003336  mov     dword ptr [rsi], 1
0x18000333c  lea     rcx, [rsi+22h]; void *
0x180003340  mov     [rsi+8], rbx
0x180003344  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003349  lea     r8d, [rdx+56h]; Size
0x18000334d  call    memset_0
0x180003352  xor     edx, edx; Val
0x180003354  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000335a  lea     rcx, [rsi+28h]; void *
0x18000335e  mov     dword ptr [rsi+24h], 1
0x180003365  lea     r8d, [rdx+50h]; Size
0x180003369  call    memset_0
0x18000336e  xor     ebx, ebx
0x180003370  mov     [r15], rsi
0x180003373  test    rdi, rdi
0x180003376  jz      short loc_180003389
0x180003378  mov     rcx, rdi; hMutex
0x18000337b  call    cs:__imp_ReleaseMutex
0x180003381  test    eax, eax
0x180003383  jz      loc_180003454
0x180003389  test    rbx, rbx
0x18000338c  jz      short loc_18000339B
0x18000338e  mov     rcx, rbx; hObject
0x180003391  call    cs:__imp_CloseHandle
0x180003397  test    eax, eax
0x180003399  jz      short loc_1800033C3
0x18000339b  xor     eax, eax
0x18000339d  mov     rcx, [rbp+180h+var_30]
0x1800033a4  xor     rcx, rsp; StackCookie
0x1800033a7  call    __security_check_cookie
0x1800033ac  mov     rbx, [rsp+280h+arg_10]
0x1800033b4  add     rsp, 260h
0x1800033bb  pop     r15
0x1800033bd  pop     r14
0x1800033bf  pop     rdi
0x1800033c0  pop     rsi
0x1800033c1  pop     rbp
0x1800033c2  retn
0x1800033c3  mov     rcx, [rbp+188h]; this
0x1800033ca  mov     edx, 0A0Bh; void *
0x1800033cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033d5  mov     rcx, [rbp+188h]; this
0x1800033dc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800033e2  mov     rcx, [rbp+188h]; this
0x1800033e9  mov     edx, 0A15h; void *
0x1800033ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033f4  mov     rcx, [rbp+188h]; this
0x1800033fb  mov     edx, 0A0Bh; void *
0x180003400  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003406  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000340c  mov     rcx, [rbp+188h]; this
0x180003413  mov     edx, 0A0Bh; void *
0x180003418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000341e  mov     rcx, [rbp+188h]; this
0x180003425  mov     edx, 0A0Bh; void *
0x18000342a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003430  mov     rcx, [rbp+188h]; this
0x180003437  mov     edx, 0A15h; void *
0x18000343c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003442  mov     rcx, [rbp+188h]; this
0x180003449  mov     edx, 0A0Bh; void *
0x18000344e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003454  mov     rcx, [rbp+188h]; this
0x18000345b  mov     edx, 0A15h; void *
0x180003460  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
