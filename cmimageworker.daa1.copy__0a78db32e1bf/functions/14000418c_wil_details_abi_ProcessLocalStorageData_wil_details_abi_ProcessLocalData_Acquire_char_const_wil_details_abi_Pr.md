# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000418c`
- end: `0x14000455f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140005060`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x140003e1c`
- `0x14000418c`
- `0x140004568`
- `0x1400048b8`
- `0x140004e70`
- `0x1400067d4`
- `0x140006fe4`
- `0x14000898c`
- `0x140008a6c`
- `0x140008f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400042d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004491`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400042d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400043ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004491`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000420a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000420a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004231`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004231`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400041c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400041c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400044ad`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x14000418c  mov     [rsp-8+arg_10], rbx
0x140004191  push    rbp
0x140004192  push    rsi
0x140004193  push    rdi
0x140004194  push    r14
0x140004196  push    r15
0x140004198  lea     rbp, [rsp-160h]
0x1400041a0  sub     rsp, 260h
0x1400041a7  mov     rax, cs:__security_cookie
0x1400041ae  xor     rax, rsp
0x1400041b1  mov     [rbp+180h+var_30], rax
0x1400041b8  mov     r15, rdx
0x1400041bb  mov     qword ptr [rdx], 0
0x1400041c2  mov     rbx, rcx
0x1400041c5  call    cs:__imp_GetCurrentProcessId
0x1400041cc  nop     dword ptr [rax+rax+00h]
0x1400041d1  mov     r14d, 78h ; 'x'
0x1400041d7  mov     [rsp+280h+var_258], rbx
0x1400041dc  mov     r9d, eax
0x1400041df  mov     [rsp+280h+var_260], r14d; int
0x1400041e4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400041eb  mov     edx, 104h; unsigned __int64
0x1400041f0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400041f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400041fa  mov     r9d, 1F0001h; dwDesiredAccess
0x140004200  lea     rdx, [rsp+280h+Name]; lpName
0x140004205  xor     r8d, r8d; dwFlags
0x140004208  xor     ecx, ecx; lpMutexAttributes
0x14000420a  call    cs:__imp_CreateMutexExW
0x140004211  nop     dword ptr [rax+rax+00h]
0x140004216  mov     rbx, rax
0x140004219  test    rax, rax
0x14000421c  jnz     short loc_140004228
0x14000421e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004223  jmp     loc_1400044BF
0x140004228  xor     r8d, r8d; bAlertable
0x14000422b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000422e  mov     rcx, rbx; hHandle
0x140004231  call    cs:__imp_WaitForSingleObjectEx
0x140004238  nop     dword ptr [rax+rax+00h]
0x14000423d  cmp     eax, 102h
0x140004242  jz      short loc_140004254
0x140004244  test    eax, 0FFFFFF7Fh
0x140004249  jnz     loc_14000450A
0x14000424f  mov     rdi, rbx
0x140004252  jmp     short loc_140004256
0x140004254  xor     edi, edi
0x140004256  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14000425b  mov     [rsp+280h+var_250], 0
0x140004264  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004269  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000426e  mov     esi, eax
0x140004270  test    eax, eax
0x140004272  jns     loc_140004303
0x140004278  mov     rcx, [rbp+188h]; this
0x14000427f  lea     r8, aWil; "wil"
0x140004286  mov     r9d, eax; char *
0x140004289  mov     edx, 66h ; 'f'; void *
0x14000428e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004293  mov     rcx, [rbp+188h]; this
0x14000429a  lea     r8, aWil; "wil"
0x1400042a1  mov     r9d, esi; char *
0x1400042a4  mov     edx, 6Fh ; 'o'; void *
0x1400042a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042ae  mov     rcx, [rbp+188h]; this
0x1400042b5  lea     r8, aWil; "wil"
0x1400042bc  mov     r9d, esi; char *
0x1400042bf  mov     edx, 12Eh; void *
0x1400042c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042c9  test    rdi, rdi
0x1400042cc  jz      short loc_1400042E5
0x1400042ce  mov     rcx, rdi; hMutex
0x1400042d1  call    cs:__imp_ReleaseMutex
0x1400042d8  nop     dword ptr [rax+rax+00h]
0x1400042dd  test    eax, eax
0x1400042df  jz      loc_140004517
0x1400042e5  mov     rcx, rbx; hObject
0x1400042e8  call    cs:__imp_CloseHandle
0x1400042ef  nop     dword ptr [rax+rax+00h]
0x1400042f4  test    eax, eax
0x1400042f6  jz      loc_140004529
0x1400042fc  mov     eax, esi
0x1400042fe  jmp     loc_1400044BF
0x140004303  mov     rax, [rsp+280h+var_250]
0x140004308  lea     rcx, ds:0[rax*4]
0x140004310  test    rcx, rcx
0x140004313  jz      short loc_140004323
0x140004315  mov     [r15], rcx
0x140004318  mov     eax, [rcx]
0x14000431a  inc     eax
0x14000431c  mov     [rcx], eax
0x14000431e  jmp     loc_140004489
0x140004323  mov     rdx, r14; dwBytes
0x140004326  mov     qword ptr [r15], 0
0x14000432d  mov     ecx, 8; dwFlags
0x140004332  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004337  mov     r14, rax
0x14000433a  test    rax, rax
0x14000433d  jnz     short loc_140004361
0x14000433f  mov     rcx, [rbp+188h]; this
0x140004346  lea     r8, aWil; "wil"
0x14000434d  mov     esi, 8007000Eh
0x140004352  mov     edx, 14Bh; void *
0x140004357  mov     r9d, esi; char *
0x14000435a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000435f  jmp     short loc_1400043CB
0x140004361  xorps   xmm0, xmm0
0x140004364  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004369  mov     r8, r14; void *
0x14000436c  lea     rcx, [rsp+280h+var_250]; this
0x140004371  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140004377  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x14000437c  mov     esi, eax
0x14000437e  test    eax, eax
0x140004380  jns     loc_14000441E
0x140004386  mov     rcx, [rbp+188h]; this
0x14000438d  lea     r8, aWil; "wil"
0x140004394  mov     r9d, eax; char *
0x140004397  mov     edx, 14Eh; void *
0x14000439c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043a1  lea     rcx, [rsp+280h+var_250]; this
0x1400043a6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400043ab  call    cs:__imp_GetProcessHeap
0x1400043b2  nop     dword ptr [rax+rax+00h]
0x1400043b7  mov     r8, r14; lpMem
0x1400043ba  xor     edx, edx; dwFlags
0x1400043bc  mov     rcx, rax; hHeap
0x1400043bf  call    cs:__imp_HeapFree
0x1400043c6  nop     dword ptr [rax+rax+00h]
0x1400043cb  mov     rcx, [rbp+188h]; this
0x1400043d2  lea     r8, aWil; "wil"
0x1400043d9  mov     r9d, esi; char *
0x1400043dc  mov     edx, 137h; void *
0x1400043e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043e6  test    rdi, rdi
0x1400043e9  jz      short loc_140004402
0x1400043eb  mov     rcx, rdi; hMutex
0x1400043ee  call    cs:__imp_ReleaseMutex
0x1400043f5  nop     dword ptr [rax+rax+00h]
0x1400043fa  test    eax, eax
0x1400043fc  jz      loc_14000453B
0x140004402  mov     rcx, rbx; hObject
0x140004405  call    cs:__imp_CloseHandle
0x14000440c  nop     dword ptr [rax+rax+00h]
0x140004411  test    eax, eax
0x140004413  jz      loc_1400044F8
0x140004419  jmp     loc_1400042FC
0x14000441e  mov     rax, [rsp+280h+var_250]
0x140004423  lea     rcx, [r14+22h]; void *
0x140004427  xor     edx, edx; Val
0x140004429  mov     [r14+10h], rax
0x14000442d  mov     rax, [rsp+280h+var_250+8]
0x140004432  mov     dword ptr [r14], 1
0x140004439  mov     [r14+8], rbx
0x14000443d  lea     r8d, [rdx+56h]; Size
0x140004441  mov     [rsp+280h+var_250], 0
0x14000444a  mov     [r14+18h], rax
0x14000444e  mov     [rsp+280h+var_250+8], 0
0x140004457  call    memset_0
0x14000445c  xor     edx, edx; Val
0x14000445e  mov     word ptr [r14+20h], 58h ; 'X'
0x140004465  lea     rcx, [r14+28h]; void *
0x140004469  mov     dword ptr [r14+24h], 1
0x140004471  lea     r8d, [rdx+50h]; Size
0x140004475  call    memset_0
0x14000447a  lea     rcx, [rsp+280h+var_250]; this
0x14000447f  mov     [r15], r14
0x140004482  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140004487  xor     ebx, ebx
0x140004489  test    rdi, rdi
0x14000448c  jz      short loc_1400044A5
0x14000448e  mov     rcx, rdi; hMutex
0x140004491  call    cs:__imp_ReleaseMutex
0x140004498  nop     dword ptr [rax+rax+00h]
0x14000449d  test    eax, eax
0x14000449f  jz      loc_14000454D
0x1400044a5  test    rbx, rbx
0x1400044a8  jz      short loc_1400044BD
0x1400044aa  mov     rcx, rbx; hObject
0x1400044ad  call    cs:__imp_CloseHandle
0x1400044b4  nop     dword ptr [rax+rax+00h]
0x1400044b9  test    eax, eax
0x1400044bb  jz      short loc_1400044E6
0x1400044bd  xor     eax, eax
0x1400044bf  mov     rcx, [rbp+180h+var_30]
0x1400044c6  xor     rcx, rsp; StackCookie
0x1400044c9  call    __security_check_cookie
0x1400044ce  mov     rbx, [rsp+280h+arg_10]
0x1400044d6  add     rsp, 260h
0x1400044dd  pop     r15
0x1400044df  pop     r14
0x1400044e1  pop     rdi
0x1400044e2  pop     rsi
0x1400044e3  pop     rbp
0x1400044e4  retn
0x1400044e6  mov     rcx, [rbp+188h]; this
0x1400044ed  mov     edx, 0A0Bh; void *
0x1400044f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400044f8  mov     rcx, [rbp+188h]; this
0x1400044ff  mov     edx, 0A0Bh; void *
0x140004504  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000450a  mov     rcx, [rbp+188h]; this
0x140004511  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004517  mov     rcx, [rbp+188h]; this
0x14000451e  mov     edx, 0A15h; void *
0x140004523  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004529  mov     rcx, [rbp+188h]; this
0x140004530  mov     edx, 0A0Bh; void *
0x140004535  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000453b  mov     rcx, [rbp+188h]; this
0x140004542  mov     edx, 0A15h; void *
0x140004547  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000454d  mov     rcx, [rbp+188h]; this
0x140004554  mov     edx, 0A15h; void *
0x140004559  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
