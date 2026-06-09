# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140007368`
- end: `0x140007730`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140009980`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140007368`
- `0x140007f28`
- `0x14000855c`
- `0x140009674`
- `0x14000a910`
- `0x14000c8d4`
- `0x14000dad4`
- `0x14000de70`
- `0x1400100dc`
- `0x1400100ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400073e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400073e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140007401`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140007401`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007497`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400075d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007645`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007497`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400075d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000759e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000759e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400073a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400073a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400074a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007578`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400075e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000765b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400074a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007578`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400075e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000765b`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x140007368  mov     [rsp-8+arg_10], rbx
0x14000736d  push    rbp
0x14000736e  push    rsi
0x14000736f  push    rdi
0x140007370  push    r14
0x140007372  push    r15
0x140007374  lea     rbp, [rsp-160h]
0x14000737c  sub     rsp, 260h
0x140007383  mov     rax, cs:__security_cookie
0x14000738a  xor     rax, rsp
0x14000738d  mov     [rbp+180h+var_30], rax
0x140007394  mov     r15, rdx
0x140007397  mov     qword ptr [rdx], 0
0x14000739e  mov     rbx, rcx
0x1400073a1  call    cs:__imp_GetCurrentProcessId
0x1400073a7  mov     r14d, 78h ; 'x'
0x1400073ad  mov     [rsp+280h+var_258], rbx
0x1400073b2  mov     r9d, eax
0x1400073b5  mov     [rsp+280h+var_260], r14d; int
0x1400073ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400073c1  mov     edx, 104h; unsigned __int64
0x1400073c6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400073cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400073d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400073d6  lea     rdx, [rsp+280h+Name]; lpName
0x1400073db  xor     r8d, r8d; dwFlags
0x1400073de  xor     ecx, ecx; lpMutexAttributes
0x1400073e0  call    cs:__imp_CreateMutexExW
0x1400073e6  mov     rbx, rax
0x1400073e9  test    rax, rax
0x1400073ec  jnz     short loc_1400073F8
0x1400073ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400073f3  jmp     loc_140007667
0x1400073f8  xor     r8d, r8d; bAlertable
0x1400073fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400073fe  mov     rcx, rbx; hHandle
0x140007401  call    cs:__imp_WaitForSingleObjectEx
0x140007407  cmp     eax, 102h
0x14000740c  jz      short loc_14000741E
0x14000740e  test    eax, 0FFFFFF7Fh
0x140007413  jnz     loc_14000769F
0x140007419  mov     rdi, rbx
0x14000741c  jmp     short loc_140007420
0x14000741e  xor     edi, edi
0x140007420  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140007425  mov     [rsp+280h+hObject], 0
0x14000742e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007433  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140007438  mov     esi, eax
0x14000743a  test    eax, eax
0x14000743c  jns     short loc_1400074BD
0x14000743e  mov     rcx, [rbp+188h]; this
0x140007445  lea     r8, aWil; "wil"
0x14000744c  mov     r9d, eax; char *
0x14000744f  mov     edx, 66h ; 'f'; void *
0x140007454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007459  mov     rcx, [rbp+188h]; this
0x140007460  lea     r8, aWil; "wil"
0x140007467  mov     r9d, esi; char *
0x14000746a  mov     edx, 6Fh ; 'o'; void *
0x14000746f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007474  mov     rcx, [rbp+188h]; this
0x14000747b  lea     r8, aWil; "wil"
0x140007482  mov     r9d, esi; char *
0x140007485  mov     edx, 12Eh; void *
0x14000748a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000748f  test    rdi, rdi
0x140007492  jz      short loc_1400074A5
0x140007494  mov     rcx, rdi; hMutex
0x140007497  call    cs:__imp_ReleaseMutex
0x14000749d  test    eax, eax
0x14000749f  jz      loc_1400076AC
0x1400074a5  mov     rcx, rbx; hObject
0x1400074a8  call    cs:__imp_CloseHandle
0x1400074ae  test    eax, eax
0x1400074b0  jz      loc_1400076BE
0x1400074b6  mov     eax, esi
0x1400074b8  jmp     loc_140007667
0x1400074bd  mov     rax, [rsp+280h+hObject]
0x1400074c2  lea     rcx, ds:0[rax*4]
0x1400074ca  test    rcx, rcx
0x1400074cd  jz      short loc_1400074DD
0x1400074cf  mov     [r15], rcx
0x1400074d2  mov     eax, [rcx]
0x1400074d4  inc     eax
0x1400074d6  mov     [rcx], eax
0x1400074d8  jmp     loc_14000763D
0x1400074dd  mov     rdx, r14; dwBytes
0x1400074e0  mov     qword ptr [r15], 0
0x1400074e7  mov     ecx, 8; dwFlags
0x1400074ec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400074f1  mov     rsi, rax
0x1400074f4  test    rax, rax
0x1400074f7  jnz     short loc_14000751F
0x1400074f9  mov     rcx, [rbp+188h]; this
0x140007500  lea     r8, aWil; "wil"
0x140007507  mov     r14d, 8007000Eh
0x14000750d  mov     edx, 14Bh; void *
0x140007512  mov     r9d, r14d; char *
0x140007515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000751a  jmp     loc_1400075B2
0x14000751f  xorps   xmm0, xmm0
0x140007522  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140007528  test    sil, 3
0x14000752c  jnz     loc_1400076D0
0x140007532  mov     r9, rsi
0x140007535  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000753a  shr     r9, 2; unsigned __int64
0x14000753e  lea     rcx, [rsp+280h+hObject]; this
0x140007543  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140007548  mov     r14d, eax
0x14000754b  test    eax, eax
0x14000754d  jns     loc_1400075F9
0x140007553  mov     rcx, [rbp+188h]; this
0x14000755a  lea     r8, aWil; "wil"
0x140007561  mov     r9d, eax; char *
0x140007564  mov     edx, 14Eh; void *
0x140007569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000756e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140007573  test    rcx, rcx
0x140007576  jz      short loc_140007586
0x140007578  call    cs:__imp_CloseHandle
0x14000757e  test    eax, eax
0x140007580  jz      loc_1400076D6
0x140007586  mov     rcx, [rsp+280h+hObject]; hObject
0x14000758b  test    rcx, rcx
0x14000758e  jz      short loc_14000759E
0x140007590  call    cs:__imp_CloseHandle
0x140007596  test    eax, eax
0x140007598  jz      loc_1400076E8
0x14000759e  call    cs:__imp_GetProcessHeap
0x1400075a4  mov     r8, rsi; lpMem
0x1400075a7  xor     edx, edx; dwFlags
0x1400075a9  mov     rcx, rax; hHeap
0x1400075ac  call    cs:__imp_HeapFree
0x1400075b2  mov     rcx, [rbp+188h]; this
0x1400075b9  lea     r8, aWil; "wil"
0x1400075c0  mov     r9d, r14d; char *
0x1400075c3  mov     edx, 137h; void *
0x1400075c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400075cd  test    rdi, rdi
0x1400075d0  jz      short loc_1400075E3
0x1400075d2  mov     rcx, rdi; hMutex
0x1400075d5  call    cs:__imp_ReleaseMutex
0x1400075db  test    eax, eax
0x1400075dd  jz      loc_1400076FA
0x1400075e3  mov     rcx, rbx; hObject
0x1400075e6  call    cs:__imp_CloseHandle
0x1400075ec  test    eax, eax
0x1400075ee  jz      loc_14000770C
0x1400075f4  mov     eax, r14d
0x1400075f7  jmp     short loc_140007667
0x1400075f9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400075fe  xor     edx, edx; Val
0x140007600  mov     dword ptr [rsi], 1
0x140007606  lea     rcx, [rsi+22h]; void *
0x14000760a  mov     [rsi+8], rbx
0x14000760e  movdqu  xmmword ptr [rsi+10h], xmm0
0x140007613  lea     r8d, [rdx+56h]; Size
0x140007617  call    memset_0
0x14000761c  xor     edx, edx; Val
0x14000761e  mov     word ptr [rsi+20h], 58h ; 'X'
0x140007624  lea     rcx, [rsi+28h]; void *
0x140007628  mov     dword ptr [rsi+24h], 1
0x14000762f  lea     r8d, [rdx+50h]; Size
0x140007633  call    memset_0
0x140007638  xor     ebx, ebx
0x14000763a  mov     [r15], rsi
0x14000763d  test    rdi, rdi
0x140007640  jz      short loc_140007653
0x140007642  mov     rcx, rdi; hMutex
0x140007645  call    cs:__imp_ReleaseMutex
0x14000764b  test    eax, eax
0x14000764d  jz      loc_14000771E
0x140007653  test    rbx, rbx
0x140007656  jz      short loc_140007665
0x140007658  mov     rcx, rbx; hObject
0x14000765b  call    cs:__imp_CloseHandle
0x140007661  test    eax, eax
0x140007663  jz      short loc_14000768D
0x140007665  xor     eax, eax
0x140007667  mov     rcx, [rbp+180h+var_30]
0x14000766e  xor     rcx, rsp; StackCookie
0x140007671  call    __security_check_cookie
0x140007676  mov     rbx, [rsp+280h+arg_10]
0x14000767e  add     rsp, 260h
0x140007685  pop     r15
0x140007687  pop     r14
0x140007689  pop     rdi
0x14000768a  pop     rsi
0x14000768b  pop     rbp
0x14000768c  retn
0x14000768d  mov     rcx, [rbp+188h]; this
0x140007694  mov     edx, 0A0Bh; void *
0x140007699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000769f  mov     rcx, [rbp+188h]; this
0x1400076a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400076ac  mov     rcx, [rbp+188h]; this
0x1400076b3  mov     edx, 0A15h; void *
0x1400076b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400076be  mov     rcx, [rbp+188h]; this
0x1400076c5  mov     edx, 0A0Bh; void *
0x1400076ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400076d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400076d6  mov     rcx, [rbp+188h]; this
0x1400076dd  mov     edx, 0A0Bh; void *
0x1400076e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400076e8  mov     rcx, [rbp+188h]; this
0x1400076ef  mov     edx, 0A0Bh; void *
0x1400076f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400076fa  mov     rcx, [rbp+188h]; this
0x140007701  mov     edx, 0A15h; void *
0x140007706  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000770c  mov     rcx, [rbp+188h]; this
0x140007713  mov     edx, 0A0Bh; void *
0x140007718  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000771e  mov     rcx, [rbp+188h]; this
0x140007725  mov     edx, 0A15h; void *
0x14000772a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
