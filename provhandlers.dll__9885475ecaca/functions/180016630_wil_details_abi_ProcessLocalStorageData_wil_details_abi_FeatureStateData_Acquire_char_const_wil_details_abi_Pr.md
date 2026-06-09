# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180016630`
- end: `0x180016a21`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180017564`

## callees

- `0x1800051b0`
- `0x180005ab8`
- `0x180006218`
- `0x180006da8`
- `0x1800076a4`
- `0x180007f48`
- `0x18000813c`
- `0x18000872c`
- `0x18000873c`
- `0x180015d5c`
- `0x180016630`
- `0x18003b96a`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800166a7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800166a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800166c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800166c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180016903`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180016903`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001675e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001689a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016936`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001675e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001689a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016936`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016871`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016871`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016669`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001676f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001683d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800168ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001694c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001676f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001683d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800168ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001694c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v24; // r14
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180016630  mov     [rsp-8+arg_10], rbx
0x180016635  push    rbp
0x180016636  push    rsi
0x180016637  push    rdi
0x180016638  push    r14
0x18001663a  push    r15
0x18001663c  lea     rbp, [rsp-160h]
0x180016644  sub     rsp, 260h
0x18001664b  mov     rax, cs:__security_cookie
0x180016652  xor     rax, rsp
0x180016655  mov     [rbp+180h+var_30], rax
0x18001665c  mov     r15, rdx
0x18001665f  mov     qword ptr [rdx], 0
0x180016666  mov     rbx, rcx
0x180016669  call    cs:__imp_GetCurrentProcessId
0x18001666f  mov     r14d, 130h
0x180016675  mov     [rsp+280h+var_258], rbx
0x18001667a  mov     r9d, eax
0x18001667d  mov     [rsp+280h+var_260], r14d; int
0x180016682  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180016689  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001668e  lea     edx, [r14-2Ch]; unsigned __int64
0x180016692  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016697  mov     r9d, 1F0001h; dwDesiredAccess
0x18001669d  lea     rdx, [rsp+280h+Name]; lpName
0x1800166a2  xor     r8d, r8d; dwFlags
0x1800166a5  xor     ecx, ecx; lpMutexAttributes
0x1800166a7  call    cs:__imp_CreateMutexExW
0x1800166ad  mov     rbx, rax
0x1800166b0  test    rax, rax
0x1800166b3  jnz     short loc_1800166BF
0x1800166b5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800166ba  jmp     loc_180016958
0x1800166bf  xor     r8d, r8d; bAlertable
0x1800166c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800166c5  mov     rcx, rbx; hHandle
0x1800166c8  call    cs:__imp_WaitForSingleObjectEx
0x1800166ce  cmp     eax, 102h
0x1800166d3  jz      short loc_1800166E5
0x1800166d5  test    eax, 0FFFFFF7Fh
0x1800166da  jnz     loc_1800169A2
0x1800166e0  mov     rdi, rbx
0x1800166e3  jmp     short loc_1800166E7
0x1800166e5  xor     edi, edi
0x1800166e7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800166ec  mov     [rsp+280h+hObject], 0
0x1800166f5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800166fa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800166ff  mov     esi, eax
0x180016701  test    eax, eax
0x180016703  jns     short loc_180016784
0x180016705  mov     rcx, [rbp+188h]; this
0x18001670c  lea     r8, aWil; "wil"
0x180016713  mov     r9d, eax; char *
0x180016716  mov     edx, 66h ; 'f'; void *
0x18001671b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016720  mov     rcx, [rbp+188h]; this
0x180016727  lea     r8, aWil; "wil"
0x18001672e  mov     r9d, esi; char *
0x180016731  mov     edx, 6Fh ; 'o'; void *
0x180016736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001673b  mov     rcx, [rbp+188h]; this
0x180016742  lea     r8, aWil; "wil"
0x180016749  mov     r9d, esi; char *
0x18001674c  mov     edx, 12Eh; void *
0x180016751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016756  test    rdi, rdi
0x180016759  jz      short loc_18001676C
0x18001675b  mov     rcx, rdi; hMutex
0x18001675e  call    cs:__imp_ReleaseMutex
0x180016764  test    eax, eax
0x180016766  jz      loc_1800169AF
0x18001676c  mov     rcx, rbx; hObject
0x18001676f  call    cs:__imp_CloseHandle
0x180016775  test    eax, eax
0x180016777  jz      loc_1800169C1
0x18001677d  mov     eax, esi
0x18001677f  jmp     loc_180016958
0x180016784  mov     rax, [rsp+280h+hObject]
0x180016789  lea     rcx, ds:0[rax*4]
0x180016791  test    rcx, rcx
0x180016794  jz      short loc_1800167A4
0x180016796  mov     [r15], rcx
0x180016799  mov     eax, [rcx]
0x18001679b  inc     eax
0x18001679d  mov     [rcx], eax
0x18001679f  jmp     loc_18001692E
0x1800167a4  mov     rdx, r14; dwBytes
0x1800167a7  mov     qword ptr [r15], 0
0x1800167ae  mov     ecx, 8; dwFlags
0x1800167b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800167b8  mov     r14, rax
0x1800167bb  test    rax, rax
0x1800167be  jnz     short loc_1800167E5
0x1800167c0  mov     rcx, [rbp+188h]; this
0x1800167c7  lea     r8, aWil; "wil"
0x1800167ce  mov     esi, 8007000Eh
0x1800167d3  mov     edx, 14Bh; void *
0x1800167d8  mov     r9d, esi; char *
0x1800167db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167e0  jmp     loc_180016877
0x1800167e5  xorps   xmm0, xmm0
0x1800167e8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800167ee  test    r14b, 3
0x1800167f2  jnz     loc_1800169D3
0x1800167f8  mov     r9, r14
0x1800167fb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180016800  shr     r9, 2; unsigned __int64
0x180016804  lea     rcx, [rsp+280h+hObject]; this
0x180016809  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001680e  mov     esi, eax
0x180016810  test    eax, eax
0x180016812  jns     loc_1800168BE
0x180016818  mov     rcx, [rbp+188h]; this
0x18001681f  lea     r8, aWil; "wil"
0x180016826  mov     r9d, eax; char *
0x180016829  mov     edx, 14Eh; void *
0x18001682e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016833  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180016838  test    rcx, rcx
0x18001683b  jz      short loc_18001684B
0x18001683d  call    cs:__imp_CloseHandle
0x180016843  test    eax, eax
0x180016845  jz      loc_1800169D9
0x18001684b  mov     rcx, [rsp+280h+hObject]; hObject
0x180016850  test    rcx, rcx
0x180016853  jz      short loc_180016863
0x180016855  call    cs:__imp_CloseHandle
0x18001685b  test    eax, eax
0x18001685d  jz      loc_1800169EB
0x180016863  call    cs:__imp_GetProcessHeap
0x180016869  mov     r8, r14; lpMem
0x18001686c  xor     edx, edx; dwFlags
0x18001686e  mov     rcx, rax; hHeap
0x180016871  call    cs:__imp_HeapFree
0x180016877  mov     rcx, [rbp+188h]; this
0x18001687e  lea     r8, aWil; "wil"
0x180016885  mov     r9d, esi; char *
0x180016888  mov     edx, 137h; void *
0x18001688d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016892  test    rdi, rdi
0x180016895  jz      short loc_1800168A8
0x180016897  mov     rcx, rdi; hMutex
0x18001689a  call    cs:__imp_ReleaseMutex
0x1800168a0  test    eax, eax
0x1800168a2  jz      loc_1800169FD
0x1800168a8  mov     rcx, rbx; hObject
0x1800168ab  call    cs:__imp_CloseHandle
0x1800168b1  test    eax, eax
0x1800168b3  jz      loc_180016990
0x1800168b9  jmp     loc_18001677D
0x1800168be  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800168c3  lea     rcx, [r14+28h]; void *
0x1800168c7  mov     dword ptr [r14], 1
0x1800168ce  xor     edx, edx; Val
0x1800168d0  mov     [r14+8], rbx
0x1800168d4  mov     r8d, 108h; Size
0x1800168da  movdqu  xmmword ptr [r14+10h], xmm0
0x1800168e0  call    memset_0
0x1800168e5  xor     eax, eax
0x1800168e7  lea     rcx, [r14+28h]; this
0x1800168eb  mov     [r14+20h], rax
0x1800168ef  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800168f4  lea     rbx, [r14+0E8h]
0x1800168fb  xor     r8d, r8d; Flags
0x1800168fe  mov     rcx, rbx; lpCriticalSection
0x180016901  xor     edx, edx; dwSpinCount
0x180016903  call    cs:__imp_InitializeCriticalSectionEx
0x180016909  mov     qword ptr [rbx+28h], 0
0x180016911  mov     qword ptr [rbx+30h], 0
0x180016919  mov     qword ptr [rbx+38h], 0
0x180016921  mov     qword ptr [rbx+40h], 0
0x180016929  xor     ebx, ebx
0x18001692b  mov     [r15], r14
0x18001692e  test    rdi, rdi
0x180016931  jz      short loc_180016944
0x180016933  mov     rcx, rdi; hMutex
0x180016936  call    cs:__imp_ReleaseMutex
0x18001693c  test    eax, eax
0x18001693e  jz      loc_180016A0F
0x180016944  test    rbx, rbx
0x180016947  jz      short loc_180016956
0x180016949  mov     rcx, rbx; hObject
0x18001694c  call    cs:__imp_CloseHandle
0x180016952  test    eax, eax
0x180016954  jz      short loc_18001697E
0x180016956  xor     eax, eax
0x180016958  mov     rcx, [rbp+180h+var_30]
0x18001695f  xor     rcx, rsp; StackCookie
0x180016962  call    __security_check_cookie
0x180016967  mov     rbx, [rsp+280h+arg_10]
0x18001696f  add     rsp, 260h
0x180016976  pop     r15
0x180016978  pop     r14
0x18001697a  pop     rdi
0x18001697b  pop     rsi
0x18001697c  pop     rbp
0x18001697d  retn
0x18001697e  mov     rcx, [rbp+188h]; this
0x180016985  mov     edx, 0A0Bh; void *
0x18001698a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016990  mov     rcx, [rbp+188h]; this
0x180016997  mov     edx, 0A0Bh; void *
0x18001699c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800169a2  mov     rcx, [rbp+188h]; this
0x1800169a9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800169af  mov     rcx, [rbp+188h]; this
0x1800169b6  mov     edx, 0A15h; void *
0x1800169bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800169c1  mov     rcx, [rbp+188h]; this
0x1800169c8  mov     edx, 0A0Bh; void *
0x1800169cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800169d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800169d9  mov     rcx, [rbp+188h]; this
0x1800169e0  mov     edx, 0A0Bh; void *
0x1800169e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800169eb  mov     rcx, [rbp+188h]; this
0x1800169f2  mov     edx, 0A0Bh; void *
0x1800169f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800169fd  mov     rcx, [rbp+188h]; this
0x180016a04  mov     edx, 0A15h; void *
0x180016a09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016a0f  mov     rcx, [rbp+188h]; this
0x180016a16  mov     edx, 0A15h; void *
0x180016a1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
