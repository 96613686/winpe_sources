# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005a1c`
- end: `0x180005def`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800073a8`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180005588`
- `0x180005a1c`
- `0x180006200`
- `0x18000669c`
- `0x180007080`
- `0x1800080d8`
- `0x180009c64`
- `0x18000a66c`
- `0x18000abec`
- `0x18000b5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ac1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ac1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005a9a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d21`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d3d`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180005a1c  mov     [rsp-8+arg_10], rbx
0x180005a21  push    rbp
0x180005a22  push    rsi
0x180005a23  push    rdi
0x180005a24  push    r14
0x180005a26  push    r15
0x180005a28  lea     rbp, [rsp-160h]
0x180005a30  sub     rsp, 260h
0x180005a37  mov     rax, cs:__security_cookie
0x180005a3e  xor     rax, rsp
0x180005a41  mov     [rbp+180h+var_30], rax
0x180005a48  mov     r15, rdx
0x180005a4b  mov     qword ptr [rdx], 0
0x180005a52  mov     rbx, rcx
0x180005a55  call    cs:__imp_GetCurrentProcessId
0x180005a5c  nop     dword ptr [rax+rax+00h]
0x180005a61  mov     r14d, 78h ; 'x'
0x180005a67  mov     [rsp+280h+var_258], rbx
0x180005a6c  mov     r9d, eax
0x180005a6f  mov     [rsp+280h+var_260], r14d; int
0x180005a74  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005a7b  mov     edx, 104h; unsigned __int64
0x180005a80  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005a85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a8a  mov     r9d, 1F0001h; dwDesiredAccess
0x180005a90  lea     rdx, [rsp+280h+Name]; lpName
0x180005a95  xor     r8d, r8d; dwFlags
0x180005a98  xor     ecx, ecx; lpMutexAttributes
0x180005a9a  call    cs:__imp_CreateMutexExW
0x180005aa1  nop     dword ptr [rax+rax+00h]
0x180005aa6  mov     rbx, rax
0x180005aa9  test    rax, rax
0x180005aac  jnz     short loc_180005AB8
0x180005aae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ab3  jmp     loc_180005D4F
0x180005ab8  xor     r8d, r8d; bAlertable
0x180005abb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005abe  mov     rcx, rbx; hHandle
0x180005ac1  call    cs:__imp_WaitForSingleObjectEx
0x180005ac8  nop     dword ptr [rax+rax+00h]
0x180005acd  cmp     eax, 102h
0x180005ad2  jz      short loc_180005AE4
0x180005ad4  test    eax, 0FFFFFF7Fh
0x180005ad9  jnz     loc_180005D9A
0x180005adf  mov     rdi, rbx
0x180005ae2  jmp     short loc_180005AE6
0x180005ae4  xor     edi, edi
0x180005ae6  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005aeb  mov     [rsp+280h+var_250], 0
0x180005af4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005af9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005afe  mov     esi, eax
0x180005b00  test    eax, eax
0x180005b02  jns     loc_180005B93
0x180005b08  mov     rcx, [rbp+188h]; this
0x180005b0f  lea     r8, aWil; "wil"
0x180005b16  mov     r9d, eax; char *
0x180005b19  mov     edx, 66h ; 'f'; void *
0x180005b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b23  mov     rcx, [rbp+188h]; this
0x180005b2a  lea     r8, aWil; "wil"
0x180005b31  mov     r9d, esi; char *
0x180005b34  mov     edx, 6Fh ; 'o'; void *
0x180005b39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b3e  mov     rcx, [rbp+188h]; this
0x180005b45  lea     r8, aWil; "wil"
0x180005b4c  mov     r9d, esi; char *
0x180005b4f  mov     edx, 12Eh; void *
0x180005b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b59  test    rdi, rdi
0x180005b5c  jz      short loc_180005B75
0x180005b5e  mov     rcx, rdi; hMutex
0x180005b61  call    cs:__imp_ReleaseMutex
0x180005b68  nop     dword ptr [rax+rax+00h]
0x180005b6d  test    eax, eax
0x180005b6f  jz      loc_180005DA7
0x180005b75  mov     rcx, rbx; hObject
0x180005b78  call    cs:__imp_CloseHandle
0x180005b7f  nop     dword ptr [rax+rax+00h]
0x180005b84  test    eax, eax
0x180005b86  jz      loc_180005DB9
0x180005b8c  mov     eax, esi
0x180005b8e  jmp     loc_180005D4F
0x180005b93  mov     rax, [rsp+280h+var_250]
0x180005b98  lea     rcx, ds:0[rax*4]
0x180005ba0  test    rcx, rcx
0x180005ba3  jz      short loc_180005BB3
0x180005ba5  mov     [r15], rcx
0x180005ba8  mov     eax, [rcx]
0x180005baa  inc     eax
0x180005bac  mov     [rcx], eax
0x180005bae  jmp     loc_180005D19
0x180005bb3  mov     rdx, r14; dwBytes
0x180005bb6  mov     qword ptr [r15], 0
0x180005bbd  mov     ecx, 8; dwFlags
0x180005bc2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005bc7  mov     r14, rax
0x180005bca  test    rax, rax
0x180005bcd  jnz     short loc_180005BF1
0x180005bcf  mov     rcx, [rbp+188h]; this
0x180005bd6  lea     r8, aWil; "wil"
0x180005bdd  mov     esi, 8007000Eh
0x180005be2  mov     edx, 14Bh; void *
0x180005be7  mov     r9d, esi; char *
0x180005bea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bef  jmp     short loc_180005C5B
0x180005bf1  xorps   xmm0, xmm0
0x180005bf4  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005bf9  mov     r8, r14; void *
0x180005bfc  lea     rcx, [rsp+280h+var_250]; this
0x180005c01  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005c07  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180005c0c  mov     esi, eax
0x180005c0e  test    eax, eax
0x180005c10  jns     loc_180005CAE
0x180005c16  mov     rcx, [rbp+188h]; this
0x180005c1d  lea     r8, aWil; "wil"
0x180005c24  mov     r9d, eax; char *
0x180005c27  mov     edx, 14Eh; void *
0x180005c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c31  lea     rcx, [rsp+280h+var_250]; this
0x180005c36  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005c3b  call    cs:__imp_GetProcessHeap
0x180005c42  nop     dword ptr [rax+rax+00h]
0x180005c47  mov     r8, r14; lpMem
0x180005c4a  xor     edx, edx; dwFlags
0x180005c4c  mov     rcx, rax; hHeap
0x180005c4f  call    cs:__imp_HeapFree
0x180005c56  nop     dword ptr [rax+rax+00h]
0x180005c5b  mov     rcx, [rbp+188h]; this
0x180005c62  lea     r8, aWil; "wil"
0x180005c69  mov     r9d, esi; char *
0x180005c6c  mov     edx, 137h; void *
0x180005c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c76  test    rdi, rdi
0x180005c79  jz      short loc_180005C92
0x180005c7b  mov     rcx, rdi; hMutex
0x180005c7e  call    cs:__imp_ReleaseMutex
0x180005c85  nop     dword ptr [rax+rax+00h]
0x180005c8a  test    eax, eax
0x180005c8c  jz      loc_180005DCB
0x180005c92  mov     rcx, rbx; hObject
0x180005c95  call    cs:__imp_CloseHandle
0x180005c9c  nop     dword ptr [rax+rax+00h]
0x180005ca1  test    eax, eax
0x180005ca3  jz      loc_180005D88
0x180005ca9  jmp     loc_180005B8C
0x180005cae  mov     rax, [rsp+280h+var_250]
0x180005cb3  lea     rcx, [r14+22h]; void *
0x180005cb7  xor     edx, edx; Val
0x180005cb9  mov     [r14+10h], rax
0x180005cbd  mov     rax, [rsp+280h+var_250+8]
0x180005cc2  mov     dword ptr [r14], 1
0x180005cc9  mov     [r14+8], rbx
0x180005ccd  lea     r8d, [rdx+56h]; Size
0x180005cd1  mov     [rsp+280h+var_250], 0
0x180005cda  mov     [r14+18h], rax
0x180005cde  mov     [rsp+280h+var_250+8], 0
0x180005ce7  call    memset_0
0x180005cec  xor     edx, edx; Val
0x180005cee  mov     word ptr [r14+20h], 58h ; 'X'
0x180005cf5  lea     rcx, [r14+28h]; void *
0x180005cf9  mov     dword ptr [r14+24h], 1
0x180005d01  lea     r8d, [rdx+50h]; Size
0x180005d05  call    memset_0
0x180005d0a  lea     rcx, [rsp+280h+var_250]; this
0x180005d0f  mov     [r15], r14
0x180005d12  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005d17  xor     ebx, ebx
0x180005d19  test    rdi, rdi
0x180005d1c  jz      short loc_180005D35
0x180005d1e  mov     rcx, rdi; hMutex
0x180005d21  call    cs:__imp_ReleaseMutex
0x180005d28  nop     dword ptr [rax+rax+00h]
0x180005d2d  test    eax, eax
0x180005d2f  jz      loc_180005DDD
0x180005d35  test    rbx, rbx
0x180005d38  jz      short loc_180005D4D
0x180005d3a  mov     rcx, rbx; hObject
0x180005d3d  call    cs:__imp_CloseHandle
0x180005d44  nop     dword ptr [rax+rax+00h]
0x180005d49  test    eax, eax
0x180005d4b  jz      short loc_180005D76
0x180005d4d  xor     eax, eax
0x180005d4f  mov     rcx, [rbp+180h+var_30]
0x180005d56  xor     rcx, rsp; StackCookie
0x180005d59  call    __security_check_cookie
0x180005d5e  mov     rbx, [rsp+280h+arg_10]
0x180005d66  add     rsp, 260h
0x180005d6d  pop     r15
0x180005d6f  pop     r14
0x180005d71  pop     rdi
0x180005d72  pop     rsi
0x180005d73  pop     rbp
0x180005d74  retn
0x180005d76  mov     rcx, [rbp+188h]; this
0x180005d7d  mov     edx, 0A0Bh; void *
0x180005d82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d88  mov     rcx, [rbp+188h]; this
0x180005d8f  mov     edx, 0A0Bh; void *
0x180005d94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d9a  mov     rcx, [rbp+188h]; this
0x180005da1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005da7  mov     rcx, [rbp+188h]; this
0x180005dae  mov     edx, 0A15h; void *
0x180005db3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005db9  mov     rcx, [rbp+188h]; this
0x180005dc0  mov     edx, 0A0Bh; void *
0x180005dc5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005dcb  mov     rcx, [rbp+188h]; this
0x180005dd2  mov     edx, 0A15h; void *
0x180005dd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ddd  mov     rcx, [rbp+188h]; this
0x180005de4  mov     edx, 0A15h; void *
0x180005de9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
