# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180070068`
- end: `0x180070465`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180070d24`

## callees

- `0x18005f0c0`
- `0x18005ffc4`
- `0x180061ad4`
- `0x180061dc4`
- `0x180062418`
- `0x180062c98`
- `0x180063094`
- `0x180063a98`
- `0x180063b7c`
- `0x180064008`
- `0x180064018`
- `0x18006bc60`
- `0x180070068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800700df`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800700df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180070100`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180070100`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180070196`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800702d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007036e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180070196`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800702d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007036e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007033b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007033b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007029b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007029b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800702a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800702a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800700a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800700a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007028d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800702e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007028d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800702e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070384`

## string_xrefs

- `0x1800703e1`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180070068  mov     [rsp-8+arg_10], rbx
0x18007006d  push    rbp
0x18007006e  push    rsi
0x18007006f  push    rdi
0x180070070  push    r14
0x180070072  push    r15
0x180070074  lea     rbp, [rsp-160h]
0x18007007c  sub     rsp, 260h
0x180070083  mov     rax, cs:__security_cookie
0x18007008a  xor     rax, rsp
0x18007008d  mov     [rbp+180h+var_30], rax
0x180070094  mov     r15, rdx
0x180070097  mov     qword ptr [rdx], 0
0x18007009e  mov     rbx, rcx
0x1800700a1  call    cs:__imp_GetCurrentProcessId
0x1800700a7  mov     r14d, 130h
0x1800700ad  mov     [rsp+280h+var_258], rbx
0x1800700b2  mov     r9d, eax
0x1800700b5  mov     [rsp+280h+var_260], r14d; int
0x1800700ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800700c1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800700c6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800700ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800700cf  mov     r9d, 1F0001h; dwDesiredAccess
0x1800700d5  lea     rdx, [rsp+280h+Name]; lpName
0x1800700da  xor     r8d, r8d; dwFlags
0x1800700dd  xor     ecx, ecx; lpMutexAttributes
0x1800700df  call    cs:__imp_CreateMutexExW
0x1800700e5  mov     rbx, rax
0x1800700e8  test    rax, rax
0x1800700eb  jnz     short loc_1800700F7
0x1800700ed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800700f2  jmp     loc_180070390
0x1800700f7  xor     r8d, r8d; bAlertable
0x1800700fa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800700fd  mov     rcx, rbx; hHandle
0x180070100  call    cs:__imp_WaitForSingleObjectEx
0x180070106  cmp     eax, 102h
0x18007010b  jz      short loc_18007011D
0x18007010d  test    eax, 0FFFFFF7Fh
0x180070112  jnz     loc_1800703DA
0x180070118  mov     rdi, rbx
0x18007011b  jmp     short loc_18007011F
0x18007011d  xor     edi, edi
0x18007011f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180070124  mov     [rsp+280h+hObject], 0
0x18007012d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180070132  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180070137  mov     esi, eax
0x180070139  test    eax, eax
0x18007013b  jns     short loc_1800701BC
0x18007013d  mov     rcx, [rbp+188h]; this
0x180070144  lea     r8, aWil; "wil"
0x18007014b  mov     r9d, eax; char *
0x18007014e  mov     edx, 66h ; 'f'; void *
0x180070153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070158  mov     rcx, [rbp+188h]; this
0x18007015f  lea     r8, aWil; "wil"
0x180070166  mov     r9d, esi; char *
0x180070169  mov     edx, 6Fh ; 'o'; void *
0x18007016e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070173  mov     rcx, [rbp+188h]; this
0x18007017a  lea     r8, aWil; "wil"
0x180070181  mov     r9d, esi; char *
0x180070184  mov     edx, 12Eh; void *
0x180070189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007018e  test    rdi, rdi
0x180070191  jz      short loc_1800701A4
0x180070193  mov     rcx, rdi; hMutex
0x180070196  call    cs:__imp_ReleaseMutex
0x18007019c  test    eax, eax
0x18007019e  jz      loc_1800703F3
0x1800701a4  mov     rcx, rbx; hObject
0x1800701a7  call    cs:__imp_CloseHandle
0x1800701ad  test    eax, eax
0x1800701af  jz      loc_180070405
0x1800701b5  mov     eax, esi
0x1800701b7  jmp     loc_180070390
0x1800701bc  mov     rax, [rsp+280h+hObject]
0x1800701c1  lea     rcx, ds:0[rax*4]
0x1800701c9  test    rcx, rcx
0x1800701cc  jz      short loc_1800701DC
0x1800701ce  mov     [r15], rcx
0x1800701d1  mov     eax, [rcx]
0x1800701d3  inc     eax
0x1800701d5  mov     [rcx], eax
0x1800701d7  jmp     loc_180070366
0x1800701dc  mov     rdx, r14; dwBytes
0x1800701df  mov     qword ptr [r15], 0
0x1800701e6  mov     ecx, 8; dwFlags
0x1800701eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800701f0  mov     r14, rax
0x1800701f3  test    rax, rax
0x1800701f6  jnz     short loc_18007021D
0x1800701f8  mov     rcx, [rbp+188h]; this
0x1800701ff  lea     r8, aWil; "wil"
0x180070206  mov     esi, 8007000Eh
0x18007020b  mov     edx, 14Bh; void *
0x180070210  mov     r9d, esi; char *
0x180070213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070218  jmp     loc_1800702AF
0x18007021d  xorps   xmm0, xmm0
0x180070220  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180070226  test    r14b, 3
0x18007022a  jnz     loc_180070417
0x180070230  mov     r9, r14
0x180070233  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180070238  shr     r9, 2; unsigned __int64
0x18007023c  lea     rcx, [rsp+280h+hObject]; this
0x180070241  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180070246  mov     esi, eax
0x180070248  test    eax, eax
0x18007024a  jns     loc_1800702F6
0x180070250  mov     rcx, [rbp+188h]; this
0x180070257  lea     r8, aWil; "wil"
0x18007025e  mov     r9d, eax; char *
0x180070261  mov     edx, 14Eh; void *
0x180070266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007026b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180070270  test    rcx, rcx
0x180070273  jz      short loc_180070283
0x180070275  call    cs:__imp_CloseHandle
0x18007027b  test    eax, eax
0x18007027d  jz      loc_18007041D
0x180070283  mov     rcx, [rsp+280h+hObject]; hObject
0x180070288  test    rcx, rcx
0x18007028b  jz      short loc_18007029B
0x18007028d  call    cs:__imp_CloseHandle
0x180070293  test    eax, eax
0x180070295  jz      loc_18007042F
0x18007029b  call    cs:__imp_GetProcessHeap
0x1800702a1  mov     r8, r14; lpMem
0x1800702a4  xor     edx, edx; dwFlags
0x1800702a6  mov     rcx, rax; hHeap
0x1800702a9  call    cs:__imp_HeapFree
0x1800702af  mov     rcx, [rbp+188h]; this
0x1800702b6  lea     r8, aWil; "wil"
0x1800702bd  mov     r9d, esi; char *
0x1800702c0  mov     edx, 137h; void *
0x1800702c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800702ca  test    rdi, rdi
0x1800702cd  jz      short loc_1800702E0
0x1800702cf  mov     rcx, rdi; hMutex
0x1800702d2  call    cs:__imp_ReleaseMutex
0x1800702d8  test    eax, eax
0x1800702da  jz      loc_180070441
0x1800702e0  mov     rcx, rbx; hObject
0x1800702e3  call    cs:__imp_CloseHandle
0x1800702e9  test    eax, eax
0x1800702eb  jz      loc_1800703C8
0x1800702f1  jmp     loc_1800701B5
0x1800702f6  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800702fb  lea     rcx, [r14+28h]; void *
0x1800702ff  mov     dword ptr [r14], 1
0x180070306  xor     edx, edx; Val
0x180070308  mov     [r14+8], rbx
0x18007030c  mov     r8d, 108h; Size
0x180070312  movdqu  xmmword ptr [r14+10h], xmm0
0x180070318  call    memset_0
0x18007031d  xor     eax, eax
0x18007031f  lea     rcx, [r14+28h]; this
0x180070323  mov     [r14+20h], rax
0x180070327  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18007032c  lea     rbx, [r14+0E8h]
0x180070333  xor     r8d, r8d; Flags
0x180070336  mov     rcx, rbx; lpCriticalSection
0x180070339  xor     edx, edx; dwSpinCount
0x18007033b  call    cs:__imp_InitializeCriticalSectionEx
0x180070341  mov     qword ptr [rbx+28h], 0
0x180070349  mov     qword ptr [rbx+30h], 0
0x180070351  mov     qword ptr [rbx+38h], 0
0x180070359  mov     qword ptr [rbx+40h], 0
0x180070361  xor     ebx, ebx
0x180070363  mov     [r15], r14
0x180070366  test    rdi, rdi
0x180070369  jz      short loc_18007037C
0x18007036b  mov     rcx, rdi; hMutex
0x18007036e  call    cs:__imp_ReleaseMutex
0x180070374  test    eax, eax
0x180070376  jz      loc_180070453
0x18007037c  test    rbx, rbx
0x18007037f  jz      short loc_18007038E
0x180070381  mov     rcx, rbx; hObject
0x180070384  call    cs:__imp_CloseHandle
0x18007038a  test    eax, eax
0x18007038c  jz      short loc_1800703B6
0x18007038e  xor     eax, eax
0x180070390  mov     rcx, [rbp+180h+var_30]
0x180070397  xor     rcx, rsp; StackCookie
0x18007039a  call    __security_check_cookie
0x18007039f  mov     rbx, [rsp+280h+arg_10]
0x1800703a7  add     rsp, 260h
0x1800703ae  pop     r15
0x1800703b0  pop     r14
0x1800703b2  pop     rdi
0x1800703b3  pop     rsi
0x1800703b4  pop     rbp
0x1800703b5  retn
0x1800703b6  mov     rcx, [rbp+188h]; this
0x1800703bd  mov     edx, 0A0Bh; void *
0x1800703c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800703c8  mov     rcx, [rbp+188h]; this
0x1800703cf  mov     edx, 0A0Bh; void *
0x1800703d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800703da  mov     rcx, [rbp+188h]; this
0x1800703e1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800703e8  mov     edx, 0E01h; void *
0x1800703ed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800703f3  mov     rcx, [rbp+188h]; this
0x1800703fa  mov     edx, 0A15h; void *
0x1800703ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070405  mov     rcx, [rbp+188h]; this
0x18007040c  mov     edx, 0A0Bh; void *
0x180070411  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070417  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18007041d  mov     rcx, [rbp+188h]; this
0x180070424  mov     edx, 0A0Bh; void *
0x180070429  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18007042f  mov     rcx, [rbp+188h]; this
0x180070436  mov     edx, 0A0Bh; void *
0x18007043b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070441  mov     rcx, [rbp+188h]; this
0x180070448  mov     edx, 0A15h; void *
0x18007044d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070453  mov     rcx, [rbp+188h]; this
0x18007045a  mov     edx, 0A15h; void *
0x18007045f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
