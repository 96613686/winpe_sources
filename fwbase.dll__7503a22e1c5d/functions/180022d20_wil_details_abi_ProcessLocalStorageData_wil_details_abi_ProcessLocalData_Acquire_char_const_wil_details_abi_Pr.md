# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180022d20`
- end: `0x1800230f6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180024b20`

## callees

- `0x18001e1d0`
- `0x1800213ac`
- `0x180022d20`
- `0x1800234f0`
- `0x180023a70`
- `0x180024870`
- `0x180025d20`
- `0x180027a50`
- `0x180028530`
- `0x180029310`
- `0x180029320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022d86`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180022d86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180022db1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180022db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180022ff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022d4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022d4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002300b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002300b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022f4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022f40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022f40`

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
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
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
  char *v26; // rdi
  unsigned int v27; // ebp
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
  int v45; // [rsp+20h] [rbp-258h]
  int v46; // [rsp+20h] [rbp-258h]
  int v47; // [rsp+20h] [rbp-258h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-248h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
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
  v26 = (char *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            pszDest,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *((_QWORD *)v26 + 1) = v6;
      *(_DWORD *)v26 = 1;
      v6 = 0;
      *((_OWORD *)v26 + 1) = v40;
      *(_OWORD *)(v26 + 34) = 0;
      *(_OWORD *)(v26 + 50) = 0;
      *(_OWORD *)(v26 + 66) = 0;
      *(_OWORD *)(v26 + 82) = 0;
      *(_OWORD *)(v26 + 98) = 0;
      *((_QWORD *)v26 + 14) = 0;
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      *(_OWORD *)(v26 + 40) = 0;
      *(_OWORD *)(v26 + 56) = 0;
      *(_OWORD *)(v26 + 72) = 0;
      *(_OWORD *)(v26 + 88) = 0;
      *(_OWORD *)(v26 + 104) = 0;
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
0x180022d20  push    rbx
0x180022d22  push    r14
0x180022d24  sub     rsp, 268h
0x180022d2b  mov     rax, cs:__security_cookie
0x180022d32  xor     rax, rsp
0x180022d35  mov     [rsp+278h+var_28], rax
0x180022d3d  mov     r14, rdx
0x180022d40  mov     qword ptr [rdx], 0
0x180022d47  mov     rbx, rcx
0x180022d4a  call    cs:__imp_GetCurrentProcessId
0x180022d50  mov     [rsp+278h+var_250], rbx
0x180022d55  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180022d5c  mov     r9d, eax
0x180022d5f  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x180022d67  mov     edx, 104h; cchDest
0x180022d6c  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180022d71  call    StringCchPrintfW
0x180022d76  mov     r9d, 1F0001h; dwDesiredAccess
0x180022d7c  lea     rdx, [rsp+278h+pszDest]; lpName
0x180022d81  xor     r8d, r8d; dwFlags
0x180022d84  xor     ecx, ecx; lpMutexAttributes
0x180022d86  call    cs:__imp_CreateMutexExW
0x180022d8c  mov     rbx, rax
0x180022d8f  test    rax, rax
0x180022d92  jnz     short loc_180022D9E
0x180022d94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022d99  jmp     loc_18002302F
0x180022d9e  xor     r8d, r8d; bAlertable
0x180022da1  mov     [rsp+278h+arg_18], rsi
0x180022da9  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180022dae  mov     rcx, rbx; hHandle
0x180022db1  call    cs:__imp_WaitForSingleObjectEx
0x180022db7  cmp     eax, 102h
0x180022dbc  jz      short loc_180022DCE
0x180022dbe  test    eax, 0FFFFFF7Fh
0x180022dc3  jnz     loc_18002305D
0x180022dc9  mov     rsi, rbx
0x180022dcc  jmp     short loc_180022DD0
0x180022dce  xor     esi, esi
0x180022dd0  lea     r8, [rsp+278h+hObject]; unsigned __int64 *
0x180022dd5  mov     [rsp+278h+var_18], rdi
0x180022ddd  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180022de2  mov     [rsp+278h+hObject], 0
0x180022deb  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180022df0  mov     edi, eax
0x180022df2  test    eax, eax
0x180022df4  jns     short loc_180022E63
0x180022df6  mov     rcx, [rsp+278h]; this
0x180022dfe  mov     r9d, eax; char *
0x180022e01  mov     edx, 66h ; 'f'; void *
0x180022e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e0b  mov     rcx, [rsp+278h]; this
0x180022e13  mov     r9d, edi; char *
0x180022e16  mov     edx, 6Fh ; 'o'; void *
0x180022e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e20  mov     rcx, [rsp+278h]; this
0x180022e28  mov     r9d, edi; char *
0x180022e2b  mov     edx, 12Eh; void *
0x180022e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e35  test    rsi, rsi
0x180022e38  jz      short loc_180022E4B
0x180022e3a  mov     rcx, rsi; hMutex
0x180022e3d  call    cs:__imp_ReleaseMutex
0x180022e43  test    eax, eax
0x180022e45  jz      loc_18002306B
0x180022e4b  mov     rcx, rbx; hObject
0x180022e4e  call    cs:__imp_CloseHandle
0x180022e54  test    eax, eax
0x180022e56  jz      loc_18002307E
0x180022e5c  mov     eax, edi
0x180022e5e  jmp     loc_18002301F
0x180022e63  mov     rax, [rsp+278h+hObject]
0x180022e68  mov     [rsp+278h+arg_10], rbp
0x180022e70  lea     rcx, ds:0[rax*4]
0x180022e78  test    rcx, rcx
0x180022e7b  jz      short loc_180022E8B
0x180022e7d  mov     [r14], rcx
0x180022e80  mov     eax, [rcx]
0x180022e82  inc     eax
0x180022e84  mov     [rcx], eax
0x180022e86  jmp     loc_180022FED
0x180022e8b  mov     edx, 78h ; 'x'; dwBytes
0x180022e90  mov     qword ptr [r14], 0
0x180022e97  mov     ecx, 8; dwFlags
0x180022e9c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180022ea1  mov     rdi, rax
0x180022ea4  test    rax, rax
0x180022ea7  jnz     short loc_180022EC8
0x180022ea9  mov     rcx, [rsp+278h]; this
0x180022eb1  mov     ebp, 8007000Eh
0x180022eb6  mov     r9d, ebp; char *
0x180022eb9  mov     edx, 14Bh; void *
0x180022ebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ec3  jmp     loc_180022F54
0x180022ec8  xorps   xmm0, xmm0
0x180022ecb  movdqu  xmmword ptr [rsp+278h+hObject], xmm0
0x180022ed1  test    dil, 3
0x180022ed5  jnz     loc_180023091
0x180022edb  mov     r9, rdi
0x180022ede  lea     rdx, [rsp+278h+pszDest]; unsigned __int16 *
0x180022ee3  shr     r9, 2; unsigned __int64
0x180022ee7  lea     rcx, [rsp+278h+hObject]; this
0x180022eec  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180022ef1  mov     ebp, eax
0x180022ef3  test    eax, eax
0x180022ef5  jns     loc_180022F97
0x180022efb  mov     rcx, [rsp+278h]; this
0x180022f03  mov     r9d, eax; char *
0x180022f06  mov     edx, 14Eh; void *
0x180022f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f10  mov     rcx, [rsp+278h+hObject+8]; hObject
0x180022f15  test    rcx, rcx
0x180022f18  jz      short loc_180022F28
0x180022f1a  call    cs:__imp_CloseHandle
0x180022f20  test    eax, eax
0x180022f22  jz      loc_180023097
0x180022f28  mov     rcx, [rsp+278h+hObject]; hObject
0x180022f2d  test    rcx, rcx
0x180022f30  jz      short loc_180022F40
0x180022f32  call    cs:__imp_CloseHandle
0x180022f38  test    eax, eax
0x180022f3a  jz      loc_1800230AA
0x180022f40  call    cs:__imp_GetProcessHeap
0x180022f46  mov     r8, rdi; lpMem
0x180022f49  xor     edx, edx; dwFlags
0x180022f4b  mov     rcx, rax; hHeap
0x180022f4e  call    cs:__imp_HeapFree
0x180022f54  mov     rcx, [rsp+278h]; this
0x180022f5c  mov     r9d, ebp; char *
0x180022f5f  mov     edx, 137h; void *
0x180022f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f69  test    rsi, rsi
0x180022f6c  jz      short loc_180022F7F
0x180022f6e  mov     rcx, rsi; hMutex
0x180022f71  call    cs:__imp_ReleaseMutex
0x180022f77  test    eax, eax
0x180022f79  jz      loc_1800230BD
0x180022f7f  mov     rcx, rbx; hObject
0x180022f82  call    cs:__imp_CloseHandle
0x180022f88  test    eax, eax
0x180022f8a  jz      loc_1800230D0
0x180022f90  mov     eax, ebp
0x180022f92  jmp     loc_180023017
0x180022f97  movups  xmm0, xmmword ptr [rsp+278h+hObject]
0x180022f9c  mov     [rdi+8], rbx
0x180022fa0  xor     eax, eax
0x180022fa2  mov     dword ptr [rdi], 1
0x180022fa8  xor     ebx, ebx
0x180022faa  movups  xmmword ptr [rdi+10h], xmm0
0x180022fae  xorps   xmm0, xmm0
0x180022fb1  movups  xmmword ptr [rdi+22h], xmm0
0x180022fb5  movups  xmmword ptr [rdi+32h], xmm0
0x180022fb9  movups  xmmword ptr [rdi+42h], xmm0
0x180022fbd  movups  xmmword ptr [rdi+52h], xmm0
0x180022fc1  movups  xmmword ptr [rdi+62h], xmm0
0x180022fc5  mov     [rdi+70h], rax
0x180022fc9  mov     word ptr [rdi+20h], 58h ; 'X'
0x180022fcf  mov     dword ptr [rdi+24h], 1
0x180022fd6  movups  xmmword ptr [rdi+28h], xmm0
0x180022fda  movups  xmmword ptr [rdi+38h], xmm0
0x180022fde  movups  xmmword ptr [rdi+48h], xmm0
0x180022fe2  movups  xmmword ptr [rdi+58h], xmm0
0x180022fe6  movups  xmmword ptr [rdi+68h], xmm0
0x180022fea  mov     [r14], rdi
0x180022fed  test    rsi, rsi
0x180022ff0  jz      short loc_180023003
0x180022ff2  mov     rcx, rsi; hMutex
0x180022ff5  call    cs:__imp_ReleaseMutex
0x180022ffb  test    eax, eax
0x180022ffd  jz      loc_1800230E3
0x180023003  test    rbx, rbx
0x180023006  jz      short loc_180023015
0x180023008  mov     rcx, rbx; hObject
0x18002300b  call    cs:__imp_CloseHandle
0x180023011  test    eax, eax
0x180023013  jz      short loc_18002304A
0x180023015  xor     eax, eax
0x180023017  mov     rbp, [rsp+278h+arg_10]
0x18002301f  mov     rdi, [rsp+278h+var_18]
0x180023027  mov     rsi, [rsp+278h+arg_18]
0x18002302f  mov     rcx, [rsp+278h+var_28]
0x180023037  xor     rcx, rsp; StackCookie
0x18002303a  call    __security_check_cookie
0x18002303f  add     rsp, 268h
0x180023046  pop     r14
0x180023048  pop     rbx
0x180023049  retn
0x18002304a  mov     rcx, [rsp+278h]; this
0x180023052  mov     edx, 0A0Bh; void *
0x180023057  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002305d  mov     rcx, [rsp+278h]; this
0x180023065  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002306b  mov     rcx, [rsp+278h]; this
0x180023073  mov     edx, 0A15h; void *
0x180023078  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002307e  mov     rcx, [rsp+278h]; this
0x180023086  mov     edx, 0A0Bh; void *
0x18002308b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023091  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023097  mov     rcx, [rsp+278h]; this
0x18002309f  mov     edx, 0A0Bh; void *
0x1800230a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800230aa  mov     rcx, [rsp+278h]; this
0x1800230b2  mov     edx, 0A0Bh; void *
0x1800230b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800230bd  mov     rcx, [rsp+278h]; this
0x1800230c5  mov     edx, 0A15h; void *
0x1800230ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800230d0  mov     rcx, [rsp+278h]; this
0x1800230d8  mov     edx, 0A0Bh; void *
0x1800230dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800230e3  mov     rcx, [rsp+278h]; this
0x1800230eb  mov     edx, 0A15h; void *
0x1800230f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
