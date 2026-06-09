# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800050b8`
- end: `0x180005480`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006950`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x1800050b8`
- `0x180005880`
- `0x180005db8`
- `0x1800066e8`
- `0x1800073c8`
- `0x180008b94`
- `0x180009688`
- `0x180009b0c`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005130`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005130`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005151`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005151`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005325`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005395`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005325`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005395`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ab`

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
0x1800050b8  mov     [rsp-8+arg_10], rbx
0x1800050bd  push    rbp
0x1800050be  push    rsi
0x1800050bf  push    rdi
0x1800050c0  push    r14
0x1800050c2  push    r15
0x1800050c4  lea     rbp, [rsp-160h]
0x1800050cc  sub     rsp, 260h
0x1800050d3  mov     rax, cs:__security_cookie
0x1800050da  xor     rax, rsp
0x1800050dd  mov     [rbp+180h+var_30], rax
0x1800050e4  mov     r15, rdx
0x1800050e7  mov     qword ptr [rdx], 0
0x1800050ee  mov     rbx, rcx
0x1800050f1  call    cs:__imp_GetCurrentProcessId
0x1800050f7  mov     r14d, 78h ; 'x'
0x1800050fd  mov     [rsp+280h+var_258], rbx
0x180005102  mov     r9d, eax
0x180005105  mov     [rsp+280h+var_260], r14d; int
0x18000510a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005111  mov     edx, 104h; unsigned __int64
0x180005116  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000511b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005120  mov     r9d, 1F0001h; dwDesiredAccess
0x180005126  lea     rdx, [rsp+280h+Name]; lpName
0x18000512b  xor     r8d, r8d; dwFlags
0x18000512e  xor     ecx, ecx; lpMutexAttributes
0x180005130  call    cs:__imp_CreateMutexExW
0x180005136  mov     rbx, rax
0x180005139  test    rax, rax
0x18000513c  jnz     short loc_180005148
0x18000513e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005143  jmp     loc_1800053B7
0x180005148  xor     r8d, r8d; bAlertable
0x18000514b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000514e  mov     rcx, rbx; hHandle
0x180005151  call    cs:__imp_WaitForSingleObjectEx
0x180005157  cmp     eax, 102h
0x18000515c  jz      short loc_18000516E
0x18000515e  test    eax, 0FFFFFF7Fh
0x180005163  jnz     loc_1800053EF
0x180005169  mov     rdi, rbx
0x18000516c  jmp     short loc_180005170
0x18000516e  xor     edi, edi
0x180005170  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005175  mov     [rsp+280h+hObject], 0
0x18000517e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005183  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005188  mov     esi, eax
0x18000518a  test    eax, eax
0x18000518c  jns     short loc_18000520D
0x18000518e  mov     rcx, [rbp+188h]; this
0x180005195  lea     r8, aWil; "wil"
0x18000519c  mov     r9d, eax; char *
0x18000519f  mov     edx, 66h ; 'f'; void *
0x1800051a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051a9  mov     rcx, [rbp+188h]; this
0x1800051b0  lea     r8, aWil; "wil"
0x1800051b7  mov     r9d, esi; char *
0x1800051ba  mov     edx, 6Fh ; 'o'; void *
0x1800051bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051c4  mov     rcx, [rbp+188h]; this
0x1800051cb  lea     r8, aWil; "wil"
0x1800051d2  mov     r9d, esi; char *
0x1800051d5  mov     edx, 12Eh; void *
0x1800051da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051df  test    rdi, rdi
0x1800051e2  jz      short loc_1800051F5
0x1800051e4  mov     rcx, rdi; hMutex
0x1800051e7  call    cs:__imp_ReleaseMutex
0x1800051ed  test    eax, eax
0x1800051ef  jz      loc_1800053FC
0x1800051f5  mov     rcx, rbx; hObject
0x1800051f8  call    cs:__imp_CloseHandle
0x1800051fe  test    eax, eax
0x180005200  jz      loc_18000540E
0x180005206  mov     eax, esi
0x180005208  jmp     loc_1800053B7
0x18000520d  mov     rax, [rsp+280h+hObject]
0x180005212  lea     rcx, ds:0[rax*4]
0x18000521a  test    rcx, rcx
0x18000521d  jz      short loc_18000522D
0x18000521f  mov     [r15], rcx
0x180005222  mov     eax, [rcx]
0x180005224  inc     eax
0x180005226  mov     [rcx], eax
0x180005228  jmp     loc_18000538D
0x18000522d  mov     rdx, r14; dwBytes
0x180005230  mov     qword ptr [r15], 0
0x180005237  mov     ecx, 8; dwFlags
0x18000523c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005241  mov     rsi, rax
0x180005244  test    rax, rax
0x180005247  jnz     short loc_18000526F
0x180005249  mov     rcx, [rbp+188h]; this
0x180005250  lea     r8, aWil; "wil"
0x180005257  mov     r14d, 8007000Eh
0x18000525d  mov     edx, 14Bh; void *
0x180005262  mov     r9d, r14d; char *
0x180005265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000526a  jmp     loc_180005302
0x18000526f  xorps   xmm0, xmm0
0x180005272  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005278  test    sil, 3
0x18000527c  jnz     loc_180005420
0x180005282  mov     r9, rsi
0x180005285  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000528a  shr     r9, 2; unsigned __int64
0x18000528e  lea     rcx, [rsp+280h+hObject]; this
0x180005293  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005298  mov     r14d, eax
0x18000529b  test    eax, eax
0x18000529d  jns     loc_180005349
0x1800052a3  mov     rcx, [rbp+188h]; this
0x1800052aa  lea     r8, aWil; "wil"
0x1800052b1  mov     r9d, eax; char *
0x1800052b4  mov     edx, 14Eh; void *
0x1800052b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800052c3  test    rcx, rcx
0x1800052c6  jz      short loc_1800052D6
0x1800052c8  call    cs:__imp_CloseHandle
0x1800052ce  test    eax, eax
0x1800052d0  jz      loc_180005426
0x1800052d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800052db  test    rcx, rcx
0x1800052de  jz      short loc_1800052EE
0x1800052e0  call    cs:__imp_CloseHandle
0x1800052e6  test    eax, eax
0x1800052e8  jz      loc_180005438
0x1800052ee  call    cs:__imp_GetProcessHeap
0x1800052f4  mov     r8, rsi; lpMem
0x1800052f7  xor     edx, edx; dwFlags
0x1800052f9  mov     rcx, rax; hHeap
0x1800052fc  call    cs:__imp_HeapFree
0x180005302  mov     rcx, [rbp+188h]; this
0x180005309  lea     r8, aWil; "wil"
0x180005310  mov     r9d, r14d; char *
0x180005313  mov     edx, 137h; void *
0x180005318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000531d  test    rdi, rdi
0x180005320  jz      short loc_180005333
0x180005322  mov     rcx, rdi; hMutex
0x180005325  call    cs:__imp_ReleaseMutex
0x18000532b  test    eax, eax
0x18000532d  jz      loc_18000544A
0x180005333  mov     rcx, rbx; hObject
0x180005336  call    cs:__imp_CloseHandle
0x18000533c  test    eax, eax
0x18000533e  jz      loc_18000545C
0x180005344  mov     eax, r14d
0x180005347  jmp     short loc_1800053B7
0x180005349  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000534e  xor     edx, edx; Val
0x180005350  mov     dword ptr [rsi], 1
0x180005356  lea     rcx, [rsi+22h]; void *
0x18000535a  mov     [rsi+8], rbx
0x18000535e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005363  lea     r8d, [rdx+56h]; Size
0x180005367  call    memset_0
0x18000536c  xor     edx, edx; Val
0x18000536e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005374  lea     rcx, [rsi+28h]; void *
0x180005378  mov     dword ptr [rsi+24h], 1
0x18000537f  lea     r8d, [rdx+50h]; Size
0x180005383  call    memset_0
0x180005388  xor     ebx, ebx
0x18000538a  mov     [r15], rsi
0x18000538d  test    rdi, rdi
0x180005390  jz      short loc_1800053A3
0x180005392  mov     rcx, rdi; hMutex
0x180005395  call    cs:__imp_ReleaseMutex
0x18000539b  test    eax, eax
0x18000539d  jz      loc_18000546E
0x1800053a3  test    rbx, rbx
0x1800053a6  jz      short loc_1800053B5
0x1800053a8  mov     rcx, rbx; hObject
0x1800053ab  call    cs:__imp_CloseHandle
0x1800053b1  test    eax, eax
0x1800053b3  jz      short loc_1800053DD
0x1800053b5  xor     eax, eax
0x1800053b7  mov     rcx, [rbp+180h+var_30]
0x1800053be  xor     rcx, rsp; StackCookie
0x1800053c1  call    __security_check_cookie
0x1800053c6  mov     rbx, [rsp+280h+arg_10]
0x1800053ce  add     rsp, 260h
0x1800053d5  pop     r15
0x1800053d7  pop     r14
0x1800053d9  pop     rdi
0x1800053da  pop     rsi
0x1800053db  pop     rbp
0x1800053dc  retn
0x1800053dd  mov     rcx, [rbp+188h]; this
0x1800053e4  mov     edx, 0A0Bh; void *
0x1800053e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053ef  mov     rcx, [rbp+188h]; this
0x1800053f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800053fc  mov     rcx, [rbp+188h]; this
0x180005403  mov     edx, 0A15h; void *
0x180005408  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000540e  mov     rcx, [rbp+188h]; this
0x180005415  mov     edx, 0A0Bh; void *
0x18000541a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005420  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005426  mov     rcx, [rbp+188h]; this
0x18000542d  mov     edx, 0A0Bh; void *
0x180005432  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005438  mov     rcx, [rbp+188h]; this
0x18000543f  mov     edx, 0A0Bh; void *
0x180005444  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000544a  mov     rcx, [rbp+188h]; this
0x180005451  mov     edx, 0A15h; void *
0x180005456  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000545c  mov     rcx, [rbp+188h]; this
0x180005463  mov     edx, 0A0Bh; void *
0x180005468  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000546e  mov     rcx, [rbp+188h]; this
0x180005475  mov     edx, 0A15h; void *
0x18000547a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
