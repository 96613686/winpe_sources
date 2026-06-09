# LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon(int *)

- ea: `0x18001a9ec`
- end: `0x18001ae8f`
- name: `?AsyncHandleCustomAuthenticationLogon@LOGON_USER_CONTEXT@@AEAAJPEAH@Z`
- size: `1187`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c998`

## callees

- `0x180009090`
- `0x18001951c`
- `0x1800195e0`
- `0x1800197ac`
- `0x180019b48`
- `0x180019bd4`
- `0x18001a9ec`
- `0x18001d484`
- `0x18001d544`
- `0x18001d624`
- `0x180049010`

## import_xrefs

- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab1a`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab1a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001aa28`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab08`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001aa28`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab08`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001acb5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ad42`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001acb5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ad42`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab6b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001accd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ad53`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab6b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001accd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ad53`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001ae3e`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001ae3e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001aa5c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab76`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001aa5c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab76`
- `iisutil!WriteRefTraceLog` at `0x18001aa4c`
- `iisutil!WriteRefTraceLog` at `0x18001ae21`
- `iisutil!WriteRefTraceLog` at `0x18001aa4c`
- `iisutil!WriteRefTraceLog` at `0x18001ae21`
- `iisutil!PuDbgPrintError` at `0x18001ac20`
- `iisutil!PuDbgPrintError` at `0x18001ac20`

## string_xrefs

- `0x18001adaa`: `An error occurred during the authentication process.`

## pseudocode

```c
__int64 __fastcall LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon(LOGON_USER_CONTEXT *this, int *a2)
{
  struct ICallFactory *v4; // r12
  __int64 v5; // r13
  __int64 v6; // rdx
  __int64 v7; // r15
  unsigned int v8; // eax
  __int64 v9; // rcx
  _QWORD *v10; // r14
  __int64 v11; // rax
  const unsigned __int16 *v12; // rdi
  __int64 v13; // rbx
  struct CEtwTracer *v14; // rax
  signed int CustomProviderNoLock; // ebp
  int v16; // edi
  const struct _GUID *v17; // rdx
  const wchar_t *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdi
  __int64 v22; // rbx
  struct CEtwTracer *v23; // rax
  _DWORD *v24; // rbx
  int *v25; // r8
  __int64 v26; // rsi
  int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  struct CEtwTracer *v31; // rax
  unsigned __int32 v32; // ebx
  struct IUnknown *v34; // [rsp+70h] [rbp+8h] BYREF
  int *v35; // [rsp+78h] [rbp+10h]

  v35 = a2;
  v4 = 0;
  v34 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v5 + 208));
  v6 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v5 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v6);
  v7 = *(_QWORD *)(v5 + 192);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v5 + 208));
  v8 = *(_DWORD *)(v7 + 272);
  *a2 = 0;
  v9 = *((unsigned int *)this + 48);
  if ( (unsigned int)v9 >= v8 )
  {
    CustomProviderNoLock = -2147023570;
    *((_DWORD *)this + 126) = 41;
    goto LABEL_43;
  }
  if ( (unsigned int)v9 > *(_DWORD *)(v7 + 272) )
  {
    CustomProviderNoLock = -2147024809;
LABEL_45:
    v29 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v29 + 8) && (*(_BYTE *)(v29 + 40) & 8) != 0 && *(_DWORD *)(v29 + 44) >= 3u )
    {
      v30 = *((_QWORD *)this + 1);
      v31 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpAuthenticationEvents::FailCustomLogon::RaiseEvent(
        v31,
        (const struct _GUID *)(v30 + 1272),
        CustomProviderNoLock);
    }
    goto LABEL_49;
  }
  v10 = (_QWORD *)(*(_QWORD *)(v7 + 280) + 600 * v9);
  v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v11 + 8) && (*(_BYTE *)(v11 + 40) & 8) != 0 && *(_DWORD *)(v11 + 44) >= 4u )
  {
    v12 = (const unsigned __int16 *)v10[7];
    v13 = *((_QWORD *)this + 1);
    v14 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpAuthenticationEvents::StartCustomLogon::RaiseEvent(v14, (const struct _GUID *)(v13 + 1272), v12);
  }
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 64) = &WideCharStr;
  CustomProviderNoLock = 0;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v10 + 69));
  if ( v10[73] )
  {
    v16 = 0;
  }
  else
  {
    CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)(v10 + 69));
    v16 = 1;
    if ( !v10[73] )
    {
      CustomProviderNoLock = CUSTOM_PROVIDER_ENTRY::LoadCustomProviderNoLock(
                               (CUSTOM_PROVIDER_ENTRY *)v10,
                               &GUID_00000000_0000_0000_c000_000000000046,
                               1);
      if ( CustomProviderNoLock < 0 )
        goto LABEL_15;
    }
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10[73] + 8LL))(v10[73]);
  v4 = (struct ICallFactory *)v10[73];
  if ( v16 )
  {
LABEL_15:
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v10 + 69));
    goto LABEL_17;
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v10 + 69));
LABEL_17:
  if ( CustomProviderNoLock < 0 )
    goto LABEL_18;
  v19 = ASYNC_COM_CALL_CONTEXT::InitializeOrUpdate(
          *((ASYNC_COM_CALL_CONTEXT **)this + 2),
          v17,
          v4,
          (LOGON_USER_CONTEXT *)((char *)this + 416));
  CustomProviderNoLock = v19;
  if ( v19 < 0 )
  {
    if ( v19 == -2147417848 || v19 == -2147023170 || v19 == -2146234348 || v19 == -2147023174 )
      CUSTOM_PROVIDER_ENTRY::Invalidate((CUSTOM_PROVIDER_ENTRY *)v10);
    ASYNC_COM_CALL_CONTEXT::ResetData(*((ASYNC_COM_CALL_CONTEXT **)this + 2));
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
        1770,
        "LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon",
        CustomProviderNoLock,
        "Failed to get referenced ICallFactory interface ");
    goto LABEL_18;
  }
  CustomProviderNoLock = ASYNC_COM_CALL_CONTEXT::GetReferencedAsyncFtpProvider(
                           *((ASYNC_COM_CALL_CONTEXT **)this + 2),
                           &v34);
  if ( CustomProviderNoLock < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
        1794,
        "LOGON_USER_CONTEXT::AsyncHandleCustomAuthenticationLogon",
        CustomProviderNoLock,
        "GetReferencedAsyncCustomHandler() failed.");
