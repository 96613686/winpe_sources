# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004c68`
- end: `0x180005006`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007df0`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180004c68`
- `0x180005ea8`
- `0x180006a28`
- `0x1800077ac`
- `0x180008b94`
- `0x180009f0c`
- `0x18000af00`
- `0x18000b27c`
- `0x18000f33c`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ce0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ce0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004d82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004d82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004ca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f31`

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
0x180004c68  mov     [rsp-8+arg_10], rbx
0x180004c6d  push    rbp
0x180004c6e  push    rsi
0x180004c6f  push    rdi
0x180004c70  push    r14
0x180004c72  push    r15
0x180004c74  lea     rbp, [rsp-160h]
0x180004c7c  sub     rsp, 260h
0x180004c83  mov     rax, cs:__security_cookie
0x180004c8a  xor     rax, rsp
0x180004c8d  mov     [rbp+180h+var_30], rax
0x180004c94  mov     r15, rdx
0x180004c97  mov     qword ptr [rdx], 0
0x180004c9e  mov     rbx, rcx
0x180004ca1  call    cs:__imp_GetCurrentProcessId
0x180004ca7  mov     r14d, 78h ; 'x'
0x180004cad  mov     [rsp+280h+var_258], rbx
0x180004cb2  mov     r9d, eax
0x180004cb5  mov     [rsp+280h+var_260], r14d; int
0x180004cba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004cc1  mov     edx, 104h; unsigned __int64
0x180004cc6  lea     rcx, [rsp+280h+Name]; Buffer
0x180004ccb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004cd0  mov     r9d, 1F0001h; dwDesiredAccess
0x180004cd6  lea     rdx, [rsp+280h+Name]; lpName
0x180004cdb  xor     r8d, r8d; dwFlags
0x180004cde  xor     ecx, ecx; lpMutexAttributes
0x180004ce0  call    cs:__imp_CreateMutexExW
0x180004ce6  mov     rbx, rax
0x180004ce9  test    rax, rax
0x180004cec  jnz     short loc_180004CF8
0x180004cee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004cf3  jmp     loc_180004F3D
0x180004cf8  xor     r8d, r8d; bAlertable
0x180004cfb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004cfe  mov     rcx, rbx; hHandle
0x180004d01  call    cs:__imp_WaitForSingleObjectEx
0x180004d07  cmp     eax, 102h
0x180004d0c  jz      short loc_180004D1E
0x180004d0e  test    eax, 0FFFFFF7Fh
0x180004d13  jnz     loc_180004F75
0x180004d19  mov     rdi, rbx
0x180004d1c  jmp     short loc_180004D20
0x180004d1e  xor     edi, edi
0x180004d20  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004d25  mov     [rsp+280h+hObject], 0
0x180004d2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004d33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004d38  mov     esi, eax
0x180004d3a  test    eax, eax
0x180004d3c  jns     short loc_180004DA8
0x180004d3e  mov     rcx, [rbp+188h]; this
0x180004d45  mov     r9d, eax; char *
0x180004d48  mov     edx, 66h ; 'f'; void *
0x180004d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d52  mov     rcx, [rbp+188h]; this
0x180004d59  mov     r9d, esi; char *
0x180004d5c  mov     edx, 6Fh ; 'o'; void *
0x180004d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d66  mov     rcx, [rbp+188h]; this
0x180004d6d  mov     r9d, esi; char *
0x180004d70  mov     edx, 12Eh; void *
0x180004d75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d7a  test    rdi, rdi
0x180004d7d  jz      short loc_180004D90
0x180004d7f  mov     rcx, rdi; hMutex
0x180004d82  call    cs:__imp_ReleaseMutex
0x180004d88  test    eax, eax
0x180004d8a  jz      loc_180004F82
0x180004d90  mov     rcx, rbx; hObject
0x180004d93  call    cs:__imp_CloseHandle
0x180004d99  test    eax, eax
0x180004d9b  jz      loc_180004F94
0x180004da1  mov     eax, esi
0x180004da3  jmp     loc_180004F3D
0x180004da8  mov     rax, [rsp+280h+hObject]
0x180004dad  lea     rcx, ds:0[rax*4]
0x180004db5  test    rcx, rcx
0x180004db8  jz      short loc_180004DC8
0x180004dba  mov     [r15], rcx
0x180004dbd  mov     eax, [rcx]
0x180004dbf  inc     eax
0x180004dc1  mov     [rcx], eax
0x180004dc3  jmp     loc_180004F13
0x180004dc8  mov     rdx, r14; dwBytes
0x180004dcb  mov     qword ptr [r15], 0
0x180004dd2  mov     ecx, 8; dwFlags
0x180004dd7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ddc  mov     rsi, rax
0x180004ddf  test    rax, rax
0x180004de2  jnz     short loc_180004E03
0x180004de4  mov     rcx, [rbp+188h]; this
0x180004deb  mov     r14d, 8007000Eh
0x180004df1  mov     r9d, r14d; char *
0x180004df4  mov     edx, 14Bh; void *
0x180004df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dfe  jmp     loc_180004E8F
0x180004e03  xorps   xmm0, xmm0
0x180004e06  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004e0c  test    sil, 3
0x180004e10  jnz     loc_180004FA6
0x180004e16  mov     r9, rsi
0x180004e19  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004e1e  shr     r9, 2; unsigned __int64
0x180004e22  lea     rcx, [rsp+280h+hObject]; this
0x180004e27  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004e2c  mov     r14d, eax
0x180004e2f  test    eax, eax
0x180004e31  jns     loc_180004ECF
0x180004e37  mov     rcx, [rbp+188h]; this
0x180004e3e  mov     r9d, eax; char *
0x180004e41  mov     edx, 14Eh; void *
0x180004e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e4b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004e50  test    rcx, rcx
0x180004e53  jz      short loc_180004E63
0x180004e55  call    cs:__imp_CloseHandle
0x180004e5b  test    eax, eax
0x180004e5d  jz      loc_180004FAC
0x180004e63  mov     rcx, [rsp+280h+hObject]; hObject
0x180004e68  test    rcx, rcx
0x180004e6b  jz      short loc_180004E7B
0x180004e6d  call    cs:__imp_CloseHandle
0x180004e73  test    eax, eax
0x180004e75  jz      loc_180004FBE
0x180004e7b  call    cs:__imp_GetProcessHeap
0x180004e81  mov     r8, rsi; lpMem
0x180004e84  xor     edx, edx; dwFlags
0x180004e86  mov     rcx, rax; hHeap
0x180004e89  call    cs:__imp_HeapFree
0x180004e8f  mov     rcx, [rbp+188h]; this
0x180004e96  mov     r9d, r14d; char *
0x180004e99  mov     edx, 137h; void *
0x180004e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ea3  test    rdi, rdi
0x180004ea6  jz      short loc_180004EB9
0x180004ea8  mov     rcx, rdi; hMutex
0x180004eab  call    cs:__imp_ReleaseMutex
0x180004eb1  test    eax, eax
0x180004eb3  jz      loc_180004FD0
0x180004eb9  mov     rcx, rbx; hObject
0x180004ebc  call    cs:__imp_CloseHandle
0x180004ec2  test    eax, eax
0x180004ec4  jz      loc_180004FE2
0x180004eca  mov     eax, r14d
0x180004ecd  jmp     short loc_180004F3D
0x180004ecf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004ed4  xor     edx, edx; Val
0x180004ed6  mov     dword ptr [rsi], 1
0x180004edc  lea     rcx, [rsi+22h]; void *
0x180004ee0  mov     [rsi+8], rbx
0x180004ee4  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004ee9  lea     r8d, [rdx+56h]; Size
0x180004eed  call    memset_0
0x180004ef2  xor     edx, edx; Val
0x180004ef4  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004efa  lea     rcx, [rsi+28h]; void *
0x180004efe  mov     dword ptr [rsi+24h], 1
0x180004f05  lea     r8d, [rdx+50h]; Size
0x180004f09  call    memset_0
0x180004f0e  xor     ebx, ebx
0x180004f10  mov     [r15], rsi
0x180004f13  test    rdi, rdi
0x180004f16  jz      short loc_180004F29
0x180004f18  mov     rcx, rdi; hMutex
0x180004f1b  call    cs:__imp_ReleaseMutex
0x180004f21  test    eax, eax
0x180004f23  jz      loc_180004FF4
0x180004f29  test    rbx, rbx
0x180004f2c  jz      short loc_180004F3B
0x180004f2e  mov     rcx, rbx; hObject
0x180004f31  call    cs:__imp_CloseHandle
0x180004f37  test    eax, eax
0x180004f39  jz      short loc_180004F63
0x180004f3b  xor     eax, eax
0x180004f3d  mov     rcx, [rbp+180h+var_30]
0x180004f44  xor     rcx, rsp; StackCookie
0x180004f47  call    __security_check_cookie
0x180004f4c  mov     rbx, [rsp+280h+arg_10]
0x180004f54  add     rsp, 260h
0x180004f5b  pop     r15
0x180004f5d  pop     r14
0x180004f5f  pop     rdi
0x180004f60  pop     rsi
0x180004f61  pop     rbp
0x180004f62  retn
0x180004f63  mov     rcx, [rbp+188h]; this
0x180004f6a  mov     edx, 0A0Bh; void *
0x180004f6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f75  mov     rcx, [rbp+188h]; this
0x180004f7c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004f82  mov     rcx, [rbp+188h]; this
0x180004f89  mov     edx, 0A15h; void *
0x180004f8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f94  mov     rcx, [rbp+188h]; this
0x180004f9b  mov     edx, 0A0Bh; void *
0x180004fa0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fa6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004fac  mov     rcx, [rbp+188h]; this
0x180004fb3  mov     edx, 0A0Bh; void *
0x180004fb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fbe  mov     rcx, [rbp+188h]; this
0x180004fc5  mov     edx, 0A0Bh; void *
0x180004fca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fd0  mov     rcx, [rbp+188h]; this
0x180004fd7  mov     edx, 0A15h; void *
0x180004fdc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fe2  mov     rcx, [rbp+188h]; this
0x180004fe9  mov     edx, 0A0Bh; void *
0x180004fee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ff4  mov     rcx, [rbp+188h]; this
0x180004ffb  mov     edx, 0A15h; void *
0x180005000  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
