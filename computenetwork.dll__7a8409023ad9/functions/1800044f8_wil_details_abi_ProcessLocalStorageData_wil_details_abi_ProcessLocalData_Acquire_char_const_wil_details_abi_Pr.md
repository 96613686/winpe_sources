# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800044f8`
- end: `0x1800048c0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800053d0`

## callees

- `0x180001600`
- `0x180002062`
- `0x1800044f8`
- `0x1800048c8`
- `0x180004b10`
- `0x180005168`
- `0x180006588`
- `0x180006a54`
- `0x1800073e0`
- `0x1800074e4`
- `0x1800078ac`
- `0x1800078bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004570`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004570`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004591`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004591`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004627`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004765`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800047d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004627`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004765`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800047d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000473c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000473c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000472e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000472e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004531`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004531`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004708`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004708`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047eb`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x1800044f8  mov     [rsp-8+arg_10], rbx
0x1800044fd  push    rbp
0x1800044fe  push    rsi
0x1800044ff  push    rdi
0x180004500  push    r14
0x180004502  push    r15
0x180004504  lea     rbp, [rsp-160h]
0x18000450c  sub     rsp, 260h
0x180004513  mov     rax, cs:__security_cookie
0x18000451a  xor     rax, rsp
0x18000451d  mov     [rbp+180h+var_30], rax
0x180004524  mov     r15, rdx
0x180004527  mov     qword ptr [rdx], 0
0x18000452e  mov     rbx, rcx
0x180004531  call    cs:__imp_GetCurrentProcessId
0x180004537  mov     r14d, 78h ; 'x'
0x18000453d  mov     [rsp+280h+var_258], rbx
0x180004542  mov     r9d, eax
0x180004545  mov     [rsp+280h+var_260], r14d; int
0x18000454a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004551  mov     edx, 104h; unsigned __int64
0x180004556  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000455b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004560  mov     r9d, 1F0001h; dwDesiredAccess
0x180004566  lea     rdx, [rsp+280h+Name]; lpName
0x18000456b  xor     r8d, r8d; dwFlags
0x18000456e  xor     ecx, ecx; lpMutexAttributes
0x180004570  call    cs:__imp_CreateMutexExW
0x180004576  mov     rbx, rax
0x180004579  test    rax, rax
0x18000457c  jnz     short loc_180004588
0x18000457e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004583  jmp     loc_1800047F7
0x180004588  xor     r8d, r8d; bAlertable
0x18000458b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000458e  mov     rcx, rbx; hHandle
0x180004591  call    cs:__imp_WaitForSingleObjectEx
0x180004597  cmp     eax, 102h
0x18000459c  jz      short loc_1800045AE
0x18000459e  test    eax, 0FFFFFF7Fh
0x1800045a3  jnz     loc_18000482F
0x1800045a9  mov     rdi, rbx
0x1800045ac  jmp     short loc_1800045B0
0x1800045ae  xor     edi, edi
0x1800045b0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800045b5  mov     [rsp+280h+hObject], 0
0x1800045be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800045c3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800045c8  mov     esi, eax
0x1800045ca  test    eax, eax
0x1800045cc  jns     short loc_18000464D
0x1800045ce  mov     rcx, [rbp+188h]; this
0x1800045d5  lea     r8, aWil; "wil"
0x1800045dc  mov     r9d, eax; char *
0x1800045df  mov     edx, 66h ; 'f'; void *
0x1800045e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045e9  mov     rcx, [rbp+188h]; this
0x1800045f0  lea     r8, aWil; "wil"
0x1800045f7  mov     r9d, esi; char *
0x1800045fa  mov     edx, 6Fh ; 'o'; void *
0x1800045ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004604  mov     rcx, [rbp+188h]; this
0x18000460b  lea     r8, aWil; "wil"
0x180004612  mov     r9d, esi; char *
0x180004615  mov     edx, 12Eh; void *
0x18000461a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000461f  test    rdi, rdi
0x180004622  jz      short loc_180004635
0x180004624  mov     rcx, rdi; hMutex
0x180004627  call    cs:__imp_ReleaseMutex
0x18000462d  test    eax, eax
0x18000462f  jz      loc_18000483C
0x180004635  mov     rcx, rbx; hObject
0x180004638  call    cs:__imp_CloseHandle
0x18000463e  test    eax, eax
0x180004640  jz      loc_18000484E
0x180004646  mov     eax, esi
0x180004648  jmp     loc_1800047F7
0x18000464d  mov     rax, [rsp+280h+hObject]
0x180004652  lea     rcx, ds:0[rax*4]
0x18000465a  test    rcx, rcx
0x18000465d  jz      short loc_18000466D
0x18000465f  mov     [r15], rcx
0x180004662  mov     eax, [rcx]
0x180004664  inc     eax
0x180004666  mov     [rcx], eax
0x180004668  jmp     loc_1800047CD
0x18000466d  mov     rdx, r14; dwBytes
0x180004670  mov     qword ptr [r15], 0
0x180004677  mov     ecx, 8; dwFlags
0x18000467c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004681  mov     rsi, rax
0x180004684  test    rax, rax
0x180004687  jnz     short loc_1800046AF
0x180004689  mov     rcx, [rbp+188h]; this
0x180004690  lea     r8, aWil; "wil"
0x180004697  mov     r14d, 8007000Eh
0x18000469d  mov     edx, 14Bh; void *
0x1800046a2  mov     r9d, r14d; char *
0x1800046a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046aa  jmp     loc_180004742
0x1800046af  xorps   xmm0, xmm0
0x1800046b2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800046b8  test    sil, 3
0x1800046bc  jnz     loc_180004860
0x1800046c2  mov     r9, rsi
0x1800046c5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800046ca  shr     r9, 2; unsigned __int64
0x1800046ce  lea     rcx, [rsp+280h+hObject]; this
0x1800046d3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800046d8  mov     r14d, eax
0x1800046db  test    eax, eax
0x1800046dd  jns     loc_180004789
0x1800046e3  mov     rcx, [rbp+188h]; this
0x1800046ea  lea     r8, aWil; "wil"
0x1800046f1  mov     r9d, eax; char *
0x1800046f4  mov     edx, 14Eh; void *
0x1800046f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046fe  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004703  test    rcx, rcx
0x180004706  jz      short loc_180004716
0x180004708  call    cs:__imp_CloseHandle
0x18000470e  test    eax, eax
0x180004710  jz      loc_180004866
0x180004716  mov     rcx, [rsp+280h+hObject]; hObject
0x18000471b  test    rcx, rcx
0x18000471e  jz      short loc_18000472E
0x180004720  call    cs:__imp_CloseHandle
0x180004726  test    eax, eax
0x180004728  jz      loc_180004878
0x18000472e  call    cs:__imp_GetProcessHeap
0x180004734  mov     r8, rsi; lpMem
0x180004737  xor     edx, edx; dwFlags
0x180004739  mov     rcx, rax; hHeap
0x18000473c  call    cs:__imp_HeapFree
0x180004742  mov     rcx, [rbp+188h]; this
0x180004749  lea     r8, aWil; "wil"
0x180004750  mov     r9d, r14d; char *
0x180004753  mov     edx, 137h; void *
0x180004758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000475d  test    rdi, rdi
0x180004760  jz      short loc_180004773
0x180004762  mov     rcx, rdi; hMutex
0x180004765  call    cs:__imp_ReleaseMutex
0x18000476b  test    eax, eax
0x18000476d  jz      loc_18000488A
0x180004773  mov     rcx, rbx; hObject
0x180004776  call    cs:__imp_CloseHandle
0x18000477c  test    eax, eax
0x18000477e  jz      loc_18000489C
0x180004784  mov     eax, r14d
0x180004787  jmp     short loc_1800047F7
0x180004789  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000478e  xor     edx, edx; Val
0x180004790  mov     dword ptr [rsi], 1
0x180004796  lea     rcx, [rsi+22h]; void *
0x18000479a  mov     [rsi+8], rbx
0x18000479e  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800047a3  lea     r8d, [rdx+56h]; Size
0x1800047a7  call    memset_0
0x1800047ac  xor     edx, edx; Val
0x1800047ae  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800047b4  lea     rcx, [rsi+28h]; void *
0x1800047b8  mov     dword ptr [rsi+24h], 1
0x1800047bf  lea     r8d, [rdx+50h]; Size
0x1800047c3  call    memset_0
0x1800047c8  xor     ebx, ebx
0x1800047ca  mov     [r15], rsi
0x1800047cd  test    rdi, rdi
0x1800047d0  jz      short loc_1800047E3
0x1800047d2  mov     rcx, rdi; hMutex
0x1800047d5  call    cs:__imp_ReleaseMutex
0x1800047db  test    eax, eax
0x1800047dd  jz      loc_1800048AE
0x1800047e3  test    rbx, rbx
0x1800047e6  jz      short loc_1800047F5
0x1800047e8  mov     rcx, rbx; hObject
0x1800047eb  call    cs:__imp_CloseHandle
0x1800047f1  test    eax, eax
0x1800047f3  jz      short loc_18000481D
0x1800047f5  xor     eax, eax
0x1800047f7  mov     rcx, [rbp+180h+var_30]
0x1800047fe  xor     rcx, rsp; StackCookie
0x180004801  call    __security_check_cookie
0x180004806  mov     rbx, [rsp+280h+arg_10]
0x18000480e  add     rsp, 260h
0x180004815  pop     r15
0x180004817  pop     r14
0x180004819  pop     rdi
0x18000481a  pop     rsi
0x18000481b  pop     rbp
0x18000481c  retn
0x18000481d  mov     rcx, [rbp+188h]; this
0x180004824  mov     edx, 0A0Bh; void *
0x180004829  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000482f  mov     rcx, [rbp+188h]; this
0x180004836  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000483c  mov     rcx, [rbp+188h]; this
0x180004843  mov     edx, 0A15h; void *
0x180004848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000484e  mov     rcx, [rbp+188h]; this
0x180004855  mov     edx, 0A0Bh; void *
0x18000485a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004860  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004866  mov     rcx, [rbp+188h]; this
0x18000486d  mov     edx, 0A0Bh; void *
0x180004872  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004878  mov     rcx, [rbp+188h]; this
0x18000487f  mov     edx, 0A0Bh; void *
0x180004884  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000488a  mov     rcx, [rbp+188h]; this
0x180004891  mov     edx, 0A15h; void *
0x180004896  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000489c  mov     rcx, [rbp+188h]; this
0x1800048a3  mov     edx, 0A0Bh; void *
0x1800048a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048ae  mov     rcx, [rbp+188h]; this
0x1800048b5  mov     edx, 0A15h; void *
0x1800048ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