LABEL_18:
    *((_DWORD *)this + 126) = 41;
    if ( *((_DWORD *)this + 142) )
    {
      v18 = (const wchar_t *)*((_QWORD *)this + 69);
LABEL_44:
      *((_QWORD *)this + 64) = v18;
      goto LABEL_45;
    }
LABEL_43:
    v18 = L"An error occurred during the authentication process.";
    goto LABEL_44;
  }
  v20 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v20 + 8) && (*(_BYTE *)(v20 + 40) & 0x12) != 0 && *(_DWORD *)(v20 + 44) >= 4u )
  {
    v21 = (const unsigned __int16 *)v10[7];
    v22 = *((_QWORD *)this + 1);
    v23 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpExtensibilityEvents::StartCallProvider::RaiseEvent(v23, (const struct _GUID *)(v22 + 1272), v21);
  }
  v24 = (_DWORD *)*((_QWORD *)this + 2);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v24 + 3));
  v24[12] = 0;
  v24[13] = 1;
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v24 + 3));
  (*(void (__fastcall **)(FTP_SERVERP *, _QWORD))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 0);
  v25 = &dword_18004D454;
  if ( *(_QWORD *)(v5 + 8) )
    v25 = *(int **)(v5 + 8);
  ((void (__fastcall *)(struct IUnknown *, _QWORD, int *, _QWORD, _QWORD))v34->lpVtbl[1].QueryInterface)(
    v34,
    *(_QWORD *)(*((_QWORD *)this + 1) + 1168LL),
    v25,
    *((_QWORD *)this + 7),
    *((_QWORD *)this + 14));
  ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
  v34 = 0;
  v26 = *((_QWORD *)this + 2);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v26 + 12));
  *(_DWORD *)(v26 + 52) = 0;
  v27 = *(_DWORD *)(v26 + 48);
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v26 + 12));
  if ( v27 )
  {
    v28 = *(_QWORD *)(v26 + 40);
    *(_DWORD *)(v28 + 68) = 0;
    *(_QWORD *)(v28 + 72) = 0;
    *(_DWORD *)(v28 + 80) = 1;
    (*(void (__fastcall **)(FTP_SERVERP *, _QWORD))(*(_QWORD *)g_pFtpServer + 80LL))(
      g_pFtpServer,
      *(_QWORD *)(v26 + 40));
  }
  *v35 = 1;
