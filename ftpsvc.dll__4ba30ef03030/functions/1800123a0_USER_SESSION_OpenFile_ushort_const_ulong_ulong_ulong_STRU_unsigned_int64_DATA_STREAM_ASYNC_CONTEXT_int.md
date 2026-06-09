# USER_SESSION::OpenFile(ushort const *,ulong,ulong,ulong,STRU *,unsigned __int64 *,DATA_STREAM_ASYNC_CONTEXT *,int *)

- ea: `0x1800123a0`
- end: `0x18001285e`
- name: `?OpenFile@USER_SESSION@@UEAAJPEBGKKKPEAVSTRU@@PEA_KPEAVDATA_STREAM_ASYNC_CONTEXT@@PEAH@Z`
- size: `1214`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, signed int, DWORD, DWORD, const wchar_t **, unsigned __int64 *, struct DATA_STREAM_ASYNC_CONTEXT *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800022b8`
- `0x18000fdd8`
- `0x1800116a4`
- `0x1800123a0`
- `0x1800128d8`
- `0x1800129c0`
- `0x18001313c`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180012691`
- `KERNEL32!GetFileType` at `0x180012691`
- `KERNEL32!CreateFileW` at `0x1800124e6`
- `KERNEL32!CreateFileW` at `0x1800124e6`
- `KERNEL32!GetLastError` at `0x180012517`
- `KERNEL32!GetLastError` at `0x180012517`
- `KERNEL32!CloseHandle` at `0x180012602`
- `KERNEL32!CloseHandle` at `0x180012602`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001265d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001265d`
- `iisutil!PuDbgPrint` at `0x180012569`
- `iisutil!PuDbgPrint` at `0x1800126d7`
- `iisutil!PuDbgPrint` at `0x18001278f`
- `iisutil!PuDbgPrint` at `0x180012569`
- `iisutil!PuDbgPrint` at `0x1800126d7`
- `iisutil!PuDbgPrint` at `0x18001278f`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180012853`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180012853`

## string_xrefs

- `0x180012584`: `File system denied the access.`
- `0x180012542`: `CreateFileW(%S) failed with 0x%x.\n`
- `0x18001254e`: `USER_SESSION::OpenFile`
- `0x1800126bc`: `USER_SESSION::OpenFile`
- `0x180012774`: `USER_SESSION::OpenFile`
- `0x1800126e7`: `Attempt was made to open object that is not a file or directory.`
- `0x180012768`: `Denied read access. Max Allowed Content Length exceeded.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall USER_SESSION::OpenFile(
        USER_SESSION *this,
        const unsigned __int16 *a2,
        signed int a3,
        DWORD a4,
        DWORD a5,
        const wchar_t **a6,
        unsigned __int64 *a7,
        struct DATA_STREAM_ASYNC_CONTEXT *a8,
        int *a9)
{
  bool v11; // sf
  int v12; // r8d
  signed int v13; // edi
  volatile signed __int32 *v14; // r14
  __int64 v15; // rax
  const unsigned __int16 *v16; // rbx
  struct CEtwTracer *v17; // rax
  void *v18; // rcx
  signed int LastError; // eax
  const wchar_t *v20; // rax
  __int64 v21; // rax
  const unsigned __int16 *v22; // rbx
  struct CEtwTracer *v23; // rax
  void *v24; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rax
  CEtwTracer *v28; // rax
  int v29; // [rsp+40h] [rbp-81h] BYREF
  DWORD dwCreationDisposition; // [rsp+44h] [rbp-7Dh]
  DWORD dwShareMode; // [rsp+48h] [rbp-79h]
  unsigned __int64 v32; // [rsp+50h] [rbp-71h] BYREF
  TOKEN_CACHE_ENTRY *v33; // [rsp+58h] [rbp-69h] BYREF
  int *v34; // [rsp+60h] [rbp-61h]
  __int16 v35; // [rsp+70h] [rbp-51h] BYREF
  __int128 v36; // [rsp+72h] [rbp-4Fh]
  __int128 v37; // [rsp+82h] [rbp-3Fh]
  _BYTE v38[22]; // [rsp+92h] [rbp-2Fh]
  int v39; // [rsp+A8h] [rbp-19h]
  int v40; // [rsp+ACh] [rbp-15h]

  dwShareMode = a4;
  dwCreationDisposition = a5;
  v34 = a9;
  v29 = 0;
  v33 = 0;
  v32 = 0;
  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  *((_QWORD *)this + 141) = 0;
  v11 = a3 < 0;
  v12 = 1;
  if ( !v11 )
    v12 = 2;
  v13 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)a2, v12, a6, 0, &v33, 0);
  v14 = (volatile signed __int32 *)v33;
  if ( v13 < 0 )
    goto LABEL_17;
  v13 = USER_SESSION::Impersonate(this, v33, &v29);
  if ( v13 < 0 )
    goto LABEL_17;
  v15 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v15 + 8) && (*(_BYTE *)(v15 + 40) & 0x11) != 0 && *(_DWORD *)(v15 + 44) >= 5u )
  {
    v16 = a6[4];
    v17 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(v17, (const struct _GUID *)((char *)this + 1272), v16);
  }
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
  *((_QWORD *)this + 130) = CreateFileW(a6[4], a3, dwShareMode, 0, dwCreationDisposition, 0x40000000u, 0);
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
  v18 = (void *)*((_QWORD *)this + 130);
  if ( v18 != (void *)-1LL )
  {
    if ( GetFileType(v18) != 1 )
    {
      v13 = -2147024894;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          3532,
          "USER_SESSION::OpenFile",
          "File type is not allowed (!= FILE_TYPE_DISK)");
      *((_DWORD *)this + 278) = 13;
      *((_QWORD *)this + 138) = L"Attempt was made to open object that is not a file or directory.";
      goto LABEL_17;
    }
    if ( *((__int64 *)this + 141) > 0 || a7 )
    {
      v13 = (*(__int64 (__fastcall **)(USER_SESSION *, unsigned __int64 *))(*(_QWORD *)this + 232LL))(this, &v32);
      if ( v13 < 0 )
        goto LABEL_17;
      v26 = *((_QWORD *)this + 141);
      if ( v26 && v32 > v26 )
      {
        v13 = -2147024891;
        *((_DWORD *)this + 278) = 39;
        *((_QWORD *)this + 138) = L"Maximum file size was exceeded.";
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
            3559,
            "USER_SESSION::OpenFile",
            "Denied read access. Max Allowed Content Length exceeded.\r\n");
        goto LABEL_17;
      }
    }
    v13 = (*(__int64 (__fastcall **)(FTP_SERVERP *, _QWORD))(*(_QWORD *)g_pFtpServer + 72LL))(
            g_pFtpServer,
            *((_QWORD *)this + 130));
    if ( v13 >= 0 )
    {
      v13 = 0;
      v27 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v27 + 8) && (*(_BYTE *)(v27 + 40) & 0x11) != 0 && *(_DWORD *)(v27 + 44) >= 5u )
      {
        v28 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        v36 = 0;
        v37 = 0;
        *(_OWORD *)v38 = 0;
        v40 = 0;
        *(_DWORD *)&v38[10] = 1703936;
        v35 = 64;
        WORD2(v36) = 1;
        BYTE2(v36) = 2;
        *(_QWORD *)((char *)&v37 + 6) = &`FtpFileSystemAccessEvents::GetAreaGuid'::`2'::AreaGuid;
        *(_QWORD *)&v38[14] = (char *)this + 1272;
        v39 = 16;
        CEtwTracer::EtwTraceEvent(v28, (struct _EVENT_TRACE_HEADER *)&v35);
      }
      goto LABEL_23;
    }
