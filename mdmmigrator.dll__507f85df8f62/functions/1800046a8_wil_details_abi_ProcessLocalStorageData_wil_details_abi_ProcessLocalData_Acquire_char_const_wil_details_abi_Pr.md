# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800046a8`
- end: `0x180004a70`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005630`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x1800046a8`
- `0x180004a78`
- `0x180004d64`
- `0x1800053c8`
- `0x180005ea8`
- `0x180006294`
- `0x180006c98`
- `0x180006d7c`
- `0x18000714c`
- `0x18000715c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004720`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004720`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004741`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004741`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800047d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004915`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004985`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800047d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004915`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800046e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800046e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000499b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000499b`

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
0x1800046a8  mov     [rsp-8+arg_10], rbx
0x1800046ad  push    rbp
0x1800046ae  push    rsi
0x1800046af  push    rdi
0x1800046b0  push    r14
0x1800046b2  push    r15
0x1800046b4  lea     rbp, [rsp-160h]
0x1800046bc  sub     rsp, 260h
0x1800046c3  mov     rax, cs:__security_cookie
0x1800046ca  xor     rax, rsp
0x1800046cd  mov     [rbp+180h+var_30], rax
0x1800046d4  mov     r15, rdx
0x1800046d7  mov     qword ptr [rdx], 0
0x1800046de  mov     rbx, rcx
0x1800046e1  call    cs:__imp_GetCurrentProcessId
0x1800046e7  mov     r14d, 78h ; 'x'
0x1800046ed  mov     [rsp+280h+var_258], rbx
0x1800046f2  mov     r9d, eax
0x1800046f5  mov     [rsp+280h+var_260], r14d; int
0x1800046fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004701  mov     edx, 104h; unsigned __int64
0x180004706  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000470b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004710  mov     r9d, 1F0001h; dwDesiredAccess
0x180004716  lea     rdx, [rsp+280h+Name]; lpName
0x18000471b  xor     r8d, r8d; dwFlags
0x18000471e  xor     ecx, ecx; lpMutexAttributes
0x180004720  call    cs:__imp_CreateMutexExW
0x180004726  mov     rbx, rax
0x180004729  test    rax, rax
0x18000472c  jnz     short loc_180004738
0x18000472e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004733  jmp     loc_1800049A7
0x180004738  xor     r8d, r8d; bAlertable
0x18000473b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000473e  mov     rcx, rbx; hHandle
0x180004741  call    cs:__imp_WaitForSingleObjectEx
0x180004747  cmp     eax, 102h
0x18000474c  jz      short loc_18000475E
0x18000474e  test    eax, 0FFFFFF7Fh
0x180004753  jnz     loc_1800049DF
0x180004759  mov     rdi, rbx
0x18000475c  jmp     short loc_180004760
0x18000475e  xor     edi, edi
0x180004760  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004765  mov     [rsp+280h+hObject], 0
0x18000476e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004773  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004778  mov     esi, eax
0x18000477a  test    eax, eax
0x18000477c  jns     short loc_1800047FD
0x18000477e  mov     rcx, [rbp+188h]; this
0x180004785  lea     r8, aWil; "wil"
0x18000478c  mov     r9d, eax; char *
0x18000478f  mov     edx, 66h ; 'f'; void *
0x180004794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004799  mov     rcx, [rbp+188h]; this
0x1800047a0  lea     r8, aWil; "wil"
0x1800047a7  mov     r9d, esi; char *
0x1800047aa  mov     edx, 6Fh ; 'o'; void *
0x1800047af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047b4  mov     rcx, [rbp+188h]; this
0x1800047bb  lea     r8, aWil; "wil"
0x1800047c2  mov     r9d, esi; char *
0x1800047c5  mov     edx, 12Eh; void *
0x1800047ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047cf  test    rdi, rdi
0x1800047d2  jz      short loc_1800047E5
0x1800047d4  mov     rcx, rdi; hMutex
0x1800047d7  call    cs:__imp_ReleaseMutex
0x1800047dd  test    eax, eax
0x1800047df  jz      loc_1800049EC
0x1800047e5  mov     rcx, rbx; hObject
0x1800047e8  call    cs:__imp_CloseHandle
0x1800047ee  test    eax, eax
0x1800047f0  jz      loc_1800049FE
0x1800047f6  mov     eax, esi
0x1800047f8  jmp     loc_1800049A7
0x1800047fd  mov     rax, [rsp+280h+hObject]
0x180004802  lea     rcx, ds:0[rax*4]
0x18000480a  test    rcx, rcx
0x18000480d  jz      short loc_18000481D
0x18000480f  mov     [r15], rcx
0x180004812  mov     eax, [rcx]
0x180004814  inc     eax
0x180004816  mov     [rcx], eax
0x180004818  jmp     loc_18000497D
0x18000481d  mov     rdx, r14; dwBytes
0x180004820  mov     qword ptr [r15], 0
0x180004827  mov     ecx, 8; dwFlags
0x18000482c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004831  mov     rsi, rax
0x180004834  test    rax, rax
0x180004837  jnz     short loc_18000485F
0x180004839  mov     rcx, [rbp+188h]; this
0x180004840  lea     r8, aWil; "wil"
0x180004847  mov     r14d, 8007000Eh
0x18000484d  mov     edx, 14Bh; void *
0x180004852  mov     r9d, r14d; char *
0x180004855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000485a  jmp     loc_1800048F2
0x18000485f  xorps   xmm0, xmm0
0x180004862  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004868  test    sil, 3
0x18000486c  jnz     loc_180004A10
0x180004872  mov     r9, rsi
0x180004875  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000487a  shr     r9, 2; unsigned __int64
0x18000487e  lea     rcx, [rsp+280h+hObject]; this
0x180004883  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004888  mov     r14d, eax
0x18000488b  test    eax, eax
0x18000488d  jns     loc_180004939
0x180004893  mov     rcx, [rbp+188h]; this
0x18000489a  lea     r8, aWil; "wil"
0x1800048a1  mov     r9d, eax; char *
0x1800048a4  mov     edx, 14Eh; void *
0x1800048a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048ae  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800048b3  test    rcx, rcx
0x1800048b6  jz      short loc_1800048C6
0x1800048b8  call    cs:__imp_CloseHandle
0x1800048be  test    eax, eax
0x1800048c0  jz      loc_180004A16
0x1800048c6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800048cb  test    rcx, rcx
0x1800048ce  jz      short loc_1800048DE
0x1800048d0  call    cs:__imp_CloseHandle
0x1800048d6  test    eax, eax
0x1800048d8  jz      loc_180004A28
0x1800048de  call    cs:__imp_GetProcessHeap
0x1800048e4  mov     r8, rsi; lpMem
0x1800048e7  xor     edx, edx; dwFlags
0x1800048e9  mov     rcx, rax; hHeap
0x1800048ec  call    cs:__imp_HeapFree
0x1800048f2  mov     rcx, [rbp+188h]; this
0x1800048f9  lea     r8, aWil; "wil"
0x180004900  mov     r9d, r14d; char *
0x180004903  mov     edx, 137h; void *
0x180004908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000490d  test    rdi, rdi
0x180004910  jz      short loc_180004923
0x180004912  mov     rcx, rdi; hMutex
0x180004915  call    cs:__imp_ReleaseMutex
0x18000491b  test    eax, eax
0x18000491d  jz      loc_180004A3A
0x180004923  mov     rcx, rbx; hObject
0x180004926  call    cs:__imp_CloseHandle
0x18000492c  test    eax, eax
0x18000492e  jz      loc_180004A4C
0x180004934  mov     eax, r14d
0x180004937  jmp     short loc_1800049A7
0x180004939  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000493e  xor     edx, edx; Val
0x180004940  mov     dword ptr [rsi], 1
0x180004946  lea     rcx, [rsi+22h]; void *
0x18000494a  mov     [rsi+8], rbx
0x18000494e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004953  lea     r8d, [rdx+56h]; Size
0x180004957  call    memset_0
0x18000495c  xor     edx, edx; Val
0x18000495e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004964  lea     rcx, [rsi+28h]; void *
0x180004968  mov     dword ptr [rsi+24h], 1
0x18000496f  lea     r8d, [rdx+50h]; Size
0x180004973  call    memset_0
0x180004978  xor     ebx, ebx
0x18000497a  mov     [r15], rsi
0x18000497d  test    rdi, rdi
0x180004980  jz      short loc_180004993
0x180004982  mov     rcx, rdi; hMutex
0x180004985  call    cs:__imp_ReleaseMutex
0x18000498b  test    eax, eax
0x18000498d  jz      loc_180004A5E
0x180004993  test    rbx, rbx
0x180004996  jz      short loc_1800049A5
0x180004998  mov     rcx, rbx; hObject
0x18000499b  call    cs:__imp_CloseHandle
0x1800049a1  test    eax, eax
0x1800049a3  jz      short loc_1800049CD
0x1800049a5  xor     eax, eax
0x1800049a7  mov     rcx, [rbp+180h+var_30]
0x1800049ae  xor     rcx, rsp; StackCookie
0x1800049b1  call    __security_check_cookie
0x1800049b6  mov     rbx, [rsp+280h+arg_10]
0x1800049be  add     rsp, 260h
0x1800049c5  pop     r15
0x1800049c7  pop     r14
0x1800049c9  pop     rdi
0x1800049ca  pop     rsi
0x1800049cb  pop     rbp
0x1800049cc  retn
0x1800049cd  mov     rcx, [rbp+188h]; this
0x1800049d4  mov     edx, 0A0Bh; void *
0x1800049d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800049df  mov     rcx, [rbp+188h]; this
0x1800049e6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800049ec  mov     rcx, [rbp+188h]; this
0x1800049f3  mov     edx, 0A15h; void *
0x1800049f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800049fe  mov     rcx, [rbp+188h]; this
0x180004a05  mov     edx, 0A0Bh; void *
0x180004a0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a16  mov     rcx, [rbp+188h]; this
0x180004a1d  mov     edx, 0A0Bh; void *
0x180004a22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a28  mov     rcx, [rbp+188h]; this
0x180004a2f  mov     edx, 0A0Bh; void *
0x180004a34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a3a  mov     rcx, [rbp+188h]; this
0x180004a41  mov     edx, 0A15h; void *
0x180004a46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a4c  mov     rcx, [rbp+188h]; this
0x180004a53  mov     edx, 0A0Bh; void *
0x180004a58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a5e  mov     rcx, [rbp+188h]; this
0x180004a65  mov     edx, 0A15h; void *
0x180004a6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
