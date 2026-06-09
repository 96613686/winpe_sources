# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003a68`
- end: `0x180003e30`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004970`

## callees

- `0x180001540`
- `0x180001fd6`
- `0x180003a68`
- `0x180003e38`
- `0x180004080`
- `0x180004700`
- `0x18000524c`
- `0x18000553c`
- `0x18000607c`
- `0x18000615c`
- `0x180006730`
- `0x180006740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ae0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ae0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5b`

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
0x180003a68  mov     [rsp-8+arg_10], rbx
0x180003a6d  push    rbp
0x180003a6e  push    rsi
0x180003a6f  push    rdi
0x180003a70  push    r14
0x180003a72  push    r15
0x180003a74  lea     rbp, [rsp-160h]
0x180003a7c  sub     rsp, 260h
0x180003a83  mov     rax, cs:__security_cookie
0x180003a8a  xor     rax, rsp
0x180003a8d  mov     [rbp+180h+var_30], rax
0x180003a94  mov     r15, rdx
0x180003a97  mov     qword ptr [rdx], 0
0x180003a9e  mov     rbx, rcx
0x180003aa1  call    cs:__imp_GetCurrentProcessId
0x180003aa7  mov     r14d, 78h ; 'x'
0x180003aad  mov     [rsp+280h+var_258], rbx
0x180003ab2  mov     r9d, eax
0x180003ab5  mov     [rsp+280h+var_260], r14d; int
0x180003aba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ac1  mov     edx, 104h; unsigned __int64
0x180003ac6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180003acb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003ad0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ad6  lea     rdx, [rsp+280h+Name]; lpName
0x180003adb  xor     r8d, r8d; dwFlags
0x180003ade  xor     ecx, ecx; lpMutexAttributes
0x180003ae0  call    cs:__imp_CreateMutexExW
0x180003ae6  mov     rbx, rax
0x180003ae9  test    rax, rax
0x180003aec  jnz     short loc_180003AF8
0x180003aee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003af3  jmp     loc_180003D67
0x180003af8  xor     r8d, r8d; bAlertable
0x180003afb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003afe  mov     rcx, rbx; hHandle
0x180003b01  call    cs:__imp_WaitForSingleObjectEx
0x180003b07  cmp     eax, 102h
0x180003b0c  jz      short loc_180003B1E
0x180003b0e  test    eax, 0FFFFFF7Fh
0x180003b13  jnz     loc_180003D9F
0x180003b19  mov     rdi, rbx
0x180003b1c  jmp     short loc_180003B20
0x180003b1e  xor     edi, edi
0x180003b20  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b25  mov     [rsp+280h+hObject], 0
0x180003b2e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180003b33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180003b38  mov     esi, eax
0x180003b3a  test    eax, eax
0x180003b3c  jns     short loc_180003BBD
0x180003b3e  mov     rcx, [rbp+188h]; this
0x180003b45  lea     r8, aWil; "wil"
0x180003b4c  mov     r9d, eax; char *
0x180003b4f  mov     edx, 66h ; 'f'; void *
0x180003b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b59  mov     rcx, [rbp+188h]; this
0x180003b60  lea     r8, aWil; "wil"
0x180003b67  mov     r9d, esi; char *
0x180003b6a  mov     edx, 6Fh ; 'o'; void *
0x180003b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b74  mov     rcx, [rbp+188h]; this
0x180003b7b  lea     r8, aWil; "wil"
0x180003b82  mov     r9d, esi; char *
0x180003b85  mov     edx, 12Eh; void *
0x180003b8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b8f  test    rdi, rdi
0x180003b92  jz      short loc_180003BA5
0x180003b94  mov     rcx, rdi; hMutex
0x180003b97  call    cs:__imp_ReleaseMutex
0x180003b9d  test    eax, eax
0x180003b9f  jz      loc_180003DAC
0x180003ba5  mov     rcx, rbx; hObject
0x180003ba8  call    cs:__imp_CloseHandle
0x180003bae  test    eax, eax
0x180003bb0  jz      loc_180003DBE
0x180003bb6  mov     eax, esi
0x180003bb8  jmp     loc_180003D67
0x180003bbd  mov     rax, [rsp+280h+hObject]
0x180003bc2  lea     rcx, ds:0[rax*4]
0x180003bca  test    rcx, rcx
0x180003bcd  jz      short loc_180003BDD
0x180003bcf  mov     [r15], rcx
0x180003bd2  mov     eax, [rcx]
0x180003bd4  inc     eax
0x180003bd6  mov     [rcx], eax
0x180003bd8  jmp     loc_180003D3D
0x180003bdd  mov     rdx, r14; dwBytes
0x180003be0  mov     qword ptr [r15], 0
0x180003be7  mov     ecx, 8; dwFlags
0x180003bec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003bf1  mov     rsi, rax
0x180003bf4  test    rax, rax
0x180003bf7  jnz     short loc_180003C1F
0x180003bf9  mov     rcx, [rbp+188h]; this
0x180003c00  lea     r8, aWil; "wil"
0x180003c07  mov     r14d, 8007000Eh
0x180003c0d  mov     edx, 14Bh; void *
0x180003c12  mov     r9d, r14d; char *
0x180003c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1a  jmp     loc_180003CB2
0x180003c1f  xorps   xmm0, xmm0
0x180003c22  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c28  test    sil, 3
0x180003c2c  jnz     loc_180003DD0
0x180003c32  mov     r9, rsi
0x180003c35  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180003c3a  shr     r9, 2; unsigned __int64
0x180003c3e  lea     rcx, [rsp+280h+hObject]; this
0x180003c43  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180003c48  mov     r14d, eax
0x180003c4b  test    eax, eax
0x180003c4d  jns     loc_180003CF9
0x180003c53  mov     rcx, [rbp+188h]; this
0x180003c5a  lea     r8, aWil; "wil"
0x180003c61  mov     r9d, eax; char *
0x180003c64  mov     edx, 14Eh; void *
0x180003c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c6e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003c73  test    rcx, rcx
0x180003c76  jz      short loc_180003C86
0x180003c78  call    cs:__imp_CloseHandle
0x180003c7e  test    eax, eax
0x180003c80  jz      loc_180003DD6
0x180003c86  mov     rcx, [rsp+280h+hObject]; hObject
0x180003c8b  test    rcx, rcx
0x180003c8e  jz      short loc_180003C9E
0x180003c90  call    cs:__imp_CloseHandle
0x180003c96  test    eax, eax
0x180003c98  jz      loc_180003DE8
0x180003c9e  call    cs:__imp_GetProcessHeap
0x180003ca4  mov     r8, rsi; lpMem
0x180003ca7  xor     edx, edx; dwFlags
0x180003ca9  mov     rcx, rax; hHeap
0x180003cac  call    cs:__imp_HeapFree
0x180003cb2  mov     rcx, [rbp+188h]; this
0x180003cb9  lea     r8, aWil; "wil"
0x180003cc0  mov     r9d, r14d; char *
0x180003cc3  mov     edx, 137h; void *
0x180003cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ccd  test    rdi, rdi
0x180003cd0  jz      short loc_180003CE3
0x180003cd2  mov     rcx, rdi; hMutex
0x180003cd5  call    cs:__imp_ReleaseMutex
0x180003cdb  test    eax, eax
0x180003cdd  jz      loc_180003DFA
0x180003ce3  mov     rcx, rbx; hObject
0x180003ce6  call    cs:__imp_CloseHandle
0x180003cec  test    eax, eax
0x180003cee  jz      loc_180003E0C
0x180003cf4  mov     eax, r14d
0x180003cf7  jmp     short loc_180003D67
0x180003cf9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003cfe  xor     edx, edx; Val
0x180003d00  mov     dword ptr [rsi], 1
0x180003d06  lea     rcx, [rsi+22h]; void *
0x180003d0a  mov     [rsi+8], rbx
0x180003d0e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003d13  lea     r8d, [rdx+56h]; Size
0x180003d17  call    memset_0
0x180003d1c  xor     edx, edx; Val
0x180003d1e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d24  lea     rcx, [rsi+28h]; void *
0x180003d28  mov     dword ptr [rsi+24h], 1
0x180003d2f  lea     r8d, [rdx+50h]; Size
0x180003d33  call    memset_0
0x180003d38  xor     ebx, ebx
0x180003d3a  mov     [r15], rsi
0x180003d3d  test    rdi, rdi
0x180003d40  jz      short loc_180003D53
0x180003d42  mov     rcx, rdi; hMutex
0x180003d45  call    cs:__imp_ReleaseMutex
0x180003d4b  test    eax, eax
0x180003d4d  jz      loc_180003E1E
0x180003d53  test    rbx, rbx
0x180003d56  jz      short loc_180003D65
0x180003d58  mov     rcx, rbx; hObject
0x180003d5b  call    cs:__imp_CloseHandle
0x180003d61  test    eax, eax
0x180003d63  jz      short loc_180003D8D
0x180003d65  xor     eax, eax
0x180003d67  mov     rcx, [rbp+180h+var_30]
0x180003d6e  xor     rcx, rsp; StackCookie
0x180003d71  call    __security_check_cookie
0x180003d76  mov     rbx, [rsp+280h+arg_10]
0x180003d7e  add     rsp, 260h
0x180003d85  pop     r15
0x180003d87  pop     r14
0x180003d89  pop     rdi
0x180003d8a  pop     rsi
0x180003d8b  pop     rbp
0x180003d8c  retn
0x180003d8d  mov     rcx, [rbp+188h]; this
0x180003d94  mov     edx, 0A0Bh; void *
0x180003d99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d9f  mov     rcx, [rbp+188h]; this
0x180003da6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003dac  mov     rcx, [rbp+188h]; this
0x180003db3  mov     edx, 0A15h; void *
0x180003db8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dbe  mov     rcx, [rbp+188h]; this
0x180003dc5  mov     edx, 0A0Bh; void *
0x180003dca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003dd6  mov     rcx, [rbp+188h]; this
0x180003ddd  mov     edx, 0A0Bh; void *
0x180003de2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003de8  mov     rcx, [rbp+188h]; this
0x180003def  mov     edx, 0A0Bh; void *
0x180003df4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dfa  mov     rcx, [rbp+188h]; this
0x180003e01  mov     edx, 0A15h; void *
0x180003e06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e0c  mov     rcx, [rbp+188h]; this
0x180003e13  mov     edx, 0A0Bh; void *
0x180003e18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e1e  mov     rcx, [rbp+188h]; this
0x180003e25  mov     edx, 0A15h; void *
0x180003e2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
