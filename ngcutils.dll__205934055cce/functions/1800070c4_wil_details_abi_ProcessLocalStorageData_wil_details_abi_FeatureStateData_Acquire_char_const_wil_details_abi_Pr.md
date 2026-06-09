# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800070c4`
- end: `0x1800074c1`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800077b4`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x180006224`
- `0x1800070c4`
- `0x1800074c8`
- `0x180007a5c`
- `0x180008388`
- `0x180008e04`
- `0x18000a5b4`
- `0x18000b0c8`
- `0x18000b54c`
- `0x18000be1c`
- `0x18000be2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000713b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000713b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000732e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000732e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000715c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000715c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007397`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800070fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800070fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000733f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000733f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073e0`

## string_xrefs

- `0x18000743d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x1800070c4  mov     [rsp-8+arg_10], rbx
0x1800070c9  push    rbp
0x1800070ca  push    rsi
0x1800070cb  push    rdi
0x1800070cc  push    r14
0x1800070ce  push    r15
0x1800070d0  lea     rbp, [rsp-160h]
0x1800070d8  sub     rsp, 260h
0x1800070df  mov     rax, cs:__security_cookie
0x1800070e6  xor     rax, rsp
0x1800070e9  mov     [rbp+180h+var_30], rax
0x1800070f0  mov     r15, rdx
0x1800070f3  mov     qword ptr [rdx], 0
0x1800070fa  mov     rbx, rcx
0x1800070fd  call    cs:__imp_GetCurrentProcessId
0x180007103  mov     r14d, 130h
0x180007109  mov     [rsp+280h+var_258], rbx
0x18000710e  mov     r9d, eax
0x180007111  mov     [rsp+280h+var_260], r14d; int
0x180007116  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000711d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007122  lea     edx, [r14-2Ch]; unsigned __int64
0x180007126  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000712b  mov     r9d, 1F0001h; dwDesiredAccess
0x180007131  lea     rdx, [rsp+280h+Name]; lpName
0x180007136  xor     r8d, r8d; dwFlags
0x180007139  xor     ecx, ecx; lpMutexAttributes
0x18000713b  call    cs:__imp_CreateMutexExW
0x180007141  mov     rbx, rax
0x180007144  test    rax, rax
0x180007147  jnz     short loc_180007153
0x180007149  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000714e  jmp     loc_1800073EC
0x180007153  xor     r8d, r8d; bAlertable
0x180007156  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007159  mov     rcx, rbx; hHandle
0x18000715c  call    cs:__imp_WaitForSingleObjectEx
0x180007162  cmp     eax, 102h
0x180007167  jz      short loc_180007179
0x180007169  test    eax, 0FFFFFF7Fh
0x18000716e  jnz     loc_180007436
0x180007174  mov     rdi, rbx
0x180007177  jmp     short loc_18000717B
0x180007179  xor     edi, edi
0x18000717b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007180  mov     [rsp+280h+hObject], 0
0x180007189  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000718e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007193  mov     esi, eax
0x180007195  test    eax, eax
0x180007197  jns     short loc_180007218
0x180007199  mov     rcx, [rbp+188h]; this
0x1800071a0  lea     r8, aWil; "wil"
0x1800071a7  mov     r9d, eax; char *
0x1800071aa  mov     edx, 66h ; 'f'; void *
0x1800071af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071b4  mov     rcx, [rbp+188h]; this
0x1800071bb  lea     r8, aWil; "wil"
0x1800071c2  mov     r9d, esi; char *
0x1800071c5  mov     edx, 6Fh ; 'o'; void *
0x1800071ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071cf  mov     rcx, [rbp+188h]; this
0x1800071d6  lea     r8, aWil; "wil"
0x1800071dd  mov     r9d, esi; char *
0x1800071e0  mov     edx, 12Eh; void *
0x1800071e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071ea  test    rdi, rdi
0x1800071ed  jz      short loc_180007200
0x1800071ef  mov     rcx, rdi; hMutex
0x1800071f2  call    cs:__imp_ReleaseMutex
0x1800071f8  test    eax, eax
0x1800071fa  jz      loc_18000744F
0x180007200  mov     rcx, rbx; hObject
0x180007203  call    cs:__imp_CloseHandle
0x180007209  test    eax, eax
0x18000720b  jz      loc_180007461
0x180007211  mov     eax, esi
0x180007213  jmp     loc_1800073EC
0x180007218  mov     rax, [rsp+280h+hObject]
0x18000721d  lea     rcx, ds:0[rax*4]
0x180007225  test    rcx, rcx
0x180007228  jz      short loc_180007238
0x18000722a  mov     [r15], rcx
0x18000722d  mov     eax, [rcx]
0x18000722f  inc     eax
0x180007231  mov     [rcx], eax
0x180007233  jmp     loc_1800073C2
0x180007238  mov     rdx, r14; dwBytes
0x18000723b  mov     qword ptr [r15], 0
0x180007242  mov     ecx, 8; dwFlags
0x180007247  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000724c  mov     r14, rax
0x18000724f  test    rax, rax
0x180007252  jnz     short loc_180007279
0x180007254  mov     rcx, [rbp+188h]; this
0x18000725b  lea     r8, aWil; "wil"
0x180007262  mov     esi, 8007000Eh
0x180007267  mov     edx, 14Bh; void *
0x18000726c  mov     r9d, esi; char *
0x18000726f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007274  jmp     loc_18000730B
0x180007279  xorps   xmm0, xmm0
0x18000727c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180007282  test    r14b, 3
0x180007286  jnz     loc_180007473
0x18000728c  mov     r9, r14
0x18000728f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007294  shr     r9, 2; unsigned __int64
0x180007298  lea     rcx, [rsp+280h+hObject]; this
0x18000729d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800072a2  mov     esi, eax
0x1800072a4  test    eax, eax
0x1800072a6  jns     loc_180007352
0x1800072ac  mov     rcx, [rbp+188h]; this
0x1800072b3  lea     r8, aWil; "wil"
0x1800072ba  mov     r9d, eax; char *
0x1800072bd  mov     edx, 14Eh; void *
0x1800072c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072c7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800072cc  test    rcx, rcx
0x1800072cf  jz      short loc_1800072DF
0x1800072d1  call    cs:__imp_CloseHandle
0x1800072d7  test    eax, eax
0x1800072d9  jz      loc_180007479
0x1800072df  mov     rcx, [rsp+280h+hObject]; hObject
0x1800072e4  test    rcx, rcx
0x1800072e7  jz      short loc_1800072F7
0x1800072e9  call    cs:__imp_CloseHandle
0x1800072ef  test    eax, eax
0x1800072f1  jz      loc_18000748B
0x1800072f7  call    cs:__imp_GetProcessHeap
0x1800072fd  mov     r8, r14; lpMem
0x180007300  xor     edx, edx; dwFlags
0x180007302  mov     rcx, rax; hHeap
0x180007305  call    cs:__imp_HeapFree
0x18000730b  mov     rcx, [rbp+188h]; this
0x180007312  lea     r8, aWil; "wil"
0x180007319  mov     r9d, esi; char *
0x18000731c  mov     edx, 137h; void *
0x180007321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007326  test    rdi, rdi
0x180007329  jz      short loc_18000733C
0x18000732b  mov     rcx, rdi; hMutex
0x18000732e  call    cs:__imp_ReleaseMutex
0x180007334  test    eax, eax
0x180007336  jz      loc_18000749D
0x18000733c  mov     rcx, rbx; hObject
0x18000733f  call    cs:__imp_CloseHandle
0x180007345  test    eax, eax
0x180007347  jz      loc_180007424
0x18000734d  jmp     loc_180007211
0x180007352  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007357  lea     rcx, [r14+28h]; void *
0x18000735b  mov     dword ptr [r14], 1
0x180007362  xor     edx, edx; Val
0x180007364  mov     [r14+8], rbx
0x180007368  mov     r8d, 108h; Size
0x18000736e  movdqu  xmmword ptr [r14+10h], xmm0
0x180007374  call    memset_0
0x180007379  xor     eax, eax
0x18000737b  lea     rcx, [r14+28h]; this
0x18000737f  mov     [r14+20h], rax
0x180007383  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007388  lea     rbx, [r14+0E8h]
0x18000738f  xor     r8d, r8d; Flags
0x180007392  mov     rcx, rbx; lpCriticalSection
0x180007395  xor     edx, edx; dwSpinCount
0x180007397  call    cs:__imp_InitializeCriticalSectionEx
0x18000739d  mov     qword ptr [rbx+28h], 0
0x1800073a5  mov     qword ptr [rbx+30h], 0
0x1800073ad  mov     qword ptr [rbx+38h], 0
0x1800073b5  mov     qword ptr [rbx+40h], 0
0x1800073bd  xor     ebx, ebx
0x1800073bf  mov     [r15], r14
0x1800073c2  test    rdi, rdi
0x1800073c5  jz      short loc_1800073D8
0x1800073c7  mov     rcx, rdi; hMutex
0x1800073ca  call    cs:__imp_ReleaseMutex
0x1800073d0  test    eax, eax
0x1800073d2  jz      loc_1800074AF
0x1800073d8  test    rbx, rbx
0x1800073db  jz      short loc_1800073EA
0x1800073dd  mov     rcx, rbx; hObject
0x1800073e0  call    cs:__imp_CloseHandle
0x1800073e6  test    eax, eax
0x1800073e8  jz      short loc_180007412
0x1800073ea  xor     eax, eax
0x1800073ec  mov     rcx, [rbp+180h+var_30]
0x1800073f3  xor     rcx, rsp; StackCookie
0x1800073f6  call    __security_check_cookie
0x1800073fb  mov     rbx, [rsp+280h+arg_10]
0x180007403  add     rsp, 260h
0x18000740a  pop     r15
0x18000740c  pop     r14
0x18000740e  pop     rdi
0x18000740f  pop     rsi
0x180007410  pop     rbp
0x180007411  retn
0x180007412  mov     rcx, [rbp+188h]; this
0x180007419  mov     edx, 0A0Bh; void *
0x18000741e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007424  mov     rcx, [rbp+188h]; this
0x18000742b  mov     edx, 0A0Bh; void *
0x180007430  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007436  mov     rcx, [rbp+188h]; this
0x18000743d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007444  mov     edx, 0E01h; void *
0x180007449  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000744f  mov     rcx, [rbp+188h]; this
0x180007456  mov     edx, 0A15h; void *
0x18000745b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007461  mov     rcx, [rbp+188h]; this
0x180007468  mov     edx, 0A0Bh; void *
0x18000746d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007473  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007479  mov     rcx, [rbp+188h]; this
0x180007480  mov     edx, 0A0Bh; void *
0x180007485  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000748b  mov     rcx, [rbp+188h]; this
0x180007492  mov     edx, 0A0Bh; void *
0x180007497  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000749d  mov     rcx, [rbp+188h]; this
0x1800074a4  mov     edx, 0A15h; void *
0x1800074a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074af  mov     rcx, [rbp+188h]; this
0x1800074b6  mov     edx, 0A15h; void *
0x1800074bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
