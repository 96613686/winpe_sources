# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002ab8`
- end: `0x140002e56`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000392c`

## callees

- `0x1400017bf`
- `0x140002ab8`
- `0x140002e5c`
- `0x140003080`
- `0x1400036c8`
- `0x140004198`
- `0x140004454`
- `0x1400047b4`
- `0x140004840`
- `0x140004bfc`
- `0x140004c0c`
- `0x140004cd0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140002af1`
- `KERNEL32!GetCurrentProcessId` at `0x140002af1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002b51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002b51`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002bd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002cfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002d6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002bd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002cfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002d6b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002b30`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002b30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002be3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002d81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002be3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002d81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002cd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ccb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ccb`

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
0x140002ab8  mov     [rsp-8+arg_10], rbx
0x140002abd  push    rbp
0x140002abe  push    rsi
0x140002abf  push    rdi
0x140002ac0  push    r14
0x140002ac2  push    r15
0x140002ac4  lea     rbp, [rsp-160h]
0x140002acc  sub     rsp, 260h
0x140002ad3  mov     rax, cs:__security_cookie
0x140002ada  xor     rax, rsp
0x140002add  mov     [rbp+180h+var_30], rax
0x140002ae4  mov     r15, rdx
0x140002ae7  mov     qword ptr [rdx], 0
0x140002aee  mov     rbx, rcx
0x140002af1  call    cs:__imp_GetCurrentProcessId
0x140002af7  mov     r14d, 78h ; 'x'
0x140002afd  mov     [rsp+280h+var_258], rbx
0x140002b02  mov     r9d, eax
0x140002b05  mov     [rsp+280h+var_260], r14d; int
0x140002b0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002b11  mov     edx, 104h; unsigned __int64
0x140002b16  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002b1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002b20  mov     r9d, 1F0001h; dwDesiredAccess
0x140002b26  lea     rdx, [rsp+280h+Name]; lpName
0x140002b2b  xor     r8d, r8d; dwFlags
0x140002b2e  xor     ecx, ecx; lpMutexAttributes
0x140002b30  call    cs:__imp_CreateMutexExW
0x140002b36  mov     rbx, rax
0x140002b39  test    rax, rax
0x140002b3c  jnz     short loc_140002B48
0x140002b3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002b43  jmp     loc_140002D8D
0x140002b48  xor     r8d, r8d; bAlertable
0x140002b4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002b4e  mov     rcx, rbx; hHandle
0x140002b51  call    cs:__imp_WaitForSingleObjectEx
0x140002b57  cmp     eax, 102h
0x140002b5c  jz      short loc_140002B6E
0x140002b5e  test    eax, 0FFFFFF7Fh
0x140002b63  jnz     loc_140002DC5
0x140002b69  mov     rdi, rbx
0x140002b6c  jmp     short loc_140002B70
0x140002b6e  xor     edi, edi
0x140002b70  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002b75  mov     [rsp+280h+hObject], 0
0x140002b7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002b83  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002b88  mov     esi, eax
0x140002b8a  test    eax, eax
0x140002b8c  jns     short loc_140002BF8
0x140002b8e  mov     rcx, [rbp+188h]; this
0x140002b95  mov     r9d, eax; char *
0x140002b98  mov     edx, 66h ; 'f'; void *
0x140002b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002ba2  mov     rcx, [rbp+188h]; this
0x140002ba9  mov     r9d, esi; char *
0x140002bac  mov     edx, 6Fh ; 'o'; void *
0x140002bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002bb6  mov     rcx, [rbp+188h]; this
0x140002bbd  mov     r9d, esi; char *
0x140002bc0  mov     edx, 12Eh; void *
0x140002bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002bca  test    rdi, rdi
0x140002bcd  jz      short loc_140002BE0
0x140002bcf  mov     rcx, rdi; hMutex
0x140002bd2  call    cs:__imp_ReleaseMutex
0x140002bd8  test    eax, eax
0x140002bda  jz      loc_140002DD2
0x140002be0  mov     rcx, rbx; hObject
0x140002be3  call    cs:__imp_CloseHandle
0x140002be9  test    eax, eax
0x140002beb  jz      loc_140002DE4
0x140002bf1  mov     eax, esi
0x140002bf3  jmp     loc_140002D8D
0x140002bf8  mov     rax, [rsp+280h+hObject]
0x140002bfd  lea     rcx, ds:0[rax*4]
0x140002c05  test    rcx, rcx
0x140002c08  jz      short loc_140002C18
0x140002c0a  mov     [r15], rcx
0x140002c0d  mov     eax, [rcx]
0x140002c0f  inc     eax
0x140002c11  mov     [rcx], eax
0x140002c13  jmp     loc_140002D63
0x140002c18  mov     rdx, r14; dwBytes
0x140002c1b  mov     qword ptr [r15], 0
0x140002c22  mov     ecx, 8; dwFlags
0x140002c27  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002c2c  mov     rsi, rax
0x140002c2f  test    rax, rax
0x140002c32  jnz     short loc_140002C53
0x140002c34  mov     rcx, [rbp+188h]; this
0x140002c3b  mov     r14d, 8007000Eh
0x140002c41  mov     r9d, r14d; char *
0x140002c44  mov     edx, 14Bh; void *
0x140002c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c4e  jmp     loc_140002CDF
0x140002c53  xorps   xmm0, xmm0
0x140002c56  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002c5c  test    sil, 3
0x140002c60  jnz     loc_140002DF6
0x140002c66  mov     r9, rsi
0x140002c69  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140002c6e  shr     r9, 2; unsigned __int64
0x140002c72  lea     rcx, [rsp+280h+hObject]; this
0x140002c77  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140002c7c  mov     r14d, eax
0x140002c7f  test    eax, eax
0x140002c81  jns     loc_140002D1F
0x140002c87  mov     rcx, [rbp+188h]; this
0x140002c8e  mov     r9d, eax; char *
0x140002c91  mov     edx, 14Eh; void *
0x140002c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c9b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140002ca0  test    rcx, rcx
0x140002ca3  jz      short loc_140002CB3
0x140002ca5  call    cs:__imp_CloseHandle
0x140002cab  test    eax, eax
0x140002cad  jz      loc_140002DFC
0x140002cb3  mov     rcx, [rsp+280h+hObject]; hObject
0x140002cb8  test    rcx, rcx
0x140002cbb  jz      short loc_140002CCB
0x140002cbd  call    cs:__imp_CloseHandle
0x140002cc3  test    eax, eax
0x140002cc5  jz      loc_140002E0E
0x140002ccb  call    cs:__imp_GetProcessHeap
0x140002cd1  mov     r8, rsi; lpMem
0x140002cd4  xor     edx, edx; dwFlags
0x140002cd6  mov     rcx, rax; hHeap
0x140002cd9  call    cs:__imp_HeapFree
0x140002cdf  mov     rcx, [rbp+188h]; this
0x140002ce6  mov     r9d, r14d; char *
0x140002ce9  mov     edx, 137h; void *
0x140002cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002cf3  test    rdi, rdi
0x140002cf6  jz      short loc_140002D09
0x140002cf8  mov     rcx, rdi; hMutex
0x140002cfb  call    cs:__imp_ReleaseMutex
0x140002d01  test    eax, eax
0x140002d03  jz      loc_140002E20
0x140002d09  mov     rcx, rbx; hObject
0x140002d0c  call    cs:__imp_CloseHandle
0x140002d12  test    eax, eax
0x140002d14  jz      loc_140002E32
0x140002d1a  mov     eax, r14d
0x140002d1d  jmp     short loc_140002D8D
0x140002d1f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002d24  xor     edx, edx; Val
0x140002d26  mov     dword ptr [rsi], 1
0x140002d2c  lea     rcx, [rsi+22h]; void *
0x140002d30  mov     [rsi+8], rbx
0x140002d34  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002d39  lea     r8d, [rdx+56h]; Size
0x140002d3d  call    memset_0
0x140002d42  xor     edx, edx; Val
0x140002d44  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002d4a  lea     rcx, [rsi+28h]; void *
0x140002d4e  mov     dword ptr [rsi+24h], 1
0x140002d55  lea     r8d, [rdx+50h]; Size
0x140002d59  call    memset_0
0x140002d5e  xor     ebx, ebx
0x140002d60  mov     [r15], rsi
0x140002d63  test    rdi, rdi
0x140002d66  jz      short loc_140002D79
0x140002d68  mov     rcx, rdi; hMutex
0x140002d6b  call    cs:__imp_ReleaseMutex
0x140002d71  test    eax, eax
0x140002d73  jz      loc_140002E44
0x140002d79  test    rbx, rbx
0x140002d7c  jz      short loc_140002D8B
0x140002d7e  mov     rcx, rbx; hObject
0x140002d81  call    cs:__imp_CloseHandle
0x140002d87  test    eax, eax
0x140002d89  jz      short loc_140002DB3
0x140002d8b  xor     eax, eax
0x140002d8d  mov     rcx, [rbp+180h+var_30]
0x140002d94  xor     rcx, rsp; StackCookie
0x140002d97  call    __security_check_cookie
0x140002d9c  mov     rbx, [rsp+280h+arg_10]
0x140002da4  add     rsp, 260h
0x140002dab  pop     r15
0x140002dad  pop     r14
0x140002daf  pop     rdi
0x140002db0  pop     rsi
0x140002db1  pop     rbp
0x140002db2  retn
0x140002db3  mov     rcx, [rbp+188h]; this
0x140002dba  mov     edx, 0A0Bh; void *
0x140002dbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002dc5  mov     rcx, [rbp+188h]; this
0x140002dcc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140002dd2  mov     rcx, [rbp+188h]; this
0x140002dd9  mov     edx, 0A15h; void *
0x140002dde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002de4  mov     rcx, [rbp+188h]; this
0x140002deb  mov     edx, 0A0Bh; void *
0x140002df0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002df6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002dfc  mov     rcx, [rbp+188h]; this
0x140002e03  mov     edx, 0A0Bh; void *
0x140002e08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e0e  mov     rcx, [rbp+188h]; this
0x140002e15  mov     edx, 0A0Bh; void *
0x140002e1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e20  mov     rcx, [rbp+188h]; this
0x140002e27  mov     edx, 0A15h; void *
0x140002e2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e32  mov     rcx, [rbp+188h]; this
0x140002e39  mov     edx, 0A0Bh; void *
0x140002e3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002e44  mov     rcx, [rbp+188h]; this
0x140002e4b  mov     edx, 0A15h; void *
0x140002e50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
