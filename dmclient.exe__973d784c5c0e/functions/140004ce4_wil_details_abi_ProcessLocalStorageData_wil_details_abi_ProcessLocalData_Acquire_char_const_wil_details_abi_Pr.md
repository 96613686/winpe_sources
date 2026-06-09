# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004ce4`
- end: `0x1400050b7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140007398`

## callees

- `0x140004a04`
- `0x140004ce4`
- `0x140005740`
- `0x140006b00`
- `0x1400070c0`
- `0x14000a98c`
- `0x14000b084`
- `0x14000b904`
- `0x14000b9ec`
- `0x14000bfd4`
- `0x1400195e2`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004d62`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004d62`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004d89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004d89`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004e29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004fe9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004e29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004f03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004f03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004f17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005005`

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
0x140004ce4  mov     [rsp-8+arg_10], rbx
0x140004ce9  push    rbp
0x140004cea  push    rsi
0x140004ceb  push    rdi
0x140004cec  push    r14
0x140004cee  push    r15
0x140004cf0  lea     rbp, [rsp-160h]
0x140004cf8  sub     rsp, 260h
0x140004cff  mov     rax, cs:__security_cookie
0x140004d06  xor     rax, rsp
0x140004d09  mov     [rbp+180h+var_30], rax
0x140004d10  mov     r15, rdx
0x140004d13  mov     qword ptr [rdx], 0
0x140004d1a  mov     rbx, rcx
0x140004d1d  call    cs:__imp_GetCurrentProcessId
0x140004d24  nop     dword ptr [rax+rax+00h]
0x140004d29  mov     r14d, 78h ; 'x'
0x140004d2f  mov     [rsp+280h+var_258], rbx
0x140004d34  mov     r9d, eax
0x140004d37  mov     [rsp+280h+var_260], r14d; int
0x140004d3c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004d43  mov     edx, 104h; unsigned __int64
0x140004d48  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004d4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004d52  mov     r9d, 1F0001h; dwDesiredAccess
0x140004d58  lea     rdx, [rsp+280h+Name]; lpName
0x140004d5d  xor     r8d, r8d; dwFlags
0x140004d60  xor     ecx, ecx; lpMutexAttributes
0x140004d62  call    cs:__imp_CreateMutexExW
0x140004d69  nop     dword ptr [rax+rax+00h]
0x140004d6e  mov     rbx, rax
0x140004d71  test    rax, rax
0x140004d74  jnz     short loc_140004D80
0x140004d76  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004d7b  jmp     loc_140005017
0x140004d80  xor     r8d, r8d; bAlertable
0x140004d83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004d86  mov     rcx, rbx; hHandle
0x140004d89  call    cs:__imp_WaitForSingleObjectEx
0x140004d90  nop     dword ptr [rax+rax+00h]
0x140004d95  cmp     eax, 102h
0x140004d9a  jz      short loc_140004DAC
0x140004d9c  test    eax, 0FFFFFF7Fh
0x140004da1  jnz     loc_140005062
0x140004da7  mov     rdi, rbx
0x140004daa  jmp     short loc_140004DAE
0x140004dac  xor     edi, edi
0x140004dae  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140004db3  mov     [rsp+280h+var_250], 0
0x140004dbc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004dc1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004dc6  mov     esi, eax
0x140004dc8  test    eax, eax
0x140004dca  jns     loc_140004E5B
0x140004dd0  mov     rcx, [rbp+188h]; this
0x140004dd7  lea     r8, aWil; "wil"
0x140004dde  mov     r9d, eax; char *
0x140004de1  mov     edx, 66h ; 'f'; void *
0x140004de6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004deb  mov     rcx, [rbp+188h]; this
0x140004df2  lea     r8, aWil; "wil"
0x140004df9  mov     r9d, esi; char *
0x140004dfc  mov     edx, 6Fh ; 'o'; void *
0x140004e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e06  mov     rcx, [rbp+188h]; this
0x140004e0d  lea     r8, aWil; "wil"
0x140004e14  mov     r9d, esi; char *
0x140004e17  mov     edx, 12Eh; void *
0x140004e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e21  test    rdi, rdi
0x140004e24  jz      short loc_140004E3D
0x140004e26  mov     rcx, rdi; hMutex
0x140004e29  call    cs:__imp_ReleaseMutex
0x140004e30  nop     dword ptr [rax+rax+00h]
0x140004e35  test    eax, eax
0x140004e37  jz      loc_14000506F
0x140004e3d  mov     rcx, rbx; hObject
0x140004e40  call    cs:__imp_CloseHandle
0x140004e47  nop     dword ptr [rax+rax+00h]
0x140004e4c  test    eax, eax
0x140004e4e  jz      loc_140005081
0x140004e54  mov     eax, esi
0x140004e56  jmp     loc_140005017
0x140004e5b  mov     rax, [rsp+280h+var_250]
0x140004e60  lea     rcx, ds:0[rax*4]
0x140004e68  test    rcx, rcx
0x140004e6b  jz      short loc_140004E7B
0x140004e6d  mov     [r15], rcx
0x140004e70  mov     eax, [rcx]
0x140004e72  inc     eax
0x140004e74  mov     [rcx], eax
0x140004e76  jmp     loc_140004FE1
0x140004e7b  mov     rdx, r14; dwBytes
0x140004e7e  mov     qword ptr [r15], 0
0x140004e85  mov     ecx, 8; dwFlags
0x140004e8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004e8f  mov     r14, rax
0x140004e92  test    rax, rax
0x140004e95  jnz     short loc_140004EB9
0x140004e97  mov     rcx, [rbp+188h]; this
0x140004e9e  lea     r8, aWil; "wil"
0x140004ea5  mov     esi, 8007000Eh
0x140004eaa  mov     edx, 14Bh; void *
0x140004eaf  mov     r9d, esi; char *
0x140004eb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004eb7  jmp     short loc_140004F23
0x140004eb9  xorps   xmm0, xmm0
0x140004ebc  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004ec1  mov     r8, r14; void *
0x140004ec4  lea     rcx, [rsp+280h+var_250]; this
0x140004ec9  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140004ecf  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140004ed4  mov     esi, eax
0x140004ed6  test    eax, eax
0x140004ed8  jns     loc_140004F76
0x140004ede  mov     rcx, [rbp+188h]; this
0x140004ee5  lea     r8, aWil; "wil"
0x140004eec  mov     r9d, eax; char *
0x140004eef  mov     edx, 14Eh; void *
0x140004ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ef9  lea     rcx, [rsp+280h+var_250]; this
0x140004efe  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140004f03  call    cs:__imp_GetProcessHeap
0x140004f0a  nop     dword ptr [rax+rax+00h]
0x140004f0f  mov     r8, r14; lpMem
0x140004f12  xor     edx, edx; dwFlags
0x140004f14  mov     rcx, rax; hHeap
0x140004f17  call    cs:__imp_HeapFree
0x140004f1e  nop     dword ptr [rax+rax+00h]
0x140004f23  mov     rcx, [rbp+188h]; this
0x140004f2a  lea     r8, aWil; "wil"
0x140004f31  mov     r9d, esi; char *
0x140004f34  mov     edx, 137h; void *
0x140004f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f3e  test    rdi, rdi
0x140004f41  jz      short loc_140004F5A
0x140004f43  mov     rcx, rdi; hMutex
0x140004f46  call    cs:__imp_ReleaseMutex
0x140004f4d  nop     dword ptr [rax+rax+00h]
0x140004f52  test    eax, eax
0x140004f54  jz      loc_140005093
0x140004f5a  mov     rcx, rbx; hObject
0x140004f5d  call    cs:__imp_CloseHandle
0x140004f64  nop     dword ptr [rax+rax+00h]
0x140004f69  test    eax, eax
0x140004f6b  jz      loc_140005050
0x140004f71  jmp     loc_140004E54
0x140004f76  mov     rax, [rsp+280h+var_250]
0x140004f7b  lea     rcx, [r14+22h]; void *
0x140004f7f  xor     edx, edx; Val
0x140004f81  mov     [r14+10h], rax
0x140004f85  mov     rax, [rsp+280h+var_250+8]
0x140004f8a  mov     dword ptr [r14], 1
0x140004f91  mov     [r14+8], rbx
0x140004f95  lea     r8d, [rdx+56h]; Size
0x140004f99  mov     [rsp+280h+var_250], 0
0x140004fa2  mov     [r14+18h], rax
0x140004fa6  mov     [rsp+280h+var_250+8], 0
0x140004faf  call    memset_0
0x140004fb4  xor     edx, edx; Val
0x140004fb6  mov     word ptr [r14+20h], 58h ; 'X'
0x140004fbd  lea     rcx, [r14+28h]; void *
0x140004fc1  mov     dword ptr [r14+24h], 1
0x140004fc9  lea     r8d, [rdx+50h]; Size
0x140004fcd  call    memset_0
0x140004fd2  lea     rcx, [rsp+280h+var_250]; this
0x140004fd7  mov     [r15], r14
0x140004fda  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140004fdf  xor     ebx, ebx
0x140004fe1  test    rdi, rdi
0x140004fe4  jz      short loc_140004FFD
0x140004fe6  mov     rcx, rdi; hMutex
0x140004fe9  call    cs:__imp_ReleaseMutex
0x140004ff0  nop     dword ptr [rax+rax+00h]
0x140004ff5  test    eax, eax
0x140004ff7  jz      loc_1400050A5
0x140004ffd  test    rbx, rbx
0x140005000  jz      short loc_140005015
0x140005002  mov     rcx, rbx; hObject
0x140005005  call    cs:__imp_CloseHandle
0x14000500c  nop     dword ptr [rax+rax+00h]
0x140005011  test    eax, eax
0x140005013  jz      short loc_14000503E
0x140005015  xor     eax, eax
0x140005017  mov     rcx, [rbp+180h+var_30]
0x14000501e  xor     rcx, rsp; StackCookie
0x140005021  call    __security_check_cookie
0x140005026  mov     rbx, [rsp+280h+arg_10]
0x14000502e  add     rsp, 260h
0x140005035  pop     r15
0x140005037  pop     r14
0x140005039  pop     rdi
0x14000503a  pop     rsi
0x14000503b  pop     rbp
0x14000503c  retn
0x14000503e  mov     rcx, [rbp+188h]; this
0x140005045  mov     edx, 0A0Bh; void *
0x14000504a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005050  mov     rcx, [rbp+188h]; this
0x140005057  mov     edx, 0A0Bh; void *
0x14000505c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005062  mov     rcx, [rbp+188h]; this
0x140005069  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000506f  mov     rcx, [rbp+188h]; this
0x140005076  mov     edx, 0A15h; void *
0x14000507b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005081  mov     rcx, [rbp+188h]; this
0x140005088  mov     edx, 0A0Bh; void *
0x14000508d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005093  mov     rcx, [rbp+188h]; this
0x14000509a  mov     edx, 0A15h; void *
0x14000509f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400050a5  mov     rcx, [rbp+188h]; this
0x1400050ac  mov     edx, 0A15h; void *
0x1400050b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
