# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000870c`
- end: `0x180008aaa`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180009e6c`

## callees

- `0x18000870c`
- `0x180008e80`
- `0x1800092e4`
- `0x180009c08`
- `0x18000a7f8`
- `0x18000ba90`
- `0x18000bf60`
- `0x18000c268`
- `0x18000ca3c`
- `0x18000ca4c`
- `0x18000d89e`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000894f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008826`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000894f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089bf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008784`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008784`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000892d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000892d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000891f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000891f`

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
0x18000870c  mov     [rsp-8+arg_10], rbx
0x180008711  push    rbp
0x180008712  push    rsi
0x180008713  push    rdi
0x180008714  push    r14
0x180008716  push    r15
0x180008718  lea     rbp, [rsp-160h]
0x180008720  sub     rsp, 260h
0x180008727  mov     rax, cs:__security_cookie
0x18000872e  xor     rax, rsp
0x180008731  mov     [rbp+180h+var_30], rax
0x180008738  mov     r15, rdx
0x18000873b  mov     qword ptr [rdx], 0
0x180008742  mov     rbx, rcx
0x180008745  call    cs:__imp_GetCurrentProcessId
0x18000874b  mov     r14d, 78h ; 'x'
0x180008751  mov     [rsp+280h+var_258], rbx
0x180008756  mov     r9d, eax
0x180008759  mov     [rsp+280h+var_260], r14d; int
0x18000875e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008765  mov     edx, 104h; unsigned __int64
0x18000876a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000876f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008774  mov     r9d, 1F0001h; dwDesiredAccess
0x18000877a  lea     rdx, [rsp+280h+Name]; lpName
0x18000877f  xor     r8d, r8d; dwFlags
0x180008782  xor     ecx, ecx; lpMutexAttributes
0x180008784  call    cs:__imp_CreateMutexExW
0x18000878a  mov     rbx, rax
0x18000878d  test    rax, rax
0x180008790  jnz     short loc_18000879C
0x180008792  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008797  jmp     loc_1800089E1
0x18000879c  xor     r8d, r8d; bAlertable
0x18000879f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800087a2  mov     rcx, rbx; hHandle
0x1800087a5  call    cs:__imp_WaitForSingleObjectEx
0x1800087ab  cmp     eax, 102h
0x1800087b0  jz      short loc_1800087C2
0x1800087b2  test    eax, 0FFFFFF7Fh
0x1800087b7  jnz     loc_180008A19
0x1800087bd  mov     rdi, rbx
0x1800087c0  jmp     short loc_1800087C4
0x1800087c2  xor     edi, edi
0x1800087c4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800087c9  mov     [rsp+280h+hObject], 0
0x1800087d2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800087d7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800087dc  mov     esi, eax
0x1800087de  test    eax, eax
0x1800087e0  jns     short loc_18000884C
0x1800087e2  mov     rcx, [rbp+188h]; this
0x1800087e9  mov     r9d, eax; char *
0x1800087ec  mov     edx, 66h ; 'f'; void *
0x1800087f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087f6  mov     rcx, [rbp+188h]; this
0x1800087fd  mov     r9d, esi; char *
0x180008800  mov     edx, 6Fh ; 'o'; void *
0x180008805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000880a  mov     rcx, [rbp+188h]; this
0x180008811  mov     r9d, esi; char *
0x180008814  mov     edx, 12Eh; void *
0x180008819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000881e  test    rdi, rdi
0x180008821  jz      short loc_180008834
0x180008823  mov     rcx, rdi; hMutex
0x180008826  call    cs:__imp_ReleaseMutex
0x18000882c  test    eax, eax
0x18000882e  jz      loc_180008A26
0x180008834  mov     rcx, rbx; hObject
0x180008837  call    cs:__imp_CloseHandle
0x18000883d  test    eax, eax
0x18000883f  jz      loc_180008A38
0x180008845  mov     eax, esi
0x180008847  jmp     loc_1800089E1
0x18000884c  mov     rax, [rsp+280h+hObject]
0x180008851  lea     rcx, ds:0[rax*4]
0x180008859  test    rcx, rcx
0x18000885c  jz      short loc_18000886C
0x18000885e  mov     [r15], rcx
0x180008861  mov     eax, [rcx]
0x180008863  inc     eax
0x180008865  mov     [rcx], eax
0x180008867  jmp     loc_1800089B7
0x18000886c  mov     rdx, r14; dwBytes
0x18000886f  mov     qword ptr [r15], 0
0x180008876  mov     ecx, 8; dwFlags
0x18000887b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008880  mov     rsi, rax
0x180008883  test    rax, rax
0x180008886  jnz     short loc_1800088A7
0x180008888  mov     rcx, [rbp+188h]; this
0x18000888f  mov     r14d, 8007000Eh
0x180008895  mov     r9d, r14d; char *
0x180008898  mov     edx, 14Bh; void *
0x18000889d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088a2  jmp     loc_180008933
0x1800088a7  xorps   xmm0, xmm0
0x1800088aa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800088b0  test    sil, 3
0x1800088b4  jnz     loc_180008A4A
0x1800088ba  mov     r9, rsi
0x1800088bd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800088c2  shr     r9, 2; unsigned __int64
0x1800088c6  lea     rcx, [rsp+280h+hObject]; this
0x1800088cb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800088d0  mov     r14d, eax
0x1800088d3  test    eax, eax
0x1800088d5  jns     loc_180008973
0x1800088db  mov     rcx, [rbp+188h]; this
0x1800088e2  mov     r9d, eax; char *
0x1800088e5  mov     edx, 14Eh; void *
0x1800088ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088ef  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800088f4  test    rcx, rcx
0x1800088f7  jz      short loc_180008907
0x1800088f9  call    cs:__imp_CloseHandle
0x1800088ff  test    eax, eax
0x180008901  jz      loc_180008A50
0x180008907  mov     rcx, [rsp+280h+hObject]; hObject
0x18000890c  test    rcx, rcx
0x18000890f  jz      short loc_18000891F
0x180008911  call    cs:__imp_CloseHandle
0x180008917  test    eax, eax
0x180008919  jz      loc_180008A62
0x18000891f  call    cs:__imp_GetProcessHeap
0x180008925  mov     r8, rsi; lpMem
0x180008928  xor     edx, edx; dwFlags
0x18000892a  mov     rcx, rax; hHeap
0x18000892d  call    cs:__imp_HeapFree
0x180008933  mov     rcx, [rbp+188h]; this
0x18000893a  mov     r9d, r14d; char *
0x18000893d  mov     edx, 137h; void *
0x180008942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008947  test    rdi, rdi
0x18000894a  jz      short loc_18000895D
0x18000894c  mov     rcx, rdi; hMutex
0x18000894f  call    cs:__imp_ReleaseMutex
0x180008955  test    eax, eax
0x180008957  jz      loc_180008A74
0x18000895d  mov     rcx, rbx; hObject
0x180008960  call    cs:__imp_CloseHandle
0x180008966  test    eax, eax
0x180008968  jz      loc_180008A86
0x18000896e  mov     eax, r14d
0x180008971  jmp     short loc_1800089E1
0x180008973  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008978  xor     edx, edx; Val
0x18000897a  mov     dword ptr [rsi], 1
0x180008980  lea     rcx, [rsi+22h]; void *
0x180008984  mov     [rsi+8], rbx
0x180008988  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000898d  lea     r8d, [rdx+56h]; Size
0x180008991  call    memset_0
0x180008996  xor     edx, edx; Val
0x180008998  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000899e  lea     rcx, [rsi+28h]; void *
0x1800089a2  mov     dword ptr [rsi+24h], 1
0x1800089a9  lea     r8d, [rdx+50h]; Size
0x1800089ad  call    memset_0
0x1800089b2  xor     ebx, ebx
0x1800089b4  mov     [r15], rsi
0x1800089b7  test    rdi, rdi
0x1800089ba  jz      short loc_1800089CD
0x1800089bc  mov     rcx, rdi; hMutex
0x1800089bf  call    cs:__imp_ReleaseMutex
0x1800089c5  test    eax, eax
0x1800089c7  jz      loc_180008A98
0x1800089cd  test    rbx, rbx
0x1800089d0  jz      short loc_1800089DF
0x1800089d2  mov     rcx, rbx; hObject
0x1800089d5  call    cs:__imp_CloseHandle
0x1800089db  test    eax, eax
0x1800089dd  jz      short loc_180008A07
0x1800089df  xor     eax, eax
0x1800089e1  mov     rcx, [rbp+180h+var_30]
0x1800089e8  xor     rcx, rsp; StackCookie
0x1800089eb  call    __security_check_cookie
0x1800089f0  mov     rbx, [rsp+280h+arg_10]
0x1800089f8  add     rsp, 260h
0x1800089ff  pop     r15
0x180008a01  pop     r14
0x180008a03  pop     rdi
0x180008a04  pop     rsi
0x180008a05  pop     rbp
0x180008a06  retn
0x180008a07  mov     rcx, [rbp+188h]; this
0x180008a0e  mov     edx, 0A0Bh; void *
0x180008a13  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a19  mov     rcx, [rbp+188h]; this
0x180008a20  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008a26  mov     rcx, [rbp+188h]; this
0x180008a2d  mov     edx, 0A15h; void *
0x180008a32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a38  mov     rcx, [rbp+188h]; this
0x180008a3f  mov     edx, 0A0Bh; void *
0x180008a44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a4a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008a50  mov     rcx, [rbp+188h]; this
0x180008a57  mov     edx, 0A0Bh; void *
0x180008a5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a62  mov     rcx, [rbp+188h]; this
0x180008a69  mov     edx, 0A0Bh; void *
0x180008a6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a74  mov     rcx, [rbp+188h]; this
0x180008a7b  mov     edx, 0A15h; void *
0x180008a80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a86  mov     rcx, [rbp+188h]; this
0x180008a8d  mov     edx, 0A0Bh; void *
0x180008a92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a98  mov     rcx, [rbp+188h]; this
0x180008a9f  mov     edx, 0A15h; void *
0x180008aa4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
