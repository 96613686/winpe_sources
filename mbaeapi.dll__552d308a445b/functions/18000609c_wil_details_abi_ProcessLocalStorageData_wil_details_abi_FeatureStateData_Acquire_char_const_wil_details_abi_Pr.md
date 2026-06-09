# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000609c`
- end: `0x180006492`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180006784`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180005134`
- `0x18000609c`
- `0x180006498`
- `0x1800069d8`
- `0x180007308`
- `0x180007cf8`
- `0x180009474`
- `0x180009ffc`
- `0x18000a47c`
- `0x18000ad4c`
- `0x18000ad5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006306`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800063a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006306`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800063a2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006113`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006113`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006134`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006134`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000636f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000636f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063b8`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x18000609c  mov     [rsp-8+arg_10], rbx
0x1800060a1  push    rbp
0x1800060a2  push    rsi
0x1800060a3  push    rdi
0x1800060a4  push    r14
0x1800060a6  push    r15
0x1800060a8  lea     rbp, [rsp-160h]
0x1800060b0  sub     rsp, 260h
0x1800060b7  mov     rax, cs:__security_cookie
0x1800060be  xor     rax, rsp
0x1800060c1  mov     [rbp+180h+var_30], rax
0x1800060c8  mov     r15, rdx
0x1800060cb  mov     qword ptr [rdx], 0
0x1800060d2  mov     rbx, rcx
0x1800060d5  call    cs:__imp_GetCurrentProcessId
0x1800060db  mov     r14d, 130h
0x1800060e1  mov     [rsp+280h+var_258], rbx
0x1800060e6  mov     r9d, eax
0x1800060e9  mov     [rsp+280h+var_260], r14d; int
0x1800060ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800060f5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800060fa  lea     edx, [r14-2Ch]; unsigned __int64
0x1800060fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006103  mov     r9d, 1F0001h; dwDesiredAccess
0x180006109  lea     rdx, [rsp+280h+Name]; lpName
0x18000610e  xor     r8d, r8d; dwFlags
0x180006111  xor     ecx, ecx; lpMutexAttributes
0x180006113  call    cs:__imp_CreateMutexExW
0x180006119  mov     rbx, rax
0x18000611c  test    rax, rax
0x18000611f  jnz     short loc_18000612B
0x180006121  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006126  jmp     loc_1800063C4
0x18000612b  xor     r8d, r8d; bAlertable
0x18000612e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006131  mov     rcx, rbx; hHandle
0x180006134  call    cs:__imp_WaitForSingleObjectEx
0x18000613a  cmp     eax, 102h
0x18000613f  jz      short loc_180006151
0x180006141  test    eax, 0FFFFFF7Fh
0x180006146  jnz     loc_18000640E
0x18000614c  mov     rdi, rbx
0x18000614f  jmp     short loc_180006153
0x180006151  xor     edi, edi
0x180006153  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006158  mov     [rsp+280h+hObject], 0
0x180006161  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006166  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000616b  mov     esi, eax
0x18000616d  test    eax, eax
0x18000616f  jns     short loc_1800061F0
0x180006171  mov     rcx, [rbp+188h]; this
0x180006178  lea     r8, aWil; "wil"
0x18000617f  mov     r9d, eax; char *
0x180006182  mov     edx, 66h ; 'f'; void *
0x180006187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000618c  mov     rcx, [rbp+188h]; this
0x180006193  lea     r8, aWil; "wil"
0x18000619a  mov     r9d, esi; char *
0x18000619d  mov     edx, 6Fh ; 'o'; void *
0x1800061a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061a7  mov     rcx, [rbp+188h]; this
0x1800061ae  lea     r8, aWil; "wil"
0x1800061b5  mov     r9d, esi; char *
0x1800061b8  mov     edx, 12Eh; void *
0x1800061bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061c2  test    rdi, rdi
0x1800061c5  jz      short loc_1800061D8
0x1800061c7  mov     rcx, rdi; hMutex
0x1800061ca  call    cs:__imp_ReleaseMutex
0x1800061d0  test    eax, eax
0x1800061d2  jz      loc_180006420
0x1800061d8  mov     rcx, rbx; hObject
0x1800061db  call    cs:__imp_CloseHandle
0x1800061e1  test    eax, eax
0x1800061e3  jz      loc_180006432
0x1800061e9  mov     eax, esi
0x1800061eb  jmp     loc_1800063C4
0x1800061f0  mov     rax, [rsp+280h+hObject]
0x1800061f5  lea     rcx, ds:0[rax*4]
0x1800061fd  test    rcx, rcx
0x180006200  jz      short loc_180006210
0x180006202  mov     [r15], rcx
0x180006205  mov     eax, [rcx]
0x180006207  inc     eax
0x180006209  mov     [rcx], eax
0x18000620b  jmp     loc_18000639A
0x180006210  mov     rdx, r14; dwBytes
0x180006213  mov     qword ptr [r15], 0
0x18000621a  mov     ecx, 8; dwFlags
0x18000621f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006224  mov     r14, rax
0x180006227  test    rax, rax
0x18000622a  jnz     short loc_180006251
0x18000622c  mov     rcx, [rbp+188h]; this
0x180006233  lea     r8, aWil; "wil"
0x18000623a  mov     esi, 8007000Eh
0x18000623f  mov     edx, 14Bh; void *
0x180006244  mov     r9d, esi; char *
0x180006247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000624c  jmp     loc_1800062E3
0x180006251  xorps   xmm0, xmm0
0x180006254  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000625a  test    r14b, 3
0x18000625e  jnz     loc_180006444
0x180006264  mov     r9, r14
0x180006267  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000626c  shr     r9, 2; unsigned __int64
0x180006270  lea     rcx, [rsp+280h+hObject]; this
0x180006275  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000627a  mov     esi, eax
0x18000627c  test    eax, eax
0x18000627e  jns     loc_18000632A
0x180006284  mov     rcx, [rbp+188h]; this
0x18000628b  lea     r8, aWil; "wil"
0x180006292  mov     r9d, eax; char *
0x180006295  mov     edx, 14Eh; void *
0x18000629a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000629f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800062a4  test    rcx, rcx
0x1800062a7  jz      short loc_1800062B7
0x1800062a9  call    cs:__imp_CloseHandle
0x1800062af  test    eax, eax
0x1800062b1  jz      loc_18000644A
0x1800062b7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800062bc  test    rcx, rcx
0x1800062bf  jz      short loc_1800062CF
0x1800062c1  call    cs:__imp_CloseHandle
0x1800062c7  test    eax, eax
0x1800062c9  jz      loc_18000645C
0x1800062cf  call    cs:__imp_GetProcessHeap
0x1800062d5  mov     r8, r14; lpMem
0x1800062d8  xor     edx, edx; dwFlags
0x1800062da  mov     rcx, rax; hHeap
0x1800062dd  call    cs:__imp_HeapFree
0x1800062e3  mov     rcx, [rbp+188h]; this
0x1800062ea  lea     r8, aWil; "wil"
0x1800062f1  mov     r9d, esi; char *
0x1800062f4  mov     edx, 137h; void *
0x1800062f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062fe  test    rdi, rdi
0x180006301  jz      short loc_180006314
0x180006303  mov     rcx, rdi; hMutex
0x180006306  call    cs:__imp_ReleaseMutex
0x18000630c  test    eax, eax
0x18000630e  jz      loc_18000646E
0x180006314  mov     rcx, rbx; hObject
0x180006317  call    cs:__imp_CloseHandle
0x18000631d  test    eax, eax
0x18000631f  jz      loc_1800063FC
0x180006325  jmp     loc_1800061E9
0x18000632a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000632f  lea     rcx, [r14+28h]; void *
0x180006333  mov     dword ptr [r14], 1
0x18000633a  xor     edx, edx; Val
0x18000633c  mov     [r14+8], rbx
0x180006340  mov     r8d, 108h; Size
0x180006346  movdqu  xmmword ptr [r14+10h], xmm0
0x18000634c  call    memset_0
0x180006351  xor     eax, eax
0x180006353  lea     rcx, [r14+28h]; this
0x180006357  mov     [r14+20h], rax
0x18000635b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006360  lea     rbx, [r14+0E8h]
0x180006367  xor     r8d, r8d; Flags
0x18000636a  mov     rcx, rbx; lpCriticalSection
0x18000636d  xor     edx, edx; dwSpinCount
0x18000636f  call    cs:__imp_InitializeCriticalSectionEx
0x180006375  mov     qword ptr [rbx+28h], 0
0x18000637d  mov     qword ptr [rbx+30h], 0
0x180006385  mov     qword ptr [rbx+38h], 0
0x18000638d  mov     qword ptr [rbx+40h], 0
0x180006395  xor     ebx, ebx
0x180006397  mov     [r15], r14
0x18000639a  test    rdi, rdi
0x18000639d  jz      short loc_1800063B0
0x18000639f  mov     rcx, rdi; hMutex
0x1800063a2  call    cs:__imp_ReleaseMutex
0x1800063a8  test    eax, eax
0x1800063aa  jz      loc_180006480
0x1800063b0  test    rbx, rbx
0x1800063b3  jz      short loc_1800063C2
0x1800063b5  mov     rcx, rbx; hObject
0x1800063b8  call    cs:__imp_CloseHandle
0x1800063be  test    eax, eax
0x1800063c0  jz      short loc_1800063EA
0x1800063c2  xor     eax, eax
0x1800063c4  mov     rcx, [rbp+180h+var_30]
0x1800063cb  xor     rcx, rsp; StackCookie
0x1800063ce  call    __security_check_cookie
0x1800063d3  mov     rbx, [rsp+280h+arg_10]
0x1800063db  add     rsp, 260h
0x1800063e2  pop     r15
0x1800063e4  pop     r14
0x1800063e6  pop     rdi
0x1800063e7  pop     rsi
0x1800063e8  pop     rbp
0x1800063e9  retn
0x1800063ea  mov     rcx, [rbp+188h]; this
0x1800063f1  mov     edx, 0A0Bh; void *
0x1800063f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063fc  mov     rcx, [rbp+188h]; this
0x180006403  mov     edx, 0A0Bh; void *
0x180006408  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000640e  mov     rcx, [rbp+188h]; this
0x180006415  mov     edx, 0E01h; void *
0x18000641a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006420  mov     rcx, [rbp+188h]; this
0x180006427  mov     edx, 0A15h; void *
0x18000642c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006432  mov     rcx, [rbp+188h]; this
0x180006439  mov     edx, 0A0Bh; void *
0x18000643e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006444  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000644a  mov     rcx, [rbp+188h]; this
0x180006451  mov     edx, 0A0Bh; void *
0x180006456  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000645c  mov     rcx, [rbp+188h]; this
0x180006463  mov     edx, 0A0Bh; void *
0x180006468  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000646e  mov     rcx, [rbp+188h]; this
0x180006475  mov     edx, 0A15h; void *
0x18000647a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006480  mov     rcx, [rbp+188h]; this
0x180006487  mov     edx, 0A15h; void *
0x18000648c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
