# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003ba0`
- end: `0x180003f72`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000419c`

## callees

- `0x1800031a4`
- `0x180003588`
- `0x180003ba0`
- `0x180003f78`
- `0x180004318`
- `0x180004c70`
- `0x180005910`
- `0x180006ca8`
- `0x1800071bc`
- `0x180007608`
- `0x180007e10`
- `0x180014dce`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bd9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003e61`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003e61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ccb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ccb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c44`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c44`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c1d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c1d`

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
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x180003ba0  mov     [rsp-8+arg_10], rbx
0x180003ba5  push    rbp
0x180003ba6  push    rsi
0x180003ba7  push    rdi
0x180003ba8  push    r14
0x180003baa  push    r15
0x180003bac  lea     rbp, [rsp-160h]
0x180003bb4  sub     rsp, 260h
0x180003bbb  mov     rax, cs:__security_cookie
0x180003bc2  xor     rax, rsp
0x180003bc5  mov     [rbp+180h+var_30], rax
0x180003bcc  mov     r15, rdx
0x180003bcf  mov     qword ptr [rdx], 0
0x180003bd6  mov     rbx, rcx
0x180003bd9  call    cs:__imp_GetCurrentProcessId
0x180003be0  nop     dword ptr [rax+rax+00h]
0x180003be5  mov     r14d, 130h
0x180003beb  mov     [rsp+280h+var_258], rbx
0x180003bf0  mov     r9d, eax
0x180003bf3  mov     [rsp+280h+var_260], r14d; int
0x180003bf8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003bff  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c04  lea     edx, [r14-2Ch]; unsigned __int64
0x180003c08  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c0d  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c13  lea     rdx, [rsp+280h+Name]; lpName
0x180003c18  xor     r8d, r8d; dwFlags
0x180003c1b  xor     ecx, ecx; lpMutexAttributes
0x180003c1d  call    cs:__imp_CreateMutexExW
0x180003c24  nop     dword ptr [rax+rax+00h]
0x180003c29  mov     rbx, rax
0x180003c2c  test    rax, rax
0x180003c2f  jnz     short loc_180003C3B
0x180003c31  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c36  jmp     loc_180003ED2
0x180003c3b  xor     r8d, r8d; bAlertable
0x180003c3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c41  mov     rcx, rbx; hHandle
0x180003c44  call    cs:__imp_WaitForSingleObjectEx
0x180003c4b  nop     dword ptr [rax+rax+00h]
0x180003c50  cmp     eax, 102h
0x180003c55  jz      short loc_180003C67
0x180003c57  test    eax, 0FFFFFF7Fh
0x180003c5c  jnz     loc_180003F1D
0x180003c62  mov     rdi, rbx
0x180003c65  jmp     short loc_180003C69
0x180003c67  xor     edi, edi
0x180003c69  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180003c6e  mov     [rsp+280h+var_250], 0
0x180003c77  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c7c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c81  mov     esi, eax
0x180003c83  test    eax, eax
0x180003c85  jns     short loc_180003CFD
0x180003c87  mov     rcx, [rbp+188h]; this
0x180003c8e  mov     r9d, eax; char *
0x180003c91  mov     edx, 66h ; 'f'; void *
0x180003c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c9b  mov     rcx, [rbp+188h]; this
0x180003ca2  mov     r9d, esi; char *
0x180003ca5  mov     edx, 6Fh ; 'o'; void *
0x180003caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003caf  mov     rcx, [rbp+188h]; this
0x180003cb6  mov     r9d, esi; char *
0x180003cb9  mov     edx, 12Eh; void *
0x180003cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cc3  test    rdi, rdi
0x180003cc6  jz      short loc_180003CDF
0x180003cc8  mov     rcx, rdi; hMutex
0x180003ccb  call    cs:__imp_ReleaseMutex
0x180003cd2  nop     dword ptr [rax+rax+00h]
0x180003cd7  test    eax, eax
0x180003cd9  jz      loc_180003F2A
0x180003cdf  mov     rcx, rbx; hObject
0x180003ce2  call    cs:__imp_CloseHandle
0x180003ce9  nop     dword ptr [rax+rax+00h]
0x180003cee  test    eax, eax
0x180003cf0  jz      loc_180003F3C
0x180003cf6  mov     eax, esi
0x180003cf8  jmp     loc_180003ED2
0x180003cfd  mov     rax, [rsp+280h+var_250]
0x180003d02  lea     rcx, ds:0[rax*4]
0x180003d0a  test    rcx, rcx
0x180003d0d  jz      short loc_180003D1D
0x180003d0f  mov     [r15], rcx
0x180003d12  mov     eax, [rcx]
0x180003d14  inc     eax
0x180003d16  mov     [rcx], eax
0x180003d18  jmp     loc_180003E9C
0x180003d1d  mov     rdx, r14; dwBytes
0x180003d20  mov     qword ptr [r15], 0
0x180003d27  mov     ecx, 8; dwFlags
0x180003d2c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d31  mov     r14, rax
0x180003d34  test    rax, rax
0x180003d37  jnz     short loc_180003D54
0x180003d39  mov     rcx, [rbp+188h]; this
0x180003d40  mov     esi, 8007000Eh
0x180003d45  mov     r9d, esi; char *
0x180003d48  mov     edx, 14Bh; void *
0x180003d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d52  jmp     short loc_180003DB7
0x180003d54  xorps   xmm0, xmm0
0x180003d57  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d5c  mov     r8, r14; void *
0x180003d5f  lea     rcx, [rsp+280h+var_250]; this
0x180003d64  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180003d6a  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003d6f  mov     esi, eax
0x180003d71  test    eax, eax
0x180003d73  jns     loc_180003E03
0x180003d79  mov     rcx, [rbp+188h]; this
0x180003d80  mov     r9d, eax; char *
0x180003d83  mov     edx, 14Eh; void *
0x180003d88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d8d  lea     rcx, [rsp+280h+var_250]; this
0x180003d92  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003d97  call    cs:__imp_GetProcessHeap
0x180003d9e  nop     dword ptr [rax+rax+00h]
0x180003da3  mov     r8, r14; lpMem
0x180003da6  xor     edx, edx; dwFlags
0x180003da8  mov     rcx, rax; hHeap
0x180003dab  call    cs:__imp_HeapFree
0x180003db2  nop     dword ptr [rax+rax+00h]
0x180003db7  mov     rcx, [rbp+188h]; this
0x180003dbe  mov     r9d, esi; char *
0x180003dc1  mov     edx, 137h; void *
0x180003dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dcb  test    rdi, rdi
0x180003dce  jz      short loc_180003DE7
0x180003dd0  mov     rcx, rdi; hMutex
0x180003dd3  call    cs:__imp_ReleaseMutex
0x180003dda  nop     dword ptr [rax+rax+00h]
0x180003ddf  test    eax, eax
0x180003de1  jz      loc_180003F4E
0x180003de7  mov     rcx, rbx; hObject
0x180003dea  call    cs:__imp_CloseHandle
0x180003df1  nop     dword ptr [rax+rax+00h]
0x180003df6  test    eax, eax
0x180003df8  jz      loc_180003F0B
0x180003dfe  jmp     loc_180003CF6
0x180003e03  mov     rax, [rsp+280h+var_250]
0x180003e08  lea     rcx, [r14+28h]; void *
0x180003e0c  mov     [r14+10h], rax
0x180003e10  xor     edx, edx; Val
0x180003e12  mov     rax, [rsp+280h+var_250+8]
0x180003e17  mov     r8d, 108h; Size
0x180003e1d  mov     [r14+18h], rax
0x180003e21  mov     dword ptr [r14], 1
0x180003e28  mov     [r14+8], rbx
0x180003e2c  mov     [rsp+280h+var_250], 0
0x180003e35  mov     [rsp+280h+var_250+8], 0
0x180003e3e  call    memset_0
0x180003e43  xor     eax, eax
0x180003e45  lea     rcx, [r14+28h]; this
0x180003e49  mov     [r14+20h], rax
0x180003e4d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003e52  lea     rbx, [r14+0E8h]
0x180003e59  xor     r8d, r8d; Flags
0x180003e5c  mov     rcx, rbx; lpCriticalSection
0x180003e5f  xor     edx, edx; dwSpinCount
0x180003e61  call    cs:__imp_InitializeCriticalSectionEx
0x180003e68  nop     dword ptr [rax+rax+00h]
0x180003e6d  mov     qword ptr [rbx+28h], 0
0x180003e75  lea     rcx, [rsp+280h+var_250]; this
0x180003e7a  mov     qword ptr [rbx+30h], 0
0x180003e82  mov     qword ptr [rbx+38h], 0
0x180003e8a  mov     qword ptr [rbx+40h], 0
0x180003e92  mov     [r15], r14
0x180003e95  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003e9a  xor     ebx, ebx
0x180003e9c  test    rdi, rdi
0x180003e9f  jz      short loc_180003EB8
0x180003ea1  mov     rcx, rdi; hMutex
0x180003ea4  call    cs:__imp_ReleaseMutex
0x180003eab  nop     dword ptr [rax+rax+00h]
0x180003eb0  test    eax, eax
0x180003eb2  jz      loc_180003F60
0x180003eb8  test    rbx, rbx
0x180003ebb  jz      short loc_180003ED0
0x180003ebd  mov     rcx, rbx; hObject
0x180003ec0  call    cs:__imp_CloseHandle
0x180003ec7  nop     dword ptr [rax+rax+00h]
0x180003ecc  test    eax, eax
0x180003ece  jz      short loc_180003EF9
0x180003ed0  xor     eax, eax
0x180003ed2  mov     rcx, [rbp+180h+var_30]
0x180003ed9  xor     rcx, rsp; StackCookie
0x180003edc  call    __security_check_cookie
0x180003ee1  mov     rbx, [rsp+280h+arg_10]
0x180003ee9  add     rsp, 260h
0x180003ef0  pop     r15
0x180003ef2  pop     r14
0x180003ef4  pop     rdi
0x180003ef5  pop     rsi
0x180003ef6  pop     rbp
0x180003ef7  retn
0x180003ef9  mov     rcx, [rbp+188h]; this
0x180003f00  mov     edx, 0A0Bh; void *
0x180003f05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f0b  mov     rcx, [rbp+188h]; this
0x180003f12  mov     edx, 0A0Bh; void *
0x180003f17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f1d  mov     rcx, [rbp+188h]; this
0x180003f24  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f2a  mov     rcx, [rbp+188h]; this
0x180003f31  mov     edx, 0A15h; void *
0x180003f36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f3c  mov     rcx, [rbp+188h]; this
0x180003f43  mov     edx, 0A0Bh; void *
0x180003f48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f4e  mov     rcx, [rbp+188h]; this
0x180003f55  mov     edx, 0A15h; void *
0x180003f5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f60  mov     rcx, [rbp+188h]; this
0x180003f67  mov     edx, 0A15h; void *
0x180003f6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
