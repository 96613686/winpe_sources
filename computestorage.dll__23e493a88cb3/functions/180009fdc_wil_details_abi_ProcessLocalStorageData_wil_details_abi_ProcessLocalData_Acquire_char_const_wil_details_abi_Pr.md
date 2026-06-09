# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009fdc`
- end: `0x18000a38d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `945`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000b588`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180009640`
- `0x180009fdc`
- `0x18000a80c`
- `0x18000ad80`
- `0x18000b398`
- `0x18000db5c`
- `0x18000e414`
- `0x180012640`
- `0x180012870`
- `0x1800134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a108`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a210`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a108`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a210`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2b3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a05a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a05a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a081`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2cf`

## string_xrefs

- `0x18000a333`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned __int64 v33; // rax
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v41, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v39);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_23;
  }
  *a2 = 0;
  v22 = wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v24 = v22;
  if ( !v22 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v23, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v26 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v22);
  v14 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v27, (const char *)(unsigned int)v26, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v25, (const char *)v14, v40);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return v14;
  }
  *((_QWORD *)v24 + 2) = v41[0];
  v33 = v41[1];
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v41[0] = 0;
  *((_QWORD *)v24 + 3) = v33;
  v41[1] = 0;
  memset_0((char *)v24 + 34, 0, 0x56u);
  *((_WORD *)v24 + 16) = 88;
  v24[9] = 1;
  memset_0(v24 + 10, 0, 0x50u);
  *a2 = v24;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x180009fdc  mov     [rsp-8+arg_10], rbx
