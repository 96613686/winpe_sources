# FTP_COMMAND::CallPreProcessProvider(void)

- ea: `0x180037f14`
- end: `0x1800384c5`
- name: `?CallPreProcessProvider@FTP_COMMAND@@QEAAJXZ`
- size: `1457`
- prototype: `__int64 __fastcall(FTP_COMMAND *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dbac`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x180019b48`
- `0x18001d310`
- `0x18001d39c`
- `0x18001d544`
- `0x18002c12c`
- `0x180037f14`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180038117`
- `msvcrt!_wcsicmp` at `0x18003812f`
- `msvcrt!_wcsicmp` at `0x180038117`
- `msvcrt!_wcsicmp` at `0x18003812f`
- `KERNEL32!SystemTimeToFileTime` at `0x180038045`
- `KERNEL32!SystemTimeToFileTime` at `0x180038045`
- `KERNEL32!GetLastError` at `0x18003849d`
- `KERNEL32!GetLastError` at `0x18003849d`
- `WS2_32!__imp_ntohs` at `0x1800380d0`
- `WS2_32!__imp_ntohs` at `0x1800380fc`
- `WS2_32!__imp_ntohs` at `0x1800380d0`
- `WS2_32!__imp_ntohs` at `0x1800380fc`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180037f7c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180037f7c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003845e`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003845e`
- `iisutil!PuDbgPrint` at `0x1800383ec`
- `iisutil!PuDbgPrint` at `0x1800383ec`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180037fb1`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180037fb1`
- `iisutil!WriteRefTraceLog` at `0x180037fa1`
- `iisutil!WriteRefTraceLog` at `0x180038441`
- `iisutil!WriteRefTraceLog` at `0x180037fa1`
- `iisutil!WriteRefTraceLog` at `0x180038441`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180038291`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180038291`
- `iisutil!PuDbgPrintError` at `0x180038262`
- `iisutil!PuDbgPrintError` at `0x180038262`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800382d9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800382d9`

## string_xrefs

- `0x180038254`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_command.cxx`
- `0x1800383de`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_command.cxx`
- `0x180038247`: `FTP_COMMAND::CallPreProcessProvider`
- `0x1800383d1`: `FTP_COMMAND::CallPreProcessProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_COMMAND::CallPreProcessProvider(FTP_COMMAND *this)
{
  __int64 v2; // r14
  CReaderWriterLock3 *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r14
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
  const wchar_t *v43; // [rsp+A0h] [rbp-60h]
  const wchar_t *v44; // [rsp+A8h] [rbp-58h]
  struct _FILETIME v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v49[32]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v50; // [rsp+100h] [rbp+0h]

  v36 = 0;
  memset_0(v39, 0, 0x68u);
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
                             &GUID_a3c19b60_5a28_471a_8f93_ab30411cee82,
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
          v43 = (const wchar_t *)*((_QWORD *)this + 13);
          if ( _wcsicmp(v43, L"PASS")
            || (v17 = _wcsicmp(*((const wchar_t **)this + 43), L"Anonymous") == 0, v18 = L"***", v17) )
          {
            v18 = (const wchar_t *)*((_QWORD *)this + 43);
          }
          v44 = v18;
          v45 = FileTime;
          v19 = (_QWORD *)*((_QWORD *)this + 132);
          v46 = v19[8] + v19[10];
          v47 = v19[9] + v19[11];
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
              7454,
              "FTP_COMMAND::CallPreProcessProvider",
              v11,
              "Failed to call IFtpPreprocessProvider::HandlePreProcess.");
          v25 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v25 + 8) && (*(_BYTE *)(v25 + 40) & 0x12) != 0 && *(_DWORD *)(v25 + 44) >= 3u )
          {
            STRU::STRU(v49);
            GetLastComExceptionErrorInfo((struct STRU *)v49, v26);
            v27 = v50;
            v28 = (const struct _GUID *)*((_QWORD *)this + 132);
            v29 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            FtpExtensibilityEvents::FailCallProvider::RaiseEvent(v29, v28 + 23, v11, v27);
            STRU::~STRU(v49);
            v24 = v37;
            v8 = (_DWORD *)((char *)this + 1176);
          }
          if ( v11 != -2147417848 && v11 != -2147023170 && v11 != -2146234348 && v11 != -2147023174 )
            goto LABEL_46;
          ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
          v36 = 0;
          CUSTOM_PROVIDER_ENTRY::Invalidate(v9);
          if ( (int)CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(v9, &GUID_a3c19b60_5a28_471a_8f93_ab30411cee82, &v36) < 0 )
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
            7521,
            "FTP_COMMAND::CallPreProcessProvider",
            "IFtpPreprocessProvider [%S] set [%d] not to continue process.\n",
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
0x180037f14  push    rbp
0x180037f16  push    rbx
0x180037f17  push    rsi
0x180037f18  push    rdi
0x180037f19  push    r12
0x180037f1b  push    r13
0x180037f1d  push    r14
0x180037f1f  push    r15
0x180037f21  lea     rbp, [rsp-28h]
0x180037f26  sub     rsp, 128h
0x180037f2d  mov     rax, cs:__security_cookie
0x180037f34  xor     rax, rsp
0x180037f37  mov     [rbp+60h+var_48], rax
0x180037f3b  mov     r15, rcx
0x180037f3e  mov     [rsp+160h+var_120], 0
0x180037f47  xor     edx, edx; Val
0x180037f49  lea     r8d, [rdx+68h]; Size
0x180037f4d  lea     rcx, [rsp+160h+var_100]; void *
0x180037f52  call    memset_0
0x180037f57  xorps   xmm0, xmm0
0x180037f5a  movups  xmmword ptr [rbp+60h+SystemTime.wYear], xmm0
0x180037f5e  mov     qword ptr [rsp+160h+FileTime.dwLowDateTime], 0
0x180037f67  mov     rax, [r15+420h]
0x180037f6e  mov     r14, [rax+60h]
0x180037f72  lea     rbx, [r14+0D0h]
0x180037f79  mov     rcx, rbx
0x180037f7c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180037f82  mov     r8, [r14+0C0h]
0x180037f89  mov     edx, 1
0x180037f8e  lock xadd [r8], edx
0x180037f93  inc     edx
0x180037f95  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180037f9c  test    rcx, rcx
0x180037f9f  jz      short loc_180037FA7
0x180037fa1  call    cs:__imp_WriteRefTraceLog
0x180037fa7  mov     r14, [r14+0C0h]
0x180037fae  mov     rcx, rbx
0x180037fb1  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180037fb7  mov     eax, [r14+140h]
0x180037fbe  test    eax, eax
0x180037fc0  jz      loc_18003841F
0x180037fc6  xor     r12d, r12d
0x180037fc9  lea     rdi, [r15+498h]
0x180037fd0  cmp     dword ptr [rdi], 0
0x180037fd3  jnz     loc_18003841F
0x180037fd9  cmp     r12d, eax
0x180037fdc  ja      loc_1800384BB
0x180037fe2  mov     eax, r12d
0x180037fe5  imul    r13, rax, 258h
0x180037fec  add     r13, [r14+148h]
0x180037ff3  lea     r8, [rsp+160h+var_120]; struct IUnknown **
0x180037ff8  lea     rdx, _GUID_a3c19b60_5a28_471a_8f93_ab30411cee82; struct _GUID *
0x180037fff  mov     rcx, r13; this
0x180038002  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180038007  mov     esi, eax
0x180038009  test    eax, eax
0x18003800b  jns     short loc_18003801D
0x18003800d  cmp     eax, 80004002h
0x180038012  jnz     loc_180038421
0x180038018  jmp     loc_18003840C
0x18003801d  cmp     [rsp+160h+var_100], 0
0x180038023  jnz     loc_180038173
0x180038029  mov     rax, [r15+420h]
0x180038030  movups  xmm0, xmmword ptr [rax+1244h]
0x180038037  movdqu  xmmword ptr [rbp+60h+SystemTime.wYear], xmm0
0x18003803c  lea     rdx, [rsp+160h+FileTime]; lpFileTime
0x180038041  lea     rcx, [rbp+60h+SystemTime]; lpSystemTime
0x180038045  call    cs:__imp_SystemTimeToFileTime
0x18003804b  test    eax, eax
0x18003804d  jz      loc_18003849D
0x180038053  mov     rcx, [r15+420h]
0x18003805a  mov     rax, [rcx]
0x18003805d  mov     rax, [rax+40h]
0x180038061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038066  mov     [rsp+160h+var_100], rax
0x18003806b  mov     rdx, [r15+420h]
0x180038072  mov     rax, [rdx+60h]
0x180038076  lea     rcx, dword_18004D454
0x18003807d  cmp     qword ptr [rax+8], 0
0x180038082  cmovnz  rcx, [rax+8]
0x180038087  mov     [rsp+160h+var_F8], rcx
0x18003808c  mov     rcx, [rdx+420h]
0x180038093  mov     rax, [rcx]
0x180038096  mov     rax, [rax+30h]
0x18003809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003809f  mov     [rsp+160h+var_F0], rax
0x1800380a4  mov     rcx, [r15+420h]
0x1800380ab  mov     rax, [rcx+388h]
0x1800380b2  mov     [rsp+160h+var_E8], rax
0x1800380b7  mov     rax, [rcx+16C0h]
0x1800380be  mov     [rbp+60h+var_E0], rax
0x1800380c2  mov     rcx, [rcx+438h]
0x1800380c9  movzx   ecx, word ptr [rcx+1C2h]; netshort
0x1800380d0  call    cs:__imp_ntohs
0x1800380d6  movzx   eax, ax
0x1800380d9  mov     [rbp+60h+var_D8], eax
0x1800380dc  mov     rcx, [r15+420h]
0x1800380e3  mov     rax, [rcx+1668h]
0x1800380ea  mov     [rbp+60h+var_D0], rax
0x1800380ee  mov     rcx, [rcx+438h]
0x1800380f5  movzx   ecx, word ptr [rcx+142h]; netshort
0x1800380fc  call    cs:__imp_ntohs
0x180038102  movzx   eax, ax
0x180038105  mov     [rbp+60h+var_C8], eax
0x180038108  mov     rcx, [r15+68h]; String1
0x18003810c  mov     [rbp+60h+var_C0], rcx
0x180038110  lea     rdx, aPass_0; "PASS"
0x180038117  call    cs:__imp__wcsicmp
0x18003811d  test    eax, eax
0x18003811f  jnz     short loc_180038140
0x180038121  lea     rdx, aAnonymous; "Anonymous"
0x180038128  mov     rcx, [r15+158h]; String1
0x18003812f  call    cs:__imp__wcsicmp
0x180038135  test    eax, eax
0x180038137  lea     rax, asc_180053EC8; "***"
0x18003813e  jnz     short loc_180038147
0x180038140  mov     rax, [r15+158h]
0x180038147  mov     [rbp+60h+var_B8], rax
0x18003814b  mov     rax, qword ptr [rsp+160h+FileTime.dwLowDateTime]
0x180038150  mov     [rbp+60h+var_B0], rax
0x180038154  mov     rcx, [r15+420h]
0x18003815b  mov     rax, [rcx+50h]
0x18003815f  add     rax, [rcx+40h]
0x180038163  mov     [rbp+60h+var_A8], rax
0x180038167  mov     rax, [rcx+58h]
0x18003816b  add     rax, [rcx+48h]
0x18003816f  mov     [rbp+60h+var_A0], rax
0x180038173  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003817a  mov     rax, [rcx]
0x18003817d  mov     rax, [rax+20h]
0x180038181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038186  cmp     dword ptr [rax+8], 0
0x18003818a  jz      short loc_1800381CF
0x18003818c  test    byte ptr [rax+28h], 12h
0x180038190  jz      short loc_1800381CF
0x180038192  cmp     dword ptr [rax+2Ch], 4
0x180038196  jb      short loc_1800381CF
0x180038198  mov     rdi, [r13+38h]
0x18003819c  mov     rbx, [r15+420h]
0x1800381a3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800381aa  mov     rax, [rcx]
0x1800381ad  mov     rax, [rax+20h]
0x1800381b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381b6  mov     r8, rdi; unsigned __int16 *
0x1800381b9  lea     rdx, [rbx+170h]; struct _GUID *
0x1800381c0  mov     rcx, rax; struct CEtwTracer *
0x1800381c3  call    ?RaiseEvent@StartCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpExtensibilityEvents::StartCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x1800381c8  lea     rdi, [r15+498h]
0x1800381cf  xor     ebx, ebx
0x1800381d1  mov     [rsp+160h+var_118], ebx
0x1800381d5  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800381dc  mov     rax, [rcx]
0x1800381df  mov     edx, 1
0x1800381e4  mov     rax, [rax+0B0h]
0x1800381eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381f0  mov     rcx, [rsp+160h+var_120]
0x1800381f5  mov     rax, [rcx]
0x1800381f8  mov     r8, rdi
0x1800381fb  lea     rdx, [rsp+160h+var_100]
0x180038200  mov     rax, [rax+18h]
0x180038204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038209  mov     esi, eax
0x18003820b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180038212  mov     rax, [rcx]
0x180038215  mov     edx, 1
0x18003821a  mov     rax, [rax+0B8h]
0x180038221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038226  test    esi, esi
0x180038228  jns     loc_18003835B
0x18003822e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180038235  jz      short loc_180038268
0x180038237  lea     rax, aFailedToCallIf; "Failed to call IFtpPreprocessProvider::"...
0x18003823e  mov     [rsp+160h+var_138], rax
0x180038243  mov     dword ptr [rsp+160h+var_140], esi
0x180038247  lea     r9, aFtpCommandCall_0; "FTP_COMMAND::CallPreProcessProvider"
0x18003824e  mov     r8d, 1D1Eh
0x180038254  lea     rdx, aInetsrvIisIisr_8; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18003825b  mov     rcx, cs:g_pDebug
0x180038262  call    cs:__imp_PuDbgPrintError
0x180038268  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003826f  mov     rax, [rcx]
0x180038272  mov     rax, [rax+20h]
0x180038276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003827b  cmp     dword ptr [rax+8], 0
0x18003827f  jz      short loc_1800382EA
0x180038281  test    byte ptr [rax+28h], 12h
0x180038285  jz      short loc_1800382EA
0x180038287  cmp     dword ptr [rax+2Ch], 3
0x18003828b  jb      short loc_1800382EA
0x18003828d  lea     rcx, [rbp+60h+var_80]
0x180038291  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180038297  nop
0x180038298  lea     rcx, [rbp+60h+var_80]; struct STRU *
0x18003829c  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x1800382a1  mov     rbx, [rbp+60h+var_60]
0x1800382a5  mov     rdi, [r15+420h]
0x1800382ac  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800382b3  mov     rax, [rcx]
0x1800382b6  mov     rax, [rax+20h]
0x1800382ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382bf  mov     r9, rbx; unsigned __int16 *
0x1800382c2  mov     r8d, esi; unsigned int
0x1800382c5  lea     rdx, [rdi+170h]; struct _GUID *
0x1800382cc  mov     rcx, rax; struct CEtwTracer *
0x1800382cf  call    ?RaiseEvent@FailCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBG@Z; FtpExtensibilityEvents::FailCallProvider::RaiseEvent(CEtwTracer *,_GUID const *,ulong,ushort const *)
0x1800382d4  nop
0x1800382d5  lea     rcx, [rbp+60h+var_80]
0x1800382d9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800382df  mov     ebx, [rsp+160h+var_118]
0x1800382e3  lea     rdi, [r15+498h]
0x1800382ea  cmp     esi, 80010108h
0x1800382f0  jz      short loc_18003830E
0x1800382f2  cmp     esi, 800706BEh
0x1800382f8  jz      short loc_18003830E
0x1800382fa  cmp     esi, 80131014h
0x180038300  jz      short loc_18003830E
0x180038302  cmp     esi, 800706BAh
0x180038308  jnz     loc_180038421
0x18003830e  mov     rcx, [rsp+160h+var_120]
0x180038313  mov     rax, [rcx]
0x180038316  mov     rax, [rax+10h]
0x18003831a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003831f  mov     [rsp+160h+var_120], 0
0x180038328  mov     rcx, r13; this
0x18003832b  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x180038330  lea     r8, [rsp+160h+var_120]; struct IUnknown **
0x180038335  lea     rdx, _GUID_a3c19b60_5a28_471a_8f93_ab30411cee82; struct _GUID *
0x18003833c  mov     rcx, r13; this
0x18003833f  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180038344  test    eax, eax
0x180038346  js      loc_180038421
0x18003834c  inc     ebx
0x18003834e  mov     [rsp+160h+var_118], ebx
0x180038352  cmp     ebx, 2
0x180038355  jb      loc_1800381D5
0x18003835b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180038362  mov     rax, [rcx]
0x180038365  mov     rax, [rax+20h]
0x180038369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003836e  cmp     dword ptr [rax+8], 0
0x180038372  jz      short loc_1800383A9
0x180038374  test    byte ptr [rax+28h], 12h
0x180038378  jz      short loc_1800383A9
0x18003837a  cmp     dword ptr [rax+2Ch], 4
0x18003837e  jb      short loc_1800383A9
0x180038380  mov     rbx, [r15+420h]
0x180038387  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003838e  mov     rax, [rcx]
0x180038391  mov     rax, [rax+20h]
0x180038395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003839a  lea     rdx, [rbx+170h]; struct _GUID *
0x1800383a1  mov     rcx, rax; struct CEtwTracer *
0x1800383a4  call    ?RaiseEvent@EndCallProvider@FtpExtensibilityEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@@Z; FtpExtensibilityEvents::EndCallProvider::RaiseEvent(CEtwTracer *,_GUID const *)
0x1800383a9  mov     eax, [rdi]
0x1800383ab  test    eax, eax
0x1800383ad  jz      short loc_1800383F2
0x1800383af  test    byte ptr cs:g_dwDebugFlags, 3
0x1800383b6  jz      short loc_1800383F2
0x1800383b8  mov     [rsp+160h+var_130], eax
0x1800383bc  mov     rax, [r13+38h]
0x1800383c0  mov     [rsp+160h+var_138], rax
0x1800383c5  lea     rax, aIftppreprocess; "IFtpPreprocessProvider [%S] set [%d] no"...
0x1800383cc  mov     [rsp+160h+var_140], rax
0x1800383d1  lea     r9, aFtpCommandCall_0; "FTP_COMMAND::CallPreProcessProvider"
0x1800383d8  mov     r8d, 1D61h
0x1800383de  lea     rdx, aInetsrvIisIisr_8; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800383e5  mov     rcx, cs:g_pDebug
0x1800383ec  call    cs:__imp_PuDbgPrint
0x1800383f2  mov     rcx, [rsp+160h+var_120]
0x1800383f7  mov     rax, [rcx]
0x1800383fa  mov     rax, [rax+10h]
0x1800383fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038403  mov     [rsp+160h+var_120], 0
0x18003840c  inc     r12d
0x18003840f  mov     eax, [r14+140h]
0x180038416  cmp     r12d, eax
0x180038419  jb      loc_180037FD0
0x18003841f  xor     esi, esi
0x180038421  test    r14, r14
0x180038424  jz      short loc_180038465
0x180038426  or      ebx, 0FFFFFFFFh
0x180038429  lock xadd [r14], ebx
0x18003842e  dec     ebx
0x180038430  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180038437  test    rcx, rcx
0x18003843a  jz      short loc_180038447
0x18003843c  mov     r8, r14
0x18003843f  mov     edx, ebx
0x180038441  call    cs:__imp_WriteRefTraceLog
0x180038447  test    ebx, ebx
0x180038449  jnz     short loc_180038465
0x18003844b  mov     rcx, r14; this
0x18003844e  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180038453  nop
0x180038454  mov     rdx, r14
0x180038457  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003845e  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180038464  nop
0x180038465  mov     rcx, [rsp+160h+var_120]
0x18003846a  test    rcx, rcx
  ... truncated ...
```
