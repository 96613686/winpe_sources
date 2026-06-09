# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x180026a40`
- end: `0x180026e8e`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `1102`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800272dc`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000514c`
- `0x180009060`
- `0x18000bcb8`
- `0x18000f7bc`
- `0x1800108d4`
- `0x180026a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026b13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026b13`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026b8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026c06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026c66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026b8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026c06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026c66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026d97`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026abc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026abc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026afc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ae4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ae4`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180026ba8`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180026ba8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180026c36`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180026c36`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026bd6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026bd6`

## string_xrefs

- `0x180026de8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e02`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e1c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e36`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e50`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e62`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026e7c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026a8c`: `RtlArrayCache%lsMutex%d`
- `0x180026b63`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::RtlArrayCache::Initialize(
        Windows::Compat::Inventory::RtlArrayCache *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  wil::details *v5; // rcx
  HANDLE Mutex; // rdi
  void *v7; // rbx
  DWORD LastError; // ebp
  const char *v9; // r9
  void *v10; // rdi
  DWORD v11; // eax
  const char *v12; // r9
  signed int v13; // eax
  const char *v14; // r9
  HANDLE FileMappingW; // rax
  signed int v16; // eax
  const char *v17; // r9
  char v18; // bl
  _DWORD *v19; // rax
  signed int v20; // eax
  const char *v21; // r9
  _OWORD *v22; // rax
  _OWORD *v23; // rdx
  _OWORD *v24; // rax
  _OWORD *v25; // rdx
  const char *v26; // r9
  const char *v27; // r9
  _QWORD *v28; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-258h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-258h]
  WCHAR Name[268]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowa = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMutex%d", a2, dwMaximumSizeLowa);
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    v7 = (void *)*((_QWORD *)this + 5);
    if ( v7 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v9);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 5) = Mutex;
  }
  else if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      return (unsigned __int16)v13 | 0x80070000;
    return v4;
  }
  v10 = (void *)*((_QWORD *)this + 5);
  v11 = WaitForSingleObjectEx(v10, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v10 = 0;
  }
  else if ( (v11 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v12);
  }
  dwMaximumSizeLow[0] = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLow);
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v10 && !ReleaseMutex(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    return v4;
  }
  FileMappingW = OpenFileMappingW(2u, 0, Name);
  *((_QWORD *)this + 4) = FileMappingW;
  if ( FileMappingW )
  {
    v18 = 1;
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x18u, Name);
    *((_QWORD *)this + 4) = FileMappingW;
    if ( !FileMappingW )
    {
      v16 = GetLastError();
      v4 = v16;
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v17);
      return v4;
    }
    v18 = 0;
  }
  v19 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
  *((_QWORD *)this + 6) = v19;
  if ( v19 )
  {
    if ( v18 )
      goto LABEL_45;
    v19[4] = 0;
    v22 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 0;
      v22[1] = 0;
      v22[2] = 0;
      *(_QWORD *)v22 = NtCurrentPeb()->ProcessHeap;
      *((_QWORD *)v22 + 4) = 16;
      *((_QWORD *)v22 + 2) = 0;
      *((_QWORD *)v22 + 3) = 0;
      *((_QWORD *)v22 + 5) = 0;
      *((_QWORD *)v22 + 1) = 8;
    }
    else
    {
      v23 = 0;
    }
    **((_QWORD **)this + 6) = v23;
    v24 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v25 = v24;
    if ( v24 )
    {
      *v24 = 0;
      v24[1] = 0;
      v24[2] = 0;
      *(_QWORD *)v24 = NtCurrentPeb()->ProcessHeap;
      *((_QWORD *)v24 + 4) = 16;
      *((_QWORD *)v24 + 2) = 0;
      *((_QWORD *)v24 + 3) = 0;
      *((_QWORD *)v24 + 5) = 0;
      *((_QWORD *)v24 + 1) = 8;
    }
    else
    {
      v25 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v25;
    v19 = (_DWORD *)*((_QWORD *)this + 6);
    if ( *(_QWORD *)v19 && *((_QWORD *)v19 + 1) )
    {
LABEL_45:
      ++v19[4];
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v27);
      v28 = (_QWORD *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 2) = v28[1];
      *((_QWORD *)this + 1) = *v28;
      return 0;
    }
    else
    {
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v26);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v20 = GetLastError();
    v4 = v20;
    if ( v20 > 0 )
      v4 = (unsigned __int16)v20 | 0x80070000;
    if ( v10 && !ReleaseMutex(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v21);
  }
  return v4;
}

