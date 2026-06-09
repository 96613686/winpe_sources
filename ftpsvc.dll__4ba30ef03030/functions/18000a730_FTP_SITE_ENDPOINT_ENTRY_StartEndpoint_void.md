# FTP_SITE_ENDPOINT_ENTRY::StartEndpoint(void)

- ea: `0x18000a730`
- end: `0x18000a9f7`
- name: `?StartEndpoint@FTP_SITE_ENDPOINT_ENTRY@@QEAAJXZ`
- size: `711`
- prototype: `__int64 __fastcall(FTP_SITE_ENDPOINT_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18000aa00`
- `0x18000ca90`

## callees

- `0x180009090`
- `0x18000a0e4`
- `0x18000a730`
- `0x18000b428`
- `0x180018ebc`
- `0x180031f80`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a764`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a764`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000a972`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000a972`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a799`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a799`
- `iisutil!WriteRefTraceLog` at `0x18000a789`
- `iisutil!WriteRefTraceLog` at `0x18000a955`
- `iisutil!WriteRefTraceLog` at `0x18000a789`
- `iisutil!WriteRefTraceLog` at `0x18000a955`
- `iisutil!PuDbgPrintError` at `0x18000a841`
- `iisutil!PuDbgPrintError` at `0x18000a930`
- `iisutil!PuDbgPrintError` at `0x18000a841`
- `iisutil!PuDbgPrintError` at `0x18000a930`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SITE_ENDPOINT_ENTRY::StartEndpoint(FTP_SITE_ENDPOINT_ENTRY *this)
{
  __int64 v2; // r14
  CReaderWriterLock3 *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r14
  int v6; // r12d
  signed int Endpoint; // ebx
  int *v8; // r15
  FTP_SITE_MANAGER *v9; // rax
  FTP_LOG_NT_EVENT_TABLE *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  int *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  const wchar_t *v16; // rcx
  unsigned __int32 v17; // edi
  FTP_LOG_NT_EVENT_TABLE *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int16 *v22; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h]
  int *v24; // [rsp+50h] [rbp-10h]
  __int64 v25; // [rsp+58h] [rbp-8h]
  int v26; // [rsp+90h] [rbp+30h] BYREF

  v26 = 0;
  v2 = *((_QWORD *)this + 24);
  v3 = (CReaderWriterLock3 *)(v2 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v2 + 208));
  v4 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v2 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v4);
  v5 = *(_QWORD *)(v2 + 192);
  CReaderWriterLock3::ReadUnlock(v3);
  v6 = 0;
  Endpoint = FTP_SITE::ParseBinding(
               *((wchar_t **)this + 4),
               (struct sockaddr_storage *)((char *)this + 56),
               0,
               *(_DWORD *)(v5 + 144) == 0);
  v8 = &dword_18004D454;
  if ( Endpoint >= 0 )
  {
    v9 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
    Endpoint = FTP_SITE_MANAGER::AddBindingToTable(
                 v9,
                 *((struct FTP_SITE **)this + 24),
                 *((const unsigned __int16 **)this + 4),
                 &v26);
    if ( Endpoint >= 0 )
    {
      v14 = (**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
      Endpoint = FTP_ENDPOINT_MANAGER::GetEndpoint(
                   *(FTP_ENDPOINT_MANAGER **)(v14 + 80),
                   (struct sockaddr_storage *)((char *)this + 56),
                   *(_DWORD *)(v5 + 148),
                   (struct FTP_ENDPOINT **)this + 23);
      if ( Endpoint >= 0 )
      {
        Endpoint = 0;
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v15 = *((_QWORD *)this + 24);
        v16 = (const wchar_t *)&dword_18004D454;
        if ( *(_QWORD *)(v15 + 8) )
          v16 = *(const wchar_t **)(v15 + 8);
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site.cxx",
          2133,
          "FTP_SITE_ENDPOINT_ENTRY::StartEndpoint",
          Endpoint,
          "Failed to add binding for site %S\n",
          v16);
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site.cxx",
          2101,
          "FTP_SITE_ENDPOINT_ENTRY::StartEndpoint",
          Endpoint,
          "Failed to initialize add to binding %S to hash table\n",
          *((const wchar_t **)this + 4));
      if ( v26 )
      {
        v10 = (FTP_LOG_NT_EVENT_TABLE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 40LL))(g_pFtpServer);
        v11 = *((_QWORD *)this + 4);
        v12 = *((_QWORD *)this + 24);
        v13 = &dword_18004D454;
        if ( *(_QWORD *)(v12 + 8) )
          v13 = *(int **)(v12 + 8);
        v22 = 0;
        v23 = 0;
        v24 = v13;
        v25 = v11;
        FTP_LOG_NT_EVENT_TABLE::LogEvent(v10, 0x8000000D, 4u, (const unsigned __int16 **const)&v22, Endpoint);
        v6 = 1;
      }
    }
  }
  v17 = _InterlockedDecrement((volatile signed __int32 *)v5);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v17);
  if ( !v17 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
  }
  if ( !v6 && Endpoint < 0 )
  {
    v18 = (FTP_LOG_NT_EVENT_TABLE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 40LL))(g_pFtpServer);
    v19 = *((_QWORD *)this + 4);
    v20 = *((_QWORD *)this + 24);
    if ( *(_QWORD *)(v20 + 8) )
      v8 = *(int **)(v20 + 8);
    v22 = 0;
    v23 = 0;
    v24 = v8;
    v25 = v19;
    FTP_LOG_NT_EVENT_TABLE::LogEvent(v18, 0x8000000B, 4u, (const unsigned __int16 **const)&v22, Endpoint);
  }
  return (unsigned int)Endpoint;
}

