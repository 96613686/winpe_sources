# W3_FILE_INFO::GetFileInfo(ushort const *,IHttpFileInfo * *,void *,ushort const *,void *,int,_GUID const *)

- ea: `0x180011c40`
- end: `0x1800121ce`
- name: `?GetFileInfo@W3_FILE_INFO@@SAJPEBGPEAPEAVIHttpFileInfo@@PEAX02HPEBU_GUID@@@Z`
- size: `1422`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IHttpFileInfo **, void *, const unsigned __int16 *, HANDLE Token, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800115b0`

## callees

- `0x180011c40`
- `0x1800121d4`
- `0x180012270`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!wcschr` at `0x180011cfa`
- `msvcrt!wcschr` at `0x180011cfa`
- `msvcrt!_wcsupr` at `0x180011ce5`
- `msvcrt!_wcsupr` at `0x180011f3d`
- `msvcrt!_wcsupr` at `0x180011ce5`
- `msvcrt!_wcsupr` at `0x180011f3d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011d28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dcc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011db7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011db7`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180011f63`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180011f63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011dff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011dff`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800120f0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800120f0`
- `ntdll!NtQueryInformationFile` at `0x180011fc2`
- `ntdll!NtQueryInformationFile` at `0x180011fc2`
- `ntdll!RtlNtStatusToDosError` at `0x180012171`
- `ntdll!RtlNtStatusToDosError` at `0x180012171`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180011ecf`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180011ecf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012129`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012129`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180012097`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180012097`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011cd6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011d89`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011f2e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012083`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800120d3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011cd6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011d89`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011f2e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012083`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800120d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011f1c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011f1c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011ca7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011e63`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011ca7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011e63`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800120b8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800120b8`
- `iisutil!MakePathCanonicalizationProof` at `0x180011cbb`
- `iisutil!MakePathCanonicalizationProof` at `0x180011cbb`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180011e1a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180011e1a`
- `W3TP!ThreadPoolSetInfo` at `0x180011d63`
- `W3TP!ThreadPoolSetInfo` at `0x180011dee`
- `W3TP!ThreadPoolSetInfo` at `0x180011d63`
- `W3TP!ThreadPoolSetInfo` at `0x180011dee`

## pseudocode

