# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007528`
- end: `0x140007928`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140007bdc`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000669c`
- `0x140006d78`
- `0x140007528`
- `0x1400079a4`
- `0x140007e34`
- `0x1400089a8`
- `0x1400097c8`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14000c4bc`
- `0x14000ce7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007817`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007817`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000766c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007789`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000785a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000766c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007789`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000785a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400075cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400075cc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400075a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400075a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007746`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000775a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000775a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007876`

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
0x140007528  mov     [rsp-8+arg_10], rbx
0x14000752d  push    rbp
0x14000752e  push    rsi
0x14000752f  push    rdi
0x140007530  push    r14
0x140007532  push    r15
0x140007534  lea     rbp, [rsp-160h]
0x14000753c  sub     rsp, 260h
0x140007543  mov     rax, cs:__security_cookie
0x14000754a  xor     rax, rsp
0x14000754d  mov     [rbp+180h+var_30], rax
0x140007554  mov     r15, rdx
0x140007557  mov     qword ptr [rdx], 0
0x14000755e  mov     rbx, rcx
0x140007561  call    cs:__imp_GetCurrentProcessId
0x140007568  nop     dword ptr [rax+rax+00h]
0x14000756d  mov     r14d, 130h
0x140007573  mov     [rsp+280h+var_258], rbx
0x140007578  mov     r9d, eax
0x14000757b  mov     [rsp+280h+var_260], r14d; int
0x140007580  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007587  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000758c  lea     edx, [r14-2Ch]; unsigned __int64
0x140007590  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007595  mov     r9d, 1F0001h; dwDesiredAccess
0x14000759b  lea     rdx, [rsp+280h+Name]; lpName
0x1400075a0  xor     r8d, r8d; dwFlags
0x1400075a3  xor     ecx, ecx; lpMutexAttributes
0x1400075a5  call    cs:__imp_CreateMutexExW
0x1400075ac  nop     dword ptr [rax+rax+00h]
0x1400075b1  mov     rbx, rax
0x1400075b4  test    rax, rax
0x1400075b7  jnz     short loc_1400075C3
0x1400075b9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400075be  jmp     loc_140007888
0x1400075c3  xor     r8d, r8d; bAlertable
0x1400075c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400075c9  mov     rcx, rbx; hHandle
0x1400075cc  call    cs:__imp_WaitForSingleObjectEx
0x1400075d3  nop     dword ptr [rax+rax+00h]
0x1400075d8  cmp     eax, 102h
0x1400075dd  jz      short loc_1400075EF
0x1400075df  test    eax, 0FFFFFF7Fh
0x1400075e4  jnz     loc_1400078D3
0x1400075ea  mov     rdi, rbx
0x1400075ed  jmp     short loc_1400075F1
0x1400075ef  xor     edi, edi
0x1400075f1  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1400075f6  mov     [rsp+280h+var_250], 0
0x1400075ff  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007604  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140007609  mov     esi, eax
0x14000760b  test    eax, eax
0x14000760d  jns     loc_14000769E
0x140007613  mov     rcx, [rbp+188h]; this
0x14000761a  lea     r8, aWil; "wil"
0x140007621  mov     r9d, eax; char *
0x140007624  mov     edx, 66h ; 'f'; void *
0x140007629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000762e  mov     rcx, [rbp+188h]; this
0x140007635  lea     r8, aWil; "wil"
0x14000763c  mov     r9d, esi; char *
0x14000763f  mov     edx, 6Fh ; 'o'; void *
0x140007644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007649  mov     rcx, [rbp+188h]; this
0x140007650  lea     r8, aWil; "wil"
0x140007657  mov     r9d, esi; char *
0x14000765a  mov     edx, 12Eh; void *
0x14000765f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007664  test    rdi, rdi
0x140007667  jz      short loc_140007680
0x140007669  mov     rcx, rdi; hMutex
0x14000766c  call    cs:__imp_ReleaseMutex
0x140007673  nop     dword ptr [rax+rax+00h]
0x140007678  test    eax, eax
0x14000767a  jz      loc_1400078E0
0x140007680  mov     rcx, rbx; hObject
0x140007683  call    cs:__imp_CloseHandle
0x14000768a  nop     dword ptr [rax+rax+00h]
0x14000768f  test    eax, eax
0x140007691  jz      loc_1400078F2
0x140007697  mov     eax, esi
0x140007699  jmp     loc_140007888
0x14000769e  mov     rax, [rsp+280h+var_250]
0x1400076a3  lea     rcx, ds:0[rax*4]
0x1400076ab  test    rcx, rcx
0x1400076ae  jz      short loc_1400076BE
0x1400076b0  mov     [r15], rcx
0x1400076b3  mov     eax, [rcx]
0x1400076b5  inc     eax
0x1400076b7  mov     [rcx], eax
0x1400076b9  jmp     loc_140007852
0x1400076be  mov     rdx, r14; dwBytes
0x1400076c1  mov     qword ptr [r15], 0
0x1400076c8  mov     ecx, 8; dwFlags
0x1400076cd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400076d2  mov     r14, rax
0x1400076d5  test    rax, rax
0x1400076d8  jnz     short loc_1400076FC
0x1400076da  mov     rcx, [rbp+188h]; this
0x1400076e1  lea     r8, aWil; "wil"
0x1400076e8  mov     esi, 8007000Eh
0x1400076ed  mov     edx, 14Bh; void *
0x1400076f2  mov     r9d, esi; char *
0x1400076f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400076fa  jmp     short loc_140007766
0x1400076fc  xorps   xmm0, xmm0
0x1400076ff  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140007704  mov     r8, r14; void *
0x140007707  lea     rcx, [rsp+280h+var_250]; this
0x14000770c  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140007712  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140007717  mov     esi, eax
0x140007719  test    eax, eax
0x14000771b  jns     loc_1400077B9
0x140007721  mov     rcx, [rbp+188h]; this
0x140007728  lea     r8, aWil; "wil"
0x14000772f  mov     r9d, eax; char *
0x140007732  mov     edx, 14Eh; void *
0x140007737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000773c  lea     rcx, [rsp+280h+var_250]; this
0x140007741  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140007746  call    cs:__imp_GetProcessHeap
0x14000774d  nop     dword ptr [rax+rax+00h]
0x140007752  mov     r8, r14; lpMem
0x140007755  xor     edx, edx; dwFlags
0x140007757  mov     rcx, rax; hHeap
0x14000775a  call    cs:__imp_HeapFree
0x140007761  nop     dword ptr [rax+rax+00h]
0x140007766  mov     rcx, [rbp+188h]; this
0x14000776d  lea     r8, aWil; "wil"
0x140007774  mov     r9d, esi; char *
0x140007777  mov     edx, 137h; void *
0x14000777c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007781  test    rdi, rdi
0x140007784  jz      short loc_14000779D
0x140007786  mov     rcx, rdi; hMutex
0x140007789  call    cs:__imp_ReleaseMutex
0x140007790  nop     dword ptr [rax+rax+00h]
0x140007795  test    eax, eax
0x140007797  jz      loc_140007904
0x14000779d  mov     rcx, rbx; hObject
0x1400077a0  call    cs:__imp_CloseHandle
0x1400077a7  nop     dword ptr [rax+rax+00h]
0x1400077ac  test    eax, eax
0x1400077ae  jz      loc_1400078C1
0x1400077b4  jmp     loc_140007697
0x1400077b9  mov     rax, [rsp+280h+var_250]
0x1400077be  lea     rcx, [r14+28h]; void *
0x1400077c2  mov     [r14+10h], rax
0x1400077c6  xor     edx, edx; Val
0x1400077c8  mov     rax, [rsp+280h+var_250+8]
0x1400077cd  mov     r8d, 108h; Size
0x1400077d3  mov     [r14+18h], rax
0x1400077d7  mov     dword ptr [r14], 1
0x1400077de  mov     [r14+8], rbx
0x1400077e2  mov     [rsp+280h+var_250], 0
0x1400077eb  mov     [rsp+280h+var_250+8], 0
0x1400077f4  call    memset_0
0x1400077f9  xor     eax, eax
0x1400077fb  lea     rcx, [r14+28h]; this
0x1400077ff  mov     [r14+20h], rax
0x140007803  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140007808  lea     rbx, [r14+0E8h]
0x14000780f  xor     r8d, r8d; Flags
0x140007812  mov     rcx, rbx; lpCriticalSection
0x140007815  xor     edx, edx; dwSpinCount
0x140007817  call    cs:__imp_InitializeCriticalSectionEx
0x14000781e  nop     dword ptr [rax+rax+00h]
0x140007823  mov     qword ptr [rbx+28h], 0
0x14000782b  lea     rcx, [rsp+280h+var_250]; this
0x140007830  mov     qword ptr [rbx+30h], 0
0x140007838  mov     qword ptr [rbx+38h], 0
0x140007840  mov     qword ptr [rbx+40h], 0
0x140007848  mov     [r15], r14
0x14000784b  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140007850  xor     ebx, ebx
0x140007852  test    rdi, rdi
0x140007855  jz      short loc_14000786E
0x140007857  mov     rcx, rdi; hMutex
0x14000785a  call    cs:__imp_ReleaseMutex
0x140007861  nop     dword ptr [rax+rax+00h]
0x140007866  test    eax, eax
0x140007868  jz      loc_140007916
0x14000786e  test    rbx, rbx
0x140007871  jz      short loc_140007886
0x140007873  mov     rcx, rbx; hObject
0x140007876  call    cs:__imp_CloseHandle
0x14000787d  nop     dword ptr [rax+rax+00h]
0x140007882  test    eax, eax
0x140007884  jz      short loc_1400078AF
0x140007886  xor     eax, eax
0x140007888  mov     rcx, [rbp+180h+var_30]
0x14000788f  xor     rcx, rsp; StackCookie
0x140007892  call    __security_check_cookie
0x140007897  mov     rbx, [rsp+280h+arg_10]
0x14000789f  add     rsp, 260h
0x1400078a6  pop     r15
0x1400078a8  pop     r14
0x1400078aa  pop     rdi
0x1400078ab  pop     rsi
0x1400078ac  pop     rbp
0x1400078ad  retn
0x1400078af  mov     rcx, [rbp+188h]; this
0x1400078b6  mov     edx, 0A0Bh; void *
0x1400078bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400078c1  mov     rcx, [rbp+188h]; this
0x1400078c8  mov     edx, 0A0Bh; void *
0x1400078cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400078d3  mov     rcx, [rbp+188h]; this
0x1400078da  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400078e0  mov     rcx, [rbp+188h]; this
0x1400078e7  mov     edx, 0A15h; void *
0x1400078ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400078f2  mov     rcx, [rbp+188h]; this
0x1400078f9  mov     edx, 0A0Bh; void *
0x1400078fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007904  mov     rcx, [rbp+188h]; this
0x14000790b  mov     edx, 0A15h; void *
0x140007910  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007916  mov     rcx, [rbp+188h]; this
0x14000791d  mov     edx, 0A15h; void *
0x140007922  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
