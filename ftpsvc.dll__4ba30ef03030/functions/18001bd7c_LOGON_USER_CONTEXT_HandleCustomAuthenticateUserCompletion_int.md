# LOGON_USER_CONTEXT::HandleCustomAuthenticateUserCompletion(int *)

- ea: `0x18001bd7c`
- end: `0x18001c156`
- name: `?HandleCustomAuthenticateUserCompletion@LOGON_USER_CONTEXT@@AEAAJPEAH@Z`
- size: `986`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a920`

## callees

- `0x180009090`
- `0x18001951c`
- `0x18001bd7c`
- `0x18001ccec`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d704`
- `0x18001e7e4`
- `0x18002c12c`
- `0x180049010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001c11c`
- `ole32!CoTaskMemFree` at `0x18001c11c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001bf58`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001bf58`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c10c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c10c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001bf40`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001bf40`
- `iisutil!PuDbgPrint` at `0x18001c03d`
- `iisutil!PuDbgPrint` at `0x18001c03d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001bf8d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001bf8d`
- `iisutil!WriteRefTraceLog` at `0x18001bf7d`
- `iisutil!WriteRefTraceLog` at `0x18001c0ef`
- `iisutil!WriteRefTraceLog` at `0x18001bf7d`
- `iisutil!WriteRefTraceLog` at `0x18001c0ef`

## string_xrefs

- `0x18001be6d`: `An error occurred during the authentication process.`
- `0x18001c016`: `Failed to insert into credentials cache. hr=0x%x\n`
- `0x18001c022`: `LOGON_USER_CONTEXT::HandleCustomAuthenticateUserCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::HandleCustomAuthenticateUserCompletion(LOGON_USER_CONTEXT *this, int *a2)
{
  signed int ReferencedAsyncFtpProvider; // r14d
  __int64 v5; // r15
  const wchar_t **v6; // rbx
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  const unsigned __int16 *v9; // rbx
  __int64 v10; // rdi
  struct CEtwTracer *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r15
  CReaderWriterLock3 *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rbx
  CREDENTIALS_CACHE *v20; // rax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rbx
  struct CEtwTracer *v26; // rax
  unsigned __int32 v27; // ebx
  int v29; // [rsp+70h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+48h] BYREF
  struct IUnknown *v31; // [rsp+80h] [rbp+50h] BYREF

  v29 = 0;
  pv = 0;
  v31 = 0;
  *a2 = 0;
  ReferencedAsyncFtpProvider = ASYNC_COM_CALL_CONTEXT::GetReferencedAsyncFtpProvider(
                                 *((ASYNC_COM_CALL_CONTEXT **)this + 2),
                                 &v31);
  if ( ReferencedAsyncFtpProvider < 0 )
    goto LABEL_44;
  v5 = 0;
  ReferencedAsyncFtpProvider = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *, int *))v31->lpVtbl[1].AddRef)(
                                 v31,
                                 &pv,
                                 &v29);
  (*(void (__fastcall **)(FTP_SERVERP *, _QWORD))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 0);
  if ( ReferencedAsyncFtpProvider < 0 )
  {
    if ( ReferencedAsyncFtpProvider != -2147417848
      && ReferencedAsyncFtpProvider != -2147023170
      && ReferencedAsyncFtpProvider != -2146234348
      && ReferencedAsyncFtpProvider != -2147023174 )
    {
      **((_WORD **)this + 69) = 0;
      *((_DWORD *)this + 142) = 0;
      GetLastComExceptionErrorInfo((LOGON_USER_CONTEXT *)((char *)this + 520));
      *((_DWORD *)this + 126) = 41;
      v6 = (const wchar_t **)((char *)this + 552);
      if ( *((_DWORD *)this + 142) )
        v7 = *v6;
      else
        v7 = L"An error occurred during the authentication process.";
      *((_QWORD *)this + 64) = v7;
      v8 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v8 + 8) && (*(_BYTE *)(v8 + 40) & 0x12) != 0 && *(_DWORD *)(v8 + 44) >= 3u )
      {
        v9 = *v6;
        v10 = *((_QWORD *)this + 1);
        v11 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        FtpExtensibilityEvents::FailCallProvider::RaiseEvent(
          v11,
          (const struct _GUID *)(v10 + 1272),
          ReferencedAsyncFtpProvider,
          v9);
      }
      goto LABEL_44;
    }
    v12 = *((_QWORD *)this + 2);
    v13 = *(_DWORD *)(v12 + 56);
    if ( v13 >= 2 )
    {
      ReferencedAsyncFtpProvider = LOGON_USER_CONTEXT::RequestCustomProviderUpdate(this, *((_DWORD *)this + 48));
      if ( ReferencedAsyncFtpProvider < 0 )
        goto LABEL_44;
      *(_DWORD *)(*((_QWORD *)this + 2) + 56LL) = 0;
    }
    else
    {
      *(_DWORD *)(v12 + 56) = v13 + 1;
    }
    goto LABEL_36;
  }
  if ( !v29 )
  {
    ++*((_DWORD *)this + 48);
LABEL_36:
    if ( v31 )
    {
      ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
      v31 = 0;
    }
    ReferencedAsyncFtpProvider = LOGON_USER_CONTEXT::ProcessUserLogon(this, a2);
    goto LABEL_39;
  }
  *((_DWORD *)this + 54) = 1;
  if ( pv )
    STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 136), (const unsigned __int16 *)pv);
  v14 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  v15 = (CReaderWriterLock3 *)(v14 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v14 + 208));
  v16 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v14 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v16);
  v5 = *(_QWORD *)(v14 + 192);
  CReaderWriterLock3::ReadUnlock(v15);
  v17 = *((unsigned int *)this + 48);
  if ( (unsigned int)v17 <= *(_DWORD *)(v5 + 272) )
  {
    v18 = 600 * v17;
    v19 = *(_QWORD *)(v5 + 280);
    v20 = (CREDENTIALS_CACHE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 192LL))(g_pFtpServer);
    v21 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
    v22 = (const unsigned __int16 *)&dword_18004D454;
    if ( *(_QWORD *)(v21 + 8) )
      v22 = *(const unsigned __int16 **)(v21 + 8);
    v23 = CREDENTIALS_CACHE::Insert(
            v20,
            *((const unsigned __int16 **)this + 7),
            *((const unsigned __int16 **)this + 14),
            *(const unsigned __int16 **)(v18 + v19 + 56),
            v22,
            (const unsigned __int16 *)pv);
    if ( v23 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
        2042,
        "LOGON_USER_CONTEXT::HandleCustomAuthenticateUserCompletion",
        "Failed to insert into credentials cache. hr=0x%x\n",
        v23);
    v24 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v24 + 8) && (*(_BYTE *)(v24 + 40) & 0x12) != 0 && *(_DWORD *)(v24 + 44) >= 4u )
    {
      v25 = *((_QWORD *)this + 1);
      v26 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpExtensibilityEvents::EndCallProvider::RaiseEvent(v26, (const struct _GUID *)(v25 + 1272));
    }
    *((_DWORD *)this + 120) = 103;
    goto LABEL_36;
  }
  ReferencedAsyncFtpProvider = -2147024809;
