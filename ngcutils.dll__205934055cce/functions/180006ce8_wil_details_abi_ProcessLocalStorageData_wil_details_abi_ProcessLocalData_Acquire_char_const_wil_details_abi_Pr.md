# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006ce8`
- end: `0x1800070bc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800085f0`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x180006ce8`
- `0x1800074c8`
- `0x180007a5c`
- `0x180008388`
- `0x180008e04`
- `0x18000a5b4`
- `0x18000b0c8`
- `0x18000b54c`
- `0x18000be1c`
- `0x18000be2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006d60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006fc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006fc5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d81`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006d21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006d21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fdb`

## string_xrefs

- `0x180007026`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x180006ce8  mov     [rsp-8+arg_10], rbx
0x180006ced  push    rbp
0x180006cee  push    rsi
0x180006cef  push    rdi
0x180006cf0  push    r14
0x180006cf2  push    r15
0x180006cf4  lea     rbp, [rsp-160h]
0x180006cfc  sub     rsp, 260h
0x180006d03  mov     rax, cs:__security_cookie
0x180006d0a  xor     rax, rsp
0x180006d0d  mov     [rbp+180h+var_30], rax
0x180006d14  mov     r15, rdx
0x180006d17  mov     qword ptr [rdx], 0
0x180006d1e  mov     rbx, rcx
0x180006d21  call    cs:__imp_GetCurrentProcessId
0x180006d27  mov     r14d, 78h ; 'x'
0x180006d2d  mov     [rsp+280h+var_258], rbx
0x180006d32  mov     r9d, eax
0x180006d35  mov     [rsp+280h+var_260], r14d; int
0x180006d3a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006d41  mov     edx, 104h; unsigned __int64
0x180006d46  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006d4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d50  mov     r9d, 1F0001h; dwDesiredAccess
0x180006d56  lea     rdx, [rsp+280h+Name]; lpName
0x180006d5b  xor     r8d, r8d; dwFlags
0x180006d5e  xor     ecx, ecx; lpMutexAttributes
0x180006d60  call    cs:__imp_CreateMutexExW
0x180006d66  mov     rbx, rax
0x180006d69  test    rax, rax
0x180006d6c  jnz     short loc_180006D78
0x180006d6e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006d73  jmp     loc_180006FE7
0x180006d78  xor     r8d, r8d; bAlertable
0x180006d7b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006d7e  mov     rcx, rbx; hHandle
0x180006d81  call    cs:__imp_WaitForSingleObjectEx
0x180006d87  cmp     eax, 102h
0x180006d8c  jz      short loc_180006D9E
0x180006d8e  test    eax, 0FFFFFF7Fh
0x180006d93  jnz     loc_18000701F
0x180006d99  mov     rdi, rbx
0x180006d9c  jmp     short loc_180006DA0
0x180006d9e  xor     edi, edi
0x180006da0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006da5  mov     [rsp+280h+hObject], 0
0x180006dae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006db3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006db8  mov     esi, eax
0x180006dba  test    eax, eax
0x180006dbc  jns     short loc_180006E3D
0x180006dbe  mov     rcx, [rbp+188h]; this
0x180006dc5  lea     r8, aWil; "wil"
0x180006dcc  mov     r9d, eax; char *
0x180006dcf  mov     edx, 66h ; 'f'; void *
0x180006dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dd9  mov     rcx, [rbp+188h]; this
0x180006de0  lea     r8, aWil; "wil"
0x180006de7  mov     r9d, esi; char *
0x180006dea  mov     edx, 6Fh ; 'o'; void *
0x180006def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006df4  mov     rcx, [rbp+188h]; this
0x180006dfb  lea     r8, aWil; "wil"
0x180006e02  mov     r9d, esi; char *
0x180006e05  mov     edx, 12Eh; void *
0x180006e0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e0f  test    rdi, rdi
0x180006e12  jz      short loc_180006E25
0x180006e14  mov     rcx, rdi; hMutex
0x180006e17  call    cs:__imp_ReleaseMutex
0x180006e1d  test    eax, eax
0x180006e1f  jz      loc_180007038
0x180006e25  mov     rcx, rbx; hObject
0x180006e28  call    cs:__imp_CloseHandle
0x180006e2e  test    eax, eax
0x180006e30  jz      loc_18000704A
0x180006e36  mov     eax, esi
0x180006e38  jmp     loc_180006FE7
0x180006e3d  mov     rax, [rsp+280h+hObject]
0x180006e42  lea     rcx, ds:0[rax*4]
0x180006e4a  test    rcx, rcx
0x180006e4d  jz      short loc_180006E5D
0x180006e4f  mov     [r15], rcx
0x180006e52  mov     eax, [rcx]
0x180006e54  inc     eax
0x180006e56  mov     [rcx], eax
0x180006e58  jmp     loc_180006FBD
0x180006e5d  mov     rdx, r14; dwBytes
0x180006e60  mov     qword ptr [r15], 0
0x180006e67  mov     ecx, 8; dwFlags
0x180006e6c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006e71  mov     rsi, rax
0x180006e74  test    rax, rax
0x180006e77  jnz     short loc_180006E9F
0x180006e79  mov     rcx, [rbp+188h]; this
0x180006e80  lea     r8, aWil; "wil"
0x180006e87  mov     r14d, 8007000Eh
0x180006e8d  mov     edx, 14Bh; void *
0x180006e92  mov     r9d, r14d; char *
0x180006e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e9a  jmp     loc_180006F32
0x180006e9f  xorps   xmm0, xmm0
0x180006ea2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006ea8  test    sil, 3
0x180006eac  jnz     loc_18000705C
0x180006eb2  mov     r9, rsi
0x180006eb5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006eba  shr     r9, 2; unsigned __int64
0x180006ebe  lea     rcx, [rsp+280h+hObject]; this
0x180006ec3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006ec8  mov     r14d, eax
0x180006ecb  test    eax, eax
0x180006ecd  jns     loc_180006F79
0x180006ed3  mov     rcx, [rbp+188h]; this
0x180006eda  lea     r8, aWil; "wil"
0x180006ee1  mov     r9d, eax; char *
0x180006ee4  mov     edx, 14Eh; void *
0x180006ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006eee  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006ef3  test    rcx, rcx
0x180006ef6  jz      short loc_180006F06
0x180006ef8  call    cs:__imp_CloseHandle
0x180006efe  test    eax, eax
0x180006f00  jz      loc_180007062
0x180006f06  mov     rcx, [rsp+280h+hObject]; hObject
0x180006f0b  test    rcx, rcx
0x180006f0e  jz      short loc_180006F1E
0x180006f10  call    cs:__imp_CloseHandle
0x180006f16  test    eax, eax
0x180006f18  jz      loc_180007074
0x180006f1e  call    cs:__imp_GetProcessHeap
0x180006f24  mov     r8, rsi; lpMem
0x180006f27  xor     edx, edx; dwFlags
0x180006f29  mov     rcx, rax; hHeap
0x180006f2c  call    cs:__imp_HeapFree
0x180006f32  mov     rcx, [rbp+188h]; this
0x180006f39  lea     r8, aWil; "wil"
0x180006f40  mov     r9d, r14d; char *
0x180006f43  mov     edx, 137h; void *
0x180006f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f4d  test    rdi, rdi
0x180006f50  jz      short loc_180006F63
0x180006f52  mov     rcx, rdi; hMutex
0x180006f55  call    cs:__imp_ReleaseMutex
0x180006f5b  test    eax, eax
0x180006f5d  jz      loc_180007086
0x180006f63  mov     rcx, rbx; hObject
0x180006f66  call    cs:__imp_CloseHandle
0x180006f6c  test    eax, eax
0x180006f6e  jz      loc_180007098
0x180006f74  mov     eax, r14d
0x180006f77  jmp     short loc_180006FE7
0x180006f79  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006f7e  xor     edx, edx; Val
0x180006f80  mov     dword ptr [rsi], 1
0x180006f86  lea     rcx, [rsi+22h]; void *
0x180006f8a  mov     [rsi+8], rbx
0x180006f8e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006f93  lea     r8d, [rdx+56h]; Size
0x180006f97  call    memset_0
0x180006f9c  xor     edx, edx; Val
0x180006f9e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006fa4  lea     rcx, [rsi+28h]; void *
0x180006fa8  mov     dword ptr [rsi+24h], 1
0x180006faf  lea     r8d, [rdx+50h]; Size
0x180006fb3  call    memset_0
0x180006fb8  xor     ebx, ebx
0x180006fba  mov     [r15], rsi
0x180006fbd  test    rdi, rdi
0x180006fc0  jz      short loc_180006FD3
0x180006fc2  mov     rcx, rdi; hMutex
0x180006fc5  call    cs:__imp_ReleaseMutex
0x180006fcb  test    eax, eax
0x180006fcd  jz      loc_1800070AA
0x180006fd3  test    rbx, rbx
0x180006fd6  jz      short loc_180006FE5
0x180006fd8  mov     rcx, rbx; hObject
0x180006fdb  call    cs:__imp_CloseHandle
0x180006fe1  test    eax, eax
0x180006fe3  jz      short loc_18000700D
0x180006fe5  xor     eax, eax
0x180006fe7  mov     rcx, [rbp+180h+var_30]
0x180006fee  xor     rcx, rsp; StackCookie
0x180006ff1  call    __security_check_cookie
0x180006ff6  mov     rbx, [rsp+280h+arg_10]
0x180006ffe  add     rsp, 260h
0x180007005  pop     r15
0x180007007  pop     r14
0x180007009  pop     rdi
0x18000700a  pop     rsi
0x18000700b  pop     rbp
0x18000700c  retn
0x18000700d  mov     rcx, [rbp+188h]; this
0x180007014  mov     edx, 0A0Bh; void *
0x180007019  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000701f  mov     rcx, [rbp+188h]; this
0x180007026  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000702d  mov     edx, 0E01h; void *
0x180007032  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180007038  mov     rcx, [rbp+188h]; this
0x18000703f  mov     edx, 0A15h; void *
0x180007044  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000704a  mov     rcx, [rbp+188h]; this
0x180007051  mov     edx, 0A0Bh; void *
0x180007056  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000705c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007062  mov     rcx, [rbp+188h]; this
0x180007069  mov     edx, 0A0Bh; void *
0x18000706e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007074  mov     rcx, [rbp+188h]; this
0x18000707b  mov     edx, 0A0Bh; void *
0x180007080  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007086  mov     rcx, [rbp+188h]; this
0x18000708d  mov     edx, 0A15h; void *
0x180007092  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007098  mov     rcx, [rbp+188h]; this
0x18000709f  mov     edx, 0A0Bh; void *
0x1800070a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800070aa  mov     rcx, [rbp+188h]; this
0x1800070b1  mov     edx, 0A15h; void *
0x1800070b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
