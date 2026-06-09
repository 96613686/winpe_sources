# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008010`
- end: `0x1800083ae`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800089fc`

## callees

- `0x1800015b0`
- `0x180001fe2`
- `0x180005d40`
- `0x180007a6c`
- `0x180008010`
- `0x1800083b4`
- `0x1800085c8`
- `0x180008878`
- `0x180008c0c`
- `0x180008e58`
- `0x18000914c`
- `0x1800093c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008231`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008231`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000812a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008253`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000812a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008253`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800080a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800080a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008088`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008088`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000813b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000813b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d9`

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
0x180008010  mov     [rsp-8+arg_10], rbx
0x180008015  push    rbp
0x180008016  push    rsi
0x180008017  push    rdi
0x180008018  push    r14
0x18000801a  push    r15
0x18000801c  lea     rbp, [rsp-160h]
0x180008024  sub     rsp, 260h
0x18000802b  mov     rax, cs:__security_cookie
0x180008032  xor     rax, rsp
0x180008035  mov     [rbp+180h+var_30], rax
0x18000803c  mov     r15, rdx
0x18000803f  mov     qword ptr [rdx], 0
0x180008046  mov     rbx, rcx
0x180008049  call    cs:__imp_GetCurrentProcessId
0x18000804f  mov     r14d, 78h ; 'x'
0x180008055  mov     [rsp+280h+var_258], rbx
0x18000805a  mov     r9d, eax
0x18000805d  mov     [rsp+280h+var_260], r14d; int
0x180008062  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008069  mov     edx, 104h; unsigned __int64
0x18000806e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008073  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008078  mov     r9d, 1F0001h; dwDesiredAccess
0x18000807e  lea     rdx, [rsp+280h+Name]; lpName
0x180008083  xor     r8d, r8d; dwFlags
0x180008086  xor     ecx, ecx; lpMutexAttributes
0x180008088  call    cs:__imp_CreateMutexExW
0x18000808e  mov     rbx, rax
0x180008091  test    rax, rax
0x180008094  jnz     short loc_1800080A0
0x180008096  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000809b  jmp     loc_1800082E5
0x1800080a0  xor     r8d, r8d; bAlertable
0x1800080a3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800080a6  mov     rcx, rbx; hHandle
0x1800080a9  call    cs:__imp_WaitForSingleObjectEx
0x1800080af  cmp     eax, 102h
0x1800080b4  jz      short loc_1800080C6
0x1800080b6  test    eax, 0FFFFFF7Fh
0x1800080bb  jnz     loc_18000831D
0x1800080c1  mov     rdi, rbx
0x1800080c4  jmp     short loc_1800080C8
0x1800080c6  xor     edi, edi
0x1800080c8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800080cd  mov     [rsp+280h+hObject], 0
0x1800080d6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800080db  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800080e0  mov     esi, eax
0x1800080e2  test    eax, eax
0x1800080e4  jns     short loc_180008150
0x1800080e6  mov     rcx, [rbp+188h]; this
0x1800080ed  mov     r9d, eax; char *
0x1800080f0  mov     edx, 66h ; 'f'; void *
0x1800080f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080fa  mov     rcx, [rbp+188h]; this
0x180008101  mov     r9d, esi; char *
0x180008104  mov     edx, 6Fh ; 'o'; void *
0x180008109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000810e  mov     rcx, [rbp+188h]; this
0x180008115  mov     r9d, esi; char *
0x180008118  mov     edx, 12Eh; void *
0x18000811d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008122  test    rdi, rdi
0x180008125  jz      short loc_180008138
0x180008127  mov     rcx, rdi; hMutex
0x18000812a  call    cs:__imp_ReleaseMutex
0x180008130  test    eax, eax
0x180008132  jz      loc_18000832A
0x180008138  mov     rcx, rbx; hObject
0x18000813b  call    cs:__imp_CloseHandle
0x180008141  test    eax, eax
0x180008143  jz      loc_18000833C
0x180008149  mov     eax, esi
0x18000814b  jmp     loc_1800082E5
0x180008150  mov     rax, [rsp+280h+hObject]
0x180008155  lea     rcx, ds:0[rax*4]
0x18000815d  test    rcx, rcx
0x180008160  jz      short loc_180008170
0x180008162  mov     [r15], rcx
0x180008165  mov     eax, [rcx]
0x180008167  inc     eax
0x180008169  mov     [rcx], eax
0x18000816b  jmp     loc_1800082BB
0x180008170  mov     rdx, r14; dwBytes
0x180008173  mov     qword ptr [r15], 0
0x18000817a  mov     ecx, 8; dwFlags
0x18000817f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008184  mov     rsi, rax
0x180008187  test    rax, rax
0x18000818a  jnz     short loc_1800081AB
0x18000818c  mov     rcx, [rbp+188h]; this
0x180008193  mov     r14d, 8007000Eh
0x180008199  mov     r9d, r14d; char *
0x18000819c  mov     edx, 14Bh; void *
0x1800081a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081a6  jmp     loc_180008237
0x1800081ab  xorps   xmm0, xmm0
0x1800081ae  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800081b4  test    sil, 3
0x1800081b8  jnz     loc_18000834E
0x1800081be  mov     r9, rsi
0x1800081c1  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800081c6  shr     r9, 2; unsigned __int64
0x1800081ca  lea     rcx, [rsp+280h+hObject]; this
0x1800081cf  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800081d4  mov     r14d, eax
0x1800081d7  test    eax, eax
0x1800081d9  jns     loc_180008277
0x1800081df  mov     rcx, [rbp+188h]; this
0x1800081e6  mov     r9d, eax; char *
0x1800081e9  mov     edx, 14Eh; void *
0x1800081ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081f3  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800081f8  test    rcx, rcx
0x1800081fb  jz      short loc_18000820B
0x1800081fd  call    cs:__imp_CloseHandle
0x180008203  test    eax, eax
0x180008205  jz      loc_180008354
0x18000820b  mov     rcx, [rsp+280h+hObject]; hObject
0x180008210  test    rcx, rcx
0x180008213  jz      short loc_180008223
0x180008215  call    cs:__imp_CloseHandle
0x18000821b  test    eax, eax
0x18000821d  jz      loc_180008366
0x180008223  call    cs:__imp_GetProcessHeap
0x180008229  mov     r8, rsi; lpMem
0x18000822c  xor     edx, edx; dwFlags
0x18000822e  mov     rcx, rax; hHeap
0x180008231  call    cs:__imp_HeapFree
0x180008237  mov     rcx, [rbp+188h]; this
0x18000823e  mov     r9d, r14d; char *
0x180008241  mov     edx, 137h; void *
0x180008246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000824b  test    rdi, rdi
0x18000824e  jz      short loc_180008261
0x180008250  mov     rcx, rdi; hMutex
0x180008253  call    cs:__imp_ReleaseMutex
0x180008259  test    eax, eax
0x18000825b  jz      loc_180008378
0x180008261  mov     rcx, rbx; hObject
0x180008264  call    cs:__imp_CloseHandle
0x18000826a  test    eax, eax
0x18000826c  jz      loc_18000838A
0x180008272  mov     eax, r14d
0x180008275  jmp     short loc_1800082E5
0x180008277  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000827c  xor     edx, edx; Val
0x18000827e  mov     dword ptr [rsi], 1
0x180008284  lea     rcx, [rsi+22h]; void *
0x180008288  mov     [rsi+8], rbx
0x18000828c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008291  lea     r8d, [rdx+56h]; Size
0x180008295  call    memset_0
0x18000829a  xor     edx, edx; Val
0x18000829c  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800082a2  lea     rcx, [rsi+28h]; void *
0x1800082a6  mov     dword ptr [rsi+24h], 1
0x1800082ad  lea     r8d, [rdx+50h]; Size
0x1800082b1  call    memset_0
0x1800082b6  xor     ebx, ebx
0x1800082b8  mov     [r15], rsi
0x1800082bb  test    rdi, rdi
0x1800082be  jz      short loc_1800082D1
0x1800082c0  mov     rcx, rdi; hMutex
0x1800082c3  call    cs:__imp_ReleaseMutex
0x1800082c9  test    eax, eax
0x1800082cb  jz      loc_18000839C
0x1800082d1  test    rbx, rbx
0x1800082d4  jz      short loc_1800082E3
0x1800082d6  mov     rcx, rbx; hObject
0x1800082d9  call    cs:__imp_CloseHandle
0x1800082df  test    eax, eax
0x1800082e1  jz      short loc_18000830B
0x1800082e3  xor     eax, eax
0x1800082e5  mov     rcx, [rbp+180h+var_30]
0x1800082ec  xor     rcx, rsp; StackCookie
0x1800082ef  call    __security_check_cookie
0x1800082f4  mov     rbx, [rsp+280h+arg_10]
0x1800082fc  add     rsp, 260h
0x180008303  pop     r15
0x180008305  pop     r14
0x180008307  pop     rdi
0x180008308  pop     rsi
0x180008309  pop     rbp
0x18000830a  retn
0x18000830b  mov     rcx, [rbp+188h]; this
0x180008312  mov     edx, 0A0Bh; void *
0x180008317  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000831d  mov     rcx, [rbp+188h]; this
0x180008324  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000832a  mov     rcx, [rbp+188h]; this
0x180008331  mov     edx, 0A15h; void *
0x180008336  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000833c  mov     rcx, [rbp+188h]; this
0x180008343  mov     edx, 0A0Bh; void *
0x180008348  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000834e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008354  mov     rcx, [rbp+188h]; this
0x18000835b  mov     edx, 0A0Bh; void *
0x180008360  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008366  mov     rcx, [rbp+188h]; this
0x18000836d  mov     edx, 0A0Bh; void *
0x180008372  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008378  mov     rcx, [rbp+188h]; this
0x18000837f  mov     edx, 0A15h; void *
0x180008384  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000838a  mov     rcx, [rbp+188h]; this
0x180008391  mov     edx, 0A0Bh; void *
0x180008396  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000839c  mov     rcx, [rbp+188h]; this
0x1800083a3  mov     edx, 0A15h; void *
0x1800083a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
