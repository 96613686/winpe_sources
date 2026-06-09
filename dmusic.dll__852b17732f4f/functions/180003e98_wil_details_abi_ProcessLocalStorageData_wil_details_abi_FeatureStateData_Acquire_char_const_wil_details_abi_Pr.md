# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e98`
- end: `0x180004289`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004584`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x180003004`
- `0x180003e98`
- `0x180004290`
- `0x1800047d8`
- `0x180005108`
- `0x18000603c`
- `0x180007684`
- `0x18000818c`
- `0x1800085ec`
- `0x180008ebc`
- `0x180008ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f0f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004102`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000419e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004102`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000419e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000416b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000416b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041b4`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180003e98  mov     [rsp-8+arg_10], rbx
0x180003e9d  push    rbp
0x180003e9e  push    rsi
0x180003e9f  push    rdi
0x180003ea0  push    r14
0x180003ea2  push    r15
0x180003ea4  lea     rbp, [rsp-160h]
0x180003eac  sub     rsp, 260h
0x180003eb3  mov     rax, cs:__security_cookie
0x180003eba  xor     rax, rsp
0x180003ebd  mov     [rbp+180h+var_30], rax
0x180003ec4  mov     r15, rdx
0x180003ec7  mov     qword ptr [rdx], 0
0x180003ece  mov     rbx, rcx
0x180003ed1  call    cs:__imp_GetCurrentProcessId
0x180003ed7  mov     r14d, 130h
0x180003edd  mov     [rsp+280h+var_258], rbx
0x180003ee2  mov     r9d, eax
0x180003ee5  mov     [rsp+280h+var_260], r14d; int
0x180003eea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ef1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ef6  lea     edx, [r14-2Ch]; unsigned __int64
0x180003efa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003eff  mov     r9d, 1F0001h; dwDesiredAccess
0x180003f05  lea     rdx, [rsp+280h+Name]; lpName
0x180003f0a  xor     r8d, r8d; dwFlags
0x180003f0d  xor     ecx, ecx; lpMutexAttributes
0x180003f0f  call    cs:__imp_CreateMutexExW
0x180003f15  mov     rbx, rax
0x180003f18  test    rax, rax
0x180003f1b  jnz     short loc_180003F27
0x180003f1d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f22  jmp     loc_1800041C0
0x180003f27  xor     r8d, r8d; bAlertable
0x180003f2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003f2d  mov     rcx, rbx; hHandle
0x180003f30  call    cs:__imp_WaitForSingleObjectEx
0x180003f36  cmp     eax, 102h
0x180003f3b  jz      short loc_180003F4D
0x180003f3d  test    eax, 0FFFFFF7Fh
0x180003f42  jnz     loc_18000420A
0x180003f48  mov     rdi, rbx
0x180003f4b  jmp     short loc_180003F4F
0x180003f4d  xor     edi, edi
0x180003f4f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f54  mov     [rsp+280h+hObject], 0
0x180003f5d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f62  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003f67  mov     esi, eax
0x180003f69  test    eax, eax
0x180003f6b  jns     short loc_180003FEC
0x180003f6d  mov     rcx, [rbp+188h]; this
0x180003f74  lea     r8, aWil; "wil"
0x180003f7b  mov     r9d, eax; char *
0x180003f7e  mov     edx, 66h ; 'f'; void *
0x180003f83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f88  mov     rcx, [rbp+188h]; this
0x180003f8f  lea     r8, aWil; "wil"
0x180003f96  mov     r9d, esi; char *
0x180003f99  mov     edx, 6Fh ; 'o'; void *
0x180003f9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fa3  mov     rcx, [rbp+188h]; this
0x180003faa  lea     r8, aWil; "wil"
0x180003fb1  mov     r9d, esi; char *
0x180003fb4  mov     edx, 12Eh; void *
0x180003fb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fbe  test    rdi, rdi
0x180003fc1  jz      short loc_180003FD4
0x180003fc3  mov     rcx, rdi; hMutex
0x180003fc6  call    cs:__imp_ReleaseMutex
0x180003fcc  test    eax, eax
0x180003fce  jz      loc_180004217
0x180003fd4  mov     rcx, rbx; hObject
0x180003fd7  call    cs:__imp_CloseHandle
0x180003fdd  test    eax, eax
0x180003fdf  jz      loc_180004229
0x180003fe5  mov     eax, esi
0x180003fe7  jmp     loc_1800041C0
0x180003fec  mov     rax, [rsp+280h+hObject]
0x180003ff1  lea     rcx, ds:0[rax*4]
0x180003ff9  test    rcx, rcx
0x180003ffc  jz      short loc_18000400C
0x180003ffe  mov     [r15], rcx
0x180004001  mov     eax, [rcx]
0x180004003  inc     eax
0x180004005  mov     [rcx], eax
0x180004007  jmp     loc_180004196
0x18000400c  mov     rdx, r14; dwBytes
0x18000400f  mov     qword ptr [r15], 0
0x180004016  mov     ecx, 8; dwFlags
0x18000401b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004020  mov     r14, rax
0x180004023  test    rax, rax
0x180004026  jnz     short loc_18000404D
0x180004028  mov     rcx, [rbp+188h]; this
0x18000402f  lea     r8, aWil; "wil"
0x180004036  mov     esi, 8007000Eh
0x18000403b  mov     edx, 14Bh; void *
0x180004040  mov     r9d, esi; char *
0x180004043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004048  jmp     loc_1800040DF
0x18000404d  xorps   xmm0, xmm0
0x180004050  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004056  test    r14b, 3
0x18000405a  jnz     loc_18000423B
0x180004060  mov     r9, r14
0x180004063  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004068  shr     r9, 2; unsigned __int64
0x18000406c  lea     rcx, [rsp+280h+hObject]; this
0x180004071  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004076  mov     esi, eax
0x180004078  test    eax, eax
0x18000407a  jns     loc_180004126
0x180004080  mov     rcx, [rbp+188h]; this
0x180004087  lea     r8, aWil; "wil"
0x18000408e  mov     r9d, eax; char *
0x180004091  mov     edx, 14Eh; void *
0x180004096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000409b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800040a0  test    rcx, rcx
0x1800040a3  jz      short loc_1800040B3
0x1800040a5  call    cs:__imp_CloseHandle
0x1800040ab  test    eax, eax
0x1800040ad  jz      loc_180004241
0x1800040b3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800040b8  test    rcx, rcx
0x1800040bb  jz      short loc_1800040CB
0x1800040bd  call    cs:__imp_CloseHandle
0x1800040c3  test    eax, eax
0x1800040c5  jz      loc_180004253
0x1800040cb  call    cs:__imp_GetProcessHeap
0x1800040d1  mov     r8, r14; lpMem
0x1800040d4  xor     edx, edx; dwFlags
0x1800040d6  mov     rcx, rax; hHeap
0x1800040d9  call    cs:__imp_HeapFree
0x1800040df  mov     rcx, [rbp+188h]; this
0x1800040e6  lea     r8, aWil; "wil"
0x1800040ed  mov     r9d, esi; char *
0x1800040f0  mov     edx, 137h; void *
0x1800040f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040fa  test    rdi, rdi
0x1800040fd  jz      short loc_180004110
0x1800040ff  mov     rcx, rdi; hMutex
0x180004102  call    cs:__imp_ReleaseMutex
0x180004108  test    eax, eax
0x18000410a  jz      loc_180004265
0x180004110  mov     rcx, rbx; hObject
0x180004113  call    cs:__imp_CloseHandle
0x180004119  test    eax, eax
0x18000411b  jz      loc_1800041F8
0x180004121  jmp     loc_180003FE5
0x180004126  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000412b  lea     rcx, [r14+28h]; void *
0x18000412f  mov     dword ptr [r14], 1
0x180004136  xor     edx, edx; Val
0x180004138  mov     [r14+8], rbx
0x18000413c  mov     r8d, 108h; Size
0x180004142  movdqu  xmmword ptr [r14+10h], xmm0
0x180004148  call    memset_0
0x18000414d  xor     eax, eax
0x18000414f  lea     rcx, [r14+28h]; this
0x180004153  mov     [r14+20h], rax
0x180004157  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000415c  lea     rbx, [r14+0E8h]
0x180004163  xor     r8d, r8d; Flags
0x180004166  mov     rcx, rbx; lpCriticalSection
0x180004169  xor     edx, edx; dwSpinCount
0x18000416b  call    cs:__imp_InitializeCriticalSectionEx
0x180004171  mov     qword ptr [rbx+28h], 0
0x180004179  mov     qword ptr [rbx+30h], 0
0x180004181  mov     qword ptr [rbx+38h], 0
0x180004189  mov     qword ptr [rbx+40h], 0
0x180004191  xor     ebx, ebx
0x180004193  mov     [r15], r14
0x180004196  test    rdi, rdi
0x180004199  jz      short loc_1800041AC
0x18000419b  mov     rcx, rdi; hMutex
0x18000419e  call    cs:__imp_ReleaseMutex
0x1800041a4  test    eax, eax
0x1800041a6  jz      loc_180004277
0x1800041ac  test    rbx, rbx
0x1800041af  jz      short loc_1800041BE
0x1800041b1  mov     rcx, rbx; hObject
0x1800041b4  call    cs:__imp_CloseHandle
0x1800041ba  test    eax, eax
0x1800041bc  jz      short loc_1800041E6
0x1800041be  xor     eax, eax
0x1800041c0  mov     rcx, [rbp+180h+var_30]
0x1800041c7  xor     rcx, rsp; StackCookie
0x1800041ca  call    __security_check_cookie
0x1800041cf  mov     rbx, [rsp+280h+arg_10]
0x1800041d7  add     rsp, 260h
0x1800041de  pop     r15
0x1800041e0  pop     r14
0x1800041e2  pop     rdi
0x1800041e3  pop     rsi
0x1800041e4  pop     rbp
0x1800041e5  retn
0x1800041e6  mov     rcx, [rbp+188h]; this
0x1800041ed  mov     edx, 0A0Bh; void *
0x1800041f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041f8  mov     rcx, [rbp+188h]; this
0x1800041ff  mov     edx, 0A0Bh; void *
0x180004204  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000420a  mov     rcx, [rbp+188h]; this
0x180004211  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004217  mov     rcx, [rbp+188h]; this
0x18000421e  mov     edx, 0A15h; void *
0x180004223  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004229  mov     rcx, [rbp+188h]; this
0x180004230  mov     edx, 0A0Bh; void *
0x180004235  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000423b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004241  mov     rcx, [rbp+188h]; this
0x180004248  mov     edx, 0A0Bh; void *
0x18000424d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004253  mov     rcx, [rbp+188h]; this
0x18000425a  mov     edx, 0A0Bh; void *
0x18000425f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004265  mov     rcx, [rbp+188h]; this
0x18000426c  mov     edx, 0A15h; void *
0x180004271  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004277  mov     rcx, [rbp+188h]; this
0x18000427e  mov     edx, 0A15h; void *
0x180004283  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
