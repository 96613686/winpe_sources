# LOGON_USER_CONTEXT::LookupHomeDirectory(int *)

- ea: `0x18001c450`
- end: `0x18001c991`
- name: `?LookupHomeDirectory@LOGON_USER_CONTEXT@@AEAAJPEAH@Z`
- size: `1345`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ccec`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x18001c450`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d544`
- `0x18002c12c`
- `0x180047027`
- `0x180049010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001c92f`
- `ole32!CoTaskMemFree` at `0x18001c92f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c488`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c488`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c977`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c977`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c6a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c6a8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c4be`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c4be`
- `iisutil!WriteRefTraceLog` at `0x18001c4ad`
- `iisutil!WriteRefTraceLog` at `0x18001c95a`
- `iisutil!WriteRefTraceLog` at `0x18001c4ad`
- `iisutil!WriteRefTraceLog` at `0x18001c95a`
- `iisutil!PuDbgPrintError` at `0x18001c6e9`
- `iisutil!PuDbgPrintError` at `0x18001c7a7`
- `iisutil!PuDbgPrintError` at `0x18001c85b`
- `iisutil!PuDbgPrintError` at `0x18001c6e9`
- `iisutil!PuDbgPrintError` at `0x18001c7a7`
- `iisutil!PuDbgPrintError` at `0x18001c85b`

## string_xrefs

