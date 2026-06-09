# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004c9c`
- end: `0x180005063`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005844`

## callees

- `0x180002270`
- `0x180002be8`
- `0x180003d94`
- `0x180004c9c`
- `0x180005570`
- `0x180005a98`
- `0x180006b18`
- `0x180007e78`
- `0x180009984`
- `0x18000b73c`
- `0x18000bccc`
- `0x18000c57c`
- `0x18000c58c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004cd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004cd5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d13`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004d34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004f45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004db5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004edc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004db5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004edc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f8e`

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
0x180004c9c  mov     [rsp-8+arg_10], rbx
0x180004ca1  push    rbp
0x180004ca2  push    rsi
0x180004ca3  push    rdi
0x180004ca4  push    r14
0x180004ca6  push    r15
0x180004ca8  lea     rbp, [rsp-160h]
0x180004cb0  sub     rsp, 260h
0x180004cb7  mov     rax, cs:__security_cookie
0x180004cbe  xor     rax, rsp
0x180004cc1  mov     [rbp+180h+var_30], rax
0x180004cc8  mov     r15, rdx
0x180004ccb  mov     qword ptr [rdx], 0
0x180004cd2  mov     rbx, rcx
0x180004cd5  call    cs:__imp_GetCurrentProcessId
0x180004cdb  mov     r14d, 130h
0x180004ce1  mov     [rsp+280h+var_258], rbx
0x180004ce6  mov     r9d, eax
0x180004ce9  mov     [rsp+280h+var_260], r14d; int
0x180004cee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004cf5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004cfa  lea     edx, [r14-2Ch]; unsigned __int64
0x180004cfe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d03  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d09  lea     rdx, [rsp+280h+Name]; lpName
0x180004d0e  xor     r8d, r8d; dwFlags
0x180004d11  xor     ecx, ecx; lpMutexAttributes
0x180004d13  call    cs:__imp_CreateMutexExW
0x180004d19  mov     rbx, rax
0x180004d1c  test    rax, rax
0x180004d1f  jnz     short loc_180004D2B
0x180004d21  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d26  jmp     loc_180004F9A
0x180004d2b  xor     r8d, r8d; bAlertable
0x180004d2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004d31  mov     rcx, rbx; hHandle
0x180004d34  call    cs:__imp_WaitForSingleObjectEx
0x180004d3a  cmp     eax, 102h
0x180004d3f  jz      short loc_180004D51
0x180004d41  test    eax, 0FFFFFF7Fh
0x180004d46  jnz     loc_180004FE4
0x180004d4c  mov     rdi, rbx
0x180004d4f  jmp     short loc_180004D53
0x180004d51  xor     edi, edi
0x180004d53  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004d58  mov     [rsp+280h+hObject], 0
0x180004d61  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004d66  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004d6b  mov     esi, eax
0x180004d6d  test    eax, eax
0x180004d6f  jns     short loc_180004DDB
0x180004d71  mov     rcx, [rbp+188h]; this
0x180004d78  mov     r9d, eax; char *
0x180004d7b  mov     edx, 66h ; 'f'; void *
0x180004d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d85  mov     rcx, [rbp+188h]; this
0x180004d8c  mov     r9d, esi; char *
0x180004d8f  mov     edx, 6Fh ; 'o'; void *
0x180004d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d99  mov     rcx, [rbp+188h]; this
0x180004da0  mov     r9d, esi; char *
0x180004da3  mov     edx, 12Eh; void *
0x180004da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dad  test    rdi, rdi
0x180004db0  jz      short loc_180004DC3
0x180004db2  mov     rcx, rdi; hMutex
0x180004db5  call    cs:__imp_ReleaseMutex
0x180004dbb  test    eax, eax
0x180004dbd  jz      loc_180004FF1
0x180004dc3  mov     rcx, rbx; hObject
0x180004dc6  call    cs:__imp_CloseHandle
0x180004dcc  test    eax, eax
0x180004dce  jz      loc_180005003
0x180004dd4  mov     eax, esi
0x180004dd6  jmp     loc_180004F9A
0x180004ddb  mov     rax, [rsp+280h+hObject]
0x180004de0  lea     rcx, ds:0[rax*4]
0x180004de8  test    rcx, rcx
0x180004deb  jz      short loc_180004DFB
0x180004ded  mov     [r15], rcx
0x180004df0  mov     eax, [rcx]
0x180004df2  inc     eax
0x180004df4  mov     [rcx], eax
0x180004df6  jmp     loc_180004F70
0x180004dfb  mov     rdx, r14; dwBytes
0x180004dfe  mov     qword ptr [r15], 0
0x180004e05  mov     ecx, 8; dwFlags
0x180004e0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e0f  mov     r14, rax
0x180004e12  test    rax, rax
0x180004e15  jnz     short loc_180004E35
0x180004e17  mov     rcx, [rbp+188h]; this
0x180004e1e  mov     esi, 8007000Eh
0x180004e23  mov     r9d, esi; char *
0x180004e26  mov     edx, 14Bh; void *
0x180004e2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e30  jmp     loc_180004EC0
0x180004e35  xorps   xmm0, xmm0
0x180004e38  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004e3e  test    r14b, 3
0x180004e42  jnz     loc_180005015
0x180004e48  mov     r9, r14
0x180004e4b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004e50  shr     r9, 2; unsigned __int64
0x180004e54  lea     rcx, [rsp+280h+hObject]; this
0x180004e59  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004e5e  mov     esi, eax
0x180004e60  test    eax, eax
0x180004e62  jns     loc_180004F00
0x180004e68  mov     rcx, [rbp+188h]; this
0x180004e6f  mov     r9d, eax; char *
0x180004e72  mov     edx, 14Eh; void *
0x180004e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e7c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004e81  test    rcx, rcx
0x180004e84  jz      short loc_180004E94
0x180004e86  call    cs:__imp_CloseHandle
0x180004e8c  test    eax, eax
0x180004e8e  jz      loc_18000501B
0x180004e94  mov     rcx, [rsp+280h+hObject]; hObject
0x180004e99  test    rcx, rcx
0x180004e9c  jz      short loc_180004EAC
0x180004e9e  call    cs:__imp_CloseHandle
0x180004ea4  test    eax, eax
0x180004ea6  jz      loc_18000502D
0x180004eac  call    cs:__imp_GetProcessHeap
0x180004eb2  mov     r8, r14; lpMem
0x180004eb5  xor     edx, edx; dwFlags
0x180004eb7  mov     rcx, rax; hHeap
0x180004eba  call    cs:__imp_HeapFree
0x180004ec0  mov     rcx, [rbp+188h]; this
0x180004ec7  mov     r9d, esi; char *
0x180004eca  mov     edx, 137h; void *
0x180004ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ed4  test    rdi, rdi
0x180004ed7  jz      short loc_180004EEA
0x180004ed9  mov     rcx, rdi; hMutex
0x180004edc  call    cs:__imp_ReleaseMutex
0x180004ee2  test    eax, eax
0x180004ee4  jz      loc_18000503F
0x180004eea  mov     rcx, rbx; hObject
0x180004eed  call    cs:__imp_CloseHandle
0x180004ef3  test    eax, eax
0x180004ef5  jz      loc_180004FD2
0x180004efb  jmp     loc_180004DD4
0x180004f00  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004f05  lea     rcx, [r14+28h]; void *
0x180004f09  mov     dword ptr [r14], 1
0x180004f10  xor     edx, edx; Val
0x180004f12  mov     [r14+8], rbx
0x180004f16  mov     r8d, 108h; Size
0x180004f1c  movdqu  xmmword ptr [r14+10h], xmm0
0x180004f22  call    memset_0
0x180004f27  xor     eax, eax
0x180004f29  lea     rcx, [r14+28h]; this
0x180004f2d  mov     [r14+20h], rax
0x180004f31  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004f36  lea     rbx, [r14+0E8h]
0x180004f3d  xor     r8d, r8d; Flags
0x180004f40  mov     rcx, rbx; lpCriticalSection
0x180004f43  xor     edx, edx; dwSpinCount
0x180004f45  call    cs:__imp_InitializeCriticalSectionEx
0x180004f4b  mov     qword ptr [rbx+28h], 0
0x180004f53  mov     qword ptr [rbx+30h], 0
0x180004f5b  mov     qword ptr [rbx+38h], 0
0x180004f63  mov     qword ptr [rbx+40h], 0
0x180004f6b  xor     ebx, ebx
0x180004f6d  mov     [r15], r14
0x180004f70  test    rdi, rdi
0x180004f73  jz      short loc_180004F86
0x180004f75  mov     rcx, rdi; hMutex
0x180004f78  call    cs:__imp_ReleaseMutex
0x180004f7e  test    eax, eax
0x180004f80  jz      loc_180005051
0x180004f86  test    rbx, rbx
0x180004f89  jz      short loc_180004F98
0x180004f8b  mov     rcx, rbx; hObject
0x180004f8e  call    cs:__imp_CloseHandle
0x180004f94  test    eax, eax
0x180004f96  jz      short loc_180004FC0
0x180004f98  xor     eax, eax
0x180004f9a  mov     rcx, [rbp+180h+var_30]
0x180004fa1  xor     rcx, rsp; StackCookie
0x180004fa4  call    __security_check_cookie
0x180004fa9  mov     rbx, [rsp+280h+arg_10]
0x180004fb1  add     rsp, 260h
0x180004fb8  pop     r15
0x180004fba  pop     r14
0x180004fbc  pop     rdi
0x180004fbd  pop     rsi
0x180004fbe  pop     rbp
0x180004fbf  retn
0x180004fc0  mov     rcx, [rbp+188h]; this
0x180004fc7  mov     edx, 0A0Bh; void *
0x180004fcc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fd2  mov     rcx, [rbp+188h]; this
0x180004fd9  mov     edx, 0A0Bh; void *
0x180004fde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fe4  mov     rcx, [rbp+188h]; this
0x180004feb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004ff1  mov     rcx, [rbp+188h]; this
0x180004ff8  mov     edx, 0A15h; void *
0x180004ffd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005003  mov     rcx, [rbp+188h]; this
0x18000500a  mov     edx, 0A0Bh; void *
0x18000500f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005015  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000501b  mov     rcx, [rbp+188h]; this
0x180005022  mov     edx, 0A0Bh; void *
0x180005027  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000502d  mov     rcx, [rbp+188h]; this
0x180005034  mov     edx, 0A0Bh; void *
0x180005039  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000503f  mov     rcx, [rbp+188h]; this
0x180005046  mov     edx, 0A15h; void *
0x18000504b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005051  mov     rcx, [rbp+188h]; this
0x180005058  mov     edx, 0A15h; void *
0x18000505d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
