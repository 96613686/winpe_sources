# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800b524c`
- end: `0x1800b561e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800b685c`

## callees

- `0x18000eb54`
- `0x1800b45c0`
- `0x1800b4c3c`
- `0x1800b524c`
- `0x1800b65c4`
- `0x1800b6ab8`
- `0x1800b7a70`
- `0x1800ba9a8`
- `0x1800bc8b0`
- `0x1800bd2cc`
- `0x1800bdbb0`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b5285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b5285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b538e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b556c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b538e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b556c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b52f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b52f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5377`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b547f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5550`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5377`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b547f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b5550`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800b550d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800b550d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800b52c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800b52c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b5457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b5457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5443`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5443`

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
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x1800b524c  mov     [rsp-8+arg_10], rbx
0x1800b5251  push    rbp
0x1800b5252  push    rsi
0x1800b5253  push    rdi
0x1800b5254  push    r14
0x1800b5256  push    r15
0x1800b5258  lea     rbp, [rsp-160h]
0x1800b5260  sub     rsp, 260h
0x1800b5267  mov     rax, cs:__security_cookie
0x1800b526e  xor     rax, rsp
0x1800b5271  mov     [rbp+180h+var_30], rax
0x1800b5278  mov     r15, rdx
0x1800b527b  mov     qword ptr [rdx], 0
0x1800b5282  mov     rbx, rcx
0x1800b5285  call    cs:__imp_GetCurrentProcessId
0x1800b528c  nop     dword ptr [rax+rax+00h]
0x1800b5291  mov     r14d, 130h
0x1800b5297  mov     [rsp+280h+var_258], rbx
0x1800b529c  mov     r9d, eax
0x1800b529f  mov     [rsp+280h+var_260], r14d; int
0x1800b52a4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800b52ab  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b52b0  lea     edx, [r14-2Ch]; unsigned __int64
0x1800b52b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b52b9  mov     r9d, 1F0001h; dwDesiredAccess
0x1800b52bf  lea     rdx, [rsp+280h+Name]; lpName
0x1800b52c4  xor     r8d, r8d; dwFlags
0x1800b52c7  xor     ecx, ecx; lpMutexAttributes
0x1800b52c9  call    cs:__imp_CreateMutexExW
0x1800b52d0  nop     dword ptr [rax+rax+00h]
0x1800b52d5  mov     rbx, rax
0x1800b52d8  test    rax, rax
0x1800b52db  jnz     short loc_1800B52E7
0x1800b52dd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800b52e2  jmp     loc_1800B557E
0x1800b52e7  xor     r8d, r8d; bAlertable
0x1800b52ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b52ed  mov     rcx, rbx; hHandle
0x1800b52f0  call    cs:__imp_WaitForSingleObjectEx
0x1800b52f7  nop     dword ptr [rax+rax+00h]
0x1800b52fc  cmp     eax, 102h
0x1800b5301  jz      short loc_1800B5313
0x1800b5303  test    eax, 0FFFFFF7Fh
0x1800b5308  jnz     loc_1800B55C9
0x1800b530e  mov     rdi, rbx
0x1800b5311  jmp     short loc_1800B5315
0x1800b5313  xor     edi, edi
0x1800b5315  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800b531a  mov     [rsp+280h+var_250], 0
0x1800b5323  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800b5328  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800b532d  mov     esi, eax
0x1800b532f  test    eax, eax
0x1800b5331  jns     short loc_1800B53A9
0x1800b5333  mov     rcx, [rbp+188h]; this
0x1800b533a  mov     r9d, eax; char *
0x1800b533d  mov     edx, 66h ; 'f'; void *
0x1800b5342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5347  mov     rcx, [rbp+188h]; this
0x1800b534e  mov     r9d, esi; char *
0x1800b5351  mov     edx, 6Fh ; 'o'; void *
0x1800b5356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b535b  mov     rcx, [rbp+188h]; this
0x1800b5362  mov     r9d, esi; char *
0x1800b5365  mov     edx, 12Eh; void *
0x1800b536a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b536f  test    rdi, rdi
0x1800b5372  jz      short loc_1800B538B
0x1800b5374  mov     rcx, rdi; hMutex
0x1800b5377  call    cs:__imp_ReleaseMutex
0x1800b537e  nop     dword ptr [rax+rax+00h]
0x1800b5383  test    eax, eax
0x1800b5385  jz      loc_1800B55D6
0x1800b538b  mov     rcx, rbx; hObject
0x1800b538e  call    cs:__imp_CloseHandle
0x1800b5395  nop     dword ptr [rax+rax+00h]
0x1800b539a  test    eax, eax
0x1800b539c  jz      loc_1800B55E8
0x1800b53a2  mov     eax, esi
0x1800b53a4  jmp     loc_1800B557E
0x1800b53a9  mov     rax, [rsp+280h+var_250]
0x1800b53ae  lea     rcx, ds:0[rax*4]
0x1800b53b6  test    rcx, rcx
0x1800b53b9  jz      short loc_1800B53C9
0x1800b53bb  mov     [r15], rcx
0x1800b53be  mov     eax, [rcx]
0x1800b53c0  inc     eax
0x1800b53c2  mov     [rcx], eax
0x1800b53c4  jmp     loc_1800B5548
0x1800b53c9  mov     rdx, r14; dwBytes
0x1800b53cc  mov     qword ptr [r15], 0
0x1800b53d3  mov     ecx, 8; dwFlags
0x1800b53d8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800b53dd  mov     r14, rax
0x1800b53e0  test    rax, rax
0x1800b53e3  jnz     short loc_1800B5400
0x1800b53e5  mov     rcx, [rbp+188h]; this
0x1800b53ec  mov     esi, 8007000Eh
0x1800b53f1  mov     r9d, esi; char *
0x1800b53f4  mov     edx, 14Bh; void *
0x1800b53f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b53fe  jmp     short loc_1800B5463
0x1800b5400  xorps   xmm0, xmm0
0x1800b5403  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800b5408  mov     r8, r14; void *
0x1800b540b  lea     rcx, [rsp+280h+var_250]; this
0x1800b5410  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800b5416  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800b541b  mov     esi, eax
0x1800b541d  test    eax, eax
0x1800b541f  jns     loc_1800B54AF
0x1800b5425  mov     rcx, [rbp+188h]; this
0x1800b542c  mov     r9d, eax; char *
0x1800b542f  mov     edx, 14Eh; void *
0x1800b5434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5439  lea     rcx, [rsp+280h+var_250]; this
0x1800b543e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800b5443  call    cs:__imp_GetProcessHeap
0x1800b544a  nop     dword ptr [rax+rax+00h]
0x1800b544f  mov     r8, r14; lpMem
0x1800b5452  xor     edx, edx; dwFlags
0x1800b5454  mov     rcx, rax; hHeap
0x1800b5457  call    cs:__imp_HeapFree
0x1800b545e  nop     dword ptr [rax+rax+00h]
0x1800b5463  mov     rcx, [rbp+188h]; this
0x1800b546a  mov     r9d, esi; char *
0x1800b546d  mov     edx, 137h; void *
0x1800b5472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5477  test    rdi, rdi
0x1800b547a  jz      short loc_1800B5493
0x1800b547c  mov     rcx, rdi; hMutex
0x1800b547f  call    cs:__imp_ReleaseMutex
0x1800b5486  nop     dword ptr [rax+rax+00h]
0x1800b548b  test    eax, eax
0x1800b548d  jz      loc_1800B55FA
0x1800b5493  mov     rcx, rbx; hObject
0x1800b5496  call    cs:__imp_CloseHandle
0x1800b549d  nop     dword ptr [rax+rax+00h]
0x1800b54a2  test    eax, eax
0x1800b54a4  jz      loc_1800B55B7
0x1800b54aa  jmp     loc_1800B53A2
0x1800b54af  mov     rax, [rsp+280h+var_250]
0x1800b54b4  lea     rcx, [r14+28h]; void *
0x1800b54b8  mov     [r14+10h], rax
0x1800b54bc  xor     edx, edx; Val
0x1800b54be  mov     rax, [rsp+280h+var_250+8]
0x1800b54c3  mov     r8d, 108h; Size
0x1800b54c9  mov     [r14+18h], rax
0x1800b54cd  mov     dword ptr [r14], 1
0x1800b54d4  mov     [r14+8], rbx
0x1800b54d8  mov     [rsp+280h+var_250], 0
0x1800b54e1  mov     [rsp+280h+var_250+8], 0
0x1800b54ea  call    memset_0
0x1800b54ef  xor     eax, eax
0x1800b54f1  lea     rcx, [r14+28h]; this
0x1800b54f5  mov     [r14+20h], rax
0x1800b54f9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800b54fe  lea     rbx, [r14+0E8h]
0x1800b5505  xor     r8d, r8d; Flags
0x1800b5508  mov     rcx, rbx; lpCriticalSection
0x1800b550b  xor     edx, edx; dwSpinCount
0x1800b550d  call    cs:__imp_InitializeCriticalSectionEx
0x1800b5514  nop     dword ptr [rax+rax+00h]
0x1800b5519  mov     qword ptr [rbx+28h], 0
0x1800b5521  lea     rcx, [rsp+280h+var_250]; this
0x1800b5526  mov     qword ptr [rbx+30h], 0
0x1800b552e  mov     qword ptr [rbx+38h], 0
0x1800b5536  mov     qword ptr [rbx+40h], 0
0x1800b553e  mov     [r15], r14
0x1800b5541  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800b5546  xor     ebx, ebx
0x1800b5548  test    rdi, rdi
0x1800b554b  jz      short loc_1800B5564
0x1800b554d  mov     rcx, rdi; hMutex
0x1800b5550  call    cs:__imp_ReleaseMutex
0x1800b5557  nop     dword ptr [rax+rax+00h]
0x1800b555c  test    eax, eax
0x1800b555e  jz      loc_1800B560C
0x1800b5564  test    rbx, rbx
0x1800b5567  jz      short loc_1800B557C
0x1800b5569  mov     rcx, rbx; hObject
0x1800b556c  call    cs:__imp_CloseHandle
0x1800b5573  nop     dword ptr [rax+rax+00h]
0x1800b5578  test    eax, eax
0x1800b557a  jz      short loc_1800B55A5
0x1800b557c  xor     eax, eax
0x1800b557e  mov     rcx, [rbp+180h+var_30]
0x1800b5585  xor     rcx, rsp; StackCookie
0x1800b5588  call    __security_check_cookie
0x1800b558d  mov     rbx, [rsp+280h+arg_10]
0x1800b5595  add     rsp, 260h
0x1800b559c  pop     r15
0x1800b559e  pop     r14
0x1800b55a0  pop     rdi
0x1800b55a1  pop     rsi
0x1800b55a2  pop     rbp
0x1800b55a3  retn
0x1800b55a5  mov     rcx, [rbp+188h]; this
0x1800b55ac  mov     edx, 0A0Bh; void *
0x1800b55b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b55b7  mov     rcx, [rbp+188h]; this
0x1800b55be  mov     edx, 0A0Bh; void *
0x1800b55c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b55c9  mov     rcx, [rbp+188h]; this
0x1800b55d0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800b55d6  mov     rcx, [rbp+188h]; this
0x1800b55dd  mov     edx, 0A15h; void *
0x1800b55e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b55e8  mov     rcx, [rbp+188h]; this
0x1800b55ef  mov     edx, 0A0Bh; void *
0x1800b55f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b55fa  mov     rcx, [rbp+188h]; this
0x1800b5601  mov     edx, 0A15h; void *
0x1800b5606  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800b560c  mov     rcx, [rbp+188h]; this
0x1800b5613  mov     edx, 0A15h; void *
0x1800b5618  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
