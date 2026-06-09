# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a918`
- end: `0x18000acf0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000cc68`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18000a488`
- `0x18000a918`
- `0x18000b2a8`
- `0x18000b948`
- `0x18000c690`
- `0x18000d668`
- `0x18000f1b4`
- `0x18000fcc8`
- `0x180010198`
- `0x1800115b4`
- `0x1800115c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aa47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000abf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aa47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000abf3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a990`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a990`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a9b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a9b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac09`

## string_xrefs

- `0x18000ac42`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ac5b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ac74`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ac8d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000acac`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000acc5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000acde`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x18000a918  mov     [rsp-8+arg_10], rbx
0x18000a91d  push    rbp
0x18000a91e  push    rsi
0x18000a91f  push    rdi
0x18000a920  push    r14
0x18000a922  push    r15
0x18000a924  lea     rbp, [rsp-160h]
0x18000a92c  sub     rsp, 260h
0x18000a933  mov     rax, cs:__security_cookie
0x18000a93a  xor     rax, rsp
0x18000a93d  mov     [rbp+180h+var_30], rax
0x18000a944  mov     r15, rdx
0x18000a947  mov     qword ptr [rdx], 0
0x18000a94e  mov     rbx, rcx
0x18000a951  call    cs:__imp_GetCurrentProcessId
0x18000a957  mov     r14d, 78h ; 'x'
0x18000a95d  mov     [rsp+280h+var_258], rbx
0x18000a962  mov     r9d, eax
0x18000a965  mov     [rsp+280h+var_260], r14d; int
0x18000a96a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a971  mov     edx, 104h; unsigned __int64
0x18000a976  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a97b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a980  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a986  lea     rdx, [rsp+280h+Name]; lpName
0x18000a98b  xor     r8d, r8d; dwFlags
0x18000a98e  xor     ecx, ecx; lpMutexAttributes
0x18000a990  call    cs:__imp_CreateMutexExW
0x18000a996  mov     rbx, rax
0x18000a999  test    rax, rax
0x18000a99c  jnz     short loc_18000A9A8
0x18000a99e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a9a3  jmp     loc_18000AC15
0x18000a9a8  xor     r8d, r8d; bAlertable
0x18000a9ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a9ae  mov     rcx, rbx; hHandle
0x18000a9b1  call    cs:__imp_WaitForSingleObjectEx
0x18000a9b7  cmp     eax, 102h
0x18000a9bc  jz      short loc_18000A9CE
0x18000a9be  test    eax, 0FFFFFF7Fh
0x18000a9c3  jnz     loc_18000AC54
0x18000a9c9  mov     rdi, rbx
0x18000a9cc  jmp     short loc_18000A9D0
0x18000a9ce  xor     edi, edi
0x18000a9d0  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000a9d5  mov     [rsp+280h+var_250], 0
0x18000a9de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a9e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a9e8  mov     esi, eax
0x18000a9ea  test    eax, eax
0x18000a9ec  jns     short loc_18000AA6D
0x18000a9ee  mov     rcx, [rbp+188h]; this
0x18000a9f5  lea     r8, aWil; "wil"
0x18000a9fc  mov     r9d, eax; char *
0x18000a9ff  mov     edx, 66h ; 'f'; void *
0x18000aa04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa09  mov     rcx, [rbp+188h]; this
0x18000aa10  lea     r8, aWil; "wil"
0x18000aa17  mov     r9d, esi; char *
0x18000aa1a  mov     edx, 6Fh ; 'o'; void *
0x18000aa1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa24  mov     rcx, [rbp+188h]; this
0x18000aa2b  lea     r8, aWil; "wil"
0x18000aa32  mov     r9d, esi; char *
0x18000aa35  mov     edx, 12Eh; void *
0x18000aa3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa3f  test    rdi, rdi
0x18000aa42  jz      short loc_18000AA55
0x18000aa44  mov     rcx, rdi; hMutex
0x18000aa47  call    cs:__imp_ReleaseMutex
0x18000aa4d  test    eax, eax
0x18000aa4f  jz      loc_18000AC6D
0x18000aa55  mov     rcx, rbx; hObject
0x18000aa58  call    cs:__imp_CloseHandle
0x18000aa5e  test    eax, eax
0x18000aa60  jz      loc_18000AC86
0x18000aa66  mov     eax, esi
0x18000aa68  jmp     loc_18000AC15
0x18000aa6d  mov     rax, [rsp+280h+var_250]
0x18000aa72  lea     rcx, ds:0[rax*4]
0x18000aa7a  test    rcx, rcx
0x18000aa7d  jz      short loc_18000AA8D
0x18000aa7f  mov     [r15], rcx
0x18000aa82  mov     eax, [rcx]
0x18000aa84  inc     eax
0x18000aa86  mov     [rcx], eax
0x18000aa88  jmp     loc_18000ABEB
0x18000aa8d  mov     rdx, r14; dwBytes
0x18000aa90  mov     qword ptr [r15], 0
0x18000aa97  mov     ecx, 8; dwFlags
0x18000aa9c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aaa1  mov     rsi, rax
0x18000aaa4  test    rax, rax
0x18000aaa7  jnz     short loc_18000AACC
0x18000aaa9  mov     rcx, [rbp+188h]; this
0x18000aab0  lea     r8, aWil; "wil"
0x18000aab7  mov     r14d, 8007000Eh
0x18000aabd  mov     edx, 14Bh; void *
0x18000aac2  mov     r9d, r14d; char *
0x18000aac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaca  jmp     short loc_18000AB39
0x18000aacc  xorps   xmm0, xmm0
0x18000aacf  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000aad5  test    sil, 3
0x18000aad9  jnz     loc_18000AC9F
0x18000aadf  mov     r9, rsi
0x18000aae2  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000aae7  shr     r9, 2; unsigned __int64
0x18000aaeb  lea     rcx, [rsp+280h+var_250]; this
0x18000aaf0  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000aaf5  mov     r14d, eax
0x18000aaf8  test    eax, eax
0x18000aafa  jns     loc_18000AB83
0x18000ab00  mov     rcx, [rbp+188h]; this
0x18000ab07  lea     r8, aWil; "wil"
0x18000ab0e  mov     r9d, eax; char *
0x18000ab11  mov     edx, 14Eh; void *
0x18000ab16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab1b  lea     rcx, [rsp+280h+var_250]; this
0x18000ab20  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ab25  call    cs:__imp_GetProcessHeap
0x18000ab2b  mov     r8, rsi; lpMem
0x18000ab2e  xor     edx, edx; dwFlags
0x18000ab30  mov     rcx, rax; hHeap
0x18000ab33  call    cs:__imp_HeapFree
0x18000ab39  mov     rcx, [rbp+188h]; this
0x18000ab40  lea     r8, aWil; "wil"
0x18000ab47  mov     r9d, r14d; char *
0x18000ab4a  mov     edx, 137h; void *
0x18000ab4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab54  test    rdi, rdi
0x18000ab57  jz      short loc_18000AB6A
0x18000ab59  mov     rcx, rdi; hMutex
0x18000ab5c  call    cs:__imp_ReleaseMutex
0x18000ab62  test    eax, eax
0x18000ab64  jz      loc_18000ACA5
0x18000ab6a  mov     rcx, rbx; hObject
0x18000ab6d  call    cs:__imp_CloseHandle
0x18000ab73  test    eax, eax
0x18000ab75  jz      loc_18000ACBE
0x18000ab7b  mov     eax, r14d
0x18000ab7e  jmp     loc_18000AC15
0x18000ab83  mov     rax, [rsp+280h+var_250]
0x18000ab88  lea     rcx, [rsi+22h]; void *
0x18000ab8c  xor     edx, edx; Val
0x18000ab8e  mov     [rsi+10h], rax
0x18000ab92  mov     rax, [rsp+280h+var_250+8]
0x18000ab97  mov     dword ptr [rsi], 1
0x18000ab9d  mov     [rsi+8], rbx
0x18000aba1  lea     r8d, [rdx+56h]; Size
0x18000aba5  mov     [rsp+280h+var_250], 0
0x18000abae  mov     [rsi+18h], rax
0x18000abb2  mov     [rsp+280h+var_250+8], 0
0x18000abbb  call    memset_0
0x18000abc0  xor     edx, edx; Val
0x18000abc2  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000abc8  lea     rcx, [rsi+28h]; void *
0x18000abcc  mov     dword ptr [rsi+24h], 1
0x18000abd3  lea     r8d, [rdx+50h]; Size
0x18000abd7  call    memset_0
0x18000abdc  lea     rcx, [rsp+280h+var_250]; this
0x18000abe1  mov     [r15], rsi
0x18000abe4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000abe9  xor     ebx, ebx
0x18000abeb  test    rdi, rdi
0x18000abee  jz      short loc_18000AC01
0x18000abf0  mov     rcx, rdi; hMutex
0x18000abf3  call    cs:__imp_ReleaseMutex
0x18000abf9  test    eax, eax
0x18000abfb  jz      loc_18000ACD7
0x18000ac01  test    rbx, rbx
0x18000ac04  jz      short loc_18000AC13
0x18000ac06  mov     rcx, rbx; hObject
0x18000ac09  call    cs:__imp_CloseHandle
0x18000ac0f  test    eax, eax
0x18000ac11  jz      short loc_18000AC3B
0x18000ac13  xor     eax, eax
0x18000ac15  mov     rcx, [rbp+180h+var_30]
0x18000ac1c  xor     rcx, rsp; StackCookie
0x18000ac1f  call    __security_check_cookie
0x18000ac24  mov     rbx, [rsp+280h+arg_10]
0x18000ac2c  add     rsp, 260h
0x18000ac33  pop     r15
0x18000ac35  pop     r14
0x18000ac37  pop     rdi
0x18000ac38  pop     rsi
0x18000ac39  pop     rbp
0x18000ac3a  retn
0x18000ac3b  mov     rcx, [rbp+188h]; this
0x18000ac42  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ac49  mov     edx, 0A0Bh; void *
0x18000ac4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac54  mov     rcx, [rbp+188h]; this
0x18000ac5b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ac62  mov     edx, 0E01h; void *
0x18000ac67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ac6d  mov     rcx, [rbp+188h]; this
0x18000ac74  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ac7b  mov     edx, 0A15h; void *
0x18000ac80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac86  mov     rcx, [rbp+188h]; this
0x18000ac8d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ac94  mov     edx, 0A0Bh; void *
0x18000ac99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac9f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000aca5  mov     rcx, [rbp+188h]; this
0x18000acac  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000acb3  mov     edx, 0A15h; void *
0x18000acb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000acbe  mov     rcx, [rbp+188h]; this
0x18000acc5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000accc  mov     edx, 0A0Bh; void *
0x18000acd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000acd7  mov     rcx, [rbp+188h]; this
0x18000acde  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ace5  mov     edx, 0A15h; void *
0x18000acea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
