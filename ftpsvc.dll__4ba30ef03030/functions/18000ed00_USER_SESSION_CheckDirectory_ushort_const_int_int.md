# USER_SESSION::CheckDirectory(ushort const *,int *,int)

- ea: `0x18000ed00`
- end: `0x18000f192`
- name: `?CheckDirectory@USER_SESSION@@UEAAJPEBGPEAHH@Z`
- size: `1170`
- prototype: `__int64 __fastcall(USER_SESSION *__hidden this, const unsigned __int16 *, int *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800022b8`
- `0x18000ed00`
- `0x18000fdd8`
- `0x1800116a4`
- `0x1800128d8`
- `0x1800129c0`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetFileInformationByHandle` at `0x18000efd5`
- `KERNEL32!GetFileInformationByHandle` at `0x18000efd5`
- `KERNEL32!CreateFileW` at `0x18000eeb3`
- `KERNEL32!CreateFileW` at `0x18000ef79`
- `KERNEL32!CreateFileW` at `0x18000eeb3`
- `KERNEL32!CreateFileW` at `0x18000ef79`
- `KERNEL32!GetLastError` at `0x18000eedc`
- `KERNEL32!GetLastError` at `0x18000ef9b`
- `KERNEL32!GetLastError` at `0x18000efe3`
- `KERNEL32!GetLastError` at `0x18000eedc`
- `KERNEL32!GetLastError` at `0x18000ef9b`
- `KERNEL32!GetLastError` at `0x18000efe3`
- `KERNEL32!CloseHandle` at `0x18000f057`
- `KERNEL32!CloseHandle` at `0x18000f057`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f09b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f09b`
- `iisutil!PuDbgPrint` at `0x18000ef2e`
- `iisutil!PuDbgPrint` at `0x18000ef2e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ed7e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ed7e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ee01`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ee01`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18000f186`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18000f186`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0b0`

## string_xrefs

- `0x18000efb0`: `File system denied the access.`
- `0x18000ef07`: `CreateFileW(%S) failed with 0x%x.\n`
- `0x18000ef13`: `USER_SESSION::CheckDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall USER_SESSION::CheckDirectory(USER_SESSION *this, const unsigned __int16 *a2, int *a3, int a4)
{
  __int64 FileW; // r15
  signed int v9; // edi
  volatile signed __int32 *v10; // rsi
  __int64 v11; // rax
  const unsigned __int16 *v12; // rbx
  struct CEtwTracer *v13; // rax
  int v14; // ebx
  signed int LastError; // eax
  const wchar_t *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  __int64 v19; // rax
  const unsigned __int16 *v20; // rbx
  struct CEtwTracer *v21; // rax
  __int64 v23; // rax
  CEtwTracer *v24; // rax
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  TOKEN_CACHE_ENTRY *v26; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+80h] [rbp-80h]
  __int16 v30; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+92h] [rbp-6Eh]
  __int128 v32; // [rsp+A2h] [rbp-5Eh]
  _BYTE v33[22]; // [rsp+B2h] [rbp-4Eh]
  int v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+CCh] [rbp-34h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v37[264]; // [rsp+110h] [rbp+10h] BYREF

  v25 = 0;
  v26 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  FileW = -1;
  memset_0(v37, 0, 0x208u);
  STRU::STRU((STRU *)v27, v37, 0x104u);
  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  v9 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)a2, 21, v27, 0, &v26, a4);
  v10 = (volatile signed __int32 *)v26;
  if ( v9 < 0 )
    goto LABEL_28;
  if ( !v29 && *((_DWORD *)this + 3) == 5 )
  {
    v9 = 0;
    goto LABEL_34;
  }
  if ( lpFileName[v29 - 1] != 92 )
  {
    v9 = STRU::Append((STRU *)v27, L"\\");
    if ( v9 < 0 )
      goto LABEL_28;
  }
  v9 = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v10, &v25);
  if ( v9 < 0 )
    goto LABEL_28;
  v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v11 + 8) && (*(_BYTE *)(v11 + 40) & 0x11) != 0 && *(_DWORD *)(v11 + 44) >= 5u )
  {
    v12 = lpFileName;
    v13 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(v13, (const struct _GUID *)((char *)this + 1272), v12);
  }
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
  v14 = 3;
  FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        1823,
        "USER_SESSION::CheckDirectory",
        "CreateFileW(%S) failed with 0x%x.\r\n",
        lpFileName,
        v9);
    if ( v9 != -2147024891 )
    {
      v16 = L"File system returned an error.";
      goto LABEL_23;
    }
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
    FileW = (__int64)CreateFileW(lpFileName, 0x40000000u, 3u, 0, 3u, 0x2000000u, 0);
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
    if ( FileW == -1 )
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      v16 = L"File system denied the access.";
      v14 = 2;
LABEL_23:
      *((_DWORD *)this + 278) = v14;
      *((_QWORD *)this + 138) = v16;
      if ( v9 < 0 )
        goto LABEL_28;
    }
  }
  if ( GetFileInformationByHandle((HANDLE)FileW, &FileInformation) )
  {
    if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
    {
      v9 = 0;
      v23 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v23 + 8) && (*(_BYTE *)(v23 + 40) & 0x11) != 0 && *(_DWORD *)(v23 + 44) >= 5u )
      {
        v24 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        v31 = 0;
        v32 = 0;
        *(_OWORD *)v33 = 0;
        v35 = 0;
        *(_DWORD *)&v33[10] = 1703936;
        v30 = 64;
        WORD2(v31) = 1;
        BYTE2(v31) = 2;
        *(_QWORD *)((char *)&v32 + 6) = &`FtpFileSystemAccessEvents::GetAreaGuid'::`2'::AreaGuid;
        *(_QWORD *)&v33[14] = (char *)this + 1272;
        v34 = 16;
        CEtwTracer::EtwTraceEvent(v24, (struct _EVENT_TRACE_HEADER *)&v30);
      }
      goto LABEL_32;
    }
    v9 = -2147024893;
  }
  else
  {
    v18 = GetLastError();
    v9 = v18;
    if ( v18 > 0 )
      v9 = (unsigned __int16)v18 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_32;
  }