```

## disassembly

```asm
0x180026a40  mov     [rsp+arg_10], rbx
0x180026a45  mov     [rsp+arg_18], rbp
0x180026a4a  push    rsi
0x180026a4b  push    rdi
0x180026a4c  push    r14
0x180026a4e  sub     rsp, 260h
0x180026a55  mov     rax, cs:__security_cookie
0x180026a5c  xor     rax, rsp
0x180026a5f  mov     [rsp+278h+var_20], rax
0x180026a67  mov     r14, rdx
0x180026a6a  mov     rsi, rcx
0x180026a6d  xor     edx, edx; Val
0x180026a6f  mov     r8d, 208h; Size
0x180026a75  lea     rcx, [rsp+278h+Name]; void *
0x180026a7a  call    memset_0
0x180026a7f  call    cs:__imp_GetCurrentProcessId
0x180026a85  mov     [rsp+278h+dwMaximumSizeLow], eax
0x180026a89  mov     r9, r14
0x180026a8c  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x180026a93  mov     edx, 104h; unsigned __int64
0x180026a98  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180026a9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026aa2  mov     ebx, eax
0x180026aa4  test    eax, eax
0x180026aa6  js      loc_180026DB6
0x180026aac  mov     r9d, 1F0001h; dwDesiredAccess
0x180026ab2  xor     r8d, r8d; dwFlags
0x180026ab5  lea     rdx, [rsp+278h+Name]; lpName
0x180026aba  xor     ecx, ecx; lpMutexAttributes
0x180026abc  call    cs:__imp_CreateMutexExW
0x180026ac2  mov     rdi, rax
0x180026ac5  test    rax, rax
0x180026ac8  jz      short loc_180026B2D
0x180026aca  call    cs:__imp_GetLastError
0x180026ad0  mov     rbx, [rsi+28h]
0x180026ad4  test    rbx, rbx
0x180026ad7  jz      short loc_180026B02
0x180026ad9  call    cs:__imp_GetLastError
0x180026adf  mov     ebp, eax
0x180026ae1  mov     rcx, rbx; hObject
0x180026ae4  call    cs:__imp_CloseHandle
0x180026aea  mov     rcx, [rsp+278h]; this
0x180026af2  test    eax, eax
0x180026af4  jz      loc_180026E62
0x180026afa  mov     ecx, ebp; dwErrCode
0x180026afc  call    cs:__imp_SetLastError
0x180026b02  mov     [rsi+28h], rdi
0x180026b06  mov     rdi, [rsi+28h]
0x180026b0a  xor     r8d, r8d; bAlertable
0x180026b0d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180026b10  mov     rcx, rdi; hHandle
0x180026b13  call    cs:__imp_WaitForSingleObjectEx
0x180026b19  cmp     eax, 102h
0x180026b1e  jz      short loc_180026B54
0x180026b20  test    eax, 0FFFFFF7Fh
0x180026b25  jnz     loc_180026DFA
0x180026b2b  jmp     short loc_180026B56
0x180026b2d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180026b32  test    eax, eax
0x180026b34  jns     short loc_180026B06
0x180026b36  call    cs:__imp_GetLastError
0x180026b3c  mov     ebx, eax
0x180026b3e  test    eax, eax
0x180026b40  jle     loc_180026DB6
0x180026b46  movzx   ebx, ax
0x180026b49  or      ebx, 80070000h
0x180026b4f  jmp     loc_180026DB6
0x180026b54  xor     edi, edi
0x180026b56  call    cs:__imp_GetCurrentProcessId
0x180026b5c  mov     [rsp+278h+dwMaximumSizeLow], eax
0x180026b60  mov     r9, r14
0x180026b63  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x180026b6a  mov     edx, 104h; unsigned __int64
0x180026b6f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180026b74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026b79  mov     ebx, eax
0x180026b7b  test    eax, eax
0x180026b7d  jns     short loc_180026B9E
0x180026b7f  test    rdi, rdi
0x180026b82  jz      loc_180026DB6
0x180026b88  mov     rcx, rdi; hMutex
0x180026b8b  call    cs:__imp_ReleaseMutex
0x180026b91  test    eax, eax
0x180026b93  jz      loc_180026E14
0x180026b99  jmp     loc_180026DB6
0x180026b9e  lea     r8, [rsp+278h+Name]; lpName
0x180026ba3  xor     edx, edx; bInheritHandle
0x180026ba5  lea     ecx, [rdx+2]; dwDesiredAccess
0x180026ba8  call    cs:__imp_OpenFileMappingW
0x180026bae  mov     [rsi+20h], rax
0x180026bb2  test    rax, rax
0x180026bb5  jnz     short loc_180026C1D
0x180026bb7  lea     rax, [rsp+278h+Name]
0x180026bbc  mov     [rsp+278h+lpName], rax; lpName
0x180026bc1  mov     [rsp+278h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x180026bc9  xor     r9d, r9d; dwMaximumSizeHigh
0x180026bcc  xor     edx, edx; lpFileMappingAttributes
0x180026bce  lea     r8d, [r9+4]; flProtect
0x180026bd2  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180026bd6  call    cs:__imp_CreateFileMappingW
0x180026bdc  mov     [rsi+20h], rax
0x180026be0  test    rax, rax
0x180026be3  jnz     short loc_180026C19
0x180026be5  call    cs:__imp_GetLastError
0x180026beb  mov     ebx, eax
0x180026bed  test    eax, eax
0x180026bef  jle     short loc_180026BFA
0x180026bf1  movzx   ebx, ax
0x180026bf4  or      ebx, 80070000h
0x180026bfa  test    rdi, rdi
0x180026bfd  jz      loc_180026DB6
0x180026c03  mov     rcx, rdi; hMutex
0x180026c06  call    cs:__imp_ReleaseMutex
0x180026c0c  test    eax, eax
0x180026c0e  jz      loc_180026E2E
0x180026c14  jmp     loc_180026DB6
0x180026c19  xor     bl, bl
0x180026c1b  jmp     short loc_180026C1F
0x180026c1d  mov     bl, 1
0x180026c1f  mov     qword ptr [rsp+278h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180026c28  xor     r9d, r9d; dwFileOffsetLow
0x180026c2b  xor     r8d, r8d; dwFileOffsetHigh
0x180026c2e  mov     edx, 0F001Fh; dwDesiredAccess
0x180026c33  mov     rcx, rax; hFileMappingObject
0x180026c36  call    cs:__imp_MapViewOfFile
0x180026c3c  mov     [rsi+30h], rax
0x180026c40  test    rax, rax
0x180026c43  jnz     short loc_180026C79
0x180026c45  call    cs:__imp_GetLastError
0x180026c4b  mov     ebx, eax
0x180026c4d  test    eax, eax
0x180026c4f  jle     short loc_180026C5A
0x180026c51  movzx   ebx, ax
0x180026c54  or      ebx, 80070000h
0x180026c5a  test    rdi, rdi
0x180026c5d  jz      loc_180026DB6
0x180026c63  mov     rcx, rdi; hMutex
0x180026c66  call    cs:__imp_ReleaseMutex
0x180026c6c  test    eax, eax
0x180026c6e  jz      loc_180026E48
0x180026c74  jmp     loc_180026DB6
0x180026c79  test    bl, bl
0x180026c7b  jnz     loc_180026D8C
0x180026c81  mov     dword ptr [rax+10h], 0
0x180026c88  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026c8f  mov     ebx, 30h ; '0'
0x180026c94  mov     ecx, ebx; unsigned __int64
0x180026c96  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026c9b  mov     rdx, rax
0x180026c9e  mov     [rsp+278h+var_248], rax
0x180026ca3  lea     ebp, [rbx-20h]
0x180026ca6  lea     r14d, [rbx-28h]
0x180026caa  test    rax, rax
0x180026cad  jz      short loc_180026CEF
0x180026caf  xorps   xmm1, xmm1
0x180026cb2  movups  xmmword ptr [rax], xmm1
0x180026cb5  movups  xmmword ptr [rax+10h], xmm1
0x180026cb9  movups  xmmword ptr [rax+20h], xmm1
0x180026cbd  mov     rax, gs:60h
0x180026cc6  mov     rcx, [rax+30h]
0x180026cca  mov     [rdx], rcx
0x180026ccd  mov     [rdx+20h], rbp
0x180026cd1  mov     qword ptr [rdx+10h], 0
0x180026cd9  mov     qword ptr [rdx+18h], 0
0x180026ce1  mov     qword ptr [rdx+28h], 0
0x180026ce9  mov     [rdx+8], r14
0x180026ced  jmp     short loc_180026CF1
0x180026cef  xor     edx, edx
0x180026cf1  mov     rax, [rsi+30h]
0x180026cf5  mov     [rax], rdx
0x180026cf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026cff  mov     rcx, rbx; unsigned __int64
0x180026d02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026d07  mov     rdx, rax
0x180026d0a  mov     [rsp+278h+var_248], rax
0x180026d0f  test    rax, rax
0x180026d12  jz      short loc_180026D54
0x180026d14  xorps   xmm1, xmm1
0x180026d17  movups  xmmword ptr [rax], xmm1
0x180026d1a  movups  xmmword ptr [rax+10h], xmm1
0x180026d1e  movups  xmmword ptr [rax+20h], xmm1
0x180026d22  mov     rax, gs:60h
0x180026d2b  mov     rcx, [rax+30h]
0x180026d2f  mov     [rdx], rcx
0x180026d32  mov     [rdx+20h], rbp
0x180026d36  mov     qword ptr [rdx+10h], 0
0x180026d3e  mov     qword ptr [rdx+18h], 0
0x180026d46  mov     qword ptr [rdx+28h], 0
0x180026d4e  mov     [rdx+8], r14
0x180026d52  jmp     short loc_180026D56
0x180026d54  xor     edx, edx
0x180026d56  mov     rax, [rsi+30h]
0x180026d5a  mov     [rax+8], rdx
0x180026d5e  mov     rax, [rsi+30h]
0x180026d62  cmp     qword ptr [rax], 0
0x180026d66  jz      short loc_180026D6F
0x180026d68  cmp     qword ptr [rax+8], 0
0x180026d6d  jnz     short loc_180026D8C
0x180026d6f  test    rdi, rdi
0x180026d72  jz      short loc_180026D85
0x180026d74  mov     rcx, rdi; hMutex
0x180026d77  call    cs:__imp_ReleaseMutex
0x180026d7d  test    eax, eax
0x180026d7f  jz      loc_180026E74
0x180026d85  mov     ebx, 8007000Eh
0x180026d8a  jmp     short loc_180026DB6
0x180026d8c  inc     dword ptr [rax+10h]
0x180026d8f  test    rdi, rdi
0x180026d92  jz      short loc_180026DA1
0x180026d94  mov     rcx, rdi; hMutex
0x180026d97  call    cs:__imp_ReleaseMutex
0x180026d9d  test    eax, eax
0x180026d9f  jz      short loc_180026DE0
0x180026da1  mov     rcx, [rsi+30h]
0x180026da5  mov     rax, [rcx+8]
0x180026da9  mov     [rsi+10h], rax
0x180026dad  mov     rax, [rcx]
0x180026db0  mov     [rsi+8], rax
0x180026db4  xor     ebx, ebx
0x180026db6  mov     eax, ebx
0x180026db8  mov     rcx, [rsp+278h+var_20]
0x180026dc0  xor     rcx, rsp; StackCookie
0x180026dc3  call    __security_check_cookie
0x180026dc8  lea     r11, [rsp+278h+var_18]
0x180026dd0  mov     rbx, [r11+30h]
0x180026dd4  mov     rbp, [r11+38h]
0x180026dd8  mov     rsp, r11
0x180026ddb  pop     r14
0x180026ddd  pop     rdi
0x180026dde  pop     rsi
0x180026ddf  retn
0x180026de0  mov     rcx, [rsp+278h]; this
0x180026de8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026def  mov     edx, 0A15h; void *
0x180026df4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026dfa  mov     rcx, [rsp+278h]; this
0x180026e02  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e09  mov     edx, 0E01h; void *
0x180026e0e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180026e14  mov     rcx, [rsp+278h]; this
0x180026e1c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e23  mov     edx, 0A15h; void *
0x180026e28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026e2e  mov     rcx, [rsp+278h]; this
0x180026e36  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e3d  mov     edx, 0A15h; void *
0x180026e42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026e48  mov     rcx, [rsp+278h]; this
0x180026e50  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e57  mov     edx, 0A15h; void *
0x180026e5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026e62  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e69  mov     edx, 0A0Bh; void *
0x180026e6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026e74  mov     rcx, [rsp+278h]; this
0x180026e7c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e83  mov     edx, 0A15h; void *
0x180026e88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
