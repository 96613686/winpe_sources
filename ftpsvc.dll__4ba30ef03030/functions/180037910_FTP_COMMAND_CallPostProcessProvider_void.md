# FTP_COMMAND::CallPostProcessProvider(void)

- ea: `0x180037910`
- end: `0x180037f0d`
- name: `?CallPostProcessProvider@FTP_COMMAND@@QEAAJXZ`
- size: `1533`
- prototype: `__int64 __fastcall(FTP_COMMAND *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035240`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x180019b48`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d544`
- `0x18002c12c`
- `0x180037910`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180037b2b`
- `msvcrt!_wcsicmp` at `0x180037b43`
- `msvcrt!_wcsicmp` at `0x180037b2b`
- `msvcrt!_wcsicmp` at `0x180037b43`
- `KERNEL32!SystemTimeToFileTime` at `0x180037a43`
- `KERNEL32!SystemTimeToFileTime` at `0x180037a43`
- `KERNEL32!GetLastError` at `0x180037ee5`
- `KERNEL32!GetLastError` at `0x180037ee5`
- `WS2_32!__imp_ntohs` at `0x180037ace`
- `WS2_32!__imp_ntohs` at `0x180037afa`
- `WS2_32!__imp_ntohs` at `0x180037ace`
- `WS2_32!__imp_ntohs` at `0x180037afa`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003797a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003797a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180037ea6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180037ea6`
- `iisutil!PuDbgPrint` at `0x180037e34`
- `iisutil!PuDbgPrint` at `0x180037e34`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800379af`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800379af`
- `iisutil!WriteRefTraceLog` at `0x18003799f`
- `iisutil!WriteRefTraceLog` at `0x180037e89`
- `iisutil!WriteRefTraceLog` at `0x18003799f`
- `iisutil!WriteRefTraceLog` at `0x180037e89`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180037cd9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180037cd9`
- `iisutil!PuDbgPrintError` at `0x180037caa`
- `iisutil!PuDbgPrintError` at `0x180037caa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180037d21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180037d21`

## string_xrefs

- `0x180037c9c`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_command.cxx`
- `0x180037e26`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_command.cxx`
- `0x180037c8f`: `FTP_COMMAND::CallPostProcessProvider`
- `0x180037e19`: `FTP_COMMAND::CallPostProcessProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_COMMAND::CallPostProcessProvider(FTP_COMMAND *this)
{
  __int64 v2; // r15
  CReaderWriterLock3 *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // r12d
  _DWORD *v8; // rdi
  CUSTOM_PROVIDER_ENTRY *v9; // r13
  int ReferencedProvider; // eax
  int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // rax
  int *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  bool v17; // zf
  const wchar_t *v18; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdi
  const struct _GUID *v22; // rbx
  struct CEtwTracer *v23; // rax
  unsigned int v24; // ebx
  __int64 v25; // rax
  int v26; // edx
  unsigned __int16 *v27; // rbx
  const struct _GUID *v28; // rdi
  struct CEtwTracer *v29; // rax
  __int64 v30; // rax
  const struct _GUID *v31; // rbx
  struct CEtwTracer *v32; // rax
  unsigned __int32 v33; // ebx
  signed int LastError; // eax
  struct IUnknown *v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-B8h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v39[5]; // [rsp+60h] [rbp-A0h] BYREF
  int v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h]
  int v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  const wchar_t *v45; // [rsp+B0h] [rbp-50h]
  const wchar_t *v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+D0h] [rbp-30h]
  int v50; // [rsp+D4h] [rbp-2Ch]
  int v51; // [rsp+D8h] [rbp-28h]
  struct _FILETIME v52; // [rsp+DCh] [rbp-24h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  __int64 v54; // [rsp+F0h] [rbp-10h]
  SYSTEMTIME SystemTime; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v56[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v57; // [rsp+130h] [rbp+30h]

  v36 = 0;
  memset_0(v39, 0, 0x98u);
  SystemTime = 0;
  FileTime = 0;
  v2 = *(_QWORD *)(*((_QWORD *)this + 132) + 96LL);
  v3 = (CReaderWriterLock3 *)(v2 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v2 + 208));
  v4 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v2 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v4);
  v5 = *(_QWORD *)(v2 + 192);
  CReaderWriterLock3::ReadUnlock(v3);
  v6 = *(_DWORD *)(v5 + 320);
  if ( v6 )
  {
    v7 = 0;
    v8 = (_DWORD *)((char *)this + 1176);
    while ( !*v8 )
    {
      if ( v7 > v6 )
      {
        v11 = -2147024809;
        goto LABEL_46;
      }
      v9 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v5 + 328) + 600LL * v7);
      ReferencedProvider = CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
                             v9,
                             &GUID_4522cbc6_16cd_49ad_8653_9a2c579e4280,
                             &v36);
      v11 = ReferencedProvider;
      if ( ReferencedProvider >= 0 )
      {
        if ( !v39[0] )
        {
          SystemTime = *(SYSTEMTIME *)(*((_QWORD *)this + 132) + 4676LL);
          if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_46;
          }
          v39[0] = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 132) + 64LL))(*((_QWORD *)this + 132));
          v12 = *((_QWORD *)this + 132);
          v13 = *(_QWORD *)(v12 + 96);
          v14 = &dword_18004D454;
          if ( *(_QWORD *)(v13 + 8) )
            v14 = *(int **)(v13 + 8);
          v39[1] = v14;
          v39[2] = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v12 + 1056) + 48LL))(*(_QWORD *)(v12 + 1056));
          v15 = (_QWORD *)*((_QWORD *)this + 132);
          v39[3] = v15[113];
          v39[4] = v15[728];
          v40 = ntohs(*(_WORD *)(v15[135] + 450LL));
          v16 = *((_QWORD *)this + 132);
          v41 = *(_QWORD *)(v16 + 5736);
          v42 = ntohs(*(_WORD *)(*(_QWORD *)(v16 + 1080) + 322LL));
          v43 = *((_QWORD *)this + 102);
          v44 = *((_QWORD *)this + 103);
          v45 = (const wchar_t *)*((_QWORD *)this + 13);
          if ( _wcsicmp(v45, L"PASS")
            || (v17 = _wcsicmp(*((const wchar_t **)this + 43), L"Anonymous") == 0, v18 = L"***", v17) )
          {
            v18 = (const wchar_t *)*((_QWORD *)this + 43);
          }
          v46 = v18;
          v47 = *((_QWORD *)this + 82);
          v48 = *((_QWORD *)this + 152);
          v49 = *((_DWORD *)this + 273);
          v50 = *((_DWORD *)this + 274);
          v51 = *((_DWORD *)this + 292);
          v52 = FileTime;
          v19 = (_QWORD *)*((_QWORD *)this + 132);
          v53 = v19[8] + v19[10];
          v54 = v19[9] + v19[11];
        }
        v20 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v20 + 8) && (*(_BYTE *)(v20 + 40) & 0x12) != 0 && *(_DWORD *)(v20 + 44) >= 4u )
        {
          v21 = (const unsigned __int16 *)*((_QWORD *)v9 + 7);
          v22 = (const struct _GUID *)*((_QWORD *)this + 132);
          v23 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::StartCallProvider::RaiseEvent(v23, v22 + 23, v21);
          v8 = (_DWORD *)((char *)this + 1176);
        }
        v24 = 0;
        v37 = 0;
        do
        {
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 1);
          v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, _DWORD *))v36->lpVtbl[1].QueryInterface)(
                  v36,
                  v39,
                  v8);
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 1);
          if ( v11 >= 0 )
            break;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_command.cxx",
              7677,
              "FTP_COMMAND::CallPostProcessProvider",
              v11,
              "Failed to call IFtpPostprocessProvider::HandlePostProcess.");
          v25 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v25 + 8) && (*(_BYTE *)(v25 + 40) & 0x12) != 0 && *(_DWORD *)(v25 + 44) >= 3u )
          {
            STRU::STRU(v56);
            GetLastComExceptionErrorInfo((struct STRU *)v56, v26);
            v27 = v57;
            v28 = (const struct _GUID *)*((_QWORD *)this + 132);
            v29 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            FtpExtensibilityEvents::FailCallProvider::RaiseEvent(v29, v28 + 23, v11, v27);
            STRU::~STRU(v56);
            v24 = v37;
            v8 = (_DWORD *)((char *)this + 1176);
          }
          if ( v11 != -2147417848 && v11 != -2147023170 && v11 != -2146234348 && v11 != -2147023174 )
            goto LABEL_46;
          ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
          v36 = 0;
          CUSTOM_PROVIDER_ENTRY::Invalidate(v9);
          if ( (int)CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(v9, &GUID_4522cbc6_16cd_49ad_8653_9a2c579e4280, &v36) < 0 )
            goto LABEL_46;
          v37 = ++v24;
        }
        while ( v24 < 2 );
        v30 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v30 + 8) && (*(_BYTE *)(v30 + 40) & 0x12) != 0 && *(_DWORD *)(v30 + 44) >= 4u )
        {
          v31 = (const struct _GUID *)*((_QWORD *)this + 132);
          v32 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::EndCallProvider::RaiseEvent(v32, v31 + 23);
        }
        if ( *v8 && (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_command.cxx",
            7744,
            "FTP_COMMAND::CallPostProcessProvider",
            "IFtpPostprocessProvider [%S] set [%d] not to continue process.\n",
            *((const wchar_t **)v9 + 7),
            *v8);
        ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
        v36 = 0;
      }
      else if ( ReferencedProvider != -2147467262 )
      {
        goto LABEL_46;
      }
      ++v7;
      v6 = *(_DWORD *)(v5 + 320);
      if ( v7 >= v6 )
        break;
    }
  }
  v11 = 0;
