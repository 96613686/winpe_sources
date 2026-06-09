# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180021234`
- end: `0x1800215fc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180022514`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x18000e30c`
- `0x18000e5f8`
- `0x180021234`
- `0x1800219fc`
- `0x180021e60`
- `0x1800223d8`
- `0x180022850`
- `0x1800240b8`
- `0x180024774`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002146a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002146a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021478`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002126d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002126d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800212ac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800212ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800212cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800212cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021363`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800214a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021511`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021363`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800214a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021374`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002145c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021374`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002145c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021527`

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
  __int64 v23; // r8
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
                    (__int64)v9,
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
0x180021234  mov     [rsp-8+arg_10], rbx
0x180021239  push    rbp
0x18002123a  push    rsi
0x18002123b  push    rdi
0x18002123c  push    r14
0x18002123e  push    r15
0x180021240  lea     rbp, [rsp-160h]
0x180021248  sub     rsp, 260h
0x18002124f  mov     rax, cs:__security_cookie
0x180021256  xor     rax, rsp
0x180021259  mov     [rbp+180h+var_30], rax
0x180021260  mov     r15, rdx
0x180021263  mov     qword ptr [rdx], 0
0x18002126a  mov     rbx, rcx
0x18002126d  call    cs:__imp_GetCurrentProcessId
0x180021273  mov     r14d, 78h ; 'x'
0x180021279  mov     [rsp+280h+var_258], rbx
0x18002127e  mov     r9d, eax
0x180021281  mov     [rsp+280h+var_260], r14d; int
0x180021286  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002128d  mov     edx, 104h; unsigned __int64
0x180021292  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180021297  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002129c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800212a2  lea     rdx, [rsp+280h+Name]; lpName
0x1800212a7  xor     r8d, r8d; dwFlags
0x1800212aa  xor     ecx, ecx; lpMutexAttributes
0x1800212ac  call    cs:__imp_CreateMutexExW
0x1800212b2  mov     rbx, rax
0x1800212b5  test    rax, rax
0x1800212b8  jnz     short loc_1800212C4
0x1800212ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800212bf  jmp     loc_180021533
0x1800212c4  xor     r8d, r8d; bAlertable
0x1800212c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800212ca  mov     rcx, rbx; hHandle
0x1800212cd  call    cs:__imp_WaitForSingleObjectEx
0x1800212d3  cmp     eax, 102h
0x1800212d8  jz      short loc_1800212EA
0x1800212da  test    eax, 0FFFFFF7Fh
0x1800212df  jnz     loc_18002156B
0x1800212e5  mov     rdi, rbx
0x1800212e8  jmp     short loc_1800212EC
0x1800212ea  xor     edi, edi
0x1800212ec  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800212f1  mov     [rsp+280h+hObject], 0
0x1800212fa  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800212ff  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180021304  mov     esi, eax
0x180021306  test    eax, eax
0x180021308  jns     short loc_180021389
0x18002130a  mov     rcx, [rbp+188h]; this
0x180021311  lea     r8, aWil; "wil"
0x180021318  mov     r9d, eax; char *
0x18002131b  mov     edx, 66h ; 'f'; void *
0x180021320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021325  mov     rcx, [rbp+188h]; this
0x18002132c  lea     r8, aWil; "wil"
0x180021333  mov     r9d, esi; char *
0x180021336  mov     edx, 6Fh ; 'o'; void *
0x18002133b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021340  mov     rcx, [rbp+188h]; this
0x180021347  lea     r8, aWil; "wil"
0x18002134e  mov     r9d, esi; char *
0x180021351  mov     edx, 12Eh; void *
0x180021356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002135b  test    rdi, rdi
0x18002135e  jz      short loc_180021371
0x180021360  mov     rcx, rdi; hMutex
0x180021363  call    cs:__imp_ReleaseMutex
0x180021369  test    eax, eax
0x18002136b  jz      loc_180021578
0x180021371  mov     rcx, rbx; hObject
0x180021374  call    cs:__imp_CloseHandle
0x18002137a  test    eax, eax
0x18002137c  jz      loc_18002158A
0x180021382  mov     eax, esi
0x180021384  jmp     loc_180021533
0x180021389  mov     rax, [rsp+280h+hObject]
0x18002138e  lea     rcx, ds:0[rax*4]
0x180021396  test    rcx, rcx
0x180021399  jz      short loc_1800213A9
0x18002139b  mov     [r15], rcx
0x18002139e  mov     eax, [rcx]
0x1800213a0  inc     eax
0x1800213a2  mov     [rcx], eax
0x1800213a4  jmp     loc_180021509
0x1800213a9  mov     rdx, r14; dwBytes
0x1800213ac  mov     qword ptr [r15], 0
0x1800213b3  mov     ecx, 8; dwFlags
0x1800213b8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800213bd  mov     rsi, rax
0x1800213c0  test    rax, rax
0x1800213c3  jnz     short loc_1800213EB
0x1800213c5  mov     rcx, [rbp+188h]; this
0x1800213cc  lea     r8, aWil; "wil"
0x1800213d3  mov     r14d, 8007000Eh
0x1800213d9  mov     edx, 14Bh; void *
0x1800213de  mov     r9d, r14d; char *
0x1800213e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213e6  jmp     loc_18002147E
0x1800213eb  xorps   xmm0, xmm0
0x1800213ee  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800213f4  test    sil, 3
0x1800213f8  jnz     loc_18002159C
0x1800213fe  mov     r9, rsi
0x180021401  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180021406  shr     r9, 2; unsigned __int64
0x18002140a  lea     rcx, [rsp+280h+hObject]; this
0x18002140f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180021414  mov     r14d, eax
0x180021417  test    eax, eax
0x180021419  jns     loc_1800214C5
0x18002141f  mov     rcx, [rbp+188h]; this
0x180021426  lea     r8, aWil; "wil"
0x18002142d  mov     r9d, eax; char *
0x180021430  mov     edx, 14Eh; void *
0x180021435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002143a  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18002143f  test    rcx, rcx
0x180021442  jz      short loc_180021452
0x180021444  call    cs:__imp_CloseHandle
0x18002144a  test    eax, eax
0x18002144c  jz      loc_1800215A2
0x180021452  mov     rcx, [rsp+280h+hObject]; hObject
0x180021457  test    rcx, rcx
0x18002145a  jz      short loc_18002146A
0x18002145c  call    cs:__imp_CloseHandle
0x180021462  test    eax, eax
0x180021464  jz      loc_1800215B4
0x18002146a  call    cs:__imp_GetProcessHeap
0x180021470  mov     r8, rsi; lpMem
0x180021473  xor     edx, edx; dwFlags
0x180021475  mov     rcx, rax; hHeap
0x180021478  call    cs:__imp_HeapFree
0x18002147e  mov     rcx, [rbp+188h]; this
0x180021485  lea     r8, aWil; "wil"
0x18002148c  mov     r9d, r14d; char *
0x18002148f  mov     edx, 137h; void *
0x180021494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021499  test    rdi, rdi
0x18002149c  jz      short loc_1800214AF
0x18002149e  mov     rcx, rdi; hMutex
0x1800214a1  call    cs:__imp_ReleaseMutex
0x1800214a7  test    eax, eax
0x1800214a9  jz      loc_1800215C6
0x1800214af  mov     rcx, rbx; hObject
0x1800214b2  call    cs:__imp_CloseHandle
0x1800214b8  test    eax, eax
0x1800214ba  jz      loc_1800215D8
0x1800214c0  mov     eax, r14d
0x1800214c3  jmp     short loc_180021533
0x1800214c5  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800214ca  xor     edx, edx; Val
0x1800214cc  mov     dword ptr [rsi], 1
0x1800214d2  lea     rcx, [rsi+22h]; void *
0x1800214d6  mov     [rsi+8], rbx
0x1800214da  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800214df  lea     r8d, [rdx+56h]; Size
0x1800214e3  call    memset_0
0x1800214e8  xor     edx, edx; Val
0x1800214ea  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800214f0  lea     rcx, [rsi+28h]; void *
0x1800214f4  mov     dword ptr [rsi+24h], 1
0x1800214fb  lea     r8d, [rdx+50h]; Size
0x1800214ff  call    memset_0
0x180021504  xor     ebx, ebx
0x180021506  mov     [r15], rsi
0x180021509  test    rdi, rdi
0x18002150c  jz      short loc_18002151F
0x18002150e  mov     rcx, rdi; hMutex
0x180021511  call    cs:__imp_ReleaseMutex
0x180021517  test    eax, eax
0x180021519  jz      loc_1800215EA
0x18002151f  test    rbx, rbx
0x180021522  jz      short loc_180021531
0x180021524  mov     rcx, rbx; hObject
0x180021527  call    cs:__imp_CloseHandle
0x18002152d  test    eax, eax
0x18002152f  jz      short loc_180021559
0x180021531  xor     eax, eax
0x180021533  mov     rcx, [rbp+180h+var_30]
0x18002153a  xor     rcx, rsp; StackCookie
0x18002153d  call    __security_check_cookie
0x180021542  mov     rbx, [rsp+280h+arg_10]
0x18002154a  add     rsp, 260h
0x180021551  pop     r15
0x180021553  pop     r14
0x180021555  pop     rdi
0x180021556  pop     rsi
0x180021557  pop     rbp
0x180021558  retn
0x180021559  mov     rcx, [rbp+188h]; this
0x180021560  mov     edx, 0A0Bh; void *
0x180021565  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002156b  mov     rcx, [rbp+188h]; this
0x180021572  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180021578  mov     rcx, [rbp+188h]; this
0x18002157f  mov     edx, 0A15h; void *
0x180021584  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002158a  mov     rcx, [rbp+188h]; this
0x180021591  mov     edx, 0A0Bh; void *
0x180021596  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002159c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800215a2  mov     rcx, [rbp+188h]; this
0x1800215a9  mov     edx, 0A0Bh; void *
0x1800215ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800215b4  mov     rcx, [rbp+188h]; this
0x1800215bb  mov     edx, 0A0Bh; void *
0x1800215c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800215c6  mov     rcx, [rbp+188h]; this
0x1800215cd  mov     edx, 0A15h; void *
0x1800215d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800215d8  mov     rcx, [rbp+188h]; this
0x1800215df  mov     edx, 0A0Bh; void *
0x1800215e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800215ea  mov     rcx, [rbp+188h]; this
0x1800215f1  mov     edx, 0A15h; void *
0x1800215f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
