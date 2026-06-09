# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800095cc`
- end: `0x1800099bd`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009bf4`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x180004f08`
- `0x1800051f4`
- `0x180005858`
- `0x1800063d8`
- `0x1800067c4`
- `0x180007228`
- `0x18000730c`
- `0x180007798`
- `0x1800077a8`
- `0x180008678`
- `0x1800095cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009643`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009643`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000989f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000989f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009664`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009664`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800096fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009836`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800098d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800096fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009836`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800098d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000980d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000980d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009605`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000970b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000970b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098e8`

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
0x1800095cc  mov     [rsp-8+arg_10], rbx
0x1800095d1  push    rbp
0x1800095d2  push    rsi
0x1800095d3  push    rdi
0x1800095d4  push    r14
0x1800095d6  push    r15
0x1800095d8  lea     rbp, [rsp-160h]
0x1800095e0  sub     rsp, 260h
0x1800095e7  mov     rax, cs:__security_cookie
0x1800095ee  xor     rax, rsp
0x1800095f1  mov     [rbp+180h+var_30], rax
0x1800095f8  mov     r15, rdx
0x1800095fb  mov     qword ptr [rdx], 0
0x180009602  mov     rbx, rcx
0x180009605  call    cs:__imp_GetCurrentProcessId
0x18000960b  mov     r14d, 130h
0x180009611  mov     [rsp+280h+var_258], rbx
0x180009616  mov     r9d, eax
0x180009619  mov     [rsp+280h+var_260], r14d; int
0x18000961e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009625  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000962a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000962e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009633  mov     r9d, 1F0001h; dwDesiredAccess
0x180009639  lea     rdx, [rsp+280h+Name]; lpName
0x18000963e  xor     r8d, r8d; dwFlags
0x180009641  xor     ecx, ecx; lpMutexAttributes
0x180009643  call    cs:__imp_CreateMutexExW
0x180009649  mov     rbx, rax
0x18000964c  test    rax, rax
0x18000964f  jnz     short loc_18000965B
0x180009651  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009656  jmp     loc_1800098F4
0x18000965b  xor     r8d, r8d; bAlertable
0x18000965e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009661  mov     rcx, rbx; hHandle
0x180009664  call    cs:__imp_WaitForSingleObjectEx
0x18000966a  cmp     eax, 102h
0x18000966f  jz      short loc_180009681
0x180009671  test    eax, 0FFFFFF7Fh
0x180009676  jnz     loc_18000993E
0x18000967c  mov     rdi, rbx
0x18000967f  jmp     short loc_180009683
0x180009681  xor     edi, edi
0x180009683  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009688  mov     [rsp+280h+hObject], 0
0x180009691  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009696  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000969b  mov     esi, eax
0x18000969d  test    eax, eax
0x18000969f  jns     short loc_180009720
0x1800096a1  mov     rcx, [rbp+188h]; this
0x1800096a8  lea     r8, aWil; "wil"
0x1800096af  mov     r9d, eax; char *
0x1800096b2  mov     edx, 66h ; 'f'; void *
0x1800096b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096bc  mov     rcx, [rbp+188h]; this
0x1800096c3  lea     r8, aWil; "wil"
0x1800096ca  mov     r9d, esi; char *
0x1800096cd  mov     edx, 6Fh ; 'o'; void *
0x1800096d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096d7  mov     rcx, [rbp+188h]; this
0x1800096de  lea     r8, aWil; "wil"
0x1800096e5  mov     r9d, esi; char *
0x1800096e8  mov     edx, 12Eh; void *
0x1800096ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096f2  test    rdi, rdi
0x1800096f5  jz      short loc_180009708
0x1800096f7  mov     rcx, rdi; hMutex
0x1800096fa  call    cs:__imp_ReleaseMutex
0x180009700  test    eax, eax
0x180009702  jz      loc_18000994B
0x180009708  mov     rcx, rbx; hObject
0x18000970b  call    cs:__imp_CloseHandle
0x180009711  test    eax, eax
0x180009713  jz      loc_18000995D
0x180009719  mov     eax, esi
0x18000971b  jmp     loc_1800098F4
0x180009720  mov     rax, [rsp+280h+hObject]
0x180009725  lea     rcx, ds:0[rax*4]
0x18000972d  test    rcx, rcx
0x180009730  jz      short loc_180009740
0x180009732  mov     [r15], rcx
0x180009735  mov     eax, [rcx]
0x180009737  inc     eax
0x180009739  mov     [rcx], eax
0x18000973b  jmp     loc_1800098CA
0x180009740  mov     rdx, r14; dwBytes
0x180009743  mov     qword ptr [r15], 0
0x18000974a  mov     ecx, 8; dwFlags
0x18000974f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009754  mov     r14, rax
0x180009757  test    rax, rax
0x18000975a  jnz     short loc_180009781
0x18000975c  mov     rcx, [rbp+188h]; this
0x180009763  lea     r8, aWil; "wil"
0x18000976a  mov     esi, 8007000Eh
0x18000976f  mov     edx, 14Bh; void *
0x180009774  mov     r9d, esi; char *
0x180009777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000977c  jmp     loc_180009813
0x180009781  xorps   xmm0, xmm0
0x180009784  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000978a  test    r14b, 3
0x18000978e  jnz     loc_18000996F
0x180009794  mov     r9, r14
0x180009797  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000979c  shr     r9, 2; unsigned __int64
0x1800097a0  lea     rcx, [rsp+280h+hObject]; this
0x1800097a5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800097aa  mov     esi, eax
0x1800097ac  test    eax, eax
0x1800097ae  jns     loc_18000985A
0x1800097b4  mov     rcx, [rbp+188h]; this
0x1800097bb  lea     r8, aWil; "wil"
0x1800097c2  mov     r9d, eax; char *
0x1800097c5  mov     edx, 14Eh; void *
0x1800097ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097cf  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800097d4  test    rcx, rcx
0x1800097d7  jz      short loc_1800097E7
0x1800097d9  call    cs:__imp_CloseHandle
0x1800097df  test    eax, eax
0x1800097e1  jz      loc_180009975
0x1800097e7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800097ec  test    rcx, rcx
0x1800097ef  jz      short loc_1800097FF
0x1800097f1  call    cs:__imp_CloseHandle
0x1800097f7  test    eax, eax
0x1800097f9  jz      loc_180009987
0x1800097ff  call    cs:__imp_GetProcessHeap
0x180009805  mov     r8, r14; lpMem
0x180009808  xor     edx, edx; dwFlags
0x18000980a  mov     rcx, rax; hHeap
0x18000980d  call    cs:__imp_HeapFree
0x180009813  mov     rcx, [rbp+188h]; this
0x18000981a  lea     r8, aWil; "wil"
0x180009821  mov     r9d, esi; char *
0x180009824  mov     edx, 137h; void *
0x180009829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000982e  test    rdi, rdi
0x180009831  jz      short loc_180009844
0x180009833  mov     rcx, rdi; hMutex
0x180009836  call    cs:__imp_ReleaseMutex
0x18000983c  test    eax, eax
0x18000983e  jz      loc_180009999
0x180009844  mov     rcx, rbx; hObject
0x180009847  call    cs:__imp_CloseHandle
0x18000984d  test    eax, eax
0x18000984f  jz      loc_18000992C
0x180009855  jmp     loc_180009719
0x18000985a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000985f  lea     rcx, [r14+28h]; void *
0x180009863  mov     dword ptr [r14], 1
0x18000986a  xor     edx, edx; Val
0x18000986c  mov     [r14+8], rbx
0x180009870  mov     r8d, 108h; Size
0x180009876  movdqu  xmmword ptr [r14+10h], xmm0
0x18000987c  call    memset_0
0x180009881  xor     eax, eax
0x180009883  lea     rcx, [r14+28h]; this
0x180009887  mov     [r14+20h], rax
0x18000988b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009890  lea     rbx, [r14+0E8h]
0x180009897  xor     r8d, r8d; Flags
0x18000989a  mov     rcx, rbx; lpCriticalSection
0x18000989d  xor     edx, edx; dwSpinCount
0x18000989f  call    cs:__imp_InitializeCriticalSectionEx
0x1800098a5  mov     qword ptr [rbx+28h], 0
0x1800098ad  mov     qword ptr [rbx+30h], 0
0x1800098b5  mov     qword ptr [rbx+38h], 0
0x1800098bd  mov     qword ptr [rbx+40h], 0
0x1800098c5  xor     ebx, ebx
0x1800098c7  mov     [r15], r14
0x1800098ca  test    rdi, rdi
0x1800098cd  jz      short loc_1800098E0
0x1800098cf  mov     rcx, rdi; hMutex
0x1800098d2  call    cs:__imp_ReleaseMutex
0x1800098d8  test    eax, eax
0x1800098da  jz      loc_1800099AB
0x1800098e0  test    rbx, rbx
0x1800098e3  jz      short loc_1800098F2
0x1800098e5  mov     rcx, rbx; hObject
0x1800098e8  call    cs:__imp_CloseHandle
0x1800098ee  test    eax, eax
0x1800098f0  jz      short loc_18000991A
0x1800098f2  xor     eax, eax
0x1800098f4  mov     rcx, [rbp+180h+var_30]
0x1800098fb  xor     rcx, rsp; StackCookie
0x1800098fe  call    __security_check_cookie
0x180009903  mov     rbx, [rsp+280h+arg_10]
0x18000990b  add     rsp, 260h
0x180009912  pop     r15
0x180009914  pop     r14
0x180009916  pop     rdi
0x180009917  pop     rsi
0x180009918  pop     rbp
0x180009919  retn
0x18000991a  mov     rcx, [rbp+188h]; this
0x180009921  mov     edx, 0A0Bh; void *
0x180009926  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000992c  mov     rcx, [rbp+188h]; this
0x180009933  mov     edx, 0A0Bh; void *
0x180009938  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000993e  mov     rcx, [rbp+188h]; this
0x180009945  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000994b  mov     rcx, [rbp+188h]; this
0x180009952  mov     edx, 0A15h; void *
0x180009957  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000995d  mov     rcx, [rbp+188h]; this
0x180009964  mov     edx, 0A0Bh; void *
0x180009969  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000996f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009975  mov     rcx, [rbp+188h]; this
0x18000997c  mov     edx, 0A0Bh; void *
0x180009981  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009987  mov     rcx, [rbp+188h]; this
0x18000998e  mov     edx, 0A0Bh; void *
0x180009993  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009999  mov     rcx, [rbp+188h]; this
0x1800099a0  mov     edx, 0A15h; void *
0x1800099a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800099ab  mov     rcx, [rbp+188h]; this
0x1800099b2  mov     edx, 0A15h; void *
0x1800099b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
