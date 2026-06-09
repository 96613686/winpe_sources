# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023100`
- end: `0x1800234e2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800238e0`

## callees

- `0x18001e1d0`
- `0x18001eb54`
- `0x1800213ac`
- `0x180022450`
- `0x180023100`
- `0x1800234f0`
- `0x180023a70`
- `0x180024870`
- `0x180025d20`
- `0x180027a50`
- `0x180028530`
- `0x180029310`
- `0x180029320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023165`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023165`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023190`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023190`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023219`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023349`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800233e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023219`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023349`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800233e0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800233b0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800233b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023129`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002322a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800232f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002330a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002335a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002322a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800232f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002330a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002335a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023326`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023326`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023318`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023318`

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
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  char *v26; // r14
  unsigned int v27; // esi
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
  int v45; // [rsp+20h] [rbp-268h]
  int v46; // [rsp+20h] [rbp-268h]
  int v47; // [rsp+20h] [rbp-268h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (char *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            pszDest,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      *((_QWORD *)v26 + 1) = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0(v26 + 40, 0, 0x108u);
      *((_QWORD *)v26 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 232), 0, 0);
      *((_QWORD *)v26 + 34) = 0;
      v6 = 0;
      *((_QWORD *)v26 + 35) = 0;
      *((_QWORD *)v26 + 36) = 0;
      *((_QWORD *)v26 + 37) = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 304);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
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
0x180023100  push    rbx
0x180023102  push    rbp
0x180023103  push    r15
0x180023105  sub     rsp, 270h
0x18002310c  mov     rax, cs:__security_cookie
0x180023113  xor     rax, rsp
0x180023116  mov     [rsp+288h+var_38], rax
0x18002311e  xor     ebp, ebp
0x180023120  mov     r15, rdx
0x180023123  mov     [rdx], rbp
0x180023126  mov     rbx, rcx
0x180023129  call    cs:__imp_GetCurrentProcessId
0x18002312f  mov     [rsp+288h+var_260], rbx
0x180023134  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002313b  mov     r9d, eax
0x18002313e  mov     [rsp+288h+var_268], 130h; int
0x180023146  mov     edx, 104h; cchDest
0x18002314b  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180023150  call    StringCchPrintfW
0x180023155  mov     r9d, 1F0001h; dwDesiredAccess
0x18002315b  lea     rdx, [rsp+288h+pszDest]; lpName
0x180023160  xor     r8d, r8d; dwFlags
0x180023163  xor     ecx, ecx; lpMutexAttributes
0x180023165  call    cs:__imp_CreateMutexExW
0x18002316b  mov     rbx, rax
0x18002316e  test    rax, rax
0x180023171  jnz     short loc_18002317D
0x180023173  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023178  jmp     loc_18002341A
0x18002317d  xor     r8d, r8d; bAlertable
0x180023180  mov     [rsp+288h+var_20], rdi
0x180023188  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18002318d  mov     rcx, rbx; hHandle
0x180023190  call    cs:__imp_WaitForSingleObjectEx
0x180023196  cmp     eax, 102h
0x18002319b  jz      short loc_1800231AD
0x18002319d  test    eax, 0FFFFFF7Fh
0x1800231a2  jnz     loc_180023449
0x1800231a8  mov     rdi, rbx
0x1800231ab  jmp     short loc_1800231B0
0x1800231ad  mov     rdi, rbp
0x1800231b0  lea     r8, [rsp+288h+hObject]; unsigned __int64 *
0x1800231b5  mov     [rsp+288h+arg_10], rsi
0x1800231bd  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x1800231c2  mov     [rsp+288h+hObject], rbp
0x1800231c7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800231cc  mov     esi, eax
0x1800231ce  test    eax, eax
0x1800231d0  jns     short loc_18002323F
0x1800231d2  mov     rcx, [rsp+288h]; this
0x1800231da  mov     r9d, eax; char *
0x1800231dd  mov     edx, 66h ; 'f'; void *
0x1800231e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231e7  mov     rcx, [rsp+288h]; this
0x1800231ef  mov     r9d, esi; char *
0x1800231f2  mov     edx, 6Fh ; 'o'; void *
0x1800231f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231fc  mov     rcx, [rsp+288h]; this
0x180023204  mov     r9d, esi; char *
0x180023207  mov     edx, 12Eh; void *
0x18002320c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023211  test    rdi, rdi
0x180023214  jz      short loc_180023227
0x180023216  mov     rcx, rdi; hMutex
0x180023219  call    cs:__imp_ReleaseMutex
0x18002321f  test    eax, eax
0x180023221  jz      loc_180023457
0x180023227  mov     rcx, rbx; hObject
0x18002322a  call    cs:__imp_CloseHandle
0x180023230  test    eax, eax
0x180023232  jz      loc_18002346A
0x180023238  mov     eax, esi
0x18002323a  jmp     loc_18002340A
0x18002323f  mov     rax, [rsp+288h+hObject]
0x180023244  mov     [rsp+288h+var_28], r14
0x18002324c  lea     rcx, ds:0[rax*4]
0x180023254  test    rcx, rcx
0x180023257  jz      short loc_180023267
0x180023259  mov     [r15], rcx
0x18002325c  mov     eax, [rcx]
0x18002325e  inc     eax
0x180023260  mov     [rcx], eax
0x180023262  jmp     loc_1800233D8
0x180023267  mov     edx, 130h; dwBytes
0x18002326c  mov     [r15], rbp
0x18002326f  mov     ecx, 8; dwFlags
0x180023274  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023279  mov     r14, rax
0x18002327c  test    rax, rax
0x18002327f  jnz     short loc_1800232A0
0x180023281  mov     rcx, [rsp+288h]; this
0x180023289  mov     esi, 8007000Eh
0x18002328e  mov     r9d, esi; char *
0x180023291  mov     edx, 14Bh; void *
0x180023296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002329b  jmp     loc_18002332C
0x1800232a0  xorps   xmm0, xmm0
0x1800232a3  movdqu  xmmword ptr [rsp+288h+hObject], xmm0
0x1800232a9  test    r14b, 3
0x1800232ad  jnz     loc_18002347D
0x1800232b3  mov     r9, r14
0x1800232b6  lea     rdx, [rsp+288h+pszDest]; unsigned __int16 *
0x1800232bb  shr     r9, 2; unsigned __int64
0x1800232bf  lea     rcx, [rsp+288h+hObject]; this
0x1800232c4  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800232c9  mov     esi, eax
0x1800232cb  test    eax, eax
0x1800232cd  jns     loc_18002336F
0x1800232d3  mov     rcx, [rsp+288h]; this
0x1800232db  mov     r9d, eax; char *
0x1800232de  mov     edx, 14Eh; void *
0x1800232e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800232e8  mov     rcx, [rsp+288h+hObject+8]; hObject
0x1800232ed  test    rcx, rcx
0x1800232f0  jz      short loc_180023300
0x1800232f2  call    cs:__imp_CloseHandle
0x1800232f8  test    eax, eax
0x1800232fa  jz      loc_180023483
0x180023300  mov     rcx, [rsp+288h+hObject]; hObject
0x180023305  test    rcx, rcx
0x180023308  jz      short loc_180023318
0x18002330a  call    cs:__imp_CloseHandle
0x180023310  test    eax, eax
0x180023312  jz      loc_180023496
0x180023318  call    cs:__imp_GetProcessHeap
0x18002331e  mov     r8, r14; lpMem
0x180023321  xor     edx, edx; dwFlags
0x180023323  mov     rcx, rax; hHeap
0x180023326  call    cs:__imp_HeapFree
0x18002332c  mov     rcx, [rsp+288h]; this
0x180023334  mov     r9d, esi; char *
0x180023337  mov     edx, 137h; void *
0x18002333c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023341  test    rdi, rdi
0x180023344  jz      short loc_180023357
0x180023346  mov     rcx, rdi; hMutex
0x180023349  call    cs:__imp_ReleaseMutex
0x18002334f  test    eax, eax
0x180023351  jz      loc_1800234A9
0x180023357  mov     rcx, rbx; hObject
0x18002335a  call    cs:__imp_CloseHandle
0x180023360  test    eax, eax
0x180023362  jz      loc_1800234BC
0x180023368  mov     eax, esi
0x18002336a  jmp     loc_180023402
0x18002336f  movups  xmm0, xmmword ptr [rsp+288h+hObject]
0x180023374  lea     rcx, [r14+28h]; void *
0x180023378  mov     dword ptr [r14], 1
0x18002337f  xor     edx, edx; Val
0x180023381  mov     [r14+8], rbx
0x180023385  mov     r8d, 108h; Size
0x18002338b  movups  xmmword ptr [r14+10h], xmm0
0x180023390  call    memset_0
0x180023395  xor     eax, eax
0x180023397  lea     rcx, [r14+28h]; this
0x18002339b  mov     [r14+20h], rax
0x18002339f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800233a4  xor     r8d, r8d; Flags
0x1800233a7  lea     rcx, [r14+0E8h]; lpCriticalSection
0x1800233ae  xor     edx, edx; dwSpinCount
0x1800233b0  call    cs:__imp_InitializeCriticalSectionEx
0x1800233b6  mov     [r14+110h], rbp
0x1800233bd  mov     rbx, rbp
0x1800233c0  mov     [r14+118h], rbp
0x1800233c7  mov     [r14+120h], rbp
0x1800233ce  mov     [r14+128h], rbp
0x1800233d5  mov     [r15], r14
0x1800233d8  test    rdi, rdi
0x1800233db  jz      short loc_1800233EE
0x1800233dd  mov     rcx, rdi; hMutex
0x1800233e0  call    cs:__imp_ReleaseMutex
0x1800233e6  test    eax, eax
0x1800233e8  jz      loc_1800234CF
0x1800233ee  test    rbx, rbx
0x1800233f1  jz      short loc_180023400
0x1800233f3  mov     rcx, rbx; hObject
0x1800233f6  call    cs:__imp_CloseHandle
0x1800233fc  test    eax, eax
0x1800233fe  jz      short loc_180023436
0x180023400  xor     eax, eax
0x180023402  mov     r14, [rsp+288h+var_28]
0x18002340a  mov     rsi, [rsp+288h+arg_10]
0x180023412  mov     rdi, [rsp+288h+var_20]
0x18002341a  mov     rcx, [rsp+288h+var_38]
0x180023422  xor     rcx, rsp; StackCookie
0x180023425  call    __security_check_cookie
0x18002342a  add     rsp, 270h
0x180023431  pop     r15
0x180023433  pop     rbp
0x180023434  pop     rbx
0x180023435  retn
0x180023436  mov     rcx, [rsp+288h]; this
0x18002343e  mov     edx, 0A0Bh; void *
0x180023443  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023449  mov     rcx, [rsp+288h]; this
0x180023451  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180023457  mov     rcx, [rsp+288h]; this
0x18002345f  mov     edx, 0A15h; void *
0x180023464  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002346a  mov     rcx, [rsp+288h]; this
0x180023472  mov     edx, 0A0Bh; void *
0x180023477  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002347d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023483  mov     rcx, [rsp+288h]; this
0x18002348b  mov     edx, 0A0Bh; void *
0x180023490  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023496  mov     rcx, [rsp+288h]; this
0x18002349e  mov     edx, 0A0Bh; void *
0x1800234a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800234a9  mov     rcx, [rsp+288h]; this
0x1800234b1  mov     edx, 0A15h; void *
0x1800234b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800234bc  mov     rcx, [rsp+288h]; this
0x1800234c4  mov     edx, 0A0Bh; void *
0x1800234c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800234cf  mov     rcx, [rsp+288h]; this
0x1800234d7  mov     edx, 0A15h; void *
0x1800234dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
