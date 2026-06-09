# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180012254`
- end: `0x18001265e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800170f4`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180004a78`
- `0x180004d64`
- `0x1800053c8`
- `0x180005ea8`
- `0x180006294`
- `0x180006c98`
- `0x180006d7c`
- `0x18000714c`
- `0x18000715c`
- `0x180011b10`
- `0x180012254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800122cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800122cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001256a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001256a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800122ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800122ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012389`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001259d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012389`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001259d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800124b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800124b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800124c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800124c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001228d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001228d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800123a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001249f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800123a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001249f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125ba`

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
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  HANDLE v42; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h]
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
  v42 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)&v42,
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4LL * (_QWORD)v42);
  if ( 4LL * (_QWORD)v42 )
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  v42 = 0;
  hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)&v42,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( v42 && !CloseHandle(v42) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_QWORD *)v24 + 2) = v42;
  *((_QWORD *)v24 + 3) = hObject;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  *a2 = v24;
  v6 = 0;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180012254  mov     [rsp-8+arg_10], rbx
0x180012259  push    rbp
0x18001225a  push    rsi
0x18001225b  push    rdi
0x18001225c  push    r14
0x18001225e  push    r15
0x180012260  lea     rbp, [rsp-160h]
0x180012268  sub     rsp, 260h
0x18001226f  mov     rax, cs:__security_cookie
0x180012276  xor     rax, rsp
0x180012279  mov     [rbp+180h+var_30], rax
0x180012280  mov     r15, rdx
0x180012283  mov     rbx, rcx
0x180012286  mov     qword ptr [rdx], 0
0x18001228d  call    cs:__imp_GetCurrentProcessId
0x180012293  mov     r9d, eax
0x180012296  mov     [rsp+280h+var_258], rbx
0x18001229b  mov     r14d, 130h
0x1800122a1  mov     [rsp+280h+var_260], r14d; int
0x1800122a6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800122ad  lea     edx, [r14-2Ch]; unsigned __int64
0x1800122b1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800122b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800122bb  nop
0x1800122bc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800122c2  xor     r8d, r8d; dwFlags
0x1800122c5  lea     rdx, [rsp+280h+Name]; lpName
0x1800122ca  xor     ecx, ecx; lpMutexAttributes
0x1800122cc  call    cs:__imp_CreateMutexExW
0x1800122d2  mov     rbx, rax
0x1800122d5  test    rax, rax
0x1800122d8  jnz     short loc_1800122E5
0x1800122da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800122df  nop
0x1800122e0  jmp     loc_1800125CD
0x1800122e5  xor     r8d, r8d; bAlertable
0x1800122e8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800122eb  mov     rcx, rbx; hHandle
0x1800122ee  call    cs:__imp_WaitForSingleObjectEx
0x1800122f4  cmp     eax, 102h
0x1800122f9  jz      short loc_18001230B
0x1800122fb  test    eax, 0FFFFFF7Fh
0x180012300  jnz     loc_1800125FE
0x180012306  mov     rdi, rbx
0x180012309  jmp     short loc_18001230D
0x18001230b  xor     edi, edi
0x18001230d  mov     [rsp+280h+var_250], 0
0x180012316  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18001231b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012320  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180012325  mov     esi, eax
0x180012327  test    eax, eax
0x180012329  jns     loc_1800123BD
0x18001232f  mov     rcx, [rbp+188h]; this
0x180012336  mov     r9d, eax; char *
0x180012339  lea     r8, aWil; "wil"
0x180012340  mov     edx, 66h ; 'f'; void *
0x180012345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001234a  mov     rcx, [rbp+188h]; this
0x180012351  mov     r9d, esi; char *
0x180012354  lea     r8, aWil; "wil"
0x18001235b  mov     edx, 6Fh ; 'o'; void *
0x180012360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012365  mov     rcx, [rbp+188h]; this
0x18001236c  mov     r9d, esi; char *
0x18001236f  lea     r8, aWil; "wil"
0x180012376  mov     edx, 12Eh; void *
0x18001237b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012380  nop
0x180012381  test    rdi, rdi
0x180012384  jz      short loc_18001239E
0x180012386  mov     rcx, rdi; hMutex
0x180012389  call    cs:__imp_ReleaseMutex
0x18001238f  mov     rcx, [rbp+188h]; this
0x180012396  test    eax, eax
0x180012398  jz      loc_18001260B
0x18001239e  mov     rcx, rbx; hObject
0x1800123a1  call    cs:__imp_CloseHandle
0x1800123a7  mov     rcx, [rbp+188h]; this
0x1800123ae  test    eax, eax
0x1800123b0  jz      loc_180012616
0x1800123b6  mov     eax, esi
0x1800123b8  jmp     loc_1800125CD
0x1800123bd  mov     rax, [rsp+280h+var_250]
0x1800123c2  lea     rcx, ds:0[rax*4]
0x1800123ca  test    rcx, rcx
0x1800123cd  jz      short loc_1800123DD
0x1800123cf  mov     [r15], rcx
0x1800123d2  mov     eax, [rcx]
0x1800123d4  inc     eax
0x1800123d6  mov     [rcx], eax
0x1800123d8  jmp     loc_180012595
0x1800123dd  mov     qword ptr [r15], 0
0x1800123e4  mov     rdx, r14; dwBytes
0x1800123e7  mov     ecx, 8; dwFlags
0x1800123ec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800123f1  mov     r14, rax
0x1800123f4  test    rax, rax
0x1800123f7  jnz     short loc_18001241E
0x1800123f9  mov     rcx, [rbp+188h]; this
0x180012400  mov     esi, 8007000Eh
0x180012405  mov     r9d, esi; char *
0x180012408  lea     r8, aWil; "wil"
0x18001240f  mov     edx, 14Bh; void *
0x180012414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012419  jmp     loc_1800124C8
0x18001241e  mov     [rsp+280h+var_250], 0
0x180012427  mov     [rsp+280h+hObject], 0
0x180012430  test    r14b, 3
0x180012434  jnz     loc_180012621
0x18001243a  mov     r9, r14
0x18001243d  shr     r9, 2; unsigned __int64
0x180012441  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180012446  lea     rcx, [rsp+280h+var_250]; this
0x18001244b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180012450  mov     esi, eax
0x180012452  test    eax, eax
0x180012454  jns     loc_18001251E
0x18001245a  mov     rcx, [rbp+188h]; this
0x180012461  mov     r9d, eax; char *
0x180012464  lea     r8, aWil; "wil"
0x18001246b  mov     edx, 14Eh; void *
0x180012470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012475  nop
0x180012476  mov     rcx, [rsp+280h+hObject]; hObject
0x18001247b  test    rcx, rcx
0x18001247e  jz      short loc_180012495
0x180012480  call    cs:__imp_CloseHandle
0x180012486  mov     rcx, [rbp+188h]; this
0x18001248d  test    eax, eax
0x18001248f  jz      loc_180012627
0x180012495  mov     rcx, [rsp+280h+var_250]; hObject
0x18001249a  test    rcx, rcx
0x18001249d  jz      short loc_1800124B4
0x18001249f  call    cs:__imp_CloseHandle
0x1800124a5  mov     rcx, [rbp+188h]; this
0x1800124ac  test    eax, eax
0x1800124ae  jz      loc_180012632
0x1800124b4  call    cs:__imp_GetProcessHeap
0x1800124ba  mov     rcx, rax; hHeap
0x1800124bd  mov     r8, r14; lpMem
0x1800124c0  xor     edx, edx; dwFlags
0x1800124c2  call    cs:__imp_HeapFree
0x1800124c8  mov     rcx, [rbp+188h]; this
0x1800124cf  mov     r9d, esi; char *
0x1800124d2  lea     r8, aWil; "wil"
0x1800124d9  mov     edx, 137h; void *
0x1800124de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800124e3  nop
0x1800124e4  test    rdi, rdi
0x1800124e7  jz      short loc_180012501
0x1800124e9  mov     rcx, rdi; hMutex
0x1800124ec  call    cs:__imp_ReleaseMutex
0x1800124f2  mov     rcx, [rbp+188h]; this
0x1800124f9  test    eax, eax
0x1800124fb  jz      loc_18001263D
0x180012501  mov     rcx, rbx; hObject
0x180012504  call    cs:__imp_CloseHandle
0x18001250a  mov     rcx, [rbp+188h]; this
0x180012511  test    eax, eax
0x180012513  jz      loc_180012648
0x180012519  jmp     loc_1800123B6
0x18001251e  mov     dword ptr [r14], 1
0x180012525  mov     [r14+8], rbx
0x180012529  mov     rax, [rsp+280h+var_250]
0x18001252e  mov     [r14+10h], rax
0x180012532  mov     rax, [rsp+280h+hObject]
0x180012537  mov     [r14+18h], rax
0x18001253b  lea     rcx, [r14+28h]; void *
0x18001253f  xor     edx, edx; Val
0x180012541  mov     r8d, 108h; Size
0x180012547  call    memset_0
0x18001254c  xor     eax, eax
0x18001254e  mov     [r14+20h], rax
0x180012552  lea     rcx, [r14+28h]; this
0x180012556  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001255b  lea     rbx, [r14+0E8h]
0x180012562  xor     r8d, r8d; Flags
0x180012565  xor     edx, edx; dwSpinCount
0x180012567  mov     rcx, rbx; lpCriticalSection
0x18001256a  call    cs:__imp_InitializeCriticalSectionEx
0x180012570  mov     qword ptr [rbx+28h], 0
0x180012578  mov     qword ptr [rbx+30h], 0
0x180012580  mov     qword ptr [rbx+38h], 0
0x180012588  mov     qword ptr [rbx+40h], 0
0x180012590  mov     [r15], r14
0x180012593  xor     ebx, ebx
0x180012595  test    rdi, rdi
0x180012598  jz      short loc_1800125B2
0x18001259a  mov     rcx, rdi; hMutex
0x18001259d  call    cs:__imp_ReleaseMutex
0x1800125a3  mov     rcx, [rbp+188h]; this
0x1800125aa  test    eax, eax
0x1800125ac  jz      loc_180012653
0x1800125b2  test    rbx, rbx
0x1800125b5  jz      short loc_1800125CB
0x1800125b7  mov     rcx, rbx; hObject
0x1800125ba  call    cs:__imp_CloseHandle
0x1800125c0  mov     rcx, [rbp+188h]; this
0x1800125c7  test    eax, eax
0x1800125c9  jz      short loc_1800125F3
0x1800125cb  xor     eax, eax
0x1800125cd  mov     rcx, [rbp+180h+var_30]
0x1800125d4  xor     rcx, rsp; StackCookie
0x1800125d7  call    __security_check_cookie
0x1800125dc  mov     rbx, [rsp+280h+arg_10]
0x1800125e4  add     rsp, 260h
0x1800125eb  pop     r15
0x1800125ed  pop     r14
0x1800125ef  pop     rdi
0x1800125f0  pop     rsi
0x1800125f1  pop     rbp
0x1800125f2  retn
0x1800125f3  mov     edx, 0A0Bh; void *
0x1800125f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800125fe  mov     rcx, [rbp+188h]; this
0x180012605  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001260b  mov     edx, 0A15h; void *
0x180012610  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012616  mov     edx, 0A0Bh; void *
0x18001261b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012621  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012627  mov     edx, 0A0Bh; void *
0x18001262c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012632  mov     edx, 0A0Bh; void *
0x180012637  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001263d  mov     edx, 0A15h; void *
0x180012642  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012648  mov     edx, 0A0Bh; void *
0x18001264d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012653  mov     edx, 0A15h; void *
0x180012658  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
