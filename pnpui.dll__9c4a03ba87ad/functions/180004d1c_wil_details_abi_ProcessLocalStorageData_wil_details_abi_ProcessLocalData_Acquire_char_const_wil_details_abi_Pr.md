# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004d1c`
- end: `0x1800050ba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006bf0`

## callees

- `0x180003614`
- `0x180004d1c`
- `0x1800056f4`
- `0x180005c30`
- `0x18000698c`
- `0x180008038`
- `0x180009554`
- `0x180009cc0`
- `0x18000a56c`
- `0x18000a57c`
- `0x18000ccde`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d94`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004db5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004db5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004fcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004fcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fe5`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
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
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
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
0x180004d1c  mov     [rsp-8+arg_10], rbx
0x180004d21  push    rbp
0x180004d22  push    rsi
0x180004d23  push    rdi
0x180004d24  push    r14
0x180004d26  push    r15
0x180004d28  lea     rbp, [rsp-160h]
0x180004d30  sub     rsp, 260h
0x180004d37  mov     rax, cs:__security_cookie
0x180004d3e  xor     rax, rsp
0x180004d41  mov     [rbp+180h+var_30], rax
0x180004d48  mov     r15, rdx
0x180004d4b  mov     qword ptr [rdx], 0
0x180004d52  mov     rbx, rcx
0x180004d55  call    cs:__imp_GetCurrentProcessId
0x180004d5b  mov     r14d, 78h ; 'x'
0x180004d61  mov     [rsp+280h+var_258], rbx
0x180004d66  mov     r9d, eax
0x180004d69  mov     [rsp+280h+var_260], r14d; int
0x180004d6e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d75  mov     edx, 104h; unsigned __int64
0x180004d7a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004d7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d84  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d8a  lea     rdx, [rsp+280h+Name]; lpName
0x180004d8f  xor     r8d, r8d; dwFlags
0x180004d92  xor     ecx, ecx; lpMutexAttributes
0x180004d94  call    cs:__imp_CreateMutexExW
0x180004d9a  mov     rbx, rax
0x180004d9d  test    rax, rax
0x180004da0  jnz     short loc_180004DAC
0x180004da2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004da7  jmp     loc_180004FF1
0x180004dac  xor     r8d, r8d; bAlertable
0x180004daf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004db2  mov     rcx, rbx; hHandle
0x180004db5  call    cs:__imp_WaitForSingleObjectEx
0x180004dbb  cmp     eax, 102h
0x180004dc0  jz      short loc_180004DD2
0x180004dc2  test    eax, 0FFFFFF7Fh
0x180004dc7  jnz     loc_180005029
0x180004dcd  mov     rdi, rbx
0x180004dd0  jmp     short loc_180004DD4
0x180004dd2  xor     edi, edi
0x180004dd4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004dd9  mov     [rsp+280h+hObject], 0
0x180004de2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004de7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004dec  mov     esi, eax
0x180004dee  test    eax, eax
0x180004df0  jns     short loc_180004E5C
0x180004df2  mov     rcx, [rbp+188h]; this
0x180004df9  mov     r9d, eax; char *
0x180004dfc  mov     edx, 66h ; 'f'; void *
0x180004e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e06  mov     rcx, [rbp+188h]; this
0x180004e0d  mov     r9d, esi; char *
0x180004e10  mov     edx, 6Fh ; 'o'; void *
0x180004e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e1a  mov     rcx, [rbp+188h]; this
0x180004e21  mov     r9d, esi; char *
0x180004e24  mov     edx, 12Eh; void *
0x180004e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e2e  test    rdi, rdi
0x180004e31  jz      short loc_180004E44
0x180004e33  mov     rcx, rdi; hMutex
0x180004e36  call    cs:__imp_ReleaseMutex
0x180004e3c  test    eax, eax
0x180004e3e  jz      loc_180005036
0x180004e44  mov     rcx, rbx; hObject
0x180004e47  call    cs:__imp_CloseHandle
0x180004e4d  test    eax, eax
0x180004e4f  jz      loc_180005048
0x180004e55  mov     eax, esi
0x180004e57  jmp     loc_180004FF1
0x180004e5c  mov     rax, [rsp+280h+hObject]
0x180004e61  lea     rcx, ds:0[rax*4]
0x180004e69  test    rcx, rcx
0x180004e6c  jz      short loc_180004E7C
0x180004e6e  mov     [r15], rcx
0x180004e71  mov     eax, [rcx]
0x180004e73  inc     eax
0x180004e75  mov     [rcx], eax
0x180004e77  jmp     loc_180004FC7
0x180004e7c  mov     rdx, r14; dwBytes
0x180004e7f  mov     qword ptr [r15], 0
0x180004e86  mov     ecx, 8; dwFlags
0x180004e8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e90  mov     rsi, rax
0x180004e93  test    rax, rax
0x180004e96  jnz     short loc_180004EB7
0x180004e98  mov     rcx, [rbp+188h]; this
0x180004e9f  mov     r14d, 8007000Eh
0x180004ea5  mov     r9d, r14d; char *
0x180004ea8  mov     edx, 14Bh; void *
0x180004ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004eb2  jmp     loc_180004F43
0x180004eb7  xorps   xmm0, xmm0
0x180004eba  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004ec0  test    sil, 3
0x180004ec4  jnz     loc_18000505A
0x180004eca  mov     r9, rsi
0x180004ecd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004ed2  shr     r9, 2; unsigned __int64
0x180004ed6  lea     rcx, [rsp+280h+hObject]; this
0x180004edb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004ee0  mov     r14d, eax
0x180004ee3  test    eax, eax
0x180004ee5  jns     loc_180004F83
0x180004eeb  mov     rcx, [rbp+188h]; this
0x180004ef2  mov     r9d, eax; char *
0x180004ef5  mov     edx, 14Eh; void *
0x180004efa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004eff  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004f04  test    rcx, rcx
0x180004f07  jz      short loc_180004F17
0x180004f09  call    cs:__imp_CloseHandle
0x180004f0f  test    eax, eax
0x180004f11  jz      loc_180005060
0x180004f17  mov     rcx, [rsp+280h+hObject]; hObject
0x180004f1c  test    rcx, rcx
0x180004f1f  jz      short loc_180004F2F
0x180004f21  call    cs:__imp_CloseHandle
0x180004f27  test    eax, eax
0x180004f29  jz      loc_180005072
0x180004f2f  call    cs:__imp_GetProcessHeap
0x180004f35  mov     r8, rsi; lpMem
0x180004f38  xor     edx, edx; dwFlags
0x180004f3a  mov     rcx, rax; hHeap
0x180004f3d  call    cs:__imp_HeapFree
0x180004f43  mov     rcx, [rbp+188h]; this
0x180004f4a  mov     r9d, r14d; char *
0x180004f4d  mov     edx, 137h; void *
0x180004f52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f57  test    rdi, rdi
0x180004f5a  jz      short loc_180004F6D
0x180004f5c  mov     rcx, rdi; hMutex
0x180004f5f  call    cs:__imp_ReleaseMutex
0x180004f65  test    eax, eax
0x180004f67  jz      loc_180005084
0x180004f6d  mov     rcx, rbx; hObject
0x180004f70  call    cs:__imp_CloseHandle
0x180004f76  test    eax, eax
0x180004f78  jz      loc_180005096
0x180004f7e  mov     eax, r14d
0x180004f81  jmp     short loc_180004FF1
0x180004f83  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004f88  xor     edx, edx; Val
0x180004f8a  mov     dword ptr [rsi], 1
0x180004f90  lea     rcx, [rsi+22h]; void *
0x180004f94  mov     [rsi+8], rbx
0x180004f98  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004f9d  lea     r8d, [rdx+56h]; Size
0x180004fa1  call    memset_0
0x180004fa6  xor     edx, edx; Val
0x180004fa8  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004fae  lea     rcx, [rsi+28h]; void *
0x180004fb2  mov     dword ptr [rsi+24h], 1
0x180004fb9  lea     r8d, [rdx+50h]; Size
0x180004fbd  call    memset_0
0x180004fc2  xor     ebx, ebx
0x180004fc4  mov     [r15], rsi
0x180004fc7  test    rdi, rdi
0x180004fca  jz      short loc_180004FDD
0x180004fcc  mov     rcx, rdi; hMutex
0x180004fcf  call    cs:__imp_ReleaseMutex
0x180004fd5  test    eax, eax
0x180004fd7  jz      loc_1800050A8
0x180004fdd  test    rbx, rbx
0x180004fe0  jz      short loc_180004FEF
0x180004fe2  mov     rcx, rbx; hObject
0x180004fe5  call    cs:__imp_CloseHandle
0x180004feb  test    eax, eax
0x180004fed  jz      short loc_180005017
0x180004fef  xor     eax, eax
0x180004ff1  mov     rcx, [rbp+180h+var_30]
0x180004ff8  xor     rcx, rsp; StackCookie
0x180004ffb  call    __security_check_cookie
0x180005000  mov     rbx, [rsp+280h+arg_10]
0x180005008  add     rsp, 260h
0x18000500f  pop     r15
0x180005011  pop     r14
0x180005013  pop     rdi
0x180005014  pop     rsi
0x180005015  pop     rbp
0x180005016  retn
0x180005017  mov     rcx, [rbp+188h]; this
0x18000501e  mov     edx, 0A0Bh; void *
0x180005023  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005029  mov     rcx, [rbp+188h]; this
0x180005030  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005036  mov     rcx, [rbp+188h]; this
0x18000503d  mov     edx, 0A15h; void *
0x180005042  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005048  mov     rcx, [rbp+188h]; this
0x18000504f  mov     edx, 0A0Bh; void *
0x180005054  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000505a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005060  mov     rcx, [rbp+188h]; this
0x180005067  mov     edx, 0A0Bh; void *
0x18000506c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005072  mov     rcx, [rbp+188h]; this
0x180005079  mov     edx, 0A0Bh; void *
0x18000507e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005084  mov     rcx, [rbp+188h]; this
0x18000508b  mov     edx, 0A15h; void *
0x180005090  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005096  mov     rcx, [rbp+188h]; this
0x18000509d  mov     edx, 0A0Bh; void *
0x1800050a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050a8  mov     rcx, [rbp+188h]; this
0x1800050af  mov     edx, 0A15h; void *
0x1800050b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
