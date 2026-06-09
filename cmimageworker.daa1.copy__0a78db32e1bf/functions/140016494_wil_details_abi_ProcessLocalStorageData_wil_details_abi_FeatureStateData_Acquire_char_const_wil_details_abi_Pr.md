# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140016494`
- end: `0x140016894`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400194d0`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x140003e1c`
- `0x140004568`
- `0x1400048b8`
- `0x140004e70`
- `0x1400067d4`
- `0x140006fe4`
- `0x14000898c`
- `0x140008a6c`
- `0x140008f74`
- `0x140015500`
- `0x140016494`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140016783`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140016783`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400165d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400166f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400167c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400165d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400166f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400167c6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140016511`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140016511`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140016538`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140016538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400166b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400166b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400166c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400166c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400164cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400164cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400165ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001670c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400167e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400165ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001670c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400167e2`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x140016494  mov     [rsp-8+arg_10], rbx
0x140016499  push    rbp
0x14001649a  push    rsi
0x14001649b  push    rdi
0x14001649c  push    r14
0x14001649e  push    r15
0x1400164a0  lea     rbp, [rsp-160h]
0x1400164a8  sub     rsp, 260h
0x1400164af  mov     rax, cs:__security_cookie
0x1400164b6  xor     rax, rsp
0x1400164b9  mov     [rbp+180h+var_30], rax
0x1400164c0  mov     r15, rdx
0x1400164c3  mov     qword ptr [rdx], 0
0x1400164ca  mov     rbx, rcx
0x1400164cd  call    cs:__imp_GetCurrentProcessId
0x1400164d4  nop     dword ptr [rax+rax+00h]
0x1400164d9  mov     r14d, 130h
0x1400164df  mov     [rsp+280h+var_258], rbx
0x1400164e4  mov     r9d, eax
0x1400164e7  mov     [rsp+280h+var_260], r14d; int
0x1400164ec  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400164f3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400164f8  lea     edx, [r14-2Ch]; unsigned __int64
0x1400164fc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140016501  mov     r9d, 1F0001h; dwDesiredAccess
0x140016507  lea     rdx, [rsp+280h+Name]; lpName
0x14001650c  xor     r8d, r8d; dwFlags
0x14001650f  xor     ecx, ecx; lpMutexAttributes
0x140016511  call    cs:__imp_CreateMutexExW
0x140016518  nop     dword ptr [rax+rax+00h]
0x14001651d  mov     rbx, rax
0x140016520  test    rax, rax
0x140016523  jnz     short loc_14001652F
0x140016525  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001652a  jmp     loc_1400167F4
0x14001652f  xor     r8d, r8d; bAlertable
0x140016532  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140016535  mov     rcx, rbx; hHandle
0x140016538  call    cs:__imp_WaitForSingleObjectEx
0x14001653f  nop     dword ptr [rax+rax+00h]
0x140016544  cmp     eax, 102h
0x140016549  jz      short loc_14001655B
0x14001654b  test    eax, 0FFFFFF7Fh
0x140016550  jnz     loc_14001683F
0x140016556  mov     rdi, rbx
0x140016559  jmp     short loc_14001655D
0x14001655b  xor     edi, edi
0x14001655d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140016562  mov     [rsp+280h+var_250], 0
0x14001656b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140016570  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140016575  mov     esi, eax
0x140016577  test    eax, eax
0x140016579  jns     loc_14001660A
0x14001657f  mov     rcx, [rbp+188h]; this
0x140016586  lea     r8, aWil; "wil"
0x14001658d  mov     r9d, eax; char *
0x140016590  mov     edx, 66h ; 'f'; void *
0x140016595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001659a  mov     rcx, [rbp+188h]; this
0x1400165a1  lea     r8, aWil; "wil"
0x1400165a8  mov     r9d, esi; char *
0x1400165ab  mov     edx, 6Fh ; 'o'; void *
0x1400165b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400165b5  mov     rcx, [rbp+188h]; this
0x1400165bc  lea     r8, aWil; "wil"
0x1400165c3  mov     r9d, esi; char *
0x1400165c6  mov     edx, 12Eh; void *
0x1400165cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400165d0  test    rdi, rdi
0x1400165d3  jz      short loc_1400165EC
0x1400165d5  mov     rcx, rdi; hMutex
0x1400165d8  call    cs:__imp_ReleaseMutex
0x1400165df  nop     dword ptr [rax+rax+00h]
0x1400165e4  test    eax, eax
0x1400165e6  jz      loc_14001684C
0x1400165ec  mov     rcx, rbx; hObject
0x1400165ef  call    cs:__imp_CloseHandle
0x1400165f6  nop     dword ptr [rax+rax+00h]
0x1400165fb  test    eax, eax
0x1400165fd  jz      loc_14001685E
0x140016603  mov     eax, esi
0x140016605  jmp     loc_1400167F4
0x14001660a  mov     rax, [rsp+280h+var_250]
0x14001660f  lea     rcx, ds:0[rax*4]
0x140016617  test    rcx, rcx
0x14001661a  jz      short loc_14001662A
0x14001661c  mov     [r15], rcx
0x14001661f  mov     eax, [rcx]
0x140016621  inc     eax
0x140016623  mov     [rcx], eax
0x140016625  jmp     loc_1400167BE
0x14001662a  mov     rdx, r14; dwBytes
0x14001662d  mov     qword ptr [r15], 0
0x140016634  mov     ecx, 8; dwFlags
0x140016639  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001663e  mov     r14, rax
0x140016641  test    rax, rax
0x140016644  jnz     short loc_140016668
0x140016646  mov     rcx, [rbp+188h]; this
0x14001664d  lea     r8, aWil; "wil"
0x140016654  mov     esi, 8007000Eh
0x140016659  mov     edx, 14Bh; void *
0x14001665e  mov     r9d, esi; char *
0x140016661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016666  jmp     short loc_1400166D2
0x140016668  xorps   xmm0, xmm0
0x14001666b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140016670  mov     r8, r14; void *
0x140016673  lea     rcx, [rsp+280h+var_250]; this
0x140016678  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14001667e  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140016683  mov     esi, eax
0x140016685  test    eax, eax
0x140016687  jns     loc_140016725
0x14001668d  mov     rcx, [rbp+188h]; this
0x140016694  lea     r8, aWil; "wil"
0x14001669b  mov     r9d, eax; char *
0x14001669e  mov     edx, 14Eh; void *
0x1400166a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400166a8  lea     rcx, [rsp+280h+var_250]; this
0x1400166ad  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400166b2  call    cs:__imp_GetProcessHeap
0x1400166b9  nop     dword ptr [rax+rax+00h]
0x1400166be  mov     r8, r14; lpMem
0x1400166c1  xor     edx, edx; dwFlags
0x1400166c3  mov     rcx, rax; hHeap
0x1400166c6  call    cs:__imp_HeapFree
0x1400166cd  nop     dword ptr [rax+rax+00h]
0x1400166d2  mov     rcx, [rbp+188h]; this
0x1400166d9  lea     r8, aWil; "wil"
0x1400166e0  mov     r9d, esi; char *
0x1400166e3  mov     edx, 137h; void *
0x1400166e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400166ed  test    rdi, rdi
0x1400166f0  jz      short loc_140016709
0x1400166f2  mov     rcx, rdi; hMutex
0x1400166f5  call    cs:__imp_ReleaseMutex
0x1400166fc  nop     dword ptr [rax+rax+00h]
0x140016701  test    eax, eax
0x140016703  jz      loc_140016870
0x140016709  mov     rcx, rbx; hObject
0x14001670c  call    cs:__imp_CloseHandle
0x140016713  nop     dword ptr [rax+rax+00h]
0x140016718  test    eax, eax
0x14001671a  jz      loc_14001682D
0x140016720  jmp     loc_140016603
0x140016725  mov     rax, [rsp+280h+var_250]
0x14001672a  lea     rcx, [r14+28h]; void *
0x14001672e  mov     [r14+10h], rax
0x140016732  xor     edx, edx; Val
0x140016734  mov     rax, [rsp+280h+var_250+8]
0x140016739  mov     r8d, 108h; Size
0x14001673f  mov     [r14+18h], rax
0x140016743  mov     dword ptr [r14], 1
0x14001674a  mov     [r14+8], rbx
0x14001674e  mov     [rsp+280h+var_250], 0
0x140016757  mov     [rsp+280h+var_250+8], 0
0x140016760  call    memset_0
0x140016765  xor     eax, eax
0x140016767  lea     rcx, [r14+28h]; this
0x14001676b  mov     [r14+20h], rax
0x14001676f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140016774  lea     rbx, [r14+0E8h]
0x14001677b  xor     r8d, r8d; Flags
0x14001677e  mov     rcx, rbx; lpCriticalSection
0x140016781  xor     edx, edx; dwSpinCount
0x140016783  call    cs:__imp_InitializeCriticalSectionEx
0x14001678a  nop     dword ptr [rax+rax+00h]
0x14001678f  mov     qword ptr [rbx+28h], 0
0x140016797  lea     rcx, [rsp+280h+var_250]; this
0x14001679c  mov     qword ptr [rbx+30h], 0
0x1400167a4  mov     qword ptr [rbx+38h], 0
0x1400167ac  mov     qword ptr [rbx+40h], 0
0x1400167b4  mov     [r15], r14
0x1400167b7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400167bc  xor     ebx, ebx
0x1400167be  test    rdi, rdi
0x1400167c1  jz      short loc_1400167DA
0x1400167c3  mov     rcx, rdi; hMutex
0x1400167c6  call    cs:__imp_ReleaseMutex
0x1400167cd  nop     dword ptr [rax+rax+00h]
0x1400167d2  test    eax, eax
0x1400167d4  jz      loc_140016882
0x1400167da  test    rbx, rbx
0x1400167dd  jz      short loc_1400167F2
0x1400167df  mov     rcx, rbx; hObject
0x1400167e2  call    cs:__imp_CloseHandle
0x1400167e9  nop     dword ptr [rax+rax+00h]
0x1400167ee  test    eax, eax
0x1400167f0  jz      short loc_14001681B
0x1400167f2  xor     eax, eax
0x1400167f4  mov     rcx, [rbp+180h+var_30]
0x1400167fb  xor     rcx, rsp; StackCookie
0x1400167fe  call    __security_check_cookie
0x140016803  mov     rbx, [rsp+280h+arg_10]
0x14001680b  add     rsp, 260h
0x140016812  pop     r15
0x140016814  pop     r14
0x140016816  pop     rdi
0x140016817  pop     rsi
0x140016818  pop     rbp
0x140016819  retn
0x14001681b  mov     rcx, [rbp+188h]; this
0x140016822  mov     edx, 0A0Bh; void *
0x140016827  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001682d  mov     rcx, [rbp+188h]; this
0x140016834  mov     edx, 0A0Bh; void *
0x140016839  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001683f  mov     rcx, [rbp+188h]; this
0x140016846  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14001684c  mov     rcx, [rbp+188h]; this
0x140016853  mov     edx, 0A15h; void *
0x140016858  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001685e  mov     rcx, [rbp+188h]; this
0x140016865  mov     edx, 0A0Bh; void *
0x14001686a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140016870  mov     rcx, [rbp+188h]; this
0x140016877  mov     edx, 0A15h; void *
0x14001687c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140016882  mov     rcx, [rbp+188h]; this
0x140016889  mov     edx, 0A15h; void *
0x14001688e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
