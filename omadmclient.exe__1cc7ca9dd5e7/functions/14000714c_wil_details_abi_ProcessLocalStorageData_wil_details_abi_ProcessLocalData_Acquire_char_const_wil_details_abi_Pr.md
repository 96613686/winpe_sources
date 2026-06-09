# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000714c`
- end: `0x14000751f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140008c24`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x140006d78`
- `0x14000714c`
- `0x1400079a4`
- `0x140007e34`
- `0x1400089a8`
- `0x1400097c8`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14000c4bc`
- `0x14000ce7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007291`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400073ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007451`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007291`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400073ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007451`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400071f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400071f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400071ca`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400071ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000736b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000736b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000737f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000737f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400073c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000746d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400073c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000746d`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x14000714c  mov     [rsp-8+arg_10], rbx
0x140007151  push    rbp
0x140007152  push    rsi
0x140007153  push    rdi
0x140007154  push    r14
0x140007156  push    r15
0x140007158  lea     rbp, [rsp-160h]
0x140007160  sub     rsp, 260h
0x140007167  mov     rax, cs:__security_cookie
0x14000716e  xor     rax, rsp
0x140007171  mov     [rbp+180h+var_30], rax
0x140007178  mov     r15, rdx
0x14000717b  mov     qword ptr [rdx], 0
0x140007182  mov     rbx, rcx
0x140007185  call    cs:__imp_GetCurrentProcessId
0x14000718c  nop     dword ptr [rax+rax+00h]
0x140007191  mov     r14d, 78h ; 'x'
0x140007197  mov     [rsp+280h+var_258], rbx
0x14000719c  mov     r9d, eax
0x14000719f  mov     [rsp+280h+var_260], r14d; int
0x1400071a4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400071ab  mov     edx, 104h; unsigned __int64
0x1400071b0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400071b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400071ba  mov     r9d, 1F0001h; dwDesiredAccess
0x1400071c0  lea     rdx, [rsp+280h+Name]; lpName
0x1400071c5  xor     r8d, r8d; dwFlags
0x1400071c8  xor     ecx, ecx; lpMutexAttributes
0x1400071ca  call    cs:__imp_CreateMutexExW
0x1400071d1  nop     dword ptr [rax+rax+00h]
0x1400071d6  mov     rbx, rax
0x1400071d9  test    rax, rax
0x1400071dc  jnz     short loc_1400071E8
0x1400071de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400071e3  jmp     loc_14000747F
0x1400071e8  xor     r8d, r8d; bAlertable
0x1400071eb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400071ee  mov     rcx, rbx; hHandle
0x1400071f1  call    cs:__imp_WaitForSingleObjectEx
0x1400071f8  nop     dword ptr [rax+rax+00h]
0x1400071fd  cmp     eax, 102h
0x140007202  jz      short loc_140007214
0x140007204  test    eax, 0FFFFFF7Fh
0x140007209  jnz     loc_1400074CA
0x14000720f  mov     rdi, rbx
0x140007212  jmp     short loc_140007216
0x140007214  xor     edi, edi
0x140007216  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14000721b  mov     [rsp+280h+var_250], 0
0x140007224  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007229  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000722e  mov     esi, eax
0x140007230  test    eax, eax
0x140007232  jns     loc_1400072C3
0x140007238  mov     rcx, [rbp+188h]; this
0x14000723f  lea     r8, aWil; "wil"
0x140007246  mov     r9d, eax; char *
0x140007249  mov     edx, 66h ; 'f'; void *
0x14000724e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007253  mov     rcx, [rbp+188h]; this
0x14000725a  lea     r8, aWil; "wil"
0x140007261  mov     r9d, esi; char *
0x140007264  mov     edx, 6Fh ; 'o'; void *
0x140007269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000726e  mov     rcx, [rbp+188h]; this
0x140007275  lea     r8, aWil; "wil"
0x14000727c  mov     r9d, esi; char *
0x14000727f  mov     edx, 12Eh; void *
0x140007284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007289  test    rdi, rdi
0x14000728c  jz      short loc_1400072A5
0x14000728e  mov     rcx, rdi; hMutex
0x140007291  call    cs:__imp_ReleaseMutex
0x140007298  nop     dword ptr [rax+rax+00h]
0x14000729d  test    eax, eax
0x14000729f  jz      loc_1400074D7
0x1400072a5  mov     rcx, rbx; hObject
0x1400072a8  call    cs:__imp_CloseHandle
0x1400072af  nop     dword ptr [rax+rax+00h]
0x1400072b4  test    eax, eax
0x1400072b6  jz      loc_1400074E9
0x1400072bc  mov     eax, esi
0x1400072be  jmp     loc_14000747F
0x1400072c3  mov     rax, [rsp+280h+var_250]
0x1400072c8  lea     rcx, ds:0[rax*4]
0x1400072d0  test    rcx, rcx
0x1400072d3  jz      short loc_1400072E3
0x1400072d5  mov     [r15], rcx
0x1400072d8  mov     eax, [rcx]
0x1400072da  inc     eax
0x1400072dc  mov     [rcx], eax
0x1400072de  jmp     loc_140007449
0x1400072e3  mov     rdx, r14; dwBytes
0x1400072e6  mov     qword ptr [r15], 0
0x1400072ed  mov     ecx, 8; dwFlags
0x1400072f2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400072f7  mov     r14, rax
0x1400072fa  test    rax, rax
0x1400072fd  jnz     short loc_140007321
0x1400072ff  mov     rcx, [rbp+188h]; this
0x140007306  lea     r8, aWil; "wil"
0x14000730d  mov     esi, 8007000Eh
0x140007312  mov     edx, 14Bh; void *
0x140007317  mov     r9d, esi; char *
0x14000731a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000731f  jmp     short loc_14000738B
0x140007321  xorps   xmm0, xmm0
0x140007324  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140007329  mov     r8, r14; void *
0x14000732c  lea     rcx, [rsp+280h+var_250]; this
0x140007331  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140007337  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x14000733c  mov     esi, eax
0x14000733e  test    eax, eax
0x140007340  jns     loc_1400073DE
0x140007346  mov     rcx, [rbp+188h]; this
0x14000734d  lea     r8, aWil; "wil"
0x140007354  mov     r9d, eax; char *
0x140007357  mov     edx, 14Eh; void *
0x14000735c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007361  lea     rcx, [rsp+280h+var_250]; this
0x140007366  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000736b  call    cs:__imp_GetProcessHeap
0x140007372  nop     dword ptr [rax+rax+00h]
0x140007377  mov     r8, r14; lpMem
0x14000737a  xor     edx, edx; dwFlags
0x14000737c  mov     rcx, rax; hHeap
0x14000737f  call    cs:__imp_HeapFree
0x140007386  nop     dword ptr [rax+rax+00h]
0x14000738b  mov     rcx, [rbp+188h]; this
0x140007392  lea     r8, aWil; "wil"
0x140007399  mov     r9d, esi; char *
0x14000739c  mov     edx, 137h; void *
0x1400073a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400073a6  test    rdi, rdi
0x1400073a9  jz      short loc_1400073C2
0x1400073ab  mov     rcx, rdi; hMutex
0x1400073ae  call    cs:__imp_ReleaseMutex
0x1400073b5  nop     dword ptr [rax+rax+00h]
0x1400073ba  test    eax, eax
0x1400073bc  jz      loc_1400074FB
0x1400073c2  mov     rcx, rbx; hObject
0x1400073c5  call    cs:__imp_CloseHandle
0x1400073cc  nop     dword ptr [rax+rax+00h]
0x1400073d1  test    eax, eax
0x1400073d3  jz      loc_1400074B8
0x1400073d9  jmp     loc_1400072BC
0x1400073de  mov     rax, [rsp+280h+var_250]
0x1400073e3  lea     rcx, [r14+22h]; void *
0x1400073e7  xor     edx, edx; Val
0x1400073e9  mov     [r14+10h], rax
0x1400073ed  mov     rax, [rsp+280h+var_250+8]
0x1400073f2  mov     dword ptr [r14], 1
0x1400073f9  mov     [r14+8], rbx
0x1400073fd  lea     r8d, [rdx+56h]; Size
0x140007401  mov     [rsp+280h+var_250], 0
0x14000740a  mov     [r14+18h], rax
0x14000740e  mov     [rsp+280h+var_250+8], 0
0x140007417  call    memset_0
0x14000741c  xor     edx, edx; Val
0x14000741e  mov     word ptr [r14+20h], 58h ; 'X'
0x140007425  lea     rcx, [r14+28h]; void *
0x140007429  mov     dword ptr [r14+24h], 1
0x140007431  lea     r8d, [rdx+50h]; Size
0x140007435  call    memset_0
0x14000743a  lea     rcx, [rsp+280h+var_250]; this
0x14000743f  mov     [r15], r14
0x140007442  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140007447  xor     ebx, ebx
0x140007449  test    rdi, rdi
0x14000744c  jz      short loc_140007465
0x14000744e  mov     rcx, rdi; hMutex
0x140007451  call    cs:__imp_ReleaseMutex
0x140007458  nop     dword ptr [rax+rax+00h]
0x14000745d  test    eax, eax
0x14000745f  jz      loc_14000750D
0x140007465  test    rbx, rbx
0x140007468  jz      short loc_14000747D
0x14000746a  mov     rcx, rbx; hObject
0x14000746d  call    cs:__imp_CloseHandle
0x140007474  nop     dword ptr [rax+rax+00h]
0x140007479  test    eax, eax
0x14000747b  jz      short loc_1400074A6
0x14000747d  xor     eax, eax
0x14000747f  mov     rcx, [rbp+180h+var_30]
0x140007486  xor     rcx, rsp; StackCookie
0x140007489  call    __security_check_cookie
0x14000748e  mov     rbx, [rsp+280h+arg_10]
0x140007496  add     rsp, 260h
0x14000749d  pop     r15
0x14000749f  pop     r14
0x1400074a1  pop     rdi
0x1400074a2  pop     rsi
0x1400074a3  pop     rbp
0x1400074a4  retn
0x1400074a6  mov     rcx, [rbp+188h]; this
0x1400074ad  mov     edx, 0A0Bh; void *
0x1400074b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400074b8  mov     rcx, [rbp+188h]; this
0x1400074bf  mov     edx, 0A0Bh; void *
0x1400074c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400074ca  mov     rcx, [rbp+188h]; this
0x1400074d1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400074d7  mov     rcx, [rbp+188h]; this
0x1400074de  mov     edx, 0A15h; void *
0x1400074e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400074e9  mov     rcx, [rbp+188h]; this
0x1400074f0  mov     edx, 0A0Bh; void *
0x1400074f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400074fb  mov     rcx, [rbp+188h]; this
0x140007502  mov     edx, 0A15h; void *
0x140007507  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000750d  mov     rcx, [rbp+188h]; this
0x140007514  mov     edx, 0A15h; void *
0x140007519  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
