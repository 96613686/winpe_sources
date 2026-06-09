# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800050c0`
- end: `0x180005487`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800059d4`

## callees

- `0x180003614`
- `0x1800044c0`
- `0x1800050c0`
- `0x1800056f4`
- `0x180005c30`
- `0x18000698c`
- `0x180008038`
- `0x180009554`
- `0x180009cc0`
- `0x18000a56c`
- `0x18000a57c`
- `0x18000ccde`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005137`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005137`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005158`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005158`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005369`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005369`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005300`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000539c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800051d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005300`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000539c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b2`

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
0x1800050c0  mov     [rsp-8+arg_10], rbx
0x1800050c5  push    rbp
0x1800050c6  push    rsi
0x1800050c7  push    rdi
0x1800050c8  push    r14
0x1800050ca  push    r15
0x1800050cc  lea     rbp, [rsp-160h]
0x1800050d4  sub     rsp, 260h
0x1800050db  mov     rax, cs:__security_cookie
0x1800050e2  xor     rax, rsp
0x1800050e5  mov     [rbp+180h+var_30], rax
0x1800050ec  mov     r15, rdx
0x1800050ef  mov     qword ptr [rdx], 0
0x1800050f6  mov     rbx, rcx
0x1800050f9  call    cs:__imp_GetCurrentProcessId
0x1800050ff  mov     r14d, 130h
0x180005105  mov     [rsp+280h+var_258], rbx
0x18000510a  mov     r9d, eax
0x18000510d  mov     [rsp+280h+var_260], r14d; int
0x180005112  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005119  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000511e  lea     edx, [r14-2Ch]; unsigned __int64
0x180005122  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005127  mov     r9d, 1F0001h; dwDesiredAccess
0x18000512d  lea     rdx, [rsp+280h+Name]; lpName
0x180005132  xor     r8d, r8d; dwFlags
0x180005135  xor     ecx, ecx; lpMutexAttributes
0x180005137  call    cs:__imp_CreateMutexExW
0x18000513d  mov     rbx, rax
0x180005140  test    rax, rax
0x180005143  jnz     short loc_18000514F
0x180005145  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000514a  jmp     loc_1800053BE
0x18000514f  xor     r8d, r8d; bAlertable
0x180005152  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005155  mov     rcx, rbx; hHandle
0x180005158  call    cs:__imp_WaitForSingleObjectEx
0x18000515e  cmp     eax, 102h
0x180005163  jz      short loc_180005175
0x180005165  test    eax, 0FFFFFF7Fh
0x18000516a  jnz     loc_180005408
0x180005170  mov     rdi, rbx
0x180005173  jmp     short loc_180005177
0x180005175  xor     edi, edi
0x180005177  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000517c  mov     [rsp+280h+hObject], 0
0x180005185  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000518a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000518f  mov     esi, eax
0x180005191  test    eax, eax
0x180005193  jns     short loc_1800051FF
0x180005195  mov     rcx, [rbp+188h]; this
0x18000519c  mov     r9d, eax; char *
0x18000519f  mov     edx, 66h ; 'f'; void *
0x1800051a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051a9  mov     rcx, [rbp+188h]; this
0x1800051b0  mov     r9d, esi; char *
0x1800051b3  mov     edx, 6Fh ; 'o'; void *
0x1800051b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051bd  mov     rcx, [rbp+188h]; this
0x1800051c4  mov     r9d, esi; char *
0x1800051c7  mov     edx, 12Eh; void *
0x1800051cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051d1  test    rdi, rdi
0x1800051d4  jz      short loc_1800051E7
0x1800051d6  mov     rcx, rdi; hMutex
0x1800051d9  call    cs:__imp_ReleaseMutex
0x1800051df  test    eax, eax
0x1800051e1  jz      loc_180005415
0x1800051e7  mov     rcx, rbx; hObject
0x1800051ea  call    cs:__imp_CloseHandle
0x1800051f0  test    eax, eax
0x1800051f2  jz      loc_180005427
0x1800051f8  mov     eax, esi
0x1800051fa  jmp     loc_1800053BE
0x1800051ff  mov     rax, [rsp+280h+hObject]
0x180005204  lea     rcx, ds:0[rax*4]
0x18000520c  test    rcx, rcx
0x18000520f  jz      short loc_18000521F
0x180005211  mov     [r15], rcx
0x180005214  mov     eax, [rcx]
0x180005216  inc     eax
0x180005218  mov     [rcx], eax
0x18000521a  jmp     loc_180005394
0x18000521f  mov     rdx, r14; dwBytes
0x180005222  mov     qword ptr [r15], 0
0x180005229  mov     ecx, 8; dwFlags
0x18000522e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005233  mov     r14, rax
0x180005236  test    rax, rax
0x180005239  jnz     short loc_180005259
0x18000523b  mov     rcx, [rbp+188h]; this
0x180005242  mov     esi, 8007000Eh
0x180005247  mov     r9d, esi; char *
0x18000524a  mov     edx, 14Bh; void *
0x18000524f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005254  jmp     loc_1800052E4
0x180005259  xorps   xmm0, xmm0
0x18000525c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005262  test    r14b, 3
0x180005266  jnz     loc_180005439
0x18000526c  mov     r9, r14
0x18000526f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005274  shr     r9, 2; unsigned __int64
0x180005278  lea     rcx, [rsp+280h+hObject]; this
0x18000527d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005282  mov     esi, eax
0x180005284  test    eax, eax
0x180005286  jns     loc_180005324
0x18000528c  mov     rcx, [rbp+188h]; this
0x180005293  mov     r9d, eax; char *
0x180005296  mov     edx, 14Eh; void *
0x18000529b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052a0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800052a5  test    rcx, rcx
0x1800052a8  jz      short loc_1800052B8
0x1800052aa  call    cs:__imp_CloseHandle
0x1800052b0  test    eax, eax
0x1800052b2  jz      loc_18000543F
0x1800052b8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800052bd  test    rcx, rcx
0x1800052c0  jz      short loc_1800052D0
0x1800052c2  call    cs:__imp_CloseHandle
0x1800052c8  test    eax, eax
0x1800052ca  jz      loc_180005451
0x1800052d0  call    cs:__imp_GetProcessHeap
0x1800052d6  mov     r8, r14; lpMem
0x1800052d9  xor     edx, edx; dwFlags
0x1800052db  mov     rcx, rax; hHeap
0x1800052de  call    cs:__imp_HeapFree
0x1800052e4  mov     rcx, [rbp+188h]; this
0x1800052eb  mov     r9d, esi; char *
0x1800052ee  mov     edx, 137h; void *
0x1800052f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052f8  test    rdi, rdi
0x1800052fb  jz      short loc_18000530E
0x1800052fd  mov     rcx, rdi; hMutex
0x180005300  call    cs:__imp_ReleaseMutex
0x180005306  test    eax, eax
0x180005308  jz      loc_180005463
0x18000530e  mov     rcx, rbx; hObject
0x180005311  call    cs:__imp_CloseHandle
0x180005317  test    eax, eax
0x180005319  jz      loc_1800053F6
0x18000531f  jmp     loc_1800051F8
0x180005324  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005329  lea     rcx, [r14+28h]; void *
0x18000532d  mov     dword ptr [r14], 1
0x180005334  xor     edx, edx; Val
0x180005336  mov     [r14+8], rbx
0x18000533a  mov     r8d, 108h; Size
0x180005340  movdqu  xmmword ptr [r14+10h], xmm0
0x180005346  call    memset_0
0x18000534b  xor     eax, eax
0x18000534d  lea     rcx, [r14+28h]; this
0x180005351  mov     [r14+20h], rax
0x180005355  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000535a  lea     rbx, [r14+0E8h]
0x180005361  xor     r8d, r8d; Flags
0x180005364  mov     rcx, rbx; lpCriticalSection
0x180005367  xor     edx, edx; dwSpinCount
0x180005369  call    cs:__imp_InitializeCriticalSectionEx
0x18000536f  mov     qword ptr [rbx+28h], 0
0x180005377  mov     qword ptr [rbx+30h], 0
0x18000537f  mov     qword ptr [rbx+38h], 0
0x180005387  mov     qword ptr [rbx+40h], 0
0x18000538f  xor     ebx, ebx
0x180005391  mov     [r15], r14
0x180005394  test    rdi, rdi
0x180005397  jz      short loc_1800053AA
0x180005399  mov     rcx, rdi; hMutex
0x18000539c  call    cs:__imp_ReleaseMutex
0x1800053a2  test    eax, eax
0x1800053a4  jz      loc_180005475
0x1800053aa  test    rbx, rbx
0x1800053ad  jz      short loc_1800053BC
0x1800053af  mov     rcx, rbx; hObject
0x1800053b2  call    cs:__imp_CloseHandle
0x1800053b8  test    eax, eax
0x1800053ba  jz      short loc_1800053E4
0x1800053bc  xor     eax, eax
0x1800053be  mov     rcx, [rbp+180h+var_30]
0x1800053c5  xor     rcx, rsp; StackCookie
0x1800053c8  call    __security_check_cookie
0x1800053cd  mov     rbx, [rsp+280h+arg_10]
0x1800053d5  add     rsp, 260h
0x1800053dc  pop     r15
0x1800053de  pop     r14
0x1800053e0  pop     rdi
0x1800053e1  pop     rsi
0x1800053e2  pop     rbp
0x1800053e3  retn
0x1800053e4  mov     rcx, [rbp+188h]; this
0x1800053eb  mov     edx, 0A0Bh; void *
0x1800053f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800053f6  mov     rcx, [rbp+188h]; this
0x1800053fd  mov     edx, 0A0Bh; void *
0x180005402  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005408  mov     rcx, [rbp+188h]; this
0x18000540f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005415  mov     rcx, [rbp+188h]; this
0x18000541c  mov     edx, 0A15h; void *
0x180005421  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005427  mov     rcx, [rbp+188h]; this
0x18000542e  mov     edx, 0A0Bh; void *
0x180005433  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005439  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000543f  mov     rcx, [rbp+188h]; this
0x180005446  mov     edx, 0A0Bh; void *
0x18000544b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005451  mov     rcx, [rbp+188h]; this
0x180005458  mov     edx, 0A0Bh; void *
0x18000545d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005463  mov     rcx, [rbp+188h]; this
0x18000546a  mov     edx, 0A15h; void *
0x18000546f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005475  mov     rcx, [rbp+188h]; this
0x18000547c  mov     edx, 0A15h; void *
0x180005481  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
