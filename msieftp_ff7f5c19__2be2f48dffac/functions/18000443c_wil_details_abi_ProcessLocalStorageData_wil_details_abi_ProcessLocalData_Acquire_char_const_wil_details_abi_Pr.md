# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000443c`
- end: `0x1800047da`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000676c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000443c`
- `0x180004c48`
- `0x180005188`
- `0x180006508`
- `0x180007470`
- `0x180009170`
- `0x1800096c4`
- `0x180009af8`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800044b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800044b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004556`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000467f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004556`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000467f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000465d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000465d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000464f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000464f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004705`

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
0x18000443c  mov     [rsp-8+arg_10], rbx
0x180004441  push    rbp
0x180004442  push    rsi
0x180004443  push    rdi
0x180004444  push    r14
0x180004446  push    r15
0x180004448  lea     rbp, [rsp-160h]
0x180004450  sub     rsp, 260h
0x180004457  mov     rax, cs:__security_cookie
0x18000445e  xor     rax, rsp
0x180004461  mov     [rbp+180h+var_30], rax
0x180004468  mov     r15, rdx
0x18000446b  mov     qword ptr [rdx], 0
0x180004472  mov     rbx, rcx
0x180004475  call    cs:__imp_GetCurrentProcessId
0x18000447b  mov     r14d, 78h ; 'x'
0x180004481  mov     [rsp+280h+var_258], rbx
0x180004486  mov     r9d, eax
0x180004489  mov     [rsp+280h+var_260], r14d; int
0x18000448e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004495  mov     edx, 104h; unsigned __int64
0x18000449a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000449f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800044a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800044aa  lea     rdx, [rsp+280h+Name]; lpName
0x1800044af  xor     r8d, r8d; dwFlags
0x1800044b2  xor     ecx, ecx; lpMutexAttributes
0x1800044b4  call    cs:__imp_CreateMutexExW
0x1800044ba  mov     rbx, rax
0x1800044bd  test    rax, rax
0x1800044c0  jnz     short loc_1800044CC
0x1800044c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044c7  jmp     loc_180004711
0x1800044cc  xor     r8d, r8d; bAlertable
0x1800044cf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800044d2  mov     rcx, rbx; hHandle
0x1800044d5  call    cs:__imp_WaitForSingleObjectEx
0x1800044db  cmp     eax, 102h
0x1800044e0  jz      short loc_1800044F2
0x1800044e2  test    eax, 0FFFFFF7Fh
0x1800044e7  jnz     loc_180004749
0x1800044ed  mov     rdi, rbx
0x1800044f0  jmp     short loc_1800044F4
0x1800044f2  xor     edi, edi
0x1800044f4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800044f9  mov     [rsp+280h+hObject], 0
0x180004502  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004507  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000450c  mov     esi, eax
0x18000450e  test    eax, eax
0x180004510  jns     short loc_18000457C
0x180004512  mov     rcx, [rbp+188h]; this
0x180004519  mov     r9d, eax; char *
0x18000451c  mov     edx, 66h ; 'f'; void *
0x180004521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004526  mov     rcx, [rbp+188h]; this
0x18000452d  mov     r9d, esi; char *
0x180004530  mov     edx, 6Fh ; 'o'; void *
0x180004535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000453a  mov     rcx, [rbp+188h]; this
0x180004541  mov     r9d, esi; char *
0x180004544  mov     edx, 12Eh; void *
0x180004549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000454e  test    rdi, rdi
0x180004551  jz      short loc_180004564
0x180004553  mov     rcx, rdi; hMutex
0x180004556  call    cs:__imp_ReleaseMutex
0x18000455c  test    eax, eax
0x18000455e  jz      loc_180004756
0x180004564  mov     rcx, rbx; hObject
0x180004567  call    cs:__imp_CloseHandle
0x18000456d  test    eax, eax
0x18000456f  jz      loc_180004768
0x180004575  mov     eax, esi
0x180004577  jmp     loc_180004711
0x18000457c  mov     rax, [rsp+280h+hObject]
0x180004581  lea     rcx, ds:0[rax*4]
0x180004589  test    rcx, rcx
0x18000458c  jz      short loc_18000459C
0x18000458e  mov     [r15], rcx
0x180004591  mov     eax, [rcx]
0x180004593  inc     eax
0x180004595  mov     [rcx], eax
0x180004597  jmp     loc_1800046E7
0x18000459c  mov     rdx, r14; dwBytes
0x18000459f  mov     qword ptr [r15], 0
0x1800045a6  mov     ecx, 8; dwFlags
0x1800045ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800045b0  mov     rsi, rax
0x1800045b3  test    rax, rax
0x1800045b6  jnz     short loc_1800045D7
0x1800045b8  mov     rcx, [rbp+188h]; this
0x1800045bf  mov     r14d, 8007000Eh
0x1800045c5  mov     r9d, r14d; char *
0x1800045c8  mov     edx, 14Bh; void *
0x1800045cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045d2  jmp     loc_180004663
0x1800045d7  xorps   xmm0, xmm0
0x1800045da  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800045e0  test    sil, 3
0x1800045e4  jnz     loc_18000477A
0x1800045ea  mov     r9, rsi
0x1800045ed  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800045f2  shr     r9, 2; unsigned __int64
0x1800045f6  lea     rcx, [rsp+280h+hObject]; this
0x1800045fb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004600  mov     r14d, eax
0x180004603  test    eax, eax
0x180004605  jns     loc_1800046A3
0x18000460b  mov     rcx, [rbp+188h]; this
0x180004612  mov     r9d, eax; char *
0x180004615  mov     edx, 14Eh; void *
0x18000461a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000461f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004624  test    rcx, rcx
0x180004627  jz      short loc_180004637
0x180004629  call    cs:__imp_CloseHandle
0x18000462f  test    eax, eax
0x180004631  jz      loc_180004780
0x180004637  mov     rcx, [rsp+280h+hObject]; hObject
0x18000463c  test    rcx, rcx
0x18000463f  jz      short loc_18000464F
0x180004641  call    cs:__imp_CloseHandle
0x180004647  test    eax, eax
0x180004649  jz      loc_180004792
0x18000464f  call    cs:__imp_GetProcessHeap
0x180004655  mov     r8, rsi; lpMem
0x180004658  xor     edx, edx; dwFlags
0x18000465a  mov     rcx, rax; hHeap
0x18000465d  call    cs:__imp_HeapFree
0x180004663  mov     rcx, [rbp+188h]; this
0x18000466a  mov     r9d, r14d; char *
0x18000466d  mov     edx, 137h; void *
0x180004672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004677  test    rdi, rdi
0x18000467a  jz      short loc_18000468D
0x18000467c  mov     rcx, rdi; hMutex
0x18000467f  call    cs:__imp_ReleaseMutex
0x180004685  test    eax, eax
0x180004687  jz      loc_1800047A4
0x18000468d  mov     rcx, rbx; hObject
0x180004690  call    cs:__imp_CloseHandle
0x180004696  test    eax, eax
0x180004698  jz      loc_1800047B6
0x18000469e  mov     eax, r14d
0x1800046a1  jmp     short loc_180004711
0x1800046a3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800046a8  xor     edx, edx; Val
0x1800046aa  mov     dword ptr [rsi], 1
0x1800046b0  lea     rcx, [rsi+22h]; void *
0x1800046b4  mov     [rsi+8], rbx
0x1800046b8  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800046bd  lea     r8d, [rdx+56h]; Size
0x1800046c1  call    memset_0
0x1800046c6  xor     edx, edx; Val
0x1800046c8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800046ce  lea     rcx, [rsi+28h]; void *
0x1800046d2  mov     dword ptr [rsi+24h], 1
0x1800046d9  lea     r8d, [rdx+50h]; Size
0x1800046dd  call    memset_0
0x1800046e2  xor     ebx, ebx
0x1800046e4  mov     [r15], rsi
0x1800046e7  test    rdi, rdi
0x1800046ea  jz      short loc_1800046FD
0x1800046ec  mov     rcx, rdi; hMutex
0x1800046ef  call    cs:__imp_ReleaseMutex
0x1800046f5  test    eax, eax
0x1800046f7  jz      loc_1800047C8
0x1800046fd  test    rbx, rbx
0x180004700  jz      short loc_18000470F
0x180004702  mov     rcx, rbx; hObject
0x180004705  call    cs:__imp_CloseHandle
0x18000470b  test    eax, eax
0x18000470d  jz      short loc_180004737
0x18000470f  xor     eax, eax
0x180004711  mov     rcx, [rbp+180h+var_30]
0x180004718  xor     rcx, rsp; StackCookie
0x18000471b  call    __security_check_cookie
0x180004720  mov     rbx, [rsp+280h+arg_10]
0x180004728  add     rsp, 260h
0x18000472f  pop     r15
0x180004731  pop     r14
0x180004733  pop     rdi
0x180004734  pop     rsi
0x180004735  pop     rbp
0x180004736  retn
0x180004737  mov     rcx, [rbp+188h]; this
0x18000473e  mov     edx, 0A0Bh; void *
0x180004743  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004749  mov     rcx, [rbp+188h]; this
0x180004750  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004756  mov     rcx, [rbp+188h]; this
0x18000475d  mov     edx, 0A15h; void *
0x180004762  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004768  mov     rcx, [rbp+188h]; this
0x18000476f  mov     edx, 0A0Bh; void *
0x180004774  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000477a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004780  mov     rcx, [rbp+188h]; this
0x180004787  mov     edx, 0A0Bh; void *
0x18000478c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004792  mov     rcx, [rbp+188h]; this
0x180004799  mov     edx, 0A0Bh; void *
0x18000479e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047a4  mov     rcx, [rbp+188h]; this
0x1800047ab  mov     edx, 0A15h; void *
0x1800047b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047b6  mov     rcx, [rbp+188h]; this
0x1800047bd  mov     edx, 0A0Bh; void *
0x1800047c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047c8  mov     rcx, [rbp+188h]; this
0x1800047cf  mov     edx, 0A15h; void *
0x1800047d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
