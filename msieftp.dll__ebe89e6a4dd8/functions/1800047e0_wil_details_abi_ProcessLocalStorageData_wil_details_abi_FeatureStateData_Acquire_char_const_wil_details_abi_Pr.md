# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800047e0`
- end: `0x180004ba7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004f34`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180003ad0`
- `0x1800047e0`
- `0x180004c48`
- `0x180005188`
- `0x180006508`
- `0x180007470`
- `0x180009170`
- `0x1800096c4`
- `0x180009af8`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004857`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004857`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004878`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004878`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800048f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004abc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800048f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004abc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004a89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004a89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000490a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000490a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad2`

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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp-8+arg_10], rbx
0x1800047e5  push    rbp
0x1800047e6  push    rsi
0x1800047e7  push    rdi
0x1800047e8  push    r14
0x1800047ea  push    r15
0x1800047ec  lea     rbp, [rsp-160h]
0x1800047f4  sub     rsp, 260h
0x1800047fb  mov     rax, cs:__security_cookie
0x180004802  xor     rax, rsp
0x180004805  mov     [rbp+180h+var_30], rax
0x18000480c  mov     r15, rdx
0x18000480f  mov     qword ptr [rdx], 0
0x180004816  mov     rbx, rcx
0x180004819  call    cs:__imp_GetCurrentProcessId
0x18000481f  mov     r14d, 130h
0x180004825  mov     [rsp+280h+var_258], rbx
0x18000482a  mov     r9d, eax
0x18000482d  mov     [rsp+280h+var_260], r14d; int
0x180004832  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004839  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000483e  lea     edx, [r14-2Ch]; unsigned __int64
0x180004842  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004847  mov     r9d, 1F0001h; dwDesiredAccess
0x18000484d  lea     rdx, [rsp+280h+Name]; lpName
0x180004852  xor     r8d, r8d; dwFlags
0x180004855  xor     ecx, ecx; lpMutexAttributes
0x180004857  call    cs:__imp_CreateMutexExW
0x18000485d  mov     rbx, rax
0x180004860  test    rax, rax
0x180004863  jnz     short loc_18000486F
0x180004865  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000486a  jmp     loc_180004ADE
0x18000486f  xor     r8d, r8d; bAlertable
0x180004872  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004875  mov     rcx, rbx; hHandle
0x180004878  call    cs:__imp_WaitForSingleObjectEx
0x18000487e  cmp     eax, 102h
0x180004883  jz      short loc_180004895
0x180004885  test    eax, 0FFFFFF7Fh
0x18000488a  jnz     loc_180004B28
0x180004890  mov     rdi, rbx
0x180004893  jmp     short loc_180004897
0x180004895  xor     edi, edi
0x180004897  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000489c  mov     [rsp+280h+hObject], 0
0x1800048a5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800048aa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800048af  mov     esi, eax
0x1800048b1  test    eax, eax
0x1800048b3  jns     short loc_18000491F
0x1800048b5  mov     rcx, [rbp+188h]; this
0x1800048bc  mov     r9d, eax; char *
0x1800048bf  mov     edx, 66h ; 'f'; void *
0x1800048c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048c9  mov     rcx, [rbp+188h]; this
0x1800048d0  mov     r9d, esi; char *
0x1800048d3  mov     edx, 6Fh ; 'o'; void *
0x1800048d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048dd  mov     rcx, [rbp+188h]; this
0x1800048e4  mov     r9d, esi; char *
0x1800048e7  mov     edx, 12Eh; void *
0x1800048ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048f1  test    rdi, rdi
0x1800048f4  jz      short loc_180004907
0x1800048f6  mov     rcx, rdi; hMutex
0x1800048f9  call    cs:__imp_ReleaseMutex
0x1800048ff  test    eax, eax
0x180004901  jz      loc_180004B35
0x180004907  mov     rcx, rbx; hObject
0x18000490a  call    cs:__imp_CloseHandle
0x180004910  test    eax, eax
0x180004912  jz      loc_180004B47
0x180004918  mov     eax, esi
0x18000491a  jmp     loc_180004ADE
0x18000491f  mov     rax, [rsp+280h+hObject]
0x180004924  lea     rcx, ds:0[rax*4]
0x18000492c  test    rcx, rcx
0x18000492f  jz      short loc_18000493F
0x180004931  mov     [r15], rcx
0x180004934  mov     eax, [rcx]
0x180004936  inc     eax
0x180004938  mov     [rcx], eax
0x18000493a  jmp     loc_180004AB4
0x18000493f  mov     rdx, r14; dwBytes
0x180004942  mov     qword ptr [r15], 0
0x180004949  mov     ecx, 8; dwFlags
0x18000494e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004953  mov     r14, rax
0x180004956  test    rax, rax
0x180004959  jnz     short loc_180004979
0x18000495b  mov     rcx, [rbp+188h]; this
0x180004962  mov     esi, 8007000Eh
0x180004967  mov     r9d, esi; char *
0x18000496a  mov     edx, 14Bh; void *
0x18000496f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004974  jmp     loc_180004A04
0x180004979  xorps   xmm0, xmm0
0x18000497c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004982  test    r14b, 3
0x180004986  jnz     loc_180004B59
0x18000498c  mov     r9, r14
0x18000498f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004994  shr     r9, 2; unsigned __int64
0x180004998  lea     rcx, [rsp+280h+hObject]; this
0x18000499d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800049a2  mov     esi, eax
0x1800049a4  test    eax, eax
0x1800049a6  jns     loc_180004A44
0x1800049ac  mov     rcx, [rbp+188h]; this
0x1800049b3  mov     r9d, eax; char *
0x1800049b6  mov     edx, 14Eh; void *
0x1800049bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049c0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800049c5  test    rcx, rcx
0x1800049c8  jz      short loc_1800049D8
0x1800049ca  call    cs:__imp_CloseHandle
0x1800049d0  test    eax, eax
0x1800049d2  jz      loc_180004B5F
0x1800049d8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800049dd  test    rcx, rcx
0x1800049e0  jz      short loc_1800049F0
0x1800049e2  call    cs:__imp_CloseHandle
0x1800049e8  test    eax, eax
0x1800049ea  jz      loc_180004B71
0x1800049f0  call    cs:__imp_GetProcessHeap
0x1800049f6  mov     r8, r14; lpMem
0x1800049f9  xor     edx, edx; dwFlags
0x1800049fb  mov     rcx, rax; hHeap
0x1800049fe  call    cs:__imp_HeapFree
0x180004a04  mov     rcx, [rbp+188h]; this
0x180004a0b  mov     r9d, esi; char *
0x180004a0e  mov     edx, 137h; void *
0x180004a13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a18  test    rdi, rdi
0x180004a1b  jz      short loc_180004A2E
0x180004a1d  mov     rcx, rdi; hMutex
0x180004a20  call    cs:__imp_ReleaseMutex
0x180004a26  test    eax, eax
0x180004a28  jz      loc_180004B83
0x180004a2e  mov     rcx, rbx; hObject
0x180004a31  call    cs:__imp_CloseHandle
0x180004a37  test    eax, eax
0x180004a39  jz      loc_180004B16
0x180004a3f  jmp     loc_180004918
0x180004a44  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004a49  lea     rcx, [r14+28h]; void *
0x180004a4d  mov     dword ptr [r14], 1
0x180004a54  xor     edx, edx; Val
0x180004a56  mov     [r14+8], rbx
0x180004a5a  mov     r8d, 108h; Size
0x180004a60  movdqu  xmmword ptr [r14+10h], xmm0
0x180004a66  call    memset_0
0x180004a6b  xor     eax, eax
0x180004a6d  lea     rcx, [r14+28h]; this
0x180004a71  mov     [r14+20h], rax
0x180004a75  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004a7a  lea     rbx, [r14+0E8h]
0x180004a81  xor     r8d, r8d; Flags
0x180004a84  mov     rcx, rbx; lpCriticalSection
0x180004a87  xor     edx, edx; dwSpinCount
0x180004a89  call    cs:__imp_InitializeCriticalSectionEx
0x180004a8f  mov     qword ptr [rbx+28h], 0
0x180004a97  mov     qword ptr [rbx+30h], 0
0x180004a9f  mov     qword ptr [rbx+38h], 0
0x180004aa7  mov     qword ptr [rbx+40h], 0
0x180004aaf  xor     ebx, ebx
0x180004ab1  mov     [r15], r14
0x180004ab4  test    rdi, rdi
0x180004ab7  jz      short loc_180004ACA
0x180004ab9  mov     rcx, rdi; hMutex
0x180004abc  call    cs:__imp_ReleaseMutex
0x180004ac2  test    eax, eax
0x180004ac4  jz      loc_180004B95
0x180004aca  test    rbx, rbx
0x180004acd  jz      short loc_180004ADC
0x180004acf  mov     rcx, rbx; hObject
0x180004ad2  call    cs:__imp_CloseHandle
0x180004ad8  test    eax, eax
0x180004ada  jz      short loc_180004B04
0x180004adc  xor     eax, eax
0x180004ade  mov     rcx, [rbp+180h+var_30]
0x180004ae5  xor     rcx, rsp; StackCookie
0x180004ae8  call    __security_check_cookie
0x180004aed  mov     rbx, [rsp+280h+arg_10]
0x180004af5  add     rsp, 260h
0x180004afc  pop     r15
0x180004afe  pop     r14
0x180004b00  pop     rdi
0x180004b01  pop     rsi
0x180004b02  pop     rbp
0x180004b03  retn
0x180004b04  mov     rcx, [rbp+188h]; this
0x180004b0b  mov     edx, 0A0Bh; void *
0x180004b10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b16  mov     rcx, [rbp+188h]; this
0x180004b1d  mov     edx, 0A0Bh; void *
0x180004b22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b28  mov     rcx, [rbp+188h]; this
0x180004b2f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004b35  mov     rcx, [rbp+188h]; this
0x180004b3c  mov     edx, 0A15h; void *
0x180004b41  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b47  mov     rcx, [rbp+188h]; this
0x180004b4e  mov     edx, 0A0Bh; void *
0x180004b53  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b59  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b5f  mov     rcx, [rbp+188h]; this
0x180004b66  mov     edx, 0A0Bh; void *
0x180004b6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b71  mov     rcx, [rbp+188h]; this
0x180004b78  mov     edx, 0A0Bh; void *
0x180004b7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b83  mov     rcx, [rbp+188h]; this
0x180004b8a  mov     edx, 0A15h; void *
0x180004b8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b95  mov     rcx, [rbp+188h]; this
0x180004b9c  mov     edx, 0A15h; void *
0x180004ba1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
