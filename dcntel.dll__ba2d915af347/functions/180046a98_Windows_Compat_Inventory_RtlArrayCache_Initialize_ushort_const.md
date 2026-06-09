# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x180046a98`
- end: `0x180046e9c`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `1028`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800472dc`

## callees

- `0x180008dc0`
- `0x1800097d0`
- `0x180009f14`
- `0x18000e4c0`
- `0x18000f378`
- `0x18001286c`
- `0x180013708`
- `0x180046a98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046bdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046c56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046db4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046bdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046c56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046db4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046dd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180046b65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180046b65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046b16`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046b16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046d0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046d0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046d66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046ad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046ba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046ad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046b3e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180046bf8`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180046bf8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046c26`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046c26`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046c86`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046c86`

## string_xrefs

- `0x180046ae1`: `RtlArrayCache%lsMutex%d`
- `0x180046bb1`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::RtlArrayCache::Initialize(
        Windows::Compat::Inventory::RtlArrayCache *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  wil::details *v5; // rcx
  HANDLE Mutex; // rdi
  void *v7; // rbx
  DWORD LastError; // ebp
  unsigned int v9; // r8d
  const char *v10; // r9
  void *v11; // rdi
  DWORD v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  const char *v15; // r9
  signed int v16; // eax
  unsigned int v17; // r8d
  const char *v18; // r9
  HANDLE FileMappingW; // rax
  signed int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  char v23; // bl
  _DWORD *v24; // rax
  signed int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  _OWORD *v28; // rax
  _QWORD *v29; // rbx
  _OWORD *v30; // rax
  _QWORD *v31; // rbx
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  _QWORD *v36; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-258h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 5) = Mutex;
  }
  else if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
    return v4;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  v12 = WaitForSingleObjectEx(v11, 0xFFFFFFFF, 0);
  if ( v12 == 258 )
  {
    v11 = 0;
  }
  else if ( (v12 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v13, v14, v15);
  }
  dwMaximumSizeLow[0] = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLow);
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    return v4;
  }
  FileMappingW = OpenFileMappingW(2u, 0, Name);
  *((_QWORD *)this + 4) = FileMappingW;
  if ( FileMappingW )
  {
    v23 = 1;
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x18u, Name);
    *((_QWORD *)this + 4) = FileMappingW;
    if ( !FileMappingW )
    {
      v20 = GetLastError();
      v4 = v20;
      if ( v20 > 0 )
        v4 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v21, v22);
      return v4;
    }
    v23 = 0;
  }
  v24 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
  *((_QWORD *)this + 6) = v24;
  if ( v24 )
  {
    if ( v23 )
      goto LABEL_45;
    v24[4] = 0;
    v28 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v28;
    if ( v28 )
    {
      *v28 = 0;
      v28[1] = 0;
      v28[2] = 0;
      *(_QWORD *)v28 = GetProcessHeap();
      v29[4] = 16;
      v29[2] = 0;
      v29[3] = 0;
      v29[5] = 0;
      v29[1] = 8;
    }
    else
    {
      v29 = 0;
    }
    **((_QWORD **)this + 6) = v29;
    v30 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v30;
    if ( v30 )
    {
      *v30 = 0;
      v30[1] = 0;
      v30[2] = 0;
      *(_QWORD *)v30 = GetProcessHeap();
      v31[4] = 16;
      v31[2] = 0;
      v31[3] = 0;
      v31[5] = 0;
      v31[1] = 8;
    }
    else
    {
      v31 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v31;
    v24 = (_DWORD *)*((_QWORD *)this + 6);
    if ( *(_QWORD *)v24 && *((_QWORD *)v24 + 1) )
    {
LABEL_45:
      ++v24[4];
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
      v36 = (_QWORD *)*((_QWORD *)this + 6);
      v4 = 0;
      *((_QWORD *)this + 2) = v36[1];
      *((_QWORD *)this + 1) = *v36;
    }
    else
    {
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v25 = GetLastError();
    v4 = v25;
    if ( v25 > 0 )
      v4 = (unsigned __int16)v25 | 0x80070000;
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  }
  return v4;
}

```

## disassembly

```asm
0x180046a98  mov     [rsp+arg_10], rbx
0x180046a9d  push    rbp
0x180046a9e  push    rsi
0x180046a9f  push    rdi
0x180046aa0  push    r12
0x180046aa2  push    r14
0x180046aa4  sub     rsp, 250h
0x180046aab  mov     rax, cs:__security_cookie
0x180046ab2  xor     rax, rsp
0x180046ab5  mov     [rsp+278h+var_38], rax
0x180046abd  mov     r14, rdx
0x180046ac0  mov     rsi, rcx
0x180046ac3  xor     edx, edx; Val
0x180046ac5  lea     rcx, [rsp+278h+Name]; void *
0x180046aca  mov     r8d, 208h; Size
0x180046ad0  call    memset_0
0x180046ad5  call    cs:__imp_GetCurrentProcessId
0x180046adb  mov     r12d, 104h
0x180046ae1  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x180046ae8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180046aed  mov     [rsp+278h+dwMaximumSizeLow], eax
0x180046af1  mov     edx, r12d; unsigned __int64
0x180046af4  mov     r9, r14
0x180046af7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046afc  mov     ebx, eax
0x180046afe  test    eax, eax
0x180046b00  js      loc_180046DF3
0x180046b06  mov     r9d, 1F0001h; dwDesiredAccess
0x180046b0c  lea     rdx, [rsp+278h+Name]; lpName
0x180046b11  xor     r8d, r8d; dwFlags
0x180046b14  xor     ecx, ecx; lpMutexAttributes
0x180046b16  call    cs:__imp_CreateMutexExW
0x180046b1c  mov     rdi, rax
0x180046b1f  test    rax, rax
0x180046b22  jz      short loc_180046B7F
0x180046b24  call    cs:__imp_GetLastError
0x180046b2a  mov     rbx, [rsi+28h]
0x180046b2e  test    rbx, rbx
0x180046b31  jz      short loc_180046B54
0x180046b33  call    cs:__imp_GetLastError
0x180046b39  mov     rcx, rbx; hObject
0x180046b3c  mov     ebp, eax
0x180046b3e  call    cs:__imp_CloseHandle
0x180046b44  test    eax, eax
0x180046b46  jz      loc_180046E76
0x180046b4c  mov     ecx, ebp; dwErrCode
0x180046b4e  call    cs:__imp_SetLastError
0x180046b54  mov     [rsi+28h], rdi
0x180046b58  mov     rdi, [rsi+28h]
0x180046b5c  xor     r8d, r8d; bAlertable
0x180046b5f  mov     rcx, rdi; hHandle
0x180046b62  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180046b65  call    cs:__imp_WaitForSingleObjectEx
0x180046b6b  cmp     eax, 102h
0x180046b70  jz      short loc_180046BA6
0x180046b72  test    eax, 0FFFFFF7Fh
0x180046b77  jnz     loc_180046E2F
0x180046b7d  jmp     short loc_180046BA8
0x180046b7f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180046b84  test    eax, eax
0x180046b86  jns     short loc_180046B58
0x180046b88  call    cs:__imp_GetLastError
0x180046b8e  mov     ebx, eax
0x180046b90  test    eax, eax
0x180046b92  jle     loc_180046DF3
0x180046b98  movzx   ebx, ax
0x180046b9b  or      ebx, 80070000h
0x180046ba1  jmp     loc_180046DF3
0x180046ba6  xor     edi, edi
0x180046ba8  call    cs:__imp_GetCurrentProcessId
0x180046bae  mov     r9, r14
0x180046bb1  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x180046bb8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180046bbd  mov     [rsp+278h+dwMaximumSizeLow], eax
0x180046bc1  mov     rdx, r12; unsigned __int64
0x180046bc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046bc9  mov     ebx, eax
0x180046bcb  test    eax, eax
0x180046bcd  jns     short loc_180046BEE
0x180046bcf  test    rdi, rdi
0x180046bd2  jz      loc_180046DF3
0x180046bd8  mov     rcx, rdi; hMutex
0x180046bdb  call    cs:__imp_ReleaseMutex
0x180046be1  test    eax, eax
0x180046be3  jz      loc_180046E3D
0x180046be9  jmp     loc_180046DF3
0x180046bee  xor     edx, edx; bInheritHandle
0x180046bf0  lea     r8, [rsp+278h+Name]; lpName
0x180046bf5  lea     ecx, [rdx+2]; dwDesiredAccess
0x180046bf8  call    cs:__imp_OpenFileMappingW
0x180046bfe  mov     [rsi+20h], rax
0x180046c02  test    rax, rax
0x180046c05  jnz     short loc_180046C6D
0x180046c07  xor     r9d, r9d; dwMaximumSizeHigh
0x180046c0a  lea     rax, [rsp+278h+Name]
0x180046c0f  mov     [rsp+278h+lpName], rax; lpName
0x180046c14  xor     edx, edx; lpFileMappingAttributes
0x180046c16  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180046c1a  mov     [rsp+278h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x180046c22  lea     r8d, [r9+4]; flProtect
0x180046c26  call    cs:__imp_CreateFileMappingW
0x180046c2c  mov     [rsi+20h], rax
0x180046c30  test    rax, rax
0x180046c33  jnz     short loc_180046C69
0x180046c35  call    cs:__imp_GetLastError
0x180046c3b  mov     ebx, eax
0x180046c3d  test    eax, eax
0x180046c3f  jle     short loc_180046C4A
0x180046c41  movzx   ebx, ax
0x180046c44  or      ebx, 80070000h
0x180046c4a  test    rdi, rdi
0x180046c4d  jz      loc_180046DF3
0x180046c53  mov     rcx, rdi; hMutex
0x180046c56  call    cs:__imp_ReleaseMutex
0x180046c5c  test    eax, eax
0x180046c5e  jz      loc_180046E50
0x180046c64  jmp     loc_180046DF3
0x180046c69  xor     bl, bl
0x180046c6b  jmp     short loc_180046C6F
0x180046c6d  mov     bl, 1
0x180046c6f  xor     r9d, r9d; dwFileOffsetLow
0x180046c72  mov     qword ptr [rsp+278h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180046c7b  xor     r8d, r8d; dwFileOffsetHigh
0x180046c7e  mov     edx, 0F001Fh; dwDesiredAccess
0x180046c83  mov     rcx, rax; hFileMappingObject
0x180046c86  call    cs:__imp_MapViewOfFile
0x180046c8c  mov     [rsi+30h], rax
0x180046c90  test    rax, rax
0x180046c93  jnz     short loc_180046CC9
0x180046c95  call    cs:__imp_GetLastError
0x180046c9b  mov     ebx, eax
0x180046c9d  test    eax, eax
0x180046c9f  jle     short loc_180046CAA
0x180046ca1  movzx   ebx, ax
0x180046ca4  or      ebx, 80070000h
0x180046caa  test    rdi, rdi
0x180046cad  jz      loc_180046DF3
0x180046cb3  mov     rcx, rdi; hMutex
0x180046cb6  call    cs:__imp_ReleaseMutex
0x180046cbc  test    eax, eax
0x180046cbe  jz      loc_180046E63
0x180046cc4  jmp     loc_180046DF3
0x180046cc9  test    bl, bl
0x180046ccb  jnz     loc_180046DC9
0x180046cd1  mov     r12d, 30h ; '0'
0x180046cd7  mov     dword ptr [rax+10h], 0
0x180046cde  mov     ecx, r12d; unsigned __int64
0x180046ce1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046ce8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046ced  lea     ebp, [r12-20h]
0x180046cf2  mov     rbx, rax
0x180046cf5  lea     r14d, [r12-28h]
0x180046cfa  test    rax, rax
0x180046cfd  jz      short loc_180046D38
0x180046cff  xorps   xmm0, xmm0
0x180046d02  movups  xmmword ptr [rax], xmm0
0x180046d05  movups  xmmword ptr [rax+10h], xmm0
0x180046d09  movups  xmmword ptr [rax+20h], xmm0
0x180046d0d  call    cs:__imp_GetProcessHeap
0x180046d13  mov     [rbx], rax
0x180046d16  mov     [rbx+20h], rbp
0x180046d1a  mov     qword ptr [rbx+10h], 0
0x180046d22  mov     qword ptr [rbx+18h], 0
0x180046d2a  mov     qword ptr [rbx+28h], 0
0x180046d32  mov     [rbx+8], r14
0x180046d36  jmp     short loc_180046D3A
0x180046d38  xor     ebx, ebx
0x180046d3a  mov     rax, [rsi+30h]
0x180046d3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046d45  mov     rcx, r12; unsigned __int64
0x180046d48  mov     [rax], rbx
0x180046d4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046d50  mov     rbx, rax
0x180046d53  test    rax, rax
0x180046d56  jz      short loc_180046D91
0x180046d58  xorps   xmm0, xmm0
0x180046d5b  movups  xmmword ptr [rax], xmm0
0x180046d5e  movups  xmmword ptr [rax+10h], xmm0
0x180046d62  movups  xmmword ptr [rax+20h], xmm0
0x180046d66  call    cs:__imp_GetProcessHeap
0x180046d6c  mov     [rbx], rax
0x180046d6f  mov     [rbx+20h], rbp
0x180046d73  mov     qword ptr [rbx+10h], 0
0x180046d7b  mov     qword ptr [rbx+18h], 0
0x180046d83  mov     qword ptr [rbx+28h], 0
0x180046d8b  mov     [rbx+8], r14
0x180046d8f  jmp     short loc_180046D93
0x180046d91  xor     ebx, ebx
0x180046d93  mov     rax, [rsi+30h]
0x180046d97  mov     [rax+8], rbx
0x180046d9b  mov     rax, [rsi+30h]
0x180046d9f  cmp     qword ptr [rax], 0
0x180046da3  jz      short loc_180046DAC
0x180046da5  cmp     qword ptr [rax+8], 0
0x180046daa  jnz     short loc_180046DC9
0x180046dac  test    rdi, rdi
0x180046daf  jz      short loc_180046DC2
0x180046db1  mov     rcx, rdi; hMutex
0x180046db4  call    cs:__imp_ReleaseMutex
0x180046dba  test    eax, eax
0x180046dbc  jz      loc_180046E89
0x180046dc2  mov     ebx, 8007000Eh
0x180046dc7  jmp     short loc_180046DF3
0x180046dc9  inc     dword ptr [rax+10h]
0x180046dcc  test    rdi, rdi
0x180046dcf  jz      short loc_180046DDE
0x180046dd1  mov     rcx, rdi; hMutex
0x180046dd4  call    cs:__imp_ReleaseMutex
0x180046dda  test    eax, eax
0x180046ddc  jz      short loc_180046E1C
0x180046dde  mov     rcx, [rsi+30h]
0x180046de2  xor     ebx, ebx
0x180046de4  mov     rax, [rcx+8]
0x180046de8  mov     [rsi+10h], rax
0x180046dec  mov     rax, [rcx]
0x180046def  mov     [rsi+8], rax
0x180046df3  mov     eax, ebx
0x180046df5  mov     rcx, [rsp+278h+var_38]
0x180046dfd  xor     rcx, rsp; StackCookie
0x180046e00  call    __security_check_cookie
0x180046e05  mov     rbx, [rsp+278h+arg_10]
0x180046e0d  add     rsp, 250h
0x180046e14  pop     r14
0x180046e16  pop     r12
0x180046e18  pop     rdi
0x180046e19  pop     rsi
0x180046e1a  pop     rbp
0x180046e1b  retn
0x180046e1c  mov     rcx, [rsp+278h]; this
0x180046e24  mov     edx, 0A15h; void *
0x180046e29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e2f  mov     rcx, [rsp+278h]; this
0x180046e37  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180046e3d  mov     rcx, [rsp+278h]; this
0x180046e45  mov     edx, 0A15h; void *
0x180046e4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e50  mov     rcx, [rsp+278h]; this
0x180046e58  mov     edx, 0A15h; void *
0x180046e5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e63  mov     rcx, [rsp+278h]; this
0x180046e6b  mov     edx, 0A15h; void *
0x180046e70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e76  mov     rcx, [rsp+278h]; this
0x180046e7e  mov     edx, 0A0Bh; void *
0x180046e83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e89  mov     rcx, [rsp+278h]; this
0x180046e91  mov     edx, 0A15h; void *
0x180046e96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
