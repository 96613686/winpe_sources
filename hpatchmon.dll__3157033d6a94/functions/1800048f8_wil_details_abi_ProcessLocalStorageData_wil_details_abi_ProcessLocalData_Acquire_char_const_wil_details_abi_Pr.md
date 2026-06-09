# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800048f8`
- end: `0x180004c96`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006d80`

## callees

- `0x180002270`
- `0x180002be8`
- `0x1800048f8`
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

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004931`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004970`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004970`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004991`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004991`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004afd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004afd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bc1`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1800048f8  mov     [rsp-8+arg_10], rbx
0x1800048fd  push    rbp
0x1800048fe  push    rsi
0x1800048ff  push    rdi
0x180004900  push    r14
0x180004902  push    r15
0x180004904  lea     rbp, [rsp-160h]
0x18000490c  sub     rsp, 260h
0x180004913  mov     rax, cs:__security_cookie
0x18000491a  xor     rax, rsp
0x18000491d  mov     [rbp+180h+var_30], rax
0x180004924  mov     r15, rdx
0x180004927  mov     qword ptr [rdx], 0
0x18000492e  mov     rbx, rcx
0x180004931  call    cs:__imp_GetCurrentProcessId
0x180004937  mov     r14d, 78h ; 'x'
0x18000493d  mov     [rsp+280h+var_258], rbx
0x180004942  mov     r9d, eax
0x180004945  mov     [rsp+280h+var_260], r14d; int
0x18000494a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004951  mov     edx, 104h; unsigned __int64
0x180004956  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000495b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004960  mov     r9d, 1F0001h; dwDesiredAccess
0x180004966  lea     rdx, [rsp+280h+Name]; lpName
0x18000496b  xor     r8d, r8d; dwFlags
0x18000496e  xor     ecx, ecx; lpMutexAttributes
0x180004970  call    cs:__imp_CreateMutexExW
0x180004976  mov     rbx, rax
0x180004979  test    rax, rax
0x18000497c  jnz     short loc_180004988
0x18000497e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004983  jmp     loc_180004BCD
0x180004988  xor     r8d, r8d; bAlertable
0x18000498b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000498e  mov     rcx, rbx; hHandle
0x180004991  call    cs:__imp_WaitForSingleObjectEx
0x180004997  cmp     eax, 102h
0x18000499c  jz      short loc_1800049AE
0x18000499e  test    eax, 0FFFFFF7Fh
0x1800049a3  jnz     loc_180004C05
0x1800049a9  mov     rdi, rbx
0x1800049ac  jmp     short loc_1800049B0
0x1800049ae  xor     edi, edi
0x1800049b0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800049b5  mov     [rsp+280h+hObject], 0
0x1800049be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800049c3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800049c8  mov     esi, eax
0x1800049ca  test    eax, eax
0x1800049cc  jns     short loc_180004A38
0x1800049ce  mov     rcx, [rbp+188h]; this
0x1800049d5  mov     r9d, eax; char *
0x1800049d8  mov     edx, 66h ; 'f'; void *
0x1800049dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049e2  mov     rcx, [rbp+188h]; this
0x1800049e9  mov     r9d, esi; char *
0x1800049ec  mov     edx, 6Fh ; 'o'; void *
0x1800049f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049f6  mov     rcx, [rbp+188h]; this
0x1800049fd  mov     r9d, esi; char *
0x180004a00  mov     edx, 12Eh; void *
0x180004a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a0a  test    rdi, rdi
0x180004a0d  jz      short loc_180004A20
0x180004a0f  mov     rcx, rdi; hMutex
0x180004a12  call    cs:__imp_ReleaseMutex
0x180004a18  test    eax, eax
0x180004a1a  jz      loc_180004C12
0x180004a20  mov     rcx, rbx; hObject
0x180004a23  call    cs:__imp_CloseHandle
0x180004a29  test    eax, eax
0x180004a2b  jz      loc_180004C24
0x180004a31  mov     eax, esi
0x180004a33  jmp     loc_180004BCD
0x180004a38  mov     rax, [rsp+280h+hObject]
0x180004a3d  lea     rcx, ds:0[rax*4]
0x180004a45  test    rcx, rcx
0x180004a48  jz      short loc_180004A58
0x180004a4a  mov     [r15], rcx
0x180004a4d  mov     eax, [rcx]
0x180004a4f  inc     eax
0x180004a51  mov     [rcx], eax
0x180004a53  jmp     loc_180004BA3
0x180004a58  mov     rdx, r14; dwBytes
0x180004a5b  mov     qword ptr [r15], 0
0x180004a62  mov     ecx, 8; dwFlags
0x180004a67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a6c  mov     rsi, rax
0x180004a6f  test    rax, rax
0x180004a72  jnz     short loc_180004A93
0x180004a74  mov     rcx, [rbp+188h]; this
0x180004a7b  mov     r14d, 8007000Eh
0x180004a81  mov     r9d, r14d; char *
0x180004a84  mov     edx, 14Bh; void *
0x180004a89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a8e  jmp     loc_180004B1F
0x180004a93  xorps   xmm0, xmm0
0x180004a96  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004a9c  test    sil, 3
0x180004aa0  jnz     loc_180004C36
0x180004aa6  mov     r9, rsi
0x180004aa9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004aae  shr     r9, 2; unsigned __int64
0x180004ab2  lea     rcx, [rsp+280h+hObject]; this
0x180004ab7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004abc  mov     r14d, eax
0x180004abf  test    eax, eax
0x180004ac1  jns     loc_180004B5F
0x180004ac7  mov     rcx, [rbp+188h]; this
0x180004ace  mov     r9d, eax; char *
0x180004ad1  mov     edx, 14Eh; void *
0x180004ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004adb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004ae0  test    rcx, rcx
0x180004ae3  jz      short loc_180004AF3
0x180004ae5  call    cs:__imp_CloseHandle
0x180004aeb  test    eax, eax
0x180004aed  jz      loc_180004C3C
0x180004af3  mov     rcx, [rsp+280h+hObject]; hObject
0x180004af8  test    rcx, rcx
0x180004afb  jz      short loc_180004B0B
0x180004afd  call    cs:__imp_CloseHandle
0x180004b03  test    eax, eax
0x180004b05  jz      loc_180004C4E
0x180004b0b  call    cs:__imp_GetProcessHeap
0x180004b11  mov     r8, rsi; lpMem
0x180004b14  xor     edx, edx; dwFlags
0x180004b16  mov     rcx, rax; hHeap
0x180004b19  call    cs:__imp_HeapFree
0x180004b1f  mov     rcx, [rbp+188h]; this
0x180004b26  mov     r9d, r14d; char *
0x180004b29  mov     edx, 137h; void *
0x180004b2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b33  test    rdi, rdi
0x180004b36  jz      short loc_180004B49
0x180004b38  mov     rcx, rdi; hMutex
0x180004b3b  call    cs:__imp_ReleaseMutex
0x180004b41  test    eax, eax
0x180004b43  jz      loc_180004C60
0x180004b49  mov     rcx, rbx; hObject
0x180004b4c  call    cs:__imp_CloseHandle
0x180004b52  test    eax, eax
0x180004b54  jz      loc_180004C72
0x180004b5a  mov     eax, r14d
0x180004b5d  jmp     short loc_180004BCD
0x180004b5f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004b64  xor     edx, edx; Val
0x180004b66  mov     dword ptr [rsi], 1
0x180004b6c  lea     rcx, [rsi+22h]; void *
0x180004b70  mov     [rsi+8], rbx
0x180004b74  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004b79  lea     r8d, [rdx+56h]; Size
0x180004b7d  call    memset_0
0x180004b82  xor     edx, edx; Val
0x180004b84  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004b8a  lea     rcx, [rsi+28h]; void *
0x180004b8e  mov     dword ptr [rsi+24h], 1
0x180004b95  lea     r8d, [rdx+50h]; Size
0x180004b99  call    memset_0
0x180004b9e  xor     ebx, ebx
0x180004ba0  mov     [r15], rsi
0x180004ba3  test    rdi, rdi
0x180004ba6  jz      short loc_180004BB9
0x180004ba8  mov     rcx, rdi; hMutex
0x180004bab  call    cs:__imp_ReleaseMutex
0x180004bb1  test    eax, eax
0x180004bb3  jz      loc_180004C84
0x180004bb9  test    rbx, rbx
0x180004bbc  jz      short loc_180004BCB
0x180004bbe  mov     rcx, rbx; hObject
0x180004bc1  call    cs:__imp_CloseHandle
0x180004bc7  test    eax, eax
0x180004bc9  jz      short loc_180004BF3
0x180004bcb  xor     eax, eax
0x180004bcd  mov     rcx, [rbp+180h+var_30]
0x180004bd4  xor     rcx, rsp; StackCookie
0x180004bd7  call    __security_check_cookie
0x180004bdc  mov     rbx, [rsp+280h+arg_10]
0x180004be4  add     rsp, 260h
0x180004beb  pop     r15
0x180004bed  pop     r14
0x180004bef  pop     rdi
0x180004bf0  pop     rsi
0x180004bf1  pop     rbp
0x180004bf2  retn
0x180004bf3  mov     rcx, [rbp+188h]; this
0x180004bfa  mov     edx, 0A0Bh; void *
0x180004bff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c05  mov     rcx, [rbp+188h]; this
0x180004c0c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004c12  mov     rcx, [rbp+188h]; this
0x180004c19  mov     edx, 0A15h; void *
0x180004c1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c24  mov     rcx, [rbp+188h]; this
0x180004c2b  mov     edx, 0A0Bh; void *
0x180004c30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c3c  mov     rcx, [rbp+188h]; this
0x180004c43  mov     edx, 0A0Bh; void *
0x180004c48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c4e  mov     rcx, [rbp+188h]; this
0x180004c55  mov     edx, 0A0Bh; void *
0x180004c5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c60  mov     rcx, [rbp+188h]; this
0x180004c67  mov     edx, 0A15h; void *
0x180004c6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c72  mov     rcx, [rbp+188h]; this
0x180004c79  mov     edx, 0A0Bh; void *
0x180004c7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c84  mov     rcx, [rbp+188h]; this
0x180004c8b  mov     edx, 0A15h; void *
0x180004c90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