LABEL_28:
  v19 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v19 + 8) && (*(_BYTE *)(v19 + 40) & 0x11) != 0 && *(_DWORD *)(v19 + 44) >= 2u )
  {
    v20 = lpFileName;
    v21 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpFileSystemAccessEvents::FailedCreateFile::RaiseEvent(v21, (const struct _GUID *)((char *)this + 1272), v20, v9);
  }
LABEL_32:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
LABEL_34:
  if ( v25 )
  {
    USER_SESSION::RevertImpersonation(this);
    v25 = 0;
  }
  if ( v10 && _InterlockedExchangeAdd(v10 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v10);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v10);
  }
  if ( a3 )
    *a3 = 0;
  STRU::~STRU(v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ed00  push    rbp
0x18000ed02  push    rbx
0x18000ed03  push    rsi
0x18000ed04  push    rdi
0x18000ed05  push    r12
0x18000ed07  push    r13
0x18000ed09  push    r14
0x18000ed0b  push    r15
0x18000ed0d  lea     rbp, [rsp-238h]
0x18000ed15  sub     rsp, 338h
0x18000ed1c  mov     rax, cs:__security_cookie
0x18000ed23  xor     rax, rsp
0x18000ed26  mov     [rbp+270h+var_50], rax
0x18000ed2d  mov     ebx, r9d
0x18000ed30  mov     r12, r8
0x18000ed33  mov     rdi, rdx
0x18000ed36  mov     r14, rcx
0x18000ed39  xor     r13d, r13d
0x18000ed3c  mov     [rsp+370h+var_330], r13d
0x18000ed41  mov     [rsp+370h+var_328], r13
0x18000ed46  xorps   xmm0, xmm0
0x18000ed49  xor     eax, eax
0x18000ed4b  movups  xmmword ptr [rbp+270h+FileInformation.dwFileAttributes], xmm0
0x18000ed4f  movups  xmmword ptr [rbp+270h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000ed53  movups  xmmword ptr [rbp+270h+FileInformation.nFileSizeHigh], xmm0
0x18000ed57  mov     [rbp+270h+FileInformation.nFileIndexLow], eax
0x18000ed5a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000ed5e  xor     edx, edx; Val
0x18000ed60  mov     r8d, 208h; Size
0x18000ed66  lea     rcx, [rbp+270h+var_260]; void *
0x18000ed6a  call    memset_0
0x18000ed6f  mov     r8d, 104h
0x18000ed75  lea     rdx, [rbp+270h+var_260]
0x18000ed79  lea     rcx, [rsp+370h+var_320]
0x18000ed7e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000ed84  nop
0x18000ed85  mov     [r14+458h], r13d
0x18000ed8c  lea     rax, WideCharStr
0x18000ed93  mov     [r14+450h], rax
0x18000ed9a  mov     dword ptr [rsp+370h+hTemplateFile], ebx
0x18000ed9e  lea     rax, [rsp+370h+var_328]
0x18000eda3  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18000eda8  mov     qword ptr [rsp+370h+dwCreationDisposition], r13
0x18000edad  lea     r9, [rsp+370h+var_320]
0x18000edb2  lea     r8d, [r13+15h]
0x18000edb6  mov     rdx, rdi
0x18000edb9  mov     rcx, r14
0x18000edbc  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x18000edc1  mov     edi, eax
0x18000edc3  mov     rsi, [rsp+370h+var_328]
0x18000edc8  test    eax, eax
0x18000edca  js      loc_18000EFFC
0x18000edd0  mov     eax, [rbp+270h+var_2F0]
0x18000edd3  test    eax, eax
0x18000edd5  jnz     short loc_18000EDE6
0x18000edd7  cmp     dword ptr [r14+0Ch], 5
0x18000eddc  jnz     short loc_18000EDE6
0x18000edde  mov     edi, r13d
0x18000ede1  jmp     loc_18000F05D
0x18000ede6  lea     ecx, [rax-1]
0x18000ede9  mov     rax, [rsp+370h+lpFileName]
0x18000edee  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000edf3  jz      short loc_18000EE11
0x18000edf5  lea     rdx, asc_18004BD10; "\\"
0x18000edfc  lea     rcx, [rsp+370h+var_320]
0x18000ee01  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000ee07  mov     edi, eax
0x18000ee09  test    eax, eax
0x18000ee0b  js      loc_18000EFFC
0x18000ee11  lea     r8, [rsp+370h+var_330]; int *
0x18000ee16  mov     rdx, rsi; struct TOKEN_CACHE_ENTRY *
0x18000ee19  mov     rcx, r14; this
0x18000ee1c  call    ?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z; USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)
0x18000ee21  mov     edi, eax
0x18000ee23  test    eax, eax
0x18000ee25  js      loc_18000EFFC
0x18000ee2b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ee32  mov     rax, [rcx]
0x18000ee35  mov     rax, [rax+20h]
0x18000ee39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee3e  cmp     [rax+8], r13d
0x18000ee42  jz      short loc_18000EE7A
0x18000ee44  test    byte ptr [rax+28h], 11h
0x18000ee48  jz      short loc_18000EE7A
0x18000ee4a  cmp     dword ptr [rax+2Ch], 5
0x18000ee4e  jb      short loc_18000EE7A
0x18000ee50  mov     rbx, [rsp+370h+lpFileName]
0x18000ee55  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ee5c  mov     rax, [rcx]
0x18000ee5f  mov     rax, [rax+20h]
0x18000ee63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee68  lea     rdx, [r14+4F8h]; struct _GUID *
0x18000ee6f  mov     r8, rbx; unsigned __int16 *
0x18000ee72  mov     rcx, rax; struct CEtwTracer *
0x18000ee75  call    ?RaiseEvent@StartCreateFile@FtpFileSystemAccessEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18000ee7a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ee81  mov     rax, [rcx]
0x18000ee84  mov     rax, [rax+40h]
0x18000ee88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee8d  mov     [rsp+370h+hTemplateFile], r13; hTemplateFile
0x18000ee92  mov     [rsp+370h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000ee9a  mov     ebx, 3
0x18000ee9f  mov     [rsp+370h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000eea3  xor     r9d, r9d; lpSecurityAttributes
0x18000eea6  mov     r8d, ebx; dwShareMode
0x18000eea9  mov     edx, 80000000h; dwDesiredAccess
0x18000eeae  mov     rcx, [rsp+370h+lpFileName]; lpFileName
0x18000eeb3  call    cs:__imp_CreateFileW
0x18000eeb9  mov     r15, rax
0x18000eebc  mov     rdx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000eec3  mov     rcx, [rdx]
0x18000eec6  mov     rax, [rcx+38h]
0x18000eeca  mov     rcx, rdx
0x18000eecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed2  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000eed6  jnz     loc_18000EFCE
0x18000eedc  call    cs:__imp_GetLastError
0x18000eee2  mov     edi, eax
0x18000eee4  test    eax, eax
0x18000eee6  jle     short loc_18000EEF1
0x18000eee8  movzx   edi, ax
0x18000eeeb  or      edi, 80070000h
0x18000eef1  test    byte ptr cs:g_dwDebugFlags, bl
0x18000eef7  jz      short loc_18000EF34
0x18000eef9  mov     dword ptr [rsp+370h+hTemplateFile], edi
0x18000eefd  mov     rax, [rsp+370h+lpFileName]
0x18000ef02  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18000ef07  lea     rax, aCreatefilewSFa; "CreateFileW(%S) failed with 0x%x.\r\n"
0x18000ef0e  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x18000ef13  lea     r9, aUserSessionChe; "USER_SESSION::CheckDirectory"
0x18000ef1a  mov     r8d, 71Fh
0x18000ef20  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000ef27  mov     rcx, cs:g_pDebug
0x18000ef2e  call    cs:__imp_PuDbgPrint
0x18000ef34  cmp     edi, 80070005h
0x18000ef3a  jz      short loc_18000EF45
0x18000ef3c  lea     rax, aFileSystemRetu; "File system returned an error."
0x18000ef43  jmp     short loc_18000EFBC
0x18000ef45  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ef4c  mov     rax, [rcx]
0x18000ef4f  mov     rax, [rax+40h]
0x18000ef53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef58  mov     [rsp+370h+hTemplateFile], r13; hTemplateFile
0x18000ef5d  mov     [rsp+370h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000ef65  mov     [rsp+370h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000ef69  xor     r9d, r9d; lpSecurityAttributes
0x18000ef6c  mov     r8d, ebx; dwShareMode
0x18000ef6f  mov     edx, 40000000h; dwDesiredAccess
0x18000ef74  mov     rcx, [rsp+370h+lpFileName]; lpFileName
0x18000ef79  call    cs:__imp_CreateFileW
0x18000ef7f  mov     r15, rax
0x18000ef82  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ef89  mov     rax, [rcx]
0x18000ef8c  mov     rax, [rax+38h]
0x18000ef90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef95  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000ef99  jnz     short loc_18000EFCE
0x18000ef9b  call    cs:__imp_GetLastError
0x18000efa1  mov     edi, eax
0x18000efa3  test    eax, eax
0x18000efa5  jle     short loc_18000EFB0
0x18000efa7  movzx   edi, ax
0x18000efaa  or      edi, 80070000h
0x18000efb0  lea     rax, aFileSystemDeni; "File system denied the access."
0x18000efb7  mov     ebx, 2
0x18000efbc  mov     [r14+458h], ebx
0x18000efc3  mov     [r14+450h], rax
0x18000efca  test    edi, edi
0x18000efcc  js      short loc_18000EFFC
0x18000efce  lea     rdx, [rbp+270h+FileInformation]; lpFileInformation
0x18000efd2  mov     rcx, r15; hFile
0x18000efd5  call    cs:__imp_GetFileInformationByHandle
0x18000efdb  test    eax, eax
0x18000efdd  jnz     loc_18000F0DB
0x18000efe3  call    cs:__imp_GetLastError
0x18000efe9  mov     edi, eax
0x18000efeb  test    eax, eax
0x18000efed  jle     short loc_18000EFF8
0x18000efef  movzx   edi, ax
0x18000eff2  or      edi, 80070000h
0x18000eff8  test    edi, edi
0x18000effa  jns     short loc_18000F04E
0x18000effc  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f003  mov     rax, [rcx]
0x18000f006  mov     rax, [rax+20h]
0x18000f00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f00f  cmp     [rax+8], r13d
0x18000f013  jz      short loc_18000F04E
0x18000f015  test    byte ptr [rax+28h], 11h
0x18000f019  jz      short loc_18000F04E
0x18000f01b  cmp     dword ptr [rax+2Ch], 2
0x18000f01f  jb      short loc_18000F04E
0x18000f021  mov     rbx, [rsp+370h+lpFileName]
0x18000f026  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f02d  mov     rax, [rcx]
0x18000f030  mov     rax, [rax+20h]
0x18000f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f039  lea     rdx, [r14+4F8h]; struct _GUID *
0x18000f040  mov     r9d, edi; unsigned int
0x18000f043  mov     r8, rbx; unsigned __int16 *
0x18000f046  mov     rcx, rax; struct CEtwTracer *
0x18000f049  call    ?RaiseEvent@FailedCreateFile@FtpFileSystemAccessEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBGK@Z; FtpFileSystemAccessEvents::FailedCreateFile::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *,ulong)
0x18000f04e  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000f052  jz      short loc_18000F05D
0x18000f054  mov     rcx, r15; hObject
0x18000f057  call    cs:__imp_CloseHandle
0x18000f05d  cmp     [rsp+370h+var_330], r13d
0x18000f062  jz      short loc_18000F071
0x18000f064  mov     rcx, r14; this
0x18000f067  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x18000f06c  mov     [rsp+370h+var_330], r13d
0x18000f071  test    rsi, rsi
0x18000f074  jz      short loc_18000F0A2
0x18000f076  or      eax, 0FFFFFFFFh
0x18000f079  lock xadd [rsi+14h], eax
0x18000f07e  cmp     eax, 1
0x18000f081  jnz     short loc_18000F0A2
0x18000f083  test    rsi, rsi
0x18000f086  jz      short loc_18000F0A2
0x18000f088  mov     rcx, rsi; this
0x18000f08b  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18000f090  nop
0x18000f091  mov     rdx, rsi
0x18000f094  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18000f09b  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f0a1  nop
0x18000f0a2  test    r12, r12
0x18000f0a5  jz      short loc_18000F0AB
0x18000f0a7  mov     [r12], r13d
0x18000f0ab  lea     rcx, [rsp+370h+var_320]
0x18000f0b0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f0b6  mov     eax, edi
0x18000f0b8  mov     rcx, [rbp+270h+var_50]
0x18000f0bf  xor     rcx, rsp; StackCookie
0x18000f0c2  call    __security_check_cookie
0x18000f0c7  add     rsp, 338h
0x18000f0ce  pop     r15
0x18000f0d0  pop     r14
0x18000f0d2  pop     r13
0x18000f0d4  pop     r12
0x18000f0d6  pop     rdi
0x18000f0d7  pop     rsi
0x18000f0d8  pop     rbx
0x18000f0d9  pop     rbp
0x18000f0da  retn
0x18000f0db  test    byte ptr [rbp+270h+FileInformation.dwFileAttributes], 10h
0x18000f0df  jnz     short loc_18000F0EB
0x18000f0e1  mov     edi, 80070003h
0x18000f0e6  jmp     loc_18000EFFC
0x18000f0eb  mov     edi, r13d
0x18000f0ee  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f0f5  mov     rax, [rcx]
0x18000f0f8  mov     rax, [rax+20h]
0x18000f0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f101  cmp     [rax+8], r13d
0x18000f105  jz      loc_18000F04E
0x18000f10b  test    byte ptr [rax+28h], 11h
0x18000f10f  jz      loc_18000F04E
0x18000f115  cmp     dword ptr [rax+2Ch], 5
0x18000f119  jb      loc_18000F04E
0x18000f11f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f126  mov     rax, [rcx]
0x18000f129  mov     rax, [rax+20h]
0x18000f12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f132  mov     rcx, rax
0x18000f135  xorps   xmm0, xmm0
0x18000f138  movups  [rbp+270h+var_2DE], xmm0
0x18000f13c  movups  [rbp+270h+var_2CE], xmm0
0x18000f140  movups  xmmword ptr [rbp+270h+var_2BE], xmm0
0x18000f144  movups  xmmword ptr [rbp+270h+var_2BE+0Eh], xmm0
0x18000f148  mov     dword ptr [rbp+270h+var_2BE+0Ah], 1A0000h
0x18000f14f  mov     eax, 40h ; '@'
0x18000f154  mov     [rbp+270h+var_2E0], ax
0x18000f158  mov     eax, 1
0x18000f15d  mov     word ptr [rbp+270h+var_2DE+4], ax
0x18000f161  mov     byte ptr [rbp+270h+var_2DE+2], 2
0x18000f165  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpFileSystemAccessEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpFileSystemAccessEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000f16c  mov     qword ptr [rbp+270h+var_2CE+6], rax
0x18000f170  lea     rax, [r14+4F8h]
0x18000f177  mov     qword ptr [rbp+270h+var_2BE+0Eh], rax
0x18000f17b  mov     [rbp+270h+var_2A8], 10h
0x18000f182  lea     rdx, [rbp+270h+var_2E0]
0x18000f186  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18000f18c  jmp     loc_18000F04E
```
