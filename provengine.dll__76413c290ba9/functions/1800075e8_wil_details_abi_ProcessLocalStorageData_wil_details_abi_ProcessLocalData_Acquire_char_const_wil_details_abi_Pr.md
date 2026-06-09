# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800075e8`
- end: `0x1800079bc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800086e4`

## callees

- `0x180005598`
- `0x1800075e8`
- `0x1800079c4`
- `0x1800083c4`
- `0x1800085a8`
- `0x180009238`
- `0x1800098dc`
- `0x18000a24c`
- `0x18000ad08`
- `0x18000ad18`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000781e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000781e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000782c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000782c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007621`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007621`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007717`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007855`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800078c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007717`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007855`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800078c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007681`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007681`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007660`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078db`

## string_xrefs

- `0x180007926`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x1800075e8  mov     [rsp-8+arg_10], rbx
0x1800075ed  push    rbp
0x1800075ee  push    rsi
0x1800075ef  push    rdi
0x1800075f0  push    r14
0x1800075f2  push    r15
0x1800075f4  lea     rbp, [rsp-160h]
0x1800075fc  sub     rsp, 260h
0x180007603  mov     rax, cs:__security_cookie
0x18000760a  xor     rax, rsp
0x18000760d  mov     [rbp+180h+var_30], rax
0x180007614  mov     r15, rdx
0x180007617  mov     qword ptr [rdx], 0
0x18000761e  mov     rbx, rcx
0x180007621  call    cs:__imp_GetCurrentProcessId
0x180007627  mov     r14d, 78h ; 'x'
0x18000762d  mov     [rsp+280h+var_258], rbx
0x180007632  mov     r9d, eax
0x180007635  mov     [rsp+280h+var_260], r14d; int
0x18000763a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007641  mov     edx, 104h; unsigned __int64
0x180007646  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000764b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007650  mov     r9d, 1F0001h; dwDesiredAccess
0x180007656  lea     rdx, [rsp+280h+Name]; lpName
0x18000765b  xor     r8d, r8d; dwFlags
0x18000765e  xor     ecx, ecx; lpMutexAttributes
0x180007660  call    cs:__imp_CreateMutexExW
0x180007666  mov     rbx, rax
0x180007669  test    rax, rax
0x18000766c  jnz     short loc_180007678
0x18000766e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007673  jmp     loc_1800078E7
0x180007678  xor     r8d, r8d; bAlertable
0x18000767b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000767e  mov     rcx, rbx; hHandle
0x180007681  call    cs:__imp_WaitForSingleObjectEx
0x180007687  cmp     eax, 102h
0x18000768c  jz      short loc_18000769E
0x18000768e  test    eax, 0FFFFFF7Fh
0x180007693  jnz     loc_18000791F
0x180007699  mov     rdi, rbx
0x18000769c  jmp     short loc_1800076A0
0x18000769e  xor     edi, edi
0x1800076a0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800076a5  mov     [rsp+280h+hObject], 0
0x1800076ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800076b3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800076b8  mov     esi, eax
0x1800076ba  test    eax, eax
0x1800076bc  jns     short loc_18000773D
0x1800076be  mov     rcx, [rbp+188h]; this
0x1800076c5  lea     r8, aWil; "wil"
0x1800076cc  mov     r9d, eax; char *
0x1800076cf  mov     edx, 66h ; 'f'; void *
0x1800076d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076d9  mov     rcx, [rbp+188h]; this
0x1800076e0  lea     r8, aWil; "wil"
0x1800076e7  mov     r9d, esi; char *
0x1800076ea  mov     edx, 6Fh ; 'o'; void *
0x1800076ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076f4  mov     rcx, [rbp+188h]; this
0x1800076fb  lea     r8, aWil; "wil"
0x180007702  mov     r9d, esi; char *
0x180007705  mov     edx, 12Eh; void *
0x18000770a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000770f  test    rdi, rdi
0x180007712  jz      short loc_180007725
0x180007714  mov     rcx, rdi; hMutex
0x180007717  call    cs:__imp_ReleaseMutex
0x18000771d  test    eax, eax
0x18000771f  jz      loc_180007938
0x180007725  mov     rcx, rbx; hObject
0x180007728  call    cs:__imp_CloseHandle
0x18000772e  test    eax, eax
0x180007730  jz      loc_18000794A
0x180007736  mov     eax, esi
0x180007738  jmp     loc_1800078E7
0x18000773d  mov     rax, [rsp+280h+hObject]
0x180007742  lea     rcx, ds:0[rax*4]
0x18000774a  test    rcx, rcx
0x18000774d  jz      short loc_18000775D
0x18000774f  mov     [r15], rcx
0x180007752  mov     eax, [rcx]
0x180007754  inc     eax
0x180007756  mov     [rcx], eax
0x180007758  jmp     loc_1800078BD
0x18000775d  mov     rdx, r14; dwBytes
0x180007760  mov     qword ptr [r15], 0
0x180007767  mov     ecx, 8; dwFlags
0x18000776c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007771  mov     rsi, rax
0x180007774  test    rax, rax
0x180007777  jnz     short loc_18000779F
0x180007779  mov     rcx, [rbp+188h]; this
0x180007780  lea     r8, aWil; "wil"
0x180007787  mov     r14d, 8007000Eh
0x18000778d  mov     edx, 14Bh; void *
0x180007792  mov     r9d, r14d; char *
0x180007795  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000779a  jmp     loc_180007832
0x18000779f  xorps   xmm0, xmm0
0x1800077a2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800077a8  test    sil, 3
0x1800077ac  jnz     loc_18000795C
0x1800077b2  mov     r9, rsi
0x1800077b5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800077ba  shr     r9, 2; unsigned __int64
0x1800077be  lea     rcx, [rsp+280h+hObject]; this
0x1800077c3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800077c8  mov     r14d, eax
0x1800077cb  test    eax, eax
0x1800077cd  jns     loc_180007879
0x1800077d3  mov     rcx, [rbp+188h]; this
0x1800077da  lea     r8, aWil; "wil"
0x1800077e1  mov     r9d, eax; char *
0x1800077e4  mov     edx, 14Eh; void *
0x1800077e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077ee  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800077f3  test    rcx, rcx
0x1800077f6  jz      short loc_180007806
0x1800077f8  call    cs:__imp_CloseHandle
0x1800077fe  test    eax, eax
0x180007800  jz      loc_180007962
0x180007806  mov     rcx, [rsp+280h+hObject]; hObject
0x18000780b  test    rcx, rcx
0x18000780e  jz      short loc_18000781E
0x180007810  call    cs:__imp_CloseHandle
0x180007816  test    eax, eax
0x180007818  jz      loc_180007974
0x18000781e  call    cs:__imp_GetProcessHeap
0x180007824  mov     r8, rsi; lpMem
0x180007827  xor     edx, edx; dwFlags
0x180007829  mov     rcx, rax; hHeap
0x18000782c  call    cs:__imp_HeapFree
0x180007832  mov     rcx, [rbp+188h]; this
0x180007839  lea     r8, aWil; "wil"
0x180007840  mov     r9d, r14d; char *
0x180007843  mov     edx, 137h; void *
0x180007848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000784d  test    rdi, rdi
0x180007850  jz      short loc_180007863
0x180007852  mov     rcx, rdi; hMutex
0x180007855  call    cs:__imp_ReleaseMutex
0x18000785b  test    eax, eax
0x18000785d  jz      loc_180007986
0x180007863  mov     rcx, rbx; hObject
0x180007866  call    cs:__imp_CloseHandle
0x18000786c  test    eax, eax
0x18000786e  jz      loc_180007998
0x180007874  mov     eax, r14d
0x180007877  jmp     short loc_1800078E7
0x180007879  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000787e  xor     edx, edx; Val
0x180007880  mov     dword ptr [rsi], 1
0x180007886  lea     rcx, [rsi+22h]; void *
0x18000788a  mov     [rsi+8], rbx
0x18000788e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180007893  lea     r8d, [rdx+56h]; Size
0x180007897  call    memset_0
0x18000789c  xor     edx, edx; Val
0x18000789e  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800078a4  lea     rcx, [rsi+28h]; void *
0x1800078a8  mov     dword ptr [rsi+24h], 1
0x1800078af  lea     r8d, [rdx+50h]; Size
0x1800078b3  call    memset_0
0x1800078b8  xor     ebx, ebx
0x1800078ba  mov     [r15], rsi
0x1800078bd  test    rdi, rdi
0x1800078c0  jz      short loc_1800078D3
0x1800078c2  mov     rcx, rdi; hMutex
0x1800078c5  call    cs:__imp_ReleaseMutex
0x1800078cb  test    eax, eax
0x1800078cd  jz      loc_1800079AA
0x1800078d3  test    rbx, rbx
0x1800078d6  jz      short loc_1800078E5
0x1800078d8  mov     rcx, rbx; hObject
0x1800078db  call    cs:__imp_CloseHandle
0x1800078e1  test    eax, eax
0x1800078e3  jz      short loc_18000790D
0x1800078e5  xor     eax, eax
0x1800078e7  mov     rcx, [rbp+180h+var_30]
0x1800078ee  xor     rcx, rsp; StackCookie
0x1800078f1  call    __security_check_cookie
0x1800078f6  mov     rbx, [rsp+280h+arg_10]
0x1800078fe  add     rsp, 260h
0x180007905  pop     r15
0x180007907  pop     r14
0x180007909  pop     rdi
0x18000790a  pop     rsi
0x18000790b  pop     rbp
0x18000790c  retn
0x18000790d  mov     rcx, [rbp+188h]; this
0x180007914  mov     edx, 0A0Bh; void *
0x180007919  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000791f  mov     rcx, [rbp+188h]; this
0x180007926  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000792d  mov     edx, 0E01h; void *
0x180007932  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007938  mov     rcx, [rbp+188h]; this
0x18000793f  mov     edx, 0A15h; void *
0x180007944  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000794a  mov     rcx, [rbp+188h]; this
0x180007951  mov     edx, 0A0Bh; void *
0x180007956  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000795c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007962  mov     rcx, [rbp+188h]; this
0x180007969  mov     edx, 0A0Bh; void *
0x18000796e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007974  mov     rcx, [rbp+188h]; this
0x18000797b  mov     edx, 0A0Bh; void *
0x180007980  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007986  mov     rcx, [rbp+188h]; this
0x18000798d  mov     edx, 0A15h; void *
0x180007992  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007998  mov     rcx, [rbp+188h]; this
0x18000799f  mov     edx, 0A0Bh; void *
0x1800079a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800079aa  mov     rcx, [rbp+188h]; this
0x1800079b1  mov     edx, 0A15h; void *
0x1800079b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
