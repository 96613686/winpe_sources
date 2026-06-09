# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003d68`
- end: `0x140004106`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004c10`

## callees

- `0x140001470`
- `0x140001f0e`
- `0x140003d68`
- `0x14000410c`
- `0x140004330`
- `0x1400049a8`
- `0x140005530`
- `0x1400059c4`
- `0x14000681c`
- `0x14000691c`
- `0x140006ccc`
- `0x140006cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003de0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003de0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003e82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000401b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003e82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000401b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003da1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004031`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x140003d68  mov     [rsp-8+arg_10], rbx
0x140003d6d  push    rbp
0x140003d6e  push    rsi
0x140003d6f  push    rdi
0x140003d70  push    r14
0x140003d72  push    r15
0x140003d74  lea     rbp, [rsp-160h]
0x140003d7c  sub     rsp, 260h
0x140003d83  mov     rax, cs:__security_cookie
0x140003d8a  xor     rax, rsp
0x140003d8d  mov     [rbp+180h+var_30], rax
0x140003d94  mov     r15, rdx
0x140003d97  mov     qword ptr [rdx], 0
0x140003d9e  mov     rbx, rcx
0x140003da1  call    cs:__imp_GetCurrentProcessId
0x140003da7  mov     r14d, 78h ; 'x'
0x140003dad  mov     [rsp+280h+var_258], rbx
0x140003db2  mov     r9d, eax
0x140003db5  mov     [rsp+280h+var_260], r14d; int
0x140003dba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003dc1  mov     edx, 104h; unsigned __int64
0x140003dc6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140003dcb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140003dd0  mov     r9d, 1F0001h; dwDesiredAccess
0x140003dd6  lea     rdx, [rsp+280h+Name]; lpName
0x140003ddb  xor     r8d, r8d; dwFlags
0x140003dde  xor     ecx, ecx; lpMutexAttributes
0x140003de0  call    cs:__imp_CreateMutexExW
0x140003de6  mov     rbx, rax
0x140003de9  test    rax, rax
0x140003dec  jnz     short loc_140003DF8
0x140003dee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003df3  jmp     loc_14000403D
0x140003df8  xor     r8d, r8d; bAlertable
0x140003dfb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003dfe  mov     rcx, rbx; hHandle
0x140003e01  call    cs:__imp_WaitForSingleObjectEx
0x140003e07  cmp     eax, 102h
0x140003e0c  jz      short loc_140003E1E
0x140003e0e  test    eax, 0FFFFFF7Fh
0x140003e13  jnz     loc_140004075
0x140003e19  mov     rdi, rbx
0x140003e1c  jmp     short loc_140003E20
0x140003e1e  xor     edi, edi
0x140003e20  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003e25  mov     [rsp+280h+hObject], 0
0x140003e2e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140003e33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140003e38  mov     esi, eax
0x140003e3a  test    eax, eax
0x140003e3c  jns     short loc_140003EA8
0x140003e3e  mov     rcx, [rbp+188h]; this
0x140003e45  mov     r9d, eax; char *
0x140003e48  mov     edx, 66h ; 'f'; void *
0x140003e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e52  mov     rcx, [rbp+188h]; this
0x140003e59  mov     r9d, esi; char *
0x140003e5c  mov     edx, 6Fh ; 'o'; void *
0x140003e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e66  mov     rcx, [rbp+188h]; this
0x140003e6d  mov     r9d, esi; char *
0x140003e70  mov     edx, 12Eh; void *
0x140003e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e7a  test    rdi, rdi
0x140003e7d  jz      short loc_140003E90
0x140003e7f  mov     rcx, rdi; hMutex
0x140003e82  call    cs:__imp_ReleaseMutex
0x140003e88  test    eax, eax
0x140003e8a  jz      loc_140004082
0x140003e90  mov     rcx, rbx; hObject
0x140003e93  call    cs:__imp_CloseHandle
0x140003e99  test    eax, eax
0x140003e9b  jz      loc_140004094
0x140003ea1  mov     eax, esi
0x140003ea3  jmp     loc_14000403D
0x140003ea8  mov     rax, [rsp+280h+hObject]
0x140003ead  lea     rcx, ds:0[rax*4]
0x140003eb5  test    rcx, rcx
0x140003eb8  jz      short loc_140003EC8
0x140003eba  mov     [r15], rcx
0x140003ebd  mov     eax, [rcx]
0x140003ebf  inc     eax
0x140003ec1  mov     [rcx], eax
0x140003ec3  jmp     loc_140004013
0x140003ec8  mov     rdx, r14; dwBytes
0x140003ecb  mov     qword ptr [r15], 0
0x140003ed2  mov     ecx, 8; dwFlags
0x140003ed7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003edc  mov     rsi, rax
0x140003edf  test    rax, rax
0x140003ee2  jnz     short loc_140003F03
0x140003ee4  mov     rcx, [rbp+188h]; this
0x140003eeb  mov     r14d, 8007000Eh
0x140003ef1  mov     r9d, r14d; char *
0x140003ef4  mov     edx, 14Bh; void *
0x140003ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003efe  jmp     loc_140003F8F
0x140003f03  xorps   xmm0, xmm0
0x140003f06  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003f0c  test    sil, 3
0x140003f10  jnz     loc_1400040A6
0x140003f16  mov     r9, rsi
0x140003f19  lea     rdx, [rsp+280h+Name]; wchar_t *
0x140003f1e  shr     r9, 2; unsigned __int64
0x140003f22  lea     rcx, [rsp+280h+hObject]; this
0x140003f27  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x140003f2c  mov     r14d, eax
0x140003f2f  test    eax, eax
0x140003f31  jns     loc_140003FCF
0x140003f37  mov     rcx, [rbp+188h]; this
0x140003f3e  mov     r9d, eax; char *
0x140003f41  mov     edx, 14Eh; void *
0x140003f46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f4b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003f50  test    rcx, rcx
0x140003f53  jz      short loc_140003F63
0x140003f55  call    cs:__imp_CloseHandle
0x140003f5b  test    eax, eax
0x140003f5d  jz      loc_1400040AC
0x140003f63  mov     rcx, [rsp+280h+hObject]; hObject
0x140003f68  test    rcx, rcx
0x140003f6b  jz      short loc_140003F7B
0x140003f6d  call    cs:__imp_CloseHandle
0x140003f73  test    eax, eax
0x140003f75  jz      loc_1400040BE
0x140003f7b  call    cs:__imp_GetProcessHeap
0x140003f81  mov     r8, rsi; lpMem
0x140003f84  xor     edx, edx; dwFlags
0x140003f86  mov     rcx, rax; hHeap
0x140003f89  call    cs:__imp_HeapFree
0x140003f8f  mov     rcx, [rbp+188h]; this
0x140003f96  mov     r9d, r14d; char *
0x140003f99  mov     edx, 137h; void *
0x140003f9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fa3  test    rdi, rdi
0x140003fa6  jz      short loc_140003FB9
0x140003fa8  mov     rcx, rdi; hMutex
0x140003fab  call    cs:__imp_ReleaseMutex
0x140003fb1  test    eax, eax
0x140003fb3  jz      loc_1400040D0
0x140003fb9  mov     rcx, rbx; hObject
0x140003fbc  call    cs:__imp_CloseHandle
0x140003fc2  test    eax, eax
0x140003fc4  jz      loc_1400040E2
0x140003fca  mov     eax, r14d
0x140003fcd  jmp     short loc_14000403D
0x140003fcf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003fd4  xor     edx, edx; Val
0x140003fd6  mov     dword ptr [rsi], 1
0x140003fdc  lea     rcx, [rsi+22h]; void *
0x140003fe0  mov     [rsi+8], rbx
0x140003fe4  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003fe9  lea     r8d, [rdx+56h]; Size
0x140003fed  call    memset_0
0x140003ff2  xor     edx, edx; Val
0x140003ff4  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003ffa  lea     rcx, [rsi+28h]; void *
0x140003ffe  mov     dword ptr [rsi+24h], 1
0x140004005  lea     r8d, [rdx+50h]; Size
0x140004009  call    memset_0
0x14000400e  xor     ebx, ebx
0x140004010  mov     [r15], rsi
0x140004013  test    rdi, rdi
0x140004016  jz      short loc_140004029
0x140004018  mov     rcx, rdi; hMutex
0x14000401b  call    cs:__imp_ReleaseMutex
0x140004021  test    eax, eax
0x140004023  jz      loc_1400040F4
0x140004029  test    rbx, rbx
0x14000402c  jz      short loc_14000403B
0x14000402e  mov     rcx, rbx; hObject
0x140004031  call    cs:__imp_CloseHandle
0x140004037  test    eax, eax
0x140004039  jz      short loc_140004063
0x14000403b  xor     eax, eax
0x14000403d  mov     rcx, [rbp+180h+var_30]
0x140004044  xor     rcx, rsp; StackCookie
0x140004047  call    __security_check_cookie
0x14000404c  mov     rbx, [rsp+280h+arg_10]
0x140004054  add     rsp, 260h
0x14000405b  pop     r15
0x14000405d  pop     r14
0x14000405f  pop     rdi
0x140004060  pop     rsi
0x140004061  pop     rbp
0x140004062  retn
0x140004063  mov     rcx, [rbp+188h]; this
0x14000406a  mov     edx, 0A0Bh; void *
0x14000406f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004075  mov     rcx, [rbp+188h]; this
0x14000407c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004082  mov     rcx, [rbp+188h]; this
0x140004089  mov     edx, 0A15h; void *
0x14000408e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004094  mov     rcx, [rbp+188h]; this
0x14000409b  mov     edx, 0A0Bh; void *
0x1400040a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400040ac  mov     rcx, [rbp+188h]; this
0x1400040b3  mov     edx, 0A0Bh; void *
0x1400040b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040be  mov     rcx, [rbp+188h]; this
0x1400040c5  mov     edx, 0A0Bh; void *
0x1400040ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040d0  mov     rcx, [rbp+188h]; this
0x1400040d7  mov     edx, 0A15h; void *
0x1400040dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040e2  mov     rcx, [rbp+188h]; this
0x1400040e9  mov     edx, 0A0Bh; void *
0x1400040ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400040f4  mov     rcx, [rbp+188h]; this
0x1400040fb  mov     edx, 0A15h; void *
0x140004100  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
