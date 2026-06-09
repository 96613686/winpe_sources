# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000e58c`
- end: `0x18000e98e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000f4c8`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000e36c`
- `0x18000e58c`
- `0x18000e994`
- `0x18000ebdc`
- `0x18000f1a0`
- `0x18000fa94`
- `0x18000ff24`
- `0x18001079c`
- `0x18001087c`
- `0x180010d94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e631`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e631`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e60a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e60a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e891`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e891`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e8ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e8ad`

## string_xrefs

- `0x18000e8ed`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e906`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e931`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e94a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e963`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e97c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  _DWORD *v19; // rax
  _DWORD *v20; // r14
  int v21; // eax
  HANDLE ProcessHeap; // rax
  const char *v23; // r9
  const char *v24; // r9
  unsigned __int64 v25; // rax
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v29);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_23;
  }
  *a2 = 0;
  v19 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v20 = v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v31 = 0;
  v21 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v31, Name, v19);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v21, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return v15;
  }
  *((_QWORD *)v20 + 2) = v31[0];
  v25 = v31[1];
  *v20 = 1;
  *((_QWORD *)v20 + 1) = v6;
  v31[0] = 0;
  *((_QWORD *)v20 + 3) = v25;
  v31[1] = 0;
  memset_0((char *)v20 + 34, 0, 0x56u);
  *((_WORD *)v20 + 16) = 88;
  v20[9] = 1;
  memset_0(v20 + 10, 0, 0x50u);
  *a2 = v20;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x18000e58c  mov     [rsp-8+arg_10], rbx
