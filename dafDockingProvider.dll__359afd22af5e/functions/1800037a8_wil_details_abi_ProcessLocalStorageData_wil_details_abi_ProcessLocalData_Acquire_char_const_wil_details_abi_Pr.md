# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800037a8`
- end: `0x180003b46`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004e40`

## callees

- `0x1800037a8`
- `0x180003f1c`
- `0x180004374`
- `0x180004bd8`
- `0x1800057d8`
- `0x180006aa4`
- `0x1800073d8`
- `0x18000770c`
- `0x180007edc`
- `0x180007eec`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003820`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003820`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003841`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800037e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800037e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003995`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003995`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a71`

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
0x1800037a8  mov     [rsp-8+arg_10], rbx
0x1800037ad  push    rbp
0x1800037ae  push    rsi
0x1800037af  push    rdi
0x1800037b0  push    r14
0x1800037b2  push    r15
0x1800037b4  lea     rbp, [rsp-160h]
0x1800037bc  sub     rsp, 260h
0x1800037c3  mov     rax, cs:__security_cookie
0x1800037ca  xor     rax, rsp
0x1800037cd  mov     [rbp+180h+var_30], rax
0x1800037d4  mov     r15, rdx
0x1800037d7  mov     qword ptr [rdx], 0
0x1800037de  mov     rbx, rcx
0x1800037e1  call    cs:__imp_GetCurrentProcessId
0x1800037e7  mov     r14d, 78h ; 'x'
0x1800037ed  mov     [rsp+280h+var_258], rbx
0x1800037f2  mov     r9d, eax
0x1800037f5  mov     [rsp+280h+var_260], r14d; int
0x1800037fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003801  mov     edx, 104h; unsigned __int64
0x180003806  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000380b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003810  mov     r9d, 1F0001h; dwDesiredAccess
0x180003816  lea     rdx, [rsp+280h+Name]; lpName
0x18000381b  xor     r8d, r8d; dwFlags
0x18000381e  xor     ecx, ecx; lpMutexAttributes
0x180003820  call    cs:__imp_CreateMutexExW
0x180003826  mov     rbx, rax
0x180003829  test    rax, rax
0x18000382c  jnz     short loc_180003838
0x18000382e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003833  jmp     loc_180003A7D
0x180003838  xor     r8d, r8d; bAlertable
0x18000383b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000383e  mov     rcx, rbx; hHandle
0x180003841  call    cs:__imp_WaitForSingleObjectEx
0x180003847  cmp     eax, 102h
0x18000384c  jz      short loc_18000385E
0x18000384e  test    eax, 0FFFFFF7Fh
0x180003853  jnz     loc_180003AB5
0x180003859  mov     rdi, rbx
0x18000385c  jmp     short loc_180003860
0x18000385e  xor     edi, edi
0x180003860  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003865  mov     [rsp+280h+hObject], 0
0x18000386e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003873  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003878  mov     esi, eax
0x18000387a  test    eax, eax
0x18000387c  jns     short loc_1800038E8
0x18000387e  mov     rcx, [rbp+188h]; this
0x180003885  mov     r9d, eax; char *
0x180003888  mov     edx, 66h ; 'f'; void *
0x18000388d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003892  mov     rcx, [rbp+188h]; this
0x180003899  mov     r9d, esi; char *
0x18000389c  mov     edx, 6Fh ; 'o'; void *
0x1800038a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038a6  mov     rcx, [rbp+188h]; this
0x1800038ad  mov     r9d, esi; char *
0x1800038b0  mov     edx, 12Eh; void *
0x1800038b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ba  test    rdi, rdi
0x1800038bd  jz      short loc_1800038D0
0x1800038bf  mov     rcx, rdi; hMutex
0x1800038c2  call    cs:__imp_ReleaseMutex
0x1800038c8  test    eax, eax
0x1800038ca  jz      loc_180003AC2
0x1800038d0  mov     rcx, rbx; hObject
0x1800038d3  call    cs:__imp_CloseHandle
0x1800038d9  test    eax, eax
0x1800038db  jz      loc_180003AD4
0x1800038e1  mov     eax, esi
0x1800038e3  jmp     loc_180003A7D
0x1800038e8  mov     rax, [rsp+280h+hObject]
0x1800038ed  lea     rcx, ds:0[rax*4]
0x1800038f5  test    rcx, rcx
0x1800038f8  jz      short loc_180003908
0x1800038fa  mov     [r15], rcx
0x1800038fd  mov     eax, [rcx]
0x1800038ff  inc     eax
0x180003901  mov     [rcx], eax
0x180003903  jmp     loc_180003A53
0x180003908  mov     rdx, r14; dwBytes
0x18000390b  mov     qword ptr [r15], 0
0x180003912  mov     ecx, 8; dwFlags
0x180003917  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000391c  mov     rsi, rax
0x18000391f  test    rax, rax
0x180003922  jnz     short loc_180003943
0x180003924  mov     rcx, [rbp+188h]; this
0x18000392b  mov     r14d, 8007000Eh
0x180003931  mov     r9d, r14d; char *
0x180003934  mov     edx, 14Bh; void *
0x180003939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000393e  jmp     loc_1800039CF
0x180003943  xorps   xmm0, xmm0
0x180003946  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000394c  test    sil, 3
0x180003950  jnz     loc_180003AE6
0x180003956  mov     r9, rsi
0x180003959  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000395e  shr     r9, 2; unsigned __int64
0x180003962  lea     rcx, [rsp+280h+hObject]; this
0x180003967  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000396c  mov     r14d, eax
0x18000396f  test    eax, eax
0x180003971  jns     loc_180003A0F
0x180003977  mov     rcx, [rbp+188h]; this
0x18000397e  mov     r9d, eax; char *
0x180003981  mov     edx, 14Eh; void *
0x180003986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000398b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003990  test    rcx, rcx
0x180003993  jz      short loc_1800039A3
0x180003995  call    cs:__imp_CloseHandle
0x18000399b  test    eax, eax
0x18000399d  jz      loc_180003AEC
0x1800039a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800039a8  test    rcx, rcx
0x1800039ab  jz      short loc_1800039BB
0x1800039ad  call    cs:__imp_CloseHandle
0x1800039b3  test    eax, eax
0x1800039b5  jz      loc_180003AFE
0x1800039bb  call    cs:__imp_GetProcessHeap
0x1800039c1  mov     r8, rsi; lpMem
0x1800039c4  xor     edx, edx; dwFlags
0x1800039c6  mov     rcx, rax; hHeap
0x1800039c9  call    cs:__imp_HeapFree
0x1800039cf  mov     rcx, [rbp+188h]; this
0x1800039d6  mov     r9d, r14d; char *
0x1800039d9  mov     edx, 137h; void *
0x1800039de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039e3  test    rdi, rdi
0x1800039e6  jz      short loc_1800039F9
0x1800039e8  mov     rcx, rdi; hMutex
0x1800039eb  call    cs:__imp_ReleaseMutex
0x1800039f1  test    eax, eax
0x1800039f3  jz      loc_180003B10
0x1800039f9  mov     rcx, rbx; hObject
0x1800039fc  call    cs:__imp_CloseHandle
0x180003a02  test    eax, eax
0x180003a04  jz      loc_180003B22
0x180003a0a  mov     eax, r14d
0x180003a0d  jmp     short loc_180003A7D
0x180003a0f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003a14  xor     edx, edx; Val
0x180003a16  mov     dword ptr [rsi], 1
0x180003a1c  lea     rcx, [rsi+22h]; void *
0x180003a20  mov     [rsi+8], rbx
0x180003a24  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003a29  lea     r8d, [rdx+56h]; Size
0x180003a2d  call    memset_0
0x180003a32  xor     edx, edx; Val
0x180003a34  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003a3a  lea     rcx, [rsi+28h]; void *
0x180003a3e  mov     dword ptr [rsi+24h], 1
0x180003a45  lea     r8d, [rdx+50h]; Size
0x180003a49  call    memset_0
0x180003a4e  xor     ebx, ebx
0x180003a50  mov     [r15], rsi
0x180003a53  test    rdi, rdi
0x180003a56  jz      short loc_180003A69
0x180003a58  mov     rcx, rdi; hMutex
0x180003a5b  call    cs:__imp_ReleaseMutex
0x180003a61  test    eax, eax
0x180003a63  jz      loc_180003B34
0x180003a69  test    rbx, rbx
0x180003a6c  jz      short loc_180003A7B
0x180003a6e  mov     rcx, rbx; hObject
0x180003a71  call    cs:__imp_CloseHandle
0x180003a77  test    eax, eax
0x180003a79  jz      short loc_180003AA3
0x180003a7b  xor     eax, eax
0x180003a7d  mov     rcx, [rbp+180h+var_30]
0x180003a84  xor     rcx, rsp; StackCookie
0x180003a87  call    __security_check_cookie
0x180003a8c  mov     rbx, [rsp+280h+arg_10]
0x180003a94  add     rsp, 260h
0x180003a9b  pop     r15
0x180003a9d  pop     r14
0x180003a9f  pop     rdi
0x180003aa0  pop     rsi
0x180003aa1  pop     rbp
0x180003aa2  retn
0x180003aa3  mov     rcx, [rbp+188h]; this
0x180003aaa  mov     edx, 0A0Bh; void *
0x180003aaf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ab5  mov     rcx, [rbp+188h]; this
0x180003abc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003ac2  mov     rcx, [rbp+188h]; this
0x180003ac9  mov     edx, 0A15h; void *
0x180003ace  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ad4  mov     rcx, [rbp+188h]; this
0x180003adb  mov     edx, 0A0Bh; void *
0x180003ae0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ae6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003aec  mov     rcx, [rbp+188h]; this
0x180003af3  mov     edx, 0A0Bh; void *
0x180003af8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003afe  mov     rcx, [rbp+188h]; this
0x180003b05  mov     edx, 0A0Bh; void *
0x180003b0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b10  mov     rcx, [rbp+188h]; this
0x180003b17  mov     edx, 0A15h; void *
0x180003b1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b22  mov     rcx, [rbp+188h]; this
0x180003b29  mov     edx, 0A0Bh; void *
0x180003b2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b34  mov     rcx, [rbp+188h]; this
0x180003b3b  mov     edx, 0A15h; void *
0x180003b40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
