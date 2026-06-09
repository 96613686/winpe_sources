# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800034b8`
- end: `0x180003880`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004520`

## callees

- `0x180001520`
- `0x180001e5a`
- `0x1800034b8`
- `0x180003888`
- `0x180003c70`
- `0x1800042b8`
- `0x180004d98`
- `0x180005224`
- `0x180005bb0`
- `0x180005c6c`
- `0x18000602c`
- `0x18000603c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003795`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003795`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003551`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003551`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003530`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003530`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003736`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003736`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037ab`

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
0x1800034b8  mov     [rsp-8+arg_10], rbx
0x1800034bd  push    rbp
0x1800034be  push    rsi
0x1800034bf  push    rdi
0x1800034c0  push    r14
0x1800034c2  push    r15
0x1800034c4  lea     rbp, [rsp-160h]
0x1800034cc  sub     rsp, 260h
0x1800034d3  mov     rax, cs:__security_cookie
0x1800034da  xor     rax, rsp
0x1800034dd  mov     [rbp+180h+var_30], rax
0x1800034e4  mov     r15, rdx
0x1800034e7  mov     qword ptr [rdx], 0
0x1800034ee  mov     rbx, rcx
0x1800034f1  call    cs:__imp_GetCurrentProcessId
0x1800034f7  mov     r14d, 78h ; 'x'
0x1800034fd  mov     [rsp+280h+var_258], rbx
0x180003502  mov     r9d, eax
0x180003505  mov     [rsp+280h+var_260], r14d; int
0x18000350a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003511  mov     edx, 104h; unsigned __int64
0x180003516  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000351b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003520  mov     r9d, 1F0001h; dwDesiredAccess
0x180003526  lea     rdx, [rsp+280h+Name]; lpName
0x18000352b  xor     r8d, r8d; dwFlags
0x18000352e  xor     ecx, ecx; lpMutexAttributes
0x180003530  call    cs:__imp_CreateMutexExW
0x180003536  mov     rbx, rax
0x180003539  test    rax, rax
0x18000353c  jnz     short loc_180003548
0x18000353e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003543  jmp     loc_1800037B7
0x180003548  xor     r8d, r8d; bAlertable
0x18000354b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000354e  mov     rcx, rbx; hHandle
0x180003551  call    cs:__imp_WaitForSingleObjectEx
0x180003557  cmp     eax, 102h
0x18000355c  jz      short loc_18000356E
0x18000355e  test    eax, 0FFFFFF7Fh
0x180003563  jnz     loc_1800037EF
0x180003569  mov     rdi, rbx
0x18000356c  jmp     short loc_180003570
0x18000356e  xor     edi, edi
0x180003570  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003575  mov     [rsp+280h+hObject], 0
0x18000357e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003583  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003588  mov     esi, eax
0x18000358a  test    eax, eax
0x18000358c  jns     short loc_18000360D
0x18000358e  mov     rcx, [rbp+188h]; this
0x180003595  lea     r8, aWil; "wil"
0x18000359c  mov     r9d, eax; char *
0x18000359f  mov     edx, 66h ; 'f'; void *
0x1800035a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035a9  mov     rcx, [rbp+188h]; this
0x1800035b0  lea     r8, aWil; "wil"
0x1800035b7  mov     r9d, esi; char *
0x1800035ba  mov     edx, 6Fh ; 'o'; void *
0x1800035bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035c4  mov     rcx, [rbp+188h]; this
0x1800035cb  lea     r8, aWil; "wil"
0x1800035d2  mov     r9d, esi; char *
0x1800035d5  mov     edx, 12Eh; void *
0x1800035da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035df  test    rdi, rdi
0x1800035e2  jz      short loc_1800035F5
0x1800035e4  mov     rcx, rdi; hMutex
0x1800035e7  call    cs:__imp_ReleaseMutex
0x1800035ed  test    eax, eax
0x1800035ef  jz      loc_1800037FC
0x1800035f5  mov     rcx, rbx; hObject
0x1800035f8  call    cs:__imp_CloseHandle
0x1800035fe  test    eax, eax
0x180003600  jz      loc_18000380E
0x180003606  mov     eax, esi
0x180003608  jmp     loc_1800037B7
0x18000360d  mov     rax, [rsp+280h+hObject]
0x180003612  lea     rcx, ds:0[rax*4]
0x18000361a  test    rcx, rcx
0x18000361d  jz      short loc_18000362D
0x18000361f  mov     [r15], rcx
0x180003622  mov     eax, [rcx]
0x180003624  inc     eax
0x180003626  mov     [rcx], eax
0x180003628  jmp     loc_18000378D
0x18000362d  mov     rdx, r14; dwBytes
0x180003630  mov     qword ptr [r15], 0
0x180003637  mov     ecx, 8; dwFlags
0x18000363c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003641  mov     rsi, rax
0x180003644  test    rax, rax
0x180003647  jnz     short loc_18000366F
0x180003649  mov     rcx, [rbp+188h]; this
0x180003650  lea     r8, aWil; "wil"
0x180003657  mov     r14d, 8007000Eh
0x18000365d  mov     edx, 14Bh; void *
0x180003662  mov     r9d, r14d; char *
0x180003665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000366a  jmp     loc_180003702
0x18000366f  xorps   xmm0, xmm0
0x180003672  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003678  test    sil, 3
0x18000367c  jnz     loc_180003820
0x180003682  mov     r9, rsi
0x180003685  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000368a  shr     r9, 2; unsigned __int64
0x18000368e  lea     rcx, [rsp+280h+hObject]; this
0x180003693  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003698  mov     r14d, eax
0x18000369b  test    eax, eax
0x18000369d  jns     loc_180003749
0x1800036a3  mov     rcx, [rbp+188h]; this
0x1800036aa  lea     r8, aWil; "wil"
0x1800036b1  mov     r9d, eax; char *
0x1800036b4  mov     edx, 14Eh; void *
0x1800036b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800036c3  test    rcx, rcx
0x1800036c6  jz      short loc_1800036D6
0x1800036c8  call    cs:__imp_CloseHandle
0x1800036ce  test    eax, eax
0x1800036d0  jz      loc_180003826
0x1800036d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800036db  test    rcx, rcx
0x1800036de  jz      short loc_1800036EE
0x1800036e0  call    cs:__imp_CloseHandle
0x1800036e6  test    eax, eax
0x1800036e8  jz      loc_180003838
0x1800036ee  call    cs:__imp_GetProcessHeap
0x1800036f4  mov     r8, rsi; lpMem
0x1800036f7  xor     edx, edx; dwFlags
0x1800036f9  mov     rcx, rax; hHeap
0x1800036fc  call    cs:__imp_HeapFree
0x180003702  mov     rcx, [rbp+188h]; this
0x180003709  lea     r8, aWil; "wil"
0x180003710  mov     r9d, r14d; char *
0x180003713  mov     edx, 137h; void *
0x180003718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000371d  test    rdi, rdi
0x180003720  jz      short loc_180003733
0x180003722  mov     rcx, rdi; hMutex
0x180003725  call    cs:__imp_ReleaseMutex
0x18000372b  test    eax, eax
0x18000372d  jz      loc_18000384A
0x180003733  mov     rcx, rbx; hObject
0x180003736  call    cs:__imp_CloseHandle
0x18000373c  test    eax, eax
0x18000373e  jz      loc_18000385C
0x180003744  mov     eax, r14d
0x180003747  jmp     short loc_1800037B7
0x180003749  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000374e  xor     edx, edx; Val
0x180003750  mov     dword ptr [rsi], 1
0x180003756  lea     rcx, [rsi+22h]; void *
0x18000375a  mov     [rsi+8], rbx
0x18000375e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003763  lea     r8d, [rdx+56h]; Size
0x180003767  call    memset_0
0x18000376c  xor     edx, edx; Val
0x18000376e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003774  lea     rcx, [rsi+28h]; void *
0x180003778  mov     dword ptr [rsi+24h], 1
0x18000377f  lea     r8d, [rdx+50h]; Size
0x180003783  call    memset_0
0x180003788  xor     ebx, ebx
0x18000378a  mov     [r15], rsi
0x18000378d  test    rdi, rdi
0x180003790  jz      short loc_1800037A3
0x180003792  mov     rcx, rdi; hMutex
0x180003795  call    cs:__imp_ReleaseMutex
0x18000379b  test    eax, eax
0x18000379d  jz      loc_18000386E
0x1800037a3  test    rbx, rbx
0x1800037a6  jz      short loc_1800037B5
0x1800037a8  mov     rcx, rbx; hObject
0x1800037ab  call    cs:__imp_CloseHandle
0x1800037b1  test    eax, eax
0x1800037b3  jz      short loc_1800037DD
0x1800037b5  xor     eax, eax
0x1800037b7  mov     rcx, [rbp+180h+var_30]
0x1800037be  xor     rcx, rsp; StackCookie
0x1800037c1  call    __security_check_cookie
0x1800037c6  mov     rbx, [rsp+280h+arg_10]
0x1800037ce  add     rsp, 260h
0x1800037d5  pop     r15
0x1800037d7  pop     r14
0x1800037d9  pop     rdi
0x1800037da  pop     rsi
0x1800037db  pop     rbp
0x1800037dc  retn
0x1800037dd  mov     rcx, [rbp+188h]; this
0x1800037e4  mov     edx, 0A0Bh; void *
0x1800037e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037ef  mov     rcx, [rbp+188h]; this
0x1800037f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800037fc  mov     rcx, [rbp+188h]; this
0x180003803  mov     edx, 0A15h; void *
0x180003808  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000380e  mov     rcx, [rbp+188h]; this
0x180003815  mov     edx, 0A0Bh; void *
0x18000381a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003820  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003826  mov     rcx, [rbp+188h]; this
0x18000382d  mov     edx, 0A0Bh; void *
0x180003832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003838  mov     rcx, [rbp+188h]; this
0x18000383f  mov     edx, 0A0Bh; void *
0x180003844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000384a  mov     rcx, [rbp+188h]; this
0x180003851  mov     edx, 0A15h; void *
0x180003856  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000385c  mov     rcx, [rbp+188h]; this
0x180003863  mov     edx, 0A0Bh; void *
0x180003868  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000386e  mov     rcx, [rbp+188h]; this
0x180003875  mov     edx, 0A15h; void *
0x18000387a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
