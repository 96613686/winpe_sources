# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800034ac`
- end: `0x18000384a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000429c`

## callees

- `0x180001190`
- `0x180001962`
- `0x1800034ac`
- `0x18000385c`
- `0x180003aa0`
- `0x180004038`
- `0x180004b28`
- `0x180004e14`
- `0x180005274`
- `0x180005300`
- `0x1800056fc`
- `0x18000570c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003524`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003524`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003545`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003545`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000375f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800035c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000375f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003775`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1800034ac  mov     [rsp-8+arg_10], rbx
0x1800034b1  push    rbp
0x1800034b2  push    rsi
0x1800034b3  push    rdi
0x1800034b4  push    r14
0x1800034b6  push    r15
0x1800034b8  lea     rbp, [rsp-160h]
0x1800034c0  sub     rsp, 260h
0x1800034c7  mov     rax, cs:__security_cookie
0x1800034ce  xor     rax, rsp
0x1800034d1  mov     [rbp+180h+var_30], rax
0x1800034d8  mov     r15, rdx
0x1800034db  mov     qword ptr [rdx], 0
0x1800034e2  mov     rbx, rcx
0x1800034e5  call    cs:__imp_GetCurrentProcessId
0x1800034eb  mov     r14d, 78h ; 'x'
0x1800034f1  mov     [rsp+280h+var_258], rbx
0x1800034f6  mov     r9d, eax
0x1800034f9  mov     [rsp+280h+var_260], r14d; int
0x1800034fe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003505  mov     edx, 104h; unsigned __int64
0x18000350a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000350f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003514  mov     r9d, 1F0001h; dwDesiredAccess
0x18000351a  lea     rdx, [rsp+280h+Name]; lpName
0x18000351f  xor     r8d, r8d; dwFlags
0x180003522  xor     ecx, ecx; lpMutexAttributes
0x180003524  call    cs:__imp_CreateMutexExW
0x18000352a  mov     rbx, rax
0x18000352d  test    rax, rax
0x180003530  jnz     short loc_18000353C
0x180003532  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003537  jmp     loc_180003781
0x18000353c  xor     r8d, r8d; bAlertable
0x18000353f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003542  mov     rcx, rbx; hHandle
0x180003545  call    cs:__imp_WaitForSingleObjectEx
0x18000354b  cmp     eax, 102h
0x180003550  jz      short loc_180003562
0x180003552  test    eax, 0FFFFFF7Fh
0x180003557  jnz     loc_1800037B9
0x18000355d  mov     rdi, rbx
0x180003560  jmp     short loc_180003564
0x180003562  xor     edi, edi
0x180003564  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003569  mov     [rsp+280h+hObject], 0
0x180003572  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003577  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000357c  mov     esi, eax
0x18000357e  test    eax, eax
0x180003580  jns     short loc_1800035EC
0x180003582  mov     rcx, [rbp+188h]; this
0x180003589  mov     r9d, eax; char *
0x18000358c  mov     edx, 66h ; 'f'; void *
0x180003591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003596  mov     rcx, [rbp+188h]; this
0x18000359d  mov     r9d, esi; char *
0x1800035a0  mov     edx, 6Fh ; 'o'; void *
0x1800035a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035aa  mov     rcx, [rbp+188h]; this
0x1800035b1  mov     r9d, esi; char *
0x1800035b4  mov     edx, 12Eh; void *
0x1800035b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035be  test    rdi, rdi
0x1800035c1  jz      short loc_1800035D4
0x1800035c3  mov     rcx, rdi; hMutex
0x1800035c6  call    cs:__imp_ReleaseMutex
0x1800035cc  test    eax, eax
0x1800035ce  jz      loc_1800037C6
0x1800035d4  mov     rcx, rbx; hObject
0x1800035d7  call    cs:__imp_CloseHandle
0x1800035dd  test    eax, eax
0x1800035df  jz      loc_1800037D8
0x1800035e5  mov     eax, esi
0x1800035e7  jmp     loc_180003781
0x1800035ec  mov     rax, [rsp+280h+hObject]
0x1800035f1  lea     rcx, ds:0[rax*4]
0x1800035f9  test    rcx, rcx
0x1800035fc  jz      short loc_18000360C
0x1800035fe  mov     [r15], rcx
0x180003601  mov     eax, [rcx]
0x180003603  inc     eax
0x180003605  mov     [rcx], eax
0x180003607  jmp     loc_180003757
0x18000360c  mov     rdx, r14; dwBytes
0x18000360f  mov     qword ptr [r15], 0
0x180003616  mov     ecx, 8; dwFlags
0x18000361b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003620  mov     rsi, rax
0x180003623  test    rax, rax
0x180003626  jnz     short loc_180003647
0x180003628  mov     rcx, [rbp+188h]; this
0x18000362f  mov     r14d, 8007000Eh
0x180003635  mov     r9d, r14d; char *
0x180003638  mov     edx, 14Bh; void *
0x18000363d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003642  jmp     loc_1800036D3
0x180003647  xorps   xmm0, xmm0
0x18000364a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003650  test    sil, 3
0x180003654  jnz     loc_1800037EA
0x18000365a  mov     r9, rsi
0x18000365d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003662  shr     r9, 2; unsigned __int64
0x180003666  lea     rcx, [rsp+280h+hObject]; this
0x18000366b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003670  mov     r14d, eax
0x180003673  test    eax, eax
0x180003675  jns     loc_180003713
0x18000367b  mov     rcx, [rbp+188h]; this
0x180003682  mov     r9d, eax; char *
0x180003685  mov     edx, 14Eh; void *
0x18000368a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000368f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003694  test    rcx, rcx
0x180003697  jz      short loc_1800036A7
0x180003699  call    cs:__imp_CloseHandle
0x18000369f  test    eax, eax
0x1800036a1  jz      loc_1800037F0
0x1800036a7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800036ac  test    rcx, rcx
0x1800036af  jz      short loc_1800036BF
0x1800036b1  call    cs:__imp_CloseHandle
0x1800036b7  test    eax, eax
0x1800036b9  jz      loc_180003802
0x1800036bf  call    cs:__imp_GetProcessHeap
0x1800036c5  mov     r8, rsi; lpMem
0x1800036c8  xor     edx, edx; dwFlags
0x1800036ca  mov     rcx, rax; hHeap
0x1800036cd  call    cs:__imp_HeapFree
0x1800036d3  mov     rcx, [rbp+188h]; this
0x1800036da  mov     r9d, r14d; char *
0x1800036dd  mov     edx, 137h; void *
0x1800036e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036e7  test    rdi, rdi
0x1800036ea  jz      short loc_1800036FD
0x1800036ec  mov     rcx, rdi; hMutex
0x1800036ef  call    cs:__imp_ReleaseMutex
0x1800036f5  test    eax, eax
0x1800036f7  jz      loc_180003814
0x1800036fd  mov     rcx, rbx; hObject
0x180003700  call    cs:__imp_CloseHandle
0x180003706  test    eax, eax
0x180003708  jz      loc_180003826
0x18000370e  mov     eax, r14d
0x180003711  jmp     short loc_180003781
0x180003713  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003718  xor     edx, edx; Val
0x18000371a  mov     dword ptr [rsi], 1
0x180003720  lea     rcx, [rsi+22h]; void *
0x180003724  mov     [rsi+8], rbx
0x180003728  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000372d  lea     r8d, [rdx+56h]; Size
0x180003731  call    memset_0
0x180003736  xor     edx, edx; Val
0x180003738  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000373e  lea     rcx, [rsi+28h]; void *
0x180003742  mov     dword ptr [rsi+24h], 1
0x180003749  lea     r8d, [rdx+50h]; Size
0x18000374d  call    memset_0
0x180003752  xor     ebx, ebx
0x180003754  mov     [r15], rsi
0x180003757  test    rdi, rdi
0x18000375a  jz      short loc_18000376D
0x18000375c  mov     rcx, rdi; hMutex
0x18000375f  call    cs:__imp_ReleaseMutex
0x180003765  test    eax, eax
0x180003767  jz      loc_180003838
0x18000376d  test    rbx, rbx
0x180003770  jz      short loc_18000377F
0x180003772  mov     rcx, rbx; hObject
0x180003775  call    cs:__imp_CloseHandle
0x18000377b  test    eax, eax
0x18000377d  jz      short loc_1800037A7
0x18000377f  xor     eax, eax
0x180003781  mov     rcx, [rbp+180h+var_30]
0x180003788  xor     rcx, rsp; StackCookie
0x18000378b  call    __security_check_cookie
0x180003790  mov     rbx, [rsp+280h+arg_10]
0x180003798  add     rsp, 260h
0x18000379f  pop     r15
0x1800037a1  pop     r14
0x1800037a3  pop     rdi
0x1800037a4  pop     rsi
0x1800037a5  pop     rbp
0x1800037a6  retn
0x1800037a7  mov     rcx, [rbp+188h]; this
0x1800037ae  mov     edx, 0A0Bh; void *
0x1800037b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037b9  mov     rcx, [rbp+188h]; this
0x1800037c0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800037c6  mov     rcx, [rbp+188h]; this
0x1800037cd  mov     edx, 0A15h; void *
0x1800037d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037d8  mov     rcx, [rbp+188h]; this
0x1800037df  mov     edx, 0A0Bh; void *
0x1800037e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037ea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800037f0  mov     rcx, [rbp+188h]; this
0x1800037f7  mov     edx, 0A0Bh; void *
0x1800037fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003802  mov     rcx, [rbp+188h]; this
0x180003809  mov     edx, 0A0Bh; void *
0x18000380e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003814  mov     rcx, [rbp+188h]; this
0x18000381b  mov     edx, 0A15h; void *
0x180003820  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003826  mov     rcx, [rbp+188h]; this
0x18000382d  mov     edx, 0A0Bh; void *
0x180003832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003838  mov     rcx, [rbp+188h]; this
0x18000383f  mov     edx, 0A15h; void *
0x180003844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
