# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000500c`
- end: `0x1800053d3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000657c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000403c`
- `0x18000500c`
- `0x180005ea8`
- `0x180006a28`
- `0x1800077ac`
- `0x180008b94`
- `0x180009f0c`
- `0x18000af00`
- `0x18000b27c`
- `0x18000f33c`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005083`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005083`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800050a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800050a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000524c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000524c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800052b5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800052b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000521c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000521c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000522a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000522a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000520e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000520e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000525d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052fe`

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
  __int64 v25; // r8
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
0x18000500c  mov     [rsp-8+arg_10], rbx
0x180005011  push    rbp
0x180005012  push    rsi
0x180005013  push    rdi
0x180005014  push    r14
0x180005016  push    r15
0x180005018  lea     rbp, [rsp-160h]
0x180005020  sub     rsp, 260h
0x180005027  mov     rax, cs:__security_cookie
0x18000502e  xor     rax, rsp
0x180005031  mov     [rbp+180h+var_30], rax
0x180005038  mov     r15, rdx
0x18000503b  mov     qword ptr [rdx], 0
0x180005042  mov     rbx, rcx
0x180005045  call    cs:__imp_GetCurrentProcessId
0x18000504b  mov     r14d, 130h
0x180005051  mov     [rsp+280h+var_258], rbx
0x180005056  mov     r9d, eax
0x180005059  mov     [rsp+280h+var_260], r14d; int
0x18000505e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005065  lea     rcx, [rsp+280h+Name]; Buffer
0x18000506a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000506e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005073  mov     r9d, 1F0001h; dwDesiredAccess
0x180005079  lea     rdx, [rsp+280h+Name]; lpName
0x18000507e  xor     r8d, r8d; dwFlags
0x180005081  xor     ecx, ecx; lpMutexAttributes
0x180005083  call    cs:__imp_CreateMutexExW
0x180005089  mov     rbx, rax
0x18000508c  test    rax, rax
0x18000508f  jnz     short loc_18000509B
0x180005091  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005096  jmp     loc_18000530A
0x18000509b  xor     r8d, r8d; bAlertable
0x18000509e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800050a1  mov     rcx, rbx; hHandle
0x1800050a4  call    cs:__imp_WaitForSingleObjectEx
0x1800050aa  cmp     eax, 102h
0x1800050af  jz      short loc_1800050C1
0x1800050b1  test    eax, 0FFFFFF7Fh
0x1800050b6  jnz     loc_180005354
0x1800050bc  mov     rdi, rbx
0x1800050bf  jmp     short loc_1800050C3
0x1800050c1  xor     edi, edi
0x1800050c3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800050c8  mov     [rsp+280h+hObject], 0
0x1800050d1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800050d6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800050db  mov     esi, eax
0x1800050dd  test    eax, eax
0x1800050df  jns     short loc_18000514B
0x1800050e1  mov     rcx, [rbp+188h]; this
0x1800050e8  mov     r9d, eax; char *
0x1800050eb  mov     edx, 66h ; 'f'; void *
0x1800050f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050f5  mov     rcx, [rbp+188h]; this
0x1800050fc  mov     r9d, esi; char *
0x1800050ff  mov     edx, 6Fh ; 'o'; void *
0x180005104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005109  mov     rcx, [rbp+188h]; this
0x180005110  mov     r9d, esi; char *
0x180005113  mov     edx, 12Eh; void *
0x180005118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000511d  test    rdi, rdi
0x180005120  jz      short loc_180005133
0x180005122  mov     rcx, rdi; hMutex
0x180005125  call    cs:__imp_ReleaseMutex
0x18000512b  test    eax, eax
0x18000512d  jz      loc_180005361
0x180005133  mov     rcx, rbx; hObject
0x180005136  call    cs:__imp_CloseHandle
0x18000513c  test    eax, eax
0x18000513e  jz      loc_180005373
0x180005144  mov     eax, esi
0x180005146  jmp     loc_18000530A
0x18000514b  mov     rax, [rsp+280h+hObject]
0x180005150  lea     rcx, ds:0[rax*4]
0x180005158  test    rcx, rcx
0x18000515b  jz      short loc_18000516B
0x18000515d  mov     [r15], rcx
0x180005160  mov     eax, [rcx]
0x180005162  inc     eax
0x180005164  mov     [rcx], eax
0x180005166  jmp     loc_1800052E0
0x18000516b  mov     rdx, r14; dwBytes
0x18000516e  mov     qword ptr [r15], 0
0x180005175  mov     ecx, 8; dwFlags
0x18000517a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000517f  mov     r14, rax
0x180005182  test    rax, rax
0x180005185  jnz     short loc_1800051A5
0x180005187  mov     rcx, [rbp+188h]; this
0x18000518e  mov     esi, 8007000Eh
0x180005193  mov     r9d, esi; char *
0x180005196  mov     edx, 14Bh; void *
0x18000519b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051a0  jmp     loc_180005230
0x1800051a5  xorps   xmm0, xmm0
0x1800051a8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800051ae  test    r14b, 3
0x1800051b2  jnz     loc_180005385
0x1800051b8  mov     r9, r14
0x1800051bb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800051c0  shr     r9, 2; unsigned __int64
0x1800051c4  lea     rcx, [rsp+280h+hObject]; this
0x1800051c9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800051ce  mov     esi, eax
0x1800051d0  test    eax, eax
0x1800051d2  jns     loc_180005270
0x1800051d8  mov     rcx, [rbp+188h]; this
0x1800051df  mov     r9d, eax; char *
0x1800051e2  mov     edx, 14Eh; void *
0x1800051e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051ec  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800051f1  test    rcx, rcx
0x1800051f4  jz      short loc_180005204
0x1800051f6  call    cs:__imp_CloseHandle
0x1800051fc  test    eax, eax
0x1800051fe  jz      loc_18000538B
0x180005204  mov     rcx, [rsp+280h+hObject]; hObject
0x180005209  test    rcx, rcx
0x18000520c  jz      short loc_18000521C
0x18000520e  call    cs:__imp_CloseHandle
0x180005214  test    eax, eax
0x180005216  jz      loc_18000539D
0x18000521c  call    cs:__imp_GetProcessHeap
0x180005222  mov     r8, r14; lpMem
0x180005225  xor     edx, edx; dwFlags
0x180005227  mov     rcx, rax; hHeap
0x18000522a  call    cs:__imp_HeapFree
0x180005230  mov     rcx, [rbp+188h]; this
0x180005237  mov     r9d, esi; char *
0x18000523a  mov     edx, 137h; void *
0x18000523f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005244  test    rdi, rdi
0x180005247  jz      short loc_18000525A
0x180005249  mov     rcx, rdi; hMutex
0x18000524c  call    cs:__imp_ReleaseMutex
0x180005252  test    eax, eax
0x180005254  jz      loc_1800053AF
0x18000525a  mov     rcx, rbx; hObject
0x18000525d  call    cs:__imp_CloseHandle
0x180005263  test    eax, eax
0x180005265  jz      loc_180005342
0x18000526b  jmp     loc_180005144
0x180005270  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005275  lea     rcx, [r14+28h]; void *
0x180005279  mov     dword ptr [r14], 1
0x180005280  xor     edx, edx; Val
0x180005282  mov     [r14+8], rbx
0x180005286  mov     r8d, 108h; Size
0x18000528c  movdqu  xmmword ptr [r14+10h], xmm0
0x180005292  call    memset_0
0x180005297  xor     eax, eax
0x180005299  lea     rcx, [r14+28h]; this
0x18000529d  mov     [r14+20h], rax
0x1800052a1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800052a6  lea     rbx, [r14+0E8h]
0x1800052ad  xor     r8d, r8d; Flags
0x1800052b0  mov     rcx, rbx; lpCriticalSection
0x1800052b3  xor     edx, edx; dwSpinCount
0x1800052b5  call    cs:__imp_InitializeCriticalSectionEx
0x1800052bb  mov     qword ptr [rbx+28h], 0
0x1800052c3  mov     qword ptr [rbx+30h], 0
0x1800052cb  mov     qword ptr [rbx+38h], 0
0x1800052d3  mov     qword ptr [rbx+40h], 0
0x1800052db  xor     ebx, ebx
0x1800052dd  mov     [r15], r14
0x1800052e0  test    rdi, rdi
0x1800052e3  jz      short loc_1800052F6
0x1800052e5  mov     rcx, rdi; hMutex
0x1800052e8  call    cs:__imp_ReleaseMutex
0x1800052ee  test    eax, eax
0x1800052f0  jz      loc_1800053C1
0x1800052f6  test    rbx, rbx
0x1800052f9  jz      short loc_180005308
0x1800052fb  mov     rcx, rbx; hObject
0x1800052fe  call    cs:__imp_CloseHandle
0x180005304  test    eax, eax
0x180005306  jz      short loc_180005330
0x180005308  xor     eax, eax
0x18000530a  mov     rcx, [rbp+180h+var_30]
0x180005311  xor     rcx, rsp; StackCookie
0x180005314  call    __security_check_cookie
0x180005319  mov     rbx, [rsp+280h+arg_10]
0x180005321  add     rsp, 260h
0x180005328  pop     r15
0x18000532a  pop     r14
0x18000532c  pop     rdi
0x18000532d  pop     rsi
0x18000532e  pop     rbp
0x18000532f  retn
0x180005330  mov     rcx, [rbp+188h]; this
0x180005337  mov     edx, 0A0Bh; void *
0x18000533c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005342  mov     rcx, [rbp+188h]; this
0x180005349  mov     edx, 0A0Bh; void *
0x18000534e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005354  mov     rcx, [rbp+188h]; this
0x18000535b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005361  mov     rcx, [rbp+188h]; this
0x180005368  mov     edx, 0A15h; void *
0x18000536d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005373  mov     rcx, [rbp+188h]; this
0x18000537a  mov     edx, 0A0Bh; void *
0x18000537f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005385  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000538b  mov     rcx, [rbp+188h]; this
0x180005392  mov     edx, 0A0Bh; void *
0x180005397  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000539d  mov     rcx, [rbp+188h]; this
0x1800053a4  mov     edx, 0A0Bh; void *
0x1800053a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053af  mov     rcx, [rbp+188h]; this
0x1800053b6  mov     edx, 0A15h; void *
0x1800053bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053c1  mov     rcx, [rbp+188h]; this
0x1800053c8  mov     edx, 0A15h; void *
0x1800053cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
