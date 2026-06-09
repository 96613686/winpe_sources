# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004bd0`
- end: `0x140004f98`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140007274`

## callees

- `0x140004bd0`
- `0x140005600`
- `0x140006a28`
- `0x140006fb8`
- `0x14000a74c`
- `0x14000ad94`
- `0x14000b5c4`
- `0x14000b69c`
- `0x14000bc1c`
- `0x14000bc2c`
- `0x1400187b2`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004cff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004ead`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004cff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004ead`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004c69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004c69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004c48`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004c48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004c09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004df8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ec3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004df8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ec3`

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
0x140004bd0  mov     [rsp-8+arg_10], rbx
0x140004bd5  push    rbp
0x140004bd6  push    rsi
0x140004bd7  push    rdi
0x140004bd8  push    r14
0x140004bda  push    r15
0x140004bdc  lea     rbp, [rsp-160h]
0x140004be4  sub     rsp, 260h
0x140004beb  mov     rax, cs:__security_cookie
0x140004bf2  xor     rax, rsp
0x140004bf5  mov     [rbp+180h+var_30], rax
0x140004bfc  mov     r15, rdx
0x140004bff  mov     qword ptr [rdx], 0
0x140004c06  mov     rbx, rcx
0x140004c09  call    cs:__imp_GetCurrentProcessId
0x140004c0f  mov     r14d, 78h ; 'x'
0x140004c15  mov     [rsp+280h+var_258], rbx
0x140004c1a  mov     r9d, eax
0x140004c1d  mov     [rsp+280h+var_260], r14d; int
0x140004c22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004c29  mov     edx, 104h; unsigned __int64
0x140004c2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004c33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004c38  mov     r9d, 1F0001h; dwDesiredAccess
0x140004c3e  lea     rdx, [rsp+280h+Name]; lpName
0x140004c43  xor     r8d, r8d; dwFlags
0x140004c46  xor     ecx, ecx; lpMutexAttributes
0x140004c48  call    cs:__imp_CreateMutexExW
0x140004c4e  mov     rbx, rax
0x140004c51  test    rax, rax
0x140004c54  jnz     short loc_140004C60
0x140004c56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004c5b  jmp     loc_140004ECF
0x140004c60  xor     r8d, r8d; bAlertable
0x140004c63  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004c66  mov     rcx, rbx; hHandle
0x140004c69  call    cs:__imp_WaitForSingleObjectEx
0x140004c6f  cmp     eax, 102h
0x140004c74  jz      short loc_140004C86
0x140004c76  test    eax, 0FFFFFF7Fh
0x140004c7b  jnz     loc_140004F07
0x140004c81  mov     rdi, rbx
0x140004c84  jmp     short loc_140004C88
0x140004c86  xor     edi, edi
0x140004c88  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004c8d  mov     [rsp+280h+hObject], 0
0x140004c96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004c9b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004ca0  mov     esi, eax
0x140004ca2  test    eax, eax
0x140004ca4  jns     short loc_140004D25
0x140004ca6  mov     rcx, [rbp+188h]; this
0x140004cad  lea     r8, aWil; "wil"
0x140004cb4  mov     r9d, eax; char *
0x140004cb7  mov     edx, 66h ; 'f'; void *
0x140004cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004cc1  mov     rcx, [rbp+188h]; this
0x140004cc8  lea     r8, aWil; "wil"
0x140004ccf  mov     r9d, esi; char *
0x140004cd2  mov     edx, 6Fh ; 'o'; void *
0x140004cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004cdc  mov     rcx, [rbp+188h]; this
0x140004ce3  lea     r8, aWil; "wil"
0x140004cea  mov     r9d, esi; char *
0x140004ced  mov     edx, 12Eh; void *
0x140004cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004cf7  test    rdi, rdi
0x140004cfa  jz      short loc_140004D0D
0x140004cfc  mov     rcx, rdi; hMutex
0x140004cff  call    cs:__imp_ReleaseMutex
0x140004d05  test    eax, eax
0x140004d07  jz      loc_140004F14
0x140004d0d  mov     rcx, rbx; hObject
0x140004d10  call    cs:__imp_CloseHandle
0x140004d16  test    eax, eax
0x140004d18  jz      loc_140004F26
0x140004d1e  mov     eax, esi
0x140004d20  jmp     loc_140004ECF
0x140004d25  mov     rax, [rsp+280h+hObject]
0x140004d2a  lea     rcx, ds:0[rax*4]
0x140004d32  test    rcx, rcx
0x140004d35  jz      short loc_140004D45
0x140004d37  mov     [r15], rcx
0x140004d3a  mov     eax, [rcx]
0x140004d3c  inc     eax
0x140004d3e  mov     [rcx], eax
0x140004d40  jmp     loc_140004EA5
0x140004d45  mov     rdx, r14; dwBytes
0x140004d48  mov     qword ptr [r15], 0
0x140004d4f  mov     ecx, 8; dwFlags
0x140004d54  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004d59  mov     rsi, rax
0x140004d5c  test    rax, rax
0x140004d5f  jnz     short loc_140004D87
0x140004d61  mov     rcx, [rbp+188h]; this
0x140004d68  lea     r8, aWil; "wil"
0x140004d6f  mov     r14d, 8007000Eh
0x140004d75  mov     edx, 14Bh; void *
0x140004d7a  mov     r9d, r14d; char *
0x140004d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004d82  jmp     loc_140004E1A
0x140004d87  xorps   xmm0, xmm0
0x140004d8a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004d90  test    sil, 3
0x140004d94  jnz     loc_140004F38
0x140004d9a  mov     r9, rsi
0x140004d9d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004da2  shr     r9, 2; unsigned __int64
0x140004da6  lea     rcx, [rsp+280h+hObject]; this
0x140004dab  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140004db0  mov     r14d, eax
0x140004db3  test    eax, eax
0x140004db5  jns     loc_140004E61
0x140004dbb  mov     rcx, [rbp+188h]; this
0x140004dc2  lea     r8, aWil; "wil"
0x140004dc9  mov     r9d, eax; char *
0x140004dcc  mov     edx, 14Eh; void *
0x140004dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004dd6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004ddb  test    rcx, rcx
0x140004dde  jz      short loc_140004DEE
0x140004de0  call    cs:__imp_CloseHandle
0x140004de6  test    eax, eax
0x140004de8  jz      loc_140004F3E
0x140004dee  mov     rcx, [rsp+280h+hObject]; hObject
0x140004df3  test    rcx, rcx
0x140004df6  jz      short loc_140004E06
0x140004df8  call    cs:__imp_CloseHandle
0x140004dfe  test    eax, eax
0x140004e00  jz      loc_140004F50
0x140004e06  call    cs:__imp_GetProcessHeap
0x140004e0c  mov     r8, rsi; lpMem
0x140004e0f  xor     edx, edx; dwFlags
0x140004e11  mov     rcx, rax; hHeap
0x140004e14  call    cs:__imp_HeapFree
0x140004e1a  mov     rcx, [rbp+188h]; this
0x140004e21  lea     r8, aWil; "wil"
0x140004e28  mov     r9d, r14d; char *
0x140004e2b  mov     edx, 137h; void *
0x140004e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e35  test    rdi, rdi
0x140004e38  jz      short loc_140004E4B
0x140004e3a  mov     rcx, rdi; hMutex
0x140004e3d  call    cs:__imp_ReleaseMutex
0x140004e43  test    eax, eax
0x140004e45  jz      loc_140004F62
0x140004e4b  mov     rcx, rbx; hObject
0x140004e4e  call    cs:__imp_CloseHandle
0x140004e54  test    eax, eax
0x140004e56  jz      loc_140004F74
0x140004e5c  mov     eax, r14d
0x140004e5f  jmp     short loc_140004ECF
0x140004e61  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004e66  xor     edx, edx; Val
0x140004e68  mov     dword ptr [rsi], 1
0x140004e6e  lea     rcx, [rsi+22h]; void *
0x140004e72  mov     [rsi+8], rbx
0x140004e76  movdqu  xmmword ptr [rsi+10h], xmm0
0x140004e7b  lea     r8d, [rdx+56h]; Size
0x140004e7f  call    memset_0
0x140004e84  xor     edx, edx; Val
0x140004e86  mov     word ptr [rsi+20h], 58h ; 'X'
0x140004e8c  lea     rcx, [rsi+28h]; void *
0x140004e90  mov     dword ptr [rsi+24h], 1
0x140004e97  lea     r8d, [rdx+50h]; Size
0x140004e9b  call    memset_0
0x140004ea0  xor     ebx, ebx
0x140004ea2  mov     [r15], rsi
0x140004ea5  test    rdi, rdi
0x140004ea8  jz      short loc_140004EBB
0x140004eaa  mov     rcx, rdi; hMutex
0x140004ead  call    cs:__imp_ReleaseMutex
0x140004eb3  test    eax, eax
0x140004eb5  jz      loc_140004F86
0x140004ebb  test    rbx, rbx
0x140004ebe  jz      short loc_140004ECD
0x140004ec0  mov     rcx, rbx; hObject
0x140004ec3  call    cs:__imp_CloseHandle
0x140004ec9  test    eax, eax
0x140004ecb  jz      short loc_140004EF5
0x140004ecd  xor     eax, eax
0x140004ecf  mov     rcx, [rbp+180h+var_30]
0x140004ed6  xor     rcx, rsp; StackCookie
0x140004ed9  call    __security_check_cookie
0x140004ede  mov     rbx, [rsp+280h+arg_10]
0x140004ee6  add     rsp, 260h
0x140004eed  pop     r15
0x140004eef  pop     r14
0x140004ef1  pop     rdi
0x140004ef2  pop     rsi
0x140004ef3  pop     rbp
0x140004ef4  retn
0x140004ef5  mov     rcx, [rbp+188h]; this
0x140004efc  mov     edx, 0A0Bh; void *
0x140004f01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f07  mov     rcx, [rbp+188h]; this
0x140004f0e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004f14  mov     rcx, [rbp+188h]; this
0x140004f1b  mov     edx, 0A15h; void *
0x140004f20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f26  mov     rcx, [rbp+188h]; this
0x140004f2d  mov     edx, 0A0Bh; void *
0x140004f32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004f3e  mov     rcx, [rbp+188h]; this
0x140004f45  mov     edx, 0A0Bh; void *
0x140004f4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f50  mov     rcx, [rbp+188h]; this
0x140004f57  mov     edx, 0A0Bh; void *
0x140004f5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f62  mov     rcx, [rbp+188h]; this
0x140004f69  mov     edx, 0A15h; void *
0x140004f6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f74  mov     rcx, [rbp+188h]; this
0x140004f7b  mov     edx, 0A0Bh; void *
0x140004f80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f86  mov     rcx, [rbp+188h]; this
0x140004f8d  mov     edx, 0A15h; void *
0x140004f92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
