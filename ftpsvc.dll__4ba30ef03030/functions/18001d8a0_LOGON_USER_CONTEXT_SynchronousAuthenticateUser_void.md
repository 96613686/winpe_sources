# LOGON_USER_CONTEXT::SynchronousAuthenticateUser(void)

- ea: `0x18001d8a0`
- end: `0x18001dfc2`
- name: `?SynchronousAuthenticateUser@LOGON_USER_CONTEXT@@AEAAJXZ`
- size: `1826`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c998`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d484`
- `0x18001d544`
- `0x18001d624`
- `0x18001d704`
- `0x18001d8a0`
- `0x18001e7e4`
- `0x18002c12c`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001dd7f`
- `ole32!CoTaskMemFree` at `0x18001df9a`
- `ole32!CoTaskMemFree` at `0x18001dd7f`
- `ole32!CoTaskMemFree` at `0x18001df9a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d8e7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d8e7`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001df33`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001df33`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ddac`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ddac`
- `iisutil!PuDbgPrint` at `0x18001de45`
- `iisutil!PuDbgPrint` at `0x18001de45`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d921`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d921`
- `iisutil!WriteRefTraceLog` at `0x18001d911`
- `iisutil!WriteRefTraceLog` at `0x18001df16`
- `iisutil!WriteRefTraceLog` at `0x18001d911`
- `iisutil!WriteRefTraceLog` at `0x18001df16`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001dd6a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001dd6a`
- `iisutil!PuDbgPrintError` at `0x18001dbc9`
- `iisutil!PuDbgPrintError` at `0x18001dc4e`
- `iisutil!PuDbgPrintError` at `0x18001de83`
- `iisutil!PuDbgPrintError` at `0x18001dbc9`
- `iisutil!PuDbgPrintError` at `0x18001dc4e`
- `iisutil!PuDbgPrintError` at `0x18001de83`

## string_xrefs