- `0x18001c77c`: `Failed to retrieve IFtpHomeDirectoryProvider interface.`
- `0x18001c6ce`: `LOGON_USER_CONTEXT::LookupHomeDirectory`
- `0x18001c78c`: `LOGON_USER_CONTEXT::LookupHomeDirectory`
- `0x18001c840`: `LOGON_USER_CONTEXT::LookupHomeDirectory`
- `0x18001c6be`: `Failed to call IFtpHomeDirectoryProvider::GetUserHomeDirectoryData.`
- `0x18001c82c`: `Active Directory Isolation must be combined with basic or client certificate authentication.\n`
- `0x18001c871`: `ActiveDirectory Isolation must be combined with basic authentication.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::LookupHomeDirectory(LOGON_USER_CONTEXT *this, int *a2)
{
  unsigned int v3; // r14d
  signed int v4; // esi
  __int64 v5; // rdi
  __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // r13
  int v9; // ecx
  unsigned int v10; // eax
  CUSTOM_PROVIDER_ENTRY *v11; // rdi
  int ReferencedProvider; // eax
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdi
  __int64 v15; // rbx
  struct CEtwTracer *v16; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v18; // rax
  int *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rbx
  struct CEtwTracer *v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rbx
  __int64 v25; // rdi
  struct CEtwTracer *v26; // rax
  __int64 v27; // rbx
  const wchar_t *v28; // rax
  const wchar_t *v29; // rax
  char *v30; // r15
  __int64 (__fastcall *v31)(FTP_SERVERP *, __int64, __int64, __int64, __int64, __int64, char *, char *); // r12
  __int64 v32; // rdi
  __int64 v33; // rsi
  __int64 v34; // r14
  __int64 v35; // rbx
  __int64 v36; // rax
  unsigned __int32 v37; // ebx
  struct IUnknown *v39; // [rsp+A0h] [rbp+48h] BYREF
  int *v40; // [rsp+A8h] [rbp+50h]
  LPVOID pv; // [rsp+B0h] [rbp+58h] BYREF
  char *v42; // [rsp+B8h] [rbp+60h]

  v40 = a2;
  v3 = 0;
  v4 = 0;
  v5 = *((_QWORD *)this + 1);
  v39 = (struct IUnknown *)v5;
  v6 = *(_QWORD *)(v5 + 16);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v6 + 208));
  v7 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v6 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v7);
  v8 = *(_QWORD *)(v6 + 192);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v6 + 208));
  pv = 0;
  v9 = *(_DWORD *)(*((_QWORD *)this + 1) + 12LL);
  if ( v9 == 5 )
  {
    v10 = *(_DWORD *)(v8 + 320);
    if ( v10 )
    {
      while ( 1 )
      {
        v39 = 0;
        if ( v3 > v10 )
        {
          v4 = -2147024809;
          goto LABEL_46;
        }
        v11 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v8 + 328) + 600LL * v3);
        ReferencedProvider = CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
                               v11,
                               &GUID_0933b392_18dd_4097_8b9c_83325c35d9a6,
                               &v39);
        v4 = ReferencedProvider;
        if ( ReferencedProvider != -2147467262 )
        {
          if ( ReferencedProvider < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
                871,
                "LOGON_USER_CONTEXT::LookupHomeDirectory",
                ReferencedProvider,
                "Failed to retrieve IFtpHomeDirectoryProvider interface.");
            goto LABEL_46;
          }
          v13 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v13 + 8) && (*(_BYTE *)(v13 + 40) & 0x12) != 0 && *(_DWORD *)(v13 + 44) >= 4u )
          {
            v14 = (const unsigned __int16 *)*((_QWORD *)v11 + 7);
            v15 = *((_QWORD *)this + 1);
            v16 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            FtpExtensibilityEvents::StartCallProvider::RaiseEvent(v16, (const struct _GUID *)(v15 + 1272), v14);
          }
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 1);
          QueryInterface = v39->lpVtbl[1].QueryInterface;
          v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
          v19 = &dword_18004D454;
          if ( *(_QWORD *)(v6 + 8) )
            v19 = *(int **)(v6 + 8);
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, __int64, LPVOID *))QueryInterface)(
                 v39,
                 *(_QWORD *)(*((_QWORD *)this + 1) + 1168LL),
                 v19,
                 v18,
                 &pv);
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 1);
          if ( v4 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
                906,
                "LOGON_USER_CONTEXT::LookupHomeDirectory",
                v4,
                "Failed to call IFtpHomeDirectoryProvider::GetUserHomeDirectoryData.");
            v23 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            if ( *(_DWORD *)(v23 + 8) && (*(_BYTE *)(v23 + 40) & 0x12) != 0 && *(_DWORD *)(v23 + 44) >= 3u )
            {
              **((_WORD **)this + 69) = 0;
              *((_DWORD *)this + 142) = 0;
              GetLastComExceptionErrorInfo((LOGON_USER_CONTEXT *)((char *)this + 520));
              v24 = (const unsigned __int16 *)*((_QWORD *)this + 69);
              v25 = *((_QWORD *)this + 1);
              v26 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
              FtpExtensibilityEvents::FailCallProvider::RaiseEvent(v26, (const struct _GUID *)(v25 + 1272), v4, v24);
            }
            goto LABEL_46;
          }
          v20 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v20 + 8) && (*(_BYTE *)(v20 + 40) & 0x12) != 0 && *(_DWORD *)(v20 + 44) >= 4u )
          {
            v21 = *((_QWORD *)this + 1);
            v22 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            FtpExtensibilityEvents::EndCallProvider::RaiseEvent(v22, (const struct _GUID *)(v21 + 1272));
          }
          if ( pv && *(_WORD *)pv )
          {
            v4 = STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 232), (const unsigned __int16 *)pv);
            goto LABEL_46;
          }
        }
        if ( v39 )
        {
          ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
          v39 = 0;
        }
        ++v3;
        v10 = *(_DWORD *)(v8 + 320);
        if ( v3 >= v10 )
          goto LABEL_46;
      }
    }
  }
  else if ( v9 == 2 )
  {
    v42 = (char *)this + 232;
    if ( !*((_DWORD *)this + 70) )
    {
      v27 = v5 + 24;
      v28 = (const wchar_t *)(**(__int64 (__fastcall ***)(__int64))(v5 + 24))(v5 + 24);
      if ( !wcscmp_0(v28, L"BasicAuth")
        || (v29 = (const wchar_t *)(**(__int64 (__fastcall ***)(__int64))v27)(v5 + 24), !wcscmp_0(
                                                                                           v29,
                                                                                           L"ClientCertAuth")) )
      {
        v30 = (char *)this + 416;
        *((_DWORD *)v30 + 16) = 101;
        v31 = *(__int64 (__fastcall **)(FTP_SERVERP *, __int64, __int64, __int64, __int64, __int64, char *, char *))(*(_QWORD *)g_pFtpServer + 160LL);
        v32 = *(_QWORD *)(v8 + 840);
        v33 = *(_QWORD *)(v8 + 816);
        v34 = *(_QWORD *)(v8 + 760);
        v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 96LL))(v27);
        v36 = ((__int64 (__fastcall *)(struct IUnknown *))v39[3].lpVtbl[3].Release)(&v39[3]);
        v4 = v31(g_pFtpServer, v36, v35, v34, v33, v32, v30, v42);
        if ( v4 >= 0 && v40 )
          *v40 = 1;
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
            990,
            "LOGON_USER_CONTEXT::LookupHomeDirectory",
            -2147024891,
            "Active Directory Isolation must be combined with basic or client certificate authentication.\r\n");
        v4 = -2147024891;
        *((_DWORD *)this + 126) = 40;
        *((_QWORD *)this + 64) = L"ActiveDirectory Isolation must be combined with basic authentication.";
      }
LABEL_46:
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
    }
  }
  if ( v8 )
  {
    v37 = _InterlockedDecrement((volatile signed __int32 *)v8);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v37);
    if ( !v37 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v8);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v8);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c450  mov     [rsp-40h+arg_8], rdx
0x18001c455  push    rbp
0x18001c456  push    rbx
0x18001c457  push    rsi
0x18001c458  push    rdi
0x18001c459  push    r12
0x18001c45b  push    r13
0x18001c45d  push    r14
0x18001c45f  push    r15
0x18001c461  mov     rbp, rsp
0x18001c464  sub     rsp, 58h
0x18001c468  mov     r15, rcx
0x18001c46b  xor     r14d, r14d
0x18001c46e  mov     esi, r14d
0x18001c471  mov     rdi, [rcx+8]
0x18001c475  mov     [rbp+arg_0], rdi
0x18001c479  mov     r12, [rdi+10h]
0x18001c47d  lea     rbx, [r12+0D0h]
0x18001c485  mov     rcx, rbx
0x18001c488  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001c48e  mov     r8, [r12+0C0h]
0x18001c496  lea     edx, [r14+1]
0x18001c49a  lock xadd [r8], edx
0x18001c49f  inc     edx
0x18001c4a1  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c4a8  test    rcx, rcx
0x18001c4ab  jz      short loc_18001C4B3
0x18001c4ad  call    cs:__imp_WriteRefTraceLog
0x18001c4b3  mov     r13, [r12+0C0h]
0x18001c4bb  mov     rcx, rbx
0x18001c4be  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001c4c4  xor     ebx, ebx
0x18001c4c6  mov     [rbp+pv], rbx
0x18001c4ca  mov     rax, [r15+8]
0x18001c4ce  mov     ecx, [rax+0Ch]
0x18001c4d1  cmp     ecx, 5
0x18001c4d4  jnz     loc_18001C7BC
0x18001c4da  mov     eax, [r13+140h]
0x18001c4e1  test    eax, eax
0x18001c4e3  jz      loc_18001C939
0x18001c4e9  mov     [rbp+arg_0], rbx
0x18001c4ed  cmp     r14d, eax
0x18001c4f0  ja      loc_18001C7B2
0x18001c4f6  mov     eax, r14d
0x18001c4f9  imul    rdi, rax, 258h
0x18001c500  add     rdi, [r13+148h]
0x18001c507  lea     r8, [rbp+arg_0]; struct IUnknown **
0x18001c50b  lea     rdx, _GUID_0933b392_18dd_4097_8b9c_83325c35d9a6; struct _GUID *
0x18001c512  mov     rcx, rdi; this
0x18001c515  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x18001c51a  mov     esi, eax
0x18001c51c  cmp     eax, 80004002h
0x18001c521  jz      loc_18001C66C
0x18001c527  test    eax, eax
0x18001c529  js      loc_18001C76F
0x18001c52f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c536  mov     rax, [rcx]
0x18001c539  mov     rax, [rax+20h]
0x18001c53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c542  cmp     [rax+8], ebx
0x18001c545  jz      short loc_18001C580
0x18001c547  test    byte ptr [rax+28h], 12h
0x18001c54b  jz      short loc_18001C580
0x18001c54d  cmp     dword ptr [rax+2Ch], 4
0x18001c551  jb      short loc_18001C580
0x18001c553  mov     rdi, [rdi+38h]
0x18001c557  mov     rbx, [r15+8]
0x18001c55b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c562  mov     rax, [rcx]
0x18001c565  mov     rax, [rax+20h]
0x18001c569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c56e  mov     r8, rdi; unsigned __int16 *
0x18001c571  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001c578  mov     rcx, rax; struct CEtwTracer *
0x18001c57b  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18001c580  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c587  mov     rax, [rcx]
0x18001c58a  mov     edx, 1
0x18001c58f  mov     rax, [rax+0B0h]
0x18001c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c59b  mov     rax, [rbp+arg_0]
0x18001c59f  mov     rcx, [rax]
0x18001c5a2  mov     rbx, [rcx+18h]
0x18001c5a6  mov     rcx, [r15+8]
0x18001c5aa  mov     rax, [rcx]
0x18001c5ad  mov     rax, [rax+30h]
0x18001c5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5b6  lea     r8, dword_18004D454
0x18001c5bd  xor     edi, edi
0x18001c5bf  cmp     [r12+8], rdi
0x18001c5c4  cmovnz  r8, [r12+8]
0x18001c5ca  mov     rdx, [r15+8]
0x18001c5ce  lea     rcx, [rbp+pv]
0x18001c5d2  mov     [rsp+58h+var_38], rcx
0x18001c5d7  mov     r9, rax
0x18001c5da  mov     rdx, [rdx+490h]
0x18001c5e1  mov     rcx, [rbp+arg_0]
0x18001c5e5  mov     rax, rbx
0x18001c5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ed  mov     esi, eax
0x18001c5ef  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c5f6  mov     rax, [rcx]
0x18001c5f9  lea     edx, [rdi+1]
0x18001c5fc  mov     rax, [rax+0B8h]
0x18001c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c608  xor     ebx, ebx
0x18001c60a  test    esi, esi
0x18001c60c  js      loc_18001C6B5
0x18001c612  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c619  mov     rax, [rcx]
0x18001c61c  mov     rax, [rax+20h]
0x18001c620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c625  cmp     [rax+8], ebx
0x18001c628  jz      short loc_18001C65E
0x18001c62a  test    byte ptr [rax+28h], 12h
0x18001c62e  jz      short loc_18001C65E
0x18001c630  cmp     dword ptr [rax+2Ch], 4
0x18001c634  jb      short loc_18001C65E
0x18001c636  mov     rbx, [r15+8]
0x18001c63a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c641  mov     rax, [rcx]
0x18001c644  mov     rax, [rax+20h]
0x18001c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c64d  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001c654  mov     rcx, rax; struct CEtwTracer *
0x18001c657  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x18001c65c  xor     ebx, ebx
0x18001c65e  mov     rcx, [rbp+pv]
0x18001c662  test    rcx, rcx
0x18001c665  jz      short loc_18001C66C
0x18001c667  cmp     [rcx], bx
0x18001c66a  jnz     short loc_18001C69D
0x18001c66c  mov     rcx, [rbp+arg_0]
0x18001c670  test    rcx, rcx
0x18001c673  jz      short loc_18001C685
0x18001c675  mov     rax, [rcx]
0x18001c678  mov     rax, [rax+10h]
0x18001c67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c681  mov     [rbp+arg_0], rbx
0x18001c685  inc     r14d
0x18001c688  mov     eax, [r13+140h]
0x18001c68f  cmp     r14d, eax
0x18001c692  jb      loc_18001C4E9
0x18001c698  jmp     loc_18001C926
0x18001c69d  lea     rcx, [r15+0E8h]
0x18001c6a4  mov     rdx, [rbp+pv]
0x18001c6a8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c6ae  mov     esi, eax
0x18001c6b0  jmp     loc_18001C926
0x18001c6b5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001c6bc  jz      short loc_18001C6EF
0x18001c6be  lea     rax, aFailedToCallIf_1; "Failed to call IFtpHomeDirectoryProvide"...
0x18001c6c5  mov     [rsp+58h+var_30], rax
0x18001c6ca  mov     dword ptr [rsp+58h+var_38], esi
0x18001c6ce  lea     r9, aLogonUserConte; "LOGON_USER_CONTEXT::LookupHomeDirectory"
0x18001c6d5  mov     r8d, 38Ah
0x18001c6db  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001c6e2  mov     rcx, cs:g_pDebug
0x18001c6e9  call    cs:__imp_PuDbgPrintError
0x18001c6ef  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c6f6  mov     rax, [rcx]
0x18001c6f9  mov     rax, [rax+20h]
0x18001c6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c702  cmp     [rax+8], ebx
0x18001c705  jz      loc_18001C926
0x18001c70b  test    byte ptr [rax+28h], 12h
0x18001c70f  jz      loc_18001C926
0x18001c715  cmp     dword ptr [rax+2Ch], 3
0x18001c719  jb      loc_18001C926
0x18001c71f  lea     rcx, [r15+208h]; struct STRU *
0x18001c726  mov     rdx, [rcx+20h]; int
0x18001c72a  mov     [rdx], bx
0x18001c72d  mov     [rcx+30h], ebx
0x18001c730  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x18001c735  mov     rbx, [r15+228h]
0x18001c73c  mov     rdi, [r15+8]
0x18001c740  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c747  mov     rax, [rcx]
0x18001c74a  mov     rax, [rax+20h]
0x18001c74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c753  mov     r9, rbx; unsigned __int16 *
0x18001c756  mov     r8d, esi; unsigned int
0x18001c759  lea     rdx, [rdi+4F8h]; struct _GUID *
0x18001c760  mov     rcx, rax; struct CEtwTracer *
0x18001c763  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x18001c768  xor     ebx, ebx
0x18001c76a  jmp     loc_18001C926
0x18001c76f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001c776  jz      loc_18001C926
0x18001c77c  lea     rax, aFailedToRetrie_6; "Failed to retrieve IFtpHomeDirectoryPro"...
0x18001c783  mov     [rsp+58h+var_30], rax
0x18001c788  mov     dword ptr [rsp+58h+var_38], esi
0x18001c78c  lea     r9, aLogonUserConte; "LOGON_USER_CONTEXT::LookupHomeDirectory"
0x18001c793  mov     r8d, 367h
0x18001c799  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001c7a0  mov     rcx, cs:g_pDebug
0x18001c7a7  call    cs:__imp_PuDbgPrintError
0x18001c7ad  jmp     loc_18001C926
0x18001c7b2  mov     esi, 80070057h
0x18001c7b7  jmp     loc_18001C926
0x18001c7bc  cmp     ecx, 2
0x18001c7bf  jnz     loc_18001C939
0x18001c7c5  lea     rax, [r15+0E8h]
0x18001c7cc  mov     [rbp+arg_18], rax
0x18001c7d0  cmp     [rax+30h], ebx
0x18001c7d3  jnz     loc_18001C939
0x18001c7d9  lea     rbx, [rdi+18h]
0x18001c7dd  mov     rax, [rbx]
0x18001c7e0  mov     rcx, rbx
0x18001c7e3  mov     rax, [rax]
0x18001c7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7eb  mov     rcx, rax; String1
0x18001c7ee  lea     rdx, aBasicauth; "BasicAuth"
0x18001c7f5  call    wcscmp_0
0x18001c7fa  test    eax, eax
0x18001c7fc  jz      loc_18001C884
0x18001c802  mov     rax, [rbx]
0x18001c805  mov     rcx, rbx
0x18001c808  mov     rax, [rax]
0x18001c80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c810  mov     rcx, rax; String1
0x18001c813  lea     rdx, aClientcertauth_0; "ClientCertAuth"
0x18001c81a  call    wcscmp_0
0x18001c81f  test    eax, eax
0x18001c821  jz      short loc_18001C884
0x18001c823  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001c82a  jz      short loc_18001C861
0x18001c82c  lea     rax, aActiveDirector; "Active Directory Isolation must be comb"...
0x18001c833  mov     [rsp+58h+var_30], rax
0x18001c838  mov     dword ptr [rsp+58h+var_38], 80070005h
0x18001c840  lea     r9, aLogonUserConte; "LOGON_USER_CONTEXT::LookupHomeDirectory"
0x18001c847  mov     r8d, 3DEh
0x18001c84d  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001c854  mov     rcx, cs:g_pDebug
0x18001c85b  call    cs:__imp_PuDbgPrintError
0x18001c861  mov     esi, 80070005h
0x18001c866  mov     dword ptr [r15+1F8h], 28h ; '('
0x18001c871  lea     rax, aActivedirector_0; "ActiveDirectory Isolation must be combi"...
0x18001c878  mov     [r15+200h], rax
0x18001c87f  jmp     loc_18001C768
0x18001c884  add     r15, 1A0h
0x18001c88b  mov     dword ptr [r15+40h], 65h ; 'e'
0x18001c893  mov     rax, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c89a  mov     rdx, [rax]
0x18001c89d  mov     r12, [rdx+0A0h]
0x18001c8a4  mov     rdi, [r13+348h]
0x18001c8ab  mov     rsi, [r13+330h]
0x18001c8b2  mov     r14, [r13+2F8h]
0x18001c8b9  mov     rax, [rbx]
0x18001c8bc  mov     rcx, rbx
0x18001c8bf  mov     rax, [rax+60h]
0x18001c8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8c8  mov     rbx, rax
0x18001c8cb  mov     rcx, [rbp+arg_0]
0x18001c8cf  add     rcx, 18h
0x18001c8d3  mov     rdx, [rcx]
0x18001c8d6  mov     rax, [rdx+58h]
0x18001c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8df  mov     rcx, [rbp+arg_18]
0x18001c8e3  mov     [rsp+58h+var_20], rcx
0x18001c8e8  mov     [rsp+58h+var_28], r15
0x18001c8ed  mov     [rsp+58h+var_30], rdi
0x18001c8f2  mov     [rsp+58h+var_38], rsi
0x18001c8f7  mov     r9, r14
0x18001c8fa  mov     r8, rbx
0x18001c8fd  mov     rdx, rax
0x18001c900  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c907  mov     rax, r12
0x18001c90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90f  mov     esi, eax
0x18001c911  xor     ebx, ebx
0x18001c913  test    eax, eax
0x18001c915  js      short loc_18001C926
0x18001c917  mov     rax, [rbp+arg_8]
0x18001c91b  test    rax, rax
0x18001c91e  jz      short loc_18001C926
0x18001c920  mov     dword ptr [rax], 1
0x18001c926  mov     rcx, [rbp+pv]; pv
0x18001c92a  test    rcx, rcx
0x18001c92d  jz      short loc_18001C939
0x18001c92f  call    cs:__imp_CoTaskMemFree
0x18001c935  mov     [rbp+pv], rbx
0x18001c939  test    r13, r13
0x18001c93c  jz      short loc_18001C97E
0x18001c93e  or      ebx, 0FFFFFFFFh
0x18001c941  lock xadd [r13+0], ebx
0x18001c947  dec     ebx
0x18001c949  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c950  test    rcx, rcx
0x18001c953  jz      short loc_18001C960
0x18001c955  mov     r8, r13
0x18001c958  mov     edx, ebx
0x18001c95a  call    cs:__imp_WriteRefTraceLog
0x18001c960  test    ebx, ebx
0x18001c962  jnz     short loc_18001C97E
0x18001c964  mov     rcx, r13; this
0x18001c967  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001c96c  nop
0x18001c96d  mov     rdx, r13
0x18001c970  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
  ... truncated ...
```
