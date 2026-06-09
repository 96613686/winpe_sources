# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a8a4`
- end: `0x18000ac77`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000d194`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180006140`
- `0x18000a548`
- `0x18000a8a4`
- `0x18000b528`
- `0x18000bf64`
- `0x18000ce9c`
- `0x1800100a8`
- `0x180011b98`
- `0x180013468`
- `0x180013cf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aad7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a8dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a922`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a922`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a949`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a949`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aba9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abc5`

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
0x18000a8a4  mov     [rsp-8+arg_10], rbx
0x18000a8a9  push    rbp
0x18000a8aa  push    rsi
0x18000a8ab  push    rdi
0x18000a8ac  push    r14
0x18000a8ae  push    r15
0x18000a8b0  lea     rbp, [rsp-160h]
0x18000a8b8  sub     rsp, 260h
0x18000a8bf  mov     rax, cs:__security_cookie
0x18000a8c6  xor     rax, rsp
0x18000a8c9  mov     [rbp+180h+var_30], rax
0x18000a8d0  mov     r15, rdx
0x18000a8d3  mov     qword ptr [rdx], 0
0x18000a8da  mov     rbx, rcx
0x18000a8dd  call    cs:__imp_GetCurrentProcessId
0x18000a8e4  nop     dword ptr [rax+rax+00h]
0x18000a8e9  mov     r14d, 78h ; 'x'
0x18000a8ef  mov     [rsp+280h+var_258], rbx
0x18000a8f4  mov     r9d, eax
0x18000a8f7  mov     [rsp+280h+var_260], r14d; int
0x18000a8fc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a903  mov     edx, 104h; unsigned __int64
0x18000a908  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a90d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a912  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a918  lea     rdx, [rsp+280h+Name]; lpName
0x18000a91d  xor     r8d, r8d; dwFlags
0x18000a920  xor     ecx, ecx; lpMutexAttributes
0x18000a922  call    cs:__imp_CreateMutexExW
0x18000a929  nop     dword ptr [rax+rax+00h]
0x18000a92e  mov     rbx, rax
0x18000a931  test    rax, rax
0x18000a934  jnz     short loc_18000A940
0x18000a936  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a93b  jmp     loc_18000ABD7
0x18000a940  xor     r8d, r8d; bAlertable
0x18000a943  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a946  mov     rcx, rbx; hHandle
0x18000a949  call    cs:__imp_WaitForSingleObjectEx
0x18000a950  nop     dword ptr [rax+rax+00h]
0x18000a955  cmp     eax, 102h
0x18000a95a  jz      short loc_18000A96C
0x18000a95c  test    eax, 0FFFFFF7Fh
0x18000a961  jnz     loc_18000AC22
0x18000a967  mov     rdi, rbx
0x18000a96a  jmp     short loc_18000A96E
0x18000a96c  xor     edi, edi
0x18000a96e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000a973  mov     [rsp+280h+var_250], 0
0x18000a97c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a981  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a986  mov     esi, eax
0x18000a988  test    eax, eax
0x18000a98a  jns     loc_18000AA1B
0x18000a990  mov     rcx, [rbp+188h]; this
0x18000a997  lea     r8, aWil; "wil"
0x18000a99e  mov     r9d, eax; char *
0x18000a9a1  mov     edx, 66h ; 'f'; void *
0x18000a9a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9ab  mov     rcx, [rbp+188h]; this
0x18000a9b2  lea     r8, aWil; "wil"
0x18000a9b9  mov     r9d, esi; char *
0x18000a9bc  mov     edx, 6Fh ; 'o'; void *
0x18000a9c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9c6  mov     rcx, [rbp+188h]; this
0x18000a9cd  lea     r8, aWil; "wil"
0x18000a9d4  mov     r9d, esi; char *
0x18000a9d7  mov     edx, 12Eh; void *
0x18000a9dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9e1  test    rdi, rdi
0x18000a9e4  jz      short loc_18000A9FD
0x18000a9e6  mov     rcx, rdi; hMutex
0x18000a9e9  call    cs:__imp_ReleaseMutex
0x18000a9f0  nop     dword ptr [rax+rax+00h]
0x18000a9f5  test    eax, eax
0x18000a9f7  jz      loc_18000AC2F
0x18000a9fd  mov     rcx, rbx; hObject
0x18000aa00  call    cs:__imp_CloseHandle
0x18000aa07  nop     dword ptr [rax+rax+00h]
0x18000aa0c  test    eax, eax
0x18000aa0e  jz      loc_18000AC41
0x18000aa14  mov     eax, esi
0x18000aa16  jmp     loc_18000ABD7
0x18000aa1b  mov     rax, [rsp+280h+var_250]
0x18000aa20  lea     rcx, ds:0[rax*4]
0x18000aa28  test    rcx, rcx
0x18000aa2b  jz      short loc_18000AA3B
0x18000aa2d  mov     [r15], rcx
0x18000aa30  mov     eax, [rcx]
0x18000aa32  inc     eax
0x18000aa34  mov     [rcx], eax
0x18000aa36  jmp     loc_18000ABA1
0x18000aa3b  mov     rdx, r14; dwBytes
0x18000aa3e  mov     qword ptr [r15], 0
0x18000aa45  mov     ecx, 8; dwFlags
0x18000aa4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aa4f  mov     r14, rax
0x18000aa52  test    rax, rax
0x18000aa55  jnz     short loc_18000AA79
0x18000aa57  mov     rcx, [rbp+188h]; this
0x18000aa5e  lea     r8, aWil; "wil"
0x18000aa65  mov     esi, 8007000Eh
0x18000aa6a  mov     edx, 14Bh; void *
0x18000aa6f  mov     r9d, esi; char *
0x18000aa72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa77  jmp     short loc_18000AAE3
0x18000aa79  xorps   xmm0, xmm0
0x18000aa7c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000aa81  mov     r8, r14; void *
0x18000aa84  lea     rcx, [rsp+280h+var_250]; this
0x18000aa89  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000aa8f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000aa94  mov     esi, eax
0x18000aa96  test    eax, eax
0x18000aa98  jns     loc_18000AB36
0x18000aa9e  mov     rcx, [rbp+188h]; this
0x18000aaa5  lea     r8, aWil; "wil"
0x18000aaac  mov     r9d, eax; char *
0x18000aaaf  mov     edx, 14Eh; void *
0x18000aab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aab9  lea     rcx, [rsp+280h+var_250]; this
0x18000aabe  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000aac3  call    cs:__imp_GetProcessHeap
0x18000aaca  nop     dword ptr [rax+rax+00h]
0x18000aacf  mov     r8, r14; lpMem
0x18000aad2  xor     edx, edx; dwFlags
0x18000aad4  mov     rcx, rax; hHeap
0x18000aad7  call    cs:__imp_HeapFree
0x18000aade  nop     dword ptr [rax+rax+00h]
0x18000aae3  mov     rcx, [rbp+188h]; this
0x18000aaea  lea     r8, aWil; "wil"
0x18000aaf1  mov     r9d, esi; char *
0x18000aaf4  mov     edx, 137h; void *
0x18000aaf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aafe  test    rdi, rdi
0x18000ab01  jz      short loc_18000AB1A
0x18000ab03  mov     rcx, rdi; hMutex
0x18000ab06  call    cs:__imp_ReleaseMutex
0x18000ab0d  nop     dword ptr [rax+rax+00h]
0x18000ab12  test    eax, eax
0x18000ab14  jz      loc_18000AC53
0x18000ab1a  mov     rcx, rbx; hObject
0x18000ab1d  call    cs:__imp_CloseHandle
0x18000ab24  nop     dword ptr [rax+rax+00h]
0x18000ab29  test    eax, eax
0x18000ab2b  jz      loc_18000AC10
0x18000ab31  jmp     loc_18000AA14
0x18000ab36  mov     rax, [rsp+280h+var_250]
0x18000ab3b  lea     rcx, [r14+22h]; void *
0x18000ab3f  xor     edx, edx; Val
0x18000ab41  mov     [r14+10h], rax
0x18000ab45  mov     rax, [rsp+280h+var_250+8]
0x18000ab4a  mov     dword ptr [r14], 1
0x18000ab51  mov     [r14+8], rbx
0x18000ab55  lea     r8d, [rdx+56h]; Size
0x18000ab59  mov     [rsp+280h+var_250], 0
0x18000ab62  mov     [r14+18h], rax
0x18000ab66  mov     [rsp+280h+var_250+8], 0
0x18000ab6f  call    memset_0
0x18000ab74  xor     edx, edx; Val
0x18000ab76  mov     word ptr [r14+20h], 58h ; 'X'
0x18000ab7d  lea     rcx, [r14+28h]; void *
0x18000ab81  mov     dword ptr [r14+24h], 1
0x18000ab89  lea     r8d, [rdx+50h]; Size
0x18000ab8d  call    memset_0
0x18000ab92  lea     rcx, [rsp+280h+var_250]; this
0x18000ab97  mov     [r15], r14
0x18000ab9a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ab9f  xor     ebx, ebx
0x18000aba1  test    rdi, rdi
0x18000aba4  jz      short loc_18000ABBD
0x18000aba6  mov     rcx, rdi; hMutex
0x18000aba9  call    cs:__imp_ReleaseMutex
0x18000abb0  nop     dword ptr [rax+rax+00h]
0x18000abb5  test    eax, eax
0x18000abb7  jz      loc_18000AC65
0x18000abbd  test    rbx, rbx
0x18000abc0  jz      short loc_18000ABD5
0x18000abc2  mov     rcx, rbx; hObject
0x18000abc5  call    cs:__imp_CloseHandle
0x18000abcc  nop     dword ptr [rax+rax+00h]
0x18000abd1  test    eax, eax
0x18000abd3  jz      short loc_18000ABFE
0x18000abd5  xor     eax, eax
0x18000abd7  mov     rcx, [rbp+180h+var_30]
0x18000abde  xor     rcx, rsp; StackCookie
0x18000abe1  call    __security_check_cookie
0x18000abe6  mov     rbx, [rsp+280h+arg_10]
0x18000abee  add     rsp, 260h
0x18000abf5  pop     r15
0x18000abf7  pop     r14
0x18000abf9  pop     rdi
0x18000abfa  pop     rsi
0x18000abfb  pop     rbp
0x18000abfc  retn
0x18000abfe  mov     rcx, [rbp+188h]; this
0x18000ac05  mov     edx, 0A0Bh; void *
0x18000ac0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac10  mov     rcx, [rbp+188h]; this
0x18000ac17  mov     edx, 0A0Bh; void *
0x18000ac1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac22  mov     rcx, [rbp+188h]; this
0x18000ac29  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ac2f  mov     rcx, [rbp+188h]; this
0x18000ac36  mov     edx, 0A15h; void *
0x18000ac3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac41  mov     rcx, [rbp+188h]; this
0x18000ac48  mov     edx, 0A0Bh; void *
0x18000ac4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac53  mov     rcx, [rbp+188h]; this
0x18000ac5a  mov     edx, 0A15h; void *
0x18000ac5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac65  mov     rcx, [rbp+188h]; this
0x18000ac6c  mov     edx, 0A15h; void *
0x18000ac71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
