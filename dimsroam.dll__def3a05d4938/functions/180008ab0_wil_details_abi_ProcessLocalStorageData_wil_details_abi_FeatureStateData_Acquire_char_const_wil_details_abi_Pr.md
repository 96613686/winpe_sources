# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008ab0`
- end: `0x180008e77`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009154`

## callees

- `0x180007ffc`
- `0x180008ab0`
- `0x180008e80`
- `0x1800092e4`
- `0x180009c08`
- `0x18000a7f8`
- `0x18000ba90`
- `0x18000bf60`
- `0x18000c268`
- `0x18000ca3c`
- `0x18000ca4c`
- `0x18000d89e`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008da2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008da2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b48`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008d59`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008d59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008d8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008d8c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008b27`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008b27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cc0`

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
0x180008ab0  mov     [rsp-8+arg_10], rbx
0x180008ab5  push    rbp
0x180008ab6  push    rsi
0x180008ab7  push    rdi
0x180008ab8  push    r14
0x180008aba  push    r15
0x180008abc  lea     rbp, [rsp-160h]
0x180008ac4  sub     rsp, 260h
0x180008acb  mov     rax, cs:__security_cookie
0x180008ad2  xor     rax, rsp
0x180008ad5  mov     [rbp+180h+var_30], rax
0x180008adc  mov     r15, rdx
0x180008adf  mov     qword ptr [rdx], 0
0x180008ae6  mov     rbx, rcx
0x180008ae9  call    cs:__imp_GetCurrentProcessId
0x180008aef  mov     r14d, 130h
0x180008af5  mov     [rsp+280h+var_258], rbx
0x180008afa  mov     r9d, eax
0x180008afd  mov     [rsp+280h+var_260], r14d; int
0x180008b02  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008b09  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008b0e  lea     edx, [r14-2Ch]; unsigned __int64
0x180008b12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008b17  mov     r9d, 1F0001h; dwDesiredAccess
0x180008b1d  lea     rdx, [rsp+280h+Name]; lpName
0x180008b22  xor     r8d, r8d; dwFlags
0x180008b25  xor     ecx, ecx; lpMutexAttributes
0x180008b27  call    cs:__imp_CreateMutexExW
0x180008b2d  mov     rbx, rax
0x180008b30  test    rax, rax
0x180008b33  jnz     short loc_180008B3F
0x180008b35  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008b3a  jmp     loc_180008DAE
0x180008b3f  xor     r8d, r8d; bAlertable
0x180008b42  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008b45  mov     rcx, rbx; hHandle
0x180008b48  call    cs:__imp_WaitForSingleObjectEx
0x180008b4e  cmp     eax, 102h
0x180008b53  jz      short loc_180008B65
0x180008b55  test    eax, 0FFFFFF7Fh
0x180008b5a  jnz     loc_180008DF8
0x180008b60  mov     rdi, rbx
0x180008b63  jmp     short loc_180008B67
0x180008b65  xor     edi, edi
0x180008b67  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008b6c  mov     [rsp+280h+hObject], 0
0x180008b75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008b7a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008b7f  mov     esi, eax
0x180008b81  test    eax, eax
0x180008b83  jns     short loc_180008BEF
0x180008b85  mov     rcx, [rbp+188h]; this
0x180008b8c  mov     r9d, eax; char *
0x180008b8f  mov     edx, 66h ; 'f'; void *
0x180008b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b99  mov     rcx, [rbp+188h]; this
0x180008ba0  mov     r9d, esi; char *
0x180008ba3  mov     edx, 6Fh ; 'o'; void *
0x180008ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bad  mov     rcx, [rbp+188h]; this
0x180008bb4  mov     r9d, esi; char *
0x180008bb7  mov     edx, 12Eh; void *
0x180008bbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bc1  test    rdi, rdi
0x180008bc4  jz      short loc_180008BD7
0x180008bc6  mov     rcx, rdi; hMutex
0x180008bc9  call    cs:__imp_ReleaseMutex
0x180008bcf  test    eax, eax
0x180008bd1  jz      loc_180008E05
0x180008bd7  mov     rcx, rbx; hObject
0x180008bda  call    cs:__imp_CloseHandle
0x180008be0  test    eax, eax
0x180008be2  jz      loc_180008E17
0x180008be8  mov     eax, esi
0x180008bea  jmp     loc_180008DAE
0x180008bef  mov     rax, [rsp+280h+hObject]
0x180008bf4  lea     rcx, ds:0[rax*4]
0x180008bfc  test    rcx, rcx
0x180008bff  jz      short loc_180008C0F
0x180008c01  mov     [r15], rcx
0x180008c04  mov     eax, [rcx]
0x180008c06  inc     eax
0x180008c08  mov     [rcx], eax
0x180008c0a  jmp     loc_180008D84
0x180008c0f  mov     rdx, r14; dwBytes
0x180008c12  mov     qword ptr [r15], 0
0x180008c19  mov     ecx, 8; dwFlags
0x180008c1e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008c23  mov     r14, rax
0x180008c26  test    rax, rax
0x180008c29  jnz     short loc_180008C49
0x180008c2b  mov     rcx, [rbp+188h]; this
0x180008c32  mov     esi, 8007000Eh
0x180008c37  mov     r9d, esi; char *
0x180008c3a  mov     edx, 14Bh; void *
0x180008c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c44  jmp     loc_180008CD4
0x180008c49  xorps   xmm0, xmm0
0x180008c4c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008c52  test    r14b, 3
0x180008c56  jnz     loc_180008E29
0x180008c5c  mov     r9, r14
0x180008c5f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008c64  shr     r9, 2; unsigned __int64
0x180008c68  lea     rcx, [rsp+280h+hObject]; this
0x180008c6d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008c72  mov     esi, eax
0x180008c74  test    eax, eax
0x180008c76  jns     loc_180008D14
0x180008c7c  mov     rcx, [rbp+188h]; this
0x180008c83  mov     r9d, eax; char *
0x180008c86  mov     edx, 14Eh; void *
0x180008c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c90  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008c95  test    rcx, rcx
0x180008c98  jz      short loc_180008CA8
0x180008c9a  call    cs:__imp_CloseHandle
0x180008ca0  test    eax, eax
0x180008ca2  jz      loc_180008E2F
0x180008ca8  mov     rcx, [rsp+280h+hObject]; hObject
0x180008cad  test    rcx, rcx
0x180008cb0  jz      short loc_180008CC0
0x180008cb2  call    cs:__imp_CloseHandle
0x180008cb8  test    eax, eax
0x180008cba  jz      loc_180008E41
0x180008cc0  call    cs:__imp_GetProcessHeap
0x180008cc6  mov     r8, r14; lpMem
0x180008cc9  xor     edx, edx; dwFlags
0x180008ccb  mov     rcx, rax; hHeap
0x180008cce  call    cs:__imp_HeapFree
0x180008cd4  mov     rcx, [rbp+188h]; this
0x180008cdb  mov     r9d, esi; char *
0x180008cde  mov     edx, 137h; void *
0x180008ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ce8  test    rdi, rdi
0x180008ceb  jz      short loc_180008CFE
0x180008ced  mov     rcx, rdi; hMutex
0x180008cf0  call    cs:__imp_ReleaseMutex
0x180008cf6  test    eax, eax
0x180008cf8  jz      loc_180008E53
0x180008cfe  mov     rcx, rbx; hObject
0x180008d01  call    cs:__imp_CloseHandle
0x180008d07  test    eax, eax
0x180008d09  jz      loc_180008DE6
0x180008d0f  jmp     loc_180008BE8
0x180008d14  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008d19  lea     rcx, [r14+28h]; void *
0x180008d1d  mov     dword ptr [r14], 1
0x180008d24  xor     edx, edx; Val
0x180008d26  mov     [r14+8], rbx
0x180008d2a  mov     r8d, 108h; Size
0x180008d30  movdqu  xmmword ptr [r14+10h], xmm0
0x180008d36  call    memset_0
0x180008d3b  xor     eax, eax
0x180008d3d  lea     rcx, [r14+28h]; this
0x180008d41  mov     [r14+20h], rax
0x180008d45  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008d4a  lea     rbx, [r14+0E8h]
0x180008d51  xor     r8d, r8d; Flags
0x180008d54  mov     rcx, rbx; lpCriticalSection
0x180008d57  xor     edx, edx; dwSpinCount
0x180008d59  call    cs:__imp_InitializeCriticalSectionEx
0x180008d5f  mov     qword ptr [rbx+28h], 0
0x180008d67  mov     qword ptr [rbx+30h], 0
0x180008d6f  mov     qword ptr [rbx+38h], 0
0x180008d77  mov     qword ptr [rbx+40h], 0
0x180008d7f  xor     ebx, ebx
0x180008d81  mov     [r15], r14
0x180008d84  test    rdi, rdi
0x180008d87  jz      short loc_180008D9A
0x180008d89  mov     rcx, rdi; hMutex
0x180008d8c  call    cs:__imp_ReleaseMutex
0x180008d92  test    eax, eax
0x180008d94  jz      loc_180008E65
0x180008d9a  test    rbx, rbx
0x180008d9d  jz      short loc_180008DAC
0x180008d9f  mov     rcx, rbx; hObject
0x180008da2  call    cs:__imp_CloseHandle
0x180008da8  test    eax, eax
0x180008daa  jz      short loc_180008DD4
0x180008dac  xor     eax, eax
0x180008dae  mov     rcx, [rbp+180h+var_30]
0x180008db5  xor     rcx, rsp; StackCookie
0x180008db8  call    __security_check_cookie
0x180008dbd  mov     rbx, [rsp+280h+arg_10]
0x180008dc5  add     rsp, 260h
0x180008dcc  pop     r15
0x180008dce  pop     r14
0x180008dd0  pop     rdi
0x180008dd1  pop     rsi
0x180008dd2  pop     rbp
0x180008dd3  retn
0x180008dd4  mov     rcx, [rbp+188h]; this
0x180008ddb  mov     edx, 0A0Bh; void *
0x180008de0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008de6  mov     rcx, [rbp+188h]; this
0x180008ded  mov     edx, 0A0Bh; void *
0x180008df2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008df8  mov     rcx, [rbp+188h]; this
0x180008dff  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008e05  mov     rcx, [rbp+188h]; this
0x180008e0c  mov     edx, 0A15h; void *
0x180008e11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e17  mov     rcx, [rbp+188h]; this
0x180008e1e  mov     edx, 0A0Bh; void *
0x180008e23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e29  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008e2f  mov     rcx, [rbp+188h]; this
0x180008e36  mov     edx, 0A0Bh; void *
0x180008e3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e41  mov     rcx, [rbp+188h]; this
0x180008e48  mov     edx, 0A0Bh; void *
0x180008e4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e53  mov     rcx, [rbp+188h]; this
0x180008e5a  mov     edx, 0A15h; void *
0x180008e5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e65  mov     rcx, [rbp+188h]; this
0x180008e6c  mov     edx, 0A15h; void *
0x180008e71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