LABEL_17:
    v21 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v21 + 8) && (*(_BYTE *)(v21 + 40) & 0x11) != 0 && *(_DWORD *)(v21 + 44) >= 2u )
    {
      v22 = a6[4];
      v23 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpFileSystemAccessEvents::FailedCreateFile::RaiseEvent(
        v23,
        (const struct _GUID *)((char *)this + 1272),
        v22,
        v13);
    }
    v24 = (void *)*((_QWORD *)this + 130);
    if ( v24 != (void *)-1LL )
    {
      CloseHandle(v24);
      *((_QWORD *)this + 130) = -1;
    }
    goto LABEL_23;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
      3506,
      "USER_SESSION::OpenFile",
      "CreateFileW(%S) failed with 0x%x.\r\n",
      a6[4],
      v13);
  *((_DWORD *)this + 278) = (v13 != -2147024891) + 2;
  v20 = L"File system returned an error.";
  if ( v13 == -2147024891 )
    v20 = L"File system denied the access.";
  *((_QWORD *)this + 138) = v20;
  if ( v13 < 0 )
    goto LABEL_17;
LABEL_23:
  if ( a7 )
    *a7 = v32;
  if ( v29 )
  {
    USER_SESSION::RevertImpersonation(this);
    v29 = 0;
  }
  if ( v14 && _InterlockedExchangeAdd(v14 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v14);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v14);
  }
  if ( v34 )
    *v34 = 0;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800123a0  push    rbp