0x18000e591  push    rbp
0x18000e592  push    rsi
0x18000e593  push    rdi
0x18000e594  push    r14
0x18000e596  push    r15
0x18000e598  lea     rbp, [rsp-160h]
0x18000e5a0  sub     rsp, 260h
0x18000e5a7  mov     rax, cs:__security_cookie
0x18000e5ae  xor     rax, rsp
0x18000e5b1  mov     [rbp+180h+var_30], rax
0x18000e5b8  mov     r15, rdx
0x18000e5bb  mov     qword ptr [rdx], 0
0x18000e5c2  mov     rbx, rcx
0x18000e5c5  call    cs:__imp_GetCurrentProcessId
0x18000e5cc  nop     dword ptr [rax+rax+00h]
0x18000e5d1  mov     r14d, 78h ; 'x'
0x18000e5d7  mov     [rsp+280h+var_258], rbx
0x18000e5dc  mov     r9d, eax
0x18000e5df  mov     [rsp+280h+var_260], r14d; int
0x18000e5e4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000e5eb  mov     edx, 104h; unsigned __int64
0x18000e5f0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000e5f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e5fa  mov     r9d, 1F0001h; dwDesiredAccess
0x18000e600  lea     rdx, [rsp+280h+Name]; lpName
0x18000e605  xor     r8d, r8d; dwFlags
0x18000e608  xor     ecx, ecx; lpMutexAttributes
0x18000e60a  call    cs:__imp_CreateMutexExW
0x18000e611  nop     dword ptr [rax+rax+00h]
0x18000e616  mov     rbx, rax
0x18000e619  test    rax, rax
0x18000e61c  jnz     short loc_18000E628
0x18000e61e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e623  jmp     loc_18000E8BF
0x18000e628  xor     r8d, r8d; bAlertable
0x18000e62b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000e62e  mov     rcx, rbx; hHandle
0x18000e631  call    cs:__imp_WaitForSingleObjectEx
0x18000e638  nop     dword ptr [rax+rax+00h]
0x18000e63d  cmp     eax, 102h
0x18000e642  jz      short loc_18000E654
0x18000e644  test    eax, 0FFFFFF7Fh
0x18000e649  jnz     loc_18000E918
0x18000e64f  mov     rdi, rbx
0x18000e652  jmp     short loc_18000E656
0x18000e654  xor     edi, edi
0x18000e656  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000e65b  mov     [rsp+280h+var_250], 0
0x18000e664  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000e669  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000e66e  mov     esi, eax
0x18000e670  test    eax, eax
0x18000e672  jns     loc_18000E703
0x18000e678  mov     rcx, [rbp+188h]; this
0x18000e67f  lea     r8, aWil; "wil"
0x18000e686  mov     r9d, eax; char *
0x18000e689  mov     edx, 66h ; 'f'; void *
0x18000e68e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e693  mov     rcx, [rbp+188h]; this
0x18000e69a  lea     r8, aWil; "wil"
0x18000e6a1  mov     r9d, esi; char *
0x18000e6a4  mov     edx, 6Fh ; 'o'; void *
0x18000e6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6ae  mov     rcx, [rbp+188h]; this
0x18000e6b5  lea     r8, aWil; "wil"
0x18000e6bc  mov     r9d, esi; char *
0x18000e6bf  mov     edx, 12Eh; void *
0x18000e6c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6c9  test    rdi, rdi
0x18000e6cc  jz      short loc_18000E6E5
0x18000e6ce  mov     rcx, rdi; hMutex
0x18000e6d1  call    cs:__imp_ReleaseMutex
0x18000e6d8  nop     dword ptr [rax+rax+00h]
0x18000e6dd  test    eax, eax
0x18000e6df  jz      loc_18000E92A
0x18000e6e5  mov     rcx, rbx; hObject
0x18000e6e8  call    cs:__imp_CloseHandle
0x18000e6ef  nop     dword ptr [rax+rax+00h]
0x18000e6f4  test    eax, eax
0x18000e6f6  jz      loc_18000E943
0x18000e6fc  mov     eax, esi
0x18000e6fe  jmp     loc_18000E8BF
0x18000e703  mov     rax, [rsp+280h+var_250]
0x18000e708  lea     rcx, ds:0[rax*4]
0x18000e710  test    rcx, rcx
0x18000e713  jz      short loc_18000E723
0x18000e715  mov     [r15], rcx
0x18000e718  mov     eax, [rcx]
0x18000e71a  inc     eax
0x18000e71c  mov     [rcx], eax
0x18000e71e  jmp     loc_18000E889
0x18000e723  mov     rdx, r14; dwBytes
0x18000e726  mov     qword ptr [r15], 0
0x18000e72d  mov     ecx, 8; dwFlags
0x18000e732  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e737  mov     r14, rax
0x18000e73a  test    rax, rax
0x18000e73d  jnz     short loc_18000E761
0x18000e73f  mov     rcx, [rbp+188h]; this
0x18000e746  lea     r8, aWil; "wil"
0x18000e74d  mov     esi, 8007000Eh
0x18000e752  mov     edx, 14Bh; void *
0x18000e757  mov     r9d, esi; char *
0x18000e75a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e75f  jmp     short loc_18000E7CB
0x18000e761  xorps   xmm0, xmm0
0x18000e764  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000e769  mov     r8, r14; void *
0x18000e76c  lea     rcx, [rsp+280h+var_250]; this
0x18000e771  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000e777  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000e77c  mov     esi, eax
0x18000e77e  test    eax, eax
0x18000e780  jns     loc_18000E81E
0x18000e786  mov     rcx, [rbp+188h]; this
0x18000e78d  lea     r8, aWil; "wil"
0x18000e794  mov     r9d, eax; char *
0x18000e797  mov     edx, 14Eh; void *
0x18000e79c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7a1  lea     rcx, [rsp+280h+var_250]; this
0x18000e7a6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000e7ab  call    cs:__imp_GetProcessHeap
0x18000e7b2  nop     dword ptr [rax+rax+00h]
0x18000e7b7  mov     r8, r14; lpMem
0x18000e7ba  xor     edx, edx; dwFlags
0x18000e7bc  mov     rcx, rax; hHeap
0x18000e7bf  call    cs:__imp_HeapFree
0x18000e7c6  nop     dword ptr [rax+rax+00h]
0x18000e7cb  mov     rcx, [rbp+188h]; this
0x18000e7d2  lea     r8, aWil; "wil"
0x18000e7d9  mov     r9d, esi; char *
0x18000e7dc  mov     edx, 137h; void *
0x18000e7e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7e6  test    rdi, rdi
0x18000e7e9  jz      short loc_18000E802
0x18000e7eb  mov     rcx, rdi; hMutex
0x18000e7ee  call    cs:__imp_ReleaseMutex
0x18000e7f5  nop     dword ptr [rax+rax+00h]
0x18000e7fa  test    eax, eax
0x18000e7fc  jz      loc_18000E95C
0x18000e802  mov     rcx, rbx; hObject
0x18000e805  call    cs:__imp_CloseHandle
0x18000e80c  nop     dword ptr [rax+rax+00h]
0x18000e811  test    eax, eax
0x18000e813  jz      loc_18000E8FF
0x18000e819  jmp     loc_18000E6FC
0x18000e81e  mov     rax, [rsp+280h+var_250]
0x18000e823  lea     rcx, [r14+22h]; void *
0x18000e827  xor     edx, edx; Val
0x18000e829  mov     [r14+10h], rax
0x18000e82d  mov     rax, [rsp+280h+var_250+8]
0x18000e832  mov     dword ptr [r14], 1
0x18000e839  mov     [r14+8], rbx
0x18000e83d  lea     r8d, [rdx+56h]; Size
0x18000e841  mov     [rsp+280h+var_250], 0
0x18000e84a  mov     [r14+18h], rax
0x18000e84e  mov     [rsp+280h+var_250+8], 0
0x18000e857  call    memset_0
0x18000e85c  xor     edx, edx; Val
0x18000e85e  mov     word ptr [r14+20h], 58h ; 'X'
0x18000e865  lea     rcx, [r14+28h]; void *
0x18000e869  mov     dword ptr [r14+24h], 1
0x18000e871  lea     r8d, [rdx+50h]; Size
0x18000e875  call    memset_0
0x18000e87a  lea     rcx, [rsp+280h+var_250]; this
0x18000e87f  mov     [r15], r14
0x18000e882  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000e887  xor     ebx, ebx
0x18000e889  test    rdi, rdi
0x18000e88c  jz      short loc_18000E8A5
0x18000e88e  mov     rcx, rdi; hMutex
0x18000e891  call    cs:__imp_ReleaseMutex
0x18000e898  nop     dword ptr [rax+rax+00h]
0x18000e89d  test    eax, eax
0x18000e89f  jz      loc_18000E975
0x18000e8a5  test    rbx, rbx
0x18000e8a8  jz      short loc_18000E8BD
0x18000e8aa  mov     rcx, rbx; hObject
0x18000e8ad  call    cs:__imp_CloseHandle
0x18000e8b4  nop     dword ptr [rax+rax+00h]
0x18000e8b9  test    eax, eax
0x18000e8bb  jz      short loc_18000E8E6
0x18000e8bd  xor     eax, eax
0x18000e8bf  mov     rcx, [rbp+180h+var_30]
0x18000e8c6  xor     rcx, rsp; StackCookie
0x18000e8c9  call    __security_check_cookie
0x18000e8ce  mov     rbx, [rsp+280h+arg_10]
0x18000e8d6  add     rsp, 260h
0x18000e8dd  pop     r15
0x18000e8df  pop     r14
0x18000e8e1  pop     rdi
0x18000e8e2  pop     rsi
0x18000e8e3  pop     rbp
0x18000e8e4  retn
0x18000e8e6  mov     rcx, [rbp+188h]; this
0x18000e8ed  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e8f4  mov     edx, 0A0Bh; void *
0x18000e8f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e8ff  mov     rcx, [rbp+188h]; this
0x18000e906  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e90d  mov     edx, 0A0Bh; void *
0x18000e912  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e918  mov     rcx, [rbp+188h]; this
0x18000e91f  mov     edx, 0E01h; void *
0x18000e924  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000e92a  mov     rcx, [rbp+188h]; this
0x18000e931  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e938  mov     edx, 0A15h; void *
0x18000e93d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e943  mov     rcx, [rbp+188h]; this
0x18000e94a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e951  mov     edx, 0A0Bh; void *
0x18000e956  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e95c  mov     rcx, [rbp+188h]; this
0x18000e963  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e96a  mov     edx, 0A15h; void *
0x18000e96f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e975  mov     rcx, [rbp+188h]; this
0x18000e97c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e983  mov     edx, 0A15h; void *
0x18000e988  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
