# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008318`
- end: `0x1800086f0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000bf20`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x180007d38`
- `0x180008318`
- `0x180008afc`
- `0x180009060`
- `0x18000bcb8`
- `0x18000d178`
- `0x18000ec54`
- `0x18000f7bc`
- `0x18000ff04`
- `0x1800108c4`
- `0x1800108d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800083b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800083b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008447`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000855c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008447`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000855c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085f3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008390`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008390`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008525`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008533`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008351`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000856d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008609`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000856d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008609`

## string_xrefs

- `0x180008642`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000865b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008674`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000868d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800086ac`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800086c5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800086de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x180008318  mov     [rsp-8+arg_10], rbx
0x18000831d  push    rbp
0x18000831e  push    rsi
0x18000831f  push    rdi
0x180008320  push    r14
0x180008322  push    r15
0x180008324  lea     rbp, [rsp-160h]
0x18000832c  sub     rsp, 260h
0x180008333  mov     rax, cs:__security_cookie
0x18000833a  xor     rax, rsp
0x18000833d  mov     [rbp+180h+var_30], rax
0x180008344  mov     r15, rdx
0x180008347  mov     qword ptr [rdx], 0
0x18000834e  mov     rbx, rcx
0x180008351  call    cs:__imp_GetCurrentProcessId
0x180008357  mov     r14d, 78h ; 'x'
0x18000835d  mov     [rsp+280h+var_258], rbx
0x180008362  mov     r9d, eax
0x180008365  mov     [rsp+280h+var_260], r14d; int
0x18000836a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008371  mov     edx, 104h; unsigned __int64
0x180008376  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000837b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008380  mov     r9d, 1F0001h; dwDesiredAccess
0x180008386  lea     rdx, [rsp+280h+Name]; lpName
0x18000838b  xor     r8d, r8d; dwFlags
0x18000838e  xor     ecx, ecx; lpMutexAttributes
0x180008390  call    cs:__imp_CreateMutexExW
0x180008396  mov     rbx, rax
0x180008399  test    rax, rax
0x18000839c  jnz     short loc_1800083A8
0x18000839e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800083a3  jmp     loc_180008615
0x1800083a8  xor     r8d, r8d; bAlertable
0x1800083ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800083ae  mov     rcx, rbx; hHandle
0x1800083b1  call    cs:__imp_WaitForSingleObjectEx
0x1800083b7  cmp     eax, 102h
0x1800083bc  jz      short loc_1800083CE
0x1800083be  test    eax, 0FFFFFF7Fh
0x1800083c3  jnz     loc_180008654
0x1800083c9  mov     rdi, rbx
0x1800083cc  jmp     short loc_1800083D0
0x1800083ce  xor     edi, edi
0x1800083d0  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800083d5  mov     [rsp+280h+var_250], 0
0x1800083de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800083e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800083e8  mov     esi, eax
0x1800083ea  test    eax, eax
0x1800083ec  jns     short loc_18000846D
0x1800083ee  mov     rcx, [rbp+188h]; this
0x1800083f5  lea     r8, aWil; "wil"
0x1800083fc  mov     r9d, eax; char *
0x1800083ff  mov     edx, 66h ; 'f'; void *
0x180008404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008409  mov     rcx, [rbp+188h]; this
0x180008410  lea     r8, aWil; "wil"
0x180008417  mov     r9d, esi; char *
0x18000841a  mov     edx, 6Fh ; 'o'; void *
0x18000841f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008424  mov     rcx, [rbp+188h]; this
0x18000842b  lea     r8, aWil; "wil"
0x180008432  mov     r9d, esi; char *
0x180008435  mov     edx, 12Eh; void *
0x18000843a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000843f  test    rdi, rdi
0x180008442  jz      short loc_180008455
0x180008444  mov     rcx, rdi; hMutex
0x180008447  call    cs:__imp_ReleaseMutex
0x18000844d  test    eax, eax
0x18000844f  jz      loc_18000866D
0x180008455  mov     rcx, rbx; hObject
0x180008458  call    cs:__imp_CloseHandle
0x18000845e  test    eax, eax
0x180008460  jz      loc_180008686
0x180008466  mov     eax, esi
0x180008468  jmp     loc_180008615
0x18000846d  mov     rax, [rsp+280h+var_250]
0x180008472  lea     rcx, ds:0[rax*4]
0x18000847a  test    rcx, rcx
0x18000847d  jz      short loc_18000848D
0x18000847f  mov     [r15], rcx
0x180008482  mov     eax, [rcx]
0x180008484  inc     eax
0x180008486  mov     [rcx], eax
0x180008488  jmp     loc_1800085EB
0x18000848d  mov     rdx, r14; dwBytes
0x180008490  mov     qword ptr [r15], 0
0x180008497  mov     ecx, 8; dwFlags
0x18000849c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800084a1  mov     rsi, rax
0x1800084a4  test    rax, rax
0x1800084a7  jnz     short loc_1800084CC
0x1800084a9  mov     rcx, [rbp+188h]; this
0x1800084b0  lea     r8, aWil; "wil"
0x1800084b7  mov     r14d, 8007000Eh
0x1800084bd  mov     edx, 14Bh; void *
0x1800084c2  mov     r9d, r14d; char *
0x1800084c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084ca  jmp     short loc_180008539
0x1800084cc  xorps   xmm0, xmm0
0x1800084cf  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800084d5  test    sil, 3
0x1800084d9  jnz     loc_18000869F
0x1800084df  mov     r9, rsi
0x1800084e2  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800084e7  shr     r9, 2; unsigned __int64
0x1800084eb  lea     rcx, [rsp+280h+var_250]; this
0x1800084f0  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800084f5  mov     r14d, eax
0x1800084f8  test    eax, eax
0x1800084fa  jns     loc_180008583
0x180008500  mov     rcx, [rbp+188h]; this
0x180008507  lea     r8, aWil; "wil"
0x18000850e  mov     r9d, eax; char *
0x180008511  mov     edx, 14Eh; void *
0x180008516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000851b  lea     rcx, [rsp+280h+var_250]; this
0x180008520  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008525  call    cs:__imp_GetProcessHeap
0x18000852b  mov     r8, rsi; lpMem
0x18000852e  xor     edx, edx; dwFlags
0x180008530  mov     rcx, rax; hHeap
0x180008533  call    cs:__imp_HeapFree
0x180008539  mov     rcx, [rbp+188h]; this
0x180008540  lea     r8, aWil; "wil"
0x180008547  mov     r9d, r14d; char *
0x18000854a  mov     edx, 137h; void *
0x18000854f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008554  test    rdi, rdi
0x180008557  jz      short loc_18000856A
0x180008559  mov     rcx, rdi; hMutex
0x18000855c  call    cs:__imp_ReleaseMutex
0x180008562  test    eax, eax
0x180008564  jz      loc_1800086A5
0x18000856a  mov     rcx, rbx; hObject
0x18000856d  call    cs:__imp_CloseHandle
0x180008573  test    eax, eax
0x180008575  jz      loc_1800086BE
0x18000857b  mov     eax, r14d
0x18000857e  jmp     loc_180008615
0x180008583  mov     rax, [rsp+280h+var_250]
0x180008588  lea     rcx, [rsi+22h]; void *
0x18000858c  xor     edx, edx; Val
0x18000858e  mov     [rsi+10h], rax
0x180008592  mov     rax, [rsp+280h+var_250+8]
0x180008597  mov     dword ptr [rsi], 1
0x18000859d  mov     [rsi+8], rbx
0x1800085a1  lea     r8d, [rdx+56h]; Size
0x1800085a5  mov     [rsp+280h+var_250], 0
0x1800085ae  mov     [rsi+18h], rax
0x1800085b2  mov     [rsp+280h+var_250+8], 0
0x1800085bb  call    memset_0
0x1800085c0  xor     edx, edx; Val
0x1800085c2  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800085c8  lea     rcx, [rsi+28h]; void *
0x1800085cc  mov     dword ptr [rsi+24h], 1
0x1800085d3  lea     r8d, [rdx+50h]; Size
0x1800085d7  call    memset_0
0x1800085dc  lea     rcx, [rsp+280h+var_250]; this
0x1800085e1  mov     [r15], rsi
0x1800085e4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800085e9  xor     ebx, ebx
0x1800085eb  test    rdi, rdi
0x1800085ee  jz      short loc_180008601
0x1800085f0  mov     rcx, rdi; hMutex
0x1800085f3  call    cs:__imp_ReleaseMutex
0x1800085f9  test    eax, eax
0x1800085fb  jz      loc_1800086D7
0x180008601  test    rbx, rbx
0x180008604  jz      short loc_180008613
0x180008606  mov     rcx, rbx; hObject
0x180008609  call    cs:__imp_CloseHandle
0x18000860f  test    eax, eax
0x180008611  jz      short loc_18000863B
0x180008613  xor     eax, eax
0x180008615  mov     rcx, [rbp+180h+var_30]
0x18000861c  xor     rcx, rsp; StackCookie
0x18000861f  call    __security_check_cookie
0x180008624  mov     rbx, [rsp+280h+arg_10]
0x18000862c  add     rsp, 260h
0x180008633  pop     r15
0x180008635  pop     r14
0x180008637  pop     rdi
0x180008638  pop     rsi
0x180008639  pop     rbp
0x18000863a  retn
0x18000863b  mov     rcx, [rbp+188h]; this
0x180008642  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008649  mov     edx, 0A0Bh; void *
0x18000864e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008654  mov     rcx, [rbp+188h]; this
0x18000865b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008662  mov     edx, 0E01h; void *
0x180008667  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000866d  mov     rcx, [rbp+188h]; this
0x180008674  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000867b  mov     edx, 0A15h; void *
0x180008680  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008686  mov     rcx, [rbp+188h]; this
0x18000868d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008694  mov     edx, 0A0Bh; void *
0x180008699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000869f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800086a5  mov     rcx, [rbp+188h]; this
0x1800086ac  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800086b3  mov     edx, 0A15h; void *
0x1800086b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086be  mov     rcx, [rbp+188h]; this
0x1800086c5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800086cc  mov     edx, 0A0Bh; void *
0x1800086d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086d7  mov     rcx, [rbp+188h]; this
0x1800086de  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800086e5  mov     edx, 0A15h; void *
0x1800086ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
