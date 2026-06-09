# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000f4c8`
- end: `0x18000f8c5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1800123f8`

## callees

- `0x1800051f0`
- `0x180005860`
- `0x180005bb8`
- `0x1800062e8`
- `0x180006eac`
- `0x180007674`
- `0x180007ea4`
- `0x18000809c`
- `0x18000863c`
- `0x18000864c`
- `0x18000d034`
- `0x18000f4c8`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f5f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f709`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f7c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f5f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f709`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f7c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000f78b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000f78b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f53f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000f53f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f560`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f560`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f71a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f71a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7de`

## string_xrefs

- `0x18000f817`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f830`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f849`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f862`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f87b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f89a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f8b3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x18000f4c8  mov     [rsp-8+arg_10], rbx
0x18000f4cd  push    rbp
0x18000f4ce  push    rsi
0x18000f4cf  push    rdi
0x18000f4d0  push    r14
0x18000f4d2  push    r15
0x18000f4d4  lea     rbp, [rsp-160h]
0x18000f4dc  sub     rsp, 260h
0x18000f4e3  mov     rax, cs:__security_cookie
0x18000f4ea  xor     rax, rsp
0x18000f4ed  mov     [rbp+180h+var_30], rax
0x18000f4f4  mov     r15, rdx
0x18000f4f7  mov     qword ptr [rdx], 0
0x18000f4fe  mov     rbx, rcx
0x18000f501  call    cs:__imp_GetCurrentProcessId
0x18000f507  mov     r14d, 130h
0x18000f50d  mov     [rsp+280h+var_258], rbx
0x18000f512  mov     r9d, eax
0x18000f515  mov     [rsp+280h+var_260], r14d; int
0x18000f51a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000f521  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f526  lea     edx, [r14-2Ch]; unsigned __int64
0x18000f52a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f52f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000f535  lea     rdx, [rsp+280h+Name]; lpName
0x18000f53a  xor     r8d, r8d; dwFlags
0x18000f53d  xor     ecx, ecx; lpMutexAttributes
0x18000f53f  call    cs:__imp_CreateMutexExW
0x18000f545  mov     rbx, rax
0x18000f548  test    rax, rax
0x18000f54b  jnz     short loc_18000F557
0x18000f54d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f552  jmp     loc_18000F7EA
0x18000f557  xor     r8d, r8d; bAlertable
0x18000f55a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f55d  mov     rcx, rbx; hHandle
0x18000f560  call    cs:__imp_WaitForSingleObjectEx
0x18000f566  cmp     eax, 102h
0x18000f56b  jz      short loc_18000F57D
0x18000f56d  test    eax, 0FFFFFF7Fh
0x18000f572  jnz     loc_18000F842
0x18000f578  mov     rdi, rbx
0x18000f57b  jmp     short loc_18000F57F
0x18000f57d  xor     edi, edi
0x18000f57f  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000f584  mov     [rsp+280h+var_250], 0
0x18000f58d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f592  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000f597  mov     esi, eax
0x18000f599  test    eax, eax
0x18000f59b  jns     short loc_18000F61C
0x18000f59d  mov     rcx, [rbp+188h]; this
0x18000f5a4  lea     r8, aWil; "wil"
0x18000f5ab  mov     r9d, eax; char *
0x18000f5ae  mov     edx, 66h ; 'f'; void *
0x18000f5b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5b8  mov     rcx, [rbp+188h]; this
0x18000f5bf  lea     r8, aWil; "wil"
0x18000f5c6  mov     r9d, esi; char *
0x18000f5c9  mov     edx, 6Fh ; 'o'; void *
0x18000f5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5d3  mov     rcx, [rbp+188h]; this
0x18000f5da  lea     r8, aWil; "wil"
0x18000f5e1  mov     r9d, esi; char *
0x18000f5e4  mov     edx, 12Eh; void *
0x18000f5e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5ee  test    rdi, rdi
0x18000f5f1  jz      short loc_18000F604
0x18000f5f3  mov     rcx, rdi; hMutex
0x18000f5f6  call    cs:__imp_ReleaseMutex
0x18000f5fc  test    eax, eax
0x18000f5fe  jz      loc_18000F85B
0x18000f604  mov     rcx, rbx; hObject
0x18000f607  call    cs:__imp_CloseHandle
0x18000f60d  test    eax, eax
0x18000f60f  jz      loc_18000F874
0x18000f615  mov     eax, esi
0x18000f617  jmp     loc_18000F7EA
0x18000f61c  mov     rax, [rsp+280h+var_250]
0x18000f621  lea     rcx, ds:0[rax*4]
0x18000f629  test    rcx, rcx
0x18000f62c  jz      short loc_18000F63C
0x18000f62e  mov     [r15], rcx
0x18000f631  mov     eax, [rcx]
0x18000f633  inc     eax
0x18000f635  mov     [rcx], eax
0x18000f637  jmp     loc_18000F7C0
0x18000f63c  mov     rdx, r14; dwBytes
0x18000f63f  mov     qword ptr [r15], 0
0x18000f646  mov     ecx, 8; dwFlags
0x18000f64b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f650  mov     r14, rax
0x18000f653  test    rax, rax
0x18000f656  jnz     short loc_18000F67A
0x18000f658  mov     rcx, [rbp+188h]; this
0x18000f65f  lea     r8, aWil; "wil"
0x18000f666  mov     esi, 8007000Eh
0x18000f66b  mov     edx, 14Bh; void *
0x18000f670  mov     r9d, esi; char *
0x18000f673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f678  jmp     short loc_18000F6E6
0x18000f67a  xorps   xmm0, xmm0
0x18000f67d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000f683  test    r14b, 3
0x18000f687  jnz     loc_18000F88D
0x18000f68d  mov     r9, r14
0x18000f690  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000f695  shr     r9, 2; unsigned __int64
0x18000f699  lea     rcx, [rsp+280h+var_250]; this
0x18000f69e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000f6a3  mov     esi, eax
0x18000f6a5  test    eax, eax
0x18000f6a7  jns     loc_18000F72D
0x18000f6ad  mov     rcx, [rbp+188h]; this
0x18000f6b4  lea     r8, aWil; "wil"
0x18000f6bb  mov     r9d, eax; char *
0x18000f6be  mov     edx, 14Eh; void *
0x18000f6c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6c8  lea     rcx, [rsp+280h+var_250]; this
0x18000f6cd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000f6d2  call    cs:__imp_GetProcessHeap
0x18000f6d8  mov     r8, r14; lpMem
0x18000f6db  xor     edx, edx; dwFlags
0x18000f6dd  mov     rcx, rax; hHeap
0x18000f6e0  call    cs:__imp_HeapFree
0x18000f6e6  mov     rcx, [rbp+188h]; this
0x18000f6ed  lea     r8, aWil; "wil"
0x18000f6f4  mov     r9d, esi; char *
0x18000f6f7  mov     edx, 137h; void *
0x18000f6fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f701  test    rdi, rdi
0x18000f704  jz      short loc_18000F717
0x18000f706  mov     rcx, rdi; hMutex
0x18000f709  call    cs:__imp_ReleaseMutex
0x18000f70f  test    eax, eax
0x18000f711  jz      loc_18000F893
0x18000f717  mov     rcx, rbx; hObject
0x18000f71a  call    cs:__imp_CloseHandle
0x18000f720  test    eax, eax
0x18000f722  jz      loc_18000F829
0x18000f728  jmp     loc_18000F615
0x18000f72d  mov     rax, [rsp+280h+var_250]
0x18000f732  lea     rcx, [r14+28h]; void *
0x18000f736  mov     [r14+10h], rax
0x18000f73a  xor     edx, edx; Val
0x18000f73c  mov     rax, [rsp+280h+var_250+8]
0x18000f741  mov     r8d, 108h; Size
0x18000f747  mov     [r14+18h], rax
0x18000f74b  mov     dword ptr [r14], 1
0x18000f752  mov     [r14+8], rbx
0x18000f756  mov     [rsp+280h+var_250], 0
0x18000f75f  mov     [rsp+280h+var_250+8], 0
0x18000f768  call    memset_0
0x18000f76d  xor     eax, eax
0x18000f76f  lea     rcx, [r14+28h]; this
0x18000f773  mov     [r14+20h], rax
0x18000f777  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000f77c  lea     rbx, [r14+0E8h]
0x18000f783  xor     r8d, r8d; Flags
0x18000f786  mov     rcx, rbx; lpCriticalSection
0x18000f789  xor     edx, edx; dwSpinCount
0x18000f78b  call    cs:__imp_InitializeCriticalSectionEx
0x18000f791  mov     qword ptr [rbx+28h], 0
0x18000f799  lea     rcx, [rsp+280h+var_250]; this
0x18000f79e  mov     qword ptr [rbx+30h], 0
0x18000f7a6  mov     qword ptr [rbx+38h], 0
0x18000f7ae  mov     qword ptr [rbx+40h], 0
0x18000f7b6  mov     [r15], r14
0x18000f7b9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000f7be  xor     ebx, ebx
0x18000f7c0  test    rdi, rdi
0x18000f7c3  jz      short loc_18000F7D6
0x18000f7c5  mov     rcx, rdi; hMutex
0x18000f7c8  call    cs:__imp_ReleaseMutex
0x18000f7ce  test    eax, eax
0x18000f7d0  jz      loc_18000F8AC
0x18000f7d6  test    rbx, rbx
0x18000f7d9  jz      short loc_18000F7E8
0x18000f7db  mov     rcx, rbx; hObject
0x18000f7de  call    cs:__imp_CloseHandle
0x18000f7e4  test    eax, eax
0x18000f7e6  jz      short loc_18000F810
0x18000f7e8  xor     eax, eax
0x18000f7ea  mov     rcx, [rbp+180h+var_30]
0x18000f7f1  xor     rcx, rsp; StackCookie
0x18000f7f4  call    __security_check_cookie
0x18000f7f9  mov     rbx, [rsp+280h+arg_10]
0x18000f801  add     rsp, 260h
0x18000f808  pop     r15
0x18000f80a  pop     r14
0x18000f80c  pop     rdi
0x18000f80d  pop     rsi
0x18000f80e  pop     rbp
0x18000f80f  retn
0x18000f810  mov     rcx, [rbp+188h]; this
0x18000f817  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f81e  mov     edx, 0A0Bh; void *
0x18000f823  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f829  mov     rcx, [rbp+188h]; this
0x18000f830  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f837  mov     edx, 0A0Bh; void *
0x18000f83c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f842  mov     rcx, [rbp+188h]; this
0x18000f849  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f850  mov     edx, 0E01h; void *
0x18000f855  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f85b  mov     rcx, [rbp+188h]; this
0x18000f862  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f869  mov     edx, 0A15h; void *
0x18000f86e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f874  mov     rcx, [rbp+188h]; this
0x18000f87b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f882  mov     edx, 0A0Bh; void *
0x18000f887  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f88d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f893  mov     rcx, [rbp+188h]; this
0x18000f89a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f8a1  mov     edx, 0A15h; void *
0x18000f8a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f8ac  mov     rcx, [rbp+188h]; this
0x18000f8b3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f8ba  mov     edx, 0A15h; void *
0x18000f8bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
