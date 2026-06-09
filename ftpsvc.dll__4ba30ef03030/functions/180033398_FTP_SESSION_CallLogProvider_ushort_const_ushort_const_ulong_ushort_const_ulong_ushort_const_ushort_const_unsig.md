# FTP_SESSION::CallLogProvider(ushort const *,ushort const *,ulong,ushort const *,ulong,ushort const *,ushort const *,unsigned __int64,unsigned __int64,ushort const *,ushort const *,ushort const *,ulong,ulong,long,ulong,ushort const *)

- ea: `0x180033398`
- end: `0x18003386f`
- name: `?CallLogProvider@FTP_SESSION@@QEAAJPEBG0K0K00_K1000KKJK0@Z`
- size: `1239`
- prototype: `__int64 __fastcall(FTP_SESSION *this, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned __int64, wchar_t *String1, wchar_t *, const unsigned __int16 *, unsigned int, unsigned int, int, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034794`
- `0x180034cb4`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x180019b48`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d544`
- `0x18002c12c`
- `0x180033398`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180033596`
- `msvcrt!_wcsicmp` at `0x1800335aa`
- `msvcrt!_wcsicmp` at `0x180033596`
- `msvcrt!_wcsicmp` at `0x1800335aa`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003344c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003344c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180033826`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180033826`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033481`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033481`
- `iisutil!WriteRefTraceLog` at `0x180033471`
- `iisutil!WriteRefTraceLog` at `0x180033804`
- `iisutil!WriteRefTraceLog` at `0x180033471`
- `iisutil!WriteRefTraceLog` at `0x180033804`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800336b6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800336b6`
- `iisutil!PuDbgPrintError` at `0x180033687`
- `iisutil!PuDbgPrintError` at `0x180033687`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800336f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800336f7`

## string_xrefs

- `0x180033679`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_session.cxx`

## pseudocode

