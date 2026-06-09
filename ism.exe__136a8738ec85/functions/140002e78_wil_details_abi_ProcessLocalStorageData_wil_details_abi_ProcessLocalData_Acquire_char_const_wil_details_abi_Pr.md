# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002e78`
- end: `0x140003214`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140003d10`

## callees

- `0x140001460`
- `0x140001e56`
- `0x140002c44`
- `0x140002e78`
- `0x14000321c`
- `0x140003450`
- `0x140003aa8`
- `0x140004624`
- `0x140004914`
- `0x140005304`
- `0x1400053bc`
- `0x14000579c`
- `0x1400057ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000306a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000306a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000305c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000305c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000309d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000309d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003139`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002ef0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002ef0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002f11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002f11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000308c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003123`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000308c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003123`

## string_xrefs

- `0x140003172`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000318b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400031b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400031ca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400031e9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140003202`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v18; // r9
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  unsigned int v23; // r8d
  _DWORD *v24; // r14
  unsigned int v25; // r8d
  int v26; // eax
  unsigned int v27; // r8d
  HANDLE ProcessHeap; // rax
  const char *v29; // r9
  const char *v30; // r9
  unsigned __int64 v31; // rax
  const char *v32; // r9
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_24;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v23, (const char *)0x8007000ELL, 120);
    goto LABEL_19;
  }
  *(_OWORD *)v37 = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v37,
          Name,
          v23,
          v21 >> 2);
  v15 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v27, (const char *)(unsigned int)v26, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v25, (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v29);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v30);
    return v15;
  }
  *((_QWORD *)v24 + 2) = v37[0];
  v31 = v37[1];
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v24 + 3) = v31;
  v37[1] = 0;
  memset_0((char *)v24 + 34, 0, 0x56u);
  *((_WORD *)v24 + 16) = 88;
  v24[9] = 1;
  memset_0(v24 + 10, 0, 0x50u);
  *a2 = v24;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v33);
  return 0;
}

