# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800044b0`
- end: `0x180004877`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004b54`

## callees

- `0x1800039fc`
- `0x1800044b0`
- `0x180004880`
- `0x180004ce4`
- `0x180005608`
- `0x1800061f8`
- `0x180007490`
- `0x180007960`
- `0x180007c68`
- `0x18000843c`
- `0x18000844c`
- `0x18000bbc2`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000478c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000478c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004548`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004548`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004759`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004759`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004527`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004527`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000469a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000469a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800044e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800044e9`

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
0x1800044b0  mov     [rsp-8+arg_10], rbx
0x1800044b5  push    rbp
0x1800044b6  push    rsi
0x1800044b7  push    rdi
0x1800044b8  push    r14
0x1800044ba  push    r15
0x1800044bc  lea     rbp, [rsp-160h]
0x1800044c4  sub     rsp, 260h
0x1800044cb  mov     rax, cs:__security_cookie
0x1800044d2  xor     rax, rsp
0x1800044d5  mov     [rbp+180h+var_30], rax
0x1800044dc  mov     r15, rdx
0x1800044df  mov     qword ptr [rdx], 0
0x1800044e6  mov     rbx, rcx
0x1800044e9  call    cs:__imp_GetCurrentProcessId
0x1800044ef  mov     r14d, 130h
0x1800044f5  mov     [rsp+280h+var_258], rbx
0x1800044fa  mov     r9d, eax
0x1800044fd  mov     [rsp+280h+var_260], r14d; int
0x180004502  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004509  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000450e  lea     edx, [r14-2Ch]; unsigned __int64
0x180004512  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004517  mov     r9d, 1F0001h; dwDesiredAccess
0x18000451d  lea     rdx, [rsp+280h+Name]; lpName
0x180004522  xor     r8d, r8d; dwFlags
0x180004525  xor     ecx, ecx; lpMutexAttributes
0x180004527  call    cs:__imp_CreateMutexExW
0x18000452d  mov     rbx, rax
0x180004530  test    rax, rax
0x180004533  jnz     short loc_18000453F
0x180004535  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000453a  jmp     loc_1800047AE
0x18000453f  xor     r8d, r8d; bAlertable
0x180004542  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004545  mov     rcx, rbx; hHandle
0x180004548  call    cs:__imp_WaitForSingleObjectEx
0x18000454e  cmp     eax, 102h
0x180004553  jz      short loc_180004565
0x180004555  test    eax, 0FFFFFF7Fh
0x18000455a  jnz     loc_1800047F8
0x180004560  mov     rdi, rbx
0x180004563  jmp     short loc_180004567
0x180004565  xor     edi, edi
0x180004567  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000456c  mov     [rsp+280h+hObject], 0
0x180004575  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000457a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000457f  mov     esi, eax
0x180004581  test    eax, eax
0x180004583  jns     short loc_1800045EF
0x180004585  mov     rcx, [rbp+188h]; this
0x18000458c  mov     r9d, eax; char *
0x18000458f  mov     edx, 66h ; 'f'; void *
0x180004594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004599  mov     rcx, [rbp+188h]; this
0x1800045a0  mov     r9d, esi; char *
0x1800045a3  mov     edx, 6Fh ; 'o'; void *
0x1800045a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045ad  mov     rcx, [rbp+188h]; this
0x1800045b4  mov     r9d, esi; char *
0x1800045b7  mov     edx, 12Eh; void *
0x1800045bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045c1  test    rdi, rdi
0x1800045c4  jz      short loc_1800045D7
0x1800045c6  mov     rcx, rdi; hMutex
0x1800045c9  call    cs:__imp_ReleaseMutex
0x1800045cf  test    eax, eax
0x1800045d1  jz      loc_180004805
0x1800045d7  mov     rcx, rbx; hObject
0x1800045da  call    cs:__imp_CloseHandle
0x1800045e0  test    eax, eax
0x1800045e2  jz      loc_180004817
0x1800045e8  mov     eax, esi
0x1800045ea  jmp     loc_1800047AE
0x1800045ef  mov     rax, [rsp+280h+hObject]
0x1800045f4  lea     rcx, ds:0[rax*4]
0x1800045fc  test    rcx, rcx
0x1800045ff  jz      short loc_18000460F
0x180004601  mov     [r15], rcx
0x180004604  mov     eax, [rcx]
0x180004606  inc     eax
0x180004608  mov     [rcx], eax
0x18000460a  jmp     loc_180004784
0x18000460f  mov     rdx, r14; dwBytes
0x180004612  mov     qword ptr [r15], 0
0x180004619  mov     ecx, 8; dwFlags
0x18000461e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004623  mov     r14, rax
0x180004626  test    rax, rax
0x180004629  jnz     short loc_180004649
0x18000462b  mov     rcx, [rbp+188h]; this
0x180004632  mov     esi, 8007000Eh
0x180004637  mov     r9d, esi; char *
0x18000463a  mov     edx, 14Bh; void *
0x18000463f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004644  jmp     loc_1800046D4
0x180004649  xorps   xmm0, xmm0
0x18000464c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004652  test    r14b, 3
0x180004656  jnz     loc_180004829
0x18000465c  mov     r9, r14
0x18000465f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004664  shr     r9, 2; unsigned __int64
0x180004668  lea     rcx, [rsp+280h+hObject]; this
0x18000466d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004672  mov     esi, eax
0x180004674  test    eax, eax
0x180004676  jns     loc_180004714
0x18000467c  mov     rcx, [rbp+188h]; this
0x180004683  mov     r9d, eax; char *
0x180004686  mov     edx, 14Eh; void *
0x18000468b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004690  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004695  test    rcx, rcx
0x180004698  jz      short loc_1800046A8
0x18000469a  call    cs:__imp_CloseHandle
0x1800046a0  test    eax, eax
0x1800046a2  jz      loc_18000482F
0x1800046a8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800046ad  test    rcx, rcx
0x1800046b0  jz      short loc_1800046C0
0x1800046b2  call    cs:__imp_CloseHandle
0x1800046b8  test    eax, eax
0x1800046ba  jz      loc_180004841
0x1800046c0  call    cs:__imp_GetProcessHeap
0x1800046c6  mov     r8, r14; lpMem
0x1800046c9  xor     edx, edx; dwFlags
0x1800046cb  mov     rcx, rax; hHeap
0x1800046ce  call    cs:__imp_HeapFree
0x1800046d4  mov     rcx, [rbp+188h]; this
0x1800046db  mov     r9d, esi; char *
0x1800046de  mov     edx, 137h; void *
0x1800046e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046e8  test    rdi, rdi
0x1800046eb  jz      short loc_1800046FE
0x1800046ed  mov     rcx, rdi; hMutex
0x1800046f0  call    cs:__imp_ReleaseMutex
0x1800046f6  test    eax, eax
0x1800046f8  jz      loc_180004853
0x1800046fe  mov     rcx, rbx; hObject
0x180004701  call    cs:__imp_CloseHandle
0x180004707  test    eax, eax
0x180004709  jz      loc_1800047E6
0x18000470f  jmp     loc_1800045E8
0x180004714  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004719  lea     rcx, [r14+28h]; void *
0x18000471d  mov     dword ptr [r14], 1
0x180004724  xor     edx, edx; Val
0x180004726  mov     [r14+8], rbx
0x18000472a  mov     r8d, 108h; Size
0x180004730  movdqu  xmmword ptr [r14+10h], xmm0
0x180004736  call    memset_0
0x18000473b  xor     eax, eax
0x18000473d  lea     rcx, [r14+28h]; this
0x180004741  mov     [r14+20h], rax
0x180004745  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000474a  lea     rbx, [r14+0E8h]
0x180004751  xor     r8d, r8d; Flags
0x180004754  mov     rcx, rbx; lpCriticalSection
0x180004757  xor     edx, edx; dwSpinCount
0x180004759  call    cs:__imp_InitializeCriticalSectionEx
0x18000475f  mov     qword ptr [rbx+28h], 0
0x180004767  mov     qword ptr [rbx+30h], 0
0x18000476f  mov     qword ptr [rbx+38h], 0
0x180004777  mov     qword ptr [rbx+40h], 0
0x18000477f  xor     ebx, ebx
0x180004781  mov     [r15], r14
0x180004784  test    rdi, rdi
0x180004787  jz      short loc_18000479A
0x180004789  mov     rcx, rdi; hMutex
0x18000478c  call    cs:__imp_ReleaseMutex
0x180004792  test    eax, eax
0x180004794  jz      loc_180004865
0x18000479a  test    rbx, rbx
0x18000479d  jz      short loc_1800047AC
0x18000479f  mov     rcx, rbx; hObject
0x1800047a2  call    cs:__imp_CloseHandle
0x1800047a8  test    eax, eax
0x1800047aa  jz      short loc_1800047D4
0x1800047ac  xor     eax, eax
0x1800047ae  mov     rcx, [rbp+180h+var_30]
0x1800047b5  xor     rcx, rsp; StackCookie
0x1800047b8  call    __security_check_cookie
0x1800047bd  mov     rbx, [rsp+280h+arg_10]
0x1800047c5  add     rsp, 260h
0x1800047cc  pop     r15
0x1800047ce  pop     r14
0x1800047d0  pop     rdi
0x1800047d1  pop     rsi
0x1800047d2  pop     rbp
0x1800047d3  retn
0x1800047d4  mov     rcx, [rbp+188h]; this
0x1800047db  mov     edx, 0A0Bh; void *
0x1800047e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047e6  mov     rcx, [rbp+188h]; this
0x1800047ed  mov     edx, 0A0Bh; void *
0x1800047f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047f8  mov     rcx, [rbp+188h]; this
0x1800047ff  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004805  mov     rcx, [rbp+188h]; this
0x18000480c  mov     edx, 0A15h; void *
0x180004811  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004817  mov     rcx, [rbp+188h]; this
0x18000481e  mov     edx, 0A0Bh; void *
0x180004823  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004829  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000482f  mov     rcx, [rbp+188h]; this
0x180004836  mov     edx, 0A0Bh; void *
0x18000483b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004841  mov     rcx, [rbp+188h]; this
0x180004848  mov     edx, 0A0Bh; void *
0x18000484d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004853  mov     rcx, [rbp+188h]; this
0x18000485a  mov     edx, 0A15h; void *
0x18000485f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004865  mov     rcx, [rbp+188h]; this
0x18000486c  mov     edx, 0A15h; void *
0x180004871  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