```c
__int64 __fastcall FTP_SESSION::CallLogProvider(
        FTP_SESSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        unsigned __int64 a9,
        unsigned __int64 a10,
        wchar_t *String1,
        wchar_t *a12,
        const unsigned __int16 *a13,
        unsigned int a14,
        unsigned int a15,
        int a16,
        unsigned int a17,
        const unsigned __int16 *a18)
{
  const wchar_t *v19; // r14
  const wchar_t *v20; // rsi
  __int64 v21; // rdi
  CReaderWriterLock3 *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rdi
  unsigned int v25; // r12d
  CUSTOM_PROVIDER_ENTRY *v26; // r15
  __int64 v27; // rax
  const unsigned __int16 *v28; // rbx
  struct CEtwTracer *v29; // rax
  __int64 v30; // rax
  int *v31; // rcx
  unsigned int i; // r14d
  signed int v33; // esi
  __int64 v34; // rax
  int v35; // edx
  unsigned __int16 *v36; // rbx
  struct CEtwTracer *v37; // rax
  __int64 v38; // rax
  struct CEtwTracer *v39; // rax
  unsigned __int32 v40; // ebx
  struct IUnknown *v42; // [rsp+30h] [rbp-D0h] BYREF
  int v43; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v44; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v45; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v46; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v47; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v48; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v49; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v50; // [rsp+70h] [rbp-90h]
  wchar_t *v51; // [rsp+78h] [rbp-88h]
  wchar_t *v52; // [rsp+80h] [rbp-80h]
  _QWORD v53[5]; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v55; // [rsp+C0h] [rbp-40h]
  unsigned int v56; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v57; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v58; // [rsp+D8h] [rbp-28h]
  const wchar_t *v59; // [rsp+E0h] [rbp-20h]
  const wchar_t *v60; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v61; // [rsp+F0h] [rbp-10h]
  unsigned int v62; // [rsp+F8h] [rbp-8h]
  unsigned int v63; // [rsp+FCh] [rbp-4h]
  unsigned int v64; // [rsp+100h] [rbp+0h]
  int v65; // [rsp+104h] [rbp+4h]
  const unsigned __int16 *v66; // [rsp+108h] [rbp+8h]
  _BYTE v67[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v68; // [rsp+130h] [rbp+30h]

  v43 = a4;
  v47 = a3;
  v44 = a2;
  v48 = a5;
  v45 = a7;
  v46 = a8;
  v19 = String1;
  v52 = String1;
  v20 = a12;
  v51 = a12;
  v49 = a13;
  v50 = a18;
  v42 = 0;
  memset_0(v53, 0, 0x80u);
  v21 = *((_QWORD *)this + 12);
  v22 = (CReaderWriterLock3 *)(v21 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v21 + 208));
  v23 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v21 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v23);
  v24 = *(_QWORD *)(v21 + 192);
  CReaderWriterLock3::ReadUnlock(v22);
  if ( *(_DWORD *)(v24 + 320) )
  {
    v25 = 0;
    do
    {
      v26 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v24 + 328) + 600LL * v25);
      if ( (int)CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(v26, &GUID_a18a94cc_8299_4408_816c_7c3baca1a40e, &v42) >= 0 )
      {
        v27 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v27 + 8) && (*(_BYTE *)(v27 + 40) & 0x12) != 0 && *(_DWORD *)(v27 + 44) >= 4u )
        {
          v28 = (const unsigned __int16 *)*((_QWORD *)v26 + 7);
          v29 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::StartCallProvider::RaiseEvent(v29, (const struct _GUID *)this + 23, v28);
        }
        v53[0] = v44;
        v30 = *((_QWORD *)this + 12);
        v31 = &dword_18004D454;
        if ( *(_QWORD *)(v30 + 8) )
          v31 = *(int **)(v30 + 8);
        v53[1] = v31;
        v53[2] = v45;
        v53[3] = v46;
        v53[4] = v47;
        v54 = v43;
        v55 = v48;
        v56 = a6;
        v57 = a9;
        v58 = a10;
        v59 = v19;
        if ( _wcsicmp(v19, L"PASS") || !_wcsicmp(v20, L"Anonymous") )
          v60 = v20;
        else
          v60 = L"***";
        v61 = v49;
        v63 = a14;
        v62 = a15;
        v65 = a16;
        v64 = a17;
        v66 = v50;
        for ( i = 0; i < 2; ++i )
        {
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 1);
          v33 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *))v42->lpVtbl[1].QueryInterface)(v42, v53);
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 1);
          if ( v33 >= 0 )
            break;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_session.cxx",
              3279,
              "FTP_SESSION::CallLogProvider",
              v33,
              "Failed to call IFtpLogProvider::Log.");
          v34 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v34 + 8) && (*(_BYTE *)(v34 + 40) & 0x12) != 0 && *(_DWORD *)(v34 + 44) >= 3u )
          {
            STRU::STRU(v67);
            GetLastComExceptionErrorInfo((struct STRU *)v67, v35);
            v36 = v68;
            v37 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            FtpExtensibilityEvents::FailCallProvider::RaiseEvent(v37, (const struct _GUID *)this + 23, v33, v36);
            STRU::~STRU(v67);
          }
          if ( v33 != -2147417848 && v33 != -2147023170 && v33 != -2146234348 && v33 != -2147023174 )
            goto LABEL_37;
          ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
          v42 = 0;
          CUSTOM_PROVIDER_ENTRY::Invalidate(v26);
          if ( (int)CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(v26, &GUID_a18a94cc_8299_4408_816c_7c3baca1a40e, &v42) < 0 )
            goto LABEL_37;
        }
        v38 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        if ( *(_DWORD *)(v38 + 8) && (*(_BYTE *)(v38 + 40) & 0x12) != 0 && *(_DWORD *)(v38 + 44) >= 4u )
        {
          v39 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          FtpExtensibilityEvents::EndCallProvider::RaiseEvent(v39, (const struct _GUID *)this + 23);
        }
        ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
        v42 = 0;
        v20 = v51;
        v19 = v52;
      }
      ++v25;
    }
    while ( v25 < *(_DWORD *)(v24 + 320) );
  }
  v33 = 0;
LABEL_37:
  v40 = _InterlockedDecrement((volatile signed __int32 *)v24);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v40);
  if ( !v40 && v24 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v24);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v24);
  }
  if ( v42 )
    ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x180033398  push    rbp
0x18003339a  push    rbx
0x18003339b  push    rsi
0x18003339c  push    rdi
0x18003339d  push    r12
0x18003339f  push    r13
0x1800333a1  push    r14
0x1800333a3  push    r15
0x1800333a5  lea     rbp, [rsp-58h]
0x1800333aa  sub     rsp, 158h
0x1800333b1  mov     rax, cs:__security_cookie
0x1800333b8  xor     rax, rsp
0x1800333bb  mov     [rbp+90h+var_48], rax
0x1800333bf  mov     [rsp+190h+var_158], r9d
0x1800333c4  mov     [rsp+190h+var_138], r8
0x1800333c9  mov     [rsp+190h+var_150], rdx
0x1800333ce  mov     r13, rcx
0x1800333d1  mov     rax, [rbp+90h+arg_20]
0x1800333d8  mov     [rsp+190h+var_130], rax
0x1800333dd  mov     rax, [rbp+90h+arg_30]
0x1800333e4  mov     [rsp+190h+var_148], rax
0x1800333e9  mov     rax, [rbp+90h+arg_38]
0x1800333f0  mov     [rsp+190h+var_140], rax
0x1800333f5  mov     r14, [rbp+90h+String1]
0x1800333fc  mov     [rbp+90h+var_110], r14
0x180033400  mov     rsi, [rbp+90h+arg_58]
0x180033407  mov     [rsp+190h+var_118], rsi
0x18003340c  mov     rax, [rbp+90h+arg_60]
0x180033413  mov     [rsp+190h+var_128], rax
0x180033418  mov     rax, [rbp+90h+arg_88]
0x18003341f  mov     [rsp+190h+var_120], rax
0x180033424  mov     [rsp+190h+var_160], 0
0x18003342d  xor     edx, edx; Val
0x18003342f  mov     r8d, 80h; Size
0x180033435  lea     rcx, [rbp+90h+var_100]; void *
0x180033439  call    memset_0
0x18003343e  mov     rdi, [r13+60h]
0x180033442  lea     rbx, [rdi+0D0h]
0x180033449  mov     rcx, rbx
0x18003344c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180033452  mov     r8, [rdi+0C0h]
0x180033459  mov     edx, 1
0x18003345e  lock xadd [r8], edx
0x180033463  inc     edx
0x180033465  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003346c  test    rcx, rcx
0x18003346f  jz      short loc_180033477
0x180033471  call    cs:__imp_WriteRefTraceLog
0x180033477  mov     rdi, [rdi+0C0h]
0x18003347e  mov     rcx, rbx
0x180033481  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180033487  mov     eax, [rdi+140h]
0x18003348d  test    eax, eax
0x18003348f  jz      loc_1800337E8
0x180033495  xor     r12d, r12d
0x180033498  cmp     r12d, eax
0x18003349b  ja      loc_180033865
0x1800334a1  mov     eax, r12d
0x1800334a4  imul    r15, rax, 258h
0x1800334ab  add     r15, [rdi+148h]
0x1800334b2  lea     r8, [rsp+190h+var_160]; struct IUnknown **
0x1800334b7  lea     rdx, _GUID_a18a94cc_8299_4408_816c_7c3baca1a40e; struct _GUID *
0x1800334be  mov     rcx, r15; this
0x1800334c1  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x1800334c6  test    eax, eax
0x1800334c8  js      loc_1800337D6
0x1800334ce  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800334d5  mov     rax, [rcx]
0x1800334d8  mov     rax, [rax+20h]
0x1800334dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334e1  cmp     dword ptr [rax+8], 0
0x1800334e5  jz      short loc_18003351C
0x1800334e7  test    byte ptr [rax+28h], 12h
0x1800334eb  jz      short loc_18003351C
0x1800334ed  cmp     dword ptr [rax+2Ch], 4
0x1800334f1  jb      short loc_18003351C
0x1800334f3  mov     rbx, [r15+38h]
0x1800334f7  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800334fe  mov     rax, [rcx]
0x180033501  mov     rax, [rax+20h]
0x180033505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003350a  lea     rdx, [r13+170h]; struct _GUID *
0x180033511  mov     r8, rbx; unsigned __int16 *
0x180033514  mov     rcx, rax; struct CEtwTracer *
0x180033517  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18003351c  mov     rax, [rsp+190h+var_150]
0x180033521  mov     [rbp+90h+var_100], rax
0x180033525  mov     rax, [r13+60h]
0x180033529  lea     rcx, dword_18004D454
0x180033530  cmp     qword ptr [rax+8], 0
0x180033535  cmovnz  rcx, [rax+8]
0x18003353a  mov     [rbp+90h+var_F8], rcx
0x18003353e  mov     rax, [rsp+190h+var_148]
0x180033543  mov     [rbp+90h+var_F0], rax
0x180033547  mov     rax, [rsp+190h+var_140]
0x18003354c  mov     [rbp+90h+var_E8], rax
0x180033550  mov     rax, [rsp+190h+var_138]
0x180033555  mov     [rbp+90h+var_E0], rax
0x180033559  mov     eax, [rsp+190h+var_158]
0x18003355d  mov     [rbp+90h+var_D8], eax
0x180033560  mov     rax, [rsp+190h+var_130]
0x180033565  mov     [rbp+90h+var_D0], rax
0x180033569  mov     eax, [rbp+90h+arg_28]
0x18003356f  mov     [rbp+90h+var_C8], eax
0x180033572  mov     rax, [rbp+90h+arg_40]
0x180033579  mov     [rbp+90h+var_C0], rax
0x18003357d  mov     rax, [rbp+90h+arg_48]
0x180033584  mov     [rbp+90h+var_B8], rax
0x180033588  mov     [rbp+90h+var_B0], r14
0x18003358c  lea     rdx, aPass_0; "PASS"
0x180033593  mov     rcx, r14; String1
0x180033596  call    cs:__imp__wcsicmp
0x18003359c  test    eax, eax
0x18003359e  jnz     short loc_1800335C1
0x1800335a0  lea     rdx, aAnonymous; "Anonymous"
0x1800335a7  mov     rcx, rsi; String1
0x1800335aa  call    cs:__imp__wcsicmp
0x1800335b0  test    eax, eax
0x1800335b2  jz      short loc_1800335C1
0x1800335b4  lea     rax, asc_180053EC8; "***"
0x1800335bb  mov     [rbp+90h+var_A8], rax
0x1800335bf  jmp     short loc_1800335C5
0x1800335c1  mov     [rbp+90h+var_A8], rsi
0x1800335c5  mov     rax, [rsp+190h+var_128]
0x1800335ca  mov     [rbp+90h+var_A0], rax
0x1800335ce  mov     eax, [rbp+90h+arg_68]
0x1800335d4  mov     [rbp+90h+var_94], eax
0x1800335d7  mov     eax, [rbp+90h+arg_70]
0x1800335dd  mov     [rbp+90h+var_98], eax
0x1800335e0  mov     eax, [rbp+90h+arg_78]
0x1800335e6  mov     [rbp+90h+var_8C], eax
0x1800335e9  mov     eax, [rbp+90h+arg_80]
0x1800335ef  mov     [rbp+90h+var_90], eax
0x1800335f2  mov     rax, [rsp+190h+var_120]
0x1800335f7  mov     [rbp+90h+var_88], rax
0x1800335fb  xor     r14d, r14d
0x1800335fe  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180033605  mov     rax, [rcx]
0x180033608  mov     edx, 1
0x18003360d  mov     rax, [rax+0B0h]
0x180033614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033619  mov     rcx, [rsp+190h+var_160]
0x18003361e  mov     rax, [rcx]
0x180033621  lea     rdx, [rbp+90h+var_100]
0x180033625  mov     rax, [rax+18h]
0x180033629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003362e  mov     esi, eax
0x180033630  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180033637  mov     rdx, [rcx]
0x18003363a  mov     rax, [rdx+0B8h]
0x180033641  mov     edx, 1
0x180033646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003364b  test    esi, esi
0x18003364d  jns     loc_18003376C
0x180033653  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003365a  jz      short loc_18003368D
0x18003365c  lea     rax, aFailedToCallIf_0; "Failed to call IFtpLogProvider::Log."
0x180033663  mov     [rsp+190h+var_168], rax
0x180033668  mov     [rsp+190h+var_170], esi
0x18003366c  lea     r9, aFtpSessionCall; "FTP_SESSION::CallLogProvider"
0x180033673  mov     r8d, 0CCFh
0x180033679  lea     rdx, aInetsrvIisIisr_30; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180033680  mov     rcx, cs:g_pDebug
0x180033687  call    cs:__imp_PuDbgPrintError
0x18003368d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180033694  mov     rax, [rcx]
0x180033697  mov     rax, [rax+20h]
0x18003369b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336a0  cmp     dword ptr [rax+8], 0
0x1800336a4  jz      short loc_1800336FD
0x1800336a6  test    byte ptr [rax+28h], 12h
0x1800336aa  jz      short loc_1800336FD
0x1800336ac  cmp     dword ptr [rax+2Ch], 3
0x1800336b0  jb      short loc_1800336FD
0x1800336b2  lea     rcx, [rbp+90h+var_80]
0x1800336b6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800336bc  nop
0x1800336bd  lea     rcx, [rbp+90h+var_80]; struct STRU *
0x1800336c1  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x1800336c6  mov     rbx, [rbp+90h+var_60]
0x1800336ca  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800336d1  mov     rax, [rcx]
0x1800336d4  mov     rax, [rax+20h]
0x1800336d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336dd  lea     rdx, [r13+170h]; struct _GUID *
0x1800336e4  mov     r9, rbx; unsigned __int16 *
0x1800336e7  mov     r8d, esi; unsigned int
0x1800336ea  mov     rcx, rax; struct CEtwTracer *
0x1800336ed  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x1800336f2  nop
0x1800336f3  lea     rcx, [rbp+90h+var_80]
0x1800336f7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800336fd  cmp     esi, 80010108h
0x180033703  jz      short loc_180033721
0x180033705  cmp     esi, 800706BEh
0x18003370b  jz      short loc_180033721
0x18003370d  cmp     esi, 80131014h
0x180033713  jz      short loc_180033721
0x180033715  cmp     esi, 800706BAh
0x18003371b  jnz     loc_1800337EA
0x180033721  mov     rcx, [rsp+190h+var_160]
0x180033726  mov     rax, [rcx]
0x180033729  mov     rax, [rax+10h]
0x18003372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033732  mov     [rsp+190h+var_160], 0
0x18003373b  mov     rcx, r15; this
0x18003373e  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x180033743  lea     r8, [rsp+190h+var_160]; struct IUnknown **
0x180033748  lea     rdx, _GUID_a18a94cc_8299_4408_816c_7c3baca1a40e; struct _GUID *
0x18003374f  mov     rcx, r15; this
0x180033752  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180033757  test    eax, eax
0x180033759  js      loc_1800337EA
0x18003375f  inc     r14d
0x180033762  cmp     r14d, 2
0x180033766  jb      loc_1800335FE
0x18003376c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180033773  mov     rax, [rcx]
0x180033776  mov     rax, [rax+20h]
0x18003377a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003377f  cmp     dword ptr [rax+8], 0
0x180033783  jz      short loc_1800337B3
0x180033785  test    byte ptr [rax+28h], 12h
0x180033789  jz      short loc_1800337B3
0x18003378b  cmp     dword ptr [rax+2Ch], 4
0x18003378f  jb      short loc_1800337B3
0x180033791  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180033798  mov     rax, [rcx]
0x18003379b  mov     rax, [rax+20h]
0x18003379f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a4  lea     rdx, [r13+170h]; struct _GUID *
0x1800337ab  mov     rcx, rax; struct CEtwTracer *
0x1800337ae  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x1800337b3  mov     rcx, [rsp+190h+var_160]
0x1800337b8  mov     rax, [rcx]
0x1800337bb  mov     rax, [rax+10h]
0x1800337bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337c4  mov     [rsp+190h+var_160], 0
0x1800337cd  mov     rsi, [rsp+190h+var_118]
0x1800337d2  mov     r14, [rbp+90h+var_110]
0x1800337d6  inc     r12d
0x1800337d9  mov     eax, [rdi+140h]
0x1800337df  cmp     r12d, eax
0x1800337e2  jb      loc_1800334A1
0x1800337e8  xor     esi, esi
0x1800337ea  or      ebx, 0FFFFFFFFh
0x1800337ed  lock xadd [rdi], ebx
0x1800337f1  dec     ebx
0x1800337f3  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800337fa  test    rcx, rcx
0x1800337fd  jz      short loc_18003380A
0x1800337ff  mov     r8, rdi
0x180033802  mov     edx, ebx
0x180033804  call    cs:__imp_WriteRefTraceLog
0x18003380a  test    ebx, ebx
0x18003380c  jnz     short loc_18003382D
0x18003380e  test    rdi, rdi
0x180033811  jz      short loc_18003382D
0x180033813  mov     rcx, rdi; this
0x180033816  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003381b  nop
0x18003381c  mov     rdx, rdi
0x18003381f  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180033826  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003382c  nop
0x18003382d  mov     rcx, [rsp+190h+var_160]
0x180033832  test    rcx, rcx
0x180033835  jz      short loc_180033843
0x180033837  mov     rax, [rcx]
0x18003383a  mov     rax, [rax+10h]
0x18003383e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033843  mov     eax, esi
0x180033845  mov     rcx, [rbp+90h+var_48]
0x180033849  xor     rcx, rsp; StackCookie
0x18003384c  call    __security_check_cookie
0x180033851  add     rsp, 158h
0x180033858  pop     r15
0x18003385a  pop     r14
0x18003385c  pop     r13
0x18003385e  pop     r12
0x180033860  pop     rdi
0x180033861  pop     rsi
0x180033862  pop     rbx
0x180033863  pop     rbp
0x180033864  retn
0x180033865  mov     esi, 80070057h
0x18003386a  jmp     loc_1800337EA
```
