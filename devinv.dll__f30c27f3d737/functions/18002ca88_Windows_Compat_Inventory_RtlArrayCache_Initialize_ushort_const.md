# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x18002ca88`
- end: `0x18002ce8c`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `1028`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002d2d0`

## callees

- `0x180005e40`
- `0x1800066f0`
- `0x180006ec4`
- `0x180009bb0`
- `0x18000aa58`
- `0x18000dcec`
- `0x18000eabc`
- `0x18002ca88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cbcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cc46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cda4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cdc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cbcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cc46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cda4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002cdc4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cb55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cb55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002cb06`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002cb06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ccfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ccfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cb98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cb98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb2e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002cc76`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002cc76`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002cc16`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002cc16`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002cbe8`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002cbe8`

## string_xrefs

- `0x18002cad1`: `RtlArrayCache%lsMutex%d`
- `0x18002cba1`: `RtlArrayCache%lsMemory%d`

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
    v28 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
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
    v30 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
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
0x18002ca88  mov     [rsp+arg_10], rbx
0x18002ca8d  push    rbp
0x18002ca8e  push    rsi
0x18002ca8f  push    rdi
0x18002ca90  push    r12
0x18002ca92  push    r14
0x18002ca94  sub     rsp, 250h
0x18002ca9b  mov     rax, cs:__security_cookie
0x18002caa2  xor     rax, rsp
0x18002caa5  mov     [rsp+278h+var_38], rax
0x18002caad  mov     r14, rdx
0x18002cab0  mov     rsi, rcx
0x18002cab3  xor     edx, edx; Val
0x18002cab5  lea     rcx, [rsp+278h+Name]; void *
0x18002caba  mov     r8d, 208h; Size
0x18002cac0  call    memset_0
0x18002cac5  call    cs:__imp_GetCurrentProcessId
0x18002cacb  mov     r12d, 104h
0x18002cad1  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x18002cad8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18002cadd  mov     [rsp+278h+dwMaximumSizeLow], eax
0x18002cae1  mov     edx, r12d; unsigned __int64
0x18002cae4  mov     r9, r14
0x18002cae7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002caec  mov     ebx, eax
0x18002caee  test    eax, eax
0x18002caf0  js      loc_18002CDE3
0x18002caf6  mov     r9d, 1F0001h; dwDesiredAccess
0x18002cafc  lea     rdx, [rsp+278h+Name]; lpName
0x18002cb01  xor     r8d, r8d; dwFlags
0x18002cb04  xor     ecx, ecx; lpMutexAttributes
0x18002cb06  call    cs:__imp_CreateMutexExW
0x18002cb0c  mov     rdi, rax
0x18002cb0f  test    rax, rax
0x18002cb12  jz      short loc_18002CB6F
0x18002cb14  call    cs:__imp_GetLastError
0x18002cb1a  mov     rbx, [rsi+28h]
0x18002cb1e  test    rbx, rbx
0x18002cb21  jz      short loc_18002CB44
0x18002cb23  call    cs:__imp_GetLastError
0x18002cb29  mov     rcx, rbx; hObject
0x18002cb2c  mov     ebp, eax
0x18002cb2e  call    cs:__imp_CloseHandle
0x18002cb34  test    eax, eax
0x18002cb36  jz      loc_18002CE66
0x18002cb3c  mov     ecx, ebp; dwErrCode
0x18002cb3e  call    cs:__imp_SetLastError
0x18002cb44  mov     [rsi+28h], rdi
0x18002cb48  mov     rdi, [rsi+28h]
0x18002cb4c  xor     r8d, r8d; bAlertable
0x18002cb4f  mov     rcx, rdi; hHandle
0x18002cb52  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002cb55  call    cs:__imp_WaitForSingleObjectEx
0x18002cb5b  cmp     eax, 102h
0x18002cb60  jz      short loc_18002CB96
0x18002cb62  test    eax, 0FFFFFF7Fh
0x18002cb67  jnz     loc_18002CE1F
0x18002cb6d  jmp     short loc_18002CB98
0x18002cb6f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002cb74  test    eax, eax
0x18002cb76  jns     short loc_18002CB48
0x18002cb78  call    cs:__imp_GetLastError
0x18002cb7e  mov     ebx, eax
0x18002cb80  test    eax, eax
0x18002cb82  jle     loc_18002CDE3
0x18002cb88  movzx   ebx, ax
0x18002cb8b  or      ebx, 80070000h
0x18002cb91  jmp     loc_18002CDE3
0x18002cb96  xor     edi, edi
0x18002cb98  call    cs:__imp_GetCurrentProcessId
0x18002cb9e  mov     r9, r14
0x18002cba1  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x18002cba8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18002cbad  mov     [rsp+278h+dwMaximumSizeLow], eax
0x18002cbb1  mov     rdx, r12; unsigned __int64
0x18002cbb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cbb9  mov     ebx, eax
0x18002cbbb  test    eax, eax
0x18002cbbd  jns     short loc_18002CBDE
0x18002cbbf  test    rdi, rdi
0x18002cbc2  jz      loc_18002CDE3
0x18002cbc8  mov     rcx, rdi; hMutex
0x18002cbcb  call    cs:__imp_ReleaseMutex
0x18002cbd1  test    eax, eax
0x18002cbd3  jz      loc_18002CE2D
0x18002cbd9  jmp     loc_18002CDE3
0x18002cbde  xor     edx, edx; bInheritHandle
0x18002cbe0  lea     r8, [rsp+278h+Name]; lpName
0x18002cbe5  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002cbe8  call    cs:__imp_OpenFileMappingW
0x18002cbee  mov     [rsi+20h], rax
0x18002cbf2  test    rax, rax
0x18002cbf5  jnz     short loc_18002CC5D
0x18002cbf7  xor     r9d, r9d; dwMaximumSizeHigh
0x18002cbfa  lea     rax, [rsp+278h+Name]
0x18002cbff  mov     [rsp+278h+lpName], rax; lpName
0x18002cc04  xor     edx, edx; lpFileMappingAttributes
0x18002cc06  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002cc0a  mov     [rsp+278h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x18002cc12  lea     r8d, [r9+4]; flProtect
0x18002cc16  call    cs:__imp_CreateFileMappingW
0x18002cc1c  mov     [rsi+20h], rax
0x18002cc20  test    rax, rax
0x18002cc23  jnz     short loc_18002CC59
0x18002cc25  call    cs:__imp_GetLastError
0x18002cc2b  mov     ebx, eax
0x18002cc2d  test    eax, eax
0x18002cc2f  jle     short loc_18002CC3A
0x18002cc31  movzx   ebx, ax
0x18002cc34  or      ebx, 80070000h
0x18002cc3a  test    rdi, rdi
0x18002cc3d  jz      loc_18002CDE3
0x18002cc43  mov     rcx, rdi; hMutex
0x18002cc46  call    cs:__imp_ReleaseMutex
0x18002cc4c  test    eax, eax
0x18002cc4e  jz      loc_18002CE40
0x18002cc54  jmp     loc_18002CDE3
0x18002cc59  xor     bl, bl
0x18002cc5b  jmp     short loc_18002CC5F
0x18002cc5d  mov     bl, 1
0x18002cc5f  xor     r9d, r9d; dwFileOffsetLow
0x18002cc62  mov     qword ptr [rsp+278h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18002cc6b  xor     r8d, r8d; dwFileOffsetHigh
0x18002cc6e  mov     edx, 0F001Fh; dwDesiredAccess
0x18002cc73  mov     rcx, rax; hFileMappingObject
0x18002cc76  call    cs:__imp_MapViewOfFile
0x18002cc7c  mov     [rsi+30h], rax
0x18002cc80  test    rax, rax
0x18002cc83  jnz     short loc_18002CCB9
0x18002cc85  call    cs:__imp_GetLastError
0x18002cc8b  mov     ebx, eax
0x18002cc8d  test    eax, eax
0x18002cc8f  jle     short loc_18002CC9A
0x18002cc91  movzx   ebx, ax
0x18002cc94  or      ebx, 80070000h
0x18002cc9a  test    rdi, rdi
0x18002cc9d  jz      loc_18002CDE3
0x18002cca3  mov     rcx, rdi; hMutex
0x18002cca6  call    cs:__imp_ReleaseMutex
0x18002ccac  test    eax, eax
0x18002ccae  jz      loc_18002CE53
0x18002ccb4  jmp     loc_18002CDE3
0x18002ccb9  test    bl, bl
0x18002ccbb  jnz     loc_18002CDB9
0x18002ccc1  mov     r12d, 30h ; '0'
0x18002ccc7  mov     dword ptr [rax+10h], 0
0x18002ccce  mov     ecx, r12d; unsigned __int64
0x18002ccd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ccd8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ccdd  lea     ebp, [r12-20h]
0x18002cce2  mov     rbx, rax
0x18002cce5  lea     r14d, [r12-28h]
0x18002ccea  test    rax, rax
0x18002cced  jz      short loc_18002CD28
0x18002ccef  xorps   xmm0, xmm0
0x18002ccf2  movups  xmmword ptr [rax], xmm0
0x18002ccf5  movups  xmmword ptr [rax+10h], xmm0
0x18002ccf9  movups  xmmword ptr [rax+20h], xmm0
0x18002ccfd  call    cs:__imp_GetProcessHeap
0x18002cd03  mov     [rbx], rax
0x18002cd06  mov     [rbx+20h], rbp
0x18002cd0a  mov     qword ptr [rbx+10h], 0
0x18002cd12  mov     qword ptr [rbx+18h], 0
0x18002cd1a  mov     qword ptr [rbx+28h], 0
0x18002cd22  mov     [rbx+8], r14
0x18002cd26  jmp     short loc_18002CD2A
0x18002cd28  xor     ebx, ebx
0x18002cd2a  mov     rax, [rsi+30h]
0x18002cd2e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cd35  mov     rcx, r12; unsigned __int64
0x18002cd38  mov     [rax], rbx
0x18002cd3b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cd40  mov     rbx, rax
0x18002cd43  test    rax, rax
0x18002cd46  jz      short loc_18002CD81
0x18002cd48  xorps   xmm0, xmm0
0x18002cd4b  movups  xmmword ptr [rax], xmm0
0x18002cd4e  movups  xmmword ptr [rax+10h], xmm0
0x18002cd52  movups  xmmword ptr [rax+20h], xmm0
0x18002cd56  call    cs:__imp_GetProcessHeap
0x18002cd5c  mov     [rbx], rax
0x18002cd5f  mov     [rbx+20h], rbp
0x18002cd63  mov     qword ptr [rbx+10h], 0
0x18002cd6b  mov     qword ptr [rbx+18h], 0
0x18002cd73  mov     qword ptr [rbx+28h], 0
0x18002cd7b  mov     [rbx+8], r14
0x18002cd7f  jmp     short loc_18002CD83
0x18002cd81  xor     ebx, ebx
0x18002cd83  mov     rax, [rsi+30h]
0x18002cd87  mov     [rax+8], rbx
0x18002cd8b  mov     rax, [rsi+30h]
0x18002cd8f  cmp     qword ptr [rax], 0
0x18002cd93  jz      short loc_18002CD9C
0x18002cd95  cmp     qword ptr [rax+8], 0
0x18002cd9a  jnz     short loc_18002CDB9
0x18002cd9c  test    rdi, rdi
0x18002cd9f  jz      short loc_18002CDB2
0x18002cda1  mov     rcx, rdi; hMutex
0x18002cda4  call    cs:__imp_ReleaseMutex
0x18002cdaa  test    eax, eax
0x18002cdac  jz      loc_18002CE79
0x18002cdb2  mov     ebx, 8007000Eh
0x18002cdb7  jmp     short loc_18002CDE3
0x18002cdb9  inc     dword ptr [rax+10h]
0x18002cdbc  test    rdi, rdi
0x18002cdbf  jz      short loc_18002CDCE
0x18002cdc1  mov     rcx, rdi; hMutex
0x18002cdc4  call    cs:__imp_ReleaseMutex
0x18002cdca  test    eax, eax
0x18002cdcc  jz      short loc_18002CE0C
0x18002cdce  mov     rcx, [rsi+30h]
0x18002cdd2  xor     ebx, ebx
0x18002cdd4  mov     rax, [rcx+8]
0x18002cdd8  mov     [rsi+10h], rax
0x18002cddc  mov     rax, [rcx]
0x18002cddf  mov     [rsi+8], rax
0x18002cde3  mov     eax, ebx
0x18002cde5  mov     rcx, [rsp+278h+var_38]
0x18002cded  xor     rcx, rsp; StackCookie
0x18002cdf0  call    __security_check_cookie
0x18002cdf5  mov     rbx, [rsp+278h+arg_10]
0x18002cdfd  add     rsp, 250h
0x18002ce04  pop     r14
0x18002ce06  pop     r12
0x18002ce08  pop     rdi
0x18002ce09  pop     rsi
0x18002ce0a  pop     rbp
0x18002ce0b  retn
0x18002ce0c  mov     rcx, [rsp+278h]; this
0x18002ce14  mov     edx, 0A15h; void *
0x18002ce19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ce1f  mov     rcx, [rsp+278h]; this
0x18002ce27  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002ce2d  mov     rcx, [rsp+278h]; this
0x18002ce35  mov     edx, 0A15h; void *
0x18002ce3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ce40  mov     rcx, [rsp+278h]; this
0x18002ce48  mov     edx, 0A15h; void *
0x18002ce4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ce53  mov     rcx, [rsp+278h]; this
0x18002ce5b  mov     edx, 0A15h; void *
0x18002ce60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ce66  mov     rcx, [rsp+278h]; this
0x18002ce6e  mov     edx, 0A0Bh; void *
0x18002ce73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002ce79  mov     rcx, [rsp+278h]; this
0x18002ce81  mov     edx, 0A15h; void *
0x18002ce86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
