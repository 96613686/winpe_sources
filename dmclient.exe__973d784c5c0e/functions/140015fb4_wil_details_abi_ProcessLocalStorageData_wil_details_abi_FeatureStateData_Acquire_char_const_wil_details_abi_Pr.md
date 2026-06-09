# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140015fb4`
- end: `0x1400163b4`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400163bc`

## callees

- `0x140004a04`
- `0x140005740`
- `0x140006b00`
- `0x1400070c0`
- `0x14000a98c`
- `0x14000b084`
- `0x14000b904`
- `0x14000b9ec`
- `0x14000bfd4`
- `0x140015a64`
- `0x140015fb4`
- `0x1400195e2`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400162a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400162a3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140016031`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140016031`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140016058`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140016058`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400160f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140016215`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400162e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400160f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140016215`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400162e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400161d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400161d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400161e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400161e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140015fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140015fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001610f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001622c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001610f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001622c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016302`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x140015fb4  mov     [rsp-8+arg_10], rbx
0x140015fb9  push    rbp
0x140015fba  push    rsi
0x140015fbb  push    rdi
0x140015fbc  push    r14
0x140015fbe  push    r15
0x140015fc0  lea     rbp, [rsp-160h]
0x140015fc8  sub     rsp, 260h
0x140015fcf  mov     rax, cs:__security_cookie
0x140015fd6  xor     rax, rsp
0x140015fd9  mov     [rbp+180h+var_30], rax
0x140015fe0  mov     r15, rdx
0x140015fe3  mov     qword ptr [rdx], 0
0x140015fea  mov     rbx, rcx
0x140015fed  call    cs:__imp_GetCurrentProcessId
0x140015ff4  nop     dword ptr [rax+rax+00h]
0x140015ff9  mov     r14d, 130h
0x140015fff  mov     [rsp+280h+var_258], rbx
0x140016004  mov     r9d, eax
0x140016007  mov     [rsp+280h+var_260], r14d; int
0x14001600c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140016013  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140016018  lea     edx, [r14-2Ch]; unsigned __int64
0x14001601c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140016021  mov     r9d, 1F0001h; dwDesiredAccess
0x140016027  lea     rdx, [rsp+280h+Name]; lpName
0x14001602c  xor     r8d, r8d; dwFlags
0x14001602f  xor     ecx, ecx; lpMutexAttributes
0x140016031  call    cs:__imp_CreateMutexExW
0x140016038  nop     dword ptr [rax+rax+00h]
0x14001603d  mov     rbx, rax
0x140016040  test    rax, rax
0x140016043  jnz     short loc_14001604F
0x140016045  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001604a  jmp     loc_140016314
0x14001604f  xor     r8d, r8d; bAlertable
0x140016052  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140016055  mov     rcx, rbx; hHandle
0x140016058  call    cs:__imp_WaitForSingleObjectEx
0x14001605f  nop     dword ptr [rax+rax+00h]
0x140016064  cmp     eax, 102h
0x140016069  jz      short loc_14001607B
0x14001606b  test    eax, 0FFFFFF7Fh
0x140016070  jnz     loc_14001635F
0x140016076  mov     rdi, rbx
0x140016079  jmp     short loc_14001607D
0x14001607b  xor     edi, edi
0x14001607d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140016082  mov     [rsp+280h+var_250], 0
0x14001608b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140016090  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140016095  mov     esi, eax
0x140016097  test    eax, eax
0x140016099  jns     loc_14001612A
0x14001609f  mov     rcx, [rbp+188h]; this
0x1400160a6  lea     r8, aWil; "wil"
0x1400160ad  mov     r9d, eax; char *
0x1400160b0  mov     edx, 66h ; 'f'; void *
0x1400160b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400160ba  mov     rcx, [rbp+188h]; this
0x1400160c1  lea     r8, aWil; "wil"
0x1400160c8  mov     r9d, esi; char *
0x1400160cb  mov     edx, 6Fh ; 'o'; void *
0x1400160d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400160d5  mov     rcx, [rbp+188h]; this
0x1400160dc  lea     r8, aWil; "wil"
0x1400160e3  mov     r9d, esi; char *
0x1400160e6  mov     edx, 12Eh; void *
0x1400160eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400160f0  test    rdi, rdi
0x1400160f3  jz      short loc_14001610C
0x1400160f5  mov     rcx, rdi; hMutex
0x1400160f8  call    cs:__imp_ReleaseMutex
0x1400160ff  nop     dword ptr [rax+rax+00h]
0x140016104  test    eax, eax
0x140016106  jz      loc_14001636C
0x14001610c  mov     rcx, rbx; hObject
0x14001610f  call    cs:__imp_CloseHandle
0x140016116  nop     dword ptr [rax+rax+00h]
0x14001611b  test    eax, eax
0x14001611d  jz      loc_14001637E
0x140016123  mov     eax, esi
0x140016125  jmp     loc_140016314
0x14001612a  mov     rax, [rsp+280h+var_250]
0x14001612f  lea     rcx, ds:0[rax*4]
0x140016137  test    rcx, rcx
0x14001613a  jz      short loc_14001614A
0x14001613c  mov     [r15], rcx
0x14001613f  mov     eax, [rcx]
0x140016141  inc     eax
0x140016143  mov     [rcx], eax
0x140016145  jmp     loc_1400162DE
0x14001614a  mov     rdx, r14; dwBytes
0x14001614d  mov     qword ptr [r15], 0
0x140016154  mov     ecx, 8; dwFlags
0x140016159  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001615e  mov     r14, rax
0x140016161  test    rax, rax
0x140016164  jnz     short loc_140016188
0x140016166  mov     rcx, [rbp+188h]; this
0x14001616d  lea     r8, aWil; "wil"
0x140016174  mov     esi, 8007000Eh
0x140016179  mov     edx, 14Bh; void *
0x14001617e  mov     r9d, esi; char *
0x140016181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016186  jmp     short loc_1400161F2
0x140016188  xorps   xmm0, xmm0
0x14001618b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140016190  mov     r8, r14; void *
0x140016193  lea     rcx, [rsp+280h+var_250]; this
0x140016198  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14001619e  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1400161a3  mov     esi, eax
0x1400161a5  test    eax, eax
0x1400161a7  jns     loc_140016245
0x1400161ad  mov     rcx, [rbp+188h]; this
0x1400161b4  lea     r8, aWil; "wil"
0x1400161bb  mov     r9d, eax; char *
0x1400161be  mov     edx, 14Eh; void *
0x1400161c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400161c8  lea     rcx, [rsp+280h+var_250]; this
0x1400161cd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400161d2  call    cs:__imp_GetProcessHeap
0x1400161d9  nop     dword ptr [rax+rax+00h]
0x1400161de  mov     r8, r14; lpMem
0x1400161e1  xor     edx, edx; dwFlags
0x1400161e3  mov     rcx, rax; hHeap
0x1400161e6  call    cs:__imp_HeapFree
0x1400161ed  nop     dword ptr [rax+rax+00h]
0x1400161f2  mov     rcx, [rbp+188h]; this
0x1400161f9  lea     r8, aWil; "wil"
0x140016200  mov     r9d, esi; char *
0x140016203  mov     edx, 137h; void *
0x140016208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001620d  test    rdi, rdi
0x140016210  jz      short loc_140016229
0x140016212  mov     rcx, rdi; hMutex
0x140016215  call    cs:__imp_ReleaseMutex
0x14001621c  nop     dword ptr [rax+rax+00h]
0x140016221  test    eax, eax
0x140016223  jz      loc_140016390
0x140016229  mov     rcx, rbx; hObject
0x14001622c  call    cs:__imp_CloseHandle
0x140016233  nop     dword ptr [rax+rax+00h]
0x140016238  test    eax, eax
0x14001623a  jz      loc_14001634D
0x140016240  jmp     loc_140016123
0x140016245  mov     rax, [rsp+280h+var_250]
0x14001624a  lea     rcx, [r14+28h]; void *
0x14001624e  mov     [r14+10h], rax
0x140016252  xor     edx, edx; Val
0x140016254  mov     rax, [rsp+280h+var_250+8]
0x140016259  mov     r8d, 108h; Size
0x14001625f  mov     [r14+18h], rax
0x140016263  mov     dword ptr [r14], 1
0x14001626a  mov     [r14+8], rbx
0x14001626e  mov     [rsp+280h+var_250], 0
0x140016277  mov     [rsp+280h+var_250+8], 0
0x140016280  call    memset_0
0x140016285  xor     eax, eax
0x140016287  lea     rcx, [r14+28h]; this
0x14001628b  mov     [r14+20h], rax
0x14001628f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140016294  lea     rbx, [r14+0E8h]
0x14001629b  xor     r8d, r8d; Flags
0x14001629e  mov     rcx, rbx; lpCriticalSection
0x1400162a1  xor     edx, edx; dwSpinCount
0x1400162a3  call    cs:__imp_InitializeCriticalSectionEx
0x1400162aa  nop     dword ptr [rax+rax+00h]
0x1400162af  mov     qword ptr [rbx+28h], 0
0x1400162b7  lea     rcx, [rsp+280h+var_250]; this
0x1400162bc  mov     qword ptr [rbx+30h], 0
0x1400162c4  mov     qword ptr [rbx+38h], 0
0x1400162cc  mov     qword ptr [rbx+40h], 0
0x1400162d4  mov     [r15], r14
0x1400162d7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400162dc  xor     ebx, ebx
0x1400162de  test    rdi, rdi
0x1400162e1  jz      short loc_1400162FA
0x1400162e3  mov     rcx, rdi; hMutex
0x1400162e6  call    cs:__imp_ReleaseMutex
0x1400162ed  nop     dword ptr [rax+rax+00h]
0x1400162f2  test    eax, eax
0x1400162f4  jz      loc_1400163A2
0x1400162fa  test    rbx, rbx
0x1400162fd  jz      short loc_140016312
0x1400162ff  mov     rcx, rbx; hObject
0x140016302  call    cs:__imp_CloseHandle
0x140016309  nop     dword ptr [rax+rax+00h]
0x14001630e  test    eax, eax
0x140016310  jz      short loc_14001633B
0x140016312  xor     eax, eax
0x140016314  mov     rcx, [rbp+180h+var_30]
0x14001631b  xor     rcx, rsp; StackCookie
0x14001631e  call    __security_check_cookie
0x140016323  mov     rbx, [rsp+280h+arg_10]
0x14001632b  add     rsp, 260h
0x140016332  pop     r15
0x140016334  pop     r14
0x140016336  pop     rdi
0x140016337  pop     rsi
0x140016338  pop     rbp
0x140016339  retn
0x14001633b  mov     rcx, [rbp+188h]; this
0x140016342  mov     edx, 0A0Bh; void *
0x140016347  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001634d  mov     rcx, [rbp+188h]; this
0x140016354  mov     edx, 0A0Bh; void *
0x140016359  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001635f  mov     rcx, [rbp+188h]; this
0x140016366  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14001636c  mov     rcx, [rbp+188h]; this
0x140016373  mov     edx, 0A15h; void *
0x140016378  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001637e  mov     rcx, [rbp+188h]; this
0x140016385  mov     edx, 0A0Bh; void *
0x14001638a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140016390  mov     rcx, [rbp+188h]; this
0x140016397  mov     edx, 0A15h; void *
0x14001639c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400163a2  mov     rcx, [rbp+188h]; this
0x1400163a9  mov     edx, 0A15h; void *
0x1400163ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
