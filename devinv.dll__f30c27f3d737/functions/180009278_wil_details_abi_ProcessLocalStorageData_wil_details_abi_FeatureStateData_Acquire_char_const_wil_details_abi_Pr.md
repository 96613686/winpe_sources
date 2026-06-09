# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009278`
- end: `0x180009669`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009954`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x1800083a4`
- `0x180009278`
- `0x180009670`
- `0x180009bb0`
- `0x18000aa58`
- `0x18000b718`
- `0x18000d184`
- `0x18000dcec`
- `0x18000e1dc`
- `0x18000eaac`
- `0x18000eabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000954b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000954b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800093a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800094e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000957e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800093a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800094e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000957e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009310`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009310`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800092ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800092ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800092b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800092b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000949d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000949d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800094f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009594`

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
0x180009278  mov     [rsp-8+arg_10], rbx
0x18000927d  push    rbp
0x18000927e  push    rsi
0x18000927f  push    rdi
0x180009280  push    r14
0x180009282  push    r15
0x180009284  lea     rbp, [rsp-160h]
0x18000928c  sub     rsp, 260h
0x180009293  mov     rax, cs:__security_cookie
0x18000929a  xor     rax, rsp
0x18000929d  mov     [rbp+180h+var_30], rax
0x1800092a4  mov     r15, rdx
0x1800092a7  mov     qword ptr [rdx], 0
0x1800092ae  mov     rbx, rcx
0x1800092b1  call    cs:__imp_GetCurrentProcessId
0x1800092b7  mov     r14d, 130h
0x1800092bd  mov     [rsp+280h+var_258], rbx
0x1800092c2  mov     r9d, eax
0x1800092c5  mov     [rsp+280h+var_260], r14d; int
0x1800092ca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800092d1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800092d6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800092da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800092df  mov     r9d, 1F0001h; dwDesiredAccess
0x1800092e5  lea     rdx, [rsp+280h+Name]; lpName
0x1800092ea  xor     r8d, r8d; dwFlags
0x1800092ed  xor     ecx, ecx; lpMutexAttributes
0x1800092ef  call    cs:__imp_CreateMutexExW
0x1800092f5  mov     rbx, rax
0x1800092f8  test    rax, rax
0x1800092fb  jnz     short loc_180009307
0x1800092fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009302  jmp     loc_1800095A0
0x180009307  xor     r8d, r8d; bAlertable
0x18000930a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000930d  mov     rcx, rbx; hHandle
0x180009310  call    cs:__imp_WaitForSingleObjectEx
0x180009316  cmp     eax, 102h
0x18000931b  jz      short loc_18000932D
0x18000931d  test    eax, 0FFFFFF7Fh
0x180009322  jnz     loc_1800095EA
0x180009328  mov     rdi, rbx
0x18000932b  jmp     short loc_18000932F
0x18000932d  xor     edi, edi
0x18000932f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009334  mov     [rsp+280h+hObject], 0
0x18000933d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009342  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009347  mov     esi, eax
0x180009349  test    eax, eax
0x18000934b  jns     short loc_1800093CC
0x18000934d  mov     rcx, [rbp+188h]; this
0x180009354  lea     r8, aWil; "wil"
0x18000935b  mov     r9d, eax; char *
0x18000935e  mov     edx, 66h ; 'f'; void *
0x180009363  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009368  mov     rcx, [rbp+188h]; this
0x18000936f  lea     r8, aWil; "wil"
0x180009376  mov     r9d, esi; char *
0x180009379  mov     edx, 6Fh ; 'o'; void *
0x18000937e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009383  mov     rcx, [rbp+188h]; this
0x18000938a  lea     r8, aWil; "wil"
0x180009391  mov     r9d, esi; char *
0x180009394  mov     edx, 12Eh; void *
0x180009399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000939e  test    rdi, rdi
0x1800093a1  jz      short loc_1800093B4
0x1800093a3  mov     rcx, rdi; hMutex
0x1800093a6  call    cs:__imp_ReleaseMutex
0x1800093ac  test    eax, eax
0x1800093ae  jz      loc_1800095F7
0x1800093b4  mov     rcx, rbx; hObject
0x1800093b7  call    cs:__imp_CloseHandle
0x1800093bd  test    eax, eax
0x1800093bf  jz      loc_180009609
0x1800093c5  mov     eax, esi
0x1800093c7  jmp     loc_1800095A0
0x1800093cc  mov     rax, [rsp+280h+hObject]
0x1800093d1  lea     rcx, ds:0[rax*4]
0x1800093d9  test    rcx, rcx
0x1800093dc  jz      short loc_1800093EC
0x1800093de  mov     [r15], rcx
0x1800093e1  mov     eax, [rcx]
0x1800093e3  inc     eax
0x1800093e5  mov     [rcx], eax
0x1800093e7  jmp     loc_180009576
0x1800093ec  mov     rdx, r14; dwBytes
0x1800093ef  mov     qword ptr [r15], 0
0x1800093f6  mov     ecx, 8; dwFlags
0x1800093fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009400  mov     r14, rax
0x180009403  test    rax, rax
0x180009406  jnz     short loc_18000942D
0x180009408  mov     rcx, [rbp+188h]; this
0x18000940f  lea     r8, aWil; "wil"
0x180009416  mov     esi, 8007000Eh
0x18000941b  mov     edx, 14Bh; void *
0x180009420  mov     r9d, esi; char *
0x180009423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009428  jmp     loc_1800094BF
0x18000942d  xorps   xmm0, xmm0
0x180009430  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009436  test    r14b, 3
0x18000943a  jnz     loc_18000961B
0x180009440  mov     r9, r14
0x180009443  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009448  shr     r9, 2; unsigned __int64
0x18000944c  lea     rcx, [rsp+280h+hObject]; this
0x180009451  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009456  mov     esi, eax
0x180009458  test    eax, eax
0x18000945a  jns     loc_180009506
0x180009460  mov     rcx, [rbp+188h]; this
0x180009467  lea     r8, aWil; "wil"
0x18000946e  mov     r9d, eax; char *
0x180009471  mov     edx, 14Eh; void *
0x180009476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000947b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009480  test    rcx, rcx
0x180009483  jz      short loc_180009493
0x180009485  call    cs:__imp_CloseHandle
0x18000948b  test    eax, eax
0x18000948d  jz      loc_180009621
0x180009493  mov     rcx, [rsp+280h+hObject]; hObject
0x180009498  test    rcx, rcx
0x18000949b  jz      short loc_1800094AB
0x18000949d  call    cs:__imp_CloseHandle
0x1800094a3  test    eax, eax
0x1800094a5  jz      loc_180009633
0x1800094ab  call    cs:__imp_GetProcessHeap
0x1800094b1  mov     r8, r14; lpMem
0x1800094b4  xor     edx, edx; dwFlags
0x1800094b6  mov     rcx, rax; hHeap
0x1800094b9  call    cs:__imp_HeapFree
0x1800094bf  mov     rcx, [rbp+188h]; this
0x1800094c6  lea     r8, aWil; "wil"
0x1800094cd  mov     r9d, esi; char *
0x1800094d0  mov     edx, 137h; void *
0x1800094d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094da  test    rdi, rdi
0x1800094dd  jz      short loc_1800094F0
0x1800094df  mov     rcx, rdi; hMutex
0x1800094e2  call    cs:__imp_ReleaseMutex
0x1800094e8  test    eax, eax
0x1800094ea  jz      loc_180009645
0x1800094f0  mov     rcx, rbx; hObject
0x1800094f3  call    cs:__imp_CloseHandle
0x1800094f9  test    eax, eax
0x1800094fb  jz      loc_1800095D8
0x180009501  jmp     loc_1800093C5
0x180009506  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000950b  lea     rcx, [r14+28h]; void *
0x18000950f  mov     dword ptr [r14], 1
0x180009516  xor     edx, edx; Val
0x180009518  mov     [r14+8], rbx
0x18000951c  mov     r8d, 108h; Size
0x180009522  movdqu  xmmword ptr [r14+10h], xmm0
0x180009528  call    memset_0
0x18000952d  xor     eax, eax
0x18000952f  lea     rcx, [r14+28h]; this
0x180009533  mov     [r14+20h], rax
0x180009537  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000953c  lea     rbx, [r14+0E8h]
0x180009543  xor     r8d, r8d; Flags
0x180009546  mov     rcx, rbx; lpCriticalSection
0x180009549  xor     edx, edx; dwSpinCount
0x18000954b  call    cs:__imp_InitializeCriticalSectionEx
0x180009551  mov     qword ptr [rbx+28h], 0
0x180009559  mov     qword ptr [rbx+30h], 0
0x180009561  mov     qword ptr [rbx+38h], 0
0x180009569  mov     qword ptr [rbx+40h], 0
0x180009571  xor     ebx, ebx
0x180009573  mov     [r15], r14
0x180009576  test    rdi, rdi
0x180009579  jz      short loc_18000958C
0x18000957b  mov     rcx, rdi; hMutex
0x18000957e  call    cs:__imp_ReleaseMutex
0x180009584  test    eax, eax
0x180009586  jz      loc_180009657
0x18000958c  test    rbx, rbx
0x18000958f  jz      short loc_18000959E
0x180009591  mov     rcx, rbx; hObject
0x180009594  call    cs:__imp_CloseHandle
0x18000959a  test    eax, eax
0x18000959c  jz      short loc_1800095C6
0x18000959e  xor     eax, eax
0x1800095a0  mov     rcx, [rbp+180h+var_30]
0x1800095a7  xor     rcx, rsp; StackCookie
0x1800095aa  call    __security_check_cookie
0x1800095af  mov     rbx, [rsp+280h+arg_10]
0x1800095b7  add     rsp, 260h
0x1800095be  pop     r15
0x1800095c0  pop     r14
0x1800095c2  pop     rdi
0x1800095c3  pop     rsi
0x1800095c4  pop     rbp
0x1800095c5  retn
0x1800095c6  mov     rcx, [rbp+188h]; this
0x1800095cd  mov     edx, 0A0Bh; void *
0x1800095d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800095d8  mov     rcx, [rbp+188h]; this
0x1800095df  mov     edx, 0A0Bh; void *
0x1800095e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800095ea  mov     rcx, [rbp+188h]; this
0x1800095f1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800095f7  mov     rcx, [rbp+188h]; this
0x1800095fe  mov     edx, 0A15h; void *
0x180009603  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009609  mov     rcx, [rbp+188h]; this
0x180009610  mov     edx, 0A0Bh; void *
0x180009615  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000961b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009621  mov     rcx, [rbp+188h]; this
0x180009628  mov     edx, 0A0Bh; void *
0x18000962d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009633  mov     rcx, [rbp+188h]; this
0x18000963a  mov     edx, 0A0Bh; void *
0x18000963f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009645  mov     rcx, [rbp+188h]; this
0x18000964c  mov     edx, 0A15h; void *
0x180009651  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009657  mov     rcx, [rbp+188h]; this
0x18000965e  mov     edx, 0A15h; void *
0x180009663  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
