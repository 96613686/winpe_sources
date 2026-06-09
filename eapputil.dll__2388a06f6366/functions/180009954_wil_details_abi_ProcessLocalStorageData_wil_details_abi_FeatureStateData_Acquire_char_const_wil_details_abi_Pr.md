# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009954`
- end: `0x180009d51`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009d58`

## callees

- `0x1800021d0`
- `0x180002b78`
- `0x180004d74`
- `0x180005218`
- `0x1800058a8`
- `0x1800064cc`
- `0x180006ba4`
- `0x180007594`
- `0x18000766c`
- `0x180007a2c`
- `0x180007a3c`
- `0x180009190`
- `0x180009954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009c27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009c27`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800099cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800099cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800099ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800099ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000998d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000998d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c70`

## string_xrefs

- `0x180009ccd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180009954  mov     [rsp-8+arg_10], rbx
0x180009959  push    rbp
0x18000995a  push    rsi
0x18000995b  push    rdi
0x18000995c  push    r14
0x18000995e  push    r15
0x180009960  lea     rbp, [rsp-160h]
0x180009968  sub     rsp, 260h
0x18000996f  mov     rax, cs:__security_cookie
0x180009976  xor     rax, rsp
0x180009979  mov     [rbp+180h+var_30], rax
0x180009980  mov     r15, rdx
0x180009983  mov     qword ptr [rdx], 0
0x18000998a  mov     rbx, rcx
0x18000998d  call    cs:__imp_GetCurrentProcessId
0x180009993  mov     r14d, 130h
0x180009999  mov     [rsp+280h+var_258], rbx
0x18000999e  mov     r9d, eax
0x1800099a1  mov     [rsp+280h+var_260], r14d; int
0x1800099a6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800099ad  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800099b2  lea     edx, [r14-2Ch]; unsigned __int64
0x1800099b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800099bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800099c1  lea     rdx, [rsp+280h+Name]; lpName
0x1800099c6  xor     r8d, r8d; dwFlags
0x1800099c9  xor     ecx, ecx; lpMutexAttributes
0x1800099cb  call    cs:__imp_CreateMutexExW
0x1800099d1  mov     rbx, rax
0x1800099d4  test    rax, rax
0x1800099d7  jnz     short loc_1800099E3
0x1800099d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800099de  jmp     loc_180009C7C
0x1800099e3  xor     r8d, r8d; bAlertable
0x1800099e6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800099e9  mov     rcx, rbx; hHandle
0x1800099ec  call    cs:__imp_WaitForSingleObjectEx
0x1800099f2  cmp     eax, 102h
0x1800099f7  jz      short loc_180009A09
0x1800099f9  test    eax, 0FFFFFF7Fh
0x1800099fe  jnz     loc_180009CC6
0x180009a04  mov     rdi, rbx
0x180009a07  jmp     short loc_180009A0B
0x180009a09  xor     edi, edi
0x180009a0b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009a10  mov     [rsp+280h+hObject], 0
0x180009a19  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009a1e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009a23  mov     esi, eax
0x180009a25  test    eax, eax
0x180009a27  jns     short loc_180009AA8
0x180009a29  mov     rcx, [rbp+188h]; this
0x180009a30  lea     r8, aWil; "wil"
0x180009a37  mov     r9d, eax; char *
0x180009a3a  mov     edx, 66h ; 'f'; void *
0x180009a3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a44  mov     rcx, [rbp+188h]; this
0x180009a4b  lea     r8, aWil; "wil"
0x180009a52  mov     r9d, esi; char *
0x180009a55  mov     edx, 6Fh ; 'o'; void *
0x180009a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a5f  mov     rcx, [rbp+188h]; this
0x180009a66  lea     r8, aWil; "wil"
0x180009a6d  mov     r9d, esi; char *
0x180009a70  mov     edx, 12Eh; void *
0x180009a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a7a  test    rdi, rdi
0x180009a7d  jz      short loc_180009A90
0x180009a7f  mov     rcx, rdi; hMutex
0x180009a82  call    cs:__imp_ReleaseMutex
0x180009a88  test    eax, eax
0x180009a8a  jz      loc_180009CDF
0x180009a90  mov     rcx, rbx; hObject
0x180009a93  call    cs:__imp_CloseHandle
0x180009a99  test    eax, eax
0x180009a9b  jz      loc_180009CF1
0x180009aa1  mov     eax, esi
0x180009aa3  jmp     loc_180009C7C
0x180009aa8  mov     rax, [rsp+280h+hObject]
0x180009aad  lea     rcx, ds:0[rax*4]
0x180009ab5  test    rcx, rcx
0x180009ab8  jz      short loc_180009AC8
0x180009aba  mov     [r15], rcx
0x180009abd  mov     eax, [rcx]
0x180009abf  inc     eax
0x180009ac1  mov     [rcx], eax
0x180009ac3  jmp     loc_180009C52
0x180009ac8  mov     rdx, r14; dwBytes
0x180009acb  mov     qword ptr [r15], 0
0x180009ad2  mov     ecx, 8; dwFlags
0x180009ad7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009adc  mov     r14, rax
0x180009adf  test    rax, rax
0x180009ae2  jnz     short loc_180009B09
0x180009ae4  mov     rcx, [rbp+188h]; this
0x180009aeb  lea     r8, aWil; "wil"
0x180009af2  mov     esi, 8007000Eh
0x180009af7  mov     edx, 14Bh; void *
0x180009afc  mov     r9d, esi; char *
0x180009aff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b04  jmp     loc_180009B9B
0x180009b09  xorps   xmm0, xmm0
0x180009b0c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009b12  test    r14b, 3
0x180009b16  jnz     loc_180009D03
0x180009b1c  mov     r9, r14
0x180009b1f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009b24  shr     r9, 2; unsigned __int64
0x180009b28  lea     rcx, [rsp+280h+hObject]; this
0x180009b2d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009b32  mov     esi, eax
0x180009b34  test    eax, eax
0x180009b36  jns     loc_180009BE2
0x180009b3c  mov     rcx, [rbp+188h]; this
0x180009b43  lea     r8, aWil; "wil"
0x180009b4a  mov     r9d, eax; char *
0x180009b4d  mov     edx, 14Eh; void *
0x180009b52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b57  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009b5c  test    rcx, rcx
0x180009b5f  jz      short loc_180009B6F
0x180009b61  call    cs:__imp_CloseHandle
0x180009b67  test    eax, eax
0x180009b69  jz      loc_180009D09
0x180009b6f  mov     rcx, [rsp+280h+hObject]; hObject
0x180009b74  test    rcx, rcx
0x180009b77  jz      short loc_180009B87
0x180009b79  call    cs:__imp_CloseHandle
0x180009b7f  test    eax, eax
0x180009b81  jz      loc_180009D1B
0x180009b87  call    cs:__imp_GetProcessHeap
0x180009b8d  mov     r8, r14; lpMem
0x180009b90  xor     edx, edx; dwFlags
0x180009b92  mov     rcx, rax; hHeap
0x180009b95  call    cs:__imp_HeapFree
0x180009b9b  mov     rcx, [rbp+188h]; this
0x180009ba2  lea     r8, aWil; "wil"
0x180009ba9  mov     r9d, esi; char *
0x180009bac  mov     edx, 137h; void *
0x180009bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bb6  test    rdi, rdi
0x180009bb9  jz      short loc_180009BCC
0x180009bbb  mov     rcx, rdi; hMutex
0x180009bbe  call    cs:__imp_ReleaseMutex
0x180009bc4  test    eax, eax
0x180009bc6  jz      loc_180009D2D
0x180009bcc  mov     rcx, rbx; hObject
0x180009bcf  call    cs:__imp_CloseHandle
0x180009bd5  test    eax, eax
0x180009bd7  jz      loc_180009CB4
0x180009bdd  jmp     loc_180009AA1
0x180009be2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009be7  lea     rcx, [r14+28h]; void *
0x180009beb  mov     dword ptr [r14], 1
0x180009bf2  xor     edx, edx; Val
0x180009bf4  mov     [r14+8], rbx
0x180009bf8  mov     r8d, 108h; Size
0x180009bfe  movdqu  xmmword ptr [r14+10h], xmm0
0x180009c04  call    memset_0
0x180009c09  xor     eax, eax
0x180009c0b  lea     rcx, [r14+28h]; this
0x180009c0f  mov     [r14+20h], rax
0x180009c13  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009c18  lea     rbx, [r14+0E8h]
0x180009c1f  xor     r8d, r8d; Flags
0x180009c22  mov     rcx, rbx; lpCriticalSection
0x180009c25  xor     edx, edx; dwSpinCount
0x180009c27  call    cs:__imp_InitializeCriticalSectionEx
0x180009c2d  mov     qword ptr [rbx+28h], 0
0x180009c35  mov     qword ptr [rbx+30h], 0
0x180009c3d  mov     qword ptr [rbx+38h], 0
0x180009c45  mov     qword ptr [rbx+40h], 0
0x180009c4d  xor     ebx, ebx
0x180009c4f  mov     [r15], r14
0x180009c52  test    rdi, rdi
0x180009c55  jz      short loc_180009C68
0x180009c57  mov     rcx, rdi; hMutex
0x180009c5a  call    cs:__imp_ReleaseMutex
0x180009c60  test    eax, eax
0x180009c62  jz      loc_180009D3F
0x180009c68  test    rbx, rbx
0x180009c6b  jz      short loc_180009C7A
0x180009c6d  mov     rcx, rbx; hObject
0x180009c70  call    cs:__imp_CloseHandle
0x180009c76  test    eax, eax
0x180009c78  jz      short loc_180009CA2
0x180009c7a  xor     eax, eax
0x180009c7c  mov     rcx, [rbp+180h+var_30]
0x180009c83  xor     rcx, rsp; StackCookie
0x180009c86  call    __security_check_cookie
0x180009c8b  mov     rbx, [rsp+280h+arg_10]
0x180009c93  add     rsp, 260h
0x180009c9a  pop     r15
0x180009c9c  pop     r14
0x180009c9e  pop     rdi
0x180009c9f  pop     rsi
0x180009ca0  pop     rbp
0x180009ca1  retn
0x180009ca2  mov     rcx, [rbp+188h]; this
0x180009ca9  mov     edx, 0A0Bh; void *
0x180009cae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cb4  mov     rcx, [rbp+188h]; this
0x180009cbb  mov     edx, 0A0Bh; void *
0x180009cc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cc6  mov     rcx, [rbp+188h]; this
0x180009ccd  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009cd4  mov     edx, 0E01h; void *
0x180009cd9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009cdf  mov     rcx, [rbp+188h]; this
0x180009ce6  mov     edx, 0A15h; void *
0x180009ceb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cf1  mov     rcx, [rbp+188h]; this
0x180009cf8  mov     edx, 0A0Bh; void *
0x180009cfd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d03  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009d09  mov     rcx, [rbp+188h]; this
0x180009d10  mov     edx, 0A0Bh; void *
0x180009d15  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d1b  mov     rcx, [rbp+188h]; this
0x180009d22  mov     edx, 0A0Bh; void *
0x180009d27  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d2d  mov     rcx, [rbp+188h]; this
0x180009d34  mov     edx, 0A15h; void *
0x180009d39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d3f  mov     rcx, [rbp+188h]; this
0x180009d46  mov     edx, 0A15h; void *
0x180009d4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
