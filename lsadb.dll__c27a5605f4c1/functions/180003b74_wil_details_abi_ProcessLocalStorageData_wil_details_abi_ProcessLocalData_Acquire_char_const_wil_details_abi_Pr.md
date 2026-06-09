# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003b74`
- end: `0x180003f12`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000539c`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180003b74`
- `0x1800042e8`
- `0x180004808`
- `0x180005138`
- `0x180006538`
- `0x180007ac4`
- `0x180007f8c`
- `0x1800083c0`
- `0x180008c7c`
- `0x180008c8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d87`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003bec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003bec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c0d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e3d`

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
0x180003b74  mov     [rsp-8+arg_10], rbx
0x180003b79  push    rbp
0x180003b7a  push    rsi
0x180003b7b  push    rdi
0x180003b7c  push    r14
0x180003b7e  push    r15
0x180003b80  lea     rbp, [rsp-160h]
0x180003b88  sub     rsp, 260h
0x180003b8f  mov     rax, cs:__security_cookie
0x180003b96  xor     rax, rsp
0x180003b99  mov     [rbp+180h+var_30], rax
0x180003ba0  mov     r15, rdx
0x180003ba3  mov     qword ptr [rdx], 0
0x180003baa  mov     rbx, rcx
0x180003bad  call    cs:__imp_GetCurrentProcessId
0x180003bb3  mov     r14d, 78h ; 'x'
0x180003bb9  mov     [rsp+280h+var_258], rbx
0x180003bbe  mov     r9d, eax
0x180003bc1  mov     [rsp+280h+var_260], r14d; int
0x180003bc6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003bcd  mov     edx, 104h; unsigned __int64
0x180003bd2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003bd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003bdc  mov     r9d, 1F0001h; dwDesiredAccess
0x180003be2  lea     rdx, [rsp+280h+Name]; lpName
0x180003be7  xor     r8d, r8d; dwFlags
0x180003bea  xor     ecx, ecx; lpMutexAttributes
0x180003bec  call    cs:__imp_CreateMutexExW
0x180003bf2  mov     rbx, rax
0x180003bf5  test    rax, rax
0x180003bf8  jnz     short loc_180003C04
0x180003bfa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bff  jmp     loc_180003E49
0x180003c04  xor     r8d, r8d; bAlertable
0x180003c07  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c0a  mov     rcx, rbx; hHandle
0x180003c0d  call    cs:__imp_WaitForSingleObjectEx
0x180003c13  cmp     eax, 102h
0x180003c18  jz      short loc_180003C2A
0x180003c1a  test    eax, 0FFFFFF7Fh
0x180003c1f  jnz     loc_180003E81
0x180003c25  mov     rdi, rbx
0x180003c28  jmp     short loc_180003C2C
0x180003c2a  xor     edi, edi
0x180003c2c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003c31  mov     [rsp+280h+hObject], 0
0x180003c3a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c3f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c44  mov     esi, eax
0x180003c46  test    eax, eax
0x180003c48  jns     short loc_180003CB4
0x180003c4a  mov     rcx, [rbp+188h]; this
0x180003c51  mov     r9d, eax; char *
0x180003c54  mov     edx, 66h ; 'f'; void *
0x180003c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c5e  mov     rcx, [rbp+188h]; this
0x180003c65  mov     r9d, esi; char *
0x180003c68  mov     edx, 6Fh ; 'o'; void *
0x180003c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c72  mov     rcx, [rbp+188h]; this
0x180003c79  mov     r9d, esi; char *
0x180003c7c  mov     edx, 12Eh; void *
0x180003c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c86  test    rdi, rdi
0x180003c89  jz      short loc_180003C9C
0x180003c8b  mov     rcx, rdi; hMutex
0x180003c8e  call    cs:__imp_ReleaseMutex
0x180003c94  test    eax, eax
0x180003c96  jz      loc_180003E8E
0x180003c9c  mov     rcx, rbx; hObject
0x180003c9f  call    cs:__imp_CloseHandle
0x180003ca5  test    eax, eax
0x180003ca7  jz      loc_180003EA0
0x180003cad  mov     eax, esi
0x180003caf  jmp     loc_180003E49
0x180003cb4  mov     rax, [rsp+280h+hObject]
0x180003cb9  lea     rcx, ds:0[rax*4]
0x180003cc1  test    rcx, rcx
0x180003cc4  jz      short loc_180003CD4
0x180003cc6  mov     [r15], rcx
0x180003cc9  mov     eax, [rcx]
0x180003ccb  inc     eax
0x180003ccd  mov     [rcx], eax
0x180003ccf  jmp     loc_180003E1F
0x180003cd4  mov     rdx, r14; dwBytes
0x180003cd7  mov     qword ptr [r15], 0
0x180003cde  mov     ecx, 8; dwFlags
0x180003ce3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003ce8  mov     rsi, rax
0x180003ceb  test    rax, rax
0x180003cee  jnz     short loc_180003D0F
0x180003cf0  mov     rcx, [rbp+188h]; this
0x180003cf7  mov     r14d, 8007000Eh
0x180003cfd  mov     r9d, r14d; char *
0x180003d00  mov     edx, 14Bh; void *
0x180003d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d0a  jmp     loc_180003D9B
0x180003d0f  xorps   xmm0, xmm0
0x180003d12  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003d18  test    sil, 3
0x180003d1c  jnz     loc_180003EB2
0x180003d22  mov     r9, rsi
0x180003d25  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d2a  shr     r9, 2; unsigned __int64
0x180003d2e  lea     rcx, [rsp+280h+hObject]; this
0x180003d33  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003d38  mov     r14d, eax
0x180003d3b  test    eax, eax
0x180003d3d  jns     loc_180003DDB
0x180003d43  mov     rcx, [rbp+188h]; this
0x180003d4a  mov     r9d, eax; char *
0x180003d4d  mov     edx, 14Eh; void *
0x180003d52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d57  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003d5c  test    rcx, rcx
0x180003d5f  jz      short loc_180003D6F
0x180003d61  call    cs:__imp_CloseHandle
0x180003d67  test    eax, eax
0x180003d69  jz      loc_180003EB8
0x180003d6f  mov     rcx, [rsp+280h+hObject]; hObject
0x180003d74  test    rcx, rcx
0x180003d77  jz      short loc_180003D87
0x180003d79  call    cs:__imp_CloseHandle
0x180003d7f  test    eax, eax
0x180003d81  jz      loc_180003ECA
0x180003d87  call    cs:__imp_GetProcessHeap
0x180003d8d  mov     r8, rsi; lpMem
0x180003d90  xor     edx, edx; dwFlags
0x180003d92  mov     rcx, rax; hHeap
0x180003d95  call    cs:__imp_HeapFree
0x180003d9b  mov     rcx, [rbp+188h]; this
0x180003da2  mov     r9d, r14d; char *
0x180003da5  mov     edx, 137h; void *
0x180003daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003daf  test    rdi, rdi
0x180003db2  jz      short loc_180003DC5
0x180003db4  mov     rcx, rdi; hMutex
0x180003db7  call    cs:__imp_ReleaseMutex
0x180003dbd  test    eax, eax
0x180003dbf  jz      loc_180003EDC
0x180003dc5  mov     rcx, rbx; hObject
0x180003dc8  call    cs:__imp_CloseHandle
0x180003dce  test    eax, eax
0x180003dd0  jz      loc_180003EEE
0x180003dd6  mov     eax, r14d
0x180003dd9  jmp     short loc_180003E49
0x180003ddb  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003de0  xor     edx, edx; Val
0x180003de2  mov     dword ptr [rsi], 1
0x180003de8  lea     rcx, [rsi+22h]; void *
0x180003dec  mov     [rsi+8], rbx
0x180003df0  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003df5  lea     r8d, [rdx+56h]; Size
0x180003df9  call    memset_0
0x180003dfe  xor     edx, edx; Val
0x180003e00  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003e06  lea     rcx, [rsi+28h]; void *
0x180003e0a  mov     dword ptr [rsi+24h], 1
0x180003e11  lea     r8d, [rdx+50h]; Size
0x180003e15  call    memset_0
0x180003e1a  xor     ebx, ebx
0x180003e1c  mov     [r15], rsi
0x180003e1f  test    rdi, rdi
0x180003e22  jz      short loc_180003E35
0x180003e24  mov     rcx, rdi; hMutex
0x180003e27  call    cs:__imp_ReleaseMutex
0x180003e2d  test    eax, eax
0x180003e2f  jz      loc_180003F00
0x180003e35  test    rbx, rbx
0x180003e38  jz      short loc_180003E47
0x180003e3a  mov     rcx, rbx; hObject
0x180003e3d  call    cs:__imp_CloseHandle
0x180003e43  test    eax, eax
0x180003e45  jz      short loc_180003E6F
0x180003e47  xor     eax, eax
0x180003e49  mov     rcx, [rbp+180h+var_30]
0x180003e50  xor     rcx, rsp; StackCookie
0x180003e53  call    __security_check_cookie
0x180003e58  mov     rbx, [rsp+280h+arg_10]
0x180003e60  add     rsp, 260h
0x180003e67  pop     r15
0x180003e69  pop     r14
0x180003e6b  pop     rdi
0x180003e6c  pop     rsi
0x180003e6d  pop     rbp
0x180003e6e  retn
0x180003e6f  mov     rcx, [rbp+188h]; this
0x180003e76  mov     edx, 0A0Bh; void *
0x180003e7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e81  mov     rcx, [rbp+188h]; this
0x180003e88  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003e8e  mov     rcx, [rbp+188h]; this
0x180003e95  mov     edx, 0A15h; void *
0x180003e9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ea0  mov     rcx, [rbp+188h]; this
0x180003ea7  mov     edx, 0A0Bh; void *
0x180003eac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eb2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003eb8  mov     rcx, [rbp+188h]; this
0x180003ebf  mov     edx, 0A0Bh; void *
0x180003ec4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eca  mov     rcx, [rbp+188h]; this
0x180003ed1  mov     edx, 0A0Bh; void *
0x180003ed6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003edc  mov     rcx, [rbp+188h]; this
0x180003ee3  mov     edx, 0A15h; void *
0x180003ee8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eee  mov     rcx, [rbp+188h]; this
0x180003ef5  mov     edx, 0A0Bh; void *
0x180003efa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f00  mov     rcx, [rbp+188h]; this
0x180003f07  mov     edx, 0A15h; void *
0x180003f0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
