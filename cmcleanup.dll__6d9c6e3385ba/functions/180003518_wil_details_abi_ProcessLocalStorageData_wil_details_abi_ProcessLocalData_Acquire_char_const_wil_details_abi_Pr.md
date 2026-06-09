# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003518`
- end: `0x1800038e0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800048f4`

## callees

- `0x180001510`
- `0x1800020c4`
- `0x180003518`
- `0x180003964`
- `0x180003ff0`
- `0x180004638`
- `0x18000529c`
- `0x1800068d4`
- `0x180007370`
- `0x18000742c`
- `0x1800078b4`
- `0x1800078c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003590`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003590`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800035b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800035b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003647`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003785`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800037f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003647`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003785`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800037f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000375c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000375c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000374e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000374e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000380b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000380b`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180003518  mov     [rsp-8+arg_10], rbx
0x18000351d  push    rbp
0x18000351e  push    rsi
0x18000351f  push    rdi
0x180003520  push    r14
0x180003522  push    r15
0x180003524  lea     rbp, [rsp-160h]
0x18000352c  sub     rsp, 260h
0x180003533  mov     rax, cs:__security_cookie
0x18000353a  xor     rax, rsp
0x18000353d  mov     [rbp+180h+var_30], rax
0x180003544  mov     r15, rdx
0x180003547  mov     qword ptr [rdx], 0
0x18000354e  mov     rbx, rcx
0x180003551  call    cs:__imp_GetCurrentProcessId
0x180003557  mov     r14d, 78h ; 'x'
0x18000355d  mov     [rsp+280h+var_258], rbx
0x180003562  mov     r9d, eax
0x180003565  mov     [rsp+280h+var_260], r14d; int
0x18000356a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003571  mov     edx, 104h; unsigned __int64
0x180003576  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000357b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003580  mov     r9d, 1F0001h; dwDesiredAccess
0x180003586  lea     rdx, [rsp+280h+Name]; lpName
0x18000358b  xor     r8d, r8d; dwFlags
0x18000358e  xor     ecx, ecx; lpMutexAttributes
0x180003590  call    cs:__imp_CreateMutexExW
0x180003596  mov     rbx, rax
0x180003599  test    rax, rax
0x18000359c  jnz     short loc_1800035A8
0x18000359e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035a3  jmp     loc_180003817
0x1800035a8  xor     r8d, r8d; bAlertable
0x1800035ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800035ae  mov     rcx, rbx; hHandle
0x1800035b1  call    cs:__imp_WaitForSingleObjectEx
0x1800035b7  cmp     eax, 102h
0x1800035bc  jz      short loc_1800035CE
0x1800035be  test    eax, 0FFFFFF7Fh
0x1800035c3  jnz     loc_18000384F
0x1800035c9  mov     rdi, rbx
0x1800035cc  jmp     short loc_1800035D0
0x1800035ce  xor     edi, edi
0x1800035d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800035d5  mov     [rsp+280h+hObject], 0
0x1800035de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800035e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800035e8  mov     esi, eax
0x1800035ea  test    eax, eax
0x1800035ec  jns     short loc_18000366D
0x1800035ee  mov     rcx, [rbp+188h]; this
0x1800035f5  lea     r8, aWil; "wil"
0x1800035fc  mov     r9d, eax; char *
0x1800035ff  mov     edx, 66h ; 'f'; void *
0x180003604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003609  mov     rcx, [rbp+188h]; this
0x180003610  lea     r8, aWil; "wil"
0x180003617  mov     r9d, esi; char *
0x18000361a  mov     edx, 6Fh ; 'o'; void *
0x18000361f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003624  mov     rcx, [rbp+188h]; this
0x18000362b  lea     r8, aWil; "wil"
0x180003632  mov     r9d, esi; char *
0x180003635  mov     edx, 12Eh; void *
0x18000363a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000363f  test    rdi, rdi
0x180003642  jz      short loc_180003655
0x180003644  mov     rcx, rdi; hMutex
0x180003647  call    cs:__imp_ReleaseMutex
0x18000364d  test    eax, eax
0x18000364f  jz      loc_18000385C
0x180003655  mov     rcx, rbx; hObject
0x180003658  call    cs:__imp_CloseHandle
0x18000365e  test    eax, eax
0x180003660  jz      loc_18000386E
0x180003666  mov     eax, esi
0x180003668  jmp     loc_180003817
0x18000366d  mov     rax, [rsp+280h+hObject]
0x180003672  lea     rcx, ds:0[rax*4]
0x18000367a  test    rcx, rcx
0x18000367d  jz      short loc_18000368D
0x18000367f  mov     [r15], rcx
0x180003682  mov     eax, [rcx]
0x180003684  inc     eax
0x180003686  mov     [rcx], eax
0x180003688  jmp     loc_1800037ED
0x18000368d  mov     rdx, r14; dwBytes
0x180003690  mov     qword ptr [r15], 0
0x180003697  mov     ecx, 8; dwFlags
0x18000369c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800036a1  mov     rsi, rax
0x1800036a4  test    rax, rax
0x1800036a7  jnz     short loc_1800036CF
0x1800036a9  mov     rcx, [rbp+188h]; this
0x1800036b0  lea     r8, aWil; "wil"
0x1800036b7  mov     r14d, 8007000Eh
0x1800036bd  mov     edx, 14Bh; void *
0x1800036c2  mov     r9d, r14d; char *
0x1800036c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036ca  jmp     loc_180003762
0x1800036cf  xorps   xmm0, xmm0
0x1800036d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800036d8  test    sil, 3
0x1800036dc  jnz     loc_180003880
0x1800036e2  mov     r9, rsi
0x1800036e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800036ea  shr     r9, 2; unsigned __int64
0x1800036ee  lea     rcx, [rsp+280h+hObject]; this
0x1800036f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800036f8  mov     r14d, eax
0x1800036fb  test    eax, eax
0x1800036fd  jns     loc_1800037A9
0x180003703  mov     rcx, [rbp+188h]; this
0x18000370a  lea     r8, aWil; "wil"
0x180003711  mov     r9d, eax; char *
0x180003714  mov     edx, 14Eh; void *
0x180003719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000371e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003723  test    rcx, rcx
0x180003726  jz      short loc_180003736
0x180003728  call    cs:__imp_CloseHandle
0x18000372e  test    eax, eax
0x180003730  jz      loc_180003886
0x180003736  mov     rcx, [rsp+280h+hObject]; hObject
0x18000373b  test    rcx, rcx
0x18000373e  jz      short loc_18000374E
0x180003740  call    cs:__imp_CloseHandle
0x180003746  test    eax, eax
0x180003748  jz      loc_180003898
0x18000374e  call    cs:__imp_GetProcessHeap
0x180003754  mov     r8, rsi; lpMem
0x180003757  xor     edx, edx; dwFlags
0x180003759  mov     rcx, rax; hHeap
0x18000375c  call    cs:__imp_HeapFree
0x180003762  mov     rcx, [rbp+188h]; this
0x180003769  lea     r8, aWil; "wil"
0x180003770  mov     r9d, r14d; char *
0x180003773  mov     edx, 137h; void *
0x180003778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000377d  test    rdi, rdi
0x180003780  jz      short loc_180003793
0x180003782  mov     rcx, rdi; hMutex
0x180003785  call    cs:__imp_ReleaseMutex
0x18000378b  test    eax, eax
0x18000378d  jz      loc_1800038AA
0x180003793  mov     rcx, rbx; hObject
0x180003796  call    cs:__imp_CloseHandle
0x18000379c  test    eax, eax
0x18000379e  jz      loc_1800038BC
0x1800037a4  mov     eax, r14d
0x1800037a7  jmp     short loc_180003817
0x1800037a9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800037ae  xor     edx, edx; Val
0x1800037b0  mov     dword ptr [rsi], 1
0x1800037b6  lea     rcx, [rsi+22h]; void *
0x1800037ba  mov     [rsi+8], rbx
0x1800037be  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800037c3  lea     r8d, [rdx+56h]; Size
0x1800037c7  call    memset_0
0x1800037cc  xor     edx, edx; Val
0x1800037ce  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800037d4  lea     rcx, [rsi+28h]; void *
0x1800037d8  mov     dword ptr [rsi+24h], 1
0x1800037df  lea     r8d, [rdx+50h]; Size
0x1800037e3  call    memset_0
0x1800037e8  xor     ebx, ebx
0x1800037ea  mov     [r15], rsi
0x1800037ed  test    rdi, rdi
0x1800037f0  jz      short loc_180003803
0x1800037f2  mov     rcx, rdi; hMutex
0x1800037f5  call    cs:__imp_ReleaseMutex
0x1800037fb  test    eax, eax
0x1800037fd  jz      loc_1800038CE
0x180003803  test    rbx, rbx
0x180003806  jz      short loc_180003815
0x180003808  mov     rcx, rbx; hObject
0x18000380b  call    cs:__imp_CloseHandle
0x180003811  test    eax, eax
0x180003813  jz      short loc_18000383D
0x180003815  xor     eax, eax
0x180003817  mov     rcx, [rbp+180h+var_30]
0x18000381e  xor     rcx, rsp; StackCookie
0x180003821  call    __security_check_cookie
0x180003826  mov     rbx, [rsp+280h+arg_10]
0x18000382e  add     rsp, 260h
0x180003835  pop     r15
0x180003837  pop     r14
0x180003839  pop     rdi
0x18000383a  pop     rsi
0x18000383b  pop     rbp
0x18000383c  retn
0x18000383d  mov     rcx, [rbp+188h]; this
0x180003844  mov     edx, 0A0Bh; void *
0x180003849  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000384f  mov     rcx, [rbp+188h]; this
0x180003856  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000385c  mov     rcx, [rbp+188h]; this
0x180003863  mov     edx, 0A15h; void *
0x180003868  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000386e  mov     rcx, [rbp+188h]; this
0x180003875  mov     edx, 0A0Bh; void *
0x18000387a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003880  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003886  mov     rcx, [rbp+188h]; this
0x18000388d  mov     edx, 0A0Bh; void *
0x180003892  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003898  mov     rcx, [rbp+188h]; this
0x18000389f  mov     edx, 0A0Bh; void *
0x1800038a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800038aa  mov     rcx, [rbp+188h]; this
0x1800038b1  mov     edx, 0A15h; void *
0x1800038b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800038bc  mov     rcx, [rbp+188h]; this
0x1800038c3  mov     edx, 0A0Bh; void *
0x1800038c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800038ce  mov     rcx, [rbp+188h]; this
0x1800038d5  mov     edx, 0A15h; void *
0x1800038da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
