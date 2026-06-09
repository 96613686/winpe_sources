# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180021604`
- end: `0x1800219f5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180021cd0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x18000e30c`
- `0x18000e5f8`
- `0x180020a80`
- `0x180021604`
- `0x1800219fc`
- `0x180021e60`
- `0x1800223d8`
- `0x180022850`
- `0x1800240b8`
- `0x180024774`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021845`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002163d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002163d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002167b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002167b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800218d7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800218d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002169c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002169c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021732`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002186e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002190a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021732`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002186e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002190a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002187f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002187f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021920`

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
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
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
0x180021604  mov     [rsp-8+arg_10], rbx
0x180021609  push    rbp
0x18002160a  push    rsi
0x18002160b  push    rdi
0x18002160c  push    r14
0x18002160e  push    r15
0x180021610  lea     rbp, [rsp-160h]
0x180021618  sub     rsp, 260h
0x18002161f  mov     rax, cs:__security_cookie
0x180021626  xor     rax, rsp
0x180021629  mov     [rbp+180h+var_30], rax
0x180021630  mov     r15, rdx
0x180021633  mov     qword ptr [rdx], 0
0x18002163a  mov     rbx, rcx
0x18002163d  call    cs:__imp_GetCurrentProcessId
0x180021643  mov     r14d, 130h
0x180021649  mov     [rsp+280h+var_258], rbx
0x18002164e  mov     r9d, eax
0x180021651  mov     [rsp+280h+var_260], r14d; int
0x180021656  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002165d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180021662  lea     edx, [r14-2Ch]; unsigned __int64
0x180021666  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002166b  mov     r9d, 1F0001h; dwDesiredAccess
0x180021671  lea     rdx, [rsp+280h+Name]; lpName
0x180021676  xor     r8d, r8d; dwFlags
0x180021679  xor     ecx, ecx; lpMutexAttributes
0x18002167b  call    cs:__imp_CreateMutexExW
0x180021681  mov     rbx, rax
0x180021684  test    rax, rax
0x180021687  jnz     short loc_180021693
0x180021689  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002168e  jmp     loc_18002192C
0x180021693  xor     r8d, r8d; bAlertable
0x180021696  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021699  mov     rcx, rbx; hHandle
0x18002169c  call    cs:__imp_WaitForSingleObjectEx
0x1800216a2  cmp     eax, 102h
0x1800216a7  jz      short loc_1800216B9
0x1800216a9  test    eax, 0FFFFFF7Fh
0x1800216ae  jnz     loc_180021976
0x1800216b4  mov     rdi, rbx
0x1800216b7  jmp     short loc_1800216BB
0x1800216b9  xor     edi, edi
0x1800216bb  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800216c0  mov     [rsp+280h+hObject], 0
0x1800216c9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800216ce  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800216d3  mov     esi, eax
0x1800216d5  test    eax, eax
0x1800216d7  jns     short loc_180021758
0x1800216d9  mov     rcx, [rbp+188h]; this
0x1800216e0  lea     r8, aWil; "wil"
0x1800216e7  mov     r9d, eax; char *
0x1800216ea  mov     edx, 66h ; 'f'; void *
0x1800216ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216f4  mov     rcx, [rbp+188h]; this
0x1800216fb  lea     r8, aWil; "wil"
0x180021702  mov     r9d, esi; char *
0x180021705  mov     edx, 6Fh ; 'o'; void *
0x18002170a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002170f  mov     rcx, [rbp+188h]; this
0x180021716  lea     r8, aWil; "wil"
0x18002171d  mov     r9d, esi; char *
0x180021720  mov     edx, 12Eh; void *
0x180021725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002172a  test    rdi, rdi
0x18002172d  jz      short loc_180021740
0x18002172f  mov     rcx, rdi; hMutex
0x180021732  call    cs:__imp_ReleaseMutex
0x180021738  test    eax, eax
0x18002173a  jz      loc_180021983
0x180021740  mov     rcx, rbx; hObject
0x180021743  call    cs:__imp_CloseHandle
0x180021749  test    eax, eax
0x18002174b  jz      loc_180021995
0x180021751  mov     eax, esi
0x180021753  jmp     loc_18002192C
0x180021758  mov     rax, [rsp+280h+hObject]
0x18002175d  lea     rcx, ds:0[rax*4]
0x180021765  test    rcx, rcx
0x180021768  jz      short loc_180021778
0x18002176a  mov     [r15], rcx
0x18002176d  mov     eax, [rcx]
0x18002176f  inc     eax
0x180021771  mov     [rcx], eax
0x180021773  jmp     loc_180021902
0x180021778  mov     rdx, r14; dwBytes
0x18002177b  mov     qword ptr [r15], 0
0x180021782  mov     ecx, 8; dwFlags
0x180021787  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002178c  mov     r14, rax
0x18002178f  test    rax, rax
0x180021792  jnz     short loc_1800217B9
0x180021794  mov     rcx, [rbp+188h]; this
0x18002179b  lea     r8, aWil; "wil"
0x1800217a2  mov     esi, 8007000Eh
0x1800217a7  mov     edx, 14Bh; void *
0x1800217ac  mov     r9d, esi; char *
0x1800217af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800217b4  jmp     loc_18002184B
0x1800217b9  xorps   xmm0, xmm0
0x1800217bc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800217c2  test    r14b, 3
0x1800217c6  jnz     loc_1800219A7
0x1800217cc  mov     r9, r14
0x1800217cf  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800217d4  shr     r9, 2; unsigned __int64
0x1800217d8  lea     rcx, [rsp+280h+hObject]; this
0x1800217dd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800217e2  mov     esi, eax
0x1800217e4  test    eax, eax
0x1800217e6  jns     loc_180021892
0x1800217ec  mov     rcx, [rbp+188h]; this
0x1800217f3  lea     r8, aWil; "wil"
0x1800217fa  mov     r9d, eax; char *
0x1800217fd  mov     edx, 14Eh; void *
0x180021802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021807  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18002180c  test    rcx, rcx
0x18002180f  jz      short loc_18002181F
0x180021811  call    cs:__imp_CloseHandle
0x180021817  test    eax, eax
0x180021819  jz      loc_1800219AD
0x18002181f  mov     rcx, [rsp+280h+hObject]; hObject
0x180021824  test    rcx, rcx
0x180021827  jz      short loc_180021837
0x180021829  call    cs:__imp_CloseHandle
0x18002182f  test    eax, eax
0x180021831  jz      loc_1800219BF
0x180021837  call    cs:__imp_GetProcessHeap
0x18002183d  mov     r8, r14; lpMem
0x180021840  xor     edx, edx; dwFlags
0x180021842  mov     rcx, rax; hHeap
0x180021845  call    cs:__imp_HeapFree
0x18002184b  mov     rcx, [rbp+188h]; this
0x180021852  lea     r8, aWil; "wil"
0x180021859  mov     r9d, esi; char *
0x18002185c  mov     edx, 137h; void *
0x180021861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021866  test    rdi, rdi
0x180021869  jz      short loc_18002187C
0x18002186b  mov     rcx, rdi; hMutex
0x18002186e  call    cs:__imp_ReleaseMutex
0x180021874  test    eax, eax
0x180021876  jz      loc_1800219D1
0x18002187c  mov     rcx, rbx; hObject
0x18002187f  call    cs:__imp_CloseHandle
0x180021885  test    eax, eax
0x180021887  jz      loc_180021964
0x18002188d  jmp     loc_180021751
0x180021892  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180021897  lea     rcx, [r14+28h]; void *
0x18002189b  mov     dword ptr [r14], 1
0x1800218a2  xor     edx, edx; Val
0x1800218a4  mov     [r14+8], rbx
0x1800218a8  mov     r8d, 108h; Size
0x1800218ae  movdqu  xmmword ptr [r14+10h], xmm0
0x1800218b4  call    memset_0
0x1800218b9  xor     eax, eax
0x1800218bb  lea     rcx, [r14+28h]; this
0x1800218bf  mov     [r14+20h], rax
0x1800218c3  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800218c8  lea     rbx, [r14+0E8h]
0x1800218cf  xor     r8d, r8d; Flags
0x1800218d2  mov     rcx, rbx; lpCriticalSection
0x1800218d5  xor     edx, edx; dwSpinCount
0x1800218d7  call    cs:__imp_InitializeCriticalSectionEx
0x1800218dd  mov     qword ptr [rbx+28h], 0
0x1800218e5  mov     qword ptr [rbx+30h], 0
0x1800218ed  mov     qword ptr [rbx+38h], 0
0x1800218f5  mov     qword ptr [rbx+40h], 0
0x1800218fd  xor     ebx, ebx
0x1800218ff  mov     [r15], r14
0x180021902  test    rdi, rdi
0x180021905  jz      short loc_180021918
0x180021907  mov     rcx, rdi; hMutex
0x18002190a  call    cs:__imp_ReleaseMutex
0x180021910  test    eax, eax
0x180021912  jz      loc_1800219E3
0x180021918  test    rbx, rbx
0x18002191b  jz      short loc_18002192A
0x18002191d  mov     rcx, rbx; hObject
0x180021920  call    cs:__imp_CloseHandle
0x180021926  test    eax, eax
0x180021928  jz      short loc_180021952
0x18002192a  xor     eax, eax
0x18002192c  mov     rcx, [rbp+180h+var_30]
0x180021933  xor     rcx, rsp; StackCookie
0x180021936  call    __security_check_cookie
0x18002193b  mov     rbx, [rsp+280h+arg_10]
0x180021943  add     rsp, 260h
0x18002194a  pop     r15
0x18002194c  pop     r14
0x18002194e  pop     rdi
0x18002194f  pop     rsi
0x180021950  pop     rbp
0x180021951  retn
0x180021952  mov     rcx, [rbp+188h]; this
0x180021959  mov     edx, 0A0Bh; void *
0x18002195e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021964  mov     rcx, [rbp+188h]; this
0x18002196b  mov     edx, 0A0Bh; void *
0x180021970  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021976  mov     rcx, [rbp+188h]; this
0x18002197d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180021983  mov     rcx, [rbp+188h]; this
0x18002198a  mov     edx, 0A15h; void *
0x18002198f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021995  mov     rcx, [rbp+188h]; this
0x18002199c  mov     edx, 0A0Bh; void *
0x1800219a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800219a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800219ad  mov     rcx, [rbp+188h]; this
0x1800219b4  mov     edx, 0A0Bh; void *
0x1800219b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800219bf  mov     rcx, [rbp+188h]; this
0x1800219c6  mov     edx, 0A0Bh; void *
0x1800219cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800219d1  mov     rcx, [rbp+188h]; this
0x1800219d8  mov     edx, 0A15h; void *
0x1800219dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800219e3  mov     rcx, [rbp+188h]; this
0x1800219ea  mov     edx, 0A15h; void *
0x1800219ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
