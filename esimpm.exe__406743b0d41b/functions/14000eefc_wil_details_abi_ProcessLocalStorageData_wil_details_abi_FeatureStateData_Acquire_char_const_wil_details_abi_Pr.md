# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000eefc`
- end: `0x14000f2c3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000f594`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x14000dfb8`
- `0x14000eefc`
- `0x14000f2cc`
- `0x14000f7e8`
- `0x140010118`
- `0x140010df8`
- `0x140012554`
- `0x140013048`
- `0x1400134cc`
- `0x140013d7c`
- `0x140013d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000f1a5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000f1a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f015`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f13c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f1d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f015`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f13c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000f1d8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ef73`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ef73`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ef94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ef94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f11a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f11a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f10c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f10c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000ef35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000ef35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f14d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f1ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f14d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f1ee`

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
  unsigned int v25; // r8d
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
0x14000eefc  mov     [rsp-8+arg_10], rbx
0x14000ef01  push    rbp
0x14000ef02  push    rsi
0x14000ef03  push    rdi
0x14000ef04  push    r14
0x14000ef06  push    r15
0x14000ef08  lea     rbp, [rsp-160h]
0x14000ef10  sub     rsp, 260h
0x14000ef17  mov     rax, cs:__security_cookie
0x14000ef1e  xor     rax, rsp
0x14000ef21  mov     [rbp+180h+var_30], rax
0x14000ef28  mov     r15, rdx
0x14000ef2b  mov     qword ptr [rdx], 0
0x14000ef32  mov     rbx, rcx
0x14000ef35  call    cs:__imp_GetCurrentProcessId
0x14000ef3b  mov     r14d, 130h
0x14000ef41  mov     [rsp+280h+var_258], rbx
0x14000ef46  mov     r9d, eax
0x14000ef49  mov     [rsp+280h+var_260], r14d; int
0x14000ef4e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000ef55  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ef5a  lea     edx, [r14-2Ch]; unsigned __int64
0x14000ef5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ef63  mov     r9d, 1F0001h; dwDesiredAccess
0x14000ef69  lea     rdx, [rsp+280h+Name]; lpName
0x14000ef6e  xor     r8d, r8d; dwFlags
0x14000ef71  xor     ecx, ecx; lpMutexAttributes
0x14000ef73  call    cs:__imp_CreateMutexExW
0x14000ef79  mov     rbx, rax
0x14000ef7c  test    rax, rax
0x14000ef7f  jnz     short loc_14000EF8B
0x14000ef81  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000ef86  jmp     loc_14000F1FA
0x14000ef8b  xor     r8d, r8d; bAlertable
0x14000ef8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000ef91  mov     rcx, rbx; hHandle
0x14000ef94  call    cs:__imp_WaitForSingleObjectEx
0x14000ef9a  cmp     eax, 102h
0x14000ef9f  jz      short loc_14000EFB1
0x14000efa1  test    eax, 0FFFFFF7Fh
0x14000efa6  jnz     loc_14000F244
0x14000efac  mov     rdi, rbx
0x14000efaf  jmp     short loc_14000EFB3
0x14000efb1  xor     edi, edi
0x14000efb3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000efb8  mov     [rsp+280h+hObject], 0
0x14000efc1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000efc6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000efcb  mov     esi, eax
0x14000efcd  test    eax, eax
0x14000efcf  jns     short loc_14000F03B
0x14000efd1  mov     rcx, [rbp+188h]; this
0x14000efd8  mov     r9d, eax; char *
0x14000efdb  mov     edx, 66h ; 'f'; void *
0x14000efe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000efe5  mov     rcx, [rbp+188h]; this
0x14000efec  mov     r9d, esi; char *
0x14000efef  mov     edx, 6Fh ; 'o'; void *
0x14000eff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000eff9  mov     rcx, [rbp+188h]; this
0x14000f000  mov     r9d, esi; char *
0x14000f003  mov     edx, 12Eh; void *
0x14000f008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f00d  test    rdi, rdi
0x14000f010  jz      short loc_14000F023
0x14000f012  mov     rcx, rdi; hMutex
0x14000f015  call    cs:__imp_ReleaseMutex
0x14000f01b  test    eax, eax
0x14000f01d  jz      loc_14000F251
0x14000f023  mov     rcx, rbx; hObject
0x14000f026  call    cs:__imp_CloseHandle
0x14000f02c  test    eax, eax
0x14000f02e  jz      loc_14000F263
0x14000f034  mov     eax, esi
0x14000f036  jmp     loc_14000F1FA
0x14000f03b  mov     rax, [rsp+280h+hObject]
0x14000f040  lea     rcx, ds:0[rax*4]
0x14000f048  test    rcx, rcx
0x14000f04b  jz      short loc_14000F05B
0x14000f04d  mov     [r15], rcx
0x14000f050  mov     eax, [rcx]
0x14000f052  inc     eax
0x14000f054  mov     [rcx], eax
0x14000f056  jmp     loc_14000F1D0
0x14000f05b  mov     rdx, r14; dwBytes
0x14000f05e  mov     qword ptr [r15], 0
0x14000f065  mov     ecx, 8; dwFlags
0x14000f06a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000f06f  mov     r14, rax
0x14000f072  test    rax, rax
0x14000f075  jnz     short loc_14000F095
0x14000f077  mov     rcx, [rbp+188h]; this
0x14000f07e  mov     esi, 8007000Eh
0x14000f083  mov     r9d, esi; char *
0x14000f086  mov     edx, 14Bh; void *
0x14000f08b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f090  jmp     loc_14000F120
0x14000f095  xorps   xmm0, xmm0
0x14000f098  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000f09e  test    r14b, 3
0x14000f0a2  jnz     loc_14000F275
0x14000f0a8  mov     r9, r14
0x14000f0ab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000f0b0  shr     r9, 2; unsigned __int64
0x14000f0b4  lea     rcx, [rsp+280h+hObject]; this
0x14000f0b9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000f0be  mov     esi, eax
0x14000f0c0  test    eax, eax
0x14000f0c2  jns     loc_14000F160
0x14000f0c8  mov     rcx, [rbp+188h]; this
0x14000f0cf  mov     r9d, eax; char *
0x14000f0d2  mov     edx, 14Eh; void *
0x14000f0d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f0dc  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000f0e1  test    rcx, rcx
0x14000f0e4  jz      short loc_14000F0F4
0x14000f0e6  call    cs:__imp_CloseHandle
0x14000f0ec  test    eax, eax
0x14000f0ee  jz      loc_14000F27B
0x14000f0f4  mov     rcx, [rsp+280h+hObject]; hObject
0x14000f0f9  test    rcx, rcx
0x14000f0fc  jz      short loc_14000F10C
0x14000f0fe  call    cs:__imp_CloseHandle
0x14000f104  test    eax, eax
0x14000f106  jz      loc_14000F28D
0x14000f10c  call    cs:__imp_GetProcessHeap
0x14000f112  mov     r8, r14; lpMem
0x14000f115  xor     edx, edx; dwFlags
0x14000f117  mov     rcx, rax; hHeap
0x14000f11a  call    cs:__imp_HeapFree
0x14000f120  mov     rcx, [rbp+188h]; this
0x14000f127  mov     r9d, esi; char *
0x14000f12a  mov     edx, 137h; void *
0x14000f12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f134  test    rdi, rdi
0x14000f137  jz      short loc_14000F14A
0x14000f139  mov     rcx, rdi; hMutex
0x14000f13c  call    cs:__imp_ReleaseMutex
0x14000f142  test    eax, eax
0x14000f144  jz      loc_14000F29F
0x14000f14a  mov     rcx, rbx; hObject
0x14000f14d  call    cs:__imp_CloseHandle
0x14000f153  test    eax, eax
0x14000f155  jz      loc_14000F232
0x14000f15b  jmp     loc_14000F034
0x14000f160  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000f165  lea     rcx, [r14+28h]; void *
0x14000f169  mov     dword ptr [r14], 1
0x14000f170  xor     edx, edx; Val
0x14000f172  mov     [r14+8], rbx
0x14000f176  mov     r8d, 108h; Size
0x14000f17c  movdqu  xmmword ptr [r14+10h], xmm0
0x14000f182  call    memset_0
0x14000f187  xor     eax, eax
0x14000f189  lea     rcx, [r14+28h]; this
0x14000f18d  mov     [r14+20h], rax
0x14000f191  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000f196  lea     rbx, [r14+0E8h]
0x14000f19d  xor     r8d, r8d; Flags
0x14000f1a0  mov     rcx, rbx; lpCriticalSection
0x14000f1a3  xor     edx, edx; dwSpinCount
0x14000f1a5  call    cs:__imp_InitializeCriticalSectionEx
0x14000f1ab  mov     qword ptr [rbx+28h], 0
0x14000f1b3  mov     qword ptr [rbx+30h], 0
0x14000f1bb  mov     qword ptr [rbx+38h], 0
0x14000f1c3  mov     qword ptr [rbx+40h], 0
0x14000f1cb  xor     ebx, ebx
0x14000f1cd  mov     [r15], r14
0x14000f1d0  test    rdi, rdi
0x14000f1d3  jz      short loc_14000F1E6
0x14000f1d5  mov     rcx, rdi; hMutex
0x14000f1d8  call    cs:__imp_ReleaseMutex
0x14000f1de  test    eax, eax
0x14000f1e0  jz      loc_14000F2B1
0x14000f1e6  test    rbx, rbx
0x14000f1e9  jz      short loc_14000F1F8
0x14000f1eb  mov     rcx, rbx; hObject
0x14000f1ee  call    cs:__imp_CloseHandle
0x14000f1f4  test    eax, eax
0x14000f1f6  jz      short loc_14000F220
0x14000f1f8  xor     eax, eax
0x14000f1fa  mov     rcx, [rbp+180h+var_30]
0x14000f201  xor     rcx, rsp; StackCookie
0x14000f204  call    __security_check_cookie
0x14000f209  mov     rbx, [rsp+280h+arg_10]
0x14000f211  add     rsp, 260h
0x14000f218  pop     r15
0x14000f21a  pop     r14
0x14000f21c  pop     rdi
0x14000f21d  pop     rsi
0x14000f21e  pop     rbp
0x14000f21f  retn
0x14000f220  mov     rcx, [rbp+188h]; this
0x14000f227  mov     edx, 0A0Bh; void *
0x14000f22c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f232  mov     rcx, [rbp+188h]; this
0x14000f239  mov     edx, 0A0Bh; void *
0x14000f23e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f244  mov     rcx, [rbp+188h]; this
0x14000f24b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000f251  mov     rcx, [rbp+188h]; this
0x14000f258  mov     edx, 0A15h; void *
0x14000f25d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f263  mov     rcx, [rbp+188h]; this
0x14000f26a  mov     edx, 0A0Bh; void *
0x14000f26f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f275  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000f27b  mov     rcx, [rbp+188h]; this
0x14000f282  mov     edx, 0A0Bh; void *
0x14000f287  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f28d  mov     rcx, [rbp+188h]; this
0x14000f294  mov     edx, 0A0Bh; void *
0x14000f299  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f29f  mov     rcx, [rbp+188h]; this
0x14000f2a6  mov     edx, 0A15h; void *
0x14000f2ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000f2b1  mov     rcx, [rbp+188h]; this
0x14000f2b8  mov     edx, 0A15h; void *
0x14000f2bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
