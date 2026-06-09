# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011efc`
- end: `0x1800122f9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180013544`

## callees

- `0x180005598`
- `0x1800079c4`
- `0x1800083c4`
- `0x1800085a8`
- `0x180009238`
- `0x1800098dc`
- `0x18000a24c`
- `0x18000ad08`
- `0x18000ad18`
- `0x18000fbfc`
- `0x180011efc`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001212f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001212f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001213d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001213d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011f35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001202a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012166`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012202`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001202a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012166`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012202`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011f94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011f94`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011f73`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011f73`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800121cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800121cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001203b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001203b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012218`

## string_xrefs

- `0x180012275`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v23; // r14
  int v24; // eax
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  __int128 v34; // xmm0
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
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
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180011efc  mov     [rsp-8+arg_10], rbx
0x180011f01  push    rbp
0x180011f02  push    rsi
0x180011f03  push    rdi
0x180011f04  push    r14
0x180011f06  push    r15
0x180011f08  lea     rbp, [rsp-160h]
0x180011f10  sub     rsp, 260h
0x180011f17  mov     rax, cs:__security_cookie
0x180011f1e  xor     rax, rsp
0x180011f21  mov     [rbp+180h+var_30], rax
0x180011f28  mov     r15, rdx
0x180011f2b  mov     qword ptr [rdx], 0
0x180011f32  mov     rbx, rcx
0x180011f35  call    cs:__imp_GetCurrentProcessId
0x180011f3b  mov     r14d, 130h
0x180011f41  mov     [rsp+280h+var_258], rbx
0x180011f46  mov     r9d, eax
0x180011f49  mov     [rsp+280h+var_260], r14d; int
0x180011f4e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011f55  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011f5a  lea     edx, [r14-2Ch]; unsigned __int64
0x180011f5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011f63  mov     r9d, 1F0001h; dwDesiredAccess
0x180011f69  lea     rdx, [rsp+280h+Name]; lpName
0x180011f6e  xor     r8d, r8d; dwFlags
0x180011f71  xor     ecx, ecx; lpMutexAttributes
0x180011f73  call    cs:__imp_CreateMutexExW
0x180011f79  mov     rbx, rax
0x180011f7c  test    rax, rax
0x180011f7f  jnz     short loc_180011F8B
0x180011f81  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011f86  jmp     loc_180012224
0x180011f8b  xor     r8d, r8d; bAlertable
0x180011f8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011f91  mov     rcx, rbx; hHandle
0x180011f94  call    cs:__imp_WaitForSingleObjectEx
0x180011f9a  cmp     eax, 102h
0x180011f9f  jz      short loc_180011FB1
0x180011fa1  test    eax, 0FFFFFF7Fh
0x180011fa6  jnz     loc_18001226E
0x180011fac  mov     rdi, rbx
0x180011faf  jmp     short loc_180011FB3
0x180011fb1  xor     edi, edi
0x180011fb3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180011fb8  mov     [rsp+280h+hObject], 0
0x180011fc1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011fc6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011fcb  mov     esi, eax
0x180011fcd  test    eax, eax
0x180011fcf  jns     short loc_180012050
0x180011fd1  mov     rcx, [rbp+188h]; this
0x180011fd8  lea     r8, aWil; "wil"
0x180011fdf  mov     r9d, eax; char *
0x180011fe2  mov     edx, 66h ; 'f'; void *
0x180011fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011fec  mov     rcx, [rbp+188h]; this
0x180011ff3  lea     r8, aWil; "wil"
0x180011ffa  mov     r9d, esi; char *
0x180011ffd  mov     edx, 6Fh ; 'o'; void *
0x180012002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012007  mov     rcx, [rbp+188h]; this
0x18001200e  lea     r8, aWil; "wil"
0x180012015  mov     r9d, esi; char *
0x180012018  mov     edx, 12Eh; void *
0x18001201d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012022  test    rdi, rdi
0x180012025  jz      short loc_180012038
0x180012027  mov     rcx, rdi; hMutex
0x18001202a  call    cs:__imp_ReleaseMutex
0x180012030  test    eax, eax
0x180012032  jz      loc_180012287
0x180012038  mov     rcx, rbx; hObject
0x18001203b  call    cs:__imp_CloseHandle
0x180012041  test    eax, eax
0x180012043  jz      loc_180012299
0x180012049  mov     eax, esi
0x18001204b  jmp     loc_180012224
0x180012050  mov     rax, [rsp+280h+hObject]
0x180012055  lea     rcx, ds:0[rax*4]
0x18001205d  test    rcx, rcx
0x180012060  jz      short loc_180012070
0x180012062  mov     [r15], rcx
0x180012065  mov     eax, [rcx]
0x180012067  inc     eax
0x180012069  mov     [rcx], eax
0x18001206b  jmp     loc_1800121FA
0x180012070  mov     rdx, r14; dwBytes
0x180012073  mov     qword ptr [r15], 0
0x18001207a  mov     ecx, 8; dwFlags
0x18001207f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012084  mov     r14, rax
0x180012087  test    rax, rax
0x18001208a  jnz     short loc_1800120B1
0x18001208c  mov     rcx, [rbp+188h]; this
0x180012093  lea     r8, aWil; "wil"
0x18001209a  mov     esi, 8007000Eh
0x18001209f  mov     edx, 14Bh; void *
0x1800120a4  mov     r9d, esi; char *
0x1800120a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120ac  jmp     loc_180012143
0x1800120b1  xorps   xmm0, xmm0
0x1800120b4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800120ba  test    r14b, 3
0x1800120be  jnz     loc_1800122AB
0x1800120c4  mov     r9, r14
0x1800120c7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800120cc  shr     r9, 2; unsigned __int64
0x1800120d0  lea     rcx, [rsp+280h+hObject]; this
0x1800120d5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800120da  mov     esi, eax
0x1800120dc  test    eax, eax
0x1800120de  jns     loc_18001218A
0x1800120e4  mov     rcx, [rbp+188h]; this
0x1800120eb  lea     r8, aWil; "wil"
0x1800120f2  mov     r9d, eax; char *
0x1800120f5  mov     edx, 14Eh; void *
0x1800120fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800120ff  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180012104  test    rcx, rcx
0x180012107  jz      short loc_180012117
0x180012109  call    cs:__imp_CloseHandle
0x18001210f  test    eax, eax
0x180012111  jz      loc_1800122B1
0x180012117  mov     rcx, [rsp+280h+hObject]; hObject
0x18001211c  test    rcx, rcx
0x18001211f  jz      short loc_18001212F
0x180012121  call    cs:__imp_CloseHandle
0x180012127  test    eax, eax
0x180012129  jz      loc_1800122C3
0x18001212f  call    cs:__imp_GetProcessHeap
0x180012135  mov     r8, r14; lpMem
0x180012138  xor     edx, edx; dwFlags
0x18001213a  mov     rcx, rax; hHeap
0x18001213d  call    cs:__imp_HeapFree
0x180012143  mov     rcx, [rbp+188h]; this
0x18001214a  lea     r8, aWil; "wil"
0x180012151  mov     r9d, esi; char *
0x180012154  mov     edx, 137h; void *
0x180012159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001215e  test    rdi, rdi
0x180012161  jz      short loc_180012174
0x180012163  mov     rcx, rdi; hMutex
0x180012166  call    cs:__imp_ReleaseMutex
0x18001216c  test    eax, eax
0x18001216e  jz      loc_1800122D5
0x180012174  mov     rcx, rbx; hObject
0x180012177  call    cs:__imp_CloseHandle
0x18001217d  test    eax, eax
0x18001217f  jz      loc_18001225C
0x180012185  jmp     loc_180012049
0x18001218a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18001218f  lea     rcx, [r14+28h]; void *
0x180012193  mov     dword ptr [r14], 1
0x18001219a  xor     edx, edx; Val
0x18001219c  mov     [r14+8], rbx
0x1800121a0  mov     r8d, 108h; Size
0x1800121a6  movdqu  xmmword ptr [r14+10h], xmm0
0x1800121ac  call    memset_0
0x1800121b1  xor     eax, eax
0x1800121b3  lea     rcx, [r14+28h]; this
0x1800121b7  mov     [r14+20h], rax
0x1800121bb  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800121c0  lea     rbx, [r14+0E8h]
0x1800121c7  xor     r8d, r8d; Flags
0x1800121ca  mov     rcx, rbx; lpCriticalSection
0x1800121cd  xor     edx, edx; dwSpinCount
0x1800121cf  call    cs:__imp_InitializeCriticalSectionEx
0x1800121d5  mov     qword ptr [rbx+28h], 0
0x1800121dd  mov     qword ptr [rbx+30h], 0
0x1800121e5  mov     qword ptr [rbx+38h], 0
0x1800121ed  mov     qword ptr [rbx+40h], 0
0x1800121f5  xor     ebx, ebx
0x1800121f7  mov     [r15], r14
0x1800121fa  test    rdi, rdi
0x1800121fd  jz      short loc_180012210
0x1800121ff  mov     rcx, rdi; hMutex
0x180012202  call    cs:__imp_ReleaseMutex
0x180012208  test    eax, eax
0x18001220a  jz      loc_1800122E7
0x180012210  test    rbx, rbx
0x180012213  jz      short loc_180012222
0x180012215  mov     rcx, rbx; hObject
0x180012218  call    cs:__imp_CloseHandle
0x18001221e  test    eax, eax
0x180012220  jz      short loc_18001224A
0x180012222  xor     eax, eax
0x180012224  mov     rcx, [rbp+180h+var_30]
0x18001222b  xor     rcx, rsp; StackCookie
0x18001222e  call    __security_check_cookie
0x180012233  mov     rbx, [rsp+280h+arg_10]
0x18001223b  add     rsp, 260h
0x180012242  pop     r15
0x180012244  pop     r14
0x180012246  pop     rdi
0x180012247  pop     rsi
0x180012248  pop     rbp
0x180012249  retn
0x18001224a  mov     rcx, [rbp+188h]; this
0x180012251  mov     edx, 0A0Bh; void *
0x180012256  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001225c  mov     rcx, [rbp+188h]; this
0x180012263  mov     edx, 0A0Bh; void *
0x180012268  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001226e  mov     rcx, [rbp+188h]; this
0x180012275  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001227c  mov     edx, 0E01h; void *
0x180012281  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012287  mov     rcx, [rbp+188h]; this
0x18001228e  mov     edx, 0A15h; void *
0x180012293  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012299  mov     rcx, [rbp+188h]; this
0x1800122a0  mov     edx, 0A0Bh; void *
0x1800122a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800122ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800122b1  mov     rcx, [rbp+188h]; this
0x1800122b8  mov     edx, 0A0Bh; void *
0x1800122bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800122c3  mov     rcx, [rbp+188h]; this
0x1800122ca  mov     edx, 0A0Bh; void *
0x1800122cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800122d5  mov     rcx, [rbp+188h]; this
0x1800122dc  mov     edx, 0A15h; void *
0x1800122e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800122e7  mov     rcx, [rbp+188h]; this
0x1800122ee  mov     edx, 0A15h; void *
0x1800122f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
