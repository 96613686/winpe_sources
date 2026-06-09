# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003db8`
- end: `0x180004180`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004c80`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x180003db8`
- `0x180004188`
- `0x1800043d0`
- `0x180004a18`
- `0x1800054f8`
- `0x180005964`
- `0x1800062f0`
- `0x1800063cc`
- `0x1800067ac`
- `0x1800067bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e30`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004025`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004095`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004025`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ffc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ffc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003df1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ab`

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
0x180003db8  mov     [rsp-8+arg_10], rbx
0x180003dbd  push    rbp
0x180003dbe  push    rsi
0x180003dbf  push    rdi
0x180003dc0  push    r14
0x180003dc2  push    r15
0x180003dc4  lea     rbp, [rsp-160h]
0x180003dcc  sub     rsp, 260h
0x180003dd3  mov     rax, cs:__security_cookie
0x180003dda  xor     rax, rsp
0x180003ddd  mov     [rbp+180h+var_30], rax
0x180003de4  mov     r15, rdx
0x180003de7  mov     qword ptr [rdx], 0
0x180003dee  mov     rbx, rcx
0x180003df1  call    cs:__imp_GetCurrentProcessId
0x180003df7  mov     r14d, 78h ; 'x'
0x180003dfd  mov     [rsp+280h+var_258], rbx
0x180003e02  mov     r9d, eax
0x180003e05  mov     [rsp+280h+var_260], r14d; int
0x180003e0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e11  mov     edx, 104h; unsigned __int64
0x180003e16  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e20  mov     r9d, 1F0001h; dwDesiredAccess
0x180003e26  lea     rdx, [rsp+280h+Name]; lpName
0x180003e2b  xor     r8d, r8d; dwFlags
0x180003e2e  xor     ecx, ecx; lpMutexAttributes
0x180003e30  call    cs:__imp_CreateMutexExW
0x180003e36  mov     rbx, rax
0x180003e39  test    rax, rax
0x180003e3c  jnz     short loc_180003E48
0x180003e3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e43  jmp     loc_1800040B7
0x180003e48  xor     r8d, r8d; bAlertable
0x180003e4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003e4e  mov     rcx, rbx; hHandle
0x180003e51  call    cs:__imp_WaitForSingleObjectEx
0x180003e57  cmp     eax, 102h
0x180003e5c  jz      short loc_180003E6E
0x180003e5e  test    eax, 0FFFFFF7Fh
0x180003e63  jnz     loc_1800040EF
0x180003e69  mov     rdi, rbx
0x180003e6c  jmp     short loc_180003E70
0x180003e6e  xor     edi, edi
0x180003e70  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003e75  mov     [rsp+280h+hObject], 0
0x180003e7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e83  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003e88  mov     esi, eax
0x180003e8a  test    eax, eax
0x180003e8c  jns     short loc_180003F0D
0x180003e8e  mov     rcx, [rbp+188h]; this
0x180003e95  lea     r8, aWil; "wil"
0x180003e9c  mov     r9d, eax; char *
0x180003e9f  mov     edx, 66h ; 'f'; void *
0x180003ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ea9  mov     rcx, [rbp+188h]; this
0x180003eb0  lea     r8, aWil; "wil"
0x180003eb7  mov     r9d, esi; char *
0x180003eba  mov     edx, 6Fh ; 'o'; void *
0x180003ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ec4  mov     rcx, [rbp+188h]; this
0x180003ecb  lea     r8, aWil; "wil"
0x180003ed2  mov     r9d, esi; char *
0x180003ed5  mov     edx, 12Eh; void *
0x180003eda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003edf  test    rdi, rdi
0x180003ee2  jz      short loc_180003EF5
0x180003ee4  mov     rcx, rdi; hMutex
0x180003ee7  call    cs:__imp_ReleaseMutex
0x180003eed  test    eax, eax
0x180003eef  jz      loc_1800040FC
0x180003ef5  mov     rcx, rbx; hObject
0x180003ef8  call    cs:__imp_CloseHandle
0x180003efe  test    eax, eax
0x180003f00  jz      loc_18000410E
0x180003f06  mov     eax, esi
0x180003f08  jmp     loc_1800040B7
0x180003f0d  mov     rax, [rsp+280h+hObject]
0x180003f12  lea     rcx, ds:0[rax*4]
0x180003f1a  test    rcx, rcx
0x180003f1d  jz      short loc_180003F2D
0x180003f1f  mov     [r15], rcx
0x180003f22  mov     eax, [rcx]
0x180003f24  inc     eax
0x180003f26  mov     [rcx], eax
0x180003f28  jmp     loc_18000408D
0x180003f2d  mov     rdx, r14; dwBytes
0x180003f30  mov     qword ptr [r15], 0
0x180003f37  mov     ecx, 8; dwFlags
0x180003f3c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f41  mov     rsi, rax
0x180003f44  test    rax, rax
0x180003f47  jnz     short loc_180003F6F
0x180003f49  mov     rcx, [rbp+188h]; this
0x180003f50  lea     r8, aWil; "wil"
0x180003f57  mov     r14d, 8007000Eh
0x180003f5d  mov     edx, 14Bh; void *
0x180003f62  mov     r9d, r14d; char *
0x180003f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f6a  jmp     loc_180004002
0x180003f6f  xorps   xmm0, xmm0
0x180003f72  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003f78  test    sil, 3
0x180003f7c  jnz     loc_180004120
0x180003f82  mov     r9, rsi
0x180003f85  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003f8a  shr     r9, 2; unsigned __int64
0x180003f8e  lea     rcx, [rsp+280h+hObject]; this
0x180003f93  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003f98  mov     r14d, eax
0x180003f9b  test    eax, eax
0x180003f9d  jns     loc_180004049
0x180003fa3  mov     rcx, [rbp+188h]; this
0x180003faa  lea     r8, aWil; "wil"
0x180003fb1  mov     r9d, eax; char *
0x180003fb4  mov     edx, 14Eh; void *
0x180003fb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fbe  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003fc3  test    rcx, rcx
0x180003fc6  jz      short loc_180003FD6
0x180003fc8  call    cs:__imp_CloseHandle
0x180003fce  test    eax, eax
0x180003fd0  jz      loc_180004126
0x180003fd6  mov     rcx, [rsp+280h+hObject]; hObject
0x180003fdb  test    rcx, rcx
0x180003fde  jz      short loc_180003FEE
0x180003fe0  call    cs:__imp_CloseHandle
0x180003fe6  test    eax, eax
0x180003fe8  jz      loc_180004138
0x180003fee  call    cs:__imp_GetProcessHeap
0x180003ff4  mov     r8, rsi; lpMem
0x180003ff7  xor     edx, edx; dwFlags
0x180003ff9  mov     rcx, rax; hHeap
0x180003ffc  call    cs:__imp_HeapFree
0x180004002  mov     rcx, [rbp+188h]; this
0x180004009  lea     r8, aWil; "wil"
0x180004010  mov     r9d, r14d; char *
0x180004013  mov     edx, 137h; void *
0x180004018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000401d  test    rdi, rdi
0x180004020  jz      short loc_180004033
0x180004022  mov     rcx, rdi; hMutex
0x180004025  call    cs:__imp_ReleaseMutex
0x18000402b  test    eax, eax
0x18000402d  jz      loc_18000414A
0x180004033  mov     rcx, rbx; hObject
0x180004036  call    cs:__imp_CloseHandle
0x18000403c  test    eax, eax
0x18000403e  jz      loc_18000415C
0x180004044  mov     eax, r14d
0x180004047  jmp     short loc_1800040B7
0x180004049  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000404e  xor     edx, edx; Val
0x180004050  mov     dword ptr [rsi], 1
0x180004056  lea     rcx, [rsi+22h]; void *
0x18000405a  mov     [rsi+8], rbx
0x18000405e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004063  lea     r8d, [rdx+56h]; Size
0x180004067  call    memset_0
0x18000406c  xor     edx, edx; Val
0x18000406e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004074  lea     rcx, [rsi+28h]; void *
0x180004078  mov     dword ptr [rsi+24h], 1
0x18000407f  lea     r8d, [rdx+50h]; Size
0x180004083  call    memset_0
0x180004088  xor     ebx, ebx
0x18000408a  mov     [r15], rsi
0x18000408d  test    rdi, rdi
0x180004090  jz      short loc_1800040A3
0x180004092  mov     rcx, rdi; hMutex
0x180004095  call    cs:__imp_ReleaseMutex
0x18000409b  test    eax, eax
0x18000409d  jz      loc_18000416E
0x1800040a3  test    rbx, rbx
0x1800040a6  jz      short loc_1800040B5
0x1800040a8  mov     rcx, rbx; hObject
0x1800040ab  call    cs:__imp_CloseHandle
0x1800040b1  test    eax, eax
0x1800040b3  jz      short loc_1800040DD
0x1800040b5  xor     eax, eax
0x1800040b7  mov     rcx, [rbp+180h+var_30]
0x1800040be  xor     rcx, rsp; StackCookie
0x1800040c1  call    __security_check_cookie
0x1800040c6  mov     rbx, [rsp+280h+arg_10]
0x1800040ce  add     rsp, 260h
0x1800040d5  pop     r15
0x1800040d7  pop     r14
0x1800040d9  pop     rdi
0x1800040da  pop     rsi
0x1800040db  pop     rbp
0x1800040dc  retn
0x1800040dd  mov     rcx, [rbp+188h]; this
0x1800040e4  mov     edx, 0A0Bh; void *
0x1800040e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040ef  mov     rcx, [rbp+188h]; this
0x1800040f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800040fc  mov     rcx, [rbp+188h]; this
0x180004103  mov     edx, 0A15h; void *
0x180004108  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000410e  mov     rcx, [rbp+188h]; this
0x180004115  mov     edx, 0A0Bh; void *
0x18000411a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004120  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004126  mov     rcx, [rbp+188h]; this
0x18000412d  mov     edx, 0A0Bh; void *
0x180004132  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004138  mov     rcx, [rbp+188h]; this
0x18000413f  mov     edx, 0A0Bh; void *
0x180004144  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000414a  mov     rcx, [rbp+188h]; this
0x180004151  mov     edx, 0A15h; void *
0x180004156  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000415c  mov     rcx, [rbp+188h]; this
0x180004163  mov     edx, 0A0Bh; void *
0x180004168  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000416e  mov     rcx, [rbp+188h]; this
0x180004175  mov     edx, 0A15h; void *
0x18000417a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