```

## disassembly

```asm
0x140002e78  mov     [rsp-8+arg_10], rbx
0x140002e7d  push    rbp
0x140002e7e  push    rsi
0x140002e7f  push    rdi
0x140002e80  push    r14
0x140002e82  push    r15
0x140002e84  lea     rbp, [rsp-160h]
0x140002e8c  sub     rsp, 260h
0x140002e93  mov     rax, cs:__security_cookie
0x140002e9a  xor     rax, rsp
0x140002e9d  mov     [rbp+180h+var_30], rax
0x140002ea4  mov     r15, rdx
0x140002ea7  mov     qword ptr [rdx], 0
0x140002eae  mov     rbx, rcx
0x140002eb1  call    cs:__imp_GetCurrentProcessId
0x140002eb7  mov     r14d, 78h ; 'x'
0x140002ebd  mov     [rsp+280h+var_258], rbx
0x140002ec2  mov     r9d, eax
0x140002ec5  mov     [rsp+280h+var_260], r14d; int
0x140002eca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002ed1  mov     edx, 104h; unsigned __int64
0x140002ed6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002edb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002ee0  mov     r9d, 1F0001h; dwDesiredAccess
0x140002ee6  lea     rdx, [rsp+280h+Name]; lpName
0x140002eeb  xor     r8d, r8d; dwFlags
0x140002eee  xor     ecx, ecx; lpMutexAttributes
0x140002ef0  call    cs:__imp_CreateMutexExW
0x140002ef6  mov     rbx, rax
0x140002ef9  test    rax, rax
0x140002efc  jnz     short loc_140002F08
0x140002efe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002f03  jmp     loc_140003145
0x140002f08  xor     r8d, r8d; bAlertable
0x140002f0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002f0e  mov     rcx, rbx; hHandle
0x140002f11  call    cs:__imp_WaitForSingleObjectEx
0x140002f17  cmp     eax, 102h
0x140002f1c  jz      short loc_140002F2E
0x140002f1e  test    eax, 0FFFFFF7Fh
0x140002f23  jnz     loc_14000319D
0x140002f29  mov     rdi, rbx
0x140002f2c  jmp     short loc_140002F30
0x140002f2e  xor     edi, edi
0x140002f30  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140002f35  mov     [rsp+280h+var_250], 0
0x140002f3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002f43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002f48  mov     esi, eax
0x140002f4a  test    eax, eax
0x140002f4c  jns     short loc_140002FB8
0x140002f4e  mov     rcx, [rbp+188h]; this
0x140002f55  mov     r9d, eax; char *
0x140002f58  mov     edx, 66h ; 'f'; void *
0x140002f5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f62  mov     rcx, [rbp+188h]; this
0x140002f69  mov     r9d, esi; char *
0x140002f6c  mov     edx, 6Fh ; 'o'; void *
0x140002f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f76  mov     rcx, [rbp+188h]; this
0x140002f7d  mov     r9d, esi; char *
0x140002f80  mov     edx, 12Eh; void *
0x140002f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f8a  test    rdi, rdi
0x140002f8d  jz      short loc_140002FA0
0x140002f8f  mov     rcx, rdi; hMutex
0x140002f92  call    cs:__imp_ReleaseMutex
0x140002f98  test    eax, eax
0x140002f9a  jz      loc_1400031AA
0x140002fa0  mov     rcx, rbx; hObject
0x140002fa3  call    cs:__imp_CloseHandle
0x140002fa9  test    eax, eax
0x140002fab  jz      loc_1400031C3
0x140002fb1  mov     eax, esi
0x140002fb3  jmp     loc_140003145
0x140002fb8  mov     rax, [rsp+280h+var_250]
0x140002fbd  lea     rcx, ds:0[rax*4]
0x140002fc5  test    rcx, rcx
0x140002fc8  jz      short loc_140002FD8
0x140002fca  mov     [r15], rcx
0x140002fcd  mov     eax, [rcx]
0x140002fcf  inc     eax
0x140002fd1  mov     [rcx], eax
0x140002fd3  jmp     loc_14000311B
0x140002fd8  mov     rdx, r14; dwBytes
0x140002fdb  mov     qword ptr [r15], 0
0x140002fe2  mov     ecx, 8; dwFlags
0x140002fe7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002fec  mov     r14, rax
0x140002fef  test    rax, rax
0x140002ff2  jnz     short loc_14000300F
0x140002ff4  mov     rcx, [rbp+188h]; this
0x140002ffb  mov     esi, 8007000Eh
0x140003000  mov     r9d, esi; char *
0x140003003  mov     edx, 14Bh; void *
0x140003008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000300d  jmp     short loc_140003070
0x14000300f  xorps   xmm0, xmm0
0x140003012  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140003018  test    r14b, 3
0x14000301c  jnz     loc_1400031DC
0x140003022  mov     r9, r14
0x140003025  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000302a  shr     r9, 2; unsigned __int64
0x14000302e  lea     rcx, [rsp+280h+var_250]; this
0x140003033  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003038  mov     esi, eax
0x14000303a  test    eax, eax
0x14000303c  jns     short loc_1400030B0
0x14000303e  mov     rcx, [rbp+188h]; this
0x140003045  mov     r9d, eax; char *
0x140003048  mov     edx, 14Eh; void *
0x14000304d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003052  lea     rcx, [rsp+280h+var_250]; this
0x140003057  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000305c  call    cs:__imp_GetProcessHeap
0x140003062  mov     r8, r14; lpMem
0x140003065  xor     edx, edx; dwFlags
0x140003067  mov     rcx, rax; hHeap
0x14000306a  call    cs:__imp_HeapFree
0x140003070  mov     rcx, [rbp+188h]; this
0x140003077  mov     r9d, esi; char *
0x14000307a  mov     edx, 137h; void *
0x14000307f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003084  test    rdi, rdi
0x140003087  jz      short loc_14000309A
0x140003089  mov     rcx, rdi; hMutex
0x14000308c  call    cs:__imp_ReleaseMutex
0x140003092  test    eax, eax
0x140003094  jz      loc_1400031E2
0x14000309a  mov     rcx, rbx; hObject
0x14000309d  call    cs:__imp_CloseHandle
0x1400030a3  test    eax, eax
0x1400030a5  jz      loc_140003184
0x1400030ab  jmp     loc_140002FB1
0x1400030b0  mov     rax, [rsp+280h+var_250]
0x1400030b5  lea     rcx, [r14+22h]; void *
0x1400030b9  xor     edx, edx; Val
0x1400030bb  mov     [r14+10h], rax
0x1400030bf  mov     rax, [rsp+280h+var_250+8]
0x1400030c4  mov     dword ptr [r14], 1
0x1400030cb  mov     [r14+8], rbx
0x1400030cf  lea     r8d, [rdx+56h]; Size
0x1400030d3  mov     [rsp+280h+var_250], 0
0x1400030dc  mov     [r14+18h], rax
0x1400030e0  mov     [rsp+280h+var_250+8], 0
0x1400030e9  call    memset_0
0x1400030ee  xor     edx, edx; Val
0x1400030f0  mov     word ptr [r14+20h], 58h ; 'X'
0x1400030f7  lea     rcx, [r14+28h]; void *
0x1400030fb  mov     dword ptr [r14+24h], 1
0x140003103  lea     r8d, [rdx+50h]; Size
0x140003107  call    memset_0
0x14000310c  lea     rcx, [rsp+280h+var_250]; this
0x140003111  mov     [r15], r14
0x140003114  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140003119  xor     ebx, ebx
0x14000311b  test    rdi, rdi
0x14000311e  jz      short loc_140003131
0x140003120  mov     rcx, rdi; hMutex
0x140003123  call    cs:__imp_ReleaseMutex
0x140003129  test    eax, eax
0x14000312b  jz      loc_1400031FB
0x140003131  test    rbx, rbx
0x140003134  jz      short loc_140003143
0x140003136  mov     rcx, rbx; hObject
0x140003139  call    cs:__imp_CloseHandle
0x14000313f  test    eax, eax
0x140003141  jz      short loc_14000316B
0x140003143  xor     eax, eax
0x140003145  mov     rcx, [rbp+180h+var_30]
0x14000314c  xor     rcx, rsp; StackCookie
0x14000314f  call    __security_check_cookie
0x140003154  mov     rbx, [rsp+280h+arg_10]
0x14000315c  add     rsp, 260h
0x140003163  pop     r15
0x140003165  pop     r14
0x140003167  pop     rdi
0x140003168  pop     rsi
0x140003169  pop     rbp
0x14000316a  retn
0x14000316b  mov     rcx, [rbp+188h]; this
0x140003172  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003179  mov     edx, 0A0Bh; void *
0x14000317e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003184  mov     rcx, [rbp+188h]; this
0x14000318b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003192  mov     edx, 0A0Bh; void *
0x140003197  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000319d  mov     rcx, [rbp+188h]; this
0x1400031a4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400031aa  mov     rcx, [rbp+188h]; this
0x1400031b1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400031b8  mov     edx, 0A15h; void *
0x1400031bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400031c3  mov     rcx, [rbp+188h]; this
0x1400031ca  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400031d1  mov     edx, 0A0Bh; void *
0x1400031d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400031dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400031e2  mov     rcx, [rbp+188h]; this
0x1400031e9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400031f0  mov     edx, 0A15h; void *
0x1400031f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400031fb  mov     rcx, [rbp+188h]; this
0x140003202  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003209  mov     edx, 0A15h; void *
0x14000320e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