0x1800123a2  push    rbx
0x1800123a3  push    rsi
0x1800123a4  push    rdi
0x1800123a5  push    r12
0x1800123a7  push    r13
0x1800123a9  push    r14
0x1800123ab  push    r15
0x1800123ad  lea     rbp, [rsp-7]
0x1800123b2  sub     rsp, 0C8h
0x1800123b9  mov     rax, cs:__security_cookie
0x1800123c0  xor     rax, rsp
0x1800123c3  mov     [rbp+3Fh+var_50], rax
0x1800123c7  mov     [rbp+3Fh+dwShareMode], r9d
0x1800123cb  mov     r13d, r8d
0x1800123ce  mov     rsi, rcx
0x1800123d1  mov     r15, [rbp+3Fh+arg_28]
0x1800123d5  mov     eax, [rbp+3Fh+arg_20]
0x1800123d8  mov     [rbp+3Fh+var_BC], eax
0x1800123db  mov     r12, [rbp+3Fh+arg_30]
0x1800123df  mov     rax, [rbp+3Fh+arg_40]
0x1800123e6  mov     [rbp+3Fh+var_A0], rax
0x1800123ea  xor     ebx, ebx
0x1800123ec  mov     [rsp+100h+var_C0], ebx
0x1800123f0  mov     [rbp+3Fh+var_A8], rbx
0x1800123f4  mov     [rbp+3Fh+var_B0], rbx
0x1800123f8  mov     [rcx+458h], ebx
0x1800123fe  lea     rax, WideCharStr
0x180012405  mov     [rcx+450h], rax
0x18001240c  mov     [rcx+468h], rbx
0x180012413  test    r8d, r8d
0x180012416  lea     r8d, [rbx+1]
0x18001241a  js      short loc_180012420
0x18001241c  lea     r8d, [rbx+2]
0x180012420  mov     dword ptr [rsp+100h+hTemplateFile], ebx
0x180012424  lea     rax, [rbp+3Fh+var_A8]
0x180012428  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x18001242d  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x180012432  mov     r9, r15
0x180012435  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x18001243a  mov     edi, eax
0x18001243c  mov     r14, [rbp+3Fh+var_A8]
0x180012440  test    eax, eax
0x180012442  js      loc_1800125A3
0x180012448  lea     r8, [rsp+100h+var_C0]; int *
0x18001244d  mov     rdx, r14; struct TOKEN_CACHE_ENTRY *
0x180012450  mov     rcx, rsi; this
0x180012453  call    ?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z; USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)
0x180012458  mov     edi, eax
0x18001245a  test    eax, eax
0x18001245c  js      loc_1800125A3
0x180012462  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180012469  mov     rax, [rcx]
0x18001246c  mov     rax, [rax+20h]
0x180012470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012475  cmp     [rax+8], ebx
0x180012478  jz      short loc_1800124B1
0x18001247a  test    byte ptr [rax+28h], 11h
0x18001247e  jz      short loc_1800124B1
0x180012480  cmp     dword ptr [rax+2Ch], 5
0x180012484  jb      short loc_1800124B1
0x180012486  mov     rbx, [r15+20h]
0x18001248a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180012491  mov     rax, [rcx]
0x180012494  mov     rax, [rax+20h]
0x180012498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001249d  lea     rdx, [rsi+4F8h]; struct _GUID *
0x1800124a4  mov     r8, rbx; unsigned __int16 *
0x1800124a7  mov     rcx, rax; struct CEtwTracer *
0x1800124aa  call    ?RaiseEvent@StartCreateFile@FtpFileSystemAccessEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x1800124af  xor     ebx, ebx
0x1800124b1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800124b8  mov     rax, [rcx]
0x1800124bb  mov     rax, [rax+40h]
0x1800124bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c4  mov     [rsp+100h+hTemplateFile], rbx; hTemplateFile
0x1800124c9  mov     [rsp+100h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800124d1  mov     eax, [rbp+3Fh+var_BC]
0x1800124d4  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x1800124d8  xor     r9d, r9d; lpSecurityAttributes
0x1800124db  mov     r8d, [rbp+3Fh+dwShareMode]; dwShareMode
0x1800124df  mov     edx, r13d; dwDesiredAccess
0x1800124e2  mov     rcx, [r15+20h]; lpFileName
0x1800124e6  call    cs:__imp_CreateFileW
0x1800124ec  mov     [rsi+410h], rax
0x1800124f3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800124fa  mov     rax, [rcx]
0x1800124fd  mov     rax, [rax+38h]
0x180012501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012506  mov     rcx, [rsi+410h]; hFile
0x18001250d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012511  jnz     loc_180012691
0x180012517  call    cs:__imp_GetLastError
0x18001251d  mov     edi, eax
0x18001251f  test    eax, eax
0x180012521  jle     short loc_18001252C
0x180012523  movzx   edi, ax
0x180012526  or      edi, 80070000h
0x18001252c  test    byte ptr cs:g_dwDebugFlags, 3
0x180012533  jz      short loc_18001256F
0x180012535  mov     dword ptr [rsp+100h+hTemplateFile], edi
0x180012539  mov     rax, [r15+20h]
0x18001253d  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rax
0x180012542  lea     rax, aCreatefilewSFa; "CreateFileW(%S) failed with 0x%x.\r\n"
0x180012549  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x18001254e  lea     r9, aUserSessionOpe; "USER_SESSION::OpenFile"
0x180012555  mov     r8d, 0DB2h
0x18001255b  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180012562  mov     rcx, cs:g_pDebug
0x180012569  call    cs:__imp_PuDbgPrint
0x18001256f  mov     eax, ebx
0x180012571  mov     ecx, 80070005h
0x180012576  cmp     edi, ecx
0x180012578  setnz   al
0x18001257b  add     eax, 2
0x18001257e  mov     [rsi+458h], eax
0x180012584  lea     rdx, aFileSystemDeni; "File system denied the access."
0x18001258b  lea     rax, aFileSystemRetu; "File system returned an error."
0x180012592  cmp     edi, ecx
0x180012594  cmovz   rax, rdx
0x180012598  mov     [rsi+450h], rax
0x18001259f  test    edi, edi
0x1800125a1  jns     short loc_180012613
0x1800125a3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800125aa  mov     rax, [rcx]
0x1800125ad  mov     rax, [rax+20h]
0x1800125b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b6  cmp     [rax+8], ebx
0x1800125b9  jz      short loc_1800125F5
0x1800125bb  test    byte ptr [rax+28h], 11h
0x1800125bf  jz      short loc_1800125F5
0x1800125c1  cmp     dword ptr [rax+2Ch], 2
0x1800125c5  jb      short loc_1800125F5
0x1800125c7  mov     rbx, [r15+20h]
0x1800125cb  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800125d2  mov     rax, [rcx]
0x1800125d5  mov     rax, [rax+20h]
0x1800125d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125de  lea     rdx, [rsi+4F8h]; struct _GUID *
0x1800125e5  mov     r9d, edi; unsigned int
0x1800125e8  mov     r8, rbx; unsigned __int16 *
0x1800125eb  mov     rcx, rax; struct CEtwTracer *
0x1800125ee  call    ?RaiseEvent@FailedCreateFile@FtpFileSystemAccessEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBGK@Z; FtpFileSystemAccessEvents::FailedCreateFile::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *,ulong)
0x1800125f3  xor     ebx, ebx
0x1800125f5  mov     rcx, [rsi+410h]; hObject
0x1800125fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012600  jz      short loc_180012613
0x180012602  call    cs:__imp_CloseHandle
0x180012608  mov     qword ptr [rsi+410h], 0FFFFFFFFFFFFFFFFh
0x180012613  test    r12, r12
0x180012616  jz      short loc_180012620
0x180012618  mov     rax, [rbp+3Fh+var_B0]
0x18001261c  mov     [r12], rax
0x180012620  cmp     [rsp+100h+var_C0], ebx
0x180012624  jz      short loc_180012632
0x180012626  mov     rcx, rsi; this
0x180012629  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x18001262e  mov     [rsp+100h+var_C0], ebx
0x180012632  test    r14, r14
0x180012635  jz      short loc_180012664
0x180012637  or      eax, 0FFFFFFFFh
0x18001263a  lock xadd [r14+14h], eax
0x180012640  cmp     eax, 1
0x180012643  jnz     short loc_180012664
0x180012645  test    r14, r14
0x180012648  jz      short loc_180012664
0x18001264a  mov     rcx, r14; this
0x18001264d  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180012652  nop
0x180012653  mov     rdx, r14
0x180012656  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001265d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180012663  nop
0x180012664  mov     rax, [rbp+3Fh+var_A0]
0x180012668  test    rax, rax
0x18001266b  jz      short loc_18001266F
0x18001266d  mov     [rax], ebx
0x18001266f  mov     eax, edi
0x180012671  mov     rcx, [rbp+3Fh+var_50]
0x180012675  xor     rcx, rsp; StackCookie
0x180012678  call    __security_check_cookie
0x18001267d  add     rsp, 0C8h
0x180012684  pop     r15
0x180012686  pop     r14
0x180012688  pop     r13
0x18001268a  pop     r12
0x18001268c  pop     rdi
0x18001268d  pop     rsi
0x18001268e  pop     rbx
0x18001268f  pop     rbp
0x180012690  retn
0x180012691  call    cs:__imp_GetFileType
0x180012697  mov     r13d, 1
0x18001269d  cmp     eax, r13d
0x1800126a0  jz      short loc_1800126FA
0x1800126a2  mov     edi, 80070002h
0x1800126a7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800126ae  jz      short loc_1800126DD
0x1800126b0  lea     rax, aFileTypeIsNotA; "File type is not allowed (!= FILE_TYPE_"...
0x1800126b7  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1800126bc  lea     r9, aUserSessionOpe; "USER_SESSION::OpenFile"
0x1800126c3  mov     r8d, 0DCCh
0x1800126c9  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800126d0  mov     rcx, cs:g_pDebug
0x1800126d7  call    cs:__imp_PuDbgPrint
0x1800126dd  mov     dword ptr [rsi+458h], 0Dh
0x1800126e7  lea     rax, aAttemptWasMade; "Attempt was made to open object that is"...
0x1800126ee  mov     [rsi+450h], rax
0x1800126f5  jmp     loc_1800125A3
0x1800126fa  cmp     [rsi+468h], rbx
0x180012701  jg      short loc_18001270C
0x180012703  test    r12, r12
0x180012706  jz      loc_18001279A
0x18001270c  mov     rax, [rsi]
0x18001270f  lea     rdx, [rbp+3Fh+var_B0]
0x180012713  mov     rcx, rsi
0x180012716  mov     rax, [rax+0E8h]
0x18001271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012722  mov     edi, eax
0x180012724  test    eax, eax
0x180012726  js      loc_1800125A3
0x18001272c  mov     rax, [rsi+468h]
0x180012733  test    rax, rax
0x180012736  jz      short loc_18001279A
0x180012738  cmp     [rbp+3Fh+var_B0], rax
0x18001273c  jbe     short loc_18001279A
0x18001273e  mov     edi, 80070005h
0x180012743  mov     dword ptr [rsi+458h], 27h ; '''
0x18001274d  lea     rax, aMaximumFileSiz; "Maximum file size was exceeded."
0x180012754  mov     [rsi+450h], rax
0x18001275b  test    byte ptr cs:g_dwDebugFlags, 3
0x180012762  jz      loc_1800125A3
0x180012768  lea     rax, aDeniedReadAcce; "Denied read access. Max Allowed Content"...
0x18001276f  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x180012774  lea     r9, aUserSessionOpe; "USER_SESSION::OpenFile"
0x18001277b  mov     r8d, 0DE7h
0x180012781  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180012788  mov     rcx, cs:g_pDebug
0x18001278f  call    cs:__imp_PuDbgPrint
0x180012795  jmp     loc_1800125A3
0x18001279a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800127a1  mov     rax, [rcx]
0x1800127a4  mov     rdx, [rsi+410h]
0x1800127ab  mov     rax, [rax+48h]
0x1800127af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b4  mov     edi, eax
0x1800127b6  test    eax, eax
0x1800127b8  js      loc_1800125A3
0x1800127be  mov     edi, ebx
0x1800127c0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800127c7  mov     rax, [rcx]
0x1800127ca  mov     rax, [rax+20h]
0x1800127ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127d3  cmp     [rax+8], ebx
0x1800127d6  jz      loc_180012613
0x1800127dc  test    byte ptr [rax+28h], 11h
0x1800127e0  jz      loc_180012613
0x1800127e6  cmp     dword ptr [rax+2Ch], 5
0x1800127ea  jb      loc_180012613
0x1800127f0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800127f7  mov     rax, [rcx]
0x1800127fa  mov     rax, [rax+20h]
0x1800127fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012803  mov     rcx, rax
0x180012806  xorps   xmm0, xmm0
0x180012809  movups  [rbp+3Fh+var_8E], xmm0
0x18001280d  movups  [rbp+3Fh+var_7E], xmm0
0x180012811  movups  xmmword ptr [rbp+3Fh+var_6E], xmm0
0x180012815  movups  xmmword ptr [rbp+3Fh+var_6E+0Eh], xmm0
0x180012819  mov     dword ptr [rbp+3Fh+var_6E+0Ah], 1A0000h
0x180012820  mov     eax, 40h ; '@'
0x180012825  mov     [rbp+3Fh+var_90], ax
0x180012829  mov     word ptr [rbp+3Fh+var_8E+4], r13w
0x18001282e  mov     byte ptr [rbp+3Fh+var_8E+2], 2
0x180012832  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpFileSystemAccessEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpFileSystemAccessEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180012839  mov     qword ptr [rbp+3Fh+var_7E+6], rax
0x18001283d  lea     rax, [rsi+4F8h]
0x180012844  mov     qword ptr [rbp+3Fh+var_6E+0Eh], rax
0x180012848  mov     [rbp+3Fh+var_58], 10h
0x18001284f  lea     rdx, [rbp+3Fh+var_90]
0x180012853  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180012859  jmp     loc_180012613
```
