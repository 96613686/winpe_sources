# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003de0`
- end: `0x1400041a8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140005790`

## callees

- `0x140001ebf`
- `0x140003de0`
- `0x140004d58`
- `0x140004fa0`
- `0x140005528`
- `0x140007288`
- `0x140007734`
- `0x140008134`
- `0x14000820c`
- `0x1400087f4`
- `0x140008804`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003f0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000404d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003f0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000404d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003e58`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003e58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003e19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ff0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ff0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040d3`

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
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x140003de0  mov     [rsp-8+arg_10], rbx
0x140003de5  push    rbp
0x140003de6  push    rsi
0x140003de7  push    rdi
0x140003de8  push    r14
0x140003dea  push    r15
0x140003dec  lea     rbp, [rsp-160h]
0x140003df4  sub     rsp, 260h
0x140003dfb  mov     rax, cs:__security_cookie
0x140003e02  xor     rax, rsp
0x140003e05  mov     [rbp+180h+var_30], rax
0x140003e0c  mov     r15, rdx
0x140003e0f  mov     qword ptr [rdx], 0
0x140003e16  mov     rbx, rcx
0x140003e19  call    cs:__imp_GetCurrentProcessId
0x140003e1f  mov     r14d, 78h ; 'x'
0x140003e25  mov     [rsp+280h+var_258], rbx
0x140003e2a  mov     r9d, eax
0x140003e2d  mov     [rsp+280h+var_260], r14d; int
0x140003e32  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003e39  mov     edx, 104h; unsigned __int64
0x140003e3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003e43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003e48  mov     r9d, 1F0001h; dwDesiredAccess
0x140003e4e  lea     rdx, [rsp+280h+Name]; lpName
0x140003e53  xor     r8d, r8d; dwFlags
0x140003e56  xor     ecx, ecx; lpMutexAttributes
0x140003e58  call    cs:__imp_CreateMutexExW
0x140003e5e  mov     rbx, rax
0x140003e61  test    rax, rax
0x140003e64  jnz     short loc_140003E70
0x140003e66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003e6b  jmp     loc_1400040DF
0x140003e70  xor     r8d, r8d; bAlertable
0x140003e73  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003e76  mov     rcx, rbx; hHandle
0x140003e79  call    cs:__imp_WaitForSingleObjectEx
0x140003e7f  cmp     eax, 102h
0x140003e84  jz      short loc_140003E96
0x140003e86  test    eax, 0FFFFFF7Fh
0x140003e8b  jnz     loc_140004117
0x140003e91  mov     rdi, rbx
0x140003e94  jmp     short loc_140003E98
0x140003e96  xor     edi, edi
0x140003e98  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003e9d  mov     [rsp+280h+hObject], 0
0x140003ea6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003eab  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003eb0  mov     esi, eax
0x140003eb2  test    eax, eax
0x140003eb4  jns     short loc_140003F35
0x140003eb6  mov     rcx, [rbp+188h]; this
0x140003ebd  lea     r8, aWil; "wil"
0x140003ec4  mov     r9d, eax; char *
0x140003ec7  mov     edx, 66h ; 'f'; void *
0x140003ecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ed1  mov     rcx, [rbp+188h]; this
0x140003ed8  lea     r8, aWil; "wil"
0x140003edf  mov     r9d, esi; char *
0x140003ee2  mov     edx, 6Fh ; 'o'; void *
0x140003ee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003eec  mov     rcx, [rbp+188h]; this
0x140003ef3  lea     r8, aWil; "wil"
0x140003efa  mov     r9d, esi; char *
0x140003efd  mov     edx, 12Eh; void *
0x140003f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f07  test    rdi, rdi
0x140003f0a  jz      short loc_140003F1D
0x140003f0c  mov     rcx, rdi; hMutex
0x140003f0f  call    cs:__imp_ReleaseMutex
0x140003f15  test    eax, eax
0x140003f17  jz      loc_140004124
0x140003f1d  mov     rcx, rbx; hObject
0x140003f20  call    cs:__imp_CloseHandle
0x140003f26  test    eax, eax
0x140003f28  jz      loc_140004136
0x140003f2e  mov     eax, esi
0x140003f30  jmp     loc_1400040DF
0x140003f35  mov     rax, [rsp+280h+hObject]
0x140003f3a  lea     rcx, ds:0[rax*4]
0x140003f42  test    rcx, rcx
0x140003f45  jz      short loc_140003F55
0x140003f47  mov     [r15], rcx
0x140003f4a  mov     eax, [rcx]
0x140003f4c  inc     eax
0x140003f4e  mov     [rcx], eax
0x140003f50  jmp     loc_1400040B5
0x140003f55  mov     rdx, r14; dwBytes
0x140003f58  mov     qword ptr [r15], 0
0x140003f5f  mov     ecx, 8; dwFlags
0x140003f64  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003f69  mov     rsi, rax
0x140003f6c  test    rax, rax
0x140003f6f  jnz     short loc_140003F97
0x140003f71  mov     rcx, [rbp+188h]; this
0x140003f78  lea     r8, aWil; "wil"
0x140003f7f  mov     r14d, 8007000Eh
0x140003f85  mov     edx, 14Bh; void *
0x140003f8a  mov     r9d, r14d; char *
0x140003f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f92  jmp     loc_14000402A
0x140003f97  xorps   xmm0, xmm0
0x140003f9a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003fa0  test    sil, 3
0x140003fa4  jnz     loc_140004148
0x140003faa  mov     r9, rsi
0x140003fad  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003fb2  shr     r9, 2; unsigned __int64
0x140003fb6  lea     rcx, [rsp+280h+hObject]; this
0x140003fbb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003fc0  mov     r14d, eax
0x140003fc3  test    eax, eax
0x140003fc5  jns     loc_140004071
0x140003fcb  mov     rcx, [rbp+188h]; this
0x140003fd2  lea     r8, aWil; "wil"
0x140003fd9  mov     r9d, eax; char *
0x140003fdc  mov     edx, 14Eh; void *
0x140003fe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fe6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003feb  test    rcx, rcx
0x140003fee  jz      short loc_140003FFE
0x140003ff0  call    cs:__imp_CloseHandle
0x140003ff6  test    eax, eax
0x140003ff8  jz      loc_14000414E
0x140003ffe  mov     rcx, [rsp+280h+hObject]; hObject
0x140004003  test    rcx, rcx
0x140004006  jz      short loc_140004016
0x140004008  call    cs:__imp_CloseHandle
0x14000400e  test    eax, eax
0x140004010  jz      loc_140004160
0x140004016  call    cs:__imp_GetProcessHeap
0x14000401c  mov     r8, rsi; lpMem
0x14000401f  xor     edx, edx; dwFlags
0x140004021  mov     rcx, rax; hHeap
0x140004024  call    cs:__imp_HeapFree
0x14000402a  mov     rcx, [rbp+188h]; this
0x140004031  lea     r8, aWil; "wil"
0x140004038  mov     r9d, r14d; char *
0x14000403b  mov     edx, 137h; void *
0x140004040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004045  test    rdi, rdi
0x140004048  jz      short loc_14000405B
0x14000404a  mov     rcx, rdi; hMutex
0x14000404d  call    cs:__imp_ReleaseMutex
0x140004053  test    eax, eax
0x140004055  jz      loc_140004172
0x14000405b  mov     rcx, rbx; hObject
0x14000405e  call    cs:__imp_CloseHandle
0x140004064  test    eax, eax
0x140004066  jz      loc_140004184
0x14000406c  mov     eax, r14d
0x14000406f  jmp     short loc_1400040DF
0x140004071  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004076  xor     edx, edx; Val
0x140004078  mov     dword ptr [rsi], 1
0x14000407e  lea     rcx, [rsi+22h]; void *
0x140004082  mov     [rsi+8], rbx
0x140004086  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000408b  lea     r8d, [rdx+56h]; Size
0x14000408f  call    memset_0
0x140004094  xor     edx, edx; Val
0x140004096  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000409c  lea     rcx, [rsi+28h]; void *
0x1400040a0  mov     dword ptr [rsi+24h], 1
0x1400040a7  lea     r8d, [rdx+50h]; Size
0x1400040ab  call    memset_0
0x1400040b0  xor     ebx, ebx
0x1400040b2  mov     [r15], rsi
0x1400040b5  test    rdi, rdi
0x1400040b8  jz      short loc_1400040CB
0x1400040ba  mov     rcx, rdi; hMutex
0x1400040bd  call    cs:__imp_ReleaseMutex
0x1400040c3  test    eax, eax
0x1400040c5  jz      loc_140004196
0x1400040cb  test    rbx, rbx
0x1400040ce  jz      short loc_1400040DD
0x1400040d0  mov     rcx, rbx; hObject
0x1400040d3  call    cs:__imp_CloseHandle
0x1400040d9  test    eax, eax
0x1400040db  jz      short loc_140004105
0x1400040dd  xor     eax, eax
0x1400040df  mov     rcx, [rbp+180h+var_30]
0x1400040e6  xor     rcx, rsp; StackCookie
0x1400040e9  call    __security_check_cookie
0x1400040ee  mov     rbx, [rsp+280h+arg_10]
0x1400040f6  add     rsp, 260h
0x1400040fd  pop     r15
0x1400040ff  pop     r14
0x140004101  pop     rdi
0x140004102  pop     rsi
0x140004103  pop     rbp
0x140004104  retn
0x140004105  mov     rcx, [rbp+188h]; this
0x14000410c  mov     edx, 0A0Bh; void *
0x140004111  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004117  mov     rcx, [rbp+188h]; this
0x14000411e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004124  mov     rcx, [rbp+188h]; this
0x14000412b  mov     edx, 0A15h; void *
0x140004130  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004136  mov     rcx, [rbp+188h]; this
0x14000413d  mov     edx, 0A0Bh; void *
0x140004142  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004148  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000414e  mov     rcx, [rbp+188h]; this
0x140004155  mov     edx, 0A0Bh; void *
0x14000415a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004160  mov     rcx, [rbp+188h]; this
0x140004167  mov     edx, 0A0Bh; void *
0x14000416c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004172  mov     rcx, [rbp+188h]; this
0x140004179  mov     edx, 0A15h; void *
0x14000417e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004184  mov     rcx, [rbp+188h]; this
0x14000418b  mov     edx, 0A0Bh; void *
0x140004190  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004196  mov     rcx, [rbp+188h]; this
0x14000419d  mov     edx, 0A15h; void *
0x1400041a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
