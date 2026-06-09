# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003068`
- end: `0x180003430`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003f30`

## callees

- `0x180001510`
- `0x180001e66`
- `0x180003068`
- `0x180003438`
- `0x180003680`
- `0x180003cc8`
- `0x1800047a8`
- `0x180004a84`
- `0x180005498`
- `0x18000555c`
- `0x18000593c`
- `0x18000594c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800030e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800030e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003101`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003101`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003197`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800032d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003345`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003197`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800032d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000329e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000329e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000335b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000335b`

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
0x180003068  mov     [rsp-8+arg_10], rbx
0x18000306d  push    rbp
0x18000306e  push    rsi
0x18000306f  push    rdi
0x180003070  push    r14
0x180003072  push    r15
0x180003074  lea     rbp, [rsp-160h]
0x18000307c  sub     rsp, 260h
0x180003083  mov     rax, cs:__security_cookie
0x18000308a  xor     rax, rsp
0x18000308d  mov     [rbp+180h+var_30], rax
0x180003094  mov     r15, rdx
0x180003097  mov     qword ptr [rdx], 0
0x18000309e  mov     rbx, rcx
0x1800030a1  call    cs:__imp_GetCurrentProcessId
0x1800030a7  mov     r14d, 78h ; 'x'
0x1800030ad  mov     [rsp+280h+var_258], rbx
0x1800030b2  mov     r9d, eax
0x1800030b5  mov     [rsp+280h+var_260], r14d; int
0x1800030ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800030c1  mov     edx, 104h; unsigned __int64
0x1800030c6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800030cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800030d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800030d6  lea     rdx, [rsp+280h+Name]; lpName
0x1800030db  xor     r8d, r8d; dwFlags
0x1800030de  xor     ecx, ecx; lpMutexAttributes
0x1800030e0  call    cs:__imp_CreateMutexExW
0x1800030e6  mov     rbx, rax
0x1800030e9  test    rax, rax
0x1800030ec  jnz     short loc_1800030F8
0x1800030ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800030f3  jmp     loc_180003367
0x1800030f8  xor     r8d, r8d; bAlertable
0x1800030fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800030fe  mov     rcx, rbx; hHandle
0x180003101  call    cs:__imp_WaitForSingleObjectEx
0x180003107  cmp     eax, 102h
0x18000310c  jz      short loc_18000311E
0x18000310e  test    eax, 0FFFFFF7Fh
0x180003113  jnz     loc_18000339F
0x180003119  mov     rdi, rbx
0x18000311c  jmp     short loc_180003120
0x18000311e  xor     edi, edi
0x180003120  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003125  mov     [rsp+280h+hObject], 0
0x18000312e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003133  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003138  mov     esi, eax
0x18000313a  test    eax, eax
0x18000313c  jns     short loc_1800031BD
0x18000313e  mov     rcx, [rbp+188h]; this
0x180003145  lea     r8, aWil; "wil"
0x18000314c  mov     r9d, eax; char *
0x18000314f  mov     edx, 66h ; 'f'; void *
0x180003154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003159  mov     rcx, [rbp+188h]; this
0x180003160  lea     r8, aWil; "wil"
0x180003167  mov     r9d, esi; char *
0x18000316a  mov     edx, 6Fh ; 'o'; void *
0x18000316f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003174  mov     rcx, [rbp+188h]; this
0x18000317b  lea     r8, aWil; "wil"
0x180003182  mov     r9d, esi; char *
0x180003185  mov     edx, 12Eh; void *
0x18000318a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000318f  test    rdi, rdi
0x180003192  jz      short loc_1800031A5
0x180003194  mov     rcx, rdi; hMutex
0x180003197  call    cs:__imp_ReleaseMutex
0x18000319d  test    eax, eax
0x18000319f  jz      loc_1800033AC
0x1800031a5  mov     rcx, rbx; hObject
0x1800031a8  call    cs:__imp_CloseHandle
0x1800031ae  test    eax, eax
0x1800031b0  jz      loc_1800033BE
0x1800031b6  mov     eax, esi
0x1800031b8  jmp     loc_180003367
0x1800031bd  mov     rax, [rsp+280h+hObject]
0x1800031c2  lea     rcx, ds:0[rax*4]
0x1800031ca  test    rcx, rcx
0x1800031cd  jz      short loc_1800031DD
0x1800031cf  mov     [r15], rcx
0x1800031d2  mov     eax, [rcx]
0x1800031d4  inc     eax
0x1800031d6  mov     [rcx], eax
0x1800031d8  jmp     loc_18000333D
0x1800031dd  mov     rdx, r14; dwBytes
0x1800031e0  mov     qword ptr [r15], 0
0x1800031e7  mov     ecx, 8; dwFlags
0x1800031ec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800031f1  mov     rsi, rax
0x1800031f4  test    rax, rax
0x1800031f7  jnz     short loc_18000321F
0x1800031f9  mov     rcx, [rbp+188h]; this
0x180003200  lea     r8, aWil; "wil"
0x180003207  mov     r14d, 8007000Eh
0x18000320d  mov     edx, 14Bh; void *
0x180003212  mov     r9d, r14d; char *
0x180003215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000321a  jmp     loc_1800032B2
0x18000321f  xorps   xmm0, xmm0
0x180003222  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003228  test    sil, 3
0x18000322c  jnz     loc_1800033D0
0x180003232  mov     r9, rsi
0x180003235  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000323a  shr     r9, 2; unsigned __int64
0x18000323e  lea     rcx, [rsp+280h+hObject]; this
0x180003243  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003248  mov     r14d, eax
0x18000324b  test    eax, eax
0x18000324d  jns     loc_1800032F9
0x180003253  mov     rcx, [rbp+188h]; this
0x18000325a  lea     r8, aWil; "wil"
0x180003261  mov     r9d, eax; char *
0x180003264  mov     edx, 14Eh; void *
0x180003269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000326e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003273  test    rcx, rcx
0x180003276  jz      short loc_180003286
0x180003278  call    cs:__imp_CloseHandle
0x18000327e  test    eax, eax
0x180003280  jz      loc_1800033D6
0x180003286  mov     rcx, [rsp+280h+hObject]; hObject
0x18000328b  test    rcx, rcx
0x18000328e  jz      short loc_18000329E
0x180003290  call    cs:__imp_CloseHandle
0x180003296  test    eax, eax
0x180003298  jz      loc_1800033E8
0x18000329e  call    cs:__imp_GetProcessHeap
0x1800032a4  mov     r8, rsi; lpMem
0x1800032a7  xor     edx, edx; dwFlags
0x1800032a9  mov     rcx, rax; hHeap
0x1800032ac  call    cs:__imp_HeapFree
0x1800032b2  mov     rcx, [rbp+188h]; this
0x1800032b9  lea     r8, aWil; "wil"
0x1800032c0  mov     r9d, r14d; char *
0x1800032c3  mov     edx, 137h; void *
0x1800032c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032cd  test    rdi, rdi
0x1800032d0  jz      short loc_1800032E3
0x1800032d2  mov     rcx, rdi; hMutex
0x1800032d5  call    cs:__imp_ReleaseMutex
0x1800032db  test    eax, eax
0x1800032dd  jz      loc_1800033FA
0x1800032e3  mov     rcx, rbx; hObject
0x1800032e6  call    cs:__imp_CloseHandle
0x1800032ec  test    eax, eax
0x1800032ee  jz      loc_18000340C
0x1800032f4  mov     eax, r14d
0x1800032f7  jmp     short loc_180003367
0x1800032f9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800032fe  xor     edx, edx; Val
0x180003300  mov     dword ptr [rsi], 1
0x180003306  lea     rcx, [rsi+22h]; void *
0x18000330a  mov     [rsi+8], rbx
0x18000330e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003313  lea     r8d, [rdx+56h]; Size
0x180003317  call    memset_0
0x18000331c  xor     edx, edx; Val
0x18000331e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003324  lea     rcx, [rsi+28h]; void *
0x180003328  mov     dword ptr [rsi+24h], 1
0x18000332f  lea     r8d, [rdx+50h]; Size
0x180003333  call    memset_0
0x180003338  xor     ebx, ebx
0x18000333a  mov     [r15], rsi
0x18000333d  test    rdi, rdi
0x180003340  jz      short loc_180003353
0x180003342  mov     rcx, rdi; hMutex
0x180003345  call    cs:__imp_ReleaseMutex
0x18000334b  test    eax, eax
0x18000334d  jz      loc_18000341E
0x180003353  test    rbx, rbx
0x180003356  jz      short loc_180003365
0x180003358  mov     rcx, rbx; hObject
0x18000335b  call    cs:__imp_CloseHandle
0x180003361  test    eax, eax
0x180003363  jz      short loc_18000338D
0x180003365  xor     eax, eax
0x180003367  mov     rcx, [rbp+180h+var_30]
0x18000336e  xor     rcx, rsp; StackCookie
0x180003371  call    __security_check_cookie
0x180003376  mov     rbx, [rsp+280h+arg_10]
0x18000337e  add     rsp, 260h
0x180003385  pop     r15
0x180003387  pop     r14
0x180003389  pop     rdi
0x18000338a  pop     rsi
0x18000338b  pop     rbp
0x18000338c  retn
0x18000338d  mov     rcx, [rbp+188h]; this
0x180003394  mov     edx, 0A0Bh; void *
0x180003399  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000339f  mov     rcx, [rbp+188h]; this
0x1800033a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800033ac  mov     rcx, [rbp+188h]; this
0x1800033b3  mov     edx, 0A15h; void *
0x1800033b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033be  mov     rcx, [rbp+188h]; this
0x1800033c5  mov     edx, 0A0Bh; void *
0x1800033ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800033d6  mov     rcx, [rbp+188h]; this
0x1800033dd  mov     edx, 0A0Bh; void *
0x1800033e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033e8  mov     rcx, [rbp+188h]; this
0x1800033ef  mov     edx, 0A0Bh; void *
0x1800033f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033fa  mov     rcx, [rbp+188h]; this
0x180003401  mov     edx, 0A15h; void *
0x180003406  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000340c  mov     rcx, [rbp+188h]; this
0x180003413  mov     edx, 0A0Bh; void *
0x180003418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000341e  mov     rcx, [rbp+188h]; this
0x180003425  mov     edx, 0A15h; void *
0x18000342a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
