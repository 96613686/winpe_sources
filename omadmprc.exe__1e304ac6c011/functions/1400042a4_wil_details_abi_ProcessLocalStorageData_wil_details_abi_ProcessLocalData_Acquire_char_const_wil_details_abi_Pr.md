# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400042a4`
- end: `0x140004677`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140005bc4`

## callees

- `0x14000271f`
- `0x140003f50`
- `0x1400042a4`
- `0x140004a88`
- `0x140004f14`
- `0x140005940`
- `0x1400067f8`
- `0x140008504`
- `0x140008ea0`
- `0x14000942c`
- `0x140009e20`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400042dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400042dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400044c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400044c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400044d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400044d7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004322`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004322`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004349`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004349`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004506`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400045a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004506`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400045a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000451d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400045c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000451d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400045c5`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x1400042a4  mov     [rsp-8+arg_10], rbx
0x1400042a9  push    rbp
0x1400042aa  push    rsi
0x1400042ab  push    rdi
0x1400042ac  push    r14
0x1400042ae  push    r15
0x1400042b0  lea     rbp, [rsp-160h]
0x1400042b8  sub     rsp, 260h
0x1400042bf  mov     rax, cs:__security_cookie
0x1400042c6  xor     rax, rsp
0x1400042c9  mov     [rbp+180h+var_30], rax
0x1400042d0  mov     r15, rdx
0x1400042d3  mov     qword ptr [rdx], 0
0x1400042da  mov     rbx, rcx
0x1400042dd  call    cs:__imp_GetCurrentProcessId
0x1400042e4  nop     dword ptr [rax+rax+00h]
0x1400042e9  mov     r14d, 78h ; 'x'
0x1400042ef  mov     [rsp+280h+var_258], rbx
0x1400042f4  mov     r9d, eax
0x1400042f7  mov     [rsp+280h+var_260], r14d; int
0x1400042fc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004303  mov     edx, 104h; unsigned __int64
0x140004308  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000430d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004312  mov     r9d, 1F0001h; dwDesiredAccess
0x140004318  lea     rdx, [rsp+280h+Name]; lpName
0x14000431d  xor     r8d, r8d; dwFlags
0x140004320  xor     ecx, ecx; lpMutexAttributes
0x140004322  call    cs:__imp_CreateMutexExW
0x140004329  nop     dword ptr [rax+rax+00h]
0x14000432e  mov     rbx, rax
0x140004331  test    rax, rax
0x140004334  jnz     short loc_140004340
0x140004336  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000433b  jmp     loc_1400045D7
0x140004340  xor     r8d, r8d; bAlertable
0x140004343  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004346  mov     rcx, rbx; hHandle
0x140004349  call    cs:__imp_WaitForSingleObjectEx
0x140004350  nop     dword ptr [rax+rax+00h]
0x140004355  cmp     eax, 102h
0x14000435a  jz      short loc_14000436C
0x14000435c  test    eax, 0FFFFFF7Fh
0x140004361  jnz     loc_140004622
0x140004367  mov     rdi, rbx
0x14000436a  jmp     short loc_14000436E
0x14000436c  xor     edi, edi
0x14000436e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140004373  mov     [rsp+280h+var_250], 0
0x14000437c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004381  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004386  mov     esi, eax
0x140004388  test    eax, eax
0x14000438a  jns     loc_14000441B
0x140004390  mov     rcx, [rbp+188h]; this
0x140004397  lea     r8, aWil; "wil"
0x14000439e  mov     r9d, eax; char *
0x1400043a1  mov     edx, 66h ; 'f'; void *
0x1400043a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043ab  mov     rcx, [rbp+188h]; this
0x1400043b2  lea     r8, aWil; "wil"
0x1400043b9  mov     r9d, esi; char *
0x1400043bc  mov     edx, 6Fh ; 'o'; void *
0x1400043c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043c6  mov     rcx, [rbp+188h]; this
0x1400043cd  lea     r8, aWil; "wil"
0x1400043d4  mov     r9d, esi; char *
0x1400043d7  mov     edx, 12Eh; void *
0x1400043dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043e1  test    rdi, rdi
0x1400043e4  jz      short loc_1400043FD
0x1400043e6  mov     rcx, rdi; hMutex
0x1400043e9  call    cs:__imp_ReleaseMutex
0x1400043f0  nop     dword ptr [rax+rax+00h]
0x1400043f5  test    eax, eax
0x1400043f7  jz      loc_14000462F
0x1400043fd  mov     rcx, rbx; hObject
0x140004400  call    cs:__imp_CloseHandle
0x140004407  nop     dword ptr [rax+rax+00h]
0x14000440c  test    eax, eax
0x14000440e  jz      loc_140004641
0x140004414  mov     eax, esi
0x140004416  jmp     loc_1400045D7
0x14000441b  mov     rax, [rsp+280h+var_250]
0x140004420  lea     rcx, ds:0[rax*4]
0x140004428  test    rcx, rcx
0x14000442b  jz      short loc_14000443B
0x14000442d  mov     [r15], rcx
0x140004430  mov     eax, [rcx]
0x140004432  inc     eax
0x140004434  mov     [rcx], eax
0x140004436  jmp     loc_1400045A1
0x14000443b  mov     rdx, r14; dwBytes
0x14000443e  mov     qword ptr [r15], 0
0x140004445  mov     ecx, 8; dwFlags
0x14000444a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000444f  mov     r14, rax
0x140004452  test    rax, rax
0x140004455  jnz     short loc_140004479
0x140004457  mov     rcx, [rbp+188h]; this
0x14000445e  lea     r8, aWil; "wil"
0x140004465  mov     esi, 8007000Eh
0x14000446a  mov     edx, 14Bh; void *
0x14000446f  mov     r9d, esi; char *
0x140004472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004477  jmp     short loc_1400044E3
0x140004479  xorps   xmm0, xmm0
0x14000447c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004481  mov     r8, r14; void *
0x140004484  lea     rcx, [rsp+280h+var_250]; this
0x140004489  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14000448f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140004494  mov     esi, eax
0x140004496  test    eax, eax
0x140004498  jns     loc_140004536
0x14000449e  mov     rcx, [rbp+188h]; this
0x1400044a5  lea     r8, aWil; "wil"
0x1400044ac  mov     r9d, eax; char *
0x1400044af  mov     edx, 14Eh; void *
0x1400044b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400044b9  lea     rcx, [rsp+280h+var_250]; this
0x1400044be  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400044c3  call    cs:__imp_GetProcessHeap
0x1400044ca  nop     dword ptr [rax+rax+00h]
0x1400044cf  mov     r8, r14; lpMem
0x1400044d2  xor     edx, edx; dwFlags
0x1400044d4  mov     rcx, rax; hHeap
0x1400044d7  call    cs:__imp_HeapFree
0x1400044de  nop     dword ptr [rax+rax+00h]
0x1400044e3  mov     rcx, [rbp+188h]; this
0x1400044ea  lea     r8, aWil; "wil"
0x1400044f1  mov     r9d, esi; char *
0x1400044f4  mov     edx, 137h; void *
0x1400044f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400044fe  test    rdi, rdi
0x140004501  jz      short loc_14000451A
0x140004503  mov     rcx, rdi; hMutex
0x140004506  call    cs:__imp_ReleaseMutex
0x14000450d  nop     dword ptr [rax+rax+00h]
0x140004512  test    eax, eax
0x140004514  jz      loc_140004653
0x14000451a  mov     rcx, rbx; hObject
0x14000451d  call    cs:__imp_CloseHandle
0x140004524  nop     dword ptr [rax+rax+00h]
0x140004529  test    eax, eax
0x14000452b  jz      loc_140004610
0x140004531  jmp     loc_140004414
0x140004536  mov     rax, [rsp+280h+var_250]
0x14000453b  lea     rcx, [r14+22h]; void *
0x14000453f  xor     edx, edx; Val
0x140004541  mov     [r14+10h], rax
0x140004545  mov     rax, [rsp+280h+var_250+8]
0x14000454a  mov     dword ptr [r14], 1
0x140004551  mov     [r14+8], rbx
0x140004555  lea     r8d, [rdx+56h]; Size
0x140004559  mov     [rsp+280h+var_250], 0
0x140004562  mov     [r14+18h], rax
0x140004566  mov     [rsp+280h+var_250+8], 0
0x14000456f  call    memset_0
0x140004574  xor     edx, edx; Val
0x140004576  mov     word ptr [r14+20h], 58h ; 'X'
0x14000457d  lea     rcx, [r14+28h]; void *
0x140004581  mov     dword ptr [r14+24h], 1
0x140004589  lea     r8d, [rdx+50h]; Size
0x14000458d  call    memset_0
0x140004592  lea     rcx, [rsp+280h+var_250]; this
0x140004597  mov     [r15], r14
0x14000459a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000459f  xor     ebx, ebx
0x1400045a1  test    rdi, rdi
0x1400045a4  jz      short loc_1400045BD
0x1400045a6  mov     rcx, rdi; hMutex
0x1400045a9  call    cs:__imp_ReleaseMutex
0x1400045b0  nop     dword ptr [rax+rax+00h]
0x1400045b5  test    eax, eax
0x1400045b7  jz      loc_140004665
0x1400045bd  test    rbx, rbx
0x1400045c0  jz      short loc_1400045D5
0x1400045c2  mov     rcx, rbx; hObject
0x1400045c5  call    cs:__imp_CloseHandle
0x1400045cc  nop     dword ptr [rax+rax+00h]
0x1400045d1  test    eax, eax
0x1400045d3  jz      short loc_1400045FE
0x1400045d5  xor     eax, eax
0x1400045d7  mov     rcx, [rbp+180h+var_30]
0x1400045de  xor     rcx, rsp; StackCookie
0x1400045e1  call    __security_check_cookie
0x1400045e6  mov     rbx, [rsp+280h+arg_10]
0x1400045ee  add     rsp, 260h
0x1400045f5  pop     r15
0x1400045f7  pop     r14
0x1400045f9  pop     rdi
0x1400045fa  pop     rsi
0x1400045fb  pop     rbp
0x1400045fc  retn
0x1400045fe  mov     rcx, [rbp+188h]; this
0x140004605  mov     edx, 0A0Bh; void *
0x14000460a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004610  mov     rcx, [rbp+188h]; this
0x140004617  mov     edx, 0A0Bh; void *
0x14000461c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004622  mov     rcx, [rbp+188h]; this
0x140004629  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000462f  mov     rcx, [rbp+188h]; this
0x140004636  mov     edx, 0A15h; void *
0x14000463b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004641  mov     rcx, [rbp+188h]; this
0x140004648  mov     edx, 0A0Bh; void *
0x14000464d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004653  mov     rcx, [rbp+188h]; this
0x14000465a  mov     edx, 0A15h; void *
0x14000465f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004665  mov     rcx, [rbp+188h]; this
0x14000466c  mov     edx, 0A15h; void *
0x140004671  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