LABEL_49:
  v32 = _InterlockedDecrement((volatile signed __int32 *)v7);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v32);
  if ( !v32 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v7);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v7);
  }
  if ( v34 )
  {
    ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(struct ICallFactory *))v4->lpVtbl->Release)(v4);
  return (unsigned int)CustomProviderNoLock;
}

```

## disassembly

```asm
0x18001a9ec  mov     [rsp+arg_10], rbx
0x18001a9f1  mov     [rsp+arg_8], rdx
0x18001a9f6  push    rbp
0x18001a9f7  push    rsi
0x18001a9f8  push    rdi
0x18001a9f9  push    r12
0x18001a9fb  push    r13
0x18001a9fd  push    r14
0x18001a9ff  push    r15
0x18001aa01  sub     rsp, 30h
0x18001aa05  mov     rdi, rdx
0x18001aa08  mov     rsi, rcx
0x18001aa0b  xor     r14d, r14d
0x18001aa0e  mov     r12d, r14d
0x18001aa11  mov     [rsp+68h+arg_0], r14
0x18001aa16  mov     rax, [rcx+8]
0x18001aa1a  mov     r13, [rax+10h]
0x18001aa1e  lea     rbx, [r13+0D0h]
0x18001aa25  mov     rcx, rbx
0x18001aa28  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001aa2e  mov     r8, [r13+0C0h]
0x18001aa35  lea     edx, [r14+1]
0x18001aa39  lock xadd [r8], edx
0x18001aa3e  inc     edx
0x18001aa40  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001aa47  test    rcx, rcx
0x18001aa4a  jz      short loc_18001AA52
0x18001aa4c  call    cs:__imp_WriteRefTraceLog
0x18001aa52  mov     r15, [r13+0C0h]
0x18001aa59  mov     rcx, rbx
0x18001aa5c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001aa62  mov     eax, [r15+110h]
0x18001aa69  mov     [rdi], r14d
0x18001aa6c  mov     ecx, [rsi+0C0h]
0x18001aa72  cmp     ecx, eax
0x18001aa74  jnb     loc_18001AD9B
0x18001aa7a  cmp     ecx, [r15+110h]
0x18001aa81  ja      loc_18001AD94
0x18001aa87  imul    r14, rcx, 258h
0x18001aa8e  add     r14, [r15+118h]
0x18001aa95  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001aa9c  mov     rax, [rcx]
0x18001aa9f  mov     rax, [rax+20h]
0x18001aaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa8  cmp     [rax+8], r12d
0x18001aaac  jz      short loc_18001AAE7
0x18001aaae  test    byte ptr [rax+28h], 8
0x18001aab2  jz      short loc_18001AAE7
0x18001aab4  cmp     dword ptr [rax+2Ch], 4
0x18001aab8  jb      short loc_18001AAE7
0x18001aaba  mov     rdi, [r14+38h]
0x18001aabe  mov     rbx, [rsi+8]
0x18001aac2  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001aac9  mov     rax, [rcx]
0x18001aacc  mov     rax, [rax+20h]
0x18001aad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aad5  mov     r8, rdi; unsigned __int16 *
0x18001aad8  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001aadf  mov     rcx, rax; struct CEtwTracer *
0x18001aae2  call    ?RaiseEvent@StartCustomLogon@FtpAuthenticationEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpAuthenticationEvents::StartCustomLogon::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18001aae7  mov     [rsi+1F8h], r12d
0x18001aaee  lea     rax, WideCharStr
0x18001aaf5  mov     [rsi+200h], rax
0x18001aafc  xor     ebp, ebp
0x18001aafe  lea     rbx, [r14+228h]
0x18001ab05  mov     rcx, rbx
0x18001ab08  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001ab0e  cmp     [r14+248h], rbp
0x18001ab15  jnz     short loc_18001AB48
0x18001ab17  mov     rcx, rbx
0x18001ab1a  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x18001ab20  lea     eax, [rbp+1]
0x18001ab23  mov     edi, eax
0x18001ab25  cmp     [r14+248h], rbp
0x18001ab2c  jnz     short loc_18001AB4A
0x18001ab2e  mov     r8d, eax; int
0x18001ab31  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18001ab38  mov     rcx, r14; this
0x18001ab3b  call    ?LoadCustomProviderNoLock@CUSTOM_PROVIDER_ENTRY@@AEAAJAEBU_GUID@@H@Z; CUSTOM_PROVIDER_ENTRY::LoadCustomProviderNoLock(_GUID const &,int)
0x18001ab40  mov     ebp, eax
0x18001ab42  test    eax, eax
0x18001ab44  js      short loc_18001AB68
0x18001ab46  jmp     short loc_18001AB4A
0x18001ab48  xor     edi, edi
0x18001ab4a  mov     rcx, [r14+248h]
0x18001ab51  mov     rax, [rcx]
0x18001ab54  mov     rax, [rax+8]
0x18001ab58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab5d  mov     r12, [r14+248h]
0x18001ab64  test    edi, edi
0x18001ab66  jz      short loc_18001AB73
0x18001ab68  mov     rcx, rbx
0x18001ab6b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001ab71  jmp     short loc_18001AB7C
0x18001ab73  mov     rcx, rbx
0x18001ab76  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001ab7c  test    ebp, ebp
0x18001ab7e  jns     short loc_18001ABA6
0x18001ab80  mov     dword ptr [rsi+1F8h], 29h ; ')'
0x18001ab8a  xor     r14d, r14d
0x18001ab8d  cmp     [rsi+238h], r14d
0x18001ab94  jz      loc_18001ADAA
0x18001ab9a  mov     rax, [rsi+228h]
0x18001aba1  jmp     loc_18001ADB1
0x18001aba6  lea     r9, [rsi+1A0h]; struct FTP_ASYNC_CONTEXT *
0x18001abad  mov     r8, r12; struct ICallFactory *
0x18001abb0  mov     rcx, [rsi+10h]; this
0x18001abb4  call    ?InitializeOrUpdate@ASYNC_COM_CALL_CONTEXT@@QEAAJAEBU_GUID@@PEAUICallFactory@@PEAVFTP_ASYNC_CONTEXT@@@Z; ASYNC_COM_CALL_CONTEXT::InitializeOrUpdate(_GUID const &,ICallFactory *,FTP_ASYNC_CONTEXT *)
0x18001abb9  mov     ebp, eax
0x18001abbb  test    eax, eax
0x18001abbd  jns     short loc_18001AC2B
0x18001abbf  cmp     eax, 80010108h
0x18001abc4  jz      short loc_18001ABDB
0x18001abc6  cmp     eax, 800706BEh
0x18001abcb  jz      short loc_18001ABDB
0x18001abcd  cmp     eax, 80131014h
0x18001abd2  jz      short loc_18001ABDB
0x18001abd4  cmp     eax, 800706BAh
0x18001abd9  jnz     short loc_18001ABE3
0x18001abdb  mov     rcx, r14; this
0x18001abde  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x18001abe3  mov     rcx, [rsi+10h]; this
0x18001abe7  call    ?ResetData@ASYNC_COM_CALL_CONTEXT@@QEAAXXZ; ASYNC_COM_CALL_CONTEXT::ResetData(void)
0x18001abec  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001abf3  jz      short loc_18001AB80
0x18001abf5  lea     rax, aFailedToGetRef_0; "Failed to get referenced ICallFactory i"...
0x18001abfc  mov     r8d, 6EAh
0x18001ac02  mov     [rsp+68h+var_40], rax
0x18001ac07  lea     r9, aLogonUserConte_5; "LOGON_USER_CONTEXT::AsyncHandleCustomAu"...
0x18001ac0e  mov     dword ptr [rsp+68h+var_48], ebp
0x18001ac12  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ac19  mov     rcx, cs:g_pDebug
0x18001ac20  call    cs:__imp_PuDbgPrintError
0x18001ac26  jmp     loc_18001AB80
0x18001ac2b  lea     rdx, [rsp+68h+arg_0]; struct IUnknown **
0x18001ac30  mov     rcx, [rsi+10h]; this
0x18001ac34  call    ?GetReferencedAsyncFtpProvider@ASYNC_COM_CALL_CONTEXT@@QEAAJPEAPEAUIUnknown@@@Z; ASYNC_COM_CALL_CONTEXT::GetReferencedAsyncFtpProvider(IUnknown * *)
0x18001ac39  mov     ebp, eax
0x18001ac3b  test    eax, eax
0x18001ac3d  jns     short loc_18001AC5B
0x18001ac3f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001ac46  jz      loc_18001AB80
0x18001ac4c  lea     rax, aGetreferenceda; "GetReferencedAsyncCustomHandler() faile"...
0x18001ac53  mov     r8d, 702h
0x18001ac59  jmp     short loc_18001AC02
0x18001ac5b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001ac62  mov     rax, [rcx]
0x18001ac65  mov     rax, [rax+20h]
0x18001ac69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac6e  cmp     dword ptr [rax+8], 0
0x18001ac72  jz      short loc_18001ACAD
0x18001ac74  test    byte ptr [rax+28h], 12h
0x18001ac78  jz      short loc_18001ACAD
0x18001ac7a  cmp     dword ptr [rax+2Ch], 4
0x18001ac7e  jb      short loc_18001ACAD
0x18001ac80  mov     rdi, [r14+38h]
0x18001ac84  mov     rbx, [rsi+8]
0x18001ac88  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001ac8f  mov     rax, [rcx]
0x18001ac92  mov     rax, [rax+20h]
0x18001ac96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac9b  mov     r8, rdi; unsigned __int16 *
0x18001ac9e  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001aca5  mov     rcx, rax; struct CEtwTracer *
0x18001aca8  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18001acad  mov     rbx, [rsi+10h]
0x18001acb1  lea     rcx, [rbx+0Ch]
0x18001acb5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001acbb  xor     r14d, r14d
0x18001acbe  mov     [rbx+30h], r14d
0x18001acc2  mov     dword ptr [rbx+34h], 1
0x18001acc9  lea     rcx, [rbx+0Ch]
0x18001accd  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001acd3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001acda  mov     rax, [rcx]
0x18001acdd  xor     edx, edx
0x18001acdf  mov     rax, [rax+0B0h]
0x18001ace6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aceb  mov     rcx, [rsp+68h+arg_0]
0x18001acf0  mov     rax, [rcx]
0x18001acf3  mov     r10, [rsi+70h]
0x18001acf7  lea     r8, dword_18004D454
0x18001acfe  cmp     [r13+8], r14
0x18001ad02  cmovnz  r8, [r13+8]
0x18001ad07  mov     rdx, [rsi+8]
0x18001ad0b  mov     [rsp+68h+var_48], r10
0x18001ad10  mov     r9, [rsi+38h]
0x18001ad14  mov     rdx, [rdx+490h]
0x18001ad1b  mov     rax, [rax+18h]
0x18001ad1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad24  mov     rcx, [rsp+68h+arg_0]
0x18001ad29  mov     rax, [rcx]
0x18001ad2c  mov     rax, [rax+10h]
0x18001ad30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad35  mov     [rsp+68h+arg_0], r14
0x18001ad3a  mov     rsi, [rsi+10h]
0x18001ad3e  lea     rcx, [rsi+0Ch]
0x18001ad42  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001ad48  mov     [rsi+34h], r14d
0x18001ad4c  mov     ebx, [rsi+30h]
0x18001ad4f  lea     rcx, [rsi+0Ch]
0x18001ad53  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001ad59  test    ebx, ebx
0x18001ad5b  jz      short loc_18001AD87
0x18001ad5d  mov     rax, [rsi+28h]
0x18001ad61  mov     [rax+44h], r14d
0x18001ad65  mov     [rax+48h], r14
0x18001ad69  mov     dword ptr [rax+50h], 1
0x18001ad70  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001ad77  mov     rax, [rcx]
0x18001ad7a  mov     rdx, [rsi+28h]
0x18001ad7e  mov     rax, [rax+50h]
0x18001ad82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad87  mov     rax, [rsp+68h+arg_8]
0x18001ad8c  mov     dword ptr [rax], 1
0x18001ad92  jmp     short loc_18001AE06
0x18001ad94  mov     ebp, 80070057h
0x18001ad99  jmp     short loc_18001ADB8
0x18001ad9b  mov     ebp, 8007052Eh
0x18001ada0  mov     dword ptr [rsi+1F8h], 29h ; ')'
0x18001adaa  lea     rax, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001adb1  mov     [rsi+200h], rax
0x18001adb8  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001adbf  mov     rax, [rcx]
0x18001adc2  mov     rax, [rax+20h]
0x18001adc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adcb  cmp     [rax+8], r14d
0x18001adcf  jz      short loc_18001AE06
0x18001add1  test    byte ptr [rax+28h], 8
0x18001add5  jz      short loc_18001AE06
0x18001add7  cmp     dword ptr [rax+2Ch], 3
0x18001addb  jb      short loc_18001AE06
0x18001addd  mov     rbx, [rsi+8]
0x18001ade1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001ade8  mov     rax, [rcx]
0x18001adeb  mov     rax, [rax+20h]
0x18001adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adf4  mov     r8d, ebp; unsigned int
0x18001adf7  lea     rdx, [rbx+4F8h]; struct _GUID *
0x18001adfe  mov     rcx, rax; struct CEtwTracer *
0x18001ae01  call    ?RaiseEvent@FailCustomLogon@FtpAuthenticationEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@K@Z; FtpAuthenticationEvents::FailCustomLogon::RaiseEvent(CEtwTracer *,_GUID const *,ulong)
0x18001ae06  or      ebx, 0FFFFFFFFh
0x18001ae09  lock xadd [r15], ebx
0x18001ae0e  dec     ebx
0x18001ae10  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001ae17  test    rcx, rcx
0x18001ae1a  jz      short loc_18001AE27
0x18001ae1c  mov     r8, r15
0x18001ae1f  mov     edx, ebx
0x18001ae21  call    cs:__imp_WriteRefTraceLog
0x18001ae27  test    ebx, ebx
0x18001ae29  jnz     short loc_18001AE45
0x18001ae2b  mov     rcx, r15; this
0x18001ae2e  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001ae33  nop
0x18001ae34  mov     rdx, r15
0x18001ae37  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001ae3e  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001ae44  nop
0x18001ae45  mov     rcx, [rsp+68h+arg_0]
0x18001ae4a  test    rcx, rcx
0x18001ae4d  jz      short loc_18001AE60
0x18001ae4f  mov     rax, [rcx]
0x18001ae52  mov     rax, [rax+10h]
0x18001ae56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae5b  mov     [rsp+68h+arg_0], r14
0x18001ae60  test    r12, r12
0x18001ae63  jz      short loc_18001AE75
0x18001ae65  mov     rax, [r12]
0x18001ae69  mov     rcx, r12
0x18001ae6c  mov     rax, [rax+10h]
0x18001ae70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae75  mov     eax, ebp
0x18001ae77  mov     rbx, [rsp+68h+arg_10]
0x18001ae7f  add     rsp, 30h
0x18001ae83  pop     r15
0x18001ae85  pop     r14
0x18001ae87  pop     r13
0x18001ae89  pop     r12
0x18001ae8b  pop     rdi
0x18001ae8c  pop     rsi
0x18001ae8d  pop     rbp
0x18001ae8e  retn
```
