# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004d50`
- end: `0x180005118`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800064b4`

## callees

- `0x180004d50`
- `0x1800051b0`
- `0x180005ab8`
- `0x180006218`
- `0x180006da8`
- `0x1800076a4`
- `0x180007f48`
- `0x18000813c`
- `0x18000872c`
- `0x18000873c`
- `0x18003b96a`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004dc8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004dc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004de9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004de9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000502d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000502d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005043`

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
0x180004d50  mov     [rsp-8+arg_10], rbx
0x180004d55  push    rbp
0x180004d56  push    rsi
0x180004d57  push    rdi
0x180004d58  push    r14
0x180004d5a  push    r15
0x180004d5c  lea     rbp, [rsp-160h]
0x180004d64  sub     rsp, 260h
0x180004d6b  mov     rax, cs:__security_cookie
0x180004d72  xor     rax, rsp
0x180004d75  mov     [rbp+180h+var_30], rax
0x180004d7c  mov     r15, rdx
0x180004d7f  mov     qword ptr [rdx], 0
0x180004d86  mov     rbx, rcx
0x180004d89  call    cs:__imp_GetCurrentProcessId
0x180004d8f  mov     r14d, 78h ; 'x'
0x180004d95  mov     [rsp+280h+var_258], rbx
0x180004d9a  mov     r9d, eax
0x180004d9d  mov     [rsp+280h+var_260], r14d; int
0x180004da2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004da9  mov     edx, 104h; unsigned __int64
0x180004dae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004db3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004db8  mov     r9d, 1F0001h; dwDesiredAccess
0x180004dbe  lea     rdx, [rsp+280h+Name]; lpName
0x180004dc3  xor     r8d, r8d; dwFlags
0x180004dc6  xor     ecx, ecx; lpMutexAttributes
0x180004dc8  call    cs:__imp_CreateMutexExW
0x180004dce  mov     rbx, rax
0x180004dd1  test    rax, rax
0x180004dd4  jnz     short loc_180004DE0
0x180004dd6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ddb  jmp     loc_18000504F
0x180004de0  xor     r8d, r8d; bAlertable
0x180004de3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004de6  mov     rcx, rbx; hHandle
0x180004de9  call    cs:__imp_WaitForSingleObjectEx
0x180004def  cmp     eax, 102h
0x180004df4  jz      short loc_180004E06
0x180004df6  test    eax, 0FFFFFF7Fh
0x180004dfb  jnz     loc_180005087
0x180004e01  mov     rdi, rbx
0x180004e04  jmp     short loc_180004E08
0x180004e06  xor     edi, edi
0x180004e08  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004e0d  mov     [rsp+280h+hObject], 0
0x180004e16  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004e1b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004e20  mov     esi, eax
0x180004e22  test    eax, eax
0x180004e24  jns     short loc_180004EA5
0x180004e26  mov     rcx, [rbp+188h]; this
0x180004e2d  lea     r8, aWil; "wil"
0x180004e34  mov     r9d, eax; char *
0x180004e37  mov     edx, 66h ; 'f'; void *
0x180004e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e41  mov     rcx, [rbp+188h]; this
0x180004e48  lea     r8, aWil; "wil"
0x180004e4f  mov     r9d, esi; char *
0x180004e52  mov     edx, 6Fh ; 'o'; void *
0x180004e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e5c  mov     rcx, [rbp+188h]; this
0x180004e63  lea     r8, aWil; "wil"
0x180004e6a  mov     r9d, esi; char *
0x180004e6d  mov     edx, 12Eh; void *
0x180004e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e77  test    rdi, rdi
0x180004e7a  jz      short loc_180004E8D
0x180004e7c  mov     rcx, rdi; hMutex
0x180004e7f  call    cs:__imp_ReleaseMutex
0x180004e85  test    eax, eax
0x180004e87  jz      loc_180005094
0x180004e8d  mov     rcx, rbx; hObject
0x180004e90  call    cs:__imp_CloseHandle
0x180004e96  test    eax, eax
0x180004e98  jz      loc_1800050A6
0x180004e9e  mov     eax, esi
0x180004ea0  jmp     loc_18000504F
0x180004ea5  mov     rax, [rsp+280h+hObject]
0x180004eaa  lea     rcx, ds:0[rax*4]
0x180004eb2  test    rcx, rcx
0x180004eb5  jz      short loc_180004EC5
0x180004eb7  mov     [r15], rcx
0x180004eba  mov     eax, [rcx]
0x180004ebc  inc     eax
0x180004ebe  mov     [rcx], eax
0x180004ec0  jmp     loc_180005025
0x180004ec5  mov     rdx, r14; dwBytes
0x180004ec8  mov     qword ptr [r15], 0
0x180004ecf  mov     ecx, 8; dwFlags
0x180004ed4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ed9  mov     rsi, rax
0x180004edc  test    rax, rax
0x180004edf  jnz     short loc_180004F07
0x180004ee1  mov     rcx, [rbp+188h]; this
0x180004ee8  lea     r8, aWil; "wil"
0x180004eef  mov     r14d, 8007000Eh
0x180004ef5  mov     edx, 14Bh; void *
0x180004efa  mov     r9d, r14d; char *
0x180004efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f02  jmp     loc_180004F9A
0x180004f07  xorps   xmm0, xmm0
0x180004f0a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004f10  test    sil, 3
0x180004f14  jnz     loc_1800050B8
0x180004f1a  mov     r9, rsi
0x180004f1d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004f22  shr     r9, 2; unsigned __int64
0x180004f26  lea     rcx, [rsp+280h+hObject]; this
0x180004f2b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004f30  mov     r14d, eax
0x180004f33  test    eax, eax
0x180004f35  jns     loc_180004FE1
0x180004f3b  mov     rcx, [rbp+188h]; this
0x180004f42  lea     r8, aWil; "wil"
0x180004f49  mov     r9d, eax; char *
0x180004f4c  mov     edx, 14Eh; void *
0x180004f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f56  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004f5b  test    rcx, rcx
0x180004f5e  jz      short loc_180004F6E
0x180004f60  call    cs:__imp_CloseHandle
0x180004f66  test    eax, eax
0x180004f68  jz      loc_1800050BE
0x180004f6e  mov     rcx, [rsp+280h+hObject]; hObject
0x180004f73  test    rcx, rcx
0x180004f76  jz      short loc_180004F86
0x180004f78  call    cs:__imp_CloseHandle
0x180004f7e  test    eax, eax
0x180004f80  jz      loc_1800050D0
0x180004f86  call    cs:__imp_GetProcessHeap
0x180004f8c  mov     r8, rsi; lpMem
0x180004f8f  xor     edx, edx; dwFlags
0x180004f91  mov     rcx, rax; hHeap
0x180004f94  call    cs:__imp_HeapFree
0x180004f9a  mov     rcx, [rbp+188h]; this
0x180004fa1  lea     r8, aWil; "wil"
0x180004fa8  mov     r9d, r14d; char *
0x180004fab  mov     edx, 137h; void *
0x180004fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fb5  test    rdi, rdi
0x180004fb8  jz      short loc_180004FCB
0x180004fba  mov     rcx, rdi; hMutex
0x180004fbd  call    cs:__imp_ReleaseMutex
0x180004fc3  test    eax, eax
0x180004fc5  jz      loc_1800050E2
0x180004fcb  mov     rcx, rbx; hObject
0x180004fce  call    cs:__imp_CloseHandle
0x180004fd4  test    eax, eax
0x180004fd6  jz      loc_1800050F4
0x180004fdc  mov     eax, r14d
0x180004fdf  jmp     short loc_18000504F
0x180004fe1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004fe6  xor     edx, edx; Val
0x180004fe8  mov     dword ptr [rsi], 1
0x180004fee  lea     rcx, [rsi+22h]; void *
0x180004ff2  mov     [rsi+8], rbx
0x180004ff6  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004ffb  lea     r8d, [rdx+56h]; Size
0x180004fff  call    memset_0
0x180005004  xor     edx, edx; Val
0x180005006  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000500c  lea     rcx, [rsi+28h]; void *
0x180005010  mov     dword ptr [rsi+24h], 1
0x180005017  lea     r8d, [rdx+50h]; Size
0x18000501b  call    memset_0
0x180005020  xor     ebx, ebx
0x180005022  mov     [r15], rsi
0x180005025  test    rdi, rdi
0x180005028  jz      short loc_18000503B
0x18000502a  mov     rcx, rdi; hMutex
0x18000502d  call    cs:__imp_ReleaseMutex
0x180005033  test    eax, eax
0x180005035  jz      loc_180005106
0x18000503b  test    rbx, rbx
0x18000503e  jz      short loc_18000504D
0x180005040  mov     rcx, rbx; hObject
0x180005043  call    cs:__imp_CloseHandle
0x180005049  test    eax, eax
0x18000504b  jz      short loc_180005075
0x18000504d  xor     eax, eax
0x18000504f  mov     rcx, [rbp+180h+var_30]
0x180005056  xor     rcx, rsp; StackCookie
0x180005059  call    __security_check_cookie
0x18000505e  mov     rbx, [rsp+280h+arg_10]
0x180005066  add     rsp, 260h
0x18000506d  pop     r15
0x18000506f  pop     r14
0x180005071  pop     rdi
0x180005072  pop     rsi
0x180005073  pop     rbp
0x180005074  retn
0x180005075  mov     rcx, [rbp+188h]; this
0x18000507c  mov     edx, 0A0Bh; void *
0x180005081  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005087  mov     rcx, [rbp+188h]; this
0x18000508e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005094  mov     rcx, [rbp+188h]; this
0x18000509b  mov     edx, 0A15h; void *
0x1800050a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050a6  mov     rcx, [rbp+188h]; this
0x1800050ad  mov     edx, 0A0Bh; void *
0x1800050b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800050be  mov     rcx, [rbp+188h]; this
0x1800050c5  mov     edx, 0A0Bh; void *
0x1800050ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050d0  mov     rcx, [rbp+188h]; this
0x1800050d7  mov     edx, 0A0Bh; void *
0x1800050dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050e2  mov     rcx, [rbp+188h]; this
0x1800050e9  mov     edx, 0A15h; void *
0x1800050ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050f4  mov     rcx, [rbp+188h]; this
0x1800050fb  mov     edx, 0A0Bh; void *
0x180005100  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005106  mov     rcx, [rbp+188h]; this
0x18000510d  mov     edx, 0A15h; void *
0x180005112  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
