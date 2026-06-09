# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003114`
- end: `0x1800034b2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004a4c`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180003114`
- `0x1800038a4`
- `0x180003ec4`
- `0x1800047e8`
- `0x1800053f8`
- `0x1800067e0`
- `0x180006d20`
- `0x180007048`
- `0x18000782c`
- `0x18000783c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000318c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000318c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800031ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800031ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000322e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003357`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000322e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003357`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003335`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000314d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000314d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000323f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000323f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033dd`

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
0x180003114  mov     [rsp-8+arg_10], rbx
0x180003119  push    rbp
0x18000311a  push    rsi
0x18000311b  push    rdi
0x18000311c  push    r14
0x18000311e  push    r15
0x180003120  lea     rbp, [rsp-160h]
0x180003128  sub     rsp, 260h
0x18000312f  mov     rax, cs:__security_cookie
0x180003136  xor     rax, rsp
0x180003139  mov     [rbp+180h+var_30], rax
0x180003140  mov     r15, rdx
0x180003143  mov     qword ptr [rdx], 0
0x18000314a  mov     rbx, rcx
0x18000314d  call    cs:__imp_GetCurrentProcessId
0x180003153  mov     r14d, 78h ; 'x'
0x180003159  mov     [rsp+280h+var_258], rbx
0x18000315e  mov     r9d, eax
0x180003161  mov     [rsp+280h+var_260], r14d; int
0x180003166  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000316d  mov     edx, 104h; unsigned __int64
0x180003172  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003177  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000317c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003182  lea     rdx, [rsp+280h+Name]; lpName
0x180003187  xor     r8d, r8d; dwFlags
0x18000318a  xor     ecx, ecx; lpMutexAttributes
0x18000318c  call    cs:__imp_CreateMutexExW
0x180003192  mov     rbx, rax
0x180003195  test    rax, rax
0x180003198  jnz     short loc_1800031A4
0x18000319a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000319f  jmp     loc_1800033E9
0x1800031a4  xor     r8d, r8d; bAlertable
0x1800031a7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800031aa  mov     rcx, rbx; hHandle
0x1800031ad  call    cs:__imp_WaitForSingleObjectEx
0x1800031b3  cmp     eax, 102h
0x1800031b8  jz      short loc_1800031CA
0x1800031ba  test    eax, 0FFFFFF7Fh
0x1800031bf  jnz     loc_180003421
0x1800031c5  mov     rdi, rbx
0x1800031c8  jmp     short loc_1800031CC
0x1800031ca  xor     edi, edi
0x1800031cc  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800031d1  mov     [rsp+280h+hObject], 0
0x1800031da  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800031df  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800031e4  mov     esi, eax
0x1800031e6  test    eax, eax
0x1800031e8  jns     short loc_180003254
0x1800031ea  mov     rcx, [rbp+188h]; this
0x1800031f1  mov     r9d, eax; char *
0x1800031f4  mov     edx, 66h ; 'f'; void *
0x1800031f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031fe  mov     rcx, [rbp+188h]; this
0x180003205  mov     r9d, esi; char *
0x180003208  mov     edx, 6Fh ; 'o'; void *
0x18000320d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003212  mov     rcx, [rbp+188h]; this
0x180003219  mov     r9d, esi; char *
0x18000321c  mov     edx, 12Eh; void *
0x180003221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003226  test    rdi, rdi
0x180003229  jz      short loc_18000323C
0x18000322b  mov     rcx, rdi; hMutex
0x18000322e  call    cs:__imp_ReleaseMutex
0x180003234  test    eax, eax
0x180003236  jz      loc_18000342E
0x18000323c  mov     rcx, rbx; hObject
0x18000323f  call    cs:__imp_CloseHandle
0x180003245  test    eax, eax
0x180003247  jz      loc_180003440
0x18000324d  mov     eax, esi
0x18000324f  jmp     loc_1800033E9
0x180003254  mov     rax, [rsp+280h+hObject]
0x180003259  lea     rcx, ds:0[rax*4]
0x180003261  test    rcx, rcx
0x180003264  jz      short loc_180003274
0x180003266  mov     [r15], rcx
0x180003269  mov     eax, [rcx]
0x18000326b  inc     eax
0x18000326d  mov     [rcx], eax
0x18000326f  jmp     loc_1800033BF
0x180003274  mov     rdx, r14; dwBytes
0x180003277  mov     qword ptr [r15], 0
0x18000327e  mov     ecx, 8; dwFlags
0x180003283  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003288  mov     rsi, rax
0x18000328b  test    rax, rax
0x18000328e  jnz     short loc_1800032AF
0x180003290  mov     rcx, [rbp+188h]; this
0x180003297  mov     r14d, 8007000Eh
0x18000329d  mov     r9d, r14d; char *
0x1800032a0  mov     edx, 14Bh; void *
0x1800032a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032aa  jmp     loc_18000333B
0x1800032af  xorps   xmm0, xmm0
0x1800032b2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800032b8  test    sil, 3
0x1800032bc  jnz     loc_180003452
0x1800032c2  mov     r9, rsi
0x1800032c5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800032ca  shr     r9, 2; unsigned __int64
0x1800032ce  lea     rcx, [rsp+280h+hObject]; this
0x1800032d3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800032d8  mov     r14d, eax
0x1800032db  test    eax, eax
0x1800032dd  jns     loc_18000337B
0x1800032e3  mov     rcx, [rbp+188h]; this
0x1800032ea  mov     r9d, eax; char *
0x1800032ed  mov     edx, 14Eh; void *
0x1800032f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032f7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800032fc  test    rcx, rcx
0x1800032ff  jz      short loc_18000330F
0x180003301  call    cs:__imp_CloseHandle
0x180003307  test    eax, eax
0x180003309  jz      loc_180003458
0x18000330f  mov     rcx, [rsp+280h+hObject]; hObject
0x180003314  test    rcx, rcx
0x180003317  jz      short loc_180003327
0x180003319  call    cs:__imp_CloseHandle
0x18000331f  test    eax, eax
0x180003321  jz      loc_18000346A
0x180003327  call    cs:__imp_GetProcessHeap
0x18000332d  mov     r8, rsi; lpMem
0x180003330  xor     edx, edx; dwFlags
0x180003332  mov     rcx, rax; hHeap
0x180003335  call    cs:__imp_HeapFree
0x18000333b  mov     rcx, [rbp+188h]; this
0x180003342  mov     r9d, r14d; char *
0x180003345  mov     edx, 137h; void *
0x18000334a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000334f  test    rdi, rdi
0x180003352  jz      short loc_180003365
0x180003354  mov     rcx, rdi; hMutex
0x180003357  call    cs:__imp_ReleaseMutex
0x18000335d  test    eax, eax
0x18000335f  jz      loc_18000347C
0x180003365  mov     rcx, rbx; hObject
0x180003368  call    cs:__imp_CloseHandle
0x18000336e  test    eax, eax
0x180003370  jz      loc_18000348E
0x180003376  mov     eax, r14d
0x180003379  jmp     short loc_1800033E9
0x18000337b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003380  xor     edx, edx; Val
0x180003382  mov     dword ptr [rsi], 1
0x180003388  lea     rcx, [rsi+22h]; void *
0x18000338c  mov     [rsi+8], rbx
0x180003390  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003395  lea     r8d, [rdx+56h]; Size
0x180003399  call    memset_0
0x18000339e  xor     edx, edx; Val
0x1800033a0  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800033a6  lea     rcx, [rsi+28h]; void *
0x1800033aa  mov     dword ptr [rsi+24h], 1
0x1800033b1  lea     r8d, [rdx+50h]; Size
0x1800033b5  call    memset_0
0x1800033ba  xor     ebx, ebx
0x1800033bc  mov     [r15], rsi
0x1800033bf  test    rdi, rdi
0x1800033c2  jz      short loc_1800033D5
0x1800033c4  mov     rcx, rdi; hMutex
0x1800033c7  call    cs:__imp_ReleaseMutex
0x1800033cd  test    eax, eax
0x1800033cf  jz      loc_1800034A0
0x1800033d5  test    rbx, rbx
0x1800033d8  jz      short loc_1800033E7
0x1800033da  mov     rcx, rbx; hObject
0x1800033dd  call    cs:__imp_CloseHandle
0x1800033e3  test    eax, eax
0x1800033e5  jz      short loc_18000340F
0x1800033e7  xor     eax, eax
0x1800033e9  mov     rcx, [rbp+180h+var_30]
0x1800033f0  xor     rcx, rsp; StackCookie
0x1800033f3  call    __security_check_cookie
0x1800033f8  mov     rbx, [rsp+280h+arg_10]
0x180003400  add     rsp, 260h
0x180003407  pop     r15
0x180003409  pop     r14
0x18000340b  pop     rdi
0x18000340c  pop     rsi
0x18000340d  pop     rbp
0x18000340e  retn
0x18000340f  mov     rcx, [rbp+188h]; this
0x180003416  mov     edx, 0A0Bh; void *
0x18000341b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003421  mov     rcx, [rbp+188h]; this
0x180003428  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000342e  mov     rcx, [rbp+188h]; this
0x180003435  mov     edx, 0A15h; void *
0x18000343a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003440  mov     rcx, [rbp+188h]; this
0x180003447  mov     edx, 0A0Bh; void *
0x18000344c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003452  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003458  mov     rcx, [rbp+188h]; this
0x18000345f  mov     edx, 0A0Bh; void *
0x180003464  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000346a  mov     rcx, [rbp+188h]; this
0x180003471  mov     edx, 0A0Bh; void *
0x180003476  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000347c  mov     rcx, [rbp+188h]; this
0x180003483  mov     edx, 0A15h; void *
0x180003488  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000348e  mov     rcx, [rbp+188h]; this
0x180003495  mov     edx, 0A0Bh; void *
0x18000349a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034a0  mov     rcx, [rbp+188h]; this
0x1800034a7  mov     edx, 0A15h; void *
0x1800034ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
