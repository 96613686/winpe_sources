# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000cf30`
- end: `0x18000d2f7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000e24c`

## callees

- `0x180003f9c`
- `0x180004330`
- `0x1800048dc`
- `0x1800051fc`
- `0x180005a4c`
- `0x180005dcc`
- `0x180005f2c`
- `0x1800062ec`
- `0x1800062fc`
- `0x18000c968`
- `0x18000cf30`
- `0x18001200e`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d05a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d05a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d222`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d049`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d170`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d049`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d170`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d20c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000cfa7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000cfa7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000d1d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000d1d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cfc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cfc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d140`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d140`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d14e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d14e`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
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
0x18000cf30  mov     [rsp-8+arg_10], rbx
0x18000cf35  push    rbp
0x18000cf36  push    rsi
0x18000cf37  push    rdi
0x18000cf38  push    r14
0x18000cf3a  push    r15
0x18000cf3c  lea     rbp, [rsp-160h]
0x18000cf44  sub     rsp, 260h
0x18000cf4b  mov     rax, cs:__security_cookie
0x18000cf52  xor     rax, rsp
0x18000cf55  mov     [rbp+180h+var_30], rax
0x18000cf5c  mov     r15, rdx
0x18000cf5f  mov     qword ptr [rdx], 0
0x18000cf66  mov     rbx, rcx
0x18000cf69  call    cs:__imp_GetCurrentProcessId
0x18000cf6f  mov     r14d, 130h
0x18000cf75  mov     [rsp+280h+var_258], rbx
0x18000cf7a  mov     r9d, eax
0x18000cf7d  mov     [rsp+280h+var_260], r14d; int
0x18000cf82  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000cf89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cf8e  lea     edx, [r14-2Ch]; unsigned __int64
0x18000cf92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cf97  mov     r9d, 1F0001h; dwDesiredAccess
0x18000cf9d  lea     rdx, [rsp+280h+Name]; lpName
0x18000cfa2  xor     r8d, r8d; dwFlags
0x18000cfa5  xor     ecx, ecx; lpMutexAttributes
0x18000cfa7  call    cs:__imp_CreateMutexExW
0x18000cfad  mov     rbx, rax
0x18000cfb0  test    rax, rax
0x18000cfb3  jnz     short loc_18000CFBF
0x18000cfb5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000cfba  jmp     loc_18000D22E
0x18000cfbf  xor     r8d, r8d; bAlertable
0x18000cfc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cfc5  mov     rcx, rbx; hHandle
0x18000cfc8  call    cs:__imp_WaitForSingleObjectEx
0x18000cfce  cmp     eax, 102h
0x18000cfd3  jz      short loc_18000CFE5
0x18000cfd5  test    eax, 0FFFFFF7Fh
0x18000cfda  jnz     loc_18000D278
0x18000cfe0  mov     rdi, rbx
0x18000cfe3  jmp     short loc_18000CFE7
0x18000cfe5  xor     edi, edi
0x18000cfe7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000cfec  mov     [rsp+280h+hObject], 0
0x18000cff5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cffa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000cfff  mov     esi, eax
0x18000d001  test    eax, eax
0x18000d003  jns     short loc_18000D06F
0x18000d005  mov     rcx, [rbp+188h]; this
0x18000d00c  mov     r9d, eax; char *
0x18000d00f  mov     edx, 66h ; 'f'; void *
0x18000d014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d019  mov     rcx, [rbp+188h]; this
0x18000d020  mov     r9d, esi; char *
0x18000d023  mov     edx, 6Fh ; 'o'; void *
0x18000d028  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d02d  mov     rcx, [rbp+188h]; this
0x18000d034  mov     r9d, esi; char *
0x18000d037  mov     edx, 12Eh; void *
0x18000d03c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d041  test    rdi, rdi
0x18000d044  jz      short loc_18000D057
0x18000d046  mov     rcx, rdi; hMutex
0x18000d049  call    cs:__imp_ReleaseMutex
0x18000d04f  test    eax, eax
0x18000d051  jz      loc_18000D285
0x18000d057  mov     rcx, rbx; hObject
0x18000d05a  call    cs:__imp_CloseHandle
0x18000d060  test    eax, eax
0x18000d062  jz      loc_18000D297
0x18000d068  mov     eax, esi
0x18000d06a  jmp     loc_18000D22E
0x18000d06f  mov     rax, [rsp+280h+hObject]
0x18000d074  lea     rcx, ds:0[rax*4]
0x18000d07c  test    rcx, rcx
0x18000d07f  jz      short loc_18000D08F
0x18000d081  mov     [r15], rcx
0x18000d084  mov     eax, [rcx]
0x18000d086  inc     eax
0x18000d088  mov     [rcx], eax
0x18000d08a  jmp     loc_18000D204
0x18000d08f  mov     rdx, r14; dwBytes
0x18000d092  mov     qword ptr [r15], 0
0x18000d099  mov     ecx, 8; dwFlags
0x18000d09e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d0a3  mov     r14, rax
0x18000d0a6  test    rax, rax
0x18000d0a9  jnz     short loc_18000D0C9
0x18000d0ab  mov     rcx, [rbp+188h]; this
0x18000d0b2  mov     esi, 8007000Eh
0x18000d0b7  mov     r9d, esi; char *
0x18000d0ba  mov     edx, 14Bh; void *
0x18000d0bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0c4  jmp     loc_18000D154
0x18000d0c9  xorps   xmm0, xmm0
0x18000d0cc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000d0d2  test    r14b, 3
0x18000d0d6  jnz     loc_18000D2A9
0x18000d0dc  mov     r9, r14
0x18000d0df  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000d0e4  shr     r9, 2; unsigned __int64
0x18000d0e8  lea     rcx, [rsp+280h+hObject]; this
0x18000d0ed  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000d0f2  mov     esi, eax
0x18000d0f4  test    eax, eax
0x18000d0f6  jns     loc_18000D194
0x18000d0fc  mov     rcx, [rbp+188h]; this
0x18000d103  mov     r9d, eax; char *
0x18000d106  mov     edx, 14Eh; void *
0x18000d10b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d110  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000d115  test    rcx, rcx
0x18000d118  jz      short loc_18000D128
0x18000d11a  call    cs:__imp_CloseHandle
0x18000d120  test    eax, eax
0x18000d122  jz      loc_18000D2AF
0x18000d128  mov     rcx, [rsp+280h+hObject]; hObject
0x18000d12d  test    rcx, rcx
0x18000d130  jz      short loc_18000D140
0x18000d132  call    cs:__imp_CloseHandle
0x18000d138  test    eax, eax
0x18000d13a  jz      loc_18000D2C1
0x18000d140  call    cs:__imp_GetProcessHeap
0x18000d146  mov     r8, r14; lpMem
0x18000d149  xor     edx, edx; dwFlags
0x18000d14b  mov     rcx, rax; hHeap
0x18000d14e  call    cs:__imp_HeapFree
0x18000d154  mov     rcx, [rbp+188h]; this
0x18000d15b  mov     r9d, esi; char *
0x18000d15e  mov     edx, 137h; void *
0x18000d163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d168  test    rdi, rdi
0x18000d16b  jz      short loc_18000D17E
0x18000d16d  mov     rcx, rdi; hMutex
0x18000d170  call    cs:__imp_ReleaseMutex
0x18000d176  test    eax, eax
0x18000d178  jz      loc_18000D2D3
0x18000d17e  mov     rcx, rbx; hObject
0x18000d181  call    cs:__imp_CloseHandle
0x18000d187  test    eax, eax
0x18000d189  jz      loc_18000D266
0x18000d18f  jmp     loc_18000D068
0x18000d194  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000d199  lea     rcx, [r14+28h]; void *
0x18000d19d  mov     dword ptr [r14], 1
0x18000d1a4  xor     edx, edx; Val
0x18000d1a6  mov     [r14+8], rbx
0x18000d1aa  mov     r8d, 108h; Size
0x18000d1b0  movdqu  xmmword ptr [r14+10h], xmm0
0x18000d1b6  call    memset_0
0x18000d1bb  xor     eax, eax
0x18000d1bd  lea     rcx, [r14+28h]; this
0x18000d1c1  mov     [r14+20h], rax
0x18000d1c5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000d1ca  lea     rbx, [r14+0E8h]
0x18000d1d1  xor     r8d, r8d; Flags
0x18000d1d4  mov     rcx, rbx; lpCriticalSection
0x18000d1d7  xor     edx, edx; dwSpinCount
0x18000d1d9  call    cs:__imp_InitializeCriticalSectionEx
0x18000d1df  mov     qword ptr [rbx+28h], 0
0x18000d1e7  mov     qword ptr [rbx+30h], 0
0x18000d1ef  mov     qword ptr [rbx+38h], 0
0x18000d1f7  mov     qword ptr [rbx+40h], 0
0x18000d1ff  xor     ebx, ebx
0x18000d201  mov     [r15], r14
0x18000d204  test    rdi, rdi
0x18000d207  jz      short loc_18000D21A
0x18000d209  mov     rcx, rdi; hMutex
0x18000d20c  call    cs:__imp_ReleaseMutex
0x18000d212  test    eax, eax
0x18000d214  jz      loc_18000D2E5
0x18000d21a  test    rbx, rbx
0x18000d21d  jz      short loc_18000D22C
0x18000d21f  mov     rcx, rbx; hObject
0x18000d222  call    cs:__imp_CloseHandle
0x18000d228  test    eax, eax
0x18000d22a  jz      short loc_18000D254
0x18000d22c  xor     eax, eax
0x18000d22e  mov     rcx, [rbp+180h+var_30]
0x18000d235  xor     rcx, rsp; StackCookie
0x18000d238  call    __security_check_cookie
0x18000d23d  mov     rbx, [rsp+280h+arg_10]
0x18000d245  add     rsp, 260h
0x18000d24c  pop     r15
0x18000d24e  pop     r14
0x18000d250  pop     rdi
0x18000d251  pop     rsi
0x18000d252  pop     rbp
0x18000d253  retn
0x18000d254  mov     rcx, [rbp+188h]; this
0x18000d25b  mov     edx, 0A0Bh; void *
0x18000d260  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d266  mov     rcx, [rbp+188h]; this
0x18000d26d  mov     edx, 0A0Bh; void *
0x18000d272  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d278  mov     rcx, [rbp+188h]; this
0x18000d27f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000d285  mov     rcx, [rbp+188h]; this
0x18000d28c  mov     edx, 0A15h; void *
0x18000d291  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d297  mov     rcx, [rbp+188h]; this
0x18000d29e  mov     edx, 0A0Bh; void *
0x18000d2a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d2a9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d2af  mov     rcx, [rbp+188h]; this
0x18000d2b6  mov     edx, 0A0Bh; void *
0x18000d2bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d2c1  mov     rcx, [rbp+188h]; this
0x18000d2c8  mov     edx, 0A0Bh; void *
0x18000d2cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d2d3  mov     rcx, [rbp+188h]; this
0x18000d2da  mov     edx, 0A15h; void *
0x18000d2df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d2e5  mov     rcx, [rbp+188h]; this
0x18000d2ec  mov     edx, 0A15h; void *
0x18000d2f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
