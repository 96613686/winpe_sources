# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004998`
- end: `0x180004d6c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005b10`

## callees

- `0x1800021d0`
- `0x180002b78`
- `0x180004998`
- `0x180004d74`
- `0x180005218`
- `0x1800058a8`
- `0x1800064cc`
- `0x180006ba4`
- `0x180007594`
- `0x18000766c`
- `0x180007a2c`
- `0x180007a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a10`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004a10`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c75`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800049d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800049d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c8b`

## string_xrefs

- `0x180004cd6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x180004998  mov     [rsp-8+arg_10], rbx
0x18000499d  push    rbp
0x18000499e  push    rsi
0x18000499f  push    rdi
0x1800049a0  push    r14
0x1800049a2  push    r15
0x1800049a4  lea     rbp, [rsp-160h]
0x1800049ac  sub     rsp, 260h
0x1800049b3  mov     rax, cs:__security_cookie
0x1800049ba  xor     rax, rsp
0x1800049bd  mov     [rbp+180h+var_30], rax
0x1800049c4  mov     r15, rdx
0x1800049c7  mov     qword ptr [rdx], 0
0x1800049ce  mov     rbx, rcx
0x1800049d1  call    cs:__imp_GetCurrentProcessId
0x1800049d7  mov     r14d, 78h ; 'x'
0x1800049dd  mov     [rsp+280h+var_258], rbx
0x1800049e2  mov     r9d, eax
0x1800049e5  mov     [rsp+280h+var_260], r14d; int
0x1800049ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800049f1  mov     edx, 104h; unsigned __int64
0x1800049f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800049fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004a00  mov     r9d, 1F0001h; dwDesiredAccess
0x180004a06  lea     rdx, [rsp+280h+Name]; lpName
0x180004a0b  xor     r8d, r8d; dwFlags
0x180004a0e  xor     ecx, ecx; lpMutexAttributes
0x180004a10  call    cs:__imp_CreateMutexExW
0x180004a16  mov     rbx, rax
0x180004a19  test    rax, rax
0x180004a1c  jnz     short loc_180004A28
0x180004a1e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a23  jmp     loc_180004C97
0x180004a28  xor     r8d, r8d; bAlertable
0x180004a2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004a2e  mov     rcx, rbx; hHandle
0x180004a31  call    cs:__imp_WaitForSingleObjectEx
0x180004a37  cmp     eax, 102h
0x180004a3c  jz      short loc_180004A4E
0x180004a3e  test    eax, 0FFFFFF7Fh
0x180004a43  jnz     loc_180004CCF
0x180004a49  mov     rdi, rbx
0x180004a4c  jmp     short loc_180004A50
0x180004a4e  xor     edi, edi
0x180004a50  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004a55  mov     [rsp+280h+hObject], 0
0x180004a5e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004a63  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004a68  mov     esi, eax
0x180004a6a  test    eax, eax
0x180004a6c  jns     short loc_180004AED
0x180004a6e  mov     rcx, [rbp+188h]; this
0x180004a75  lea     r8, aWil; "wil"
0x180004a7c  mov     r9d, eax; char *
0x180004a7f  mov     edx, 66h ; 'f'; void *
0x180004a84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a89  mov     rcx, [rbp+188h]; this
0x180004a90  lea     r8, aWil; "wil"
0x180004a97  mov     r9d, esi; char *
0x180004a9a  mov     edx, 6Fh ; 'o'; void *
0x180004a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004aa4  mov     rcx, [rbp+188h]; this
0x180004aab  lea     r8, aWil; "wil"
0x180004ab2  mov     r9d, esi; char *
0x180004ab5  mov     edx, 12Eh; void *
0x180004aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004abf  test    rdi, rdi
0x180004ac2  jz      short loc_180004AD5
0x180004ac4  mov     rcx, rdi; hMutex
0x180004ac7  call    cs:__imp_ReleaseMutex
0x180004acd  test    eax, eax
0x180004acf  jz      loc_180004CE8
0x180004ad5  mov     rcx, rbx; hObject
0x180004ad8  call    cs:__imp_CloseHandle
0x180004ade  test    eax, eax
0x180004ae0  jz      loc_180004CFA
0x180004ae6  mov     eax, esi
0x180004ae8  jmp     loc_180004C97
0x180004aed  mov     rax, [rsp+280h+hObject]
0x180004af2  lea     rcx, ds:0[rax*4]
0x180004afa  test    rcx, rcx
0x180004afd  jz      short loc_180004B0D
0x180004aff  mov     [r15], rcx
0x180004b02  mov     eax, [rcx]
0x180004b04  inc     eax
0x180004b06  mov     [rcx], eax
0x180004b08  jmp     loc_180004C6D
0x180004b0d  mov     rdx, r14; dwBytes
0x180004b10  mov     qword ptr [r15], 0
0x180004b17  mov     ecx, 8; dwFlags
0x180004b1c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004b21  mov     rsi, rax
0x180004b24  test    rax, rax
0x180004b27  jnz     short loc_180004B4F
0x180004b29  mov     rcx, [rbp+188h]; this
0x180004b30  lea     r8, aWil; "wil"
0x180004b37  mov     r14d, 8007000Eh
0x180004b3d  mov     edx, 14Bh; void *
0x180004b42  mov     r9d, r14d; char *
0x180004b45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b4a  jmp     loc_180004BE2
0x180004b4f  xorps   xmm0, xmm0
0x180004b52  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004b58  test    sil, 3
0x180004b5c  jnz     loc_180004D0C
0x180004b62  mov     r9, rsi
0x180004b65  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004b6a  shr     r9, 2; unsigned __int64
0x180004b6e  lea     rcx, [rsp+280h+hObject]; this
0x180004b73  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004b78  mov     r14d, eax
0x180004b7b  test    eax, eax
0x180004b7d  jns     loc_180004C29
0x180004b83  mov     rcx, [rbp+188h]; this
0x180004b8a  lea     r8, aWil; "wil"
0x180004b91  mov     r9d, eax; char *
0x180004b94  mov     edx, 14Eh; void *
0x180004b99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b9e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004ba3  test    rcx, rcx
0x180004ba6  jz      short loc_180004BB6
0x180004ba8  call    cs:__imp_CloseHandle
0x180004bae  test    eax, eax
0x180004bb0  jz      loc_180004D12
0x180004bb6  mov     rcx, [rsp+280h+hObject]; hObject
0x180004bbb  test    rcx, rcx
0x180004bbe  jz      short loc_180004BCE
0x180004bc0  call    cs:__imp_CloseHandle
0x180004bc6  test    eax, eax
0x180004bc8  jz      loc_180004D24
0x180004bce  call    cs:__imp_GetProcessHeap
0x180004bd4  mov     r8, rsi; lpMem
0x180004bd7  xor     edx, edx; dwFlags
0x180004bd9  mov     rcx, rax; hHeap
0x180004bdc  call    cs:__imp_HeapFree
0x180004be2  mov     rcx, [rbp+188h]; this
0x180004be9  lea     r8, aWil; "wil"
0x180004bf0  mov     r9d, r14d; char *
0x180004bf3  mov     edx, 137h; void *
0x180004bf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bfd  test    rdi, rdi
0x180004c00  jz      short loc_180004C13
0x180004c02  mov     rcx, rdi; hMutex
0x180004c05  call    cs:__imp_ReleaseMutex
0x180004c0b  test    eax, eax
0x180004c0d  jz      loc_180004D36
0x180004c13  mov     rcx, rbx; hObject
0x180004c16  call    cs:__imp_CloseHandle
0x180004c1c  test    eax, eax
0x180004c1e  jz      loc_180004D48
0x180004c24  mov     eax, r14d
0x180004c27  jmp     short loc_180004C97
0x180004c29  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004c2e  xor     edx, edx; Val
0x180004c30  mov     dword ptr [rsi], 1
0x180004c36  lea     rcx, [rsi+22h]; void *
0x180004c3a  mov     [rsi+8], rbx
0x180004c3e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004c43  lea     r8d, [rdx+56h]; Size
0x180004c47  call    memset_0
0x180004c4c  xor     edx, edx; Val
0x180004c4e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004c54  lea     rcx, [rsi+28h]; void *
0x180004c58  mov     dword ptr [rsi+24h], 1
0x180004c5f  lea     r8d, [rdx+50h]; Size
0x180004c63  call    memset_0
0x180004c68  xor     ebx, ebx
0x180004c6a  mov     [r15], rsi
0x180004c6d  test    rdi, rdi
0x180004c70  jz      short loc_180004C83
0x180004c72  mov     rcx, rdi; hMutex
0x180004c75  call    cs:__imp_ReleaseMutex
0x180004c7b  test    eax, eax
0x180004c7d  jz      loc_180004D5A
0x180004c83  test    rbx, rbx
0x180004c86  jz      short loc_180004C95
0x180004c88  mov     rcx, rbx; hObject
0x180004c8b  call    cs:__imp_CloseHandle
0x180004c91  test    eax, eax
0x180004c93  jz      short loc_180004CBD
0x180004c95  xor     eax, eax
0x180004c97  mov     rcx, [rbp+180h+var_30]
0x180004c9e  xor     rcx, rsp; StackCookie
0x180004ca1  call    __security_check_cookie
0x180004ca6  mov     rbx, [rsp+280h+arg_10]
0x180004cae  add     rsp, 260h
0x180004cb5  pop     r15
0x180004cb7  pop     r14
0x180004cb9  pop     rdi
0x180004cba  pop     rsi
0x180004cbb  pop     rbp
0x180004cbc  retn
0x180004cbd  mov     rcx, [rbp+188h]; this
0x180004cc4  mov     edx, 0A0Bh; void *
0x180004cc9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ccf  mov     rcx, [rbp+188h]; this
0x180004cd6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004cdd  mov     edx, 0E01h; void *
0x180004ce2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004ce8  mov     rcx, [rbp+188h]; this
0x180004cef  mov     edx, 0A15h; void *
0x180004cf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cfa  mov     rcx, [rbp+188h]; this
0x180004d01  mov     edx, 0A0Bh; void *
0x180004d06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d0c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004d12  mov     rcx, [rbp+188h]; this
0x180004d19  mov     edx, 0A0Bh; void *
0x180004d1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d24  mov     rcx, [rbp+188h]; this
0x180004d2b  mov     edx, 0A0Bh; void *
0x180004d30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d36  mov     rcx, [rbp+188h]; this
0x180004d3d  mov     edx, 0A15h; void *
0x180004d42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d48  mov     rcx, [rbp+188h]; this
0x180004d4f  mov     edx, 0A0Bh; void *
0x180004d54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d5a  mov     rcx, [rbp+188h]; this
0x180004d61  mov     edx, 0A15h; void *
0x180004d66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
