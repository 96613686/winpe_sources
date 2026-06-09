# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003140`
- end: `0x180003508`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004000`

## callees

- `0x180003140`
- `0x180003524`
- `0x180003800`
- `0x180003d98`
- `0x180004898`
- `0x180004da4`
- `0x180005570`
- `0x18000564c`
- `0x180005b00`
- `0x180005b10`
- `0x18000c5ce`
- `0x18000c600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000326f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000341d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000326f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000341d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800031d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800031d9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031b8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003384`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003384`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003376`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003433`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180003140  mov     [rsp-8+arg_10], rbx
0x180003145  push    rbp
0x180003146  push    rsi
0x180003147  push    rdi
0x180003148  push    r14
0x18000314a  push    r15
0x18000314c  lea     rbp, [rsp-160h]
0x180003154  sub     rsp, 260h
0x18000315b  mov     rax, cs:__security_cookie
0x180003162  xor     rax, rsp
0x180003165  mov     [rbp+180h+var_30], rax
0x18000316c  mov     r15, rdx
0x18000316f  mov     qword ptr [rdx], 0
0x180003176  mov     rbx, rcx
0x180003179  call    cs:__imp_GetCurrentProcessId
0x18000317f  mov     r14d, 78h ; 'x'
0x180003185  mov     [rsp+280h+var_258], rbx
0x18000318a  mov     r9d, eax
0x18000318d  mov     [rsp+280h+var_260], r14d; int
0x180003192  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003199  mov     edx, 104h; unsigned __int64
0x18000319e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800031a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800031a8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800031ae  lea     rdx, [rsp+280h+Name]; lpName
0x1800031b3  xor     r8d, r8d; dwFlags
0x1800031b6  xor     ecx, ecx; lpMutexAttributes
0x1800031b8  call    cs:__imp_CreateMutexExW
0x1800031be  mov     rbx, rax
0x1800031c1  test    rax, rax
0x1800031c4  jnz     short loc_1800031D0
0x1800031c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800031cb  jmp     loc_18000343F
0x1800031d0  xor     r8d, r8d; bAlertable
0x1800031d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800031d6  mov     rcx, rbx; hHandle
0x1800031d9  call    cs:__imp_WaitForSingleObjectEx
0x1800031df  cmp     eax, 102h
0x1800031e4  jz      short loc_1800031F6
0x1800031e6  test    eax, 0FFFFFF7Fh
0x1800031eb  jnz     loc_180003477
0x1800031f1  mov     rdi, rbx
0x1800031f4  jmp     short loc_1800031F8
0x1800031f6  xor     edi, edi
0x1800031f8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800031fd  mov     [rsp+280h+hObject], 0
0x180003206  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000320b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003210  mov     esi, eax
0x180003212  test    eax, eax
0x180003214  jns     short loc_180003295
0x180003216  mov     rcx, [rbp+188h]; this
0x18000321d  lea     r8, aWil; "wil"
0x180003224  mov     r9d, eax; char *
0x180003227  mov     edx, 66h ; 'f'; void *
0x18000322c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003231  mov     rcx, [rbp+188h]; this
0x180003238  lea     r8, aWil; "wil"
0x18000323f  mov     r9d, esi; char *
0x180003242  mov     edx, 6Fh ; 'o'; void *
0x180003247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000324c  mov     rcx, [rbp+188h]; this
0x180003253  lea     r8, aWil; "wil"
0x18000325a  mov     r9d, esi; char *
0x18000325d  mov     edx, 12Eh; void *
0x180003262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003267  test    rdi, rdi
0x18000326a  jz      short loc_18000327D
0x18000326c  mov     rcx, rdi; hMutex
0x18000326f  call    cs:__imp_ReleaseMutex
0x180003275  test    eax, eax
0x180003277  jz      loc_180003484
0x18000327d  mov     rcx, rbx; hObject
0x180003280  call    cs:__imp_CloseHandle
0x180003286  test    eax, eax
0x180003288  jz      loc_180003496
0x18000328e  mov     eax, esi
0x180003290  jmp     loc_18000343F
0x180003295  mov     rax, [rsp+280h+hObject]
0x18000329a  lea     rcx, ds:0[rax*4]
0x1800032a2  test    rcx, rcx
0x1800032a5  jz      short loc_1800032B5
0x1800032a7  mov     [r15], rcx
0x1800032aa  mov     eax, [rcx]
0x1800032ac  inc     eax
0x1800032ae  mov     [rcx], eax
0x1800032b0  jmp     loc_180003415
0x1800032b5  mov     rdx, r14; dwBytes
0x1800032b8  mov     qword ptr [r15], 0
0x1800032bf  mov     ecx, 8; dwFlags
0x1800032c4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800032c9  mov     rsi, rax
0x1800032cc  test    rax, rax
0x1800032cf  jnz     short loc_1800032F7
0x1800032d1  mov     rcx, [rbp+188h]; this
0x1800032d8  lea     r8, aWil; "wil"
0x1800032df  mov     r14d, 8007000Eh
0x1800032e5  mov     edx, 14Bh; void *
0x1800032ea  mov     r9d, r14d; char *
0x1800032ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032f2  jmp     loc_18000338A
0x1800032f7  xorps   xmm0, xmm0
0x1800032fa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003300  test    sil, 3
0x180003304  jnz     loc_1800034A8
0x18000330a  mov     r9, rsi
0x18000330d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003312  shr     r9, 2; unsigned __int64
0x180003316  lea     rcx, [rsp+280h+hObject]; this
0x18000331b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003320  mov     r14d, eax
0x180003323  test    eax, eax
0x180003325  jns     loc_1800033D1
0x18000332b  mov     rcx, [rbp+188h]; this
0x180003332  lea     r8, aWil; "wil"
0x180003339  mov     r9d, eax; char *
0x18000333c  mov     edx, 14Eh; void *
0x180003341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003346  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000334b  test    rcx, rcx
0x18000334e  jz      short loc_18000335E
0x180003350  call    cs:__imp_CloseHandle
0x180003356  test    eax, eax
0x180003358  jz      loc_1800034AE
0x18000335e  mov     rcx, [rsp+280h+hObject]; hObject
0x180003363  test    rcx, rcx
0x180003366  jz      short loc_180003376
0x180003368  call    cs:__imp_CloseHandle
0x18000336e  test    eax, eax
0x180003370  jz      loc_1800034C0
0x180003376  call    cs:__imp_GetProcessHeap
0x18000337c  mov     r8, rsi; lpMem
0x18000337f  xor     edx, edx; dwFlags
0x180003381  mov     rcx, rax; hHeap
0x180003384  call    cs:__imp_HeapFree
0x18000338a  mov     rcx, [rbp+188h]; this
0x180003391  lea     r8, aWil; "wil"
0x180003398  mov     r9d, r14d; char *
0x18000339b  mov     edx, 137h; void *
0x1800033a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033a5  test    rdi, rdi
0x1800033a8  jz      short loc_1800033BB
0x1800033aa  mov     rcx, rdi; hMutex
0x1800033ad  call    cs:__imp_ReleaseMutex
0x1800033b3  test    eax, eax
0x1800033b5  jz      loc_1800034D2
0x1800033bb  mov     rcx, rbx; hObject
0x1800033be  call    cs:__imp_CloseHandle
0x1800033c4  test    eax, eax
0x1800033c6  jz      loc_1800034E4
0x1800033cc  mov     eax, r14d
0x1800033cf  jmp     short loc_18000343F
0x1800033d1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800033d6  xor     edx, edx; Val
0x1800033d8  mov     dword ptr [rsi], 1
0x1800033de  lea     rcx, [rsi+22h]; void *
0x1800033e2  mov     [rsi+8], rbx
0x1800033e6  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800033eb  lea     r8d, [rdx+56h]; Size
0x1800033ef  call    memset_0
0x1800033f4  xor     edx, edx; Val
0x1800033f6  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800033fc  lea     rcx, [rsi+28h]; void *
0x180003400  mov     dword ptr [rsi+24h], 1
0x180003407  lea     r8d, [rdx+50h]; Size
0x18000340b  call    memset_0
0x180003410  xor     ebx, ebx
0x180003412  mov     [r15], rsi
0x180003415  test    rdi, rdi
0x180003418  jz      short loc_18000342B
0x18000341a  mov     rcx, rdi; hMutex
0x18000341d  call    cs:__imp_ReleaseMutex
0x180003423  test    eax, eax
0x180003425  jz      loc_1800034F6
0x18000342b  test    rbx, rbx
0x18000342e  jz      short loc_18000343D
0x180003430  mov     rcx, rbx; hObject
0x180003433  call    cs:__imp_CloseHandle
0x180003439  test    eax, eax
0x18000343b  jz      short loc_180003465
0x18000343d  xor     eax, eax
0x18000343f  mov     rcx, [rbp+180h+var_30]
0x180003446  xor     rcx, rsp; StackCookie
0x180003449  call    __security_check_cookie
0x18000344e  mov     rbx, [rsp+280h+arg_10]
0x180003456  add     rsp, 260h
0x18000345d  pop     r15
0x18000345f  pop     r14
0x180003461  pop     rdi
0x180003462  pop     rsi
0x180003463  pop     rbp
0x180003464  retn
0x180003465  mov     rcx, [rbp+188h]; this
0x18000346c  mov     edx, 0A0Bh; void *
0x180003471  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003477  mov     rcx, [rbp+188h]; this
0x18000347e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003484  mov     rcx, [rbp+188h]; this
0x18000348b  mov     edx, 0A15h; void *
0x180003490  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003496  mov     rcx, [rbp+188h]; this
0x18000349d  mov     edx, 0A0Bh; void *
0x1800034a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800034ae  mov     rcx, [rbp+188h]; this
0x1800034b5  mov     edx, 0A0Bh; void *
0x1800034ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034c0  mov     rcx, [rbp+188h]; this
0x1800034c7  mov     edx, 0A0Bh; void *
0x1800034cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034d2  mov     rcx, [rbp+188h]; this
0x1800034d9  mov     edx, 0A15h; void *
0x1800034de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034e4  mov     rcx, [rbp+188h]; this
0x1800034eb  mov     edx, 0A0Bh; void *
0x1800034f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034f6  mov     rcx, [rbp+188h]; this
0x1800034fd  mov     edx, 0A15h; void *
0x180003502  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
