# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003bf8`
- end: `0x180003fe9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005400`

## callees

- `0x180002c40`
- `0x180003bf8`
- `0x180004bb4`
- `0x180005654`
- `0x180006014`
- `0x1800075e4`
- `0x1800099f8`
- `0x180009ff4`
- `0x18000a47c`
- `0x18000b3f4`
- `0x18000b404`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180003ecb`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180003ecb`
- `KERNEL32!ReleaseMutex` at `0x180003d26`
- `KERNEL32!ReleaseMutex` at `0x180003e62`
- `KERNEL32!ReleaseMutex` at `0x180003efe`
- `KERNEL32!ReleaseMutex` at `0x180003d26`
- `KERNEL32!ReleaseMutex` at `0x180003e62`
- `KERNEL32!ReleaseMutex` at `0x180003efe`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003c90`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003c90`
- `KERNEL32!CloseHandle` at `0x180003d37`
- `KERNEL32!CloseHandle` at `0x180003e05`
- `KERNEL32!CloseHandle` at `0x180003e1d`
- `KERNEL32!CloseHandle` at `0x180003e73`
- `KERNEL32!CloseHandle` at `0x180003f14`
- `KERNEL32!CloseHandle` at `0x180003d37`
- `KERNEL32!CloseHandle` at `0x180003e05`
- `KERNEL32!CloseHandle` at `0x180003e1d`
- `KERNEL32!CloseHandle` at `0x180003e73`
- `KERNEL32!CloseHandle` at `0x180003f14`
- `KERNEL32!CreateMutexExW` at `0x180003c6f`
- `KERNEL32!CreateMutexExW` at `0x180003c6f`
- `KERNEL32!GetCurrentProcessId` at `0x180003c31`
- `KERNEL32!GetCurrentProcessId` at `0x180003c31`
- `KERNEL32!GetProcessHeap` at `0x180003e2b`
- `KERNEL32!GetProcessHeap` at `0x180003e2b`
- `KERNEL32!HeapFree` at `0x180003e39`
- `KERNEL32!HeapFree` at `0x180003e39`

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
0x180003bf8  mov     [rsp-8+arg_10], rbx
0x180003bfd  push    rbp
0x180003bfe  push    rsi
0x180003bff  push    rdi
0x180003c00  push    r14
0x180003c02  push    r15
0x180003c04  lea     rbp, [rsp-160h]
0x180003c0c  sub     rsp, 260h
0x180003c13  mov     rax, cs:__security_cookie
0x180003c1a  xor     rax, rsp
0x180003c1d  mov     [rbp+180h+var_30], rax
0x180003c24  mov     r15, rdx
0x180003c27  mov     qword ptr [rdx], 0
0x180003c2e  mov     rbx, rcx
0x180003c31  call    cs:__imp_GetCurrentProcessId
0x180003c37  mov     r14d, 130h
0x180003c3d  mov     [rsp+280h+var_258], rbx
0x180003c42  mov     r9d, eax
0x180003c45  mov     [rsp+280h+var_260], r14d; int
0x180003c4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c51  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c56  lea     edx, [r14-2Ch]; unsigned __int64
0x180003c5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c5f  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c65  lea     rdx, [rsp+280h+Name]; lpName
0x180003c6a  xor     r8d, r8d; dwFlags
0x180003c6d  xor     ecx, ecx; lpMutexAttributes
0x180003c6f  call    cs:__imp_CreateMutexExW
0x180003c75  mov     rbx, rax
0x180003c78  test    rax, rax
0x180003c7b  jnz     short loc_180003C87
0x180003c7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c82  jmp     loc_180003F20
0x180003c87  xor     r8d, r8d; bAlertable
0x180003c8a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c8d  mov     rcx, rbx; hHandle
0x180003c90  call    cs:__imp_WaitForSingleObjectEx
0x180003c96  cmp     eax, 102h
0x180003c9b  jz      short loc_180003CAD
0x180003c9d  test    eax, 0FFFFFF7Fh
0x180003ca2  jnz     loc_180003F6A
0x180003ca8  mov     rdi, rbx
0x180003cab  jmp     short loc_180003CAF
0x180003cad  xor     edi, edi
0x180003caf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003cb4  mov     [rsp+280h+hObject], 0
0x180003cbd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003cc2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003cc7  mov     esi, eax
0x180003cc9  test    eax, eax
0x180003ccb  jns     short loc_180003D4C
0x180003ccd  mov     rcx, [rbp+188h]; this
0x180003cd4  lea     r8, aWil; "wil"
0x180003cdb  mov     r9d, eax; char *
0x180003cde  mov     edx, 66h ; 'f'; void *
0x180003ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ce8  mov     rcx, [rbp+188h]; this
0x180003cef  lea     r8, aWil; "wil"
0x180003cf6  mov     r9d, esi; char *
0x180003cf9  mov     edx, 6Fh ; 'o'; void *
0x180003cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d03  mov     rcx, [rbp+188h]; this
0x180003d0a  lea     r8, aWil; "wil"
0x180003d11  mov     r9d, esi; char *
0x180003d14  mov     edx, 12Eh; void *
0x180003d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d1e  test    rdi, rdi
0x180003d21  jz      short loc_180003D34
0x180003d23  mov     rcx, rdi; hMutex
0x180003d26  call    cs:__imp_ReleaseMutex
0x180003d2c  test    eax, eax
0x180003d2e  jz      loc_180003F77
0x180003d34  mov     rcx, rbx; hObject
0x180003d37  call    cs:__imp_CloseHandle
0x180003d3d  test    eax, eax
0x180003d3f  jz      loc_180003F89
0x180003d45  mov     eax, esi
0x180003d47  jmp     loc_180003F20
0x180003d4c  mov     rax, [rsp+280h+hObject]
0x180003d51  lea     rcx, ds:0[rax*4]
0x180003d59  test    rcx, rcx
0x180003d5c  jz      short loc_180003D6C
0x180003d5e  mov     [r15], rcx
0x180003d61  mov     eax, [rcx]
0x180003d63  inc     eax
0x180003d65  mov     [rcx], eax
0x180003d67  jmp     loc_180003EF6
0x180003d6c  mov     rdx, r14; dwBytes
0x180003d6f  mov     qword ptr [r15], 0
0x180003d76  mov     ecx, 8; dwFlags
0x180003d7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d80  mov     r14, rax
0x180003d83  test    rax, rax
0x180003d86  jnz     short loc_180003DAD
0x180003d88  mov     rcx, [rbp+188h]; this
0x180003d8f  lea     r8, aWil; "wil"
0x180003d96  mov     esi, 8007000Eh
0x180003d9b  mov     edx, 14Bh; void *
0x180003da0  mov     r9d, esi; char *
0x180003da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003da8  jmp     loc_180003E3F
0x180003dad  xorps   xmm0, xmm0
0x180003db0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003db6  test    r14b, 3
0x180003dba  jnz     loc_180003F9B
0x180003dc0  mov     r9, r14
0x180003dc3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003dc8  shr     r9, 2; unsigned __int64
0x180003dcc  lea     rcx, [rsp+280h+hObject]; this
0x180003dd1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003dd6  mov     esi, eax
0x180003dd8  test    eax, eax
0x180003dda  jns     loc_180003E86
0x180003de0  mov     rcx, [rbp+188h]; this
0x180003de7  lea     r8, aWil; "wil"
0x180003dee  mov     r9d, eax; char *
0x180003df1  mov     edx, 14Eh; void *
0x180003df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dfb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003e00  test    rcx, rcx
0x180003e03  jz      short loc_180003E13
0x180003e05  call    cs:__imp_CloseHandle
0x180003e0b  test    eax, eax
0x180003e0d  jz      loc_180003FA1
0x180003e13  mov     rcx, [rsp+280h+hObject]; hObject
0x180003e18  test    rcx, rcx
0x180003e1b  jz      short loc_180003E2B
0x180003e1d  call    cs:__imp_CloseHandle
0x180003e23  test    eax, eax
0x180003e25  jz      loc_180003FB3
0x180003e2b  call    cs:__imp_GetProcessHeap
0x180003e31  mov     r8, r14; lpMem
0x180003e34  xor     edx, edx; dwFlags
0x180003e36  mov     rcx, rax; hHeap
0x180003e39  call    cs:__imp_HeapFree
0x180003e3f  mov     rcx, [rbp+188h]; this
0x180003e46  lea     r8, aWil; "wil"
0x180003e4d  mov     r9d, esi; char *
0x180003e50  mov     edx, 137h; void *
0x180003e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e5a  test    rdi, rdi
0x180003e5d  jz      short loc_180003E70
0x180003e5f  mov     rcx, rdi; hMutex
0x180003e62  call    cs:__imp_ReleaseMutex
0x180003e68  test    eax, eax
0x180003e6a  jz      loc_180003FC5
0x180003e70  mov     rcx, rbx; hObject
0x180003e73  call    cs:__imp_CloseHandle
0x180003e79  test    eax, eax
0x180003e7b  jz      loc_180003F58
0x180003e81  jmp     loc_180003D45
0x180003e86  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e8b  lea     rcx, [r14+28h]; void *
0x180003e8f  mov     dword ptr [r14], 1
0x180003e96  xor     edx, edx; Val
0x180003e98  mov     [r14+8], rbx
0x180003e9c  mov     r8d, 108h; Size
0x180003ea2  movdqu  xmmword ptr [r14+10h], xmm0
0x180003ea8  call    memset_0
0x180003ead  xor     eax, eax
0x180003eaf  lea     rcx, [r14+28h]; this
0x180003eb3  mov     [r14+20h], rax
0x180003eb7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ebc  lea     rbx, [r14+0E8h]
0x180003ec3  xor     r8d, r8d; Flags
0x180003ec6  mov     rcx, rbx; lpCriticalSection
0x180003ec9  xor     edx, edx; dwSpinCount
0x180003ecb  call    cs:__imp_InitializeCriticalSectionEx
0x180003ed1  mov     qword ptr [rbx+28h], 0
0x180003ed9  mov     qword ptr [rbx+30h], 0
0x180003ee1  mov     qword ptr [rbx+38h], 0
0x180003ee9  mov     qword ptr [rbx+40h], 0
0x180003ef1  xor     ebx, ebx
0x180003ef3  mov     [r15], r14
0x180003ef6  test    rdi, rdi
0x180003ef9  jz      short loc_180003F0C
0x180003efb  mov     rcx, rdi; hMutex
0x180003efe  call    cs:__imp_ReleaseMutex
0x180003f04  test    eax, eax
0x180003f06  jz      loc_180003FD7
0x180003f0c  test    rbx, rbx
0x180003f0f  jz      short loc_180003F1E
0x180003f11  mov     rcx, rbx; hObject
0x180003f14  call    cs:__imp_CloseHandle
0x180003f1a  test    eax, eax
0x180003f1c  jz      short loc_180003F46
0x180003f1e  xor     eax, eax
0x180003f20  mov     rcx, [rbp+180h+var_30]
0x180003f27  xor     rcx, rsp; StackCookie
0x180003f2a  call    __security_check_cookie
0x180003f2f  mov     rbx, [rsp+280h+arg_10]
0x180003f37  add     rsp, 260h
0x180003f3e  pop     r15
0x180003f40  pop     r14
0x180003f42  pop     rdi
0x180003f43  pop     rsi
0x180003f44  pop     rbp
0x180003f45  retn
0x180003f46  mov     rcx, [rbp+188h]; this
0x180003f4d  mov     edx, 0A0Bh; void *
0x180003f52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f58  mov     rcx, [rbp+188h]; this
0x180003f5f  mov     edx, 0A0Bh; void *
0x180003f64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f6a  mov     rcx, [rbp+188h]; this
0x180003f71  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f77  mov     rcx, [rbp+188h]; this
0x180003f7e  mov     edx, 0A15h; void *
0x180003f83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f89  mov     rcx, [rbp+188h]; this
0x180003f90  mov     edx, 0A0Bh; void *
0x180003f95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f9b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003fa1  mov     rcx, [rbp+188h]; this
0x180003fa8  mov     edx, 0A0Bh; void *
0x180003fad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fb3  mov     rcx, [rbp+188h]; this
0x180003fba  mov     edx, 0A0Bh; void *
0x180003fbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fc5  mov     rcx, [rbp+188h]; this
0x180003fcc  mov     edx, 0A15h; void *
0x180003fd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fd7  mov     rcx, [rbp+188h]; this
0x180003fde  mov     edx, 0A15h; void *
0x180003fe3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