0x180009fe1  push    rbp
0x180009fe2  push    rsi
0x180009fe3  push    rdi
0x180009fe4  push    r14
0x180009fe6  push    r15
0x180009fe8  lea     rbp, [rsp-160h]
0x180009ff0  sub     rsp, 260h
0x180009ff7  mov     rax, cs:__security_cookie
0x180009ffe  xor     rax, rsp
0x18000a001  mov     [rbp+180h+var_30], rax
0x18000a008  mov     r15, rdx
0x18000a00b  mov     qword ptr [rdx], 0
0x18000a012  mov     rbx, rcx
0x18000a015  call    cs:__imp_GetCurrentProcessId
0x18000a01c  nop     dword ptr [rax+rax+00h]
0x18000a021  mov     r14d, 78h ; 'x'
0x18000a027  mov     [rsp+280h+var_258], rbx
0x18000a02c  mov     r9d, eax
0x18000a02f  mov     [rsp+280h+var_260], r14d; int
0x18000a034  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a03b  mov     edx, 104h; unsigned __int64
0x18000a040  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a045  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a04a  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a050  lea     rdx, [rsp+280h+Name]; lpName
0x18000a055  xor     r8d, r8d; dwFlags
0x18000a058  xor     ecx, ecx; lpMutexAttributes
0x18000a05a  call    cs:__imp_CreateMutexExW
0x18000a061  nop     dword ptr [rax+rax+00h]
0x18000a066  mov     rbx, rax
0x18000a069  test    rax, rax
0x18000a06c  jnz     short loc_18000A078
0x18000a06e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a073  jmp     loc_18000A2E1
0x18000a078  xor     r8d, r8d; bAlertable
0x18000a07b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a07e  mov     rcx, rbx; hHandle
0x18000a081  call    cs:__imp_WaitForSingleObjectEx
0x18000a088  nop     dword ptr [rax+rax+00h]
0x18000a08d  cmp     eax, 102h
0x18000a092  jz      short loc_18000A0A4
0x18000a094  test    eax, 0FFFFFF7Fh
0x18000a099  jnz     loc_18000A32C
0x18000a09f  mov     rdi, rbx
0x18000a0a2  jmp     short loc_18000A0A6
0x18000a0a4  xor     edi, edi
0x18000a0a6  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000a0ab  mov     [rsp+280h+var_250], 0
0x18000a0b4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a0b9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a0be  mov     esi, eax
0x18000a0c0  test    eax, eax
0x18000a0c2  jns     short loc_18000A13A
0x18000a0c4  mov     rcx, [rbp+188h]; this
0x18000a0cb  mov     r9d, eax; char *
0x18000a0ce  mov     edx, 66h ; 'f'; void *
0x18000a0d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0d8  mov     rcx, [rbp+188h]; this
0x18000a0df  mov     r9d, esi; char *
0x18000a0e2  mov     edx, 6Fh ; 'o'; void *
0x18000a0e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0ec  mov     rcx, [rbp+188h]; this
0x18000a0f3  mov     r9d, esi; char *
0x18000a0f6  mov     edx, 12Eh; void *
0x18000a0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a100  test    rdi, rdi
0x18000a103  jz      short loc_18000A11C
0x18000a105  mov     rcx, rdi; hMutex
0x18000a108  call    cs:__imp_ReleaseMutex
0x18000a10f  nop     dword ptr [rax+rax+00h]
0x18000a114  test    eax, eax
0x18000a116  jz      loc_18000A345
0x18000a11c  mov     rcx, rbx; hObject
0x18000a11f  call    cs:__imp_CloseHandle
0x18000a126  nop     dword ptr [rax+rax+00h]
0x18000a12b  test    eax, eax
0x18000a12d  jz      loc_18000A357
0x18000a133  mov     eax, esi
0x18000a135  jmp     loc_18000A2E1
0x18000a13a  mov     rax, [rsp+280h+var_250]
0x18000a13f  lea     rcx, ds:0[rax*4]
0x18000a147  test    rcx, rcx
0x18000a14a  jz      short loc_18000A15A
0x18000a14c  mov     [r15], rcx
0x18000a14f  mov     eax, [rcx]
0x18000a151  inc     eax
0x18000a153  mov     [rcx], eax
0x18000a155  jmp     loc_18000A2AB
0x18000a15a  mov     rdx, r14; dwBytes
0x18000a15d  mov     qword ptr [r15], 0
0x18000a164  mov     ecx, 8; dwFlags
0x18000a169  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a16e  mov     r14, rax
0x18000a171  test    rax, rax
0x18000a174  jnz     short loc_18000A191
0x18000a176  mov     rcx, [rbp+188h]; this
0x18000a17d  mov     esi, 8007000Eh
0x18000a182  mov     r9d, esi; char *
0x18000a185  mov     edx, 14Bh; void *
0x18000a18a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a18f  jmp     short loc_18000A1F4
0x18000a191  xorps   xmm0, xmm0
0x18000a194  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a199  mov     r8, r14; void *
0x18000a19c  lea     rcx, [rsp+280h+var_250]; this
0x18000a1a1  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000a1a7  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000a1ac  mov     esi, eax
0x18000a1ae  test    eax, eax
0x18000a1b0  jns     loc_18000A240
0x18000a1b6  mov     rcx, [rbp+188h]; this
0x18000a1bd  mov     r9d, eax; char *
0x18000a1c0  mov     edx, 14Eh; void *
0x18000a1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1ca  lea     rcx, [rsp+280h+var_250]; this
0x18000a1cf  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a1d4  call    cs:__imp_GetProcessHeap
0x18000a1db  nop     dword ptr [rax+rax+00h]
0x18000a1e0  mov     r8, r14; lpMem
0x18000a1e3  xor     edx, edx; dwFlags
0x18000a1e5  mov     rcx, rax; hHeap
0x18000a1e8  call    cs:__imp_HeapFree
0x18000a1ef  nop     dword ptr [rax+rax+00h]
0x18000a1f4  mov     rcx, [rbp+188h]; this
0x18000a1fb  mov     r9d, esi; char *
0x18000a1fe  mov     edx, 137h; void *
0x18000a203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a208  test    rdi, rdi
0x18000a20b  jz      short loc_18000A224
0x18000a20d  mov     rcx, rdi; hMutex
0x18000a210  call    cs:__imp_ReleaseMutex
0x18000a217  nop     dword ptr [rax+rax+00h]
0x18000a21c  test    eax, eax
0x18000a21e  jz      loc_18000A369
0x18000a224  mov     rcx, rbx; hObject
0x18000a227  call    cs:__imp_CloseHandle
0x18000a22e  nop     dword ptr [rax+rax+00h]
0x18000a233  test    eax, eax
0x18000a235  jz      loc_18000A31A
0x18000a23b  jmp     loc_18000A133
0x18000a240  mov     rax, [rsp+280h+var_250]
0x18000a245  lea     rcx, [r14+22h]; void *
0x18000a249  xor     edx, edx; Val
0x18000a24b  mov     [r14+10h], rax
0x18000a24f  mov     rax, [rsp+280h+var_250+8]
0x18000a254  mov     dword ptr [r14], 1
0x18000a25b  mov     [r14+8], rbx
0x18000a25f  lea     r8d, [rdx+56h]; Size
0x18000a263  mov     [rsp+280h+var_250], 0
0x18000a26c  mov     [r14+18h], rax
0x18000a270  mov     [rsp+280h+var_250+8], 0
0x18000a279  call    memset_0
0x18000a27e  xor     edx, edx; Val
0x18000a280  mov     word ptr [r14+20h], 58h ; 'X'
0x18000a287  lea     rcx, [r14+28h]; void *
0x18000a28b  mov     dword ptr [r14+24h], 1
0x18000a293  lea     r8d, [rdx+50h]; Size
0x18000a297  call    memset_0
0x18000a29c  lea     rcx, [rsp+280h+var_250]; this
0x18000a2a1  mov     [r15], r14
0x18000a2a4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a2a9  xor     ebx, ebx
0x18000a2ab  test    rdi, rdi
0x18000a2ae  jz      short loc_18000A2C7
0x18000a2b0  mov     rcx, rdi; hMutex
0x18000a2b3  call    cs:__imp_ReleaseMutex
0x18000a2ba  nop     dword ptr [rax+rax+00h]
0x18000a2bf  test    eax, eax
0x18000a2c1  jz      loc_18000A37B
0x18000a2c7  test    rbx, rbx
0x18000a2ca  jz      short loc_18000A2DF
0x18000a2cc  mov     rcx, rbx; hObject
0x18000a2cf  call    cs:__imp_CloseHandle
0x18000a2d6  nop     dword ptr [rax+rax+00h]
0x18000a2db  test    eax, eax
0x18000a2dd  jz      short loc_18000A308
0x18000a2df  xor     eax, eax
0x18000a2e1  mov     rcx, [rbp+180h+var_30]
0x18000a2e8  xor     rcx, rsp; StackCookie
0x18000a2eb  call    __security_check_cookie
0x18000a2f0  mov     rbx, [rsp+280h+arg_10]
0x18000a2f8  add     rsp, 260h
0x18000a2ff  pop     r15
0x18000a301  pop     r14
0x18000a303  pop     rdi
0x18000a304  pop     rsi
0x18000a305  pop     rbp
0x18000a306  retn
0x18000a308  mov     rcx, [rbp+188h]; this
0x18000a30f  mov     edx, 0A0Bh; void *
0x18000a314  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a31a  mov     rcx, [rbp+188h]; this
0x18000a321  mov     edx, 0A0Bh; void *
0x18000a326  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a32c  mov     rcx, [rbp+188h]; this
0x18000a333  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a33a  mov     edx, 0E01h; void *
0x18000a33f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a345  mov     rcx, [rbp+188h]; this
0x18000a34c  mov     edx, 0A15h; void *
0x18000a351  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a357  mov     rcx, [rbp+188h]; this
0x18000a35e  mov     edx, 0A0Bh; void *
0x18000a363  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a369  mov     rcx, [rbp+188h]; this
0x18000a370  mov     edx, 0A15h; void *
0x18000a375  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a37b  mov     rcx, [rbp+188h]; this
0x18000a382  mov     edx, 0A15h; void *
0x18000a387  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
