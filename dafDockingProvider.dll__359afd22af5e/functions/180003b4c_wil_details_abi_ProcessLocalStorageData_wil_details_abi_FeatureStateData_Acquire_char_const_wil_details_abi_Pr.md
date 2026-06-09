# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003b4c`
- end: `0x180003f13`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800041e4`

## callees

- `0x180002f20`
- `0x180003b4c`
- `0x180003f1c`
- `0x180004374`
- `0x180004bd8`
- `0x1800057d8`
- `0x180006aa4`
- `0x1800073d8`
- `0x18000770c`
- `0x180007edc`
- `0x180007eec`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003bc3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003bc3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003df5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003df5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003be4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e3e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180003b4c  mov     [rsp-8+arg_10], rbx
0x180003b51  push    rbp
0x180003b52  push    rsi
0x180003b53  push    rdi
0x180003b54  push    r14
0x180003b56  push    r15
0x180003b58  lea     rbp, [rsp-160h]
0x180003b60  sub     rsp, 260h
0x180003b67  mov     rax, cs:__security_cookie
0x180003b6e  xor     rax, rsp
0x180003b71  mov     [rbp+180h+var_30], rax
0x180003b78  mov     r15, rdx
0x180003b7b  mov     qword ptr [rdx], 0
0x180003b82  mov     rbx, rcx
0x180003b85  call    cs:__imp_GetCurrentProcessId
0x180003b8b  mov     r14d, 130h
0x180003b91  mov     [rsp+280h+var_258], rbx
0x180003b96  mov     r9d, eax
0x180003b99  mov     [rsp+280h+var_260], r14d; int
0x180003b9e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ba5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003baa  lea     edx, [r14-2Ch]; unsigned __int64
0x180003bae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003bb3  mov     r9d, 1F0001h; dwDesiredAccess
0x180003bb9  lea     rdx, [rsp+280h+Name]; lpName
0x180003bbe  xor     r8d, r8d; dwFlags
0x180003bc1  xor     ecx, ecx; lpMutexAttributes
0x180003bc3  call    cs:__imp_CreateMutexExW
0x180003bc9  mov     rbx, rax
0x180003bcc  test    rax, rax
0x180003bcf  jnz     short loc_180003BDB
0x180003bd1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bd6  jmp     loc_180003E4A
0x180003bdb  xor     r8d, r8d; bAlertable
0x180003bde  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003be1  mov     rcx, rbx; hHandle
0x180003be4  call    cs:__imp_WaitForSingleObjectEx
0x180003bea  cmp     eax, 102h
0x180003bef  jz      short loc_180003C01
0x180003bf1  test    eax, 0FFFFFF7Fh
0x180003bf6  jnz     loc_180003E94
0x180003bfc  mov     rdi, rbx
0x180003bff  jmp     short loc_180003C03
0x180003c01  xor     edi, edi
0x180003c03  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003c08  mov     [rsp+280h+hObject], 0
0x180003c11  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c16  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c1b  mov     esi, eax
0x180003c1d  test    eax, eax
0x180003c1f  jns     short loc_180003C8B
0x180003c21  mov     rcx, [rbp+188h]; this
0x180003c28  mov     r9d, eax; char *
0x180003c2b  mov     edx, 66h ; 'f'; void *
0x180003c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c35  mov     rcx, [rbp+188h]; this
0x180003c3c  mov     r9d, esi; char *
0x180003c3f  mov     edx, 6Fh ; 'o'; void *
0x180003c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c49  mov     rcx, [rbp+188h]; this
0x180003c50  mov     r9d, esi; char *
0x180003c53  mov     edx, 12Eh; void *
0x180003c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c5d  test    rdi, rdi
0x180003c60  jz      short loc_180003C73
0x180003c62  mov     rcx, rdi; hMutex
0x180003c65  call    cs:__imp_ReleaseMutex
0x180003c6b  test    eax, eax
0x180003c6d  jz      loc_180003EA1
0x180003c73  mov     rcx, rbx; hObject
0x180003c76  call    cs:__imp_CloseHandle
0x180003c7c  test    eax, eax
0x180003c7e  jz      loc_180003EB3
0x180003c84  mov     eax, esi
0x180003c86  jmp     loc_180003E4A
0x180003c8b  mov     rax, [rsp+280h+hObject]
0x180003c90  lea     rcx, ds:0[rax*4]
0x180003c98  test    rcx, rcx
0x180003c9b  jz      short loc_180003CAB
0x180003c9d  mov     [r15], rcx
0x180003ca0  mov     eax, [rcx]
0x180003ca2  inc     eax
0x180003ca4  mov     [rcx], eax
0x180003ca6  jmp     loc_180003E20
0x180003cab  mov     rdx, r14; dwBytes
0x180003cae  mov     qword ptr [r15], 0
0x180003cb5  mov     ecx, 8; dwFlags
0x180003cba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003cbf  mov     r14, rax
0x180003cc2  test    rax, rax
0x180003cc5  jnz     short loc_180003CE5
0x180003cc7  mov     rcx, [rbp+188h]; this
0x180003cce  mov     esi, 8007000Eh
0x180003cd3  mov     r9d, esi; char *
0x180003cd6  mov     edx, 14Bh; void *
0x180003cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ce0  jmp     loc_180003D70
0x180003ce5  xorps   xmm0, xmm0
0x180003ce8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003cee  test    r14b, 3
0x180003cf2  jnz     loc_180003EC5
0x180003cf8  mov     r9, r14
0x180003cfb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d00  shr     r9, 2; unsigned __int64
0x180003d04  lea     rcx, [rsp+280h+hObject]; this
0x180003d09  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003d0e  mov     esi, eax
0x180003d10  test    eax, eax
0x180003d12  jns     loc_180003DB0
0x180003d18  mov     rcx, [rbp+188h]; this
0x180003d1f  mov     r9d, eax; char *
0x180003d22  mov     edx, 14Eh; void *
0x180003d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d2c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003d31  test    rcx, rcx
0x180003d34  jz      short loc_180003D44
0x180003d36  call    cs:__imp_CloseHandle
0x180003d3c  test    eax, eax
0x180003d3e  jz      loc_180003ECB
0x180003d44  mov     rcx, [rsp+280h+hObject]; hObject
0x180003d49  test    rcx, rcx
0x180003d4c  jz      short loc_180003D5C
0x180003d4e  call    cs:__imp_CloseHandle
0x180003d54  test    eax, eax
0x180003d56  jz      loc_180003EDD
0x180003d5c  call    cs:__imp_GetProcessHeap
0x180003d62  mov     r8, r14; lpMem
0x180003d65  xor     edx, edx; dwFlags
0x180003d67  mov     rcx, rax; hHeap
0x180003d6a  call    cs:__imp_HeapFree
0x180003d70  mov     rcx, [rbp+188h]; this
0x180003d77  mov     r9d, esi; char *
0x180003d7a  mov     edx, 137h; void *
0x180003d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d84  test    rdi, rdi
0x180003d87  jz      short loc_180003D9A
0x180003d89  mov     rcx, rdi; hMutex
0x180003d8c  call    cs:__imp_ReleaseMutex
0x180003d92  test    eax, eax
0x180003d94  jz      loc_180003EEF
0x180003d9a  mov     rcx, rbx; hObject
0x180003d9d  call    cs:__imp_CloseHandle
0x180003da3  test    eax, eax
0x180003da5  jz      loc_180003E82
0x180003dab  jmp     loc_180003C84
0x180003db0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003db5  lea     rcx, [r14+28h]; void *
0x180003db9  mov     dword ptr [r14], 1
0x180003dc0  xor     edx, edx; Val
0x180003dc2  mov     [r14+8], rbx
0x180003dc6  mov     r8d, 108h; Size
0x180003dcc  movdqu  xmmword ptr [r14+10h], xmm0
0x180003dd2  call    memset_0
0x180003dd7  xor     eax, eax
0x180003dd9  lea     rcx, [r14+28h]; this
0x180003ddd  mov     [r14+20h], rax
0x180003de1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003de6  lea     rbx, [r14+0E8h]
0x180003ded  xor     r8d, r8d; Flags
0x180003df0  mov     rcx, rbx; lpCriticalSection
0x180003df3  xor     edx, edx; dwSpinCount
0x180003df5  call    cs:__imp_InitializeCriticalSectionEx
0x180003dfb  mov     qword ptr [rbx+28h], 0
0x180003e03  mov     qword ptr [rbx+30h], 0
0x180003e0b  mov     qword ptr [rbx+38h], 0
0x180003e13  mov     qword ptr [rbx+40h], 0
0x180003e1b  xor     ebx, ebx
0x180003e1d  mov     [r15], r14
0x180003e20  test    rdi, rdi
0x180003e23  jz      short loc_180003E36
0x180003e25  mov     rcx, rdi; hMutex
0x180003e28  call    cs:__imp_ReleaseMutex
0x180003e2e  test    eax, eax
0x180003e30  jz      loc_180003F01
0x180003e36  test    rbx, rbx
0x180003e39  jz      short loc_180003E48
0x180003e3b  mov     rcx, rbx; hObject
0x180003e3e  call    cs:__imp_CloseHandle
0x180003e44  test    eax, eax
0x180003e46  jz      short loc_180003E70
0x180003e48  xor     eax, eax
0x180003e4a  mov     rcx, [rbp+180h+var_30]
0x180003e51  xor     rcx, rsp; StackCookie
0x180003e54  call    __security_check_cookie
0x180003e59  mov     rbx, [rsp+280h+arg_10]
0x180003e61  add     rsp, 260h
0x180003e68  pop     r15
0x180003e6a  pop     r14
0x180003e6c  pop     rdi
0x180003e6d  pop     rsi
0x180003e6e  pop     rbp
0x180003e6f  retn
0x180003e70  mov     rcx, [rbp+188h]; this
0x180003e77  mov     edx, 0A0Bh; void *
0x180003e7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e82  mov     rcx, [rbp+188h]; this
0x180003e89  mov     edx, 0A0Bh; void *
0x180003e8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e94  mov     rcx, [rbp+188h]; this
0x180003e9b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003ea1  mov     rcx, [rbp+188h]; this
0x180003ea8  mov     edx, 0A15h; void *
0x180003ead  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eb3  mov     rcx, [rbp+188h]; this
0x180003eba  mov     edx, 0A0Bh; void *
0x180003ebf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ec5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003ecb  mov     rcx, [rbp+188h]; this
0x180003ed2  mov     edx, 0A0Bh; void *
0x180003ed7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003edd  mov     rcx, [rbp+188h]; this
0x180003ee4  mov     edx, 0A0Bh; void *
0x180003ee9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003eef  mov     rcx, [rbp+188h]; this
0x180003ef6  mov     edx, 0A15h; void *
0x180003efb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f01  mov     rcx, [rbp+188h]; this
0x180003f08  mov     edx, 0A15h; void *
0x180003f0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
