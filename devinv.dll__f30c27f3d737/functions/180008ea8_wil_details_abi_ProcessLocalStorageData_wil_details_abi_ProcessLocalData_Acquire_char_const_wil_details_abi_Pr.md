# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008ea8`
- end: `0x180009270`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000acc0`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180008ea8`
- `0x180009670`
- `0x180009bb0`
- `0x18000aa58`
- `0x18000b718`
- `0x18000d184`
- `0x18000dcec`
- `0x18000e1dc`
- `0x18000eaac`
- `0x18000eabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008fd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009115`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009185`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008fd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009115`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008f41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008f41`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000919b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000919b`

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
0x180008ea8  mov     [rsp-8+arg_10], rbx
0x180008ead  push    rbp
0x180008eae  push    rsi
0x180008eaf  push    rdi
0x180008eb0  push    r14
0x180008eb2  push    r15
0x180008eb4  lea     rbp, [rsp-160h]
0x180008ebc  sub     rsp, 260h
0x180008ec3  mov     rax, cs:__security_cookie
0x180008eca  xor     rax, rsp
0x180008ecd  mov     [rbp+180h+var_30], rax
0x180008ed4  mov     r15, rdx
0x180008ed7  mov     qword ptr [rdx], 0
0x180008ede  mov     rbx, rcx
0x180008ee1  call    cs:__imp_GetCurrentProcessId
0x180008ee7  mov     r14d, 78h ; 'x'
0x180008eed  mov     [rsp+280h+var_258], rbx
0x180008ef2  mov     r9d, eax
0x180008ef5  mov     [rsp+280h+var_260], r14d; int
0x180008efa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008f01  mov     edx, 104h; unsigned __int64
0x180008f06  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008f0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008f10  mov     r9d, 1F0001h; dwDesiredAccess
0x180008f16  lea     rdx, [rsp+280h+Name]; lpName
0x180008f1b  xor     r8d, r8d; dwFlags
0x180008f1e  xor     ecx, ecx; lpMutexAttributes
0x180008f20  call    cs:__imp_CreateMutexExW
0x180008f26  mov     rbx, rax
0x180008f29  test    rax, rax
0x180008f2c  jnz     short loc_180008F38
0x180008f2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008f33  jmp     loc_1800091A7
0x180008f38  xor     r8d, r8d; bAlertable
0x180008f3b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008f3e  mov     rcx, rbx; hHandle
0x180008f41  call    cs:__imp_WaitForSingleObjectEx
0x180008f47  cmp     eax, 102h
0x180008f4c  jz      short loc_180008F5E
0x180008f4e  test    eax, 0FFFFFF7Fh
0x180008f53  jnz     loc_1800091DF
0x180008f59  mov     rdi, rbx
0x180008f5c  jmp     short loc_180008F60
0x180008f5e  xor     edi, edi
0x180008f60  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008f65  mov     [rsp+280h+hObject], 0
0x180008f6e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008f73  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008f78  mov     esi, eax
0x180008f7a  test    eax, eax
0x180008f7c  jns     short loc_180008FFD
0x180008f7e  mov     rcx, [rbp+188h]; this
0x180008f85  lea     r8, aWil; "wil"
0x180008f8c  mov     r9d, eax; char *
0x180008f8f  mov     edx, 66h ; 'f'; void *
0x180008f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f99  mov     rcx, [rbp+188h]; this
0x180008fa0  lea     r8, aWil; "wil"
0x180008fa7  mov     r9d, esi; char *
0x180008faa  mov     edx, 6Fh ; 'o'; void *
0x180008faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fb4  mov     rcx, [rbp+188h]; this
0x180008fbb  lea     r8, aWil; "wil"
0x180008fc2  mov     r9d, esi; char *
0x180008fc5  mov     edx, 12Eh; void *
0x180008fca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fcf  test    rdi, rdi
0x180008fd2  jz      short loc_180008FE5
0x180008fd4  mov     rcx, rdi; hMutex
0x180008fd7  call    cs:__imp_ReleaseMutex
0x180008fdd  test    eax, eax
0x180008fdf  jz      loc_1800091EC
0x180008fe5  mov     rcx, rbx; hObject
0x180008fe8  call    cs:__imp_CloseHandle
0x180008fee  test    eax, eax
0x180008ff0  jz      loc_1800091FE
0x180008ff6  mov     eax, esi
0x180008ff8  jmp     loc_1800091A7
0x180008ffd  mov     rax, [rsp+280h+hObject]
0x180009002  lea     rcx, ds:0[rax*4]
0x18000900a  test    rcx, rcx
0x18000900d  jz      short loc_18000901D
0x18000900f  mov     [r15], rcx
0x180009012  mov     eax, [rcx]
0x180009014  inc     eax
0x180009016  mov     [rcx], eax
0x180009018  jmp     loc_18000917D
0x18000901d  mov     rdx, r14; dwBytes
0x180009020  mov     qword ptr [r15], 0
0x180009027  mov     ecx, 8; dwFlags
0x18000902c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009031  mov     rsi, rax
0x180009034  test    rax, rax
0x180009037  jnz     short loc_18000905F
0x180009039  mov     rcx, [rbp+188h]; this
0x180009040  lea     r8, aWil; "wil"
0x180009047  mov     r14d, 8007000Eh
0x18000904d  mov     edx, 14Bh; void *
0x180009052  mov     r9d, r14d; char *
0x180009055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000905a  jmp     loc_1800090F2
0x18000905f  xorps   xmm0, xmm0
0x180009062  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009068  test    sil, 3
0x18000906c  jnz     loc_180009210
0x180009072  mov     r9, rsi
0x180009075  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000907a  shr     r9, 2; unsigned __int64
0x18000907e  lea     rcx, [rsp+280h+hObject]; this
0x180009083  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009088  mov     r14d, eax
0x18000908b  test    eax, eax
0x18000908d  jns     loc_180009139
0x180009093  mov     rcx, [rbp+188h]; this
0x18000909a  lea     r8, aWil; "wil"
0x1800090a1  mov     r9d, eax; char *
0x1800090a4  mov     edx, 14Eh; void *
0x1800090a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090ae  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800090b3  test    rcx, rcx
0x1800090b6  jz      short loc_1800090C6
0x1800090b8  call    cs:__imp_CloseHandle
0x1800090be  test    eax, eax
0x1800090c0  jz      loc_180009216
0x1800090c6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800090cb  test    rcx, rcx
0x1800090ce  jz      short loc_1800090DE
0x1800090d0  call    cs:__imp_CloseHandle
0x1800090d6  test    eax, eax
0x1800090d8  jz      loc_180009228
0x1800090de  call    cs:__imp_GetProcessHeap
0x1800090e4  mov     r8, rsi; lpMem
0x1800090e7  xor     edx, edx; dwFlags
0x1800090e9  mov     rcx, rax; hHeap
0x1800090ec  call    cs:__imp_HeapFree
0x1800090f2  mov     rcx, [rbp+188h]; this
0x1800090f9  lea     r8, aWil; "wil"
0x180009100  mov     r9d, r14d; char *
0x180009103  mov     edx, 137h; void *
0x180009108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000910d  test    rdi, rdi
0x180009110  jz      short loc_180009123
0x180009112  mov     rcx, rdi; hMutex
0x180009115  call    cs:__imp_ReleaseMutex
0x18000911b  test    eax, eax
0x18000911d  jz      loc_18000923A
0x180009123  mov     rcx, rbx; hObject
0x180009126  call    cs:__imp_CloseHandle
0x18000912c  test    eax, eax
0x18000912e  jz      loc_18000924C
0x180009134  mov     eax, r14d
0x180009137  jmp     short loc_1800091A7
0x180009139  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000913e  xor     edx, edx; Val
0x180009140  mov     dword ptr [rsi], 1
0x180009146  lea     rcx, [rsi+22h]; void *
0x18000914a  mov     [rsi+8], rbx
0x18000914e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180009153  lea     r8d, [rdx+56h]; Size
0x180009157  call    memset_0
0x18000915c  xor     edx, edx; Val
0x18000915e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180009164  lea     rcx, [rsi+28h]; void *
0x180009168  mov     dword ptr [rsi+24h], 1
0x18000916f  lea     r8d, [rdx+50h]; Size
0x180009173  call    memset_0
0x180009178  xor     ebx, ebx
0x18000917a  mov     [r15], rsi
0x18000917d  test    rdi, rdi
0x180009180  jz      short loc_180009193
0x180009182  mov     rcx, rdi; hMutex
0x180009185  call    cs:__imp_ReleaseMutex
0x18000918b  test    eax, eax
0x18000918d  jz      loc_18000925E
0x180009193  test    rbx, rbx
0x180009196  jz      short loc_1800091A5
0x180009198  mov     rcx, rbx; hObject
0x18000919b  call    cs:__imp_CloseHandle
0x1800091a1  test    eax, eax
0x1800091a3  jz      short loc_1800091CD
0x1800091a5  xor     eax, eax
0x1800091a7  mov     rcx, [rbp+180h+var_30]
0x1800091ae  xor     rcx, rsp; StackCookie
0x1800091b1  call    __security_check_cookie
0x1800091b6  mov     rbx, [rsp+280h+arg_10]
0x1800091be  add     rsp, 260h
0x1800091c5  pop     r15
0x1800091c7  pop     r14
0x1800091c9  pop     rdi
0x1800091ca  pop     rsi
0x1800091cb  pop     rbp
0x1800091cc  retn
0x1800091cd  mov     rcx, [rbp+188h]; this
0x1800091d4  mov     edx, 0A0Bh; void *
0x1800091d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091df  mov     rcx, [rbp+188h]; this
0x1800091e6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800091ec  mov     rcx, [rbp+188h]; this
0x1800091f3  mov     edx, 0A15h; void *
0x1800091f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091fe  mov     rcx, [rbp+188h]; this
0x180009205  mov     edx, 0A0Bh; void *
0x18000920a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009210  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009216  mov     rcx, [rbp+188h]; this
0x18000921d  mov     edx, 0A0Bh; void *
0x180009222  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009228  mov     rcx, [rbp+188h]; this
0x18000922f  mov     edx, 0A0Bh; void *
0x180009234  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000923a  mov     rcx, [rbp+188h]; this
0x180009241  mov     edx, 0A15h; void *
0x180009246  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000924c  mov     rcx, [rbp+188h]; this
0x180009253  mov     edx, 0A0Bh; void *
0x180009258  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000925e  mov     rcx, [rbp+188h]; this
0x180009265  mov     edx, 0A15h; void *
0x18000926a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