LABEL_39:
  if ( v5 )
  {
    v27 = _InterlockedDecrement((volatile signed __int32 *)v5);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v27);
    if ( !v27 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
    }
  }
LABEL_44:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v31 )
    ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
  return (unsigned int)ReferencedAsyncFtpProvider;
}

```

## disassembly

```asm
0x18001bd7c  mov     [rsp-38h+arg_18], rbx
0x18001bd81  push    rbp
0x18001bd82  push    rsi
0x18001bd83  push    rdi
0x18001bd84  push    r12
0x18001bd86  push    r13
0x18001bd88  push    r14
0x18001bd8a  push    r15
0x18001bd8c  mov     rbp, rsp
0x18001bd8f  sub     rsp, 30h
0x18001bd93  mov     r12, rdx
0x18001bd96  mov     rsi, rcx
0x18001bd99  xor     r13d, r13d
0x18001bd9c  mov     [rbp+arg_0], r13d
0x18001bda0  mov     [rbp+pv], r13
0x18001bda4  mov     [rbp+arg_10], r13
0x18001bda8  mov     [rdx], r13d
0x18001bdab  lea     rdx, [rbp+arg_10]; struct IUnknown **
0x18001bdaf  mov     rcx, [rcx+10h]; this
0x18001bdb3  call    ?GetReferencedAsyncFtpProvider@ASYNC_COM_CALL_CONTEXT@@QEAAJPEAPEAUIUnknown@@@Z; ASYNC_COM_CALL_CONTEXT::GetReferencedAsyncFtpProvider(IUnknown * *)
0x18001bdb8  mov     r14d, eax
0x18001bdbb  test    eax, eax
0x18001bdbd  js      loc_18001C113
0x18001bdc3  mov     r15d, r13d
0x18001bdc6  mov     rcx, [rbp+arg_10]
0x18001bdca  mov     rax, [rcx]
0x18001bdcd  lea     r8, [rbp+arg_0]
0x18001bdd1  lea     rdx, [rbp+pv]
0x18001bdd5  mov     rax, [rax+20h]
0x18001bdd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdde  mov     r14d, eax
0x18001bde1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bde8  mov     rax, [rcx]
0x18001bdeb  xor     edx, edx
0x18001bded  mov     rax, [rax+0B8h]
0x18001bdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdf9  test    r14d, r14d
0x18001bdfc  jns     loc_18001BF1C
0x18001be02  cmp     r14d, 80010108h
0x18001be09  jz      loc_18001BEE0
0x18001be0f  cmp     r14d, 800706BEh
0x18001be16  jz      loc_18001BEE0
0x18001be1c  cmp     r14d, 80131014h
0x18001be23  jz      loc_18001BEE0
0x18001be29  cmp     r14d, 800706BAh
0x18001be30  jz      loc_18001BEE0
0x18001be36  lea     rcx, [rsi+208h]; struct STRU *
0x18001be3d  mov     rdx, [rcx+20h]; int
0x18001be41  mov     [rdx], r13w
0x18001be45  mov     [rcx+30h], r13d
0x18001be49  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x18001be4e  mov     dword ptr [rsi+1F8h], 29h ; ')'
0x18001be58  lea     rbx, [rsi+228h]
0x18001be5f  cmp     [rsi+238h], r13d
0x18001be66  jz      short loc_18001BE6D
0x18001be68  mov     rcx, [rbx]
0x18001be6b  jmp     short loc_18001BE74
0x18001be6d  lea     rcx, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001be74  mov     [rsi+200h], rcx
0x18001be7b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001be82  mov     rax, [rcx]
0x18001be85  mov     rax, [rax+20h]
0x18001be89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be8e  cmp     [rax+8], r13d
0x18001be92  jz      loc_18001C113
0x18001be98  test    byte ptr [rax+28h], 12h
0x18001be9c  jz      loc_18001C113
0x18001bea2  cmp     dword ptr [rax+2Ch], 3
0x18001bea6  jb      loc_18001C113
0x18001beac  mov     rbx, [rbx]
0x18001beaf  mov     rdi, [rsi+8]
0x18001beb3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001beba  mov     rax, [rcx]
0x18001bebd  mov     rax, [rax+20h]
0x18001bec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bec6  mov     r9, rbx; unsigned __int16 *
0x18001bec9  mov     r8d, r14d; unsigned int
0x18001becc  lea     rdx, [rdi+4F8h]; struct _GUID *
0x18001bed3  mov     rcx, rax; struct CEtwTracer *
0x18001bed6  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x18001bedb  jmp     loc_18001C113
0x18001bee0  mov     rcx, [rsi+10h]
0x18001bee4  mov     eax, [rcx+38h]
0x18001bee7  cmp     eax, 2
0x18001beea  jnb     short loc_18001BEF6
0x18001beec  inc     eax
0x18001beee  mov     [rcx+38h], eax
0x18001bef1  jmp     loc_18001C0A8
0x18001bef6  mov     edx, [rsi+0C0h]; unsigned int
0x18001befc  mov     rcx, rsi; this
0x18001beff  call    ?RequestCustomProviderUpdate@LOGON_USER_CONTEXT@@AEAAJK@Z; LOGON_USER_CONTEXT::RequestCustomProviderUpdate(ulong)
0x18001bf04  mov     r14d, eax
0x18001bf07  test    eax, eax
0x18001bf09  js      loc_18001C113
0x18001bf0f  mov     rax, [rsi+10h]
0x18001bf13  mov     [rax+38h], r13d
0x18001bf17  jmp     loc_18001C0A8
0x18001bf1c  cmp     [rbp+arg_0], r13d
0x18001bf20  jz      loc_18001C0A2
0x18001bf26  mov     dword ptr [rsi+0D8h], 1
0x18001bf30  mov     rdx, [rbp+pv]
0x18001bf34  test    rdx, rdx
0x18001bf37  jz      short loc_18001BF46
0x18001bf39  lea     rcx, [rsi+88h]
0x18001bf40  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001bf46  mov     rax, [rsi+8]
0x18001bf4a  mov     r15, [rax+10h]
0x18001bf4e  lea     rbx, [r15+0D0h]
0x18001bf55  mov     rcx, rbx
0x18001bf58  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001bf5e  mov     r8, [r15+0C0h]
0x18001bf65  mov     edx, 1
0x18001bf6a  lock xadd [r8], edx
0x18001bf6f  inc     edx
0x18001bf71  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001bf78  test    rcx, rcx
0x18001bf7b  jz      short loc_18001BF83
0x18001bf7d  call    cs:__imp_WriteRefTraceLog
0x18001bf83  mov     r15, [r15+0C0h]
0x18001bf8a  mov     rcx, rbx
0x18001bf8d  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001bf93  mov     eax, [rsi+0C0h]
0x18001bf99  cmp     eax, [r15+110h]
0x18001bfa0  ja      loc_18001C09A
0x18001bfa6  imul    rdi, rax, 258h
0x18001bfad  mov     rbx, [r15+118h]
0x18001bfb4  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bfbb  mov     rax, [rcx]
0x18001bfbe  mov     rax, [rax+0C0h]
0x18001bfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfca  mov     r8, [rbp+pv]
0x18001bfce  mov     rcx, [rsi+8]
0x18001bfd2  mov     rdx, [rcx+10h]
0x18001bfd6  lea     rcx, dword_18004D454
0x18001bfdd  cmp     [rdx+8], r13
0x18001bfe1  cmovnz  rcx, [rdx+8]
0x18001bfe6  mov     [rsp+30h+var_8], r8; unsigned __int16 *
0x18001bfeb  mov     [rsp+30h+var_10], rcx; unsigned __int16 *
0x18001bff0  mov     r9, [rdi+rbx+38h]; unsigned __int16 *
0x18001bff5  mov     r8, [rsi+70h]; unsigned __int16 *
0x18001bff9  mov     rdx, [rsi+38h]; unsigned __int16 *
0x18001bffd  mov     rcx, rax; this
0x18001c000  call    ?Insert@CREDENTIALS_CACHE@@QEAAJPEBG0000@Z; CREDENTIALS_CACHE::Insert(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c005  test    eax, eax
0x18001c007  jns     short loc_18001C043
0x18001c009  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c010  jz      short loc_18001C043
0x18001c012  mov     dword ptr [rsp+30h+var_8], eax
0x18001c016  lea     rax, aFailedToInsert; "Failed to insert into credentials cache"...
0x18001c01d  mov     [rsp+30h+var_10], rax
0x18001c022  lea     r9, aLogonUserConte_2; "LOGON_USER_CONTEXT::HandleCustomAuthent"...
0x18001c029  mov     r8d, 7FAh
0x18001c02f  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001c036  mov     rcx, cs:g_pDebug
0x18001c03d  call    cs:__imp_PuDbgPrint
0x18001c043  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c04a  mov     rax, [rcx]
0x18001c04d  mov     rax, [rax+20h]
0x18001c051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c056  cmp     [rax+8], r13d
0x18001c05a  jz      short loc_18001C08E
0x18001c05c  test    byte ptr [rax+28h], 12h
0x18001c060  jz      short loc_18001C08E
0x18001c062  cmp     dword ptr [rax+2Ch], 4
0x18001c066  jb      short loc_18001C08E
0x18001c068  mov     rbx, [rsi+8]
0x18001c06c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c073  mov     rax, [rcx]
0x18001c076  mov     rax, [rax+20h]
0x18001c07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c07f  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001c086  mov     rcx, rax; struct CEtwTracer *
0x18001c089  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x18001c08e  mov     dword ptr [rsi+1E0h], 67h ; 'g'
0x18001c098  jmp     short loc_18001C0A8
0x18001c09a  mov     r14d, 80070057h
0x18001c0a0  jmp     short loc_18001C0CF
0x18001c0a2  inc     dword ptr [rsi+0C0h]
0x18001c0a8  mov     rcx, [rbp+arg_10]
0x18001c0ac  test    rcx, rcx
0x18001c0af  jz      short loc_18001C0C1
0x18001c0b1  mov     rax, [rcx]
0x18001c0b4  mov     rax, [rax+10h]
0x18001c0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0bd  mov     [rbp+arg_10], r13
0x18001c0c1  mov     rdx, r12; int *
0x18001c0c4  mov     rcx, rsi; this
0x18001c0c7  call    ?ProcessUserLogon@LOGON_USER_CONTEXT@@QEAAJPEAH@Z; LOGON_USER_CONTEXT::ProcessUserLogon(int *)
0x18001c0cc  mov     r14d, eax
0x18001c0cf  test    r15, r15
0x18001c0d2  jz      short loc_18001C113
0x18001c0d4  or      ebx, 0FFFFFFFFh
0x18001c0d7  lock xadd [r15], ebx
0x18001c0dc  dec     ebx
0x18001c0de  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c0e5  test    rcx, rcx
0x18001c0e8  jz      short loc_18001C0F5
0x18001c0ea  mov     r8, r15
0x18001c0ed  mov     edx, ebx
0x18001c0ef  call    cs:__imp_WriteRefTraceLog
0x18001c0f5  test    ebx, ebx
0x18001c0f7  jnz     short loc_18001C113
0x18001c0f9  mov     rcx, r15; this
0x18001c0fc  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001c101  nop
0x18001c102  mov     rdx, r15
0x18001c105  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001c10c  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001c112  nop
0x18001c113  mov     rcx, [rbp+pv]; pv
0x18001c117  test    rcx, rcx
0x18001c11a  jz      short loc_18001C126
0x18001c11c  call    cs:__imp_CoTaskMemFree
0x18001c122  mov     [rbp+pv], r13
0x18001c126  mov     rcx, [rbp+arg_10]
0x18001c12a  test    rcx, rcx
0x18001c12d  jz      short loc_18001C13B
0x18001c12f  mov     rax, [rcx]
0x18001c132  mov     rax, [rax+10h]
0x18001c136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c13b  mov     eax, r14d
0x18001c13e  mov     rbx, [rsp+30h+arg_18]
0x18001c146  add     rsp, 30h
0x18001c14a  pop     r15
0x18001c14c  pop     r14
0x18001c14e  pop     r13
0x18001c150  pop     r12
0x18001c152  pop     rdi
0x18001c153  pop     rsi
0x18001c154  pop     rbp
0x18001c155  retn
```
