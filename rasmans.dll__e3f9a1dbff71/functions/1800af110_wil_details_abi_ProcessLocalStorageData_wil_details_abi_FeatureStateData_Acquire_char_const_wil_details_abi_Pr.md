# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800af110`
- end: `0x1800af4d7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800b08d4`

## callees

- `0x18000e564`
- `0x1800ae3bc`
- `0x1800af110`
- `0x1800b0594`
- `0x1800b0b30`
- `0x1800b2028`
- `0x1800b4ff4`
- `0x1800b6e74`
- `0x1800b7700`
- `0x1800b7fac`
- `0x1800b7fbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af149`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af23a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af2fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af402`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af23a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af2fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af402`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af229`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af350`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af3ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af229`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af350`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af3ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800af1a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800af1a8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800af3b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800af3b9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800af187`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800af187`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af32e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af32e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af320`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af320`

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
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1800af110  mov     [rsp-8+arg_10], rbx
0x1800af115  push    rbp
0x1800af116  push    rsi
0x1800af117  push    rdi
0x1800af118  push    r14
0x1800af11a  push    r15
0x1800af11c  lea     rbp, [rsp-160h]
0x1800af124  sub     rsp, 260h
0x1800af12b  mov     rax, cs:__security_cookie
0x1800af132  xor     rax, rsp
0x1800af135  mov     [rbp+180h+var_30], rax
0x1800af13c  mov     r15, rdx
0x1800af13f  mov     qword ptr [rdx], 0
0x1800af146  mov     rbx, rcx
0x1800af149  call    cs:__imp_GetCurrentProcessId
0x1800af14f  mov     r14d, 130h
0x1800af155  mov     [rsp+280h+var_258], rbx
0x1800af15a  mov     r9d, eax
0x1800af15d  mov     [rsp+280h+var_260], r14d; int
0x1800af162  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800af169  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800af16e  lea     edx, [r14-2Ch]; unsigned __int64
0x1800af172  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800af177  mov     r9d, 1F0001h; dwDesiredAccess
0x1800af17d  lea     rdx, [rsp+280h+Name]; lpName
0x1800af182  xor     r8d, r8d; dwFlags
0x1800af185  xor     ecx, ecx; lpMutexAttributes
0x1800af187  call    cs:__imp_CreateMutexExW
0x1800af18d  mov     rbx, rax
0x1800af190  test    rax, rax
0x1800af193  jnz     short loc_1800AF19F
0x1800af195  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800af19a  jmp     loc_1800AF40E
0x1800af19f  xor     r8d, r8d; bAlertable
0x1800af1a2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800af1a5  mov     rcx, rbx; hHandle
0x1800af1a8  call    cs:__imp_WaitForSingleObjectEx
0x1800af1ae  cmp     eax, 102h
0x1800af1b3  jz      short loc_1800AF1C5
0x1800af1b5  test    eax, 0FFFFFF7Fh
0x1800af1ba  jnz     loc_1800AF458
0x1800af1c0  mov     rdi, rbx
0x1800af1c3  jmp     short loc_1800AF1C7
0x1800af1c5  xor     edi, edi
0x1800af1c7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800af1cc  mov     [rsp+280h+hObject], 0
0x1800af1d5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800af1da  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800af1df  mov     esi, eax
0x1800af1e1  test    eax, eax
0x1800af1e3  jns     short loc_1800AF24F
0x1800af1e5  mov     rcx, [rbp+188h]; this
0x1800af1ec  mov     r9d, eax; char *
0x1800af1ef  mov     edx, 66h ; 'f'; void *
0x1800af1f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af1f9  mov     rcx, [rbp+188h]; this
0x1800af200  mov     r9d, esi; char *
0x1800af203  mov     edx, 6Fh ; 'o'; void *
0x1800af208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af20d  mov     rcx, [rbp+188h]; this
0x1800af214  mov     r9d, esi; char *
0x1800af217  mov     edx, 12Eh; void *
0x1800af21c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af221  test    rdi, rdi
0x1800af224  jz      short loc_1800AF237
0x1800af226  mov     rcx, rdi; hMutex
0x1800af229  call    cs:__imp_ReleaseMutex
0x1800af22f  test    eax, eax
0x1800af231  jz      loc_1800AF465
0x1800af237  mov     rcx, rbx; hObject
0x1800af23a  call    cs:__imp_CloseHandle
0x1800af240  test    eax, eax
0x1800af242  jz      loc_1800AF477
0x1800af248  mov     eax, esi
0x1800af24a  jmp     loc_1800AF40E
0x1800af24f  mov     rax, [rsp+280h+hObject]
0x1800af254  lea     rcx, ds:0[rax*4]
0x1800af25c  test    rcx, rcx
0x1800af25f  jz      short loc_1800AF26F
0x1800af261  mov     [r15], rcx
0x1800af264  mov     eax, [rcx]
0x1800af266  inc     eax
0x1800af268  mov     [rcx], eax
0x1800af26a  jmp     loc_1800AF3E4
0x1800af26f  mov     rdx, r14; dwBytes
0x1800af272  mov     qword ptr [r15], 0
0x1800af279  mov     ecx, 8; dwFlags
0x1800af27e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800af283  mov     r14, rax
0x1800af286  test    rax, rax
0x1800af289  jnz     short loc_1800AF2A9
0x1800af28b  mov     rcx, [rbp+188h]; this
0x1800af292  mov     esi, 8007000Eh
0x1800af297  mov     r9d, esi; char *
0x1800af29a  mov     edx, 14Bh; void *
0x1800af29f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af2a4  jmp     loc_1800AF334
0x1800af2a9  xorps   xmm0, xmm0
0x1800af2ac  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800af2b2  test    r14b, 3
0x1800af2b6  jnz     loc_1800AF489
0x1800af2bc  mov     r9, r14
0x1800af2bf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800af2c4  shr     r9, 2; unsigned __int64
0x1800af2c8  lea     rcx, [rsp+280h+hObject]; this
0x1800af2cd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800af2d2  mov     esi, eax
0x1800af2d4  test    eax, eax
0x1800af2d6  jns     loc_1800AF374
0x1800af2dc  mov     rcx, [rbp+188h]; this
0x1800af2e3  mov     r9d, eax; char *
0x1800af2e6  mov     edx, 14Eh; void *
0x1800af2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af2f0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800af2f5  test    rcx, rcx
0x1800af2f8  jz      short loc_1800AF308
0x1800af2fa  call    cs:__imp_CloseHandle
0x1800af300  test    eax, eax
0x1800af302  jz      loc_1800AF48F
0x1800af308  mov     rcx, [rsp+280h+hObject]; hObject
0x1800af30d  test    rcx, rcx
0x1800af310  jz      short loc_1800AF320
0x1800af312  call    cs:__imp_CloseHandle
0x1800af318  test    eax, eax
0x1800af31a  jz      loc_1800AF4A1
0x1800af320  call    cs:__imp_GetProcessHeap
0x1800af326  mov     r8, r14; lpMem
0x1800af329  xor     edx, edx; dwFlags
0x1800af32b  mov     rcx, rax; hHeap
0x1800af32e  call    cs:__imp_HeapFree
0x1800af334  mov     rcx, [rbp+188h]; this
0x1800af33b  mov     r9d, esi; char *
0x1800af33e  mov     edx, 137h; void *
0x1800af343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af348  test    rdi, rdi
0x1800af34b  jz      short loc_1800AF35E
0x1800af34d  mov     rcx, rdi; hMutex
0x1800af350  call    cs:__imp_ReleaseMutex
0x1800af356  test    eax, eax
0x1800af358  jz      loc_1800AF4B3
0x1800af35e  mov     rcx, rbx; hObject
0x1800af361  call    cs:__imp_CloseHandle
0x1800af367  test    eax, eax
0x1800af369  jz      loc_1800AF446
0x1800af36f  jmp     loc_1800AF248
0x1800af374  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800af379  lea     rcx, [r14+28h]; void *
0x1800af37d  mov     dword ptr [r14], 1
0x1800af384  xor     edx, edx; Val
0x1800af386  mov     [r14+8], rbx
0x1800af38a  mov     r8d, 108h; Size
0x1800af390  movdqu  xmmword ptr [r14+10h], xmm0
0x1800af396  call    memset_0
0x1800af39b  xor     eax, eax
0x1800af39d  lea     rcx, [r14+28h]; this
0x1800af3a1  mov     [r14+20h], rax
0x1800af3a5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800af3aa  lea     rbx, [r14+0E8h]
0x1800af3b1  xor     r8d, r8d; Flags
0x1800af3b4  mov     rcx, rbx; lpCriticalSection
0x1800af3b7  xor     edx, edx; dwSpinCount
0x1800af3b9  call    cs:__imp_InitializeCriticalSectionEx
0x1800af3bf  mov     qword ptr [rbx+28h], 0
0x1800af3c7  mov     qword ptr [rbx+30h], 0
0x1800af3cf  mov     qword ptr [rbx+38h], 0
0x1800af3d7  mov     qword ptr [rbx+40h], 0
0x1800af3df  xor     ebx, ebx
0x1800af3e1  mov     [r15], r14
0x1800af3e4  test    rdi, rdi
0x1800af3e7  jz      short loc_1800AF3FA
0x1800af3e9  mov     rcx, rdi; hMutex
0x1800af3ec  call    cs:__imp_ReleaseMutex
0x1800af3f2  test    eax, eax
0x1800af3f4  jz      loc_1800AF4C5
0x1800af3fa  test    rbx, rbx
0x1800af3fd  jz      short loc_1800AF40C
0x1800af3ff  mov     rcx, rbx; hObject
0x1800af402  call    cs:__imp_CloseHandle
0x1800af408  test    eax, eax
0x1800af40a  jz      short loc_1800AF434
0x1800af40c  xor     eax, eax
0x1800af40e  mov     rcx, [rbp+180h+var_30]
0x1800af415  xor     rcx, rsp; StackCookie
0x1800af418  call    __security_check_cookie
0x1800af41d  mov     rbx, [rsp+280h+arg_10]
0x1800af425  add     rsp, 260h
0x1800af42c  pop     r15
0x1800af42e  pop     r14
0x1800af430  pop     rdi
0x1800af431  pop     rsi
0x1800af432  pop     rbp
0x1800af433  retn
0x1800af434  mov     rcx, [rbp+188h]; this
0x1800af43b  mov     edx, 0A0Bh; void *
0x1800af440  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af446  mov     rcx, [rbp+188h]; this
0x1800af44d  mov     edx, 0A0Bh; void *
0x1800af452  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af458  mov     rcx, [rbp+188h]; this
0x1800af45f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800af465  mov     rcx, [rbp+188h]; this
0x1800af46c  mov     edx, 0A15h; void *
0x1800af471  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af477  mov     rcx, [rbp+188h]; this
0x1800af47e  mov     edx, 0A0Bh; void *
0x1800af483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af489  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800af48f  mov     rcx, [rbp+188h]; this
0x1800af496  mov     edx, 0A0Bh; void *
0x1800af49b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af4a1  mov     rcx, [rbp+188h]; this
0x1800af4a8  mov     edx, 0A0Bh; void *
0x1800af4ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af4b3  mov     rcx, [rbp+188h]; this
0x1800af4ba  mov     edx, 0A15h; void *
0x1800af4bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800af4c5  mov     rcx, [rbp+188h]; this
0x1800af4cc  mov     edx, 0A15h; void *
0x1800af4d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
