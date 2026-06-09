# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005c6c`
- end: `0x180006011`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000780c`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x1800057b8`
- `0x180005c6c`
- `0x1800065d8`
- `0x180006a98`
- `0x180007430`
- `0x18000889c`
- `0x18000a314`
- `0x18000b030`
- `0x18000b4dc`
- `0x18000bdac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005cea`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005cea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005d11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005d11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f43`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f5f`

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
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v42 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v42, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v42[0];
  v34 = v42[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v42[0] = 0;
  *((_QWORD *)v25 + 3) = v34;
  v42[1] = 0;
  memset_0((char *)v25 + 34, 0, 0x56u);
  *((_WORD *)v25 + 16) = 88;
  v25[9] = 1;
  memset_0(v25 + 10, 0, 0x50u);
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180005c6c  mov     [rsp-8+arg_10], rbx
0x180005c71  push    rbp
0x180005c72  push    rsi
0x180005c73  push    rdi
0x180005c74  push    r14
0x180005c76  push    r15
0x180005c78  lea     rbp, [rsp-160h]
0x180005c80  sub     rsp, 260h
0x180005c87  mov     rax, cs:__security_cookie
0x180005c8e  xor     rax, rsp
0x180005c91  mov     [rbp+180h+var_30], rax
0x180005c98  mov     r15, rdx
0x180005c9b  mov     qword ptr [rdx], 0
0x180005ca2  mov     rbx, rcx
0x180005ca5  call    cs:__imp_GetCurrentProcessId
0x180005cac  nop     dword ptr [rax+rax+00h]
0x180005cb1  mov     r14d, 78h ; 'x'
0x180005cb7  mov     [rsp+280h+var_258], rbx
0x180005cbc  mov     r9d, eax
0x180005cbf  mov     [rsp+280h+var_260], r14d; int
0x180005cc4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005ccb  mov     edx, 104h; unsigned __int64
0x180005cd0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005cd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005cda  mov     r9d, 1F0001h; dwDesiredAccess
0x180005ce0  lea     rdx, [rsp+280h+Name]; lpName
0x180005ce5  xor     r8d, r8d; dwFlags
0x180005ce8  xor     ecx, ecx; lpMutexAttributes
0x180005cea  call    cs:__imp_CreateMutexExW
0x180005cf1  nop     dword ptr [rax+rax+00h]
0x180005cf6  mov     rbx, rax
0x180005cf9  test    rax, rax
0x180005cfc  jnz     short loc_180005D08
0x180005cfe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005d03  jmp     loc_180005F71
0x180005d08  xor     r8d, r8d; bAlertable
0x180005d0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005d0e  mov     rcx, rbx; hHandle
0x180005d11  call    cs:__imp_WaitForSingleObjectEx
0x180005d18  nop     dword ptr [rax+rax+00h]
0x180005d1d  cmp     eax, 102h
0x180005d22  jz      short loc_180005D34
0x180005d24  test    eax, 0FFFFFF7Fh
0x180005d29  jnz     loc_180005FBC
0x180005d2f  mov     rdi, rbx
0x180005d32  jmp     short loc_180005D36
0x180005d34  xor     edi, edi
0x180005d36  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005d3b  mov     [rsp+280h+var_250], 0
0x180005d44  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d49  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005d4e  mov     esi, eax
0x180005d50  test    eax, eax
0x180005d52  jns     short loc_180005DCA
0x180005d54  mov     rcx, [rbp+188h]; this
0x180005d5b  mov     r9d, eax; char *
0x180005d5e  mov     edx, 66h ; 'f'; void *
0x180005d63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d68  mov     rcx, [rbp+188h]; this
0x180005d6f  mov     r9d, esi; char *
0x180005d72  mov     edx, 6Fh ; 'o'; void *
0x180005d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d7c  mov     rcx, [rbp+188h]; this
0x180005d83  mov     r9d, esi; char *
0x180005d86  mov     edx, 12Eh; void *
0x180005d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d90  test    rdi, rdi
0x180005d93  jz      short loc_180005DAC
0x180005d95  mov     rcx, rdi; hMutex
0x180005d98  call    cs:__imp_ReleaseMutex
0x180005d9f  nop     dword ptr [rax+rax+00h]
0x180005da4  test    eax, eax
0x180005da6  jz      loc_180005FC9
0x180005dac  mov     rcx, rbx; hObject
0x180005daf  call    cs:__imp_CloseHandle
0x180005db6  nop     dword ptr [rax+rax+00h]
0x180005dbb  test    eax, eax
0x180005dbd  jz      loc_180005FDB
0x180005dc3  mov     eax, esi
0x180005dc5  jmp     loc_180005F71
0x180005dca  mov     rax, [rsp+280h+var_250]
0x180005dcf  lea     rcx, ds:0[rax*4]
0x180005dd7  test    rcx, rcx
0x180005dda  jz      short loc_180005DEA
0x180005ddc  mov     [r15], rcx
0x180005ddf  mov     eax, [rcx]
0x180005de1  inc     eax
0x180005de3  mov     [rcx], eax
0x180005de5  jmp     loc_180005F3B
0x180005dea  mov     rdx, r14; dwBytes
0x180005ded  mov     qword ptr [r15], 0
0x180005df4  mov     ecx, 8; dwFlags
0x180005df9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005dfe  mov     r14, rax
0x180005e01  test    rax, rax
0x180005e04  jnz     short loc_180005E21
0x180005e06  mov     rcx, [rbp+188h]; this
0x180005e0d  mov     esi, 8007000Eh
0x180005e12  mov     r9d, esi; char *
0x180005e15  mov     edx, 14Bh; void *
0x180005e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e1f  jmp     short loc_180005E84
0x180005e21  xorps   xmm0, xmm0
0x180005e24  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005e29  mov     r8, r14; void *
0x180005e2c  lea     rcx, [rsp+280h+var_250]; this
0x180005e31  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005e37  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180005e3c  mov     esi, eax
0x180005e3e  test    eax, eax
0x180005e40  jns     loc_180005ED0
0x180005e46  mov     rcx, [rbp+188h]; this
0x180005e4d  mov     r9d, eax; char *
0x180005e50  mov     edx, 14Eh; void *
0x180005e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e5a  lea     rcx, [rsp+280h+var_250]; this
0x180005e5f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005e64  call    cs:__imp_GetProcessHeap
0x180005e6b  nop     dword ptr [rax+rax+00h]
0x180005e70  mov     r8, r14; lpMem
0x180005e73  xor     edx, edx; dwFlags
0x180005e75  mov     rcx, rax; hHeap
0x180005e78  call    cs:__imp_HeapFree
0x180005e7f  nop     dword ptr [rax+rax+00h]
0x180005e84  mov     rcx, [rbp+188h]; this
0x180005e8b  mov     r9d, esi; char *
0x180005e8e  mov     edx, 137h; void *
0x180005e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e98  test    rdi, rdi
0x180005e9b  jz      short loc_180005EB4
0x180005e9d  mov     rcx, rdi; hMutex
0x180005ea0  call    cs:__imp_ReleaseMutex
0x180005ea7  nop     dword ptr [rax+rax+00h]
0x180005eac  test    eax, eax
0x180005eae  jz      loc_180005FED
0x180005eb4  mov     rcx, rbx; hObject
0x180005eb7  call    cs:__imp_CloseHandle
0x180005ebe  nop     dword ptr [rax+rax+00h]
0x180005ec3  test    eax, eax
0x180005ec5  jz      loc_180005FAA
0x180005ecb  jmp     loc_180005DC3
0x180005ed0  mov     rax, [rsp+280h+var_250]
0x180005ed5  lea     rcx, [r14+22h]; void *
0x180005ed9  xor     edx, edx; Val
0x180005edb  mov     [r14+10h], rax
0x180005edf  mov     rax, [rsp+280h+var_250+8]
0x180005ee4  mov     dword ptr [r14], 1
0x180005eeb  mov     [r14+8], rbx
0x180005eef  lea     r8d, [rdx+56h]; Size
0x180005ef3  mov     [rsp+280h+var_250], 0
0x180005efc  mov     [r14+18h], rax
0x180005f00  mov     [rsp+280h+var_250+8], 0
0x180005f09  call    memset_0
0x180005f0e  xor     edx, edx; Val
0x180005f10  mov     word ptr [r14+20h], 58h ; 'X'
0x180005f17  lea     rcx, [r14+28h]; void *
0x180005f1b  mov     dword ptr [r14+24h], 1
0x180005f23  lea     r8d, [rdx+50h]; Size
0x180005f27  call    memset_0
0x180005f2c  lea     rcx, [rsp+280h+var_250]; this
0x180005f31  mov     [r15], r14
0x180005f34  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005f39  xor     ebx, ebx
0x180005f3b  test    rdi, rdi
0x180005f3e  jz      short loc_180005F57
0x180005f40  mov     rcx, rdi; hMutex
0x180005f43  call    cs:__imp_ReleaseMutex
0x180005f4a  nop     dword ptr [rax+rax+00h]
0x180005f4f  test    eax, eax
0x180005f51  jz      loc_180005FFF
0x180005f57  test    rbx, rbx
0x180005f5a  jz      short loc_180005F6F
0x180005f5c  mov     rcx, rbx; hObject
0x180005f5f  call    cs:__imp_CloseHandle
0x180005f66  nop     dword ptr [rax+rax+00h]
0x180005f6b  test    eax, eax
0x180005f6d  jz      short loc_180005F98
0x180005f6f  xor     eax, eax
0x180005f71  mov     rcx, [rbp+180h+var_30]
0x180005f78  xor     rcx, rsp; StackCookie
0x180005f7b  call    __security_check_cookie
0x180005f80  mov     rbx, [rsp+280h+arg_10]
0x180005f88  add     rsp, 260h
0x180005f8f  pop     r15
0x180005f91  pop     r14
0x180005f93  pop     rdi
0x180005f94  pop     rsi
0x180005f95  pop     rbp
0x180005f96  retn
0x180005f98  mov     rcx, [rbp+188h]; this
0x180005f9f  mov     edx, 0A0Bh; void *
0x180005fa4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005faa  mov     rcx, [rbp+188h]; this
0x180005fb1  mov     edx, 0A0Bh; void *
0x180005fb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005fbc  mov     rcx, [rbp+188h]; this
0x180005fc3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005fc9  mov     rcx, [rbp+188h]; this
0x180005fd0  mov     edx, 0A15h; void *
0x180005fd5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005fdb  mov     rcx, [rbp+188h]; this
0x180005fe2  mov     edx, 0A0Bh; void *
0x180005fe7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005fed  mov     rcx, [rbp+188h]; this
0x180005ff4  mov     edx, 0A15h; void *
0x180005ff9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005fff  mov     rcx, [rbp+188h]; this
0x180006006  mov     edx, 0A15h; void *
0x18000600b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