- `0x18001db2d`: `An error occurred during the authentication process.`
- `0x18001dc62`: `An error occurred during the authentication process.`
- `0x18001deb1`: `An error occurred during the authentication process.`
- `0x18001de1e`: `Failed to insert into credentials cache. hr=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::SynchronousAuthenticateUser(LOGON_USER_CONTEXT *this)
{
  __int64 v2; // r13
  int v3; // r12d
  __int64 v4; // rdx
  __int64 v5; // r15
  unsigned int v6; // edi
  CUSTOM_PROVIDER_ENTRY *v7; // rbx
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdi
  __int64 v10; // rbx
  struct CEtwTracer *v11; // rax
  _DWORD *v12; // rbx
  const wchar_t **v13; // r13
  CUSTOM_PROVIDER_ENTRY *v14; // rdi
  signed int ReferencedProvider; // esi
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdi
  __int64 v18; // rbx
  struct CEtwTracer *v19; // rax
  const unsigned __int16 *v20; // r13
  int *v21; // r8
  const wchar_t *v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rbx
  __int64 v25; // rdi
  struct CEtwTracer *v26; // rax
  unsigned int v27; // edi
  const wchar_t *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  struct CEtwTracer *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  CEtwTracer *v34; // rax
  CREDENTIALS_CACHE *v35; // rax
  __int64 v36; // rdx
  int v37; // eax
  const wchar_t **v38; // rax
  const wchar_t *v39; // rax
  unsigned __int32 v40; // ebx
  __int64 v41; // rax
  __int64 v42; // rbx
  struct CEtwTracer *v43; // rax
  unsigned int v45; // [rsp+40h] [rbp-79h]
  int v46; // [rsp+44h] [rbp-75h] BYREF
  struct IUnknown *v47; // [rsp+48h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  int v49; // [rsp+58h] [rbp-61h]
  unsigned int v50; // [rsp+5Ch] [rbp-5Dh]
  CUSTOM_PROVIDER_ENTRY *v51; // [rsp+60h] [rbp-59h]
  __int64 v52; // [rsp+68h] [rbp-51h]
  char *v53; // [rsp+70h] [rbp-49h]
  __int16 v54; // [rsp+80h] [rbp-39h] BYREF
  __int128 v55; // [rsp+82h] [rbp-37h]
  __int128 v56; // [rsp+92h] [rbp-27h]
  _BYTE v57[22]; // [rsp+A2h] [rbp-17h]
  int v58; // [rsp+B8h] [rbp-1h]
  int v59; // [rsp+BCh] [rbp+3h]

  v46 = 0;
  v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  v52 = v2;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v2 + 208));
  v3 = 1;
  v4 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v2 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v4);
  v5 = *(_QWORD *)(v2 + 192);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v2 + 208));
  v47 = 0;
  pv = 0;
  v50 = *(_DWORD *)(v5 + 272);
  v6 = 0;
  v45 = 0;
  if ( v50 )
  {
    while ( 1 )
    {
      if ( v6 > *(_DWORD *)(v5 + 272) )
      {
        ReferencedProvider = -2147024809;
        goto LABEL_70;
      }
      v7 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v5 + 280) + 600LL * v6);
      v51 = v7;
      v8 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v8 + 8) && (*(_BYTE *)(v8 + 40) & 8) != 0 && *(_DWORD *)(v8 + 44) >= 4u )
      {
        v9 = (const unsigned __int16 *)*((_QWORD *)v7 + 7);
        v10 = *((_QWORD *)this + 1);
        v11 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        FtpAuthenticationEvents::StartCustomLogon::RaiseEvent(v11, (const struct _GUID *)(v10 + 1272), v9);
      }
      v49 = 0;
      v12 = (_DWORD *)((char *)this + 568);
      v13 = (const wchar_t **)((char *)this + 552);
      while ( 1 )
      {
        *((_DWORD *)this + 126) = 0;
        *((_QWORD *)this + 64) = &WideCharStr;
        v14 = v51;
        ReferencedProvider = CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
                               v51,
                               &GUID_4659f95c_d5a8_4707_b2fc_6fd5794246cf,
                               &v47);
        if ( ReferencedProvider < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
              2419,
              "LOGON_USER_CONTEXT::SynchronousAuthenticateUser",
              ReferencedProvider,
              "Failed to get referenced IFtpAuthenticationProvider");
            v38 = (const wchar_t **)((char *)this + 552);
            v12 = (_DWORD *)((char *)this + 568);
          }
          else
          {
            v38 = v13;
          }
          *((_DWORD *)this + 126) = 41;
          if ( *v12 )
            v39 = *v38;
          else
            v39 = L"An error occurred during the authentication process.";
          *((_QWORD *)this + 64) = v39;
          goto LABEL_70;
        }
        v16 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v16 + 8) && (*(_BYTE *)(v16 + 40) & 0x12) != 0 && *(_DWORD *)(v16 + 44) >= 4u )
        {
          v17 = (const unsigned __int16 *)*((_QWORD *)v14 + 7);
          v18 = *((_QWORD *)this + 1);
          v19 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::StartCallProvider::RaiseEvent(v19, (const struct _GUID *)(v18 + 1272), v17);
        }
        (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 1);
        v20 = (const unsigned __int16 *)&dword_18004D454;
        v21 = &dword_18004D454;
        if ( *(_QWORD *)(v52 + 8) )
          v21 = *(int **)(v52 + 8);
        ReferencedProvider = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, _QWORD, _QWORD, LPVOID *, int *))v47->lpVtbl[1].QueryInterface)(
                               v47,
                               *(_QWORD *)(*((_QWORD *)this + 1) + 1168LL),
                               v21,
                               *((_QWORD *)this + 7),
                               *((_QWORD *)this + 14),
                               &pv,
                               &v46);
        (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 1);
        if ( ReferencedProvider >= 0 )
          break;
        v13 = (const wchar_t **)((char *)this + 552);
        **((_WORD **)this + 69) = 0;
        v12 = (_DWORD *)((char *)this + 568);
        v53 = (char *)this + 568;
        *((_DWORD *)this + 142) = 0;
        GetLastComExceptionErrorInfo((LOGON_USER_CONTEXT *)((char *)this + 520));
        *((_DWORD *)this + 126) = 41;
        if ( *((_DWORD *)this + 142) )
          v22 = *v13;
        else
          v22 = L"An error occurred during the authentication process.";
        *((_QWORD *)this + 64) = v22;
        v23 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v23 + 8) && (*(_BYTE *)(v23 + 40) & 0x12) != 0 && *(_DWORD *)(v23 + 44) >= 3u )
        {
          v24 = *v13;
          v25 = *((_QWORD *)this + 1);
          v26 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::FailCallProvider::RaiseEvent(
            v26,
            (const struct _GUID *)(v25 + 1272),
            ReferencedProvider,
            v24);
          v12 = v53;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
            2493,
            "LOGON_USER_CONTEXT::SynchronousAuthenticateUser",
            ReferencedProvider,
            "Failed to call AuthenticateUser()");
        if ( ReferencedProvider != -2147417848
          && ReferencedProvider != -2147023170
          && ReferencedProvider != -2146234348
          && ReferencedProvider != -2147023174 )
        {
          goto LABEL_70;
        }
        ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
        v47 = 0;
        v27 = v45;
        ReferencedProvider = LOGON_USER_CONTEXT::RequestCustomProviderUpdate(this, v45);
        if ( ReferencedProvider < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
              2505,
              "LOGON_USER_CONTEXT::SynchronousAuthenticateUser",
              ReferencedProvider,
              "Failed to get referenced custom handler");
          *((_DWORD *)this + 126) = 41;
          v28 = L"An error occurred during the authentication process.";
          if ( *v12 )
            v28 = *v13;
          *((_QWORD *)this + 64) = v28;
        }
        if ( (unsigned int)++v49 >= 2 )
        {
          v20 = (const unsigned __int16 *)&dword_18004D454;
          goto LABEL_44;
        }
      }
      v29 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v29 + 8) && (*(_BYTE *)(v29 + 40) & 0x12) != 0 && *(_DWORD *)(v29 + 44) >= 4u )
      {
        v30 = *((_QWORD *)this + 1);
        v31 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        FtpExtensibilityEvents::EndCallProvider::RaiseEvent(v31, (const struct _GUID *)(v30 + 1272));
      }
      v27 = v45;
LABEL_44:
      v32 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v32 + 8) && (*(_BYTE *)(v32 + 40) & 8) != 0 && *(_DWORD *)(v32 + 44) >= 4u )
      {
        v33 = *((_QWORD *)this + 1) + 1272LL;
        v34 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        v55 = 0;
        v56 = 0;
        *(_OWORD *)v57 = 0;
        v59 = 0;
        *(_DWORD *)&v57[10] = 1703936;
        v54 = 64;
        WORD2(v55) = 1;
        BYTE2(v55) = 7;
        *(_QWORD *)((char *)&v56 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
        *(_QWORD *)&v57[14] = v33;
        v58 = 16;
        CEtwTracer::EtwTraceEvent(v34, (struct _EVENT_TRACE_HEADER *)&v54);
      }
      if ( v46 )
        break;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v6 = v27 + 1;
      v45 = v6;
      if ( v6 >= v50 )
        goto LABEL_68;
    }
    STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 136), (const unsigned __int16 *)pv);
    *((_DWORD *)this + 54) = 1;
    v35 = (CREDENTIALS_CACHE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 192LL))(g_pFtpServer);
    v36 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
    if ( *(_QWORD *)(v36 + 8) )
      v20 = *(const unsigned __int16 **)(v36 + 8);
    v37 = CREDENTIALS_CACHE::Insert(
            v35,
            *((const unsigned __int16 **)this + 7),
            *((const unsigned __int16 **)this + 14),
            *((const unsigned __int16 **)v51 + 7),
            v20,
            (const unsigned __int16 *)pv);
    ReferencedProvider = v37;
    if ( v37 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          2569,
          "LOGON_USER_CONTEXT::SynchronousAuthenticateUser",
          "Failed to insert into credentials cache. hr=0x%x\n",
          v37);
      ReferencedProvider = 0;
    }
  }
  else
  {
    ReferencedProvider = 0;
    v3 = 0;
  }
LABEL_68:
  if ( !v46 )
    ReferencedProvider = -2147023570;
LABEL_70:
  if ( v47 )
  {
    ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
    v47 = 0;
  }
  if ( v5 )
  {
    v40 = _InterlockedDecrement((volatile signed __int32 *)v5);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v40);
    if ( !v40 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
    }
  }
  if ( ReferencedProvider < 0 )
  {
    if ( v3 )
    {
      v41 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v41 + 8) )
      {
        if ( (*(_BYTE *)(v41 + 40) & 8) != 0 && *(_DWORD *)(v41 + 44) >= 3u )
        {
          v42 = *((_QWORD *)this + 1);
          v43 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpAuthenticationEvents::FailCustomLogon::RaiseEvent(
            v43,
            (const struct _GUID *)(v42 + 1272),
            ReferencedProvider);
        }
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)ReferencedProvider;
}

```

