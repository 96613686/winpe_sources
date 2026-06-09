# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800047e8`
- end: `0x180004bd9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004ee4`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x180003954`
- `0x1800047e8`
- `0x180004be0`
- `0x180005138`
- `0x180005a68`
- `0x1800068b8`
- `0x1800081c4`
- `0x1800090ac`
- `0x18000969c`
- `0x18000a12c`
- `0x18000a13c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a29`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000485f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000485f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004916`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a52`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004916`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a52`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004abb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004abb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004880`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b04`

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
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x1800047e8  mov     [rsp-8+arg_10], rbx
0x1800047ed  push    rbp
0x1800047ee  push    rsi
0x1800047ef  push    rdi
0x1800047f0  push    r14
0x1800047f2  push    r15
0x1800047f4  lea     rbp, [rsp-160h]
0x1800047fc  sub     rsp, 260h
0x180004803  mov     rax, cs:__security_cookie
0x18000480a  xor     rax, rsp
0x18000480d  mov     [rbp+180h+var_30], rax
0x180004814  mov     r15, rdx
0x180004817  mov     qword ptr [rdx], 0
0x18000481e  mov     rbx, rcx
0x180004821  call    cs:__imp_GetCurrentProcessId
0x180004827  mov     r14d, 130h
0x18000482d  mov     [rsp+280h+var_258], rbx
0x180004832  mov     r9d, eax
0x180004835  mov     [rsp+280h+var_260], r14d; int
0x18000483a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004841  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004846  lea     edx, [r14-2Ch]; unsigned __int64
0x18000484a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000484f  mov     r9d, 1F0001h; dwDesiredAccess
0x180004855  lea     rdx, [rsp+280h+Name]; lpName
0x18000485a  xor     r8d, r8d; dwFlags
0x18000485d  xor     ecx, ecx; lpMutexAttributes
0x18000485f  call    cs:__imp_CreateMutexExW
0x180004865  mov     rbx, rax
0x180004868  test    rax, rax
0x18000486b  jnz     short loc_180004877
0x18000486d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004872  jmp     loc_180004B10
0x180004877  xor     r8d, r8d; bAlertable
0x18000487a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000487d  mov     rcx, rbx; hHandle
0x180004880  call    cs:__imp_WaitForSingleObjectEx
0x180004886  cmp     eax, 102h
0x18000488b  jz      short loc_18000489D
0x18000488d  test    eax, 0FFFFFF7Fh
0x180004892  jnz     loc_180004B5A
0x180004898  mov     rdi, rbx
0x18000489b  jmp     short loc_18000489F
0x18000489d  xor     edi, edi
0x18000489f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800048a4  mov     [rsp+280h+hObject], 0
0x1800048ad  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800048b2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800048b7  mov     esi, eax
0x1800048b9  test    eax, eax
0x1800048bb  jns     short loc_18000493C
0x1800048bd  mov     rcx, [rbp+188h]; this
0x1800048c4  lea     r8, aWil; "wil"
0x1800048cb  mov     r9d, eax; char *
0x1800048ce  mov     edx, 66h ; 'f'; void *
0x1800048d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048d8  mov     rcx, [rbp+188h]; this
0x1800048df  lea     r8, aWil; "wil"
0x1800048e6  mov     r9d, esi; char *
0x1800048e9  mov     edx, 6Fh ; 'o'; void *
0x1800048ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048f3  mov     rcx, [rbp+188h]; this
0x1800048fa  lea     r8, aWil; "wil"
0x180004901  mov     r9d, esi; char *
0x180004904  mov     edx, 12Eh; void *
0x180004909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000490e  test    rdi, rdi
0x180004911  jz      short loc_180004924
0x180004913  mov     rcx, rdi; hMutex
0x180004916  call    cs:__imp_ReleaseMutex
0x18000491c  test    eax, eax
0x18000491e  jz      loc_180004B67
0x180004924  mov     rcx, rbx; hObject
0x180004927  call    cs:__imp_CloseHandle
0x18000492d  test    eax, eax
0x18000492f  jz      loc_180004B79
0x180004935  mov     eax, esi
0x180004937  jmp     loc_180004B10
0x18000493c  mov     rax, [rsp+280h+hObject]
0x180004941  lea     rcx, ds:0[rax*4]
0x180004949  test    rcx, rcx
0x18000494c  jz      short loc_18000495C
0x18000494e  mov     [r15], rcx
0x180004951  mov     eax, [rcx]
0x180004953  inc     eax
0x180004955  mov     [rcx], eax
0x180004957  jmp     loc_180004AE6
0x18000495c  mov     rdx, r14; dwBytes
0x18000495f  mov     qword ptr [r15], 0
0x180004966  mov     ecx, 8; dwFlags
0x18000496b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004970  mov     r14, rax
0x180004973  test    rax, rax
0x180004976  jnz     short loc_18000499D
0x180004978  mov     rcx, [rbp+188h]; this
0x18000497f  lea     r8, aWil; "wil"
0x180004986  mov     esi, 8007000Eh
0x18000498b  mov     edx, 14Bh; void *
0x180004990  mov     r9d, esi; char *
0x180004993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004998  jmp     loc_180004A2F
0x18000499d  xorps   xmm0, xmm0
0x1800049a0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800049a6  test    r14b, 3
0x1800049aa  jnz     loc_180004B8B
0x1800049b0  mov     r9, r14
0x1800049b3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800049b8  shr     r9, 2; unsigned __int64
0x1800049bc  lea     rcx, [rsp+280h+hObject]; this
0x1800049c1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800049c6  mov     esi, eax
0x1800049c8  test    eax, eax
0x1800049ca  jns     loc_180004A76
0x1800049d0  mov     rcx, [rbp+188h]; this
0x1800049d7  lea     r8, aWil; "wil"
0x1800049de  mov     r9d, eax; char *
0x1800049e1  mov     edx, 14Eh; void *
0x1800049e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049eb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800049f0  test    rcx, rcx
0x1800049f3  jz      short loc_180004A03
0x1800049f5  call    cs:__imp_CloseHandle
0x1800049fb  test    eax, eax
0x1800049fd  jz      loc_180004B91
0x180004a03  mov     rcx, [rsp+280h+hObject]; hObject
0x180004a08  test    rcx, rcx
0x180004a0b  jz      short loc_180004A1B
0x180004a0d  call    cs:__imp_CloseHandle
0x180004a13  test    eax, eax
0x180004a15  jz      loc_180004BA3
0x180004a1b  call    cs:__imp_GetProcessHeap
0x180004a21  mov     r8, r14; lpMem
0x180004a24  xor     edx, edx; dwFlags
0x180004a26  mov     rcx, rax; hHeap
0x180004a29  call    cs:__imp_HeapFree
0x180004a2f  mov     rcx, [rbp+188h]; this
0x180004a36  lea     r8, aWil; "wil"
0x180004a3d  mov     r9d, esi; char *
0x180004a40  mov     edx, 137h; void *
0x180004a45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a4a  test    rdi, rdi
0x180004a4d  jz      short loc_180004A60
0x180004a4f  mov     rcx, rdi; hMutex
0x180004a52  call    cs:__imp_ReleaseMutex
0x180004a58  test    eax, eax
0x180004a5a  jz      loc_180004BB5
0x180004a60  mov     rcx, rbx; hObject
0x180004a63  call    cs:__imp_CloseHandle
0x180004a69  test    eax, eax
0x180004a6b  jz      loc_180004B48
0x180004a71  jmp     loc_180004935
0x180004a76  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004a7b  lea     rcx, [r14+28h]; void *
0x180004a7f  mov     dword ptr [r14], 1
0x180004a86  xor     edx, edx; Val
0x180004a88  mov     [r14+8], rbx
0x180004a8c  mov     r8d, 108h; Size
0x180004a92  movdqu  xmmword ptr [r14+10h], xmm0
0x180004a98  call    memset_0
0x180004a9d  xor     eax, eax
0x180004a9f  lea     rcx, [r14+28h]; this
0x180004aa3  mov     [r14+20h], rax
0x180004aa7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004aac  lea     rbx, [r14+0E8h]
0x180004ab3  xor     r8d, r8d; Flags
0x180004ab6  mov     rcx, rbx; lpCriticalSection
0x180004ab9  xor     edx, edx; dwSpinCount
0x180004abb  call    cs:__imp_InitializeCriticalSectionEx
0x180004ac1  mov     qword ptr [rbx+28h], 0
0x180004ac9  mov     qword ptr [rbx+30h], 0
0x180004ad1  mov     qword ptr [rbx+38h], 0
0x180004ad9  mov     qword ptr [rbx+40h], 0
0x180004ae1  xor     ebx, ebx
0x180004ae3  mov     [r15], r14
0x180004ae6  test    rdi, rdi
0x180004ae9  jz      short loc_180004AFC
0x180004aeb  mov     rcx, rdi; hMutex
0x180004aee  call    cs:__imp_ReleaseMutex
0x180004af4  test    eax, eax
0x180004af6  jz      loc_180004BC7
0x180004afc  test    rbx, rbx
0x180004aff  jz      short loc_180004B0E
0x180004b01  mov     rcx, rbx; hObject
0x180004b04  call    cs:__imp_CloseHandle
0x180004b0a  test    eax, eax
0x180004b0c  jz      short loc_180004B36
0x180004b0e  xor     eax, eax
0x180004b10  mov     rcx, [rbp+180h+var_30]
0x180004b17  xor     rcx, rsp; StackCookie
0x180004b1a  call    __security_check_cookie
0x180004b1f  mov     rbx, [rsp+280h+arg_10]
0x180004b27  add     rsp, 260h
0x180004b2e  pop     r15
0x180004b30  pop     r14
0x180004b32  pop     rdi
0x180004b33  pop     rsi
0x180004b34  pop     rbp
0x180004b35  retn
0x180004b36  mov     rcx, [rbp+188h]; this
0x180004b3d  mov     edx, 0A0Bh; void *
0x180004b42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b48  mov     rcx, [rbp+188h]; this
0x180004b4f  mov     edx, 0A0Bh; void *
0x180004b54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b5a  mov     rcx, [rbp+188h]; this
0x180004b61  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004b67  mov     rcx, [rbp+188h]; this
0x180004b6e  mov     edx, 0A15h; void *
0x180004b73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b79  mov     rcx, [rbp+188h]; this
0x180004b80  mov     edx, 0A0Bh; void *
0x180004b85  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b8b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b91  mov     rcx, [rbp+188h]; this
0x180004b98  mov     edx, 0A0Bh; void *
0x180004b9d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ba3  mov     rcx, [rbp+188h]; this
0x180004baa  mov     edx, 0A0Bh; void *
0x180004baf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004bb5  mov     rcx, [rbp+188h]; this
0x180004bbc  mov     edx, 0A15h; void *
0x180004bc1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004bc7  mov     rcx, [rbp+188h]; this
0x180004bce  mov     edx, 0A15h; void *
0x180004bd3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