```c
__int64 __fastcall W3_FILE_INFO::GetFileInfo(
        const unsigned __int16 *a1,
        struct IHttpFileInfo **a2,
        void *a3,
        const unsigned __int16 *a4,
        HANDLE Token,
        int a6)
{
  signed int PathCanonicalizationProof; // ebx
  wchar_t *Str; // rax
  HANDLE v12; // rsi
  unsigned __int16 *v13; // rsi
  signed int LastError; // eax
  DWORD dwFlagsAndAttributes; // edi
  const WCHAR *v16; // rax
  HANDLE FileW; // rdi
  signed int v18; // eax
  unsigned __int16 *v19; // rax
  wchar_t *v20; // rax
  void *v21; // rax
  void *v22; // rax
  NTSTATUS v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  unsigned __int16 *v26; // rdi
  const WCHAR *v27; // rax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-378h] BYREF
  _BYTE v30[64]; // [rsp+50h] [rbp-368h] BYREF
  _BYTE FileInformation[16]; // [rsp+90h] [rbp-328h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-318h]
  int v33; // [rsp+B0h] [rbp-308h]
  int v34; // [rsp+C0h] [rbp-2F8h]
  int v35; // [rsp+C4h] [rbp-2F4h]
  WCHAR szVolumeName[56]; // [rsp+100h] [rbp-2B8h] BYREF
  unsigned __int16 v37[256]; // [rsp+170h] [rbp-248h] BYREF

  *a2 = 0;
  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v30, v37, 0x100u);
  PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v30);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_32;
  Str = STRU::QueryStr((STRU *)v30);
  _wcsupr(Str);
  if ( wcschr(a1 + 6, 0x3Au) )
  {
    PathCanonicalizationProof = -2147024894;
    goto LABEL_32;
  }
  if ( Token )
  {
    v12 = Token;
    goto LABEL_5;
  }
  v12 = 0;
  if ( a3 )
  {
    v12 = a3;
LABEL_5:
    if ( !SetThreadToken(0, v12) )
    {
      v13 = 0;
      LastError = GetLastError();
      goto LABEL_7;
    }
  }
  ThreadPoolSetInfo(0, 0);
  dwFlagsAndAttributes = 1241513985;
  if ( !a6 )
    dwFlagsAndAttributes = 1778384897;
  v16 = STRU::QueryStr((STRU *)v30);
  FileW = CreateFileW(v16, 0x80000000, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v18 = GetLastError();
    PathCanonicalizationProof = v18;
    if ( v18 > 0 )
      PathCanonicalizationProof = (unsigned __int16)v18 | 0x80070000;
  }
  ThreadPoolSetInfo(1, 0);
  if ( v12 )
    RevertToSelf();
  if ( PathCanonicalizationProof >= 0 )
  {
    v19 = (unsigned __int16 *)ALLOC_CACHE_HANDLER::Alloc(W3_FILE_INFO::sm_pachW3FileInfo);
    v13 = v19;
    if ( v19 )
    {
      *((_DWORD *)v19 + 2) = 1229337431;
      *(_QWORD *)v19 = &W3_FILE_INFO::`vftable';
      *((_DWORD *)v19 + 3) = 1;
      *((_QWORD *)v19 + 2) = &W3_FILE_KEY::`vftable';
      STRU::STRU((STRU *)(v19 + 12), v19 + 40, 0x100u);
      *((_QWORD *)v13 + 74) = FileW;
      *((_QWORD *)v13 + 77) = 0;
      *((_DWORD *)v13 + 156) = 0;
      v13[314] = 0;
      *((_QWORD *)v13 + 87) = 0;
      *((_QWORD *)v13 + 88) = -1;
      *((_QWORD *)v13 + 89) = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
      *((_QWORD *)v13 + 90) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
      *((_QWORD *)v13 + 91) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
      CReaderWriterLock3::CReaderWriterLock3((CReaderWriterLock3 *)(v13 + 368));
      *((_QWORD *)v13 + 93) = 0;
      *((_QWORD *)v13 + 94) = 0;
      *((_DWORD *)v13 + 190) = 0;
      v13[382] = 1;
      *((_BYTE *)v13 + 766) = 0;
      *((_QWORD *)v13 + 96) = 0;
      *((_QWORD *)v13 + 97) = 0;
      *((_QWORD *)v13 + 98) = 0;
      PathCanonicalizationProof = STRU::Copy((STRU *)(v13 + 12), a1);
      v20 = STRU::QueryStr((STRU *)(v13 + 12));
      _wcsupr(v20);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_37;
      v21 = (void *)(*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 80LL))(v13);
      if ( GetFileType(v21) != 1 )
      {
        PathCanonicalizationProof = -2147024894;
        goto LABEL_37;
      }
      IoStatusBlock = 0;
      memset_0(FileInformation, 0, 0x68u);
      v22 = (void *)(*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 80LL))(v13);
      v23 = NtQueryInformationFile(v22, &IoStatusBlock, FileInformation, 0x68u, FileAllInformation);
      if ( (v23 & 0xC0000000) != 0xC0000000 )
      {
        v24 = v32;
        *((_QWORD *)v13 + 75) = v32;
        *((_DWORD *)v13 + 154) = v33;
        *((_DWORD *)v13 + 155) = v34;
        *((_DWORD *)v13 + 156) = v35;
        *((_QWORD *)v13 + 76) = 10000000 * (v24 / 10000000);
        PathCanonicalizationProof = W3_FILE_INFO::GenerateETag((W3_FILE_INFO *)v13);
        if ( PathCanonicalizationProof < 0 )
          goto LABEL_37;
        PathCanonicalizationProof = W3_FILE_INFO::GenerateLastModifiedTimeString((W3_FILE_INFO *)v13);
        if ( PathCanonicalizationProof < 0 )
          goto LABEL_37;
        v25 = *((_DWORD *)v13 + 154);
        if ( (v25 & 2) != 0 && (v25 & 0x10) != 0 )
        {
          v26 = STRU::QueryStr((STRU *)v30);
          if ( v26[STRU::QueryCCH((STRU *)v30) - 1] != 92 )
          {
            PathCanonicalizationProof = STRU::Append((STRU *)v30, L"\\");
            if ( PathCanonicalizationProof < 0 )
              goto LABEL_37;
          }
          v27 = STRU::QueryStr((STRU *)v30);
          if ( GetVolumeNameForVolumeMountPointW(v27, szVolumeName, 0x32u) )
            *((_DWORD *)v13 + 154) &= ~2u;
        }
        *((_QWORD *)v13 + 87) = a4;
        *((_QWORD *)v13 + 88) = Token;
        goto LABEL_30;
      }
      LastError = RtlNtStatusToDosError(v23);
LABEL_7:
      PathCanonicalizationProof = LastError;
      if ( LastError > 0 )
        PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
      if ( PathCanonicalizationProof >= 0 )
      {
        *a2 = (struct IHttpFileInfo *)v13;
        goto LABEL_32;
      }
      if ( !v13 )
        goto LABEL_32;
LABEL_37:
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_32;
    }
    PathCanonicalizationProof = -2147024888;
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
LABEL_32:
  STRU::~STRU((STRU *)v30);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180011c40  push    rbx
0x180011c42  push    rbp
0x180011c43  push    rdi
0x180011c44  push    r12
0x180011c46  push    r13
0x180011c48  push    r14
0x180011c4a  push    r15
0x180011c4c  sub     rsp, 380h
0x180011c53  mov     rax, cs:__security_cookie
0x180011c5a  xor     rax, rsp
0x180011c5d  mov     [rsp+3B8h+var_48], rax
0x180011c65  mov     rbp, [rsp+3B8h+Token]
0x180011c6d  mov     rdi, r8
0x180011c70  mov     r15, rdx
0x180011c73  mov     r14, rcx
0x180011c76  xor     r13d, r13d
0x180011c79  lea     rcx, [rsp+3B8h+var_248]; void *
0x180011c81  mov     [rdx], r13
0x180011c84  mov     r8d, 200h; Size
0x180011c8a  xor     edx, edx; Val
0x180011c8c  mov     r12, r9
0x180011c8f  call    memset_0
0x180011c94  mov     r8d, 100h
0x180011c9a  lea     rdx, [rsp+3B8h+var_248]
0x180011ca2  lea     rcx, [rsp+3B8h+var_368]
0x180011ca7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011cae  nop     dword ptr [rax+rax+00h]
0x180011cb3  lea     rdx, [rsp+3B8h+var_368]
0x180011cb8  mov     rcx, r14
0x180011cbb  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180011cc2  nop     dword ptr [rax+rax+00h]
0x180011cc7  mov     ebx, eax
0x180011cc9  test    eax, eax
0x180011ccb  js      loc_180012124
0x180011cd1  lea     rcx, [rsp+3B8h+var_368]
0x180011cd6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011cdd  nop     dword ptr [rax+rax+00h]
0x180011ce2  mov     rcx, rax; String
0x180011ce5  call    cs:__imp__wcsupr
0x180011cec  nop     dword ptr [rax+rax+00h]
0x180011cf1  mov     edx, 3Ah ; ':'; Ch
0x180011cf6  lea     rcx, [r14+0Ch]; Str
0x180011cfa  call    cs:__imp_wcschr
0x180011d01  nop     dword ptr [rax+rax+00h]
0x180011d06  test    rax, rax
0x180011d09  jnz     loc_1800121B6
0x180011d0f  mov     [rsp+3B8h+arg_18], rsi
0x180011d17  test    rbp, rbp
0x180011d1a  jz      loc_18001215B
0x180011d20  mov     rsi, rbp
0x180011d23  mov     rdx, rsi; Token
0x180011d26  xor     ecx, ecx; Thread
0x180011d28  call    cs:__imp_SetThreadToken
0x180011d2f  nop     dword ptr [rax+rax+00h]
0x180011d34  test    eax, eax
0x180011d36  jnz     short loc_180011D5F
0x180011d38  mov     rsi, r13
0x180011d3b  call    cs:__imp_GetLastError
0x180011d42  nop     dword ptr [rax+rax+00h]
0x180011d47  mov     ebx, eax
0x180011d49  test    eax, eax
0x180011d4b  jle     loc_180012115
0x180011d51  movzx   ebx, ax
0x180011d54  or      ebx, 80070000h
0x180011d5a  jmp     loc_180012115
0x180011d5f  xor     edx, edx
0x180011d61  xor     ecx, ecx
0x180011d63  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x180011d6a  nop     dword ptr [rax+rax+00h]
0x180011d6f  cmp     [rsp+3B8h+arg_28], r13d
0x180011d77  lea     rcx, [rsp+3B8h+var_368]
0x180011d7c  mov     eax, 6A000001h
0x180011d81  mov     edi, 4A000001h
0x180011d86  cmovz   edi, eax
0x180011d89  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011d90  nop     dword ptr [rax+rax+00h]
0x180011d95  mov     [rsp+3B8h+hTemplateFile], r13; hTemplateFile
0x180011d9a  xor     r9d, r9d; lpSecurityAttributes
0x180011d9d  mov     rcx, rax; lpFileName
0x180011da0  mov     [rsp+3B8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180011da4  mov     edx, 80000000h; dwDesiredAccess
0x180011da9  mov     [rsp+3B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180011db1  mov     r8d, 7; dwShareMode
0x180011db7  call    cs:__imp_CreateFileW
0x180011dbe  nop     dword ptr [rax+rax+00h]
0x180011dc3  mov     rdi, rax
0x180011dc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011dca  jnz     short loc_180011DE7
0x180011dcc  call    cs:__imp_GetLastError
0x180011dd3  nop     dword ptr [rax+rax+00h]
0x180011dd8  mov     ebx, eax
0x180011dda  test    eax, eax
0x180011ddc  jle     short loc_180011DE7
0x180011dde  movzx   ebx, ax
0x180011de1  or      ebx, 80070000h
0x180011de7  xor     edx, edx
0x180011de9  mov     ecx, 1
0x180011dee  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x180011df5  nop     dword ptr [rax+rax+00h]
0x180011dfa  test    rsi, rsi
0x180011dfd  jz      short loc_180011E0B
0x180011dff  call    cs:__imp_RevertToSelf
0x180011e06  nop     dword ptr [rax+rax+00h]
0x180011e0b  test    ebx, ebx
0x180011e0d  js      loc_180012198
0x180011e13  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x180011e1a  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180011e21  nop     dword ptr [rax+rax+00h]
0x180011e26  mov     rsi, rax
0x180011e29  test    rax, rax
0x180011e2c  jz      loc_1800121C7
0x180011e32  lea     rax, ??_7W3_FILE_INFO@@6B@; const W3_FILE_INFO::`vftable'
0x180011e39  mov     dword ptr [rsi+8], 49463357h
0x180011e40  mov     [rsi], rax
0x180011e43  lea     rdx, [rsi+50h]
0x180011e47  lea     rax, ??_7W3_FILE_KEY@@6B@; const W3_FILE_KEY::`vftable'
0x180011e4e  mov     dword ptr [rsi+0Ch], 1
0x180011e55  lea     rcx, [rsi+18h]
0x180011e59  mov     [rsi+10h], rax
0x180011e5d  mov     r8d, 100h
0x180011e63  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011e6a  nop     dword ptr [rax+rax+00h]
0x180011e6f  mov     [rsi+250h], rdi
0x180011e76  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x180011e7d  mov     [rsi+268h], r13
0x180011e84  lea     rcx, [rsi+2E0h]
0x180011e8b  mov     [rsi+270h], r13d
0x180011e92  mov     [rsi+274h], r13w
0x180011e9a  mov     [rsi+2B8h], r13
0x180011ea1  mov     qword ptr [rsi+2C0h], 0FFFFFFFFFFFFFFFFh
0x180011eac  mov     [rsi+2C8h], rax
0x180011eb3  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x180011eba  mov     [rsi+2D0h], rax
0x180011ec1  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x180011ec8  mov     [rsi+2D8h], rax
0x180011ecf  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180011ed6  nop     dword ptr [rax+rax+00h]
0x180011edb  mov     [rsi+2E8h], r13
0x180011ee2  lea     rcx, [rsi+18h]
0x180011ee6  mov     [rsi+2F0h], r13
0x180011eed  mov     rdx, r14
0x180011ef0  mov     [rsi+2F8h], r13d
0x180011ef7  mov     word ptr [rsi+2FCh], 1
0x180011f00  mov     [rsi+2FEh], r13b
0x180011f07  mov     [rsi+300h], r13
0x180011f0e  mov     [rsi+308h], r13
0x180011f15  mov     [rsi+310h], r13
0x180011f1c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011f23  nop     dword ptr [rax+rax+00h]
0x180011f28  lea     rcx, [rsi+18h]
0x180011f2c  mov     ebx, eax
0x180011f2e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011f35  nop     dword ptr [rax+rax+00h]
0x180011f3a  mov     rcx, rax; String
0x180011f3d  call    cs:__imp__wcsupr
0x180011f44  nop     dword ptr [rax+rax+00h]
0x180011f49  test    ebx, ebx
0x180011f4b  js      loc_180012187
0x180011f51  mov     rax, [rsi]
0x180011f54  mov     rcx, rsi
0x180011f57  mov     rax, [rax+50h]
0x180011f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f60  mov     rcx, rax; hFile
0x180011f63  call    cs:__imp_GetFileType
0x180011f6a  nop     dword ptr [rax+rax+00h]
0x180011f6f  cmp     eax, 1
0x180011f72  jnz     loc_1800121C0
0x180011f78  xorps   xmm0, xmm0
0x180011f7b  lea     rcx, [rsp+3B8h+FileInformation]; void *
0x180011f83  xor     edx, edx; Val
0x180011f85  mov     r8d, 68h ; 'h'; Size
0x180011f8b  movups  xmmword ptr [rsp+3B8h+IoStatusBlock], xmm0
0x180011f90  call    memset_0
0x180011f95  mov     rax, [rsi]
0x180011f98  mov     rcx, rsi
0x180011f9b  mov     rax, [rax+50h]
0x180011f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa4  mov     rcx, rax; FileHandle
0x180011fa7  mov     [rsp+3B8h+dwCreationDisposition], 12h; FileInformationClass
0x180011faf  mov     r9d, 68h ; 'h'; Length
0x180011fb5  lea     r8, [rsp+3B8h+FileInformation]; FileInformation
0x180011fbd  lea     rdx, [rsp+3B8h+IoStatusBlock]; IoStatusBlock
0x180011fc2  call    cs:__imp_NtQueryInformationFile
0x180011fc9  nop     dword ptr [rax+rax+00h]
0x180011fce  mov     ecx, eax
0x180011fd0  and     ecx, 0C0000000h
0x180011fd6  cmp     ecx, 0C0000000h
0x180011fdc  jz      loc_18001216F
0x180011fe2  mov     rcx, [rsp+3B8h+var_318]
0x180011fea  mov     [rsi+258h], rcx
0x180011ff1  mov     eax, [rsp+3B8h+var_308]
0x180011ff8  mov     [rsi+268h], eax
0x180011ffe  mov     eax, [rsp+3B8h+var_2F8]
0x180012005  mov     [rsi+26Ch], eax
0x18001200b  mov     eax, [rsp+3B8h+var_2F4]
0x180012012  mov     [rsi+270h], eax
0x180012018  mov     rax, 0D6BF94D5E57A42BDh
0x180012022  imul    rcx
0x180012025  add     rdx, rcx
0x180012028  mov     rcx, rsi; this
0x18001202b  sar     rdx, 17h
0x18001202f  mov     rax, rdx
0x180012032  shr     rax, 3Fh
0x180012036  add     rdx, rax
0x180012039  imul    rax, rdx, 989680h
0x180012040  mov     [rsi+260h], rax
0x180012047  call    ?GenerateETag@W3_FILE_INFO@@AEAAJXZ; W3_FILE_INFO::GenerateETag(void)
0x18001204c  mov     ebx, eax
0x18001204e  test    eax, eax
0x180012050  js      loc_180012187
0x180012056  mov     rcx, rsi; this
0x180012059  call    ?GenerateLastModifiedTimeString@W3_FILE_INFO@@AEAAJXZ; W3_FILE_INFO::GenerateLastModifiedTimeString(void)
0x18001205e  mov     ebx, eax
0x180012060  test    eax, eax
0x180012062  js      loc_180012187
0x180012068  mov     eax, [rsi+268h]
0x18001206e  test    al, 2
0x180012070  jz      loc_180012107
0x180012076  test    al, 10h
0x180012078  jz      loc_180012107
0x18001207e  lea     rcx, [rsp+3B8h+var_368]
0x180012083  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001208a  nop     dword ptr [rax+rax+00h]
0x18001208f  lea     rcx, [rsp+3B8h+var_368]
0x180012094  mov     rdi, rax
0x180012097  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001209e  nop     dword ptr [rax+rax+00h]
0x1800120a3  dec     eax
0x1800120a5  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x1800120aa  jz      short loc_1800120CE
0x1800120ac  lea     rdx, asc_18003C114; "\\"
0x1800120b3  lea     rcx, [rsp+3B8h+var_368]
0x1800120b8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800120bf  nop     dword ptr [rax+rax+00h]
0x1800120c4  mov     ebx, eax
0x1800120c6  test    eax, eax
0x1800120c8  js      loc_180012187
0x1800120ce  lea     rcx, [rsp+3B8h+var_368]
0x1800120d3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800120da  nop     dword ptr [rax+rax+00h]
0x1800120df  mov     r8d, 32h ; '2'; cchBufferLength
0x1800120e5  lea     rdx, [rsp+3B8h+szVolumeName]; lpszVolumeName
0x1800120ed  mov     rcx, rax; lpszVolumeMountPoint
0x1800120f0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800120f7  nop     dword ptr [rax+rax+00h]
0x1800120fc  test    eax, eax
0x1800120fe  jz      short loc_180012107
0x180012100  and     dword ptr [rsi+268h], 0FFFFFFFDh
0x180012107  mov     [rsi+2B8h], r12
0x18001210e  mov     [rsi+2C0h], rbp
0x180012115  test    ebx, ebx
0x180012117  js      short loc_180012182
0x180012119  mov     [r15], rsi
0x18001211c  mov     rsi, [rsp+3B8h+arg_18]
0x180012124  lea     rcx, [rsp+3B8h+var_368]
0x180012129  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012130  nop     dword ptr [rax+rax+00h]
0x180012135  mov     eax, ebx
0x180012137  mov     rcx, [rsp+3B8h+var_48]
0x18001213f  xor     rcx, rsp; StackCookie
0x180012142  call    __security_check_cookie
0x180012147  add     rsp, 380h
0x18001214e  pop     r15
0x180012150  pop     r14
0x180012152  pop     r13
0x180012154  pop     r12
0x180012156  pop     rdi
0x180012157  pop     rbp
0x180012158  pop     rbx
0x180012159  retn
0x18001215b  mov     rsi, r13
0x18001215e  test    rdi, rdi
0x180012161  jz      loc_180011D5F
0x180012167  mov     rsi, rdi
0x18001216a  jmp     loc_180011D23
0x18001216f  mov     ecx, eax; Status
0x180012171  call    cs:__imp_RtlNtStatusToDosError
0x180012178  nop     dword ptr [rax+rax+00h]
0x18001217d  jmp     loc_180011D47
0x180012182  test    rsi, rsi
0x180012185  jz      short loc_18001211C
0x180012187  mov     rax, [rsi]
0x18001218a  mov     rcx, rsi
0x18001218d  mov     rax, [rax+10h]
0x180012191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012196  jmp     short loc_18001211C
0x180012198  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001219c  jz      loc_18001211C
0x1800121a2  mov     rcx, rdi; hObject
0x1800121a5  call    cs:__imp_CloseHandle
0x1800121ac  nop     dword ptr [rax+rax+00h]
0x1800121b1  jmp     loc_18001211C
0x1800121b6  mov     ebx, 80070002h
0x1800121bb  jmp     loc_180012124
0x1800121c0  mov     ebx, 80070002h
0x1800121c5  jmp     short loc_180012187
0x1800121c7  mov     ebx, 80070008h
0x1800121cc  jmp     short loc_180012198
```
