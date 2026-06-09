# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007e80`
- end: `0x180008271`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180008400`

## callees

- `0x180002c00`
- `0x180004110`
- `0x1800043f4`
- `0x180004988`
- `0x180005468`
- `0x1800056c4`
- `0x1800061ac`
- `0x180006790`
- `0x1800067a0`
- `0x1800073e8`
- `0x180007e80`
- `0x1800133e2`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007f18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007f18`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007fae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800080ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008186`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007fae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800080ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008186`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007ef7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007ef7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008153`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007eb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000808d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000819c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000808d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000819c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080b3`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
0x180007e80  mov     [rsp-8+arg_10], rbx
0x180007e85  push    rbp
0x180007e86  push    rsi
0x180007e87  push    rdi
0x180007e88  push    r14
0x180007e8a  push    r15
0x180007e8c  lea     rbp, [rsp-160h]
0x180007e94  sub     rsp, 260h
0x180007e9b  mov     rax, cs:__security_cookie
0x180007ea2  xor     rax, rsp
0x180007ea5  mov     [rbp+180h+var_30], rax
0x180007eac  mov     r15, rdx
0x180007eaf  mov     qword ptr [rdx], 0
0x180007eb6  mov     rbx, rcx
0x180007eb9  call    cs:__imp_GetCurrentProcessId
0x180007ebf  mov     r14d, 130h
0x180007ec5  mov     [rsp+280h+var_258], rbx
0x180007eca  mov     r9d, eax
0x180007ecd  mov     [rsp+280h+var_260], r14d; int
0x180007ed2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007ed9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007ede  lea     edx, [r14-2Ch]; unsigned __int64
0x180007ee2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007ee7  mov     r9d, 1F0001h; dwDesiredAccess
0x180007eed  lea     rdx, [rsp+280h+Name]; lpName
0x180007ef2  xor     r8d, r8d; dwFlags
0x180007ef5  xor     ecx, ecx; lpMutexAttributes
0x180007ef7  call    cs:__imp_CreateMutexExW
0x180007efd  mov     rbx, rax
0x180007f00  test    rax, rax
0x180007f03  jnz     short loc_180007F0F
0x180007f05  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007f0a  jmp     loc_1800081A8
0x180007f0f  xor     r8d, r8d; bAlertable
0x180007f12  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007f15  mov     rcx, rbx; hHandle
0x180007f18  call    cs:__imp_WaitForSingleObjectEx
0x180007f1e  cmp     eax, 102h
0x180007f23  jz      short loc_180007F35
0x180007f25  test    eax, 0FFFFFF7Fh
0x180007f2a  jnz     loc_1800081F2
0x180007f30  mov     rdi, rbx
0x180007f33  jmp     short loc_180007F37
0x180007f35  xor     edi, edi
0x180007f37  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007f3c  mov     [rsp+280h+hObject], 0
0x180007f45  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007f4a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007f4f  mov     esi, eax
0x180007f51  test    eax, eax
0x180007f53  jns     short loc_180007FD4
0x180007f55  mov     rcx, [rbp+188h]; this
0x180007f5c  lea     r8, aWil; "wil"
0x180007f63  mov     r9d, eax; char *
0x180007f66  mov     edx, 66h ; 'f'; void *
0x180007f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f70  mov     rcx, [rbp+188h]; this
0x180007f77  lea     r8, aWil; "wil"
0x180007f7e  mov     r9d, esi; char *
0x180007f81  mov     edx, 6Fh ; 'o'; void *
0x180007f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f8b  mov     rcx, [rbp+188h]; this
0x180007f92  lea     r8, aWil; "wil"
0x180007f99  mov     r9d, esi; char *
0x180007f9c  mov     edx, 12Eh; void *
0x180007fa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fa6  test    rdi, rdi
0x180007fa9  jz      short loc_180007FBC
0x180007fab  mov     rcx, rdi; hMutex
0x180007fae  call    cs:__imp_ReleaseMutex
0x180007fb4  test    eax, eax
0x180007fb6  jz      loc_1800081FF
0x180007fbc  mov     rcx, rbx; hObject
0x180007fbf  call    cs:__imp_CloseHandle
0x180007fc5  test    eax, eax
0x180007fc7  jz      loc_180008211
0x180007fcd  mov     eax, esi
0x180007fcf  jmp     loc_1800081A8
0x180007fd4  mov     rax, [rsp+280h+hObject]
0x180007fd9  lea     rcx, ds:0[rax*4]
0x180007fe1  test    rcx, rcx
0x180007fe4  jz      short loc_180007FF4
0x180007fe6  mov     [r15], rcx
0x180007fe9  mov     eax, [rcx]
0x180007feb  inc     eax
0x180007fed  mov     [rcx], eax
0x180007fef  jmp     loc_18000817E
0x180007ff4  mov     rdx, r14; dwBytes
0x180007ff7  mov     qword ptr [r15], 0
0x180007ffe  mov     ecx, 8; dwFlags
0x180008003  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008008  mov     r14, rax
0x18000800b  test    rax, rax
0x18000800e  jnz     short loc_180008035
0x180008010  mov     rcx, [rbp+188h]; this
0x180008017  lea     r8, aWil; "wil"
0x18000801e  mov     esi, 8007000Eh
0x180008023  mov     edx, 14Bh; void *
0x180008028  mov     r9d, esi; char *
0x18000802b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008030  jmp     loc_1800080C7
0x180008035  xorps   xmm0, xmm0
0x180008038  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000803e  test    r14b, 3
0x180008042  jnz     loc_180008223
0x180008048  mov     r9, r14
0x18000804b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008050  shr     r9, 2; unsigned __int64
0x180008054  lea     rcx, [rsp+280h+hObject]; this
0x180008059  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000805e  mov     esi, eax
0x180008060  test    eax, eax
0x180008062  jns     loc_18000810E
0x180008068  mov     rcx, [rbp+188h]; this
0x18000806f  lea     r8, aWil; "wil"
0x180008076  mov     r9d, eax; char *
0x180008079  mov     edx, 14Eh; void *
0x18000807e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008083  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008088  test    rcx, rcx
0x18000808b  jz      short loc_18000809B
0x18000808d  call    cs:__imp_CloseHandle
0x180008093  test    eax, eax
0x180008095  jz      loc_180008229
0x18000809b  mov     rcx, [rsp+280h+hObject]; hObject
0x1800080a0  test    rcx, rcx
0x1800080a3  jz      short loc_1800080B3
0x1800080a5  call    cs:__imp_CloseHandle
0x1800080ab  test    eax, eax
0x1800080ad  jz      loc_18000823B
0x1800080b3  call    cs:__imp_GetProcessHeap
0x1800080b9  mov     r8, r14; lpMem
0x1800080bc  xor     edx, edx; dwFlags
0x1800080be  mov     rcx, rax; hHeap
0x1800080c1  call    cs:__imp_HeapFree
0x1800080c7  mov     rcx, [rbp+188h]; this
0x1800080ce  lea     r8, aWil; "wil"
0x1800080d5  mov     r9d, esi; char *
0x1800080d8  mov     edx, 137h; void *
0x1800080dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080e2  test    rdi, rdi
0x1800080e5  jz      short loc_1800080F8
0x1800080e7  mov     rcx, rdi; hMutex
0x1800080ea  call    cs:__imp_ReleaseMutex
0x1800080f0  test    eax, eax
0x1800080f2  jz      loc_18000824D
0x1800080f8  mov     rcx, rbx; hObject
0x1800080fb  call    cs:__imp_CloseHandle
0x180008101  test    eax, eax
0x180008103  jz      loc_1800081E0
0x180008109  jmp     loc_180007FCD
0x18000810e  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008113  lea     rcx, [r14+28h]; void *
0x180008117  mov     dword ptr [r14], 1
0x18000811e  xor     edx, edx; Val
0x180008120  mov     [r14+8], rbx
0x180008124  mov     r8d, 108h; Size
0x18000812a  movdqu  xmmword ptr [r14+10h], xmm0
0x180008130  call    memset_0
0x180008135  xor     eax, eax
0x180008137  lea     rcx, [r14+28h]; this
0x18000813b  mov     [r14+20h], rax
0x18000813f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008144  lea     rbx, [r14+0E8h]
0x18000814b  xor     r8d, r8d; Flags
0x18000814e  mov     rcx, rbx; lpCriticalSection
0x180008151  xor     edx, edx; dwSpinCount
0x180008153  call    cs:__imp_InitializeCriticalSectionEx
0x180008159  mov     qword ptr [rbx+28h], 0
0x180008161  mov     qword ptr [rbx+30h], 0
0x180008169  mov     qword ptr [rbx+38h], 0
0x180008171  mov     qword ptr [rbx+40h], 0
0x180008179  xor     ebx, ebx
0x18000817b  mov     [r15], r14
0x18000817e  test    rdi, rdi
0x180008181  jz      short loc_180008194
0x180008183  mov     rcx, rdi; hMutex
0x180008186  call    cs:__imp_ReleaseMutex
0x18000818c  test    eax, eax
0x18000818e  jz      loc_18000825F
0x180008194  test    rbx, rbx
0x180008197  jz      short loc_1800081A6
0x180008199  mov     rcx, rbx; hObject
0x18000819c  call    cs:__imp_CloseHandle
0x1800081a2  test    eax, eax
0x1800081a4  jz      short loc_1800081CE
0x1800081a6  xor     eax, eax
0x1800081a8  mov     rcx, [rbp+180h+var_30]
0x1800081af  xor     rcx, rsp; StackCookie
0x1800081b2  call    __security_check_cookie
0x1800081b7  mov     rbx, [rsp+280h+arg_10]
0x1800081bf  add     rsp, 260h
0x1800081c6  pop     r15
0x1800081c8  pop     r14
0x1800081ca  pop     rdi
0x1800081cb  pop     rsi
0x1800081cc  pop     rbp
0x1800081cd  retn
0x1800081ce  mov     rcx, [rbp+188h]; this
0x1800081d5  mov     edx, 0A0Bh; void *
0x1800081da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800081e0  mov     rcx, [rbp+188h]; this
0x1800081e7  mov     edx, 0A0Bh; void *
0x1800081ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800081f2  mov     rcx, [rbp+188h]; this
0x1800081f9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800081ff  mov     rcx, [rbp+188h]; this
0x180008206  mov     edx, 0A15h; void *
0x18000820b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008211  mov     rcx, [rbp+188h]; this
0x180008218  mov     edx, 0A0Bh; void *
0x18000821d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008223  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008229  mov     rcx, [rbp+188h]; this
0x180008230  mov     edx, 0A0Bh; void *
0x180008235  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000823b  mov     rcx, [rbp+188h]; this
0x180008242  mov     edx, 0A0Bh; void *
0x180008247  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000824d  mov     rcx, [rbp+188h]; this
0x180008254  mov     edx, 0A15h; void *
0x180008259  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000825f  mov     rcx, [rbp+188h]; this
0x180008266  mov     edx, 0A15h; void *
0x18000826b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
