# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800086f8`
- end: `0x180008af5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180008e00`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000724c`
- `0x180007d38`
- `0x1800086f8`
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

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008790`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008790`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008939`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008939`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800089bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800089bb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000876f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000876f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008910`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000894a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000894a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a0e`

## string_xrefs

- `0x180008a47`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008a60`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008a79`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008a92`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008aab`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008aca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008ae3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
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
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x1800086f8  mov     [rsp-8+arg_10], rbx
0x1800086fd  push    rbp
0x1800086fe  push    rsi
0x1800086ff  push    rdi
0x180008700  push    r14
0x180008702  push    r15
0x180008704  lea     rbp, [rsp-160h]
0x18000870c  sub     rsp, 260h
0x180008713  mov     rax, cs:__security_cookie
0x18000871a  xor     rax, rsp
0x18000871d  mov     [rbp+180h+var_30], rax
0x180008724  mov     r15, rdx
0x180008727  mov     qword ptr [rdx], 0
0x18000872e  mov     rbx, rcx
0x180008731  call    cs:__imp_GetCurrentProcessId
0x180008737  mov     r14d, 130h
0x18000873d  mov     [rsp+280h+var_258], rbx
0x180008742  mov     r9d, eax
0x180008745  mov     [rsp+280h+var_260], r14d; int
0x18000874a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008751  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008756  lea     edx, [r14-2Ch]; unsigned __int64
0x18000875a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000875f  mov     r9d, 1F0001h; dwDesiredAccess
0x180008765  lea     rdx, [rsp+280h+Name]; lpName
0x18000876a  xor     r8d, r8d; dwFlags
0x18000876d  xor     ecx, ecx; lpMutexAttributes
0x18000876f  call    cs:__imp_CreateMutexExW
0x180008775  mov     rbx, rax
0x180008778  test    rax, rax
0x18000877b  jnz     short loc_180008787
0x18000877d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008782  jmp     loc_180008A1A
0x180008787  xor     r8d, r8d; bAlertable
0x18000878a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000878d  mov     rcx, rbx; hHandle
0x180008790  call    cs:__imp_WaitForSingleObjectEx
0x180008796  cmp     eax, 102h
0x18000879b  jz      short loc_1800087AD
0x18000879d  test    eax, 0FFFFFF7Fh
0x1800087a2  jnz     loc_180008A72
0x1800087a8  mov     rdi, rbx
0x1800087ab  jmp     short loc_1800087AF
0x1800087ad  xor     edi, edi
0x1800087af  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800087b4  mov     [rsp+280h+var_250], 0
0x1800087bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800087c2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800087c7  mov     esi, eax
0x1800087c9  test    eax, eax
0x1800087cb  jns     short loc_18000884C
0x1800087cd  mov     rcx, [rbp+188h]; this
0x1800087d4  lea     r8, aWil; "wil"
0x1800087db  mov     r9d, eax; char *
0x1800087de  mov     edx, 66h ; 'f'; void *
0x1800087e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087e8  mov     rcx, [rbp+188h]; this
0x1800087ef  lea     r8, aWil; "wil"
0x1800087f6  mov     r9d, esi; char *
0x1800087f9  mov     edx, 6Fh ; 'o'; void *
0x1800087fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008803  mov     rcx, [rbp+188h]; this
0x18000880a  lea     r8, aWil; "wil"
0x180008811  mov     r9d, esi; char *
0x180008814  mov     edx, 12Eh; void *
0x180008819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000881e  test    rdi, rdi
0x180008821  jz      short loc_180008834
0x180008823  mov     rcx, rdi; hMutex
0x180008826  call    cs:__imp_ReleaseMutex
0x18000882c  test    eax, eax
0x18000882e  jz      loc_180008A8B
0x180008834  mov     rcx, rbx; hObject
0x180008837  call    cs:__imp_CloseHandle
0x18000883d  test    eax, eax
0x18000883f  jz      loc_180008AA4
0x180008845  mov     eax, esi
0x180008847  jmp     loc_180008A1A
0x18000884c  mov     rax, [rsp+280h+var_250]
0x180008851  lea     rcx, ds:0[rax*4]
0x180008859  test    rcx, rcx
0x18000885c  jz      short loc_18000886C
0x18000885e  mov     [r15], rcx
0x180008861  mov     eax, [rcx]
0x180008863  inc     eax
0x180008865  mov     [rcx], eax
0x180008867  jmp     loc_1800089F0
0x18000886c  mov     rdx, r14; dwBytes
0x18000886f  mov     qword ptr [r15], 0
0x180008876  mov     ecx, 8; dwFlags
0x18000887b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008880  mov     r14, rax
0x180008883  test    rax, rax
0x180008886  jnz     short loc_1800088AA
0x180008888  mov     rcx, [rbp+188h]; this
0x18000888f  lea     r8, aWil; "wil"
0x180008896  mov     esi, 8007000Eh
0x18000889b  mov     edx, 14Bh; void *
0x1800088a0  mov     r9d, esi; char *
0x1800088a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088a8  jmp     short loc_180008916
0x1800088aa  xorps   xmm0, xmm0
0x1800088ad  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800088b3  test    r14b, 3
0x1800088b7  jnz     loc_180008ABD
0x1800088bd  mov     r9, r14
0x1800088c0  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800088c5  shr     r9, 2; unsigned __int64
0x1800088c9  lea     rcx, [rsp+280h+var_250]; this
0x1800088ce  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800088d3  mov     esi, eax
0x1800088d5  test    eax, eax
0x1800088d7  jns     loc_18000895D
0x1800088dd  mov     rcx, [rbp+188h]; this
0x1800088e4  lea     r8, aWil; "wil"
0x1800088eb  mov     r9d, eax; char *
0x1800088ee  mov     edx, 14Eh; void *
0x1800088f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088f8  lea     rcx, [rsp+280h+var_250]; this
0x1800088fd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008902  call    cs:__imp_GetProcessHeap
0x180008908  mov     r8, r14; lpMem
0x18000890b  xor     edx, edx; dwFlags
0x18000890d  mov     rcx, rax; hHeap
0x180008910  call    cs:__imp_HeapFree
0x180008916  mov     rcx, [rbp+188h]; this
0x18000891d  lea     r8, aWil; "wil"
0x180008924  mov     r9d, esi; char *
0x180008927  mov     edx, 137h; void *
0x18000892c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008931  test    rdi, rdi
0x180008934  jz      short loc_180008947
0x180008936  mov     rcx, rdi; hMutex
0x180008939  call    cs:__imp_ReleaseMutex
0x18000893f  test    eax, eax
0x180008941  jz      loc_180008AC3
0x180008947  mov     rcx, rbx; hObject
0x18000894a  call    cs:__imp_CloseHandle
0x180008950  test    eax, eax
0x180008952  jz      loc_180008A59
0x180008958  jmp     loc_180008845
0x18000895d  mov     rax, [rsp+280h+var_250]
0x180008962  lea     rcx, [r14+28h]; void *
0x180008966  mov     [r14+10h], rax
0x18000896a  xor     edx, edx; Val
0x18000896c  mov     rax, [rsp+280h+var_250+8]
0x180008971  mov     r8d, 108h; Size
0x180008977  mov     [r14+18h], rax
0x18000897b  mov     dword ptr [r14], 1
0x180008982  mov     [r14+8], rbx
0x180008986  mov     [rsp+280h+var_250], 0
0x18000898f  mov     [rsp+280h+var_250+8], 0
0x180008998  call    memset_0
0x18000899d  xor     eax, eax
0x18000899f  lea     rcx, [r14+28h]; this
0x1800089a3  mov     [r14+20h], rax
0x1800089a7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800089ac  lea     rbx, [r14+0E8h]
0x1800089b3  xor     r8d, r8d; Flags
0x1800089b6  mov     rcx, rbx; lpCriticalSection
0x1800089b9  xor     edx, edx; dwSpinCount
0x1800089bb  call    cs:__imp_InitializeCriticalSectionEx
0x1800089c1  mov     qword ptr [rbx+28h], 0
0x1800089c9  lea     rcx, [rsp+280h+var_250]; this
0x1800089ce  mov     qword ptr [rbx+30h], 0
0x1800089d6  mov     qword ptr [rbx+38h], 0
0x1800089de  mov     qword ptr [rbx+40h], 0
0x1800089e6  mov     [r15], r14
0x1800089e9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800089ee  xor     ebx, ebx
0x1800089f0  test    rdi, rdi
0x1800089f3  jz      short loc_180008A06
0x1800089f5  mov     rcx, rdi; hMutex
0x1800089f8  call    cs:__imp_ReleaseMutex
0x1800089fe  test    eax, eax
0x180008a00  jz      loc_180008ADC
0x180008a06  test    rbx, rbx
0x180008a09  jz      short loc_180008A18
0x180008a0b  mov     rcx, rbx; hObject
0x180008a0e  call    cs:__imp_CloseHandle
0x180008a14  test    eax, eax
0x180008a16  jz      short loc_180008A40
0x180008a18  xor     eax, eax
0x180008a1a  mov     rcx, [rbp+180h+var_30]
0x180008a21  xor     rcx, rsp; StackCookie
0x180008a24  call    __security_check_cookie
0x180008a29  mov     rbx, [rsp+280h+arg_10]
0x180008a31  add     rsp, 260h
0x180008a38  pop     r15
0x180008a3a  pop     r14
0x180008a3c  pop     rdi
0x180008a3d  pop     rsi
0x180008a3e  pop     rbp
0x180008a3f  retn
0x180008a40  mov     rcx, [rbp+188h]; this
0x180008a47  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a4e  mov     edx, 0A0Bh; void *
0x180008a53  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a59  mov     rcx, [rbp+188h]; this
0x180008a60  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a67  mov     edx, 0A0Bh; void *
0x180008a6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a72  mov     rcx, [rbp+188h]; this
0x180008a79  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a80  mov     edx, 0E01h; void *
0x180008a85  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008a8b  mov     rcx, [rbp+188h]; this
0x180008a92  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a99  mov     edx, 0A15h; void *
0x180008a9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008aa4  mov     rcx, [rbp+188h]; this
0x180008aab  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008ab2  mov     edx, 0A0Bh; void *
0x180008ab7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008abd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008ac3  mov     rcx, [rbp+188h]; this
0x180008aca  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008ad1  mov     edx, 0A15h; void *
0x180008ad6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008adc  mov     rcx, [rbp+188h]; this
0x180008ae3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008aea  mov     edx, 0A15h; void *
0x180008aef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
