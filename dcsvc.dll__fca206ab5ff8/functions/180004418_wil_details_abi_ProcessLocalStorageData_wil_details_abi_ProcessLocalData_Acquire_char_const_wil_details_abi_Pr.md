# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004418`
- end: `0x1800047e0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005cd0`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x180004418`
- `0x180004be0`
- `0x180005138`
- `0x180005a68`
- `0x1800068b8`
- `0x1800081c4`
- `0x1800090ac`
- `0x18000969c`
- `0x18000a12c`
- `0x18000a13c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000464e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000464e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000465c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000465c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004490`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004490`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004547`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004685`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004547`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004685`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000470b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000470b`

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
0x180004418  mov     [rsp-8+arg_10], rbx
0x18000441d  push    rbp
0x18000441e  push    rsi
0x18000441f  push    rdi
0x180004420  push    r14
0x180004422  push    r15
0x180004424  lea     rbp, [rsp-160h]
0x18000442c  sub     rsp, 260h
0x180004433  mov     rax, cs:__security_cookie
0x18000443a  xor     rax, rsp
0x18000443d  mov     [rbp+180h+var_30], rax
0x180004444  mov     r15, rdx
0x180004447  mov     qword ptr [rdx], 0
0x18000444e  mov     rbx, rcx
0x180004451  call    cs:__imp_GetCurrentProcessId
0x180004457  mov     r14d, 78h ; 'x'
0x18000445d  mov     [rsp+280h+var_258], rbx
0x180004462  mov     r9d, eax
0x180004465  mov     [rsp+280h+var_260], r14d; int
0x18000446a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004471  mov     edx, 104h; unsigned __int64
0x180004476  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000447b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004480  mov     r9d, 1F0001h; dwDesiredAccess
0x180004486  lea     rdx, [rsp+280h+Name]; lpName
0x18000448b  xor     r8d, r8d; dwFlags
0x18000448e  xor     ecx, ecx; lpMutexAttributes
0x180004490  call    cs:__imp_CreateMutexExW
0x180004496  mov     rbx, rax
0x180004499  test    rax, rax
0x18000449c  jnz     short loc_1800044A8
0x18000449e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044a3  jmp     loc_180004717
0x1800044a8  xor     r8d, r8d; bAlertable
0x1800044ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800044ae  mov     rcx, rbx; hHandle
0x1800044b1  call    cs:__imp_WaitForSingleObjectEx
0x1800044b7  cmp     eax, 102h
0x1800044bc  jz      short loc_1800044CE
0x1800044be  test    eax, 0FFFFFF7Fh
0x1800044c3  jnz     loc_18000474F
0x1800044c9  mov     rdi, rbx
0x1800044cc  jmp     short loc_1800044D0
0x1800044ce  xor     edi, edi
0x1800044d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800044d5  mov     [rsp+280h+hObject], 0
0x1800044de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800044e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800044e8  mov     esi, eax
0x1800044ea  test    eax, eax
0x1800044ec  jns     short loc_18000456D
0x1800044ee  mov     rcx, [rbp+188h]; this
0x1800044f5  lea     r8, aWil; "wil"
0x1800044fc  mov     r9d, eax; char *
0x1800044ff  mov     edx, 66h ; 'f'; void *
0x180004504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004509  mov     rcx, [rbp+188h]; this
0x180004510  lea     r8, aWil; "wil"
0x180004517  mov     r9d, esi; char *
0x18000451a  mov     edx, 6Fh ; 'o'; void *
0x18000451f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004524  mov     rcx, [rbp+188h]; this
0x18000452b  lea     r8, aWil; "wil"
0x180004532  mov     r9d, esi; char *
0x180004535  mov     edx, 12Eh; void *
0x18000453a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000453f  test    rdi, rdi
0x180004542  jz      short loc_180004555
0x180004544  mov     rcx, rdi; hMutex
0x180004547  call    cs:__imp_ReleaseMutex
0x18000454d  test    eax, eax
0x18000454f  jz      loc_18000475C
0x180004555  mov     rcx, rbx; hObject
0x180004558  call    cs:__imp_CloseHandle
0x18000455e  test    eax, eax
0x180004560  jz      loc_18000476E
0x180004566  mov     eax, esi
0x180004568  jmp     loc_180004717
0x18000456d  mov     rax, [rsp+280h+hObject]
0x180004572  lea     rcx, ds:0[rax*4]
0x18000457a  test    rcx, rcx
0x18000457d  jz      short loc_18000458D
0x18000457f  mov     [r15], rcx
0x180004582  mov     eax, [rcx]
0x180004584  inc     eax
0x180004586  mov     [rcx], eax
0x180004588  jmp     loc_1800046ED
0x18000458d  mov     rdx, r14; dwBytes
0x180004590  mov     qword ptr [r15], 0
0x180004597  mov     ecx, 8; dwFlags
0x18000459c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800045a1  mov     rsi, rax
0x1800045a4  test    rax, rax
0x1800045a7  jnz     short loc_1800045CF
0x1800045a9  mov     rcx, [rbp+188h]; this
0x1800045b0  lea     r8, aWil; "wil"
0x1800045b7  mov     r14d, 8007000Eh
0x1800045bd  mov     edx, 14Bh; void *
0x1800045c2  mov     r9d, r14d; char *
0x1800045c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045ca  jmp     loc_180004662
0x1800045cf  xorps   xmm0, xmm0
0x1800045d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800045d8  test    sil, 3
0x1800045dc  jnz     loc_180004780
0x1800045e2  mov     r9, rsi
0x1800045e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800045ea  shr     r9, 2; unsigned __int64
0x1800045ee  lea     rcx, [rsp+280h+hObject]; this
0x1800045f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800045f8  mov     r14d, eax
0x1800045fb  test    eax, eax
0x1800045fd  jns     loc_1800046A9
0x180004603  mov     rcx, [rbp+188h]; this
0x18000460a  lea     r8, aWil; "wil"
0x180004611  mov     r9d, eax; char *
0x180004614  mov     edx, 14Eh; void *
0x180004619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000461e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004623  test    rcx, rcx
0x180004626  jz      short loc_180004636
0x180004628  call    cs:__imp_CloseHandle
0x18000462e  test    eax, eax
0x180004630  jz      loc_180004786
0x180004636  mov     rcx, [rsp+280h+hObject]; hObject
0x18000463b  test    rcx, rcx
0x18000463e  jz      short loc_18000464E
0x180004640  call    cs:__imp_CloseHandle
0x180004646  test    eax, eax
0x180004648  jz      loc_180004798
0x18000464e  call    cs:__imp_GetProcessHeap
0x180004654  mov     r8, rsi; lpMem
0x180004657  xor     edx, edx; dwFlags
0x180004659  mov     rcx, rax; hHeap
0x18000465c  call    cs:__imp_HeapFree
0x180004662  mov     rcx, [rbp+188h]; this
0x180004669  lea     r8, aWil; "wil"
0x180004670  mov     r9d, r14d; char *
0x180004673  mov     edx, 137h; void *
0x180004678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000467d  test    rdi, rdi
0x180004680  jz      short loc_180004693
0x180004682  mov     rcx, rdi; hMutex
0x180004685  call    cs:__imp_ReleaseMutex
0x18000468b  test    eax, eax
0x18000468d  jz      loc_1800047AA
0x180004693  mov     rcx, rbx; hObject
0x180004696  call    cs:__imp_CloseHandle
0x18000469c  test    eax, eax
0x18000469e  jz      loc_1800047BC
0x1800046a4  mov     eax, r14d
0x1800046a7  jmp     short loc_180004717
0x1800046a9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800046ae  xor     edx, edx; Val
0x1800046b0  mov     dword ptr [rsi], 1
0x1800046b6  lea     rcx, [rsi+22h]; void *
0x1800046ba  mov     [rsi+8], rbx
0x1800046be  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800046c3  lea     r8d, [rdx+56h]; Size
0x1800046c7  call    memset_0
0x1800046cc  xor     edx, edx; Val
0x1800046ce  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800046d4  lea     rcx, [rsi+28h]; void *
0x1800046d8  mov     dword ptr [rsi+24h], 1
0x1800046df  lea     r8d, [rdx+50h]; Size
0x1800046e3  call    memset_0
0x1800046e8  xor     ebx, ebx
0x1800046ea  mov     [r15], rsi
0x1800046ed  test    rdi, rdi
0x1800046f0  jz      short loc_180004703
0x1800046f2  mov     rcx, rdi; hMutex
0x1800046f5  call    cs:__imp_ReleaseMutex
0x1800046fb  test    eax, eax
0x1800046fd  jz      loc_1800047CE
0x180004703  test    rbx, rbx
0x180004706  jz      short loc_180004715
0x180004708  mov     rcx, rbx; hObject
0x18000470b  call    cs:__imp_CloseHandle
0x180004711  test    eax, eax
0x180004713  jz      short loc_18000473D
0x180004715  xor     eax, eax
0x180004717  mov     rcx, [rbp+180h+var_30]
0x18000471e  xor     rcx, rsp; StackCookie
0x180004721  call    __security_check_cookie
0x180004726  mov     rbx, [rsp+280h+arg_10]
0x18000472e  add     rsp, 260h
0x180004735  pop     r15
0x180004737  pop     r14
0x180004739  pop     rdi
0x18000473a  pop     rsi
0x18000473b  pop     rbp
0x18000473c  retn
0x18000473d  mov     rcx, [rbp+188h]; this
0x180004744  mov     edx, 0A0Bh; void *
0x180004749  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000474f  mov     rcx, [rbp+188h]; this
0x180004756  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000475c  mov     rcx, [rbp+188h]; this
0x180004763  mov     edx, 0A15h; void *
0x180004768  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000476e  mov     rcx, [rbp+188h]; this
0x180004775  mov     edx, 0A0Bh; void *
0x18000477a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004780  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004786  mov     rcx, [rbp+188h]; this
0x18000478d  mov     edx, 0A0Bh; void *
0x180004792  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004798  mov     rcx, [rbp+188h]; this
0x18000479f  mov     edx, 0A0Bh; void *
0x1800047a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047aa  mov     rcx, [rbp+188h]; this
0x1800047b1  mov     edx, 0A15h; void *
0x1800047b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047bc  mov     rcx, [rbp+188h]; this
0x1800047c3  mov     edx, 0A0Bh; void *
0x1800047c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047ce  mov     rcx, [rbp+188h]; this
0x1800047d5  mov     edx, 0A15h; void *
0x1800047da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
