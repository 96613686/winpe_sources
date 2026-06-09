# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004428`
- end: `0x1800047c6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005d40`

## callees

- `0x180001f60`
- `0x1800028dc`
- `0x180004428`
- `0x180004b9c`
- `0x1800050b8`
- `0x180005ad8`
- `0x180006840`
- `0x180008274`
- `0x180008d34`
- `0x18000919c`
- `0x180009a4c`
- `0x180009a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800044a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800044a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004542`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000466b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004542`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000466b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004649`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004461`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000462d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000467c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000462d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000467c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046f1`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x180004428  mov     [rsp-8+arg_10], rbx
0x18000442d  push    rbp
0x18000442e  push    rsi
0x18000442f  push    rdi
0x180004430  push    r14
0x180004432  push    r15
0x180004434  lea     rbp, [rsp-160h]
0x18000443c  sub     rsp, 260h
0x180004443  mov     rax, cs:__security_cookie
0x18000444a  xor     rax, rsp
0x18000444d  mov     [rbp+180h+var_30], rax
0x180004454  mov     r15, rdx
0x180004457  mov     qword ptr [rdx], 0
0x18000445e  mov     rbx, rcx
0x180004461  call    cs:__imp_GetCurrentProcessId
0x180004467  mov     r14d, 78h ; 'x'
0x18000446d  mov     [rsp+280h+var_258], rbx
0x180004472  mov     r9d, eax
0x180004475  mov     [rsp+280h+var_260], r14d; int
0x18000447a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004481  mov     edx, 104h; unsigned __int64
0x180004486  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000448b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004490  mov     r9d, 1F0001h; dwDesiredAccess
0x180004496  lea     rdx, [rsp+280h+Name]; lpName
0x18000449b  xor     r8d, r8d; dwFlags
0x18000449e  xor     ecx, ecx; lpMutexAttributes
0x1800044a0  call    cs:__imp_CreateMutexExW
0x1800044a6  mov     rbx, rax
0x1800044a9  test    rax, rax
0x1800044ac  jnz     short loc_1800044B8
0x1800044ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044b3  jmp     loc_1800046FD
0x1800044b8  xor     r8d, r8d; bAlertable
0x1800044bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800044be  mov     rcx, rbx; hHandle
0x1800044c1  call    cs:__imp_WaitForSingleObjectEx
0x1800044c7  cmp     eax, 102h
0x1800044cc  jz      short loc_1800044DE
0x1800044ce  test    eax, 0FFFFFF7Fh
0x1800044d3  jnz     loc_180004735
0x1800044d9  mov     rdi, rbx
0x1800044dc  jmp     short loc_1800044E0
0x1800044de  xor     edi, edi
0x1800044e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800044e5  mov     [rsp+280h+hObject], 0
0x1800044ee  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800044f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800044f8  mov     esi, eax
0x1800044fa  test    eax, eax
0x1800044fc  jns     short loc_180004568
0x1800044fe  mov     rcx, [rbp+188h]; this
0x180004505  mov     r9d, eax; char *
0x180004508  mov     edx, 66h ; 'f'; void *
0x18000450d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004512  mov     rcx, [rbp+188h]; this
0x180004519  mov     r9d, esi; char *
0x18000451c  mov     edx, 6Fh ; 'o'; void *
0x180004521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004526  mov     rcx, [rbp+188h]; this
0x18000452d  mov     r9d, esi; char *
0x180004530  mov     edx, 12Eh; void *
0x180004535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000453a  test    rdi, rdi
0x18000453d  jz      short loc_180004550
0x18000453f  mov     rcx, rdi; hMutex
0x180004542  call    cs:__imp_ReleaseMutex
0x180004548  test    eax, eax
0x18000454a  jz      loc_180004742
0x180004550  mov     rcx, rbx; hObject
0x180004553  call    cs:__imp_CloseHandle
0x180004559  test    eax, eax
0x18000455b  jz      loc_180004754
0x180004561  mov     eax, esi
0x180004563  jmp     loc_1800046FD
0x180004568  mov     rax, [rsp+280h+hObject]
0x18000456d  lea     rcx, ds:0[rax*4]
0x180004575  test    rcx, rcx
0x180004578  jz      short loc_180004588
0x18000457a  mov     [r15], rcx
0x18000457d  mov     eax, [rcx]
0x18000457f  inc     eax
0x180004581  mov     [rcx], eax
0x180004583  jmp     loc_1800046D3
0x180004588  mov     rdx, r14; dwBytes
0x18000458b  mov     qword ptr [r15], 0
0x180004592  mov     ecx, 8; dwFlags
0x180004597  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000459c  mov     rsi, rax
0x18000459f  test    rax, rax
0x1800045a2  jnz     short loc_1800045C3
0x1800045a4  mov     rcx, [rbp+188h]; this
0x1800045ab  mov     r14d, 8007000Eh
0x1800045b1  mov     r9d, r14d; char *
0x1800045b4  mov     edx, 14Bh; void *
0x1800045b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045be  jmp     loc_18000464F
0x1800045c3  xorps   xmm0, xmm0
0x1800045c6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800045cc  test    sil, 3
0x1800045d0  jnz     loc_180004766
0x1800045d6  mov     r9, rsi
0x1800045d9  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800045de  shr     r9, 2; unsigned __int64
0x1800045e2  lea     rcx, [rsp+280h+hObject]; this
0x1800045e7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800045ec  mov     r14d, eax
0x1800045ef  test    eax, eax
0x1800045f1  jns     loc_18000468F
0x1800045f7  mov     rcx, [rbp+188h]; this
0x1800045fe  mov     r9d, eax; char *
0x180004601  mov     edx, 14Eh; void *
0x180004606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000460b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004610  test    rcx, rcx
0x180004613  jz      short loc_180004623
0x180004615  call    cs:__imp_CloseHandle
0x18000461b  test    eax, eax
0x18000461d  jz      loc_18000476C
0x180004623  mov     rcx, [rsp+280h+hObject]; hObject
0x180004628  test    rcx, rcx
0x18000462b  jz      short loc_18000463B
0x18000462d  call    cs:__imp_CloseHandle
0x180004633  test    eax, eax
0x180004635  jz      loc_18000477E
0x18000463b  call    cs:__imp_GetProcessHeap
0x180004641  mov     r8, rsi; lpMem
0x180004644  xor     edx, edx; dwFlags
0x180004646  mov     rcx, rax; hHeap
0x180004649  call    cs:__imp_HeapFree
0x18000464f  mov     rcx, [rbp+188h]; this
0x180004656  mov     r9d, r14d; char *
0x180004659  mov     edx, 137h; void *
0x18000465e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004663  test    rdi, rdi
0x180004666  jz      short loc_180004679
0x180004668  mov     rcx, rdi; hMutex
0x18000466b  call    cs:__imp_ReleaseMutex
0x180004671  test    eax, eax
0x180004673  jz      loc_180004790
0x180004679  mov     rcx, rbx; hObject
0x18000467c  call    cs:__imp_CloseHandle
0x180004682  test    eax, eax
0x180004684  jz      loc_1800047A2
0x18000468a  mov     eax, r14d
0x18000468d  jmp     short loc_1800046FD
0x18000468f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004694  xor     edx, edx; Val
0x180004696  mov     dword ptr [rsi], 1
0x18000469c  lea     rcx, [rsi+22h]; void *
0x1800046a0  mov     [rsi+8], rbx
0x1800046a4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800046a9  lea     r8d, [rdx+56h]; Size
0x1800046ad  call    memset_0
0x1800046b2  xor     edx, edx; Val
0x1800046b4  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800046ba  lea     rcx, [rsi+28h]; void *
0x1800046be  mov     dword ptr [rsi+24h], 1
0x1800046c5  lea     r8d, [rdx+50h]; Size
0x1800046c9  call    memset_0
0x1800046ce  xor     ebx, ebx
0x1800046d0  mov     [r15], rsi
0x1800046d3  test    rdi, rdi
0x1800046d6  jz      short loc_1800046E9
0x1800046d8  mov     rcx, rdi; hMutex
0x1800046db  call    cs:__imp_ReleaseMutex
0x1800046e1  test    eax, eax
0x1800046e3  jz      loc_1800047B4
0x1800046e9  test    rbx, rbx
0x1800046ec  jz      short loc_1800046FB
0x1800046ee  mov     rcx, rbx; hObject
0x1800046f1  call    cs:__imp_CloseHandle
0x1800046f7  test    eax, eax
0x1800046f9  jz      short loc_180004723
0x1800046fb  xor     eax, eax
0x1800046fd  mov     rcx, [rbp+180h+var_30]
0x180004704  xor     rcx, rsp; StackCookie
0x180004707  call    __security_check_cookie
0x18000470c  mov     rbx, [rsp+280h+arg_10]
0x180004714  add     rsp, 260h
0x18000471b  pop     r15
0x18000471d  pop     r14
0x18000471f  pop     rdi
0x180004720  pop     rsi
0x180004721  pop     rbp
0x180004722  retn
0x180004723  mov     rcx, [rbp+188h]; this
0x18000472a  mov     edx, 0A0Bh; void *
0x18000472f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004735  mov     rcx, [rbp+188h]; this
0x18000473c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004742  mov     rcx, [rbp+188h]; this
0x180004749  mov     edx, 0A15h; void *
0x18000474e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004754  mov     rcx, [rbp+188h]; this
0x18000475b  mov     edx, 0A0Bh; void *
0x180004760  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004766  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000476c  mov     rcx, [rbp+188h]; this
0x180004773  mov     edx, 0A0Bh; void *
0x180004778  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000477e  mov     rcx, [rbp+188h]; this
0x180004785  mov     edx, 0A0Bh; void *
0x18000478a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004790  mov     rcx, [rbp+188h]; this
0x180004797  mov     edx, 0A15h; void *
0x18000479c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047a2  mov     rcx, [rbp+188h]; this
0x1800047a9  mov     edx, 0A0Bh; void *
0x1800047ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047b4  mov     rcx, [rbp+188h]; this
0x1800047bb  mov     edx, 0A15h; void *
0x1800047c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
