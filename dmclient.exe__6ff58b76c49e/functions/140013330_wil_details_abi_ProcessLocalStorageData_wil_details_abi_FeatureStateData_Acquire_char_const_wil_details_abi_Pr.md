# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140013330`
- end: `0x140013721`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140013728`

## callees

- `0x140005600`
- `0x140006a28`
- `0x140006fb8`
- `0x14000a74c`
- `0x14000ad94`
- `0x14000b5c4`
- `0x14000b69c`
- `0x14000bc1c`
- `0x14000bc2c`
- `0x140012cf8`
- `0x140013330`
- `0x1400187b2`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001345e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001359a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140013636`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001345e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001359a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140013636`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400133c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400133c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140013603`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140013603`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400133a7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400133a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013563`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013563`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013571`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013571`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001346f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001353d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400135ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001364c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001346f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001353d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400135ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001364c`

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
0x140013330  mov     [rsp-8+arg_10], rbx
0x140013335  push    rbp
0x140013336  push    rsi
0x140013337  push    rdi
0x140013338  push    r14
0x14001333a  push    r15
0x14001333c  lea     rbp, [rsp-160h]
0x140013344  sub     rsp, 260h
0x14001334b  mov     rax, cs:__security_cookie
0x140013352  xor     rax, rsp
0x140013355  mov     [rbp+180h+var_30], rax
0x14001335c  mov     r15, rdx
0x14001335f  mov     qword ptr [rdx], 0
0x140013366  mov     rbx, rcx
0x140013369  call    cs:__imp_GetCurrentProcessId
0x14001336f  mov     r14d, 130h
0x140013375  mov     [rsp+280h+var_258], rbx
0x14001337a  mov     r9d, eax
0x14001337d  mov     [rsp+280h+var_260], r14d; int
0x140013382  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140013389  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001338e  lea     edx, [r14-2Ch]; unsigned __int64
0x140013392  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013397  mov     r9d, 1F0001h; dwDesiredAccess
0x14001339d  lea     rdx, [rsp+280h+Name]; lpName
0x1400133a2  xor     r8d, r8d; dwFlags
0x1400133a5  xor     ecx, ecx; lpMutexAttributes
0x1400133a7  call    cs:__imp_CreateMutexExW
0x1400133ad  mov     rbx, rax
0x1400133b0  test    rax, rax
0x1400133b3  jnz     short loc_1400133BF
0x1400133b5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400133ba  jmp     loc_140013658
0x1400133bf  xor     r8d, r8d; bAlertable
0x1400133c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400133c5  mov     rcx, rbx; hHandle
0x1400133c8  call    cs:__imp_WaitForSingleObjectEx
0x1400133ce  cmp     eax, 102h
0x1400133d3  jz      short loc_1400133E5
0x1400133d5  test    eax, 0FFFFFF7Fh
0x1400133da  jnz     loc_1400136A2
0x1400133e0  mov     rdi, rbx
0x1400133e3  jmp     short loc_1400133E7
0x1400133e5  xor     edi, edi
0x1400133e7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400133ec  mov     [rsp+280h+hObject], 0
0x1400133f5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400133fa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400133ff  mov     esi, eax
0x140013401  test    eax, eax
0x140013403  jns     short loc_140013484
0x140013405  mov     rcx, [rbp+188h]; this
0x14001340c  lea     r8, aWil; "wil"
0x140013413  mov     r9d, eax; char *
0x140013416  mov     edx, 66h ; 'f'; void *
0x14001341b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013420  mov     rcx, [rbp+188h]; this
0x140013427  lea     r8, aWil; "wil"
0x14001342e  mov     r9d, esi; char *
0x140013431  mov     edx, 6Fh ; 'o'; void *
0x140013436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001343b  mov     rcx, [rbp+188h]; this
0x140013442  lea     r8, aWil; "wil"
0x140013449  mov     r9d, esi; char *
0x14001344c  mov     edx, 12Eh; void *
0x140013451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013456  test    rdi, rdi
0x140013459  jz      short loc_14001346C
0x14001345b  mov     rcx, rdi; hMutex
0x14001345e  call    cs:__imp_ReleaseMutex
0x140013464  test    eax, eax
0x140013466  jz      loc_1400136AF
0x14001346c  mov     rcx, rbx; hObject
0x14001346f  call    cs:__imp_CloseHandle
0x140013475  test    eax, eax
0x140013477  jz      loc_1400136C1
0x14001347d  mov     eax, esi
0x14001347f  jmp     loc_140013658
0x140013484  mov     rax, [rsp+280h+hObject]
0x140013489  lea     rcx, ds:0[rax*4]
0x140013491  test    rcx, rcx
0x140013494  jz      short loc_1400134A4
0x140013496  mov     [r15], rcx
0x140013499  mov     eax, [rcx]
0x14001349b  inc     eax
0x14001349d  mov     [rcx], eax
0x14001349f  jmp     loc_14001362E
0x1400134a4  mov     rdx, r14; dwBytes
0x1400134a7  mov     qword ptr [r15], 0
0x1400134ae  mov     ecx, 8; dwFlags
0x1400134b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400134b8  mov     r14, rax
0x1400134bb  test    rax, rax
0x1400134be  jnz     short loc_1400134E5
0x1400134c0  mov     rcx, [rbp+188h]; this
0x1400134c7  lea     r8, aWil; "wil"
0x1400134ce  mov     esi, 8007000Eh
0x1400134d3  mov     edx, 14Bh; void *
0x1400134d8  mov     r9d, esi; char *
0x1400134db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400134e0  jmp     loc_140013577
0x1400134e5  xorps   xmm0, xmm0
0x1400134e8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400134ee  test    r14b, 3
0x1400134f2  jnz     loc_1400136D3
0x1400134f8  mov     r9, r14
0x1400134fb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140013500  shr     r9, 2; unsigned __int64
0x140013504  lea     rcx, [rsp+280h+hObject]; this
0x140013509  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14001350e  mov     esi, eax
0x140013510  test    eax, eax
0x140013512  jns     loc_1400135BE
0x140013518  mov     rcx, [rbp+188h]; this
0x14001351f  lea     r8, aWil; "wil"
0x140013526  mov     r9d, eax; char *
0x140013529  mov     edx, 14Eh; void *
0x14001352e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013533  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140013538  test    rcx, rcx
0x14001353b  jz      short loc_14001354B
0x14001353d  call    cs:__imp_CloseHandle
0x140013543  test    eax, eax
0x140013545  jz      loc_1400136D9
0x14001354b  mov     rcx, [rsp+280h+hObject]; hObject
0x140013550  test    rcx, rcx
0x140013553  jz      short loc_140013563
0x140013555  call    cs:__imp_CloseHandle
0x14001355b  test    eax, eax
0x14001355d  jz      loc_1400136EB
0x140013563  call    cs:__imp_GetProcessHeap
0x140013569  mov     r8, r14; lpMem
0x14001356c  xor     edx, edx; dwFlags
0x14001356e  mov     rcx, rax; hHeap
0x140013571  call    cs:__imp_HeapFree
0x140013577  mov     rcx, [rbp+188h]; this
0x14001357e  lea     r8, aWil; "wil"
0x140013585  mov     r9d, esi; char *
0x140013588  mov     edx, 137h; void *
0x14001358d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013592  test    rdi, rdi
0x140013595  jz      short loc_1400135A8
0x140013597  mov     rcx, rdi; hMutex
0x14001359a  call    cs:__imp_ReleaseMutex
0x1400135a0  test    eax, eax
0x1400135a2  jz      loc_1400136FD
0x1400135a8  mov     rcx, rbx; hObject
0x1400135ab  call    cs:__imp_CloseHandle
0x1400135b1  test    eax, eax
0x1400135b3  jz      loc_140013690
0x1400135b9  jmp     loc_14001347D
0x1400135be  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400135c3  lea     rcx, [r14+28h]; void *
0x1400135c7  mov     dword ptr [r14], 1
0x1400135ce  xor     edx, edx; Val
0x1400135d0  mov     [r14+8], rbx
0x1400135d4  mov     r8d, 108h; Size
0x1400135da  movdqu  xmmword ptr [r14+10h], xmm0
0x1400135e0  call    memset_0
0x1400135e5  xor     eax, eax
0x1400135e7  lea     rcx, [r14+28h]; this
0x1400135eb  mov     [r14+20h], rax
0x1400135ef  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400135f4  lea     rbx, [r14+0E8h]
0x1400135fb  xor     r8d, r8d; Flags
0x1400135fe  mov     rcx, rbx; lpCriticalSection
0x140013601  xor     edx, edx; dwSpinCount
0x140013603  call    cs:__imp_InitializeCriticalSectionEx
0x140013609  mov     qword ptr [rbx+28h], 0
0x140013611  mov     qword ptr [rbx+30h], 0
0x140013619  mov     qword ptr [rbx+38h], 0
0x140013621  mov     qword ptr [rbx+40h], 0
0x140013629  xor     ebx, ebx
0x14001362b  mov     [r15], r14
0x14001362e  test    rdi, rdi
0x140013631  jz      short loc_140013644
0x140013633  mov     rcx, rdi; hMutex
0x140013636  call    cs:__imp_ReleaseMutex
0x14001363c  test    eax, eax
0x14001363e  jz      loc_14001370F
0x140013644  test    rbx, rbx
0x140013647  jz      short loc_140013656
0x140013649  mov     rcx, rbx; hObject
0x14001364c  call    cs:__imp_CloseHandle
0x140013652  test    eax, eax
0x140013654  jz      short loc_14001367E
0x140013656  xor     eax, eax
0x140013658  mov     rcx, [rbp+180h+var_30]
0x14001365f  xor     rcx, rsp; StackCookie
0x140013662  call    __security_check_cookie
0x140013667  mov     rbx, [rsp+280h+arg_10]
0x14001366f  add     rsp, 260h
0x140013676  pop     r15
0x140013678  pop     r14
0x14001367a  pop     rdi
0x14001367b  pop     rsi
0x14001367c  pop     rbp
0x14001367d  retn
0x14001367e  mov     rcx, [rbp+188h]; this
0x140013685  mov     edx, 0A0Bh; void *
0x14001368a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013690  mov     rcx, [rbp+188h]; this
0x140013697  mov     edx, 0A0Bh; void *
0x14001369c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136a2  mov     rcx, [rbp+188h]; this
0x1400136a9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400136af  mov     rcx, [rbp+188h]; this
0x1400136b6  mov     edx, 0A15h; void *
0x1400136bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136c1  mov     rcx, [rbp+188h]; this
0x1400136c8  mov     edx, 0A0Bh; void *
0x1400136cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400136d9  mov     rcx, [rbp+188h]; this
0x1400136e0  mov     edx, 0A0Bh; void *
0x1400136e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136eb  mov     rcx, [rbp+188h]; this
0x1400136f2  mov     edx, 0A0Bh; void *
0x1400136f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136fd  mov     rcx, [rbp+188h]; this
0x140013704  mov     edx, 0A15h; void *
0x140013709  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001370f  mov     rcx, [rbp+188h]; this
0x140013716  mov     edx, 0A15h; void *
0x14001371b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
