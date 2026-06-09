# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800034b8`
- end: `0x18000387f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180003d34`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x1800029bc`
- `0x1800034b8`
- `0x1800038a4`
- `0x180003ec4`
- `0x1800047e8`
- `0x1800053f8`
- `0x1800067e0`
- `0x180006d20`
- `0x180007048`
- `0x18000782c`
- `0x18000783c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000352f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000352f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003550`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003550`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003794`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003794`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003761`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037aa`

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
0x1800034f7  mov     r14d, 130h
0x1800034fd  mov     [rsp+280h+var_258], rbx
0x180003502  mov     r9d, eax
0x180003505  mov     [rsp+280h+var_260], r14d; int
0x18000350a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003511  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003516  lea     edx, [r14-2Ch]; unsigned __int64
0x18000351a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000351f  mov     r9d, 1F0001h; dwDesiredAccess
0x180003525  lea     rdx, [rsp+280h+Name]; lpName
0x18000352a  xor     r8d, r8d; dwFlags
0x18000352d  xor     ecx, ecx; lpMutexAttributes
0x18000352f  call    cs:__imp_CreateMutexExW
0x180003535  mov     rbx, rax
0x180003538  test    rax, rax
0x18000353b  jnz     short loc_180003547
0x18000353d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003542  jmp     loc_1800037B6
0x180003547  xor     r8d, r8d; bAlertable
0x18000354a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000354d  mov     rcx, rbx; hHandle
0x180003550  call    cs:__imp_WaitForSingleObjectEx
0x180003556  cmp     eax, 102h
0x18000355b  jz      short loc_18000356D
0x18000355d  test    eax, 0FFFFFF7Fh
0x180003562  jnz     loc_180003800
0x180003568  mov     rdi, rbx
0x18000356b  jmp     short loc_18000356F
0x18000356d  xor     edi, edi
0x18000356f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003574  mov     [rsp+280h+hObject], 0
0x18000357d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003582  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003587  mov     esi, eax
0x180003589  test    eax, eax
0x18000358b  jns     short loc_1800035F7
0x18000358d  mov     rcx, [rbp+188h]; this
0x180003594  mov     r9d, eax; char *
0x180003597  mov     edx, 66h ; 'f'; void *
0x18000359c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035a1  mov     rcx, [rbp+188h]; this
0x1800035a8  mov     r9d, esi; char *
0x1800035ab  mov     edx, 6Fh ; 'o'; void *
0x1800035b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035b5  mov     rcx, [rbp+188h]; this
0x1800035bc  mov     r9d, esi; char *
0x1800035bf  mov     edx, 12Eh; void *
0x1800035c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035c9  test    rdi, rdi
0x1800035cc  jz      short loc_1800035DF
0x1800035ce  mov     rcx, rdi; hMutex
0x1800035d1  call    cs:__imp_ReleaseMutex
0x1800035d7  test    eax, eax
0x1800035d9  jz      loc_18000380D
0x1800035df  mov     rcx, rbx; hObject
0x1800035e2  call    cs:__imp_CloseHandle
0x1800035e8  test    eax, eax
0x1800035ea  jz      loc_18000381F
0x1800035f0  mov     eax, esi
0x1800035f2  jmp     loc_1800037B6
0x1800035f7  mov     rax, [rsp+280h+hObject]
0x1800035fc  lea     rcx, ds:0[rax*4]
0x180003604  test    rcx, rcx
0x180003607  jz      short loc_180003617
0x180003609  mov     [r15], rcx
0x18000360c  mov     eax, [rcx]
0x18000360e  inc     eax
0x180003610  mov     [rcx], eax
0x180003612  jmp     loc_18000378C
0x180003617  mov     rdx, r14; dwBytes
0x18000361a  mov     qword ptr [r15], 0
0x180003621  mov     ecx, 8; dwFlags
0x180003626  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000362b  mov     r14, rax
0x18000362e  test    rax, rax
0x180003631  jnz     short loc_180003651
0x180003633  mov     rcx, [rbp+188h]; this
0x18000363a  mov     esi, 8007000Eh
0x18000363f  mov     r9d, esi; char *
0x180003642  mov     edx, 14Bh; void *
0x180003647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000364c  jmp     loc_1800036DC
0x180003651  xorps   xmm0, xmm0
0x180003654  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000365a  test    r14b, 3
0x18000365e  jnz     loc_180003831
0x180003664  mov     r9, r14
0x180003667  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000366c  shr     r9, 2; unsigned __int64
0x180003670  lea     rcx, [rsp+280h+hObject]; this
0x180003675  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000367a  mov     esi, eax
0x18000367c  test    eax, eax
0x18000367e  jns     loc_18000371C
0x180003684  mov     rcx, [rbp+188h]; this
0x18000368b  mov     r9d, eax; char *
0x18000368e  mov     edx, 14Eh; void *
0x180003693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003698  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000369d  test    rcx, rcx
0x1800036a0  jz      short loc_1800036B0
0x1800036a2  call    cs:__imp_CloseHandle
0x1800036a8  test    eax, eax
0x1800036aa  jz      loc_180003837
0x1800036b0  mov     rcx, [rsp+280h+hObject]; hObject
0x1800036b5  test    rcx, rcx
0x1800036b8  jz      short loc_1800036C8
0x1800036ba  call    cs:__imp_CloseHandle
0x1800036c0  test    eax, eax
0x1800036c2  jz      loc_180003849
0x1800036c8  call    cs:__imp_GetProcessHeap
0x1800036ce  mov     r8, r14; lpMem
0x1800036d1  xor     edx, edx; dwFlags
0x1800036d3  mov     rcx, rax; hHeap
0x1800036d6  call    cs:__imp_HeapFree
0x1800036dc  mov     rcx, [rbp+188h]; this
0x1800036e3  mov     r9d, esi; char *
0x1800036e6  mov     edx, 137h; void *
0x1800036eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036f0  test    rdi, rdi
0x1800036f3  jz      short loc_180003706
0x1800036f5  mov     rcx, rdi; hMutex
0x1800036f8  call    cs:__imp_ReleaseMutex
0x1800036fe  test    eax, eax
0x180003700  jz      loc_18000385B
0x180003706  mov     rcx, rbx; hObject
0x180003709  call    cs:__imp_CloseHandle
0x18000370f  test    eax, eax
0x180003711  jz      loc_1800037EE
0x180003717  jmp     loc_1800035F0
0x18000371c  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003721  lea     rcx, [r14+28h]; void *
0x180003725  mov     dword ptr [r14], 1
0x18000372c  xor     edx, edx; Val
0x18000372e  mov     [r14+8], rbx
0x180003732  mov     r8d, 108h; Size
0x180003738  movdqu  xmmword ptr [r14+10h], xmm0
0x18000373e  call    memset_0
0x180003743  xor     eax, eax
0x180003745  lea     rcx, [r14+28h]; this
0x180003749  mov     [r14+20h], rax
0x18000374d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003752  lea     rbx, [r14+0E8h]
0x180003759  xor     r8d, r8d; Flags
0x18000375c  mov     rcx, rbx; lpCriticalSection
0x18000375f  xor     edx, edx; dwSpinCount
0x180003761  call    cs:__imp_InitializeCriticalSectionEx
0x180003767  mov     qword ptr [rbx+28h], 0
0x18000376f  mov     qword ptr [rbx+30h], 0
0x180003777  mov     qword ptr [rbx+38h], 0
0x18000377f  mov     qword ptr [rbx+40h], 0
0x180003787  xor     ebx, ebx
0x180003789  mov     [r15], r14
0x18000378c  test    rdi, rdi
0x18000378f  jz      short loc_1800037A2
0x180003791  mov     rcx, rdi; hMutex
0x180003794  call    cs:__imp_ReleaseMutex
0x18000379a  test    eax, eax
0x18000379c  jz      loc_18000386D
0x1800037a2  test    rbx, rbx
0x1800037a5  jz      short loc_1800037B4
0x1800037a7  mov     rcx, rbx; hObject
0x1800037aa  call    cs:__imp_CloseHandle
0x1800037b0  test    eax, eax
0x1800037b2  jz      short loc_1800037DC
0x1800037b4  xor     eax, eax
0x1800037b6  mov     rcx, [rbp+180h+var_30]
0x1800037bd  xor     rcx, rsp; StackCookie
0x1800037c0  call    __security_check_cookie
0x1800037c5  mov     rbx, [rsp+280h+arg_10]
0x1800037cd  add     rsp, 260h
0x1800037d4  pop     r15
0x1800037d6  pop     r14
0x1800037d8  pop     rdi
0x1800037d9  pop     rsi
0x1800037da  pop     rbp
0x1800037db  retn
0x1800037dc  mov     rcx, [rbp+188h]; this
0x1800037e3  mov     edx, 0A0Bh; void *
0x1800037e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037ee  mov     rcx, [rbp+188h]; this
0x1800037f5  mov     edx, 0A0Bh; void *
0x1800037fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003800  mov     rcx, [rbp+188h]; this
0x180003807  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000380d  mov     rcx, [rbp+188h]; this
0x180003814  mov     edx, 0A15h; void *
0x180003819  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000381f  mov     rcx, [rbp+188h]; this
0x180003826  mov     edx, 0A0Bh; void *
0x18000382b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003831  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003837  mov     rcx, [rbp+188h]; this
0x18000383e  mov     edx, 0A0Bh; void *
0x180003843  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003849  mov     rcx, [rbp+188h]; this
0x180003850  mov     edx, 0A0Bh; void *
0x180003855  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000385b  mov     rcx, [rbp+188h]; this
0x180003862  mov     edx, 0A15h; void *
0x180003867  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000386d  mov     rcx, [rbp+188h]; this
0x180003874  mov     edx, 0A15h; void *
0x180003879  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
