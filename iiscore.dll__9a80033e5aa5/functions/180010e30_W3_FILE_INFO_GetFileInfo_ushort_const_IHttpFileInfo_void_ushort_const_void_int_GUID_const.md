# W3_FILE_INFO::GetFileInfo(ushort const *,IHttpFileInfo * *,void *,ushort const *,void *,int,_GUID const *)

- ea: `0x180010e30`
- end: `0x1800112fd`
- name: `?GetFileInfo@W3_FILE_INFO@@SAJPEBGPEAPEAVIHttpFileInfo@@PEAX02HPEBU_GUID@@@Z`
- size: `1229`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IHttpFileInfo **, void *, const unsigned __int16 *, HANDLE Token, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010810`

## callees

- `0x180010e30`
- `0x180011304`
- `0x180011390`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!wcschr` at `0x180010ed2`
- `msvcrt!wcschr` at `0x180010ed2`
- `msvcrt!_wcsupr` at `0x180010ec3`
- `msvcrt!_wcsupr` at `0x1800110c1`
- `msvcrt!_wcsupr` at `0x180010ec3`
- `msvcrt!_wcsupr` at `0x1800110c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010efa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800112e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f80`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010f71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010f71`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800110e1`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800110e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010fa7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010fa7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180011242`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180011242`
- `ntdll!NtQueryInformationFile` at `0x18001113a`
- `ntdll!NtQueryInformationFile` at `0x18001113a`
- `ntdll!RtlNtStatusToDosError` at `0x1800112b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800112b6`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180011065`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180011065`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011275`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011275`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800111fb`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800111fb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010eba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010f49`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800110b8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800111ed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001122b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010eba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010f49`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800110b8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800111ed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001122b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800110ac`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800110ac`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e97`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010fff`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e97`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010fff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011216`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011216`
- `iisutil!MakePathCanonicalizationProof` at `0x180010ea5`
- `iisutil!MakePathCanonicalizationProof` at `0x180010ea5`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010fbc`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010fbc`
- `W3TP!ThreadPoolSetInfo` at `0x180010f29`
- `W3TP!ThreadPoolSetInfo` at `0x180010f9c`
- `W3TP!ThreadPoolSetInfo` at `0x180010f29`
- `W3TP!ThreadPoolSetInfo` at `0x180010f9c`

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
0x180010e30  push    rbx
0x180010e32  push    rbp
0x180010e33  push    rdi
0x180010e34  push    r12
0x180010e36  push    r13
0x180010e38  push    r14
0x180010e3a  push    r15
0x180010e3c  sub     rsp, 380h
0x180010e43  mov     rax, cs:__security_cookie
0x180010e4a  xor     rax, rsp
0x180010e4d  mov     [rsp+3B8h+var_48], rax
0x180010e55  mov     rbp, [rsp+3B8h+Token]
0x180010e5d  mov     rdi, r8
0x180010e60  mov     r15, rdx
0x180010e63  mov     r14, rcx
0x180010e66  xor     r13d, r13d
0x180010e69  lea     rcx, [rsp+3B8h+var_248]; void *
0x180010e71  mov     [rdx], r13
0x180010e74  mov     r8d, 200h; Size
0x180010e7a  xor     edx, edx; Val
0x180010e7c  mov     r12, r9
0x180010e7f  call    memset_0
0x180010e84  mov     r8d, 100h
0x180010e8a  lea     rdx, [rsp+3B8h+var_248]
0x180010e92  lea     rcx, [rsp+3B8h+var_368]
0x180010e97  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180010e9d  lea     rdx, [rsp+3B8h+var_368]
0x180010ea2  mov     rcx, r14
0x180010ea5  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180010eab  mov     ebx, eax
0x180010ead  test    eax, eax
0x180010eaf  js      loc_180011270
0x180010eb5  lea     rcx, [rsp+3B8h+var_368]
0x180010eba  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010ec0  mov     rcx, rax; String
0x180010ec3  call    cs:__imp__wcsupr
0x180010ec9  mov     edx, 3Ah ; ':'; Ch
0x180010ece  lea     rcx, [r14+0Ch]; Str
0x180010ed2  call    cs:__imp_wcschr
0x180010ed8  test    rax, rax
0x180010edb  jnz     loc_1800112E8
0x180010ee1  mov     [rsp+3B8h+arg_18], rsi
0x180010ee9  test    rbp, rbp
0x180010eec  jz      loc_1800112A0
0x180010ef2  mov     rsi, rbp
0x180010ef5  mov     rdx, rsi; Token
0x180010ef8  xor     ecx, ecx; Thread
0x180010efa  call    cs:__imp_SetThreadToken
0x180010f00  test    eax, eax
0x180010f02  jnz     short loc_180010F25
0x180010f04  mov     rsi, r13
0x180010f07  call    cs:__imp_GetLastError
0x180010f0d  mov     ebx, eax
0x180010f0f  test    eax, eax
0x180010f11  jle     loc_180011261
0x180010f17  movzx   ebx, ax
0x180010f1a  or      ebx, 80070000h
0x180010f20  jmp     loc_180011261
0x180010f25  xor     edx, edx
0x180010f27  xor     ecx, ecx
0x180010f29  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x180010f2f  cmp     [rsp+3B8h+arg_28], r13d
0x180010f37  lea     rcx, [rsp+3B8h+var_368]
0x180010f3c  mov     eax, 6A000001h
0x180010f41  mov     edi, 4A000001h
0x180010f46  cmovz   edi, eax
0x180010f49  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010f4f  mov     [rsp+3B8h+hTemplateFile], r13; hTemplateFile
0x180010f54  xor     r9d, r9d; lpSecurityAttributes
0x180010f57  mov     rcx, rax; lpFileName
0x180010f5a  mov     [rsp+3B8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180010f5e  mov     edx, 80000000h; dwDesiredAccess
0x180010f63  mov     [rsp+3B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180010f6b  mov     r8d, 7; dwShareMode
0x180010f71  call    cs:__imp_CreateFileW
0x180010f77  mov     rdi, rax
0x180010f7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010f7e  jnz     short loc_180010F95
0x180010f80  call    cs:__imp_GetLastError
0x180010f86  mov     ebx, eax
0x180010f88  test    eax, eax
0x180010f8a  jle     short loc_180010F95
0x180010f8c  movzx   ebx, ax
0x180010f8f  or      ebx, 80070000h
0x180010f95  xor     edx, edx
0x180010f97  mov     ecx, 1
0x180010f9c  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x180010fa2  test    rsi, rsi
0x180010fa5  jz      short loc_180010FAD
0x180010fa7  call    cs:__imp_RevertToSelf
0x180010fad  test    ebx, ebx
0x180010faf  js      loc_1800112D7
0x180010fb5  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x180010fbc  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180010fc2  mov     rsi, rax
0x180010fc5  test    rax, rax
0x180010fc8  jz      loc_1800112F6
0x180010fce  lea     rax, ??_7W3_FILE_INFO@@6B@; const W3_FILE_INFO::`vftable'
0x180010fd5  mov     dword ptr [rsi+8], 49463357h
0x180010fdc  mov     [rsi], rax
0x180010fdf  lea     rdx, [rsi+50h]
0x180010fe3  lea     rax, ??_7W3_FILE_KEY@@6B@; const W3_FILE_KEY::`vftable'
0x180010fea  mov     dword ptr [rsi+0Ch], 1
0x180010ff1  lea     rcx, [rsi+18h]
0x180010ff5  mov     [rsi+10h], rax
0x180010ff9  mov     r8d, 100h
0x180010fff  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011005  mov     [rsi+250h], rdi
0x18001100c  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x180011013  mov     [rsi+268h], r13
0x18001101a  lea     rcx, [rsi+2E0h]
0x180011021  mov     [rsi+270h], r13d
0x180011028  mov     [rsi+274h], r13w
0x180011030  mov     [rsi+2B8h], r13
0x180011037  mov     qword ptr [rsi+2C0h], 0FFFFFFFFFFFFFFFFh
0x180011042  mov     [rsi+2C8h], rax
0x180011049  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x180011050  mov     [rsi+2D0h], rax
0x180011057  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18001105e  mov     [rsi+2D8h], rax
0x180011065  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001106b  mov     [rsi+2E8h], r13
0x180011072  lea     rcx, [rsi+18h]
0x180011076  mov     [rsi+2F0h], r13
0x18001107d  mov     rdx, r14
0x180011080  mov     [rsi+2F8h], r13d
0x180011087  mov     word ptr [rsi+2FCh], 1
0x180011090  mov     [rsi+2FEh], r13b
0x180011097  mov     [rsi+300h], r13
0x18001109e  mov     [rsi+308h], r13
0x1800110a5  mov     [rsi+310h], r13
0x1800110ac  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800110b2  lea     rcx, [rsi+18h]
0x1800110b6  mov     ebx, eax
0x1800110b8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800110be  mov     rcx, rax; String
0x1800110c1  call    cs:__imp__wcsupr
0x1800110c7  test    ebx, ebx
0x1800110c9  js      loc_1800112C6
0x1800110cf  mov     rax, [rsi]
0x1800110d2  mov     rcx, rsi
0x1800110d5  mov     rax, [rax+50h]
0x1800110d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110de  mov     rcx, rax; hFile
0x1800110e1  call    cs:__imp_GetFileType
0x1800110e7  cmp     eax, 1
0x1800110ea  jnz     loc_1800112EF
0x1800110f0  xorps   xmm0, xmm0
0x1800110f3  lea     rcx, [rsp+3B8h+FileInformation]; void *
0x1800110fb  xor     edx, edx; Val
0x1800110fd  mov     r8d, 68h ; 'h'; Size
0x180011103  movups  xmmword ptr [rsp+3B8h+IoStatusBlock], xmm0
0x180011108  call    memset_0
0x18001110d  mov     rax, [rsi]
0x180011110  mov     rcx, rsi
0x180011113  mov     rax, [rax+50h]
0x180011117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111c  mov     rcx, rax; FileHandle
0x18001111f  mov     [rsp+3B8h+dwCreationDisposition], 12h; FileInformationClass
0x180011127  mov     r9d, 68h ; 'h'; Length
0x18001112d  lea     r8, [rsp+3B8h+FileInformation]; FileInformation
0x180011135  lea     rdx, [rsp+3B8h+IoStatusBlock]; IoStatusBlock
0x18001113a  call    cs:__imp_NtQueryInformationFile
0x180011140  mov     ecx, eax
0x180011142  and     ecx, 0C0000000h
0x180011148  cmp     ecx, 0C0000000h
0x18001114e  jz      loc_1800112B4
0x180011154  mov     rcx, [rsp+3B8h+var_318]
0x18001115c  mov     [rsi+258h], rcx
0x180011163  mov     eax, [rsp+3B8h+var_308]
0x18001116a  mov     [rsi+268h], eax
0x180011170  mov     eax, [rsp+3B8h+var_2F8]
0x180011177  mov     [rsi+26Ch], eax
0x18001117d  mov     eax, [rsp+3B8h+var_2F4]
0x180011184  mov     [rsi+270h], eax
0x18001118a  mov     rax, 0D6BF94D5E57A42BDh
0x180011194  imul    rcx
0x180011197  add     rdx, rcx
0x18001119a  mov     rcx, rsi; this
0x18001119d  sar     rdx, 17h
0x1800111a1  mov     rax, rdx
0x1800111a4  shr     rax, 3Fh
0x1800111a8  add     rdx, rax
0x1800111ab  imul    rax, rdx, 989680h
0x1800111b2  mov     [rsi+260h], rax
0x1800111b9  call    ?GenerateETag@W3_FILE_INFO@@AEAAJXZ; W3_FILE_INFO::GenerateETag(void)
0x1800111be  mov     ebx, eax
0x1800111c0  test    eax, eax
0x1800111c2  js      loc_1800112C6
0x1800111c8  mov     rcx, rsi; this
0x1800111cb  call    ?GenerateLastModifiedTimeString@W3_FILE_INFO@@AEAAJXZ; W3_FILE_INFO::GenerateLastModifiedTimeString(void)
0x1800111d0  mov     ebx, eax
0x1800111d2  test    eax, eax
0x1800111d4  js      loc_1800112C6
0x1800111da  mov     eax, [rsi+268h]
0x1800111e0  test    al, 2
0x1800111e2  jz      short loc_180011253
0x1800111e4  test    al, 10h
0x1800111e6  jz      short loc_180011253
0x1800111e8  lea     rcx, [rsp+3B8h+var_368]
0x1800111ed  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800111f3  lea     rcx, [rsp+3B8h+var_368]
0x1800111f8  mov     rdi, rax
0x1800111fb  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180011201  dec     eax
0x180011203  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180011208  jz      short loc_180011226
0x18001120a  lea     rdx, asc_180039114; "\\"
0x180011211  lea     rcx, [rsp+3B8h+var_368]
0x180011216  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001121c  mov     ebx, eax
0x18001121e  test    eax, eax
0x180011220  js      loc_1800112C6
0x180011226  lea     rcx, [rsp+3B8h+var_368]
0x18001122b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011231  mov     r8d, 32h ; '2'; cchBufferLength
0x180011237  lea     rdx, [rsp+3B8h+szVolumeName]; lpszVolumeName
0x18001123f  mov     rcx, rax; lpszVolumeMountPoint
0x180011242  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180011248  test    eax, eax
0x18001124a  jz      short loc_180011253
0x18001124c  and     dword ptr [rsi+268h], 0FFFFFFFDh
0x180011253  mov     [rsi+2B8h], r12
0x18001125a  mov     [rsi+2C0h], rbp
0x180011261  test    ebx, ebx
0x180011263  js      short loc_1800112C1
0x180011265  mov     [r15], rsi
0x180011268  mov     rsi, [rsp+3B8h+arg_18]
0x180011270  lea     rcx, [rsp+3B8h+var_368]
0x180011275  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001127b  mov     eax, ebx
0x18001127d  mov     rcx, [rsp+3B8h+var_48]
0x180011285  xor     rcx, rsp; StackCookie
0x180011288  call    __security_check_cookie
0x18001128d  add     rsp, 380h
0x180011294  pop     r15
0x180011296  pop     r14
0x180011298  pop     r13
0x18001129a  pop     r12
0x18001129c  pop     rdi
0x18001129d  pop     rbp
0x18001129e  pop     rbx
0x18001129f  retn
0x1800112a0  mov     rsi, r13
0x1800112a3  test    rdi, rdi
0x1800112a6  jz      loc_180010F25
0x1800112ac  mov     rsi, rdi
0x1800112af  jmp     loc_180010EF5
0x1800112b4  mov     ecx, eax; Status
0x1800112b6  call    cs:__imp_RtlNtStatusToDosError
0x1800112bc  jmp     loc_180010F0D
0x1800112c1  test    rsi, rsi
0x1800112c4  jz      short loc_180011268
0x1800112c6  mov     rax, [rsi]
0x1800112c9  mov     rcx, rsi
0x1800112cc  mov     rax, [rax+10h]
0x1800112d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d5  jmp     short loc_180011268
0x1800112d7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800112db  jz      short loc_180011268
0x1800112dd  mov     rcx, rdi; hObject
0x1800112e0  call    cs:__imp_CloseHandle
0x1800112e6  jmp     short loc_180011268
0x1800112e8  mov     ebx, 80070002h
0x1800112ed  jmp     short loc_180011270
0x1800112ef  mov     ebx, 80070002h
0x1800112f4  jmp     short loc_1800112C6
0x1800112f6  mov     ebx, 80070008h
0x1800112fb  jmp     short loc_1800112D7
```