```

## disassembly

```asm
0x18000a730  mov     [rsp-28h+arg_8], rbx
0x18000a735  mov     [rsp-28h+arg_10], rsi
0x18000a73a  push    rbp
0x18000a73b  push    rdi
0x18000a73c  push    r12
0x18000a73e  push    r14
0x18000a740  push    r15
0x18000a742  mov     rbp, rsp
0x18000a745  sub     rsp, 60h
0x18000a749  mov     rsi, rcx
0x18000a74c  mov     [rbp+arg_0], 0
0x18000a753  mov     r14, [rcx+0C0h]
0x18000a75a  lea     rbx, [r14+0D0h]
0x18000a761  mov     rcx, rbx
0x18000a764  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000a76a  mov     r8, [r14+0C0h]
0x18000a771  mov     edx, 1
0x18000a776  lock xadd [r8], edx
0x18000a77b  inc     edx
0x18000a77d  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000a784  test    rcx, rcx
0x18000a787  jz      short loc_18000A78F
0x18000a789  call    cs:__imp_WriteRefTraceLog
0x18000a78f  mov     r14, [r14+0C0h]
0x18000a796  mov     rcx, rbx
0x18000a799  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a79f  xor     r12d, r12d
0x18000a7a2  xor     r9d, r9d
0x18000a7a5  cmp     [r14+90h], r9d
0x18000a7ac  setz    r9b; int
0x18000a7b0  xor     r8d, r8d; struct STRU *
0x18000a7b3  lea     rdx, [rsi+38h]; struct sockaddr_storage *
0x18000a7b7  mov     rcx, [rsi+20h]; Str
0x18000a7bb  call    ?ParseBinding@FTP_SITE@@SAJPEBGPEAUsockaddr_storage@@PEAVSTRU@@H@Z; FTP_SITE::ParseBinding(ushort const *,sockaddr_storage *,STRU *,int)
0x18000a7c0  mov     ebx, eax
0x18000a7c2  lea     r15, dword_18004D454
0x18000a7c9  test    eax, eax
0x18000a7cb  js      loc_18000A93A
0x18000a7d1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000a7d8  mov     rax, [rcx]
0x18000a7db  mov     rax, [rax]
0x18000a7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e3  lea     r9, [rbp+arg_0]; int *
0x18000a7e7  mov     r8, [rsi+20h]; unsigned __int16 *
0x18000a7eb  mov     rdx, [rsi+0C0h]; struct FTP_SITE *
0x18000a7f2  mov     rcx, rax; this
0x18000a7f5  call    ?AddBindingToTable@FTP_SITE_MANAGER@@QEAAJPEAVFTP_SITE@@PEBGPEAH@Z; FTP_SITE_MANAGER::AddBindingToTable(FTP_SITE *,ushort const *,int *)
0x18000a7fa  mov     ebx, eax
0x18000a7fc  test    eax, eax
0x18000a7fe  jns     loc_18000A8B1
0x18000a804  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a80b  jz      short loc_18000A847
0x18000a80d  mov     rax, [rsi+20h]
0x18000a811  mov     [rsp+60h+var_30], rax
0x18000a816  lea     rax, aFailedToInitia_1; "Failed to initialize add to binding %S "...
0x18000a81d  mov     [rsp+60h+var_38], rax
0x18000a822  mov     [rsp+60h+var_40], ebx
0x18000a826  lea     r9, aFtpSiteEndpoin; "FTP_SITE_ENDPOINT_ENTRY::StartEndpoint"
0x18000a82d  mov     r8d, 835h
0x18000a833  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000a83a  mov     rcx, cs:g_pDebug
0x18000a841  call    cs:__imp_PuDbgPrintError
0x18000a847  cmp     [rbp+arg_0], r12d
0x18000a84b  jz      loc_18000A93A
0x18000a851  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000a858  mov     rax, [rcx]
0x18000a85b  mov     rax, [rax+28h]
0x18000a85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a864  mov     r8, [rsi+20h]
0x18000a868  mov     rcx, [rsi+0C0h]
0x18000a86f  mov     rdx, r15
0x18000a872  cmp     [rcx+8], r12
0x18000a876  cmovnz  rdx, [rcx+8]
0x18000a87b  mov     [rbp+var_20], r12
0x18000a87f  mov     [rbp+var_18], r12
0x18000a883  mov     [rbp+var_10], rdx
0x18000a887  mov     [rbp+var_8], r8
0x18000a88b  mov     r8d, 4; unsigned __int16
0x18000a891  mov     [rsp+60h+var_40], ebx; unsigned int
0x18000a895  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18000a899  mov     edx, 8000000Dh; unsigned int
0x18000a89e  mov     rcx, rax; this
0x18000a8a1  call    ?LogEvent@FTP_LOG_NT_EVENT_TABLE@@QEAAXKGQEAPEBGK@Z; FTP_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000a8a6  mov     r12d, 1
0x18000a8ac  jmp     loc_18000A93A
0x18000a8b1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000a8b8  mov     rax, [rcx]
0x18000a8bb  mov     rax, [rax]
0x18000a8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c3  lea     r9, [rsi+0B8h]; struct FTP_ENDPOINT **
0x18000a8ca  mov     r8d, [r14+94h]; unsigned int
0x18000a8d1  lea     rdx, [rsi+38h]; struct sockaddr_storage *
0x18000a8d5  mov     rcx, [rax+50h]; this
0x18000a8d9  call    ?GetEndpoint@FTP_ENDPOINT_MANAGER@@QEAAJPEAUsockaddr_storage@@KPEAPEAVFTP_ENDPOINT@@@Z; FTP_ENDPOINT_MANAGER::GetEndpoint(sockaddr_storage *,ulong,FTP_ENDPOINT * *)
0x18000a8de  mov     ebx, eax
0x18000a8e0  test    eax, eax
0x18000a8e2  jns     short loc_18000A938
0x18000a8e4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a8eb  jz      short loc_18000A93A
0x18000a8ed  mov     rax, [rsi+0C0h]
0x18000a8f4  mov     rcx, r15
0x18000a8f7  cmp     [rax+8], r12
0x18000a8fb  cmovnz  rcx, [rax+8]
0x18000a900  mov     [rsp+60h+var_30], rcx
0x18000a905  lea     rax, aFailedToAddBin; "Failed to add binding for site %S\n"
0x18000a90c  mov     [rsp+60h+var_38], rax
0x18000a911  mov     [rsp+60h+var_40], ebx
0x18000a915  lea     r9, aFtpSiteEndpoin; "FTP_SITE_ENDPOINT_ENTRY::StartEndpoint"
0x18000a91c  mov     r8d, 855h
0x18000a922  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000a929  mov     rcx, cs:g_pDebug
0x18000a930  call    cs:__imp_PuDbgPrintError
0x18000a936  jmp     short loc_18000A93A
0x18000a938  xor     ebx, ebx
0x18000a93a  or      edi, 0FFFFFFFFh
0x18000a93d  lock xadd [r14], edi
0x18000a942  dec     edi
0x18000a944  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000a94b  test    rcx, rcx
0x18000a94e  jz      short loc_18000A95B
0x18000a950  mov     r8, r14
0x18000a953  mov     edx, edi
0x18000a955  call    cs:__imp_WriteRefTraceLog
0x18000a95b  test    edi, edi
0x18000a95d  jnz     short loc_18000A979
0x18000a95f  mov     rcx, r14; this
0x18000a962  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18000a967  nop
0x18000a968  mov     rdx, r14
0x18000a96b  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000a972  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000a978  nop
0x18000a979  test    r12d, r12d
0x18000a97c  jnz     short loc_18000A9DC
0x18000a97e  test    ebx, ebx
0x18000a980  jns     short loc_18000A9DC
0x18000a982  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000a989  mov     rax, [rcx]
0x18000a98c  mov     rax, [rax+28h]
0x18000a990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a995  mov     rdx, [rsi+20h]
0x18000a999  mov     rcx, [rsi+0C0h]
0x18000a9a0  cmp     qword ptr [rcx+8], 0
0x18000a9a5  cmovnz  r15, [rcx+8]
0x18000a9aa  mov     [rbp+var_20], 0
0x18000a9b2  mov     [rbp+var_18], 0
0x18000a9ba  mov     [rbp+var_10], r15
0x18000a9be  mov     [rbp+var_8], rdx
0x18000a9c2  lea     r8d, [r12+4]; unsigned __int16
0x18000a9c7  mov     [rsp+60h+var_40], ebx; unsigned int
0x18000a9cb  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18000a9cf  mov     edx, 8000000Bh; unsigned int
0x18000a9d4  mov     rcx, rax; this
0x18000a9d7  call    ?LogEvent@FTP_LOG_NT_EVENT_TABLE@@QEAAXKGQEAPEBGK@Z; FTP_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000a9dc  mov     eax, ebx
0x18000a9de  lea     r11, [rsp+60h+var_s0]
0x18000a9e3  mov     rbx, [r11+38h]
0x18000a9e7  mov     rsi, [r11+40h]
0x18000a9eb  mov     rsp, r11
0x18000a9ee  pop     r15
0x18000a9f0  pop     r14
0x18000a9f2  pop     r12
0x18000a9f4  pop     rdi
0x18000a9f5  pop     rbp
0x18000a9f6  retn
```
