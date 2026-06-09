# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003734`
- end: `0x180003ad2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800045c0`

## callees

- `0x180001d00`
- `0x180002722`
- `0x180003734`
- `0x180003ad8`
- `0x180003d00`
- `0x180004358`
- `0x180004e28`
- `0x180005294`
- `0x180005c20`
- `0x180005cdc`
- `0x18000608c`
- `0x18000609c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800037cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800037cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800037ac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800037ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000384e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000384e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003947`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003947`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003955`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000376d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000376d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000385f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003939`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000385f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003939`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fd`

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
0x180003734  mov     [rsp-8+arg_10], rbx
0x180003739  push    rbp
0x18000373a  push    rsi
0x18000373b  push    rdi
0x18000373c  push    r14
0x18000373e  push    r15
0x180003740  lea     rbp, [rsp-160h]
0x180003748  sub     rsp, 260h
0x18000374f  mov     rax, cs:__security_cookie
0x180003756  xor     rax, rsp
0x180003759  mov     [rbp+180h+var_30], rax
0x180003760  mov     r15, rdx
0x180003763  mov     qword ptr [rdx], 0
0x18000376a  mov     rbx, rcx
0x18000376d  call    cs:__imp_GetCurrentProcessId
0x180003773  mov     r14d, 78h ; 'x'
0x180003779  mov     [rsp+280h+var_258], rbx
0x18000377e  mov     r9d, eax
0x180003781  mov     [rsp+280h+var_260], r14d; int
0x180003786  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000378d  mov     edx, 104h; unsigned __int64
0x180003792  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003797  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000379c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800037a2  lea     rdx, [rsp+280h+Name]; lpName
0x1800037a7  xor     r8d, r8d; dwFlags
0x1800037aa  xor     ecx, ecx; lpMutexAttributes
0x1800037ac  call    cs:__imp_CreateMutexExW
0x1800037b2  mov     rbx, rax
0x1800037b5  test    rax, rax
0x1800037b8  jnz     short loc_1800037C4
0x1800037ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800037bf  jmp     loc_180003A09
0x1800037c4  xor     r8d, r8d; bAlertable
0x1800037c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800037ca  mov     rcx, rbx; hHandle
0x1800037cd  call    cs:__imp_WaitForSingleObjectEx
0x1800037d3  cmp     eax, 102h
0x1800037d8  jz      short loc_1800037EA
0x1800037da  test    eax, 0FFFFFF7Fh
0x1800037df  jnz     loc_180003A41
0x1800037e5  mov     rdi, rbx
0x1800037e8  jmp     short loc_1800037EC
0x1800037ea  xor     edi, edi
0x1800037ec  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800037f1  mov     [rsp+280h+hObject], 0
0x1800037fa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800037ff  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003804  mov     esi, eax
0x180003806  test    eax, eax
0x180003808  jns     short loc_180003874
0x18000380a  mov     rcx, [rbp+188h]; this
0x180003811  mov     r9d, eax; char *
0x180003814  mov     edx, 66h ; 'f'; void *
0x180003819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000381e  mov     rcx, [rbp+188h]; this
0x180003825  mov     r9d, esi; char *
0x180003828  mov     edx, 6Fh ; 'o'; void *
0x18000382d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003832  mov     rcx, [rbp+188h]; this
0x180003839  mov     r9d, esi; char *
0x18000383c  mov     edx, 12Eh; void *
0x180003841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003846  test    rdi, rdi
0x180003849  jz      short loc_18000385C
0x18000384b  mov     rcx, rdi; hMutex
0x18000384e  call    cs:__imp_ReleaseMutex
0x180003854  test    eax, eax
0x180003856  jz      loc_180003A4E
0x18000385c  mov     rcx, rbx; hObject
0x18000385f  call    cs:__imp_CloseHandle
0x180003865  test    eax, eax
0x180003867  jz      loc_180003A60
0x18000386d  mov     eax, esi
0x18000386f  jmp     loc_180003A09
0x180003874  mov     rax, [rsp+280h+hObject]
0x180003879  lea     rcx, ds:0[rax*4]
0x180003881  test    rcx, rcx
0x180003884  jz      short loc_180003894
0x180003886  mov     [r15], rcx
0x180003889  mov     eax, [rcx]
0x18000388b  inc     eax
0x18000388d  mov     [rcx], eax
0x18000388f  jmp     loc_1800039DF
0x180003894  mov     rdx, r14; dwBytes
0x180003897  mov     qword ptr [r15], 0
0x18000389e  mov     ecx, 8; dwFlags
0x1800038a3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800038a8  mov     rsi, rax
0x1800038ab  test    rax, rax
0x1800038ae  jnz     short loc_1800038CF
0x1800038b0  mov     rcx, [rbp+188h]; this
0x1800038b7  mov     r14d, 8007000Eh
0x1800038bd  mov     r9d, r14d; char *
0x1800038c0  mov     edx, 14Bh; void *
0x1800038c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ca  jmp     loc_18000395B
0x1800038cf  xorps   xmm0, xmm0
0x1800038d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800038d8  test    sil, 3
0x1800038dc  jnz     loc_180003A72
0x1800038e2  mov     r9, rsi
0x1800038e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800038ea  shr     r9, 2; unsigned __int64
0x1800038ee  lea     rcx, [rsp+280h+hObject]; this
0x1800038f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800038f8  mov     r14d, eax
0x1800038fb  test    eax, eax
0x1800038fd  jns     loc_18000399B
0x180003903  mov     rcx, [rbp+188h]; this
0x18000390a  mov     r9d, eax; char *
0x18000390d  mov     edx, 14Eh; void *
0x180003912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003917  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000391c  test    rcx, rcx
0x18000391f  jz      short loc_18000392F
0x180003921  call    cs:__imp_CloseHandle
0x180003927  test    eax, eax
0x180003929  jz      loc_180003A78
0x18000392f  mov     rcx, [rsp+280h+hObject]; hObject
0x180003934  test    rcx, rcx
0x180003937  jz      short loc_180003947
0x180003939  call    cs:__imp_CloseHandle
0x18000393f  test    eax, eax
0x180003941  jz      loc_180003A8A
0x180003947  call    cs:__imp_GetProcessHeap
0x18000394d  mov     r8, rsi; lpMem
0x180003950  xor     edx, edx; dwFlags
0x180003952  mov     rcx, rax; hHeap
0x180003955  call    cs:__imp_HeapFree
0x18000395b  mov     rcx, [rbp+188h]; this
0x180003962  mov     r9d, r14d; char *
0x180003965  mov     edx, 137h; void *
0x18000396a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000396f  test    rdi, rdi
0x180003972  jz      short loc_180003985
0x180003974  mov     rcx, rdi; hMutex
0x180003977  call    cs:__imp_ReleaseMutex
0x18000397d  test    eax, eax
0x18000397f  jz      loc_180003A9C
0x180003985  mov     rcx, rbx; hObject
0x180003988  call    cs:__imp_CloseHandle
0x18000398e  test    eax, eax
0x180003990  jz      loc_180003AAE
0x180003996  mov     eax, r14d
0x180003999  jmp     short loc_180003A09
0x18000399b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800039a0  xor     edx, edx; Val
0x1800039a2  mov     dword ptr [rsi], 1
0x1800039a8  lea     rcx, [rsi+22h]; void *
0x1800039ac  mov     [rsi+8], rbx
0x1800039b0  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800039b5  lea     r8d, [rdx+56h]; Size
0x1800039b9  call    memset_0
0x1800039be  xor     edx, edx; Val
0x1800039c0  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800039c6  lea     rcx, [rsi+28h]; void *
0x1800039ca  mov     dword ptr [rsi+24h], 1
0x1800039d1  lea     r8d, [rdx+50h]; Size
0x1800039d5  call    memset_0
0x1800039da  xor     ebx, ebx
0x1800039dc  mov     [r15], rsi
0x1800039df  test    rdi, rdi
0x1800039e2  jz      short loc_1800039F5
0x1800039e4  mov     rcx, rdi; hMutex
0x1800039e7  call    cs:__imp_ReleaseMutex
0x1800039ed  test    eax, eax
0x1800039ef  jz      loc_180003AC0
0x1800039f5  test    rbx, rbx
0x1800039f8  jz      short loc_180003A07
0x1800039fa  mov     rcx, rbx; hObject
0x1800039fd  call    cs:__imp_CloseHandle
0x180003a03  test    eax, eax
0x180003a05  jz      short loc_180003A2F
0x180003a07  xor     eax, eax
0x180003a09  mov     rcx, [rbp+180h+var_30]
0x180003a10  xor     rcx, rsp; StackCookie
0x180003a13  call    __security_check_cookie
0x180003a18  mov     rbx, [rsp+280h+arg_10]
0x180003a20  add     rsp, 260h
0x180003a27  pop     r15
0x180003a29  pop     r14
0x180003a2b  pop     rdi
0x180003a2c  pop     rsi
0x180003a2d  pop     rbp
0x180003a2e  retn
0x180003a2f  mov     rcx, [rbp+188h]; this
0x180003a36  mov     edx, 0A0Bh; void *
0x180003a3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a41  mov     rcx, [rbp+188h]; this
0x180003a48  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003a4e  mov     rcx, [rbp+188h]; this
0x180003a55  mov     edx, 0A15h; void *
0x180003a5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a60  mov     rcx, [rbp+188h]; this
0x180003a67  mov     edx, 0A0Bh; void *
0x180003a6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a72  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a78  mov     rcx, [rbp+188h]; this
0x180003a7f  mov     edx, 0A0Bh; void *
0x180003a84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a8a  mov     rcx, [rbp+188h]; this
0x180003a91  mov     edx, 0A0Bh; void *
0x180003a96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a9c  mov     rcx, [rbp+188h]; this
0x180003aa3  mov     edx, 0A15h; void *
0x180003aa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003aae  mov     rcx, [rbp+188h]; this
0x180003ab5  mov     edx, 0A0Bh; void *
0x180003aba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ac0  mov     rcx, [rbp+188h]; this
0x180003ac7  mov     edx, 0A15h; void *
0x180003acc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
