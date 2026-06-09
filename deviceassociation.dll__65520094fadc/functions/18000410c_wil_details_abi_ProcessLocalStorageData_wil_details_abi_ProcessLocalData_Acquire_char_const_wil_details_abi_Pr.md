# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000410c`
- end: `0x1800044aa`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000586c`

## callees

- `0x18000410c`
- `0x180004880`
- `0x180004ce4`
- `0x180005608`
- `0x1800061f8`
- `0x180007490`
- `0x180007960`
- `0x180007c68`
- `0x18000843c`
- `0x18000844c`
- `0x18000bbc2`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004226`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000434f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004226`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000434f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004184`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004184`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000431f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000431f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000432d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000432d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004145`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004145`

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
0x18000410c  mov     [rsp-8+arg_10], rbx
0x180004111  push    rbp
0x180004112  push    rsi
0x180004113  push    rdi
0x180004114  push    r14
0x180004116  push    r15
0x180004118  lea     rbp, [rsp-160h]
0x180004120  sub     rsp, 260h
0x180004127  mov     rax, cs:__security_cookie
0x18000412e  xor     rax, rsp
0x180004131  mov     [rbp+180h+var_30], rax
0x180004138  mov     r15, rdx
0x18000413b  mov     qword ptr [rdx], 0
0x180004142  mov     rbx, rcx
0x180004145  call    cs:__imp_GetCurrentProcessId
0x18000414b  mov     r14d, 78h ; 'x'
0x180004151  mov     [rsp+280h+var_258], rbx
0x180004156  mov     r9d, eax
0x180004159  mov     [rsp+280h+var_260], r14d; int
0x18000415e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004165  mov     edx, 104h; unsigned __int64
0x18000416a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000416f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004174  mov     r9d, 1F0001h; dwDesiredAccess
0x18000417a  lea     rdx, [rsp+280h+Name]; lpName
0x18000417f  xor     r8d, r8d; dwFlags
0x180004182  xor     ecx, ecx; lpMutexAttributes
0x180004184  call    cs:__imp_CreateMutexExW
0x18000418a  mov     rbx, rax
0x18000418d  test    rax, rax
0x180004190  jnz     short loc_18000419C
0x180004192  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004197  jmp     loc_1800043E1
0x18000419c  xor     r8d, r8d; bAlertable
0x18000419f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800041a2  mov     rcx, rbx; hHandle
0x1800041a5  call    cs:__imp_WaitForSingleObjectEx
0x1800041ab  cmp     eax, 102h
0x1800041b0  jz      short loc_1800041C2
0x1800041b2  test    eax, 0FFFFFF7Fh
0x1800041b7  jnz     loc_180004419
0x1800041bd  mov     rdi, rbx
0x1800041c0  jmp     short loc_1800041C4
0x1800041c2  xor     edi, edi
0x1800041c4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800041c9  mov     [rsp+280h+hObject], 0
0x1800041d2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800041d7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800041dc  mov     esi, eax
0x1800041de  test    eax, eax
0x1800041e0  jns     short loc_18000424C
0x1800041e2  mov     rcx, [rbp+188h]; this
0x1800041e9  mov     r9d, eax; char *
0x1800041ec  mov     edx, 66h ; 'f'; void *
0x1800041f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041f6  mov     rcx, [rbp+188h]; this
0x1800041fd  mov     r9d, esi; char *
0x180004200  mov     edx, 6Fh ; 'o'; void *
0x180004205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000420a  mov     rcx, [rbp+188h]; this
0x180004211  mov     r9d, esi; char *
0x180004214  mov     edx, 12Eh; void *
0x180004219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000421e  test    rdi, rdi
0x180004221  jz      short loc_180004234
0x180004223  mov     rcx, rdi; hMutex
0x180004226  call    cs:__imp_ReleaseMutex
0x18000422c  test    eax, eax
0x18000422e  jz      loc_180004426
0x180004234  mov     rcx, rbx; hObject
0x180004237  call    cs:__imp_CloseHandle
0x18000423d  test    eax, eax
0x18000423f  jz      loc_180004438
0x180004245  mov     eax, esi
0x180004247  jmp     loc_1800043E1
0x18000424c  mov     rax, [rsp+280h+hObject]
0x180004251  lea     rcx, ds:0[rax*4]
0x180004259  test    rcx, rcx
0x18000425c  jz      short loc_18000426C
0x18000425e  mov     [r15], rcx
0x180004261  mov     eax, [rcx]
0x180004263  inc     eax
0x180004265  mov     [rcx], eax
0x180004267  jmp     loc_1800043B7
0x18000426c  mov     rdx, r14; dwBytes
0x18000426f  mov     qword ptr [r15], 0
0x180004276  mov     ecx, 8; dwFlags
0x18000427b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004280  mov     rsi, rax
0x180004283  test    rax, rax
0x180004286  jnz     short loc_1800042A7
0x180004288  mov     rcx, [rbp+188h]; this
0x18000428f  mov     r14d, 8007000Eh
0x180004295  mov     r9d, r14d; char *
0x180004298  mov     edx, 14Bh; void *
0x18000429d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042a2  jmp     loc_180004333
0x1800042a7  xorps   xmm0, xmm0
0x1800042aa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800042b0  test    sil, 3
0x1800042b4  jnz     loc_18000444A
0x1800042ba  mov     r9, rsi
0x1800042bd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800042c2  shr     r9, 2; unsigned __int64
0x1800042c6  lea     rcx, [rsp+280h+hObject]; this
0x1800042cb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800042d0  mov     r14d, eax
0x1800042d3  test    eax, eax
0x1800042d5  jns     loc_180004373
0x1800042db  mov     rcx, [rbp+188h]; this
0x1800042e2  mov     r9d, eax; char *
0x1800042e5  mov     edx, 14Eh; void *
0x1800042ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042ef  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800042f4  test    rcx, rcx
0x1800042f7  jz      short loc_180004307
0x1800042f9  call    cs:__imp_CloseHandle
0x1800042ff  test    eax, eax
0x180004301  jz      loc_180004450
0x180004307  mov     rcx, [rsp+280h+hObject]; hObject
0x18000430c  test    rcx, rcx
0x18000430f  jz      short loc_18000431F
0x180004311  call    cs:__imp_CloseHandle
0x180004317  test    eax, eax
0x180004319  jz      loc_180004462
0x18000431f  call    cs:__imp_GetProcessHeap
0x180004325  mov     r8, rsi; lpMem
0x180004328  xor     edx, edx; dwFlags
0x18000432a  mov     rcx, rax; hHeap
0x18000432d  call    cs:__imp_HeapFree
0x180004333  mov     rcx, [rbp+188h]; this
0x18000433a  mov     r9d, r14d; char *
0x18000433d  mov     edx, 137h; void *
0x180004342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004347  test    rdi, rdi
0x18000434a  jz      short loc_18000435D
0x18000434c  mov     rcx, rdi; hMutex
0x18000434f  call    cs:__imp_ReleaseMutex
0x180004355  test    eax, eax
0x180004357  jz      loc_180004474
0x18000435d  mov     rcx, rbx; hObject
0x180004360  call    cs:__imp_CloseHandle
0x180004366  test    eax, eax
0x180004368  jz      loc_180004486
0x18000436e  mov     eax, r14d
0x180004371  jmp     short loc_1800043E1
0x180004373  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004378  xor     edx, edx; Val
0x18000437a  mov     dword ptr [rsi], 1
0x180004380  lea     rcx, [rsi+22h]; void *
0x180004384  mov     [rsi+8], rbx
0x180004388  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000438d  lea     r8d, [rdx+56h]; Size
0x180004391  call    memset_0
0x180004396  xor     edx, edx; Val
0x180004398  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000439e  lea     rcx, [rsi+28h]; void *
0x1800043a2  mov     dword ptr [rsi+24h], 1
0x1800043a9  lea     r8d, [rdx+50h]; Size
0x1800043ad  call    memset_0
0x1800043b2  xor     ebx, ebx
0x1800043b4  mov     [r15], rsi
0x1800043b7  test    rdi, rdi
0x1800043ba  jz      short loc_1800043CD
0x1800043bc  mov     rcx, rdi; hMutex
0x1800043bf  call    cs:__imp_ReleaseMutex
0x1800043c5  test    eax, eax
0x1800043c7  jz      loc_180004498
0x1800043cd  test    rbx, rbx
0x1800043d0  jz      short loc_1800043DF
0x1800043d2  mov     rcx, rbx; hObject
0x1800043d5  call    cs:__imp_CloseHandle
0x1800043db  test    eax, eax
0x1800043dd  jz      short loc_180004407
0x1800043df  xor     eax, eax
0x1800043e1  mov     rcx, [rbp+180h+var_30]
0x1800043e8  xor     rcx, rsp; StackCookie
0x1800043eb  call    __security_check_cookie
0x1800043f0  mov     rbx, [rsp+280h+arg_10]
0x1800043f8  add     rsp, 260h
0x1800043ff  pop     r15
0x180004401  pop     r14
0x180004403  pop     rdi
0x180004404  pop     rsi
0x180004405  pop     rbp
0x180004406  retn
0x180004407  mov     rcx, [rbp+188h]; this
0x18000440e  mov     edx, 0A0Bh; void *
0x180004413  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004419  mov     rcx, [rbp+188h]; this
0x180004420  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004426  mov     rcx, [rbp+188h]; this
0x18000442d  mov     edx, 0A15h; void *
0x180004432  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004438  mov     rcx, [rbp+188h]; this
0x18000443f  mov     edx, 0A0Bh; void *
0x180004444  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000444a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004450  mov     rcx, [rbp+188h]; this
0x180004457  mov     edx, 0A0Bh; void *
0x18000445c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004462  mov     rcx, [rbp+188h]; this
0x180004469  mov     edx, 0A0Bh; void *
0x18000446e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004474  mov     rcx, [rbp+188h]; this
0x18000447b  mov     edx, 0A15h; void *
0x180004480  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004486  mov     rcx, [rbp+188h]; this
0x18000448d  mov     edx, 0A0Bh; void *
0x180004492  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004498  mov     rcx, [rbp+188h]; this
0x18000449f  mov     edx, 0A15h; void *
0x1800044a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
