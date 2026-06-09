# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800082b8`
- end: `0x1800086a9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800089a4`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x1800073b0`
- `0x1800082b8`
- `0x1800086b0`
- `0x180008bf8`
- `0x180009528`
- `0x18000a2b8`
- `0x18000bab4`
- `0x18000c63c`
- `0x18000cabc`
- `0x18000d438`
- `0x18000d448`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085d4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000858b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000858b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008350`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008350`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008522`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085be`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000832f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000832f`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x1800082b8  mov     [rsp-8+arg_10], rbx
0x1800082bd  push    rbp
0x1800082be  push    rsi
0x1800082bf  push    rdi
0x1800082c0  push    r14
0x1800082c2  push    r15
0x1800082c4  lea     rbp, [rsp-160h]
0x1800082cc  sub     rsp, 260h
0x1800082d3  mov     rax, cs:__security_cookie
0x1800082da  xor     rax, rsp
0x1800082dd  mov     [rbp+180h+var_30], rax
0x1800082e4  mov     r15, rdx
0x1800082e7  mov     qword ptr [rdx], 0
0x1800082ee  mov     rbx, rcx
0x1800082f1  call    cs:__imp_GetCurrentProcessId
0x1800082f7  mov     r14d, 130h
0x1800082fd  mov     [rsp+280h+var_258], rbx
0x180008302  mov     r9d, eax
0x180008305  mov     [rsp+280h+var_260], r14d; int
0x18000830a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008311  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008316  lea     edx, [r14-2Ch]; unsigned __int64
0x18000831a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000831f  mov     r9d, 1F0001h; dwDesiredAccess
0x180008325  lea     rdx, [rsp+280h+Name]; lpName
0x18000832a  xor     r8d, r8d; dwFlags
0x18000832d  xor     ecx, ecx; lpMutexAttributes
0x18000832f  call    cs:__imp_CreateMutexExW
0x180008335  mov     rbx, rax
0x180008338  test    rax, rax
0x18000833b  jnz     short loc_180008347
0x18000833d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008342  jmp     loc_1800085E0
0x180008347  xor     r8d, r8d; bAlertable
0x18000834a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000834d  mov     rcx, rbx; hHandle
0x180008350  call    cs:__imp_WaitForSingleObjectEx
0x180008356  cmp     eax, 102h
0x18000835b  jz      short loc_18000836D
0x18000835d  test    eax, 0FFFFFF7Fh
0x180008362  jnz     loc_18000862A
0x180008368  mov     rdi, rbx
0x18000836b  jmp     short loc_18000836F
0x18000836d  xor     edi, edi
0x18000836f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008374  mov     [rsp+280h+hObject], 0
0x18000837d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008382  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008387  mov     esi, eax
0x180008389  test    eax, eax
0x18000838b  jns     short loc_18000840C
0x18000838d  mov     rcx, [rbp+188h]; this
0x180008394  lea     r8, aWil; "wil"
0x18000839b  mov     r9d, eax; char *
0x18000839e  mov     edx, 66h ; 'f'; void *
0x1800083a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083a8  mov     rcx, [rbp+188h]; this
0x1800083af  lea     r8, aWil; "wil"
0x1800083b6  mov     r9d, esi; char *
0x1800083b9  mov     edx, 6Fh ; 'o'; void *
0x1800083be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083c3  mov     rcx, [rbp+188h]; this
0x1800083ca  lea     r8, aWil; "wil"
0x1800083d1  mov     r9d, esi; char *
0x1800083d4  mov     edx, 12Eh; void *
0x1800083d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083de  test    rdi, rdi
0x1800083e1  jz      short loc_1800083F4
0x1800083e3  mov     rcx, rdi; hMutex
0x1800083e6  call    cs:__imp_ReleaseMutex
0x1800083ec  test    eax, eax
0x1800083ee  jz      loc_180008637
0x1800083f4  mov     rcx, rbx; hObject
0x1800083f7  call    cs:__imp_CloseHandle
0x1800083fd  test    eax, eax
0x1800083ff  jz      loc_180008649
0x180008405  mov     eax, esi
0x180008407  jmp     loc_1800085E0
0x18000840c  mov     rax, [rsp+280h+hObject]
0x180008411  lea     rcx, ds:0[rax*4]
0x180008419  test    rcx, rcx
0x18000841c  jz      short loc_18000842C
0x18000841e  mov     [r15], rcx
0x180008421  mov     eax, [rcx]
0x180008423  inc     eax
0x180008425  mov     [rcx], eax
0x180008427  jmp     loc_1800085B6
0x18000842c  mov     rdx, r14; dwBytes
0x18000842f  mov     qword ptr [r15], 0
0x180008436  mov     ecx, 8; dwFlags
0x18000843b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008440  mov     r14, rax
0x180008443  test    rax, rax
0x180008446  jnz     short loc_18000846D
0x180008448  mov     rcx, [rbp+188h]; this
0x18000844f  lea     r8, aWil; "wil"
0x180008456  mov     esi, 8007000Eh
0x18000845b  mov     edx, 14Bh; void *
0x180008460  mov     r9d, esi; char *
0x180008463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008468  jmp     loc_1800084FF
0x18000846d  xorps   xmm0, xmm0
0x180008470  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008476  test    r14b, 3
0x18000847a  jnz     loc_18000865B
0x180008480  mov     r9, r14
0x180008483  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008488  shr     r9, 2; unsigned __int64
0x18000848c  lea     rcx, [rsp+280h+hObject]; this
0x180008491  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008496  mov     esi, eax
0x180008498  test    eax, eax
0x18000849a  jns     loc_180008546
0x1800084a0  mov     rcx, [rbp+188h]; this
0x1800084a7  lea     r8, aWil; "wil"
0x1800084ae  mov     r9d, eax; char *
0x1800084b1  mov     edx, 14Eh; void *
0x1800084b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084bb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800084c0  test    rcx, rcx
0x1800084c3  jz      short loc_1800084D3
0x1800084c5  call    cs:__imp_CloseHandle
0x1800084cb  test    eax, eax
0x1800084cd  jz      loc_180008661
0x1800084d3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800084d8  test    rcx, rcx
0x1800084db  jz      short loc_1800084EB
0x1800084dd  call    cs:__imp_CloseHandle
0x1800084e3  test    eax, eax
0x1800084e5  jz      loc_180008673
0x1800084eb  call    cs:__imp_GetProcessHeap
0x1800084f1  mov     r8, r14; lpMem
0x1800084f4  xor     edx, edx; dwFlags
0x1800084f6  mov     rcx, rax; hHeap
0x1800084f9  call    cs:__imp_HeapFree
0x1800084ff  mov     rcx, [rbp+188h]; this
0x180008506  lea     r8, aWil; "wil"
0x18000850d  mov     r9d, esi; char *
0x180008510  mov     edx, 137h; void *
0x180008515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000851a  test    rdi, rdi
0x18000851d  jz      short loc_180008530
0x18000851f  mov     rcx, rdi; hMutex
0x180008522  call    cs:__imp_ReleaseMutex
0x180008528  test    eax, eax
0x18000852a  jz      loc_180008685
0x180008530  mov     rcx, rbx; hObject
0x180008533  call    cs:__imp_CloseHandle
0x180008539  test    eax, eax
0x18000853b  jz      loc_180008618
0x180008541  jmp     loc_180008405
0x180008546  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000854b  lea     rcx, [r14+28h]; void *
0x18000854f  mov     dword ptr [r14], 1
0x180008556  xor     edx, edx; Val
0x180008558  mov     [r14+8], rbx
0x18000855c  mov     r8d, 108h; Size
0x180008562  movdqu  xmmword ptr [r14+10h], xmm0
0x180008568  call    memset_0
0x18000856d  xor     eax, eax
0x18000856f  lea     rcx, [r14+28h]; this
0x180008573  mov     [r14+20h], rax
0x180008577  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000857c  lea     rbx, [r14+0E8h]
0x180008583  xor     r8d, r8d; Flags
0x180008586  mov     rcx, rbx; lpCriticalSection
0x180008589  xor     edx, edx; dwSpinCount
0x18000858b  call    cs:__imp_InitializeCriticalSectionEx
0x180008591  mov     qword ptr [rbx+28h], 0
0x180008599  mov     qword ptr [rbx+30h], 0
0x1800085a1  mov     qword ptr [rbx+38h], 0
0x1800085a9  mov     qword ptr [rbx+40h], 0
0x1800085b1  xor     ebx, ebx
0x1800085b3  mov     [r15], r14
0x1800085b6  test    rdi, rdi
0x1800085b9  jz      short loc_1800085CC
0x1800085bb  mov     rcx, rdi; hMutex
0x1800085be  call    cs:__imp_ReleaseMutex
0x1800085c4  test    eax, eax
0x1800085c6  jz      loc_180008697
0x1800085cc  test    rbx, rbx
0x1800085cf  jz      short loc_1800085DE
0x1800085d1  mov     rcx, rbx; hObject
0x1800085d4  call    cs:__imp_CloseHandle
0x1800085da  test    eax, eax
0x1800085dc  jz      short loc_180008606
0x1800085de  xor     eax, eax
0x1800085e0  mov     rcx, [rbp+180h+var_30]
0x1800085e7  xor     rcx, rsp; StackCookie
0x1800085ea  call    __security_check_cookie
0x1800085ef  mov     rbx, [rsp+280h+arg_10]
0x1800085f7  add     rsp, 260h
0x1800085fe  pop     r15
0x180008600  pop     r14
0x180008602  pop     rdi
0x180008603  pop     rsi
0x180008604  pop     rbp
0x180008605  retn
0x180008606  mov     rcx, [rbp+188h]; this
0x18000860d  mov     edx, 0A0Bh; void *
0x180008612  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008618  mov     rcx, [rbp+188h]; this
0x18000861f  mov     edx, 0A0Bh; void *
0x180008624  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000862a  mov     rcx, [rbp+188h]; this
0x180008631  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008637  mov     rcx, [rbp+188h]; this
0x18000863e  mov     edx, 0A15h; void *
0x180008643  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008649  mov     rcx, [rbp+188h]; this
0x180008650  mov     edx, 0A0Bh; void *
0x180008655  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000865b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008661  mov     rcx, [rbp+188h]; this
0x180008668  mov     edx, 0A0Bh; void *
0x18000866d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008673  mov     rcx, [rbp+188h]; this
0x18000867a  mov     edx, 0A0Bh; void *
0x18000867f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008685  mov     rcx, [rbp+188h]; this
0x18000868c  mov     edx, 0A15h; void *
0x180008691  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008697  mov     rcx, [rbp+188h]; this
0x18000869e  mov     edx, 0A15h; void *
0x1800086a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