LABEL_46:
  if ( v5 )
  {
    v33 = _InterlockedDecrement((volatile signed __int32 *)v5);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v33);
    if ( !v33 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
    }
  }
  if ( v36 )
    ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180037910  push    rbp
0x180037912  push    rbx
0x180037913  push    rsi
0x180037914  push    rdi
0x180037915  push    r12
0x180037917  push    r13
0x180037919  push    r14
0x18003791b  push    r15
0x18003791d  lea     rbp, [rsp-58h]
0x180037922  sub     rsp, 158h
0x180037929  mov     rax, cs:__security_cookie
0x180037930  xor     rax, rsp
0x180037933  mov     [rbp+90h+var_48], rax
0x180037937  mov     r14, rcx
0x18003793a  mov     [rsp+190h+var_150], 0
0x180037943  xor     edx, edx; Val
0x180037945  mov     r8d, 98h; Size
0x18003794b  lea     rcx, [rsp+190h+var_130]; void *
0x180037950  call    memset_0
0x180037955  xorps   xmm0, xmm0
0x180037958  movups  xmmword ptr [rbp+90h+SystemTime.wYear], xmm0
0x18003795c  mov     qword ptr [rsp+190h+FileTime.dwLowDateTime], 0
0x180037965  mov     rax, [r14+420h]
0x18003796c  mov     r15, [rax+60h]
0x180037970  lea     rbx, [r15+0D0h]
0x180037977  mov     rcx, rbx
0x18003797a  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180037980  mov     r8, [r15+0C0h]
0x180037987  mov     edx, 1
0x18003798c  lock xadd [r8], edx
0x180037991  inc     edx
0x180037993  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003799a  test    rcx, rcx
0x18003799d  jz      short loc_1800379A5
0x18003799f  call    cs:__imp_WriteRefTraceLog
0x1800379a5  mov     r15, [r15+0C0h]
0x1800379ac  mov     rcx, rbx
0x1800379af  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800379b5  mov     eax, [r15+140h]
0x1800379bc  test    eax, eax
0x1800379be  jz      loc_180037E67
0x1800379c4  xor     r12d, r12d
0x1800379c7  lea     rdi, [r14+498h]
0x1800379ce  cmp     dword ptr [rdi], 0
0x1800379d1  jnz     loc_180037E67
0x1800379d7  cmp     r12d, eax
0x1800379da  ja      loc_180037F03
0x1800379e0  mov     eax, r12d
0x1800379e3  imul    r13, rax, 258h
0x1800379ea  add     r13, [r15+148h]
0x1800379f1  lea     r8, [rsp+190h+var_150]; struct IUnknown **
0x1800379f6  lea     rdx, _GUID_4522cbc6_16cd_49ad_8653_9a2c579e4280; struct _GUID *
0x1800379fd  mov     rcx, r13; this
0x180037a00  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180037a05  mov     esi, eax
0x180037a07  test    eax, eax
0x180037a09  jns     short loc_180037A1B
0x180037a0b  cmp     eax, 80004002h
0x180037a10  jnz     loc_180037E69
0x180037a16  jmp     loc_180037E54
0x180037a1b  cmp     [rsp+190h+var_130], 0
0x180037a21  jnz     loc_180037BBB
0x180037a27  mov     rax, [r14+420h]
0x180037a2e  movups  xmm0, xmmword ptr [rax+1244h]
0x180037a35  movdqu  xmmword ptr [rbp+90h+SystemTime.wYear], xmm0
0x180037a3a  lea     rdx, [rsp+190h+FileTime]; lpFileTime
0x180037a3f  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x180037a43  call    cs:__imp_SystemTimeToFileTime
0x180037a49  test    eax, eax
0x180037a4b  jz      loc_180037EE5
0x180037a51  mov     rcx, [r14+420h]
0x180037a58  mov     rax, [rcx]
0x180037a5b  mov     rax, [rax+40h]
0x180037a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a64  mov     [rsp+190h+var_130], rax
0x180037a69  mov     rdx, [r14+420h]
0x180037a70  mov     rax, [rdx+60h]
0x180037a74  lea     rcx, dword_18004D454
0x180037a7b  cmp     qword ptr [rax+8], 0
0x180037a80  cmovnz  rcx, [rax+8]
0x180037a85  mov     [rsp+190h+var_128], rcx
0x180037a8a  mov     rcx, [rdx+420h]
0x180037a91  mov     rax, [rcx]
0x180037a94  mov     rax, [rax+30h]
0x180037a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a9d  mov     [rsp+190h+var_120], rax
0x180037aa2  mov     rcx, [r14+420h]
0x180037aa9  mov     rax, [rcx+388h]
0x180037ab0  mov     [rsp+190h+var_118], rax
0x180037ab5  mov     rax, [rcx+16C0h]
0x180037abc  mov     [rbp+90h+var_110], rax
0x180037ac0  mov     rcx, [rcx+438h]
0x180037ac7  movzx   ecx, word ptr [rcx+1C2h]; netshort
0x180037ace  call    cs:__imp_ntohs
0x180037ad4  movzx   eax, ax
0x180037ad7  mov     [rbp+90h+var_108], eax
0x180037ada  mov     rcx, [r14+420h]
0x180037ae1  mov     rax, [rcx+1668h]
0x180037ae8  mov     [rbp+90h+var_100], rax
0x180037aec  mov     rcx, [rcx+438h]
0x180037af3  movzx   ecx, word ptr [rcx+142h]; netshort
0x180037afa  call    cs:__imp_ntohs
0x180037b00  movzx   eax, ax
0x180037b03  mov     [rbp+90h+var_F8], eax
0x180037b06  mov     rax, [r14+330h]
0x180037b0d  mov     [rbp+90h+var_F0], rax
0x180037b11  mov     rax, [r14+338h]
0x180037b18  mov     [rbp+90h+var_E8], rax
0x180037b1c  mov     rcx, [r14+68h]; String1
0x180037b20  mov     [rbp+90h+var_E0], rcx
0x180037b24  lea     rdx, aPass_0; "PASS"
0x180037b2b  call    cs:__imp__wcsicmp
0x180037b31  test    eax, eax
0x180037b33  jnz     short loc_180037B54
0x180037b35  lea     rdx, aAnonymous; "Anonymous"
0x180037b3c  mov     rcx, [r14+158h]; String1
0x180037b43  call    cs:__imp__wcsicmp
0x180037b49  test    eax, eax
0x180037b4b  lea     rax, asc_180053EC8; "***"
0x180037b52  jnz     short loc_180037B5B
0x180037b54  mov     rax, [r14+158h]
0x180037b5b  mov     [rbp+90h+var_D8], rax
0x180037b5f  mov     rax, [r14+290h]
0x180037b66  mov     [rbp+90h+var_D0], rax
0x180037b6a  mov     rax, [r14+4C0h]
0x180037b71  mov     [rbp+90h+var_C8], rax
0x180037b75  mov     eax, [r14+444h]
0x180037b7c  mov     [rbp+90h+var_C0], eax
0x180037b7f  mov     eax, [r14+448h]
0x180037b86  mov     [rbp+90h+var_BC], eax
0x180037b89  mov     eax, [r14+490h]
0x180037b90  mov     [rbp+90h+var_B8], eax
0x180037b93  mov     rax, qword ptr [rsp+190h+FileTime.dwLowDateTime]
0x180037b98  mov     [rbp+90h+var_B4], rax
0x180037b9c  mov     rcx, [r14+420h]
0x180037ba3  mov     rax, [rcx+50h]
0x180037ba7  add     rax, [rcx+40h]
0x180037bab  mov     [rbp+90h+var_A8], rax
0x180037baf  mov     rax, [rcx+58h]
0x180037bb3  add     rax, [rcx+48h]
0x180037bb7  mov     [rbp+90h+var_A0], rax
0x180037bbb  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037bc2  mov     rax, [rcx]
0x180037bc5  mov     rax, [rax+20h]
0x180037bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bce  cmp     dword ptr [rax+8], 0
0x180037bd2  jz      short loc_180037C17
0x180037bd4  test    byte ptr [rax+28h], 12h
0x180037bd8  jz      short loc_180037C17
0x180037bda  cmp     dword ptr [rax+2Ch], 4
0x180037bde  jb      short loc_180037C17
0x180037be0  mov     rdi, [r13+38h]
0x180037be4  mov     rbx, [r14+420h]
0x180037beb  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037bf2  mov     rax, [rcx]
0x180037bf5  mov     rax, [rax+20h]
0x180037bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bfe  mov     r8, rdi; unsigned __int16 *
0x180037c01  lea     rdx, [rbx+170h]; struct _GUID *
0x180037c08  mov     rcx, rax; struct CEtwTracer *
0x180037c0b  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x180037c10  lea     rdi, [r14+498h]
0x180037c17  xor     ebx, ebx
0x180037c19  mov     [rsp+190h+var_148], ebx
0x180037c1d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037c24  mov     rax, [rcx]
0x180037c27  mov     edx, 1
0x180037c2c  mov     rax, [rax+0B0h]
0x180037c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c38  mov     rcx, [rsp+190h+var_150]
0x180037c3d  mov     rax, [rcx]
0x180037c40  mov     r8, rdi
0x180037c43  lea     rdx, [rsp+190h+var_130]
0x180037c48  mov     rax, [rax+18h]
0x180037c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c51  mov     esi, eax
0x180037c53  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037c5a  mov     rax, [rcx]
0x180037c5d  mov     edx, 1
0x180037c62  mov     rax, [rax+0B8h]
0x180037c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c6e  test    esi, esi
0x180037c70  jns     loc_180037DA3
0x180037c76  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180037c7d  jz      short loc_180037CB0
0x180037c7f  lea     rax, aFailedToCallIf_2; "Failed to call IFtpPostprocessProvider:"...
0x180037c86  mov     [rsp+190h+var_168], rax
0x180037c8b  mov     dword ptr [rsp+190h+var_170], esi
0x180037c8f  lea     r9, aFtpCommandCall; "FTP_COMMAND::CallPostProcessProvider"
0x180037c96  mov     r8d, 1DFDh
0x180037c9c  lea     rdx, aInetsrvIisIisr_8; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180037ca3  mov     rcx, cs:g_pDebug
0x180037caa  call    cs:__imp_PuDbgPrintError
0x180037cb0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037cb7  mov     rax, [rcx]
0x180037cba  mov     rax, [rax+20h]
0x180037cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cc3  cmp     dword ptr [rax+8], 0
0x180037cc7  jz      short loc_180037D32
0x180037cc9  test    byte ptr [rax+28h], 12h
0x180037ccd  jz      short loc_180037D32
0x180037ccf  cmp     dword ptr [rax+2Ch], 3
0x180037cd3  jb      short loc_180037D32
0x180037cd5  lea     rcx, [rbp+90h+var_80]
0x180037cd9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180037cdf  nop
0x180037ce0  lea     rcx, [rbp+90h+var_80]; struct STRU *
0x180037ce4  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x180037ce9  mov     rbx, [rbp+90h+var_60]
0x180037ced  mov     rdi, [r14+420h]
0x180037cf4  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037cfb  mov     rax, [rcx]
0x180037cfe  mov     rax, [rax+20h]
0x180037d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d07  mov     r9, rbx; unsigned __int16 *
0x180037d0a  mov     r8d, esi; unsigned int
0x180037d0d  lea     rdx, [rdi+170h]; struct _GUID *
0x180037d14  mov     rcx, rax; struct CEtwTracer *
0x180037d17  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x180037d1c  nop
0x180037d1d  lea     rcx, [rbp+90h+var_80]
0x180037d21  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180037d27  mov     ebx, [rsp+190h+var_148]
0x180037d2b  lea     rdi, [r14+498h]
0x180037d32  cmp     esi, 80010108h
0x180037d38  jz      short loc_180037D56
0x180037d3a  cmp     esi, 800706BEh
0x180037d40  jz      short loc_180037D56
0x180037d42  cmp     esi, 80131014h
0x180037d48  jz      short loc_180037D56
0x180037d4a  cmp     esi, 800706BAh
0x180037d50  jnz     loc_180037E69
0x180037d56  mov     rcx, [rsp+190h+var_150]
0x180037d5b  mov     rax, [rcx]
0x180037d5e  mov     rax, [rax+10h]
0x180037d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d67  mov     [rsp+190h+var_150], 0
0x180037d70  mov     rcx, r13; this
0x180037d73  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x180037d78  lea     r8, [rsp+190h+var_150]; struct IUnknown **
0x180037d7d  lea     rdx, _GUID_4522cbc6_16cd_49ad_8653_9a2c579e4280; struct _GUID *
0x180037d84  mov     rcx, r13; this
0x180037d87  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180037d8c  test    eax, eax
0x180037d8e  js      loc_180037E69
0x180037d94  inc     ebx
0x180037d96  mov     [rsp+190h+var_148], ebx
0x180037d9a  cmp     ebx, 2
0x180037d9d  jb      loc_180037C1D
0x180037da3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037daa  mov     rax, [rcx]
0x180037dad  mov     rax, [rax+20h]
0x180037db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037db6  cmp     dword ptr [rax+8], 0
0x180037dba  jz      short loc_180037DF1
0x180037dbc  test    byte ptr [rax+28h], 12h
0x180037dc0  jz      short loc_180037DF1
0x180037dc2  cmp     dword ptr [rax+2Ch], 4
0x180037dc6  jb      short loc_180037DF1
0x180037dc8  mov     rbx, [r14+420h]
0x180037dcf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180037dd6  mov     rax, [rcx]
0x180037dd9  mov     rax, [rax+20h]
0x180037ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037de2  lea     rdx, [rbx+170h]; struct _GUID *
0x180037de9  mov     rcx, rax; struct CEtwTracer *
0x180037dec  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x180037df1  mov     eax, [rdi]
0x180037df3  test    eax, eax
0x180037df5  jz      short loc_180037E3A
0x180037df7  test    byte ptr cs:g_dwDebugFlags, 3
0x180037dfe  jz      short loc_180037E3A
0x180037e00  mov     [rsp+190h+var_160], eax
0x180037e04  mov     rax, [r13+38h]
0x180037e08  mov     [rsp+190h+var_168], rax
0x180037e0d  lea     rax, aIftppostproces; "IFtpPostprocessProvider [%S] set [%d] n"...
0x180037e14  mov     [rsp+190h+var_170], rax
0x180037e19  lea     r9, aFtpCommandCall; "FTP_COMMAND::CallPostProcessProvider"
0x180037e20  mov     r8d, 1E40h
0x180037e26  lea     rdx, aInetsrvIisIisr_8; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180037e2d  mov     rcx, cs:g_pDebug
0x180037e34  call    cs:__imp_PuDbgPrint
0x180037e3a  mov     rcx, [rsp+190h+var_150]
0x180037e3f  mov     rax, [rcx]
0x180037e42  mov     rax, [rax+10h]
0x180037e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e4b  mov     [rsp+190h+var_150], 0
0x180037e54  inc     r12d
0x180037e57  mov     eax, [r15+140h]
0x180037e5e  cmp     r12d, eax
0x180037e61  jb      loc_1800379CE
0x180037e67  xor     esi, esi
0x180037e69  test    r15, r15
0x180037e6c  jz      short loc_180037EAD
0x180037e6e  or      ebx, 0FFFFFFFFh
0x180037e71  lock xadd [r15], ebx
0x180037e76  dec     ebx
0x180037e78  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180037e7f  test    rcx, rcx
0x180037e82  jz      short loc_180037E8F
  ... truncated ...
```
