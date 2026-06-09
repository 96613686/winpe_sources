# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004668`
- end: `0x140004a06`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140006410`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140004668`
- `0x140004ddc`
- `0x1400052f8`
- `0x1400061a8`
- `0x140006e88`
- `0x1400088f4`
- `0x1400093e8`
- `0x14000986c`
- `0x14000a11c`
- `0x14000a12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004782`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400048ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000491b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004782`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400048ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000491b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004701`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004701`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400046e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400046e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000487b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000487b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004889`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000486d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400048bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000486d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400048bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004931`

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
0x140004668  mov     [rsp-8+arg_10], rbx
0x14000466d  push    rbp
0x14000466e  push    rsi
0x14000466f  push    rdi
0x140004670  push    r14
0x140004672  push    r15
0x140004674  lea     rbp, [rsp-160h]
0x14000467c  sub     rsp, 260h
0x140004683  mov     rax, cs:__security_cookie
0x14000468a  xor     rax, rsp
0x14000468d  mov     [rbp+180h+var_30], rax
0x140004694  mov     r15, rdx
0x140004697  mov     qword ptr [rdx], 0
0x14000469e  mov     rbx, rcx
0x1400046a1  call    cs:__imp_GetCurrentProcessId
0x1400046a7  mov     r14d, 78h ; 'x'
0x1400046ad  mov     [rsp+280h+var_258], rbx
0x1400046b2  mov     r9d, eax
0x1400046b5  mov     [rsp+280h+var_260], r14d; int
0x1400046ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400046c1  mov     edx, 104h; unsigned __int64
0x1400046c6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400046cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400046d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400046d6  lea     rdx, [rsp+280h+Name]; lpName
0x1400046db  xor     r8d, r8d; dwFlags
0x1400046de  xor     ecx, ecx; lpMutexAttributes
0x1400046e0  call    cs:__imp_CreateMutexExW
0x1400046e6  mov     rbx, rax
0x1400046e9  test    rax, rax
0x1400046ec  jnz     short loc_1400046F8
0x1400046ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400046f3  jmp     loc_14000493D
0x1400046f8  xor     r8d, r8d; bAlertable
0x1400046fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400046fe  mov     rcx, rbx; hHandle
0x140004701  call    cs:__imp_WaitForSingleObjectEx
0x140004707  cmp     eax, 102h
0x14000470c  jz      short loc_14000471E
0x14000470e  test    eax, 0FFFFFF7Fh
0x140004713  jnz     loc_140004975
0x140004719  mov     rdi, rbx
0x14000471c  jmp     short loc_140004720
0x14000471e  xor     edi, edi
0x140004720  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004725  mov     [rsp+280h+hObject], 0
0x14000472e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004733  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004738  mov     esi, eax
0x14000473a  test    eax, eax
0x14000473c  jns     short loc_1400047A8
0x14000473e  mov     rcx, [rbp+188h]; this
0x140004745  mov     r9d, eax; char *
0x140004748  mov     edx, 66h ; 'f'; void *
0x14000474d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004752  mov     rcx, [rbp+188h]; this
0x140004759  mov     r9d, esi; char *
0x14000475c  mov     edx, 6Fh ; 'o'; void *
0x140004761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004766  mov     rcx, [rbp+188h]; this
0x14000476d  mov     r9d, esi; char *
0x140004770  mov     edx, 12Eh; void *
0x140004775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000477a  test    rdi, rdi
0x14000477d  jz      short loc_140004790
0x14000477f  mov     rcx, rdi; hMutex
0x140004782  call    cs:__imp_ReleaseMutex
0x140004788  test    eax, eax
0x14000478a  jz      loc_140004982
0x140004790  mov     rcx, rbx; hObject
0x140004793  call    cs:__imp_CloseHandle
0x140004799  test    eax, eax
0x14000479b  jz      loc_140004994
0x1400047a1  mov     eax, esi
0x1400047a3  jmp     loc_14000493D
0x1400047a8  mov     rax, [rsp+280h+hObject]
0x1400047ad  lea     rcx, ds:0[rax*4]
0x1400047b5  test    rcx, rcx
0x1400047b8  jz      short loc_1400047C8
0x1400047ba  mov     [r15], rcx
0x1400047bd  mov     eax, [rcx]
0x1400047bf  inc     eax
0x1400047c1  mov     [rcx], eax
0x1400047c3  jmp     loc_140004913
0x1400047c8  mov     rdx, r14; dwBytes
0x1400047cb  mov     qword ptr [r15], 0
0x1400047d2  mov     ecx, 8; dwFlags
0x1400047d7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400047dc  mov     rsi, rax
0x1400047df  test    rax, rax
0x1400047e2  jnz     short loc_140004803
0x1400047e4  mov     rcx, [rbp+188h]; this
0x1400047eb  mov     r14d, 8007000Eh
0x1400047f1  mov     r9d, r14d; char *
0x1400047f4  mov     edx, 14Bh; void *
0x1400047f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400047fe  jmp     loc_14000488F
0x140004803  xorps   xmm0, xmm0
0x140004806  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000480c  test    sil, 3
0x140004810  jnz     loc_1400049A6
0x140004816  mov     r9, rsi
0x140004819  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000481e  shr     r9, 2; unsigned __int64
0x140004822  lea     rcx, [rsp+280h+hObject]; this
0x140004827  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000482c  mov     r14d, eax
0x14000482f  test    eax, eax
0x140004831  jns     loc_1400048CF
0x140004837  mov     rcx, [rbp+188h]; this
0x14000483e  mov     r9d, eax; char *
0x140004841  mov     edx, 14Eh; void *
0x140004846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000484b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004850  test    rcx, rcx
0x140004853  jz      short loc_140004863
0x140004855  call    cs:__imp_CloseHandle
0x14000485b  test    eax, eax
0x14000485d  jz      loc_1400049AC
0x140004863  mov     rcx, [rsp+280h+hObject]; hObject
0x140004868  test    rcx, rcx
0x14000486b  jz      short loc_14000487B
0x14000486d  call    cs:__imp_CloseHandle
0x140004873  test    eax, eax
0x140004875  jz      loc_1400049BE
0x14000487b  call    cs:__imp_GetProcessHeap
0x140004881  mov     r8, rsi; lpMem
0x140004884  xor     edx, edx; dwFlags
0x140004886  mov     rcx, rax; hHeap
0x140004889  call    cs:__imp_HeapFree
0x14000488f  mov     rcx, [rbp+188h]; this
0x140004896  mov     r9d, r14d; char *
0x140004899  mov     edx, 137h; void *
0x14000489e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400048a3  test    rdi, rdi
0x1400048a6  jz      short loc_1400048B9
0x1400048a8  mov     rcx, rdi; hMutex
0x1400048ab  call    cs:__imp_ReleaseMutex
0x1400048b1  test    eax, eax
0x1400048b3  jz      loc_1400049D0
0x1400048b9  mov     rcx, rbx; hObject
0x1400048bc  call    cs:__imp_CloseHandle
0x1400048c2  test    eax, eax
0x1400048c4  jz      loc_1400049E2
0x1400048ca  mov     eax, r14d
0x1400048cd  jmp     short loc_14000493D
0x1400048cf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400048d4  xor     edx, edx; Val
0x1400048d6  mov     dword ptr [rsi], 1
0x1400048dc  lea     rcx, [rsi+22h]; void *
0x1400048e0  mov     [rsi+8], rbx
0x1400048e4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400048e9  lea     r8d, [rdx+56h]; Size
0x1400048ed  call    memset_0
0x1400048f2  xor     edx, edx; Val
0x1400048f4  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400048fa  lea     rcx, [rsi+28h]; void *
0x1400048fe  mov     dword ptr [rsi+24h], 1
0x140004905  lea     r8d, [rdx+50h]; Size
0x140004909  call    memset_0
0x14000490e  xor     ebx, ebx
0x140004910  mov     [r15], rsi
0x140004913  test    rdi, rdi
0x140004916  jz      short loc_140004929
0x140004918  mov     rcx, rdi; hMutex
0x14000491b  call    cs:__imp_ReleaseMutex
0x140004921  test    eax, eax
0x140004923  jz      loc_1400049F4
0x140004929  test    rbx, rbx
0x14000492c  jz      short loc_14000493B
0x14000492e  mov     rcx, rbx; hObject
0x140004931  call    cs:__imp_CloseHandle
0x140004937  test    eax, eax
0x140004939  jz      short loc_140004963
0x14000493b  xor     eax, eax
0x14000493d  mov     rcx, [rbp+180h+var_30]
0x140004944  xor     rcx, rsp; StackCookie
0x140004947  call    __security_check_cookie
0x14000494c  mov     rbx, [rsp+280h+arg_10]
0x140004954  add     rsp, 260h
0x14000495b  pop     r15
0x14000495d  pop     r14
0x14000495f  pop     rdi
0x140004960  pop     rsi
0x140004961  pop     rbp
0x140004962  retn
0x140004963  mov     rcx, [rbp+188h]; this
0x14000496a  mov     edx, 0A0Bh; void *
0x14000496f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004975  mov     rcx, [rbp+188h]; this
0x14000497c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004982  mov     rcx, [rbp+188h]; this
0x140004989  mov     edx, 0A15h; void *
0x14000498e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004994  mov     rcx, [rbp+188h]; this
0x14000499b  mov     edx, 0A0Bh; void *
0x1400049a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400049a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400049ac  mov     rcx, [rbp+188h]; this
0x1400049b3  mov     edx, 0A0Bh; void *
0x1400049b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400049be  mov     rcx, [rbp+188h]; this
0x1400049c5  mov     edx, 0A0Bh; void *
0x1400049ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400049d0  mov     rcx, [rbp+188h]; this
0x1400049d7  mov     edx, 0A15h; void *
0x1400049dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400049e2  mov     rcx, [rbp+188h]; this
0x1400049e9  mov     edx, 0A0Bh; void *
0x1400049ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400049f4  mov     rcx, [rbp+188h]; this
0x1400049fb  mov     edx, 0A15h; void *
0x140004a00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
