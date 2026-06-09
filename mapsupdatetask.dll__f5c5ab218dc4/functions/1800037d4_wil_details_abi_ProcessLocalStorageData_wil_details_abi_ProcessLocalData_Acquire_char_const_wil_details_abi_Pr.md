# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800037d4`
- end: `0x180003b77`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `931`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004ac0`

## callees

- `0x180001be0`
- `0x180002612`
- `0x1800037d4`
- `0x180003bb4`
- `0x18000420c`
- `0x180004858`
- `0x18000550c`
- `0x180005cd4`
- `0x180006b40`
- `0x180006bfc`
- `0x1800075d4`
- `0x1800075e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a87`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000384c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000384c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000386d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000386d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000380d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000380d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9d`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x1800037d4  mov     [rsp-8+arg_10], rbx
0x1800037d9  push    rbp
0x1800037da  push    rsi
0x1800037db  push    rdi
0x1800037dc  push    r14
0x1800037de  push    r15
0x1800037e0  lea     rbp, [rsp-160h]
0x1800037e8  sub     rsp, 260h
0x1800037ef  mov     rax, cs:__security_cookie
0x1800037f6  xor     rax, rsp
0x1800037f9  mov     [rbp+180h+var_30], rax
0x180003800  mov     r15, rdx
0x180003803  mov     qword ptr [rdx], 0
0x18000380a  mov     rbx, rcx
0x18000380d  call    cs:__imp_GetCurrentProcessId
0x180003813  mov     r14d, 78h ; 'x'
0x180003819  mov     [rsp+280h+var_258], rbx
0x18000381e  mov     r9d, eax
0x180003821  mov     [rsp+280h+var_260], r14d; int
0x180003826  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000382d  mov     edx, 104h; unsigned __int64
0x180003832  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003837  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000383c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003842  lea     rdx, [rsp+280h+Name]; lpName
0x180003847  xor     r8d, r8d; dwFlags
0x18000384a  xor     ecx, ecx; lpMutexAttributes
0x18000384c  call    cs:__imp_CreateMutexExW
0x180003852  mov     rbx, rax
0x180003855  test    rax, rax
0x180003858  jnz     short loc_180003864
0x18000385a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000385f  jmp     loc_180003AA9
0x180003864  xor     r8d, r8d; bAlertable
0x180003867  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000386a  mov     rcx, rbx; hHandle
0x18000386d  call    cs:__imp_WaitForSingleObjectEx
0x180003873  cmp     eax, 102h
0x180003878  jz      short loc_18000388A
0x18000387a  test    eax, 0FFFFFF7Fh
0x18000387f  jnz     loc_180003AE1
0x180003885  mov     rdi, rbx
0x180003888  jmp     short loc_18000388C
0x18000388a  xor     edi, edi
0x18000388c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003891  mov     [rsp+280h+hObject], 0
0x18000389a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000389f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800038a4  mov     esi, eax
0x1800038a6  test    eax, eax
0x1800038a8  jns     short loc_180003914
0x1800038aa  mov     rcx, [rbp+188h]; this
0x1800038b1  mov     r9d, eax; char *
0x1800038b4  mov     edx, 66h ; 'f'; void *
0x1800038b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038be  mov     rcx, [rbp+188h]; this
0x1800038c5  mov     r9d, esi; char *
0x1800038c8  mov     edx, 6Fh ; 'o'; void *
0x1800038cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038d2  mov     rcx, [rbp+188h]; this
0x1800038d9  mov     r9d, esi; char *
0x1800038dc  mov     edx, 12Eh; void *
0x1800038e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038e6  test    rdi, rdi
0x1800038e9  jz      short loc_1800038FC
0x1800038eb  mov     rcx, rdi; hMutex
0x1800038ee  call    cs:__imp_ReleaseMutex
0x1800038f4  test    eax, eax
0x1800038f6  jz      loc_180003AF3
0x1800038fc  mov     rcx, rbx; hObject
0x1800038ff  call    cs:__imp_CloseHandle
0x180003905  test    eax, eax
0x180003907  jz      loc_180003B05
0x18000390d  mov     eax, esi
0x18000390f  jmp     loc_180003AA9
0x180003914  mov     rax, [rsp+280h+hObject]
0x180003919  lea     rcx, ds:0[rax*4]
0x180003921  test    rcx, rcx
0x180003924  jz      short loc_180003934
0x180003926  mov     [r15], rcx
0x180003929  mov     eax, [rcx]
0x18000392b  inc     eax
0x18000392d  mov     [rcx], eax
0x18000392f  jmp     loc_180003A7F
0x180003934  mov     rdx, r14; dwBytes
0x180003937  mov     qword ptr [r15], 0
0x18000393e  mov     ecx, 8; dwFlags
0x180003943  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003948  mov     rsi, rax
0x18000394b  test    rax, rax
0x18000394e  jnz     short loc_18000396F
0x180003950  mov     rcx, [rbp+188h]; this
0x180003957  mov     r14d, 8007000Eh
0x18000395d  mov     r9d, r14d; char *
0x180003960  mov     edx, 14Bh; void *
0x180003965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000396a  jmp     loc_1800039FB
0x18000396f  xorps   xmm0, xmm0
0x180003972  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003978  test    sil, 3
0x18000397c  jnz     loc_180003B17
0x180003982  mov     r9, rsi
0x180003985  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000398a  shr     r9, 2; unsigned __int64
0x18000398e  lea     rcx, [rsp+280h+hObject]; this
0x180003993  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003998  mov     r14d, eax
0x18000399b  test    eax, eax
0x18000399d  jns     loc_180003A3B
0x1800039a3  mov     rcx, [rbp+188h]; this
0x1800039aa  mov     r9d, eax; char *
0x1800039ad  mov     edx, 14Eh; void *
0x1800039b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039b7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800039bc  test    rcx, rcx
0x1800039bf  jz      short loc_1800039CF
0x1800039c1  call    cs:__imp_CloseHandle
0x1800039c7  test    eax, eax
0x1800039c9  jz      loc_180003B1D
0x1800039cf  mov     rcx, [rsp+280h+hObject]; hObject
0x1800039d4  test    rcx, rcx
0x1800039d7  jz      short loc_1800039E7
0x1800039d9  call    cs:__imp_CloseHandle
0x1800039df  test    eax, eax
0x1800039e1  jz      loc_180003B2F
0x1800039e7  call    cs:__imp_GetProcessHeap
0x1800039ed  mov     r8, rsi; lpMem
0x1800039f0  xor     edx, edx; dwFlags
0x1800039f2  mov     rcx, rax; hHeap
0x1800039f5  call    cs:__imp_HeapFree
0x1800039fb  mov     rcx, [rbp+188h]; this
0x180003a02  mov     r9d, r14d; char *
0x180003a05  mov     edx, 137h; void *
0x180003a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a0f  test    rdi, rdi
0x180003a12  jz      short loc_180003A25
0x180003a14  mov     rcx, rdi; hMutex
0x180003a17  call    cs:__imp_ReleaseMutex
0x180003a1d  test    eax, eax
0x180003a1f  jz      loc_180003B41
0x180003a25  mov     rcx, rbx; hObject
0x180003a28  call    cs:__imp_CloseHandle
0x180003a2e  test    eax, eax
0x180003a30  jz      loc_180003B53
0x180003a36  mov     eax, r14d
0x180003a39  jmp     short loc_180003AA9
0x180003a3b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003a40  xor     edx, edx; Val
0x180003a42  mov     dword ptr [rsi], 1
0x180003a48  lea     rcx, [rsi+22h]; void *
0x180003a4c  mov     [rsi+8], rbx
0x180003a50  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003a55  lea     r8d, [rdx+56h]; Size
0x180003a59  call    memset_0
0x180003a5e  xor     edx, edx; Val
0x180003a60  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003a66  lea     rcx, [rsi+28h]; void *
0x180003a6a  mov     dword ptr [rsi+24h], 1
0x180003a71  lea     r8d, [rdx+50h]; Size
0x180003a75  call    memset_0
0x180003a7a  xor     ebx, ebx
0x180003a7c  mov     [r15], rsi
0x180003a7f  test    rdi, rdi
0x180003a82  jz      short loc_180003A95
0x180003a84  mov     rcx, rdi; hMutex
0x180003a87  call    cs:__imp_ReleaseMutex
0x180003a8d  test    eax, eax
0x180003a8f  jz      loc_180003B65
0x180003a95  test    rbx, rbx
0x180003a98  jz      short loc_180003AA7
0x180003a9a  mov     rcx, rbx; hObject
0x180003a9d  call    cs:__imp_CloseHandle
0x180003aa3  test    eax, eax
0x180003aa5  jz      short loc_180003ACF
0x180003aa7  xor     eax, eax
0x180003aa9  mov     rcx, [rbp+180h+var_30]
0x180003ab0  xor     rcx, rsp; StackCookie
0x180003ab3  call    __security_check_cookie
0x180003ab8  mov     rbx, [rsp+280h+arg_10]
0x180003ac0  add     rsp, 260h
0x180003ac7  pop     r15
0x180003ac9  pop     r14
0x180003acb  pop     rdi
0x180003acc  pop     rsi
0x180003acd  pop     rbp
0x180003ace  retn
0x180003acf  mov     rcx, [rbp+188h]; this
0x180003ad6  mov     edx, 0A0Bh; void *
0x180003adb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ae1  mov     rcx, [rbp+188h]; this
0x180003ae8  mov     edx, 0E01h; void *
0x180003aed  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003af3  mov     rcx, [rbp+188h]; this
0x180003afa  mov     edx, 0A15h; void *
0x180003aff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b05  mov     rcx, [rbp+188h]; this
0x180003b0c  mov     edx, 0A0Bh; void *
0x180003b11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b17  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b1d  mov     rcx, [rbp+188h]; this
0x180003b24  mov     edx, 0A0Bh; void *
0x180003b29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b2f  mov     rcx, [rbp+188h]; this
0x180003b36  mov     edx, 0A0Bh; void *
0x180003b3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b41  mov     rcx, [rbp+188h]; this
0x180003b48  mov     edx, 0A15h; void *
0x180003b4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b53  mov     rcx, [rbp+188h]; this
0x180003b5a  mov     edx, 0A0Bh; void *
0x180003b5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b65  mov     rcx, [rbp+188h]; this
0x180003b6c  mov     edx, 0A15h; void *
0x180003b71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
