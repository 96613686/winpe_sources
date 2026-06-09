# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003830`
- end: `0x140003bce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004880`

## callees

- `0x140003830`
- `0x140003e60`
- `0x140004090`
- `0x140004618`
- `0x1400050f8`
- `0x140005584`
- `0x140005d50`
- `0x140005e2c`
- `0x140006474`
- `0x140006484`
- `0x14000a33e`
- `0x14000a370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400038a8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400038a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000394a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003a73`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ae3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000394a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003a73`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ae3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400038c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400038c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003869`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000395b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000395b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003af9`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x140003830  mov     [rsp-8+arg_10], rbx
0x140003835  push    rbp
0x140003836  push    rsi
0x140003837  push    rdi
0x140003838  push    r14
0x14000383a  push    r15
0x14000383c  lea     rbp, [rsp-160h]
0x140003844  sub     rsp, 260h
0x14000384b  mov     rax, cs:__security_cookie
0x140003852  xor     rax, rsp
0x140003855  mov     [rbp+180h+var_30], rax
0x14000385c  mov     r15, rdx
0x14000385f  mov     qword ptr [rdx], 0
0x140003866  mov     rbx, rcx
0x140003869  call    cs:__imp_GetCurrentProcessId
0x14000386f  mov     r14d, 78h ; 'x'
0x140003875  mov     [rsp+280h+var_258], rbx
0x14000387a  mov     r9d, eax
0x14000387d  mov     [rsp+280h+var_260], r14d; int
0x140003882  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003889  mov     edx, 104h; unsigned __int64
0x14000388e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003893  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003898  mov     r9d, 1F0001h; dwDesiredAccess
0x14000389e  lea     rdx, [rsp+280h+Name]; lpName
0x1400038a3  xor     r8d, r8d; dwFlags
0x1400038a6  xor     ecx, ecx; lpMutexAttributes
0x1400038a8  call    cs:__imp_CreateMutexExW
0x1400038ae  mov     rbx, rax
0x1400038b1  test    rax, rax
0x1400038b4  jnz     short loc_1400038C0
0x1400038b6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400038bb  jmp     loc_140003B05
0x1400038c0  xor     r8d, r8d; bAlertable
0x1400038c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400038c6  mov     rcx, rbx; hHandle
0x1400038c9  call    cs:__imp_WaitForSingleObjectEx
0x1400038cf  cmp     eax, 102h
0x1400038d4  jz      short loc_1400038E6
0x1400038d6  test    eax, 0FFFFFF7Fh
0x1400038db  jnz     loc_140003B3D
0x1400038e1  mov     rdi, rbx
0x1400038e4  jmp     short loc_1400038E8
0x1400038e6  xor     edi, edi
0x1400038e8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400038ed  mov     [rsp+280h+hObject], 0
0x1400038f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400038fb  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003900  mov     esi, eax
0x140003902  test    eax, eax
0x140003904  jns     short loc_140003970
0x140003906  mov     rcx, [rbp+188h]; this
0x14000390d  mov     r9d, eax; char *
0x140003910  mov     edx, 66h ; 'f'; void *
0x140003915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000391a  mov     rcx, [rbp+188h]; this
0x140003921  mov     r9d, esi; char *
0x140003924  mov     edx, 6Fh ; 'o'; void *
0x140003929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000392e  mov     rcx, [rbp+188h]; this
0x140003935  mov     r9d, esi; char *
0x140003938  mov     edx, 12Eh; void *
0x14000393d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003942  test    rdi, rdi
0x140003945  jz      short loc_140003958
0x140003947  mov     rcx, rdi; hMutex
0x14000394a  call    cs:__imp_ReleaseMutex
0x140003950  test    eax, eax
0x140003952  jz      loc_140003B4A
0x140003958  mov     rcx, rbx; hObject
0x14000395b  call    cs:__imp_CloseHandle
0x140003961  test    eax, eax
0x140003963  jz      loc_140003B5C
0x140003969  mov     eax, esi
0x14000396b  jmp     loc_140003B05
0x140003970  mov     rax, [rsp+280h+hObject]
0x140003975  lea     rcx, ds:0[rax*4]
0x14000397d  test    rcx, rcx
0x140003980  jz      short loc_140003990
0x140003982  mov     [r15], rcx
0x140003985  mov     eax, [rcx]
0x140003987  inc     eax
0x140003989  mov     [rcx], eax
0x14000398b  jmp     loc_140003ADB
0x140003990  mov     rdx, r14; dwBytes
0x140003993  mov     qword ptr [r15], 0
0x14000399a  mov     ecx, 8; dwFlags
0x14000399f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400039a4  mov     rsi, rax
0x1400039a7  test    rax, rax
0x1400039aa  jnz     short loc_1400039CB
0x1400039ac  mov     rcx, [rbp+188h]; this
0x1400039b3  mov     r14d, 8007000Eh
0x1400039b9  mov     r9d, r14d; char *
0x1400039bc  mov     edx, 14Bh; void *
0x1400039c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400039c6  jmp     loc_140003A57
0x1400039cb  xorps   xmm0, xmm0
0x1400039ce  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400039d4  test    sil, 3
0x1400039d8  jnz     loc_140003B6E
0x1400039de  mov     r9, rsi
0x1400039e1  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400039e6  shr     r9, 2; unsigned __int64
0x1400039ea  lea     rcx, [rsp+280h+hObject]; this
0x1400039ef  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400039f4  mov     r14d, eax
0x1400039f7  test    eax, eax
0x1400039f9  jns     loc_140003A97
0x1400039ff  mov     rcx, [rbp+188h]; this
0x140003a06  mov     r9d, eax; char *
0x140003a09  mov     edx, 14Eh; void *
0x140003a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a13  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003a18  test    rcx, rcx
0x140003a1b  jz      short loc_140003A2B
0x140003a1d  call    cs:__imp_CloseHandle
0x140003a23  test    eax, eax
0x140003a25  jz      loc_140003B74
0x140003a2b  mov     rcx, [rsp+280h+hObject]; hObject
0x140003a30  test    rcx, rcx
0x140003a33  jz      short loc_140003A43
0x140003a35  call    cs:__imp_CloseHandle
0x140003a3b  test    eax, eax
0x140003a3d  jz      loc_140003B86
0x140003a43  call    cs:__imp_GetProcessHeap
0x140003a49  mov     r8, rsi; lpMem
0x140003a4c  xor     edx, edx; dwFlags
0x140003a4e  mov     rcx, rax; hHeap
0x140003a51  call    cs:__imp_HeapFree
0x140003a57  mov     rcx, [rbp+188h]; this
0x140003a5e  mov     r9d, r14d; char *
0x140003a61  mov     edx, 137h; void *
0x140003a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a6b  test    rdi, rdi
0x140003a6e  jz      short loc_140003A81
0x140003a70  mov     rcx, rdi; hMutex
0x140003a73  call    cs:__imp_ReleaseMutex
0x140003a79  test    eax, eax
0x140003a7b  jz      loc_140003B98
0x140003a81  mov     rcx, rbx; hObject
0x140003a84  call    cs:__imp_CloseHandle
0x140003a8a  test    eax, eax
0x140003a8c  jz      loc_140003BAA
0x140003a92  mov     eax, r14d
0x140003a95  jmp     short loc_140003B05
0x140003a97  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003a9c  xor     edx, edx; Val
0x140003a9e  mov     dword ptr [rsi], 1
0x140003aa4  lea     rcx, [rsi+22h]; void *
0x140003aa8  mov     [rsi+8], rbx
0x140003aac  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003ab1  lea     r8d, [rdx+56h]; Size
0x140003ab5  call    memset_0
0x140003aba  xor     edx, edx; Val
0x140003abc  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003ac2  lea     rcx, [rsi+28h]; void *
0x140003ac6  mov     dword ptr [rsi+24h], 1
0x140003acd  lea     r8d, [rdx+50h]; Size
0x140003ad1  call    memset_0
0x140003ad6  xor     ebx, ebx
0x140003ad8  mov     [r15], rsi
0x140003adb  test    rdi, rdi
0x140003ade  jz      short loc_140003AF1
0x140003ae0  mov     rcx, rdi; hMutex
0x140003ae3  call    cs:__imp_ReleaseMutex
0x140003ae9  test    eax, eax
0x140003aeb  jz      loc_140003BBC
0x140003af1  test    rbx, rbx
0x140003af4  jz      short loc_140003B03
0x140003af6  mov     rcx, rbx; hObject
0x140003af9  call    cs:__imp_CloseHandle
0x140003aff  test    eax, eax
0x140003b01  jz      short loc_140003B2B
0x140003b03  xor     eax, eax
0x140003b05  mov     rcx, [rbp+180h+var_30]
0x140003b0c  xor     rcx, rsp; StackCookie
0x140003b0f  call    __security_check_cookie
0x140003b14  mov     rbx, [rsp+280h+arg_10]
0x140003b1c  add     rsp, 260h
0x140003b23  pop     r15
0x140003b25  pop     r14
0x140003b27  pop     rdi
0x140003b28  pop     rsi
0x140003b29  pop     rbp
0x140003b2a  retn
0x140003b2b  mov     rcx, [rbp+188h]; this
0x140003b32  mov     edx, 0A0Bh; void *
0x140003b37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b3d  mov     rcx, [rbp+188h]; this
0x140003b44  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003b4a  mov     rcx, [rbp+188h]; this
0x140003b51  mov     edx, 0A15h; void *
0x140003b56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b5c  mov     rcx, [rbp+188h]; this
0x140003b63  mov     edx, 0A0Bh; void *
0x140003b68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b6e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003b74  mov     rcx, [rbp+188h]; this
0x140003b7b  mov     edx, 0A0Bh; void *
0x140003b80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b86  mov     rcx, [rbp+188h]; this
0x140003b8d  mov     edx, 0A0Bh; void *
0x140003b92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b98  mov     rcx, [rbp+188h]; this
0x140003b9f  mov     edx, 0A15h; void *
0x140003ba4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003baa  mov     rcx, [rbp+188h]; this
0x140003bb1  mov     edx, 0A0Bh; void *
0x140003bb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003bbc  mov     rcx, [rbp+188h]; this
0x140003bc3  mov     edx, 0A15h; void *
0x140003bc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
