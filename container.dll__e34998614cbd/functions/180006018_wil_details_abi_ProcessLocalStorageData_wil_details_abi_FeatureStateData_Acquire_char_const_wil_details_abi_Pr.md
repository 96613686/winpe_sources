# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006018`
- end: `0x1800063ea`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000691c`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x180004e84`
- `0x1800057b8`
- `0x180006018`
- `0x1800065d8`
- `0x180006a98`
- `0x180007430`
- `0x18000889c`
- `0x18000a314`
- `0x18000b030`
- `0x18000b4dc`
- `0x18000bdac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800062d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800062d9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006095`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006095`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800060bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800060bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006143`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000624b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000631c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006143`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000624b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000631c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000620f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000620f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006051`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000615a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000615a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006338`

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
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x180006018  mov     [rsp-8+arg_10], rbx
0x18000601d  push    rbp
0x18000601e  push    rsi
0x18000601f  push    rdi
0x180006020  push    r14
0x180006022  push    r15
0x180006024  lea     rbp, [rsp-160h]
0x18000602c  sub     rsp, 260h
0x180006033  mov     rax, cs:__security_cookie
0x18000603a  xor     rax, rsp
0x18000603d  mov     [rbp+180h+var_30], rax
0x180006044  mov     r15, rdx
0x180006047  mov     qword ptr [rdx], 0
0x18000604e  mov     rbx, rcx
0x180006051  call    cs:__imp_GetCurrentProcessId
0x180006058  nop     dword ptr [rax+rax+00h]
0x18000605d  mov     r14d, 130h
0x180006063  mov     [rsp+280h+var_258], rbx
0x180006068  mov     r9d, eax
0x18000606b  mov     [rsp+280h+var_260], r14d; int
0x180006070  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006077  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000607c  lea     edx, [r14-2Ch]; unsigned __int64
0x180006080  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006085  mov     r9d, 1F0001h; dwDesiredAccess
0x18000608b  lea     rdx, [rsp+280h+Name]; lpName
0x180006090  xor     r8d, r8d; dwFlags
0x180006093  xor     ecx, ecx; lpMutexAttributes
0x180006095  call    cs:__imp_CreateMutexExW
0x18000609c  nop     dword ptr [rax+rax+00h]
0x1800060a1  mov     rbx, rax
0x1800060a4  test    rax, rax
0x1800060a7  jnz     short loc_1800060B3
0x1800060a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800060ae  jmp     loc_18000634A
0x1800060b3  xor     r8d, r8d; bAlertable
0x1800060b6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800060b9  mov     rcx, rbx; hHandle
0x1800060bc  call    cs:__imp_WaitForSingleObjectEx
0x1800060c3  nop     dword ptr [rax+rax+00h]
0x1800060c8  cmp     eax, 102h
0x1800060cd  jz      short loc_1800060DF
0x1800060cf  test    eax, 0FFFFFF7Fh
0x1800060d4  jnz     loc_180006395
0x1800060da  mov     rdi, rbx
0x1800060dd  jmp     short loc_1800060E1
0x1800060df  xor     edi, edi
0x1800060e1  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800060e6  mov     [rsp+280h+var_250], 0
0x1800060ef  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800060f4  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800060f9  mov     esi, eax
0x1800060fb  test    eax, eax
0x1800060fd  jns     short loc_180006175
0x1800060ff  mov     rcx, [rbp+188h]; this
0x180006106  mov     r9d, eax; char *
0x180006109  mov     edx, 66h ; 'f'; void *
0x18000610e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006113  mov     rcx, [rbp+188h]; this
0x18000611a  mov     r9d, esi; char *
0x18000611d  mov     edx, 6Fh ; 'o'; void *
0x180006122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006127  mov     rcx, [rbp+188h]; this
0x18000612e  mov     r9d, esi; char *
0x180006131  mov     edx, 12Eh; void *
0x180006136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000613b  test    rdi, rdi
0x18000613e  jz      short loc_180006157
0x180006140  mov     rcx, rdi; hMutex
0x180006143  call    cs:__imp_ReleaseMutex
0x18000614a  nop     dword ptr [rax+rax+00h]
0x18000614f  test    eax, eax
0x180006151  jz      loc_1800063A2
0x180006157  mov     rcx, rbx; hObject
0x18000615a  call    cs:__imp_CloseHandle
0x180006161  nop     dword ptr [rax+rax+00h]
0x180006166  test    eax, eax
0x180006168  jz      loc_1800063B4
0x18000616e  mov     eax, esi
0x180006170  jmp     loc_18000634A
0x180006175  mov     rax, [rsp+280h+var_250]
0x18000617a  lea     rcx, ds:0[rax*4]
0x180006182  test    rcx, rcx
0x180006185  jz      short loc_180006195
0x180006187  mov     [r15], rcx
0x18000618a  mov     eax, [rcx]
0x18000618c  inc     eax
0x18000618e  mov     [rcx], eax
0x180006190  jmp     loc_180006314
0x180006195  mov     rdx, r14; dwBytes
0x180006198  mov     qword ptr [r15], 0
0x18000619f  mov     ecx, 8; dwFlags
0x1800061a4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800061a9  mov     r14, rax
0x1800061ac  test    rax, rax
0x1800061af  jnz     short loc_1800061CC
0x1800061b1  mov     rcx, [rbp+188h]; this
0x1800061b8  mov     esi, 8007000Eh
0x1800061bd  mov     r9d, esi; char *
0x1800061c0  mov     edx, 14Bh; void *
0x1800061c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061ca  jmp     short loc_18000622F
0x1800061cc  xorps   xmm0, xmm0
0x1800061cf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800061d4  mov     r8, r14; void *
0x1800061d7  lea     rcx, [rsp+280h+var_250]; this
0x1800061dc  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800061e2  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800061e7  mov     esi, eax
0x1800061e9  test    eax, eax
0x1800061eb  jns     loc_18000627B
0x1800061f1  mov     rcx, [rbp+188h]; this
0x1800061f8  mov     r9d, eax; char *
0x1800061fb  mov     edx, 14Eh; void *
0x180006200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006205  lea     rcx, [rsp+280h+var_250]; this
0x18000620a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000620f  call    cs:__imp_GetProcessHeap
0x180006216  nop     dword ptr [rax+rax+00h]
0x18000621b  mov     r8, r14; lpMem
0x18000621e  xor     edx, edx; dwFlags
0x180006220  mov     rcx, rax; hHeap
0x180006223  call    cs:__imp_HeapFree
0x18000622a  nop     dword ptr [rax+rax+00h]
0x18000622f  mov     rcx, [rbp+188h]; this
0x180006236  mov     r9d, esi; char *
0x180006239  mov     edx, 137h; void *
0x18000623e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006243  test    rdi, rdi
0x180006246  jz      short loc_18000625F
0x180006248  mov     rcx, rdi; hMutex
0x18000624b  call    cs:__imp_ReleaseMutex
0x180006252  nop     dword ptr [rax+rax+00h]
0x180006257  test    eax, eax
0x180006259  jz      loc_1800063C6
0x18000625f  mov     rcx, rbx; hObject
0x180006262  call    cs:__imp_CloseHandle
0x180006269  nop     dword ptr [rax+rax+00h]
0x18000626e  test    eax, eax
0x180006270  jz      loc_180006383
0x180006276  jmp     loc_18000616E
0x18000627b  mov     rax, [rsp+280h+var_250]
0x180006280  lea     rcx, [r14+28h]; void *
0x180006284  mov     [r14+10h], rax
0x180006288  xor     edx, edx; Val
0x18000628a  mov     rax, [rsp+280h+var_250+8]
0x18000628f  mov     r8d, 108h; Size
0x180006295  mov     [r14+18h], rax
0x180006299  mov     dword ptr [r14], 1
0x1800062a0  mov     [r14+8], rbx
0x1800062a4  mov     [rsp+280h+var_250], 0
0x1800062ad  mov     [rsp+280h+var_250+8], 0
0x1800062b6  call    memset_0
0x1800062bb  xor     eax, eax
0x1800062bd  lea     rcx, [r14+28h]; this
0x1800062c1  mov     [r14+20h], rax
0x1800062c5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800062ca  lea     rbx, [r14+0E8h]
0x1800062d1  xor     r8d, r8d; Flags
0x1800062d4  mov     rcx, rbx; lpCriticalSection
0x1800062d7  xor     edx, edx; dwSpinCount
0x1800062d9  call    cs:__imp_InitializeCriticalSectionEx
0x1800062e0  nop     dword ptr [rax+rax+00h]
0x1800062e5  mov     qword ptr [rbx+28h], 0
0x1800062ed  lea     rcx, [rsp+280h+var_250]; this
0x1800062f2  mov     qword ptr [rbx+30h], 0
0x1800062fa  mov     qword ptr [rbx+38h], 0
0x180006302  mov     qword ptr [rbx+40h], 0
0x18000630a  mov     [r15], r14
0x18000630d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006312  xor     ebx, ebx
0x180006314  test    rdi, rdi
0x180006317  jz      short loc_180006330
0x180006319  mov     rcx, rdi; hMutex
0x18000631c  call    cs:__imp_ReleaseMutex
0x180006323  nop     dword ptr [rax+rax+00h]
0x180006328  test    eax, eax
0x18000632a  jz      loc_1800063D8
0x180006330  test    rbx, rbx
0x180006333  jz      short loc_180006348
0x180006335  mov     rcx, rbx; hObject
0x180006338  call    cs:__imp_CloseHandle
0x18000633f  nop     dword ptr [rax+rax+00h]
0x180006344  test    eax, eax
0x180006346  jz      short loc_180006371
0x180006348  xor     eax, eax
0x18000634a  mov     rcx, [rbp+180h+var_30]
0x180006351  xor     rcx, rsp; StackCookie
0x180006354  call    __security_check_cookie
0x180006359  mov     rbx, [rsp+280h+arg_10]
0x180006361  add     rsp, 260h
0x180006368  pop     r15
0x18000636a  pop     r14
0x18000636c  pop     rdi
0x18000636d  pop     rsi
0x18000636e  pop     rbp
0x18000636f  retn
0x180006371  mov     rcx, [rbp+188h]; this
0x180006378  mov     edx, 0A0Bh; void *
0x18000637d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006383  mov     rcx, [rbp+188h]; this
0x18000638a  mov     edx, 0A0Bh; void *
0x18000638f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006395  mov     rcx, [rbp+188h]; this
0x18000639c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800063a2  mov     rcx, [rbp+188h]; this
0x1800063a9  mov     edx, 0A15h; void *
0x1800063ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063b4  mov     rcx, [rbp+188h]; this
0x1800063bb  mov     edx, 0A0Bh; void *
0x1800063c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063c6  mov     rcx, [rbp+188h]; this
0x1800063cd  mov     edx, 0A15h; void *
0x1800063d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063d8  mov     rcx, [rbp+188h]; this
0x1800063df  mov     edx, 0A15h; void *
0x1800063e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