## disassembly

```asm
0x18001d8a0  push    rbp
0x18001d8a2  push    rbx
0x18001d8a3  push    rsi
0x18001d8a4  push    rdi
0x18001d8a5  push    r12
0x18001d8a7  push    r13
0x18001d8a9  push    r14
0x18001d8ab  push    r15
0x18001d8ad  lea     rbp, [rsp-1Fh]
0x18001d8b2  sub     rsp, 0D8h
0x18001d8b9  mov     rax, cs:__security_cookie
0x18001d8c0  xor     rax, rsp
0x18001d8c3  mov     [rbp+57h+var_50], rax
0x18001d8c7  mov     r14, rcx
0x18001d8ca  mov     [rbp+57h+var_CC], 0
0x18001d8d1  mov     rax, [rcx+8]
0x18001d8d5  mov     r13, [rax+10h]
0x18001d8d9  mov     [rbp+57h+var_A8], r13
0x18001d8dd  lea     rbx, [r13+0D0h]
0x18001d8e4  mov     rcx, rbx
0x18001d8e7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001d8ed  mov     r8, [r13+0C0h]
0x18001d8f4  mov     r12d, 1
0x18001d8fa  mov     edx, r12d
0x18001d8fd  lock xadd [r8], edx
0x18001d902  add     edx, r12d
0x18001d905  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001d90c  test    rcx, rcx
0x18001d90f  jz      short loc_18001D917
0x18001d911  call    cs:__imp_WriteRefTraceLog
0x18001d917  mov     r15, [r13+0C0h]
0x18001d91e  mov     rcx, rbx
0x18001d921  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001d927  mov     [rbp+57h+var_C8], 0
0x18001d92f  mov     [rbp+57h+pv], 0
0x18001d937  mov     eax, [r15+110h]
0x18001d93e  mov     [rbp+57h+var_B4], eax
0x18001d941  xor     edi, edi
0x18001d943  mov     [rbp+57h+var_D0], edi
0x18001d946  test    eax, eax
0x18001d948  jz      loc_18001DEC8
0x18001d94e  cmp     edi, [r15+110h]
0x18001d955  ja      loc_18001DEC1
0x18001d95b  mov     eax, edi
0x18001d95d  imul    rbx, rax, 258h
0x18001d964  add     rbx, [r15+118h]
0x18001d96b  mov     [rbp+57h+var_B0], rbx
0x18001d96f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001d976  mov     rax, [rcx]
0x18001d979  mov     rax, [rax+20h]
0x18001d97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d982  cmp     dword ptr [rax+8], 0
0x18001d986  jz      short loc_18001D9C1
0x18001d988  test    byte ptr [rax+28h], 8
0x18001d98c  jz      short loc_18001D9C1
0x18001d98e  cmp     dword ptr [rax+2Ch], 4
0x18001d992  jb      short loc_18001D9C1
0x18001d994  mov     rdi, [rbx+38h]
0x18001d998  mov     rbx, [r14+8]
0x18001d99c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001d9a3  mov     rax, [rcx]
0x18001d9a6  mov     rax, [rax+20h]
0x18001d9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9af  mov     r8, rdi; unsigned __int16 *
0x18001d9b2  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001d9b9  mov     rcx, rax; struct CEtwTracer *
0x18001d9bc  call    ?RaiseEvent@StartCustomLogon@FtpAuthenticationEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpAuthenticationEvents::StartCustomLogon::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18001d9c1  mov     [rbp+57h+var_B8], 0
0x18001d9c8  lea     rbx, [r14+238h]
0x18001d9cf  lea     r13, [r14+228h]
0x18001d9d6  mov     dword ptr [r14+1F8h], 0
0x18001d9e1  lea     rax, WideCharStr
0x18001d9e8  mov     [r14+200h], rax
0x18001d9ef  lea     r8, [rbp+57h+var_C8]; struct IUnknown **
0x18001d9f3  lea     rdx, _GUID_4659f95c_d5a8_4707_b2fc_6fd5794246cf; struct _GUID *
0x18001d9fa  mov     rdi, [rbp+57h+var_B0]
0x18001d9fe  mov     rcx, rdi; this
0x18001da01  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x18001da06  mov     esi, eax
0x18001da08  test    eax, eax
0x18001da0a  js      loc_18001DE4F
0x18001da10  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001da17  mov     rax, [rcx]
0x18001da1a  mov     rax, [rax+20h]
0x18001da1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da23  cmp     dword ptr [rax+8], 0
0x18001da27  jz      short loc_18001DA62
0x18001da29  test    byte ptr [rax+28h], 12h
0x18001da2d  jz      short loc_18001DA62
0x18001da2f  cmp     dword ptr [rax+2Ch], 4
0x18001da33  jb      short loc_18001DA62
0x18001da35  mov     rdi, [rdi+38h]
0x18001da39  mov     rbx, [r14+8]
0x18001da3d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001da44  mov     rax, [rcx]
0x18001da47  mov     rax, [rax+20h]
0x18001da4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da50  mov     r8, rdi; unsigned __int16 *
0x18001da53  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001da5a  mov     rcx, rax; struct CEtwTracer *
0x18001da5d  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18001da62  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001da69  mov     rax, [rcx]
0x18001da6c  mov     edx, r12d
0x18001da6f  mov     rax, [rax+0B0h]
0x18001da76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da7b  mov     rcx, [rbp+57h+var_C8]
0x18001da7f  mov     rax, [rcx]
0x18001da82  mov     r9, [r14+70h]
0x18001da86  lea     r13, dword_18004D454
0x18001da8d  mov     r8, r13
0x18001da90  mov     rdx, [rbp+57h+var_A8]
0x18001da94  xor     edi, edi
0x18001da96  cmp     [rdx+8], rdi
0x18001da9a  cmovnz  r8, [rdx+8]
0x18001da9f  mov     rdx, [r14+8]
0x18001daa3  lea     r10, [rbp+57h+var_CC]
0x18001daa7  mov     [rsp+110h+var_E0], r10
0x18001daac  lea     r10, [rbp+57h+pv]
0x18001dab0  mov     [rsp+110h+var_E8], r10
0x18001dab5  mov     [rsp+110h+var_F0], r9
0x18001daba  mov     r9, [r14+38h]
0x18001dabe  mov     rdx, [rdx+490h]
0x18001dac5  mov     rax, [rax+18h]
0x18001dac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dace  mov     esi, eax
0x18001dad0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001dad7  mov     rax, [rcx]
0x18001dada  mov     edx, r12d
0x18001dadd  mov     rax, [rax+0B8h]
0x18001dae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae9  test    esi, esi
0x18001daeb  jns     loc_18001DC91
0x18001daf1  lea     r13, [r14+228h]
0x18001daf8  mov     rcx, [r13+0]
0x18001dafc  mov     [rcx], di
0x18001daff  lea     rbx, [r14+238h]
0x18001db06  mov     [rbp+57h+var_A0], rbx
0x18001db0a  mov     [rbx], edi
0x18001db0c  lea     rcx, [r14+208h]; struct STRU *
0x18001db13  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x18001db18  mov     dword ptr [r14+1F8h], 29h ; ')'
0x18001db23  cmp     [rbx], edi
0x18001db25  jz      short loc_18001DB2D
0x18001db27  mov     rax, [r13+0]
0x18001db2b  jmp     short loc_18001DB34
0x18001db2d  lea     rax, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001db34  mov     [r14+200h], rax
0x18001db3b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001db42  mov     rax, [rcx]
0x18001db45  mov     rax, [rax+20h]
0x18001db49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db4e  cmp     [rax+8], edi
0x18001db51  jz      short loc_18001DB95
0x18001db53  test    byte ptr [rax+28h], 12h
0x18001db57  jz      short loc_18001DB95
0x18001db59  cmp     dword ptr [rax+2Ch], 3
0x18001db5d  jb      short loc_18001DB95
0x18001db5f  mov     rbx, [r13+0]
0x18001db63  mov     rdi, [r14+8]
0x18001db67  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001db6e  mov     rax, [rcx]
0x18001db71  mov     rax, [rax+20h]
0x18001db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db7a  mov     r9, rbx; unsigned __int16 *
0x18001db7d  mov     r8d, esi; unsigned int
0x18001db80  lea     rdx, [rdi+4F8h]; struct _GUID *
0x18001db87  mov     rcx, rax; struct CEtwTracer *
0x18001db8a  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x18001db8f  mov     rbx, [rbp+57h+var_A0]
0x18001db93  xor     edi, edi
0x18001db95  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001db9c  jz      short loc_18001DBCF
0x18001db9e  lea     rax, aFailedToCallAu; "Failed to call AuthenticateUser()"
0x18001dba5  mov     [rsp+110h+var_E8], rax
0x18001dbaa  mov     dword ptr [rsp+110h+var_F0], esi
0x18001dbae  lea     r9, aLogonUserConte_1; "LOGON_USER_CONTEXT::SynchronousAuthenti"...
0x18001dbb5  mov     r8d, 9BDh
0x18001dbbb  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001dbc2  mov     rcx, cs:g_pDebug
0x18001dbc9  call    cs:__imp_PuDbgPrintError
0x18001dbcf  cmp     esi, 80010108h
0x18001dbd5  jz      short loc_18001DBF3
0x18001dbd7  cmp     esi, 800706BEh
0x18001dbdd  jz      short loc_18001DBF3
0x18001dbdf  cmp     esi, 80131014h
0x18001dbe5  jz      short loc_18001DBF3
0x18001dbe7  cmp     esi, 800706BAh
0x18001dbed  jnz     loc_18001DED9
0x18001dbf3  mov     rcx, [rbp+57h+var_C8]
0x18001dbf7  mov     rax, [rcx]
0x18001dbfa  mov     rax, [rax+10h]
0x18001dbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc03  mov     [rbp+57h+var_C8], rdi
0x18001dc07  mov     edi, [rbp+57h+var_D0]
0x18001dc0a  mov     edx, edi; unsigned int
0x18001dc0c  mov     rcx, r14; this
0x18001dc0f  call    ?RequestCustomProviderUpdate@LOGON_USER_CONTEXT@@AEAAJK@Z; LOGON_USER_CONTEXT::RequestCustomProviderUpdate(ulong)
0x18001dc14  mov     esi, eax
0x18001dc16  test    eax, eax
0x18001dc18  jns     short loc_18001DC76
0x18001dc1a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001dc21  jz      short loc_18001DC54
0x18001dc23  lea     rax, aFailedToGetRef; "Failed to get referenced custom handler"
0x18001dc2a  mov     [rsp+110h+var_E8], rax
0x18001dc2f  mov     dword ptr [rsp+110h+var_F0], esi
0x18001dc33  lea     r9, aLogonUserConte_1; "LOGON_USER_CONTEXT::SynchronousAuthenti"...
0x18001dc3a  mov     r8d, 9C9h
0x18001dc40  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001dc47  mov     rcx, cs:g_pDebug
0x18001dc4e  call    cs:__imp_PuDbgPrintError
0x18001dc54  mov     dword ptr [r14+1F8h], 29h ; ')'
0x18001dc5f  cmp     dword ptr [rbx], 0
0x18001dc62  lea     rax, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001dc69  jz      short loc_18001DC6F
0x18001dc6b  mov     rax, [r13+0]
0x18001dc6f  mov     [r14+200h], rax
0x18001dc76  mov     eax, [rbp+57h+var_B8]
0x18001dc79  add     eax, r12d
0x18001dc7c  mov     [rbp+57h+var_B8], eax
0x18001dc7f  cmp     eax, 2
0x18001dc82  jb      loc_18001D9D6
0x18001dc88  lea     r13, dword_18004D454
0x18001dc8f  jmp     short loc_18001DCDE
0x18001dc91  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001dc98  mov     rax, [rcx]
0x18001dc9b  mov     rax, [rax+20h]
0x18001dc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca4  cmp     [rax+8], edi
0x18001dca7  jz      short loc_18001DCDB
0x18001dca9  test    byte ptr [rax+28h], 12h
0x18001dcad  jz      short loc_18001DCDB
0x18001dcaf  cmp     dword ptr [rax+2Ch], 4
0x18001dcb3  jb      short loc_18001DCDB
0x18001dcb5  mov     rbx, [r14+8]
0x18001dcb9  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001dcc0  mov     rax, [rcx]
0x18001dcc3  mov     rax, [rax+20h]
0x18001dcc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dccc  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001dcd3  mov     rcx, rax; struct CEtwTracer *
0x18001dcd6  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x18001dcdb  mov     edi, [rbp+57h+var_D0]
0x18001dcde  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001dce5  mov     rax, [rcx]
0x18001dce8  mov     rax, [rax+20h]
0x18001dcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcf1  cmp     dword ptr [rax+8], 0
0x18001dcf5  jz      short loc_18001DD70
0x18001dcf7  test    byte ptr [rax+28h], 8
0x18001dcfb  jz      short loc_18001DD70
0x18001dcfd  cmp     dword ptr [rax+2Ch], 4
0x18001dd01  jb      short loc_18001DD70
0x18001dd03  mov     rbx, [r14+8]
0x18001dd07  add     rbx, 4F8h
0x18001dd0e  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001dd15  mov     rax, [rcx]
0x18001dd18  mov     rax, [rax+20h]
0x18001dd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd21  xorps   xmm0, xmm0
0x18001dd24  movups  [rbp+57h+var_8E], xmm0
0x18001dd28  movups  [rbp+57h+var_7E], xmm0
0x18001dd2c  movups  xmmword ptr [rbp+57h+var_6E], xmm0
0x18001dd30  movups  xmmword ptr [rbp+57h+var_6E+0Eh], xmm0
0x18001dd34  mov     dword ptr [rbp+57h+var_6E+0Ah], 1A0000h
0x18001dd3b  mov     ecx, 40h ; '@'
0x18001dd40  mov     [rbp+57h+var_90], cx
0x18001dd44  mov     word ptr [rbp+57h+var_8E+4], r12w
0x18001dd49  mov     byte ptr [rbp+57h+var_8E+2], 7
0x18001dd4d  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001dd54  mov     qword ptr [rbp+57h+var_7E+6], rcx
0x18001dd58  mov     qword ptr [rbp+57h+var_6E+0Eh], rbx
0x18001dd5c  mov     [rbp+57h+var_58], 10h
0x18001dd63  lea     rdx, [rbp+57h+var_90]
0x18001dd67  mov     rcx, rax
0x18001dd6a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001dd70  cmp     [rbp+57h+var_CC], 0
0x18001dd74  jnz     short loc_18001DDA1
0x18001dd76  mov     rcx, [rbp+57h+pv]; pv
0x18001dd7a  test    rcx, rcx
0x18001dd7d  jz      short loc_18001DD8D
0x18001dd7f  call    cs:__imp_CoTaskMemFree
0x18001dd85  mov     [rbp+57h+pv], 0
0x18001dd8d  add     edi, r12d
0x18001dd90  mov     [rbp+57h+var_D0], edi
0x18001dd93  cmp     edi, [rbp+57h+var_B4]
0x18001dd96  jb      loc_18001D94E
0x18001dd9c  jmp     loc_18001DECD
0x18001dda1  lea     rcx, [r14+88h]
0x18001dda8  mov     rdx, [rbp+57h+pv]
0x18001ddac  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ddb2  mov     [r14+0D8h], r12d
0x18001ddb9  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001ddc0  mov     rax, [rcx]
0x18001ddc3  mov     rax, [rax+0C0h]
0x18001ddca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddcf  mov     r8, [rbp+57h+pv]
0x18001ddd3  mov     rcx, [r14+8]
0x18001ddd7  mov     rdx, [rcx+10h]
0x18001dddb  cmp     qword ptr [rdx+8], 0
  ... truncated ...
```
