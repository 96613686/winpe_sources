# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004528`
- end: `0x1800048f0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800055e0`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180004528`
- `0x18000495c`
- `0x180004d20`
- `0x180005378`
- `0x180005ec8`
- `0x1800064b4`
- `0x180006ea4`
- `0x180006f7c`
- `0x18000733c`
- `0x18000734c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800045a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800045c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800045c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004657`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004795`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004805`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004657`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004795`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000476c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000475e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000475e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000481b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000481b`

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
0x180004528  mov     [rsp-8+arg_10], rbx
0x18000452d  push    rbp
0x18000452e  push    rsi
0x18000452f  push    rdi
0x180004530  push    r14
0x180004532  push    r15
0x180004534  lea     rbp, [rsp-160h]
0x18000453c  sub     rsp, 260h
0x180004543  mov     rax, cs:__security_cookie
0x18000454a  xor     rax, rsp
0x18000454d  mov     [rbp+180h+var_30], rax
0x180004554  mov     r15, rdx
0x180004557  mov     qword ptr [rdx], 0
0x18000455e  mov     rbx, rcx
0x180004561  call    cs:__imp_GetCurrentProcessId
0x180004567  mov     r14d, 78h ; 'x'
0x18000456d  mov     [rsp+280h+var_258], rbx
0x180004572  mov     r9d, eax
0x180004575  mov     [rsp+280h+var_260], r14d; int
0x18000457a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004581  mov     edx, 104h; unsigned __int64
0x180004586  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000458b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004590  mov     r9d, 1F0001h; dwDesiredAccess
0x180004596  lea     rdx, [rsp+280h+Name]; lpName
0x18000459b  xor     r8d, r8d; dwFlags
0x18000459e  xor     ecx, ecx; lpMutexAttributes
0x1800045a0  call    cs:__imp_CreateMutexExW
0x1800045a6  mov     rbx, rax
0x1800045a9  test    rax, rax
0x1800045ac  jnz     short loc_1800045B8
0x1800045ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800045b3  jmp     loc_180004827
0x1800045b8  xor     r8d, r8d; bAlertable
0x1800045bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800045be  mov     rcx, rbx; hHandle
0x1800045c1  call    cs:__imp_WaitForSingleObjectEx
0x1800045c7  cmp     eax, 102h
0x1800045cc  jz      short loc_1800045DE
0x1800045ce  test    eax, 0FFFFFF7Fh
0x1800045d3  jnz     loc_18000485F
0x1800045d9  mov     rdi, rbx
0x1800045dc  jmp     short loc_1800045E0
0x1800045de  xor     edi, edi
0x1800045e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800045e5  mov     [rsp+280h+hObject], 0
0x1800045ee  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800045f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800045f8  mov     esi, eax
0x1800045fa  test    eax, eax
0x1800045fc  jns     short loc_18000467D
0x1800045fe  mov     rcx, [rbp+188h]; this
0x180004605  lea     r8, aWil; "wil"
0x18000460c  mov     r9d, eax; char *
0x18000460f  mov     edx, 66h ; 'f'; void *
0x180004614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004619  mov     rcx, [rbp+188h]; this
0x180004620  lea     r8, aWil; "wil"
0x180004627  mov     r9d, esi; char *
0x18000462a  mov     edx, 6Fh ; 'o'; void *
0x18000462f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004634  mov     rcx, [rbp+188h]; this
0x18000463b  lea     r8, aWil; "wil"
0x180004642  mov     r9d, esi; char *
0x180004645  mov     edx, 12Eh; void *
0x18000464a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000464f  test    rdi, rdi
0x180004652  jz      short loc_180004665
0x180004654  mov     rcx, rdi; hMutex
0x180004657  call    cs:__imp_ReleaseMutex
0x18000465d  test    eax, eax
0x18000465f  jz      loc_18000486C
0x180004665  mov     rcx, rbx; hObject
0x180004668  call    cs:__imp_CloseHandle
0x18000466e  test    eax, eax
0x180004670  jz      loc_18000487E
0x180004676  mov     eax, esi
0x180004678  jmp     loc_180004827
0x18000467d  mov     rax, [rsp+280h+hObject]
0x180004682  lea     rcx, ds:0[rax*4]
0x18000468a  test    rcx, rcx
0x18000468d  jz      short loc_18000469D
0x18000468f  mov     [r15], rcx
0x180004692  mov     eax, [rcx]
0x180004694  inc     eax
0x180004696  mov     [rcx], eax
0x180004698  jmp     loc_1800047FD
0x18000469d  mov     rdx, r14; dwBytes
0x1800046a0  mov     qword ptr [r15], 0
0x1800046a7  mov     ecx, 8; dwFlags
0x1800046ac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800046b1  mov     rsi, rax
0x1800046b4  test    rax, rax
0x1800046b7  jnz     short loc_1800046DF
0x1800046b9  mov     rcx, [rbp+188h]; this
0x1800046c0  lea     r8, aWil; "wil"
0x1800046c7  mov     r14d, 8007000Eh
0x1800046cd  mov     edx, 14Bh; void *
0x1800046d2  mov     r9d, r14d; char *
0x1800046d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046da  jmp     loc_180004772
0x1800046df  xorps   xmm0, xmm0
0x1800046e2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800046e8  test    sil, 3
0x1800046ec  jnz     loc_180004890
0x1800046f2  mov     r9, rsi
0x1800046f5  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800046fa  shr     r9, 2; unsigned __int64
0x1800046fe  lea     rcx, [rsp+280h+hObject]; this
0x180004703  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004708  mov     r14d, eax
0x18000470b  test    eax, eax
0x18000470d  jns     loc_1800047B9
0x180004713  mov     rcx, [rbp+188h]; this
0x18000471a  lea     r8, aWil; "wil"
0x180004721  mov     r9d, eax; char *
0x180004724  mov     edx, 14Eh; void *
0x180004729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000472e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004733  test    rcx, rcx
0x180004736  jz      short loc_180004746
0x180004738  call    cs:__imp_CloseHandle
0x18000473e  test    eax, eax
0x180004740  jz      loc_180004896
0x180004746  mov     rcx, [rsp+280h+hObject]; hObject
0x18000474b  test    rcx, rcx
0x18000474e  jz      short loc_18000475E
0x180004750  call    cs:__imp_CloseHandle
0x180004756  test    eax, eax
0x180004758  jz      loc_1800048A8
0x18000475e  call    cs:__imp_GetProcessHeap
0x180004764  mov     r8, rsi; lpMem
0x180004767  xor     edx, edx; dwFlags
0x180004769  mov     rcx, rax; hHeap
0x18000476c  call    cs:__imp_HeapFree
0x180004772  mov     rcx, [rbp+188h]; this
0x180004779  lea     r8, aWil; "wil"
0x180004780  mov     r9d, r14d; char *
0x180004783  mov     edx, 137h; void *
0x180004788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000478d  test    rdi, rdi
0x180004790  jz      short loc_1800047A3
0x180004792  mov     rcx, rdi; hMutex
0x180004795  call    cs:__imp_ReleaseMutex
0x18000479b  test    eax, eax
0x18000479d  jz      loc_1800048BA
0x1800047a3  mov     rcx, rbx; hObject
0x1800047a6  call    cs:__imp_CloseHandle
0x1800047ac  test    eax, eax
0x1800047ae  jz      loc_1800048CC
0x1800047b4  mov     eax, r14d
0x1800047b7  jmp     short loc_180004827
0x1800047b9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800047be  xor     edx, edx; Val
0x1800047c0  mov     dword ptr [rsi], 1
0x1800047c6  lea     rcx, [rsi+22h]; void *
0x1800047ca  mov     [rsi+8], rbx
0x1800047ce  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800047d3  lea     r8d, [rdx+56h]; Size
0x1800047d7  call    memset_0
0x1800047dc  xor     edx, edx; Val
0x1800047de  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800047e4  lea     rcx, [rsi+28h]; void *
0x1800047e8  mov     dword ptr [rsi+24h], 1
0x1800047ef  lea     r8d, [rdx+50h]; Size
0x1800047f3  call    memset_0
0x1800047f8  xor     ebx, ebx
0x1800047fa  mov     [r15], rsi
0x1800047fd  test    rdi, rdi
0x180004800  jz      short loc_180004813
0x180004802  mov     rcx, rdi; hMutex
0x180004805  call    cs:__imp_ReleaseMutex
0x18000480b  test    eax, eax
0x18000480d  jz      loc_1800048DE
0x180004813  test    rbx, rbx
0x180004816  jz      short loc_180004825
0x180004818  mov     rcx, rbx; hObject
0x18000481b  call    cs:__imp_CloseHandle
0x180004821  test    eax, eax
0x180004823  jz      short loc_18000484D
0x180004825  xor     eax, eax
0x180004827  mov     rcx, [rbp+180h+var_30]
0x18000482e  xor     rcx, rsp; StackCookie
0x180004831  call    __security_check_cookie
0x180004836  mov     rbx, [rsp+280h+arg_10]
0x18000483e  add     rsp, 260h
0x180004845  pop     r15
0x180004847  pop     r14
0x180004849  pop     rdi
0x18000484a  pop     rsi
0x18000484b  pop     rbp
0x18000484c  retn
0x18000484d  mov     rcx, [rbp+188h]; this
0x180004854  mov     edx, 0A0Bh; void *
0x180004859  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000485f  mov     rcx, [rbp+188h]; this
0x180004866  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000486c  mov     rcx, [rbp+188h]; this
0x180004873  mov     edx, 0A15h; void *
0x180004878  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000487e  mov     rcx, [rbp+188h]; this
0x180004885  mov     edx, 0A0Bh; void *
0x18000488a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004890  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004896  mov     rcx, [rbp+188h]; this
0x18000489d  mov     edx, 0A0Bh; void *
0x1800048a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048a8  mov     rcx, [rbp+188h]; this
0x1800048af  mov     edx, 0A0Bh; void *
0x1800048b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048ba  mov     rcx, [rbp+188h]; this
0x1800048c1  mov     edx, 0A15h; void *
0x1800048c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048cc  mov     rcx, [rbp+188h]; this
0x1800048d3  mov     edx, 0A0Bh; void *
0x1800048d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048de  mov     rcx, [rbp+188h]; this
0x1800048e5  mov     edx, 0A15h; void *
0x1800048ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
