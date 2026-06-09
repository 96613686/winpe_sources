# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800047cc`
- end: `0x180004b93`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004e64`

## callees

- `0x180001f60`
- `0x1800028dc`
- `0x1800037c4`
- `0x1800047cc`
- `0x180004b9c`
- `0x1800050b8`
- `0x180005ad8`
- `0x180006840`
- `0x180008274`
- `0x180008d34`
- `0x18000919c`
- `0x180009a4c`
- `0x180009a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004843`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004843`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004864`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004864`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004a75`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004a75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800048e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800048e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004aa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004abe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004abe`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
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
0x1800047cc  mov     [rsp-8+arg_10], rbx
0x1800047d1  push    rbp
0x1800047d2  push    rsi
0x1800047d3  push    rdi
0x1800047d4  push    r14
0x1800047d6  push    r15
0x1800047d8  lea     rbp, [rsp-160h]
0x1800047e0  sub     rsp, 260h
0x1800047e7  mov     rax, cs:__security_cookie
0x1800047ee  xor     rax, rsp
0x1800047f1  mov     [rbp+180h+var_30], rax
0x1800047f8  mov     r15, rdx
0x1800047fb  mov     qword ptr [rdx], 0
0x180004802  mov     rbx, rcx
0x180004805  call    cs:__imp_GetCurrentProcessId
0x18000480b  mov     r14d, 130h
0x180004811  mov     [rsp+280h+var_258], rbx
0x180004816  mov     r9d, eax
0x180004819  mov     [rsp+280h+var_260], r14d; int
0x18000481e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004825  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000482a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000482e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004833  mov     r9d, 1F0001h; dwDesiredAccess
0x180004839  lea     rdx, [rsp+280h+Name]; lpName
0x18000483e  xor     r8d, r8d; dwFlags
0x180004841  xor     ecx, ecx; lpMutexAttributes
0x180004843  call    cs:__imp_CreateMutexExW
0x180004849  mov     rbx, rax
0x18000484c  test    rax, rax
0x18000484f  jnz     short loc_18000485B
0x180004851  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004856  jmp     loc_180004ACA
0x18000485b  xor     r8d, r8d; bAlertable
0x18000485e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004861  mov     rcx, rbx; hHandle
0x180004864  call    cs:__imp_WaitForSingleObjectEx
0x18000486a  cmp     eax, 102h
0x18000486f  jz      short loc_180004881
0x180004871  test    eax, 0FFFFFF7Fh
0x180004876  jnz     loc_180004B14
0x18000487c  mov     rdi, rbx
0x18000487f  jmp     short loc_180004883
0x180004881  xor     edi, edi
0x180004883  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004888  mov     [rsp+280h+hObject], 0
0x180004891  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004896  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000489b  mov     esi, eax
0x18000489d  test    eax, eax
0x18000489f  jns     short loc_18000490B
0x1800048a1  mov     rcx, [rbp+188h]; this
0x1800048a8  mov     r9d, eax; char *
0x1800048ab  mov     edx, 66h ; 'f'; void *
0x1800048b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048b5  mov     rcx, [rbp+188h]; this
0x1800048bc  mov     r9d, esi; char *
0x1800048bf  mov     edx, 6Fh ; 'o'; void *
0x1800048c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048c9  mov     rcx, [rbp+188h]; this
0x1800048d0  mov     r9d, esi; char *
0x1800048d3  mov     edx, 12Eh; void *
0x1800048d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048dd  test    rdi, rdi
0x1800048e0  jz      short loc_1800048F3
0x1800048e2  mov     rcx, rdi; hMutex
0x1800048e5  call    cs:__imp_ReleaseMutex
0x1800048eb  test    eax, eax
0x1800048ed  jz      loc_180004B21
0x1800048f3  mov     rcx, rbx; hObject
0x1800048f6  call    cs:__imp_CloseHandle
0x1800048fc  test    eax, eax
0x1800048fe  jz      loc_180004B33
0x180004904  mov     eax, esi
0x180004906  jmp     loc_180004ACA
0x18000490b  mov     rax, [rsp+280h+hObject]
0x180004910  lea     rcx, ds:0[rax*4]
0x180004918  test    rcx, rcx
0x18000491b  jz      short loc_18000492B
0x18000491d  mov     [r15], rcx
0x180004920  mov     eax, [rcx]
0x180004922  inc     eax
0x180004924  mov     [rcx], eax
0x180004926  jmp     loc_180004AA0
0x18000492b  mov     rdx, r14; dwBytes
0x18000492e  mov     qword ptr [r15], 0
0x180004935  mov     ecx, 8; dwFlags
0x18000493a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000493f  mov     r14, rax
0x180004942  test    rax, rax
0x180004945  jnz     short loc_180004965
0x180004947  mov     rcx, [rbp+188h]; this
0x18000494e  mov     esi, 8007000Eh
0x180004953  mov     r9d, esi; char *
0x180004956  mov     edx, 14Bh; void *
0x18000495b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004960  jmp     loc_1800049F0
0x180004965  xorps   xmm0, xmm0
0x180004968  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000496e  test    r14b, 3
0x180004972  jnz     loc_180004B45
0x180004978  mov     r9, r14
0x18000497b  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180004980  shr     r9, 2; unsigned __int64
0x180004984  lea     rcx, [rsp+280h+hObject]; this
0x180004989  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000498e  mov     esi, eax
0x180004990  test    eax, eax
0x180004992  jns     loc_180004A30
0x180004998  mov     rcx, [rbp+188h]; this
0x18000499f  mov     r9d, eax; char *
0x1800049a2  mov     edx, 14Eh; void *
0x1800049a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049ac  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800049b1  test    rcx, rcx
0x1800049b4  jz      short loc_1800049C4
0x1800049b6  call    cs:__imp_CloseHandle
0x1800049bc  test    eax, eax
0x1800049be  jz      loc_180004B4B
0x1800049c4  mov     rcx, [rsp+280h+hObject]; hObject
0x1800049c9  test    rcx, rcx
0x1800049cc  jz      short loc_1800049DC
0x1800049ce  call    cs:__imp_CloseHandle
0x1800049d4  test    eax, eax
0x1800049d6  jz      loc_180004B5D
0x1800049dc  call    cs:__imp_GetProcessHeap
0x1800049e2  mov     r8, r14; lpMem
0x1800049e5  xor     edx, edx; dwFlags
0x1800049e7  mov     rcx, rax; hHeap
0x1800049ea  call    cs:__imp_HeapFree
0x1800049f0  mov     rcx, [rbp+188h]; this
0x1800049f7  mov     r9d, esi; char *
0x1800049fa  mov     edx, 137h; void *
0x1800049ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a04  test    rdi, rdi
0x180004a07  jz      short loc_180004A1A
0x180004a09  mov     rcx, rdi; hMutex
0x180004a0c  call    cs:__imp_ReleaseMutex
0x180004a12  test    eax, eax
0x180004a14  jz      loc_180004B6F
0x180004a1a  mov     rcx, rbx; hObject
0x180004a1d  call    cs:__imp_CloseHandle
0x180004a23  test    eax, eax
0x180004a25  jz      loc_180004B02
0x180004a2b  jmp     loc_180004904
0x180004a30  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004a35  lea     rcx, [r14+28h]; void *
0x180004a39  mov     dword ptr [r14], 1
0x180004a40  xor     edx, edx; Val
0x180004a42  mov     [r14+8], rbx
0x180004a46  mov     r8d, 108h; Size
0x180004a4c  movdqu  xmmword ptr [r14+10h], xmm0
0x180004a52  call    memset_0
0x180004a57  xor     eax, eax
0x180004a59  lea     rcx, [r14+28h]; this
0x180004a5d  mov     [r14+20h], rax
0x180004a61  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004a66  lea     rbx, [r14+0E8h]
0x180004a6d  xor     r8d, r8d; Flags
0x180004a70  mov     rcx, rbx; lpCriticalSection
0x180004a73  xor     edx, edx; dwSpinCount
0x180004a75  call    cs:__imp_InitializeCriticalSectionEx
0x180004a7b  mov     qword ptr [rbx+28h], 0
0x180004a83  mov     qword ptr [rbx+30h], 0
0x180004a8b  mov     qword ptr [rbx+38h], 0
0x180004a93  mov     qword ptr [rbx+40h], 0
0x180004a9b  xor     ebx, ebx
0x180004a9d  mov     [r15], r14
0x180004aa0  test    rdi, rdi
0x180004aa3  jz      short loc_180004AB6
0x180004aa5  mov     rcx, rdi; hMutex
0x180004aa8  call    cs:__imp_ReleaseMutex
0x180004aae  test    eax, eax
0x180004ab0  jz      loc_180004B81
0x180004ab6  test    rbx, rbx
0x180004ab9  jz      short loc_180004AC8
0x180004abb  mov     rcx, rbx; hObject
0x180004abe  call    cs:__imp_CloseHandle
0x180004ac4  test    eax, eax
0x180004ac6  jz      short loc_180004AF0
0x180004ac8  xor     eax, eax
0x180004aca  mov     rcx, [rbp+180h+var_30]
0x180004ad1  xor     rcx, rsp; StackCookie
0x180004ad4  call    __security_check_cookie
0x180004ad9  mov     rbx, [rsp+280h+arg_10]
0x180004ae1  add     rsp, 260h
0x180004ae8  pop     r15
0x180004aea  pop     r14
0x180004aec  pop     rdi
0x180004aed  pop     rsi
0x180004aee  pop     rbp
0x180004aef  retn
0x180004af0  mov     rcx, [rbp+188h]; this
0x180004af7  mov     edx, 0A0Bh; void *
0x180004afc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b02  mov     rcx, [rbp+188h]; this
0x180004b09  mov     edx, 0A0Bh; void *
0x180004b0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b14  mov     rcx, [rbp+188h]; this
0x180004b1b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004b21  mov     rcx, [rbp+188h]; this
0x180004b28  mov     edx, 0A15h; void *
0x180004b2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b33  mov     rcx, [rbp+188h]; this
0x180004b3a  mov     edx, 0A0Bh; void *
0x180004b3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b45  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b4b  mov     rcx, [rbp+188h]; this
0x180004b52  mov     edx, 0A0Bh; void *
0x180004b57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b5d  mov     rcx, [rbp+188h]; this
0x180004b64  mov     edx, 0A0Bh; void *
0x180004b69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b6f  mov     rcx, [rbp+188h]; this
0x180004b76  mov     edx, 0A15h; void *
0x180004b7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b81  mov     rcx, [rbp+188h]; this
0x180004b88  mov     edx, 0A15h; void *
0x180004b8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
