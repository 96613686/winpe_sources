# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005488`
- end: `0x180005879`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005b64`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x18000432c`
- `0x180005488`
- `0x180005880`
- `0x180005db8`
- `0x1800066e8`
- `0x1800073c8`
- `0x180008b94`
- `0x180009688`
- `0x180009b0c`
- `0x18000a3bc`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800054ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800054ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005520`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005520`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000578e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000578e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000575b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000575b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057a4`

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
0x180005488  mov     [rsp-8+arg_10], rbx
0x18000548d  push    rbp
0x18000548e  push    rsi
0x18000548f  push    rdi
0x180005490  push    r14
0x180005492  push    r15
0x180005494  lea     rbp, [rsp-160h]
0x18000549c  sub     rsp, 260h
0x1800054a3  mov     rax, cs:__security_cookie
0x1800054aa  xor     rax, rsp
0x1800054ad  mov     [rbp+180h+var_30], rax
0x1800054b4  mov     r15, rdx
0x1800054b7  mov     qword ptr [rdx], 0
0x1800054be  mov     rbx, rcx
0x1800054c1  call    cs:__imp_GetCurrentProcessId
0x1800054c7  mov     r14d, 130h
0x1800054cd  mov     [rsp+280h+var_258], rbx
0x1800054d2  mov     r9d, eax
0x1800054d5  mov     [rsp+280h+var_260], r14d; int
0x1800054da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800054e1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800054e6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800054ea  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800054ef  mov     r9d, 1F0001h; dwDesiredAccess
0x1800054f5  lea     rdx, [rsp+280h+Name]; lpName
0x1800054fa  xor     r8d, r8d; dwFlags
0x1800054fd  xor     ecx, ecx; lpMutexAttributes
0x1800054ff  call    cs:__imp_CreateMutexExW
0x180005505  mov     rbx, rax
0x180005508  test    rax, rax
0x18000550b  jnz     short loc_180005517
0x18000550d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005512  jmp     loc_1800057B0
0x180005517  xor     r8d, r8d; bAlertable
0x18000551a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000551d  mov     rcx, rbx; hHandle
0x180005520  call    cs:__imp_WaitForSingleObjectEx
0x180005526  cmp     eax, 102h
0x18000552b  jz      short loc_18000553D
0x18000552d  test    eax, 0FFFFFF7Fh
0x180005532  jnz     loc_1800057FA
0x180005538  mov     rdi, rbx
0x18000553b  jmp     short loc_18000553F
0x18000553d  xor     edi, edi
0x18000553f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005544  mov     [rsp+280h+hObject], 0
0x18000554d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005552  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005557  mov     esi, eax
0x180005559  test    eax, eax
0x18000555b  jns     short loc_1800055DC
0x18000555d  mov     rcx, [rbp+188h]; this
0x180005564  lea     r8, aWil; "wil"
0x18000556b  mov     r9d, eax; char *
0x18000556e  mov     edx, 66h ; 'f'; void *
0x180005573  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005578  mov     rcx, [rbp+188h]; this
0x18000557f  lea     r8, aWil; "wil"
0x180005586  mov     r9d, esi; char *
0x180005589  mov     edx, 6Fh ; 'o'; void *
0x18000558e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005593  mov     rcx, [rbp+188h]; this
0x18000559a  lea     r8, aWil; "wil"
0x1800055a1  mov     r9d, esi; char *
0x1800055a4  mov     edx, 12Eh; void *
0x1800055a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055ae  test    rdi, rdi
0x1800055b1  jz      short loc_1800055C4
0x1800055b3  mov     rcx, rdi; hMutex
0x1800055b6  call    cs:__imp_ReleaseMutex
0x1800055bc  test    eax, eax
0x1800055be  jz      loc_180005807
0x1800055c4  mov     rcx, rbx; hObject
0x1800055c7  call    cs:__imp_CloseHandle
0x1800055cd  test    eax, eax
0x1800055cf  jz      loc_180005819
0x1800055d5  mov     eax, esi
0x1800055d7  jmp     loc_1800057B0
0x1800055dc  mov     rax, [rsp+280h+hObject]
0x1800055e1  lea     rcx, ds:0[rax*4]
0x1800055e9  test    rcx, rcx
0x1800055ec  jz      short loc_1800055FC
0x1800055ee  mov     [r15], rcx
0x1800055f1  mov     eax, [rcx]
0x1800055f3  inc     eax
0x1800055f5  mov     [rcx], eax
0x1800055f7  jmp     loc_180005786
0x1800055fc  mov     rdx, r14; dwBytes
0x1800055ff  mov     qword ptr [r15], 0
0x180005606  mov     ecx, 8; dwFlags
0x18000560b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005610  mov     r14, rax
0x180005613  test    rax, rax
0x180005616  jnz     short loc_18000563D
0x180005618  mov     rcx, [rbp+188h]; this
0x18000561f  lea     r8, aWil; "wil"
0x180005626  mov     esi, 8007000Eh
0x18000562b  mov     edx, 14Bh; void *
0x180005630  mov     r9d, esi; char *
0x180005633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005638  jmp     loc_1800056CF
0x18000563d  xorps   xmm0, xmm0
0x180005640  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005646  test    r14b, 3
0x18000564a  jnz     loc_18000582B
0x180005650  mov     r9, r14
0x180005653  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180005658  shr     r9, 2; unsigned __int64
0x18000565c  lea     rcx, [rsp+280h+hObject]; this
0x180005661  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005666  mov     esi, eax
0x180005668  test    eax, eax
0x18000566a  jns     loc_180005716
0x180005670  mov     rcx, [rbp+188h]; this
0x180005677  lea     r8, aWil; "wil"
0x18000567e  mov     r9d, eax; char *
0x180005681  mov     edx, 14Eh; void *
0x180005686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000568b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005690  test    rcx, rcx
0x180005693  jz      short loc_1800056A3
0x180005695  call    cs:__imp_CloseHandle
0x18000569b  test    eax, eax
0x18000569d  jz      loc_180005831
0x1800056a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800056a8  test    rcx, rcx
0x1800056ab  jz      short loc_1800056BB
0x1800056ad  call    cs:__imp_CloseHandle
0x1800056b3  test    eax, eax
0x1800056b5  jz      loc_180005843
0x1800056bb  call    cs:__imp_GetProcessHeap
0x1800056c1  mov     r8, r14; lpMem
0x1800056c4  xor     edx, edx; dwFlags
0x1800056c6  mov     rcx, rax; hHeap
0x1800056c9  call    cs:__imp_HeapFree
0x1800056cf  mov     rcx, [rbp+188h]; this
0x1800056d6  lea     r8, aWil; "wil"
0x1800056dd  mov     r9d, esi; char *
0x1800056e0  mov     edx, 137h; void *
0x1800056e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056ea  test    rdi, rdi
0x1800056ed  jz      short loc_180005700
0x1800056ef  mov     rcx, rdi; hMutex
0x1800056f2  call    cs:__imp_ReleaseMutex
0x1800056f8  test    eax, eax
0x1800056fa  jz      loc_180005855
0x180005700  mov     rcx, rbx; hObject
0x180005703  call    cs:__imp_CloseHandle
0x180005709  test    eax, eax
0x18000570b  jz      loc_1800057E8
0x180005711  jmp     loc_1800055D5
0x180005716  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000571b  lea     rcx, [r14+28h]; void *
0x18000571f  mov     dword ptr [r14], 1
0x180005726  xor     edx, edx; Val
0x180005728  mov     [r14+8], rbx
0x18000572c  mov     r8d, 108h; Size
0x180005732  movdqu  xmmword ptr [r14+10h], xmm0
0x180005738  call    memset_0
0x18000573d  xor     eax, eax
0x18000573f  lea     rcx, [r14+28h]; this
0x180005743  mov     [r14+20h], rax
0x180005747  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000574c  lea     rbx, [r14+0E8h]
0x180005753  xor     r8d, r8d; Flags
0x180005756  mov     rcx, rbx; lpCriticalSection
0x180005759  xor     edx, edx; dwSpinCount
0x18000575b  call    cs:__imp_InitializeCriticalSectionEx
0x180005761  mov     qword ptr [rbx+28h], 0
0x180005769  mov     qword ptr [rbx+30h], 0
0x180005771  mov     qword ptr [rbx+38h], 0
0x180005779  mov     qword ptr [rbx+40h], 0
0x180005781  xor     ebx, ebx
0x180005783  mov     [r15], r14
0x180005786  test    rdi, rdi
0x180005789  jz      short loc_18000579C
0x18000578b  mov     rcx, rdi; hMutex
0x18000578e  call    cs:__imp_ReleaseMutex
0x180005794  test    eax, eax
0x180005796  jz      loc_180005867
0x18000579c  test    rbx, rbx
0x18000579f  jz      short loc_1800057AE
0x1800057a1  mov     rcx, rbx; hObject
0x1800057a4  call    cs:__imp_CloseHandle
0x1800057aa  test    eax, eax
0x1800057ac  jz      short loc_1800057D6
0x1800057ae  xor     eax, eax
0x1800057b0  mov     rcx, [rbp+180h+var_30]
0x1800057b7  xor     rcx, rsp; StackCookie
0x1800057ba  call    __security_check_cookie
0x1800057bf  mov     rbx, [rsp+280h+arg_10]
0x1800057c7  add     rsp, 260h
0x1800057ce  pop     r15
0x1800057d0  pop     r14
0x1800057d2  pop     rdi
0x1800057d3  pop     rsi
0x1800057d4  pop     rbp
0x1800057d5  retn
0x1800057d6  mov     rcx, [rbp+188h]; this
0x1800057dd  mov     edx, 0A0Bh; void *
0x1800057e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057e8  mov     rcx, [rbp+188h]; this
0x1800057ef  mov     edx, 0A0Bh; void *
0x1800057f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057fa  mov     rcx, [rbp+188h]; this
0x180005801  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005807  mov     rcx, [rbp+188h]; this
0x18000580e  mov     edx, 0A15h; void *
0x180005813  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005819  mov     rcx, [rbp+188h]; this
0x180005820  mov     edx, 0A0Bh; void *
0x180005825  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000582b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005831  mov     rcx, [rbp+188h]; this
0x180005838  mov     edx, 0A0Bh; void *
0x18000583d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005843  mov     rcx, [rbp+188h]; this
0x18000584a  mov     edx, 0A0Bh; void *
0x18000584f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005855  mov     rcx, [rbp+188h]; this
0x18000585c  mov     edx, 0A15h; void *
0x180005861  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005867  mov     rcx, [rbp+188h]; this
0x18000586e  mov     edx, 0A15h; void *
0x180005873  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
