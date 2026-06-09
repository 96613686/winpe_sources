# CRdpUdpStream::InitializeInstance(IRDPENCCONStreamWorker *,IRDPENCTcpEndpointInfo *,IRdpUdpConnection *,RDPUDP_TRANSPORT_SETTINGS *)

- ea: `0x18040c210`
- end: `0x18040d7c4`
- name: `?InitializeInstance@CRdpUdpStream@@UEAAJPEAUIRDPENCCONStreamWorker@@PEAUIRDPENCTcpEndpointInfo@@PEAUIRdpUdpConnection@@PEAURDPUDP_TRANSPORT_SETTINGS@@@Z`
- size: `5556`
- prototype: `__int64 __fastcall(CRdpUdpStream *__hidden this, struct IRDPENCCONStreamWorker *, struct IRDPENCTcpEndpointInfo *, struct IRdpUdpConnection *, struct RDPUDP_TRANSPORT_SETTINGS *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting`

## callees

- `0x180001e8c`
- `0x180002058`
- `0x1800031a8`
- `0x1800033b4`
- `0x1800054f4`
- `0x1800186a0`
- `0x1800186d0`
- `0x180020670`
- `0x1800207cc`
- `0x180082910`
- `0x1800829d4`
- `0x180082ad8`
- `0x1800cf498`
- `0x18012962c`
- `0x18040b470`
- `0x18040b700`
- `0x18040c1c0`
- `0x18040c210`
- `0x18040da30`
- `0x18040dafc`
- `0x18040e1e0`
- `0x180428e68`
- `0x180429088`
- `0x18042a524`
- `0x18042aa9c`
- `0x18042b59c`
- `0x18042bc58`
- `0x1805d4890`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18040ce84`
- `msvcrt!wcsrchr` at `0x18040ce84`
- `KERNEL32!LoadLibraryW` at `0x18040cf66`
- `KERNEL32!LoadLibraryW` at `0x18040cf66`
- `KERNEL32!GetModuleHandleExW` at `0x18040cd71`
- `KERNEL32!GetModuleHandleExW` at `0x18040cd71`
- `KERNEL32!GetLastError` at `0x18040c752`
- `KERNEL32!GetLastError` at `0x18040cdab`
- `KERNEL32!GetLastError` at `0x18040cdda`
- `KERNEL32!GetLastError` at `0x18040cdfd`
- `KERNEL32!GetLastError` at `0x18040ce24`
- `KERNEL32!GetLastError` at `0x18040c752`
- `KERNEL32!GetLastError` at `0x18040cdab`
- `KERNEL32!GetLastError` at `0x18040cdda`
- `KERNEL32!GetLastError` at `0x18040cdfd`
- `KERNEL32!GetLastError` at `0x18040ce24`
- `KERNEL32!GetProcAddress` at `0x18040cfdb`
- `KERNEL32!GetProcAddress` at `0x18040cfdb`
- `KERNEL32!FreeLibrary` at `0x18040d061`
- `KERNEL32!FreeLibrary` at `0x18040d7ae`
- `KERNEL32!FreeLibrary` at `0x18040d061`
- `KERNEL32!FreeLibrary` at `0x18040d7ae`
- `KERNEL32!GetModuleFileNameW` at `0x18040cd90`
- `KERNEL32!GetModuleFileNameW` at `0x18040cd90`
- `KERNEL32!CreateEventW` at `0x18040c73a`
- `KERNEL32!CreateEventW` at `0x18040c73a`
- `WS2_32!__imp_htons` at `0x18040d26f`
- `WS2_32!__imp_htons` at `0x18040d26f`

## string_xrefs

- `0x18040c704`: `UDP stream failed to create server state transition logger `
- `0x18040c776`: `Failed to create the stream event`
- `0x18040c6d4`: `UDP stream failed to create client state transition logger `
- `0x18040c912`: `Illegal value for CWndBeta was read from the registry - Resetting to default`
- `0x18040cfd1`: `CreateRdpUdpStreamWrapper`
- `0x18040d00d`: `CreateRdpUdpStreamWrapper failed`
- `0x18040cf37`: `Loading dll`
- `0x18040cf9f`: `Failed to loadLibrary RdpNanoTransport.dll for URCP. Fall back to UDP v2`
- `0x18040ce8a`: `rdpnanoTransport.dll`
- `0x18040cece`: `StringCchCat of file path failed`

## pseudocode

```c
__int64 __fastcall CRdpUdpStream::InitializeInstance(
        CRdpUdpStream *this,
        struct IRDPENCCONStreamWorker *a2,
        struct IRDPENCTcpEndpointInfo *a3,
        struct IRdpUdpConnection *a4,
        struct RDPUDP_TRANSPORT_SETTINGS *a5)
{
  signed int ClientEventLogCallback; // ebx
  __int16 *v9; // rdx
  const char **v10; // rax
  char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rdi
  const char *v14; // rdi
  struct RDPUDP_TRANSPORT_SETTINGS *v15; // rdi
  CRdpUdpStream *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  __int16 *v19; // rdx
  const char *v20; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v23; // ecx
  unsigned int v24; // r8d
  int v25; // r9d
  float v26; // xmm6_4
  CRdpUdpStream *v27; // rcx
  CRdpUdpStream *v28; // rcx
  CRdpUdpStream *v29; // rcx
  CRdpUdpStream *v30; // rcx
  CRdpUdpStream *v31; // rcx
  CRdpUdpStream *v32; // rcx
  CRdpUdpStream *v33; // rcx
  CRdpUdpStream *v34; // rcx
  CRdpUdpStream *v35; // rcx
  CRdpUdpStream *v36; // rcx
  int v37; // r8d
  int v38; // r9d
  CRdpUdpStream *v39; // rcx
  int v40; // r9d
  unsigned int v41; // ecx
  _DWORD *v42; // r13
  int v43; // edx
  BOOL v44; // ecx
  signed int v45; // eax
  bool v46; // zf
  int v47; // edx
  CRdpUdpStream *v48; // rcx
  const struct _GUID *v49; // rdx
  int v50; // r8d
  int v51; // r9d
  RdpUdpETWEvents *v52; // rcx
  CRdpUdpTimer *v53; // rax
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r9d
  unsigned int v58; // eax
  DWORD ModuleFileNameW; // eax
  signed int v60; // eax
  bool v61; // sf
  signed int v62; // eax
  int v63; // ecx
  int v64; // r8d
  int v65; // r9d
  __int64 *v66; // rdx
  const char *v67; // rax
  signed int v68; // eax
  bool v69; // sf
  signed int v70; // eax
  wchar_t *v71; // rax
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  wchar_t *v75; // rbx
  int v76; // eax
  WCHAR *v77; // rax
  WCHAR *v78; // rcx
  HMODULE LibraryW; // rax
  int v80; // r8d
  int v81; // r9d
  __int64 *v82; // rdi
  FARPROC ProcAddress; // rax
  int v84; // eax
  int v85; // r8d
  int v86; // r9d
  int v87; // ecx
  int v88; // r8d
  int v89; // r9d
  void *v90; // rax
  int v91; // r8d
  int v92; // r9d
  _QWORD *v93; // rax
  int v94; // r8d
  int v95; // r9d
  __int128 v96; // xmm0
  unsigned int i; // r13d
  __int64 v98; // rdi
  __int64 (__fastcall *v99)(__int64, __int64, __int64, _QWORD, __int128 *, __int64); // rbx
  __int64 v100; // rax
  __int64 v101; // r8
  __int64 v102; // rdx
  int v103; // ecx
  int v104; // r9d
  struct _GUID *v105; // rdx
  HMODULE v106; // rcx
  int v107; // r8d
  int v108; // r9d
  CFecEncoder *v110; // rax
  int v111; // r8d
  int v112; // r9d
  CFecEncoder *v113; // rax
  int v114; // ecx
  int v115; // r8d
  int v116; // r9d
  CFecDecoder *v117; // rax
  int v118; // r8d
  int v119; // r9d
  int v120; // ecx
  int v121; // r8d
  int v122; // r9d
  void *v123; // rax
  int v124; // r9d
  HMODULE *p_phModule; // [rsp+40h] [rbp-C8h]
  const char **v126; // [rsp+48h] [rbp-C0h]
  const char **v127; // [rsp+50h] [rbp-B8h]
  const char *v128; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v129; // [rsp+60h] [rbp-A8h] BYREF
  const char *v130; // [rsp+68h] [rbp-A0h] BYREF
  const char *v131; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v132[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v133; // [rsp+88h] [rbp-80h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp-70h] BYREF
  const char *v135; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v136; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v137; // [rsp+ACh] [rbp-5Ch] BYREF
  unsigned int v138; // [rsp+B0h] [rbp-58h] BYREF
  CRdpUdpStream *v139; // [rsp+B4h] [rbp-54h] BYREF
  unsigned int v140; // [rsp+BCh] [rbp-4Ch] BYREF
  unsigned int v141; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v142; // [rsp+C4h] [rbp-44h] BYREF
  unsigned int v143; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v144; // [rsp+CCh] [rbp-3Ch] BYREF
  unsigned int v145; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int v146; // [rsp+D4h] [rbp-34h] BYREF
  unsigned int v147[4]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR Filename[264]; // [rsp+E8h] [rbp-20h] BYREF

  v135 = (const char *)a4;
  *(_QWORD *)&v133 = a3;
  if ( !a5 )
  {
    ClientEventLogCallback = -2147467261;
    if ( (unsigned int)dword_1808B5850 <= 2 )
    {
LABEL_5:
      v11 = (char *)this - 64;
      goto LABEL_158;
    }
    LODWORD(phModule) = 516;
    v135 = "pSettings is NULL";
    v128 = "InitializeInstance";
    v130 = "Error condition failed";
    v127 = &v135;
    v9 = (__int16 *)&byte_18087A91F;
    v126 = &v128;
    p_phModule = &phModule;
    v10 = &v130;
LABEL_4:
    LODWORD(v129) = -2147467261;
    v132[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v9,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v10,
      (__int64)&v129,
      (__int64)v132,
      (__int64)p_phModule,
      (__int64)v126,
      (__int64)v127);
    goto LABEL_5;
  }
  if ( !*((_DWORD *)a5 + 2) )
  {
    if ( !a2 && (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v129) = *((_DWORD *)this + 32);
      v131 = "StreamWorker is invalid";
      v130 = "InitializeInstance";
      LODWORD(phModule) = 525;
      v132[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v128) = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)qword_18087B018,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v131,
        (__int64)&v128,
        (__int64)v132,
        (__int64)&phModule,
        (__int64)&v130,
        (__int64)&v129);
    }
    if ( !a3 && (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v128) = *((_DWORD *)this + 32);
      v132[0] = "m_spEndpointInfo is invalid";
      v131 = "InitializeInstance";
      LODWORD(v129) = 529;
      v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(phModule) = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)&word_180879BD6,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)v132,
        (__int64)&phModule,
        (__int64)&v130,
        (__int64)&v129,
        (__int64)&v131,
        (__int64)&v128);
    }
    v12 = v135;
    if ( !v135 )
    {
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        LODWORD(v128) = *((_DWORD *)this + 32);
        v132[0] = "m_spConnection is invalid";
        v131 = "InitializeInstance";
        LODWORD(v129) = 533;
        v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
        LODWORD(phModule) = -2147467261;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)this,
          (unsigned int)byte_1808797CB,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)v132,
          (__int64)&phModule,
          (__int64)&v130,
          (__int64)&v129,
          (__int64)&v131,
          (__int64)&v128);
      }
      v12 = v135;
    }
    if ( !a2 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_5;
      v130 = "InitializeInstance";
      v131 = "pWorker is NULL";
      v9 = (__int16 *)&byte_1808794CF;
      LODWORD(v128) = 536;
      v135 = "Error condition failed";
      v127 = &v131;
      v126 = &v130;
      p_phModule = (HMODULE *)&v128;
      v10 = &v135;
      goto LABEL_4;
    }
    if ( !a3 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_5;
      v130 = "InitializeInstance";
      v131 = "pEndpointInfo is NULL";
      v9 = &word_180879DAE;
      LODWORD(v128) = 537;
      v135 = "Error condition failed";
      v127 = &v131;
      v126 = &v130;
      p_phModule = (HMODULE *)&v128;
      v10 = &v135;
      goto LABEL_4;
    }
    if ( !v12 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_5;
      v130 = "InitializeInstance";
      v131 = "pSocket is NULL";
      v9 = word_18087B11A;
      LODWORD(v128) = 538;
      v135 = "Error condition failed";
      v127 = &v131;
      v126 = &v130;
      p_phModule = (HMODULE *)&v128;
      v10 = &v135;
      goto LABEL_4;
    }
  }
  CTSReaderWriterLock::WriteLock((CRdpUdpStream *)((char *)this + 92));
  if ( a2 != *((struct IRDPENCCONStreamWorker **)this + 6) )
  {
    TCntPtr<ITSViewerRecorder>::SafeRelease((char *)this + 48);
    *((_QWORD *)this + 6) = a2;
    TCntPtr<IPin>::SafeAddRef((char *)this + 48);
  }
  v13 = v133;
  if ( (_QWORD)v133 != *((_QWORD *)this + 8) )
  {
    TCntPtr<ITSViewerRecorder>::SafeRelease((char *)this + 64);
    *((_QWORD *)this + 8) = v13;
    TCntPtr<IPin>::SafeAddRef((char *)this + 64);
  }
  v14 = v135;
  if ( v135 != *((const char **)this + 9) )
  {
    TCntPtr<ITSViewerRecorder>::SafeRelease((char *)this + 72);
    *((_QWORD *)this + 9) = v14;
    TCntPtr<IPin>::SafeAddRef((char *)this + 72);
  }
  CTSReaderWriterLock::WriteUnlock((CRdpUdpStream *)((char *)this + 92));
  v15 = a5;
  v16 = (CRdpUdpStream *)((char *)this - 64);
  if ( *((_DWORD *)a5 + 6) )
  {
    ClientEventLogCallback = CRdpUdpStream::CreateClientEventLogCallback(v16);
    if ( ClientEventLogCallback >= 0 )
      goto LABEL_41;
    if ( (unsigned int)dword_1808B5850 <= 4 )
      goto LABEL_40;
    v19 = word_18087AD22;
    LODWORD(v128) = *((_DWORD *)this + 32);
    v20 = "UDP stream failed to create client state transition logger ";
    goto LABEL_39;
  }
  ClientEventLogCallback = CRdpUdpStream::CreateServerEventLogCallback(v16);
  if ( ClientEventLogCallback >= 0 )
    goto LABEL_41;
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v19 = (__int16 *)&dword_180879734;
    LODWORD(v128) = *((_DWORD *)this + 32);
    v20 = "UDP stream failed to create server state transition logger ";
LABEL_39:
    *(_QWORD *)&v133 = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1808B5850,
      (_DWORD)v19,
      v17,
      v18,
      (__int64)&v133,
      (__int64)&v128);
  }
LABEL_40:
  ClientEventLogCallback = 0;
LABEL_41:
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 48) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    ClientEventLogCallback = LastError;
    if ( LastError > 0 )
      ClientEventLogCallback = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v131 = "InitializeInstance";
      *(_QWORD *)&v133 = "Failed to create the stream event";
      LODWORD(v128) = 571;
      v132[0] = "Error condition failed";
      v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v129) = ClientEventLogCallback;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v23,
        (unsigned int)byte_18087B165,
        v24,
        v25,
        (__int64)v132,
        (__int64)&v129,
        (__int64)&v130,
        (__int64)&v128,
        (__int64)&v131,
        (__int64)&v133);
    }
    goto LABEL_157;
  }
  v26 = FLOAT_0_25;
  v137 = 2;
  v136 = 875;
  v140 = 1;
  *(_QWORD *)v147 = 10000000;
  v139 = (CRdpUdpStream *)0x100000000LL;
  v138 = 0;
  v141 = 4;
  v142 = 3;
  v144 = 75000;
  v143 = 0;
  v145 = 15000;
  v146 = 0;
  CRdpUdpStream::ReadRegistryValue(0, L"ForceDisableUDPL", &v146);
  CRdpUdpStream::ReadRegistryValue(v27, L"UdpFecMode", &v137);
  if ( v137 == 1 )
    v138 = 9;
  CRdpUdpStream::ReadRegistryValue(v28, L"UdpDontTimeout", &v143);
  CRdpUdpStream::ReadRegistryValue(v29, L"UdpCongestionController", (unsigned int *)&v139 + 1);
  CRdpUdpStream::ReadRegistryValue(v30, L"UdpCWndMultiplier", &v140);
  CRdpUdpStream::ReadRegistryValue(v31, L"UdpCWndAlpha", &v141);
  CRdpUdpStream::ReadRegistryValue(v32, L"UdpCWndBeta", &v136);
  CRdpUdpStream::ReadRegistryValue(v33, L"DupAckThreshold", &v142);
  CRdpUdpStream::ReadRegistryValue(v34, L"OutOfOrderWaitTimeout", &v144);
  CRdpUdpStream::ReadRegistryValue(v35, L"UdpQLengthTraceInterval", &v145);
  if ( v136 > 0x3E8 )
  {
    if ( (unsigned int)dword_1808B5850 > 3 )
    {
      LODWORD(v129) = v136;
      *(_QWORD *)&v133 = "Illegal value for CWndBeta was read from the registry - Resetting to default";
      LODWORD(v128) = 875;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v36,
        (unsigned int)byte_180879DF9,
        v37,
        v38,
        (__int64)&v133,
        (__int64)&v129,
        (__int64)&v128);
    }
    v136 = 875;
  }
  CRdpUdpStream::ReadRegistryValue(v36, L"UdpFecAdaptiveIntervalNs", v147);
  CRdpUdpStream::ReadRegistryValue(v39, L"UdpFecAdaptiveRoundupPercent", (unsigned int *)&v139);
  if ( (unsigned int)((_DWORD)v139 - 1) <= 0x62 )
    v26 = (float)(int)v139 / 100.0;
  CRdpUdpStream::ReadRegistryValue((CRdpUdpStream *)(unsigned int)v139, L"UdpFecInitialBlockM", &v138);
  v41 = CRdpUdpStream::connId;
  v42 = (_DWORD *)((char *)this + 128);
  *((_DWORD *)this + 32) = CRdpUdpStream::connId;
  *((_DWORD *)this + 33) = 0;
  v43 = *(_DWORD *)a5;
  *((_DWORD *)this + 36) = 1045220557;
  CRdpUdpStream::connId = v41 + 1;
  v44 = v43 == 0;
  *((_DWORD *)this + 35) = v137;
  *((_DWORD *)this + 37) = HIDWORD(v139);
  *((_DWORD *)this + 38) = v140;
  *((_DWORD *)this + 39) = v141;
  v45 = v136;
  *((_DWORD *)this + 34) = v44;
  *((_DWORD *)this + 41) = v142;
  *((float *)this + 40) = (float)v45 / 1000.0;
  *((_DWORD *)this + 42) = *((_DWORD *)a5 + 5);
  *((_DWORD *)this + 43) = *((_DWORD *)a5 + 4);
  *((_QWORD *)this + 22) = *((unsigned int *)a5 + 3);
  *((_DWORD *)this + 46) = v44;
  v46 = *((_DWORD *)a5 + 2) == 0;
  *((float *)this + 52) = v26;
  *((_DWORD *)this + 47) = !v46;
  *((_QWORD *)this + 25) = *(_QWORD *)v147;
  *((_DWORD *)this + 53) = v138;
  *((_DWORD *)this + 54) = v143;
  *((_DWORD *)this + 57) = v144;
  *((_QWORD *)this + 30) = v145;
  *((_DWORD *)this + 48) = *((_DWORD *)a5 + 6);
  *((_DWORD *)this + 33) = *((unsigned __int16 *)a5 + 14);
  if ( v43 )
  {
    *((_DWORD *)this + 35) = 1;
    *((_DWORD *)this + 53) = 9;
  }
  if ( v146 )
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      *(_QWORD *)&v133 = "Overriding UDP-Lossy Transport -- Please Note: Client and Server both must override UDP Lossy. "
                         "Else, the session *WILL* disconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)&byte_18087963F,
        0,
        v40,
        (__int64)&v133);
    }
    *((_DWORD *)this + 34) = 1;
  }
  v47 = *((_DWORD *)a5 + 6);
  LODWORD(phModule) = v47 != 0 ? 1024 : 200;
  v48 = (CRdpUdpStream *)(unsigned int)phModule;
  *((_WORD *)this + 111) = v47 != 0 ? 1024 : 200;
  LOWORD(v48) = v47 != 0 ? 2048 : 256;
  *((_WORD *)this + 112) = (_WORD)v48;
  *((_WORD *)this + 113) = v47 != 0 ? 4096 : 512;
  CRdpUdpStream::ReadRegistryValue(v48, L"ReceiverWindowSize", (unsigned int *)&phModule);
  *((_WORD *)this + 110) = (_WORD)phModule;
  CRdpUdpETWEvents_CreateInstance((CRdpUdpStream *)((char *)this + 128), v49, (void **)this + 14);
  v52 = (RdpUdpETWEvents *)*((_QWORD *)this + 14);
  if ( !v52 )
  {
    ClientEventLogCallback = -2147024882;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v131 = "InitializeInstance";
      *(_QWORD *)&v133 = "CRdpUdpETWEvents allocation";
      LODWORD(v128) = 705;
      v132[0] = "Error condition failed";
      v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v129) = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)&word_18087988E,
        v50,
        v51,
        (__int64)v132,
        (__int64)&v129,
        (__int64)&v130,
        (__int64)&v128,
        (__int64)&v131,
        (__int64)&v133);
    }
    goto LABEL_5;
  }
  RdpUdpETWEvents::Enable(v52);
  v53 = (CRdpUdpTimer *)operator new(0x18u);
  if ( v53 )
  {
    *(_QWORD *)v53 = 0;
    *((_QWORD *)v53 + 1) = 1;
    *((_QWORD *)v53 + 2) = 0;
  }
  *((_QWORD *)this + 33) = v53;
  if ( !v53 )
  {
    ClientEventLogCallback = -2147024882;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v131 = "InitializeInstance";
      *(_QWORD *)&v133 = "CRdpUdpTimer allocation";
      LODWORD(v128) = 713;
      v132[0] = "Error condition failed";
      v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v129) = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)&word_18087B246,
        v54,
        v55,
        (__int64)v132,
        (__int64)&v129,
        (__int64)&v130,
        (__int64)&v128,
        (__int64)&v131,
        (__int64)&v133);
    }
    goto LABEL_5;
  }
  CRdpUdpTimer::Initialize(v53);
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    LODWORD(v128) = *((_DWORD *)this + 34) == 0;
    LODWORD(v129) = *((_DWORD *)this + 33);
    LODWORD(phModule) = *v42;
    *(_QWORD *)&v133 = "UDP Stream";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v56,
      (unsigned int)&byte_18087B67F,
      v24,
      v57,
      (__int64)&v133,
      (__int64)&phModule,
      (__int64)&v129,
      (__int64)&v128);
  }
  v58 = *((_DWORD *)this + 33);
  if ( v58 == 257 )
  {
    phModule = 0;
    memset_0(Filename, 0, 0x20Au);
    if ( GetModuleHandleExW(6u, (LPCWSTR)CRdpUdpStream::STATIC_GatewayWorkerThread, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW && ModuleFileNameW != 261 )
        goto LABEL_89;
      Filename[0] = 0;
      v60 = GetLastError();
      v61 = v60 < 0;
      if ( v60 > 0 )
        v61 = 1;
      if ( !v61 || (unsigned int)dword_1808B5850 <= 3 )
        goto LABEL_89;
      *(_QWORD *)&v133 = "InitializeInstance";
      v62 = GetLastError();
      if ( v62 > 0 )
        v62 = (unsigned __int16)v62 | 0x80070000;
      LODWORD(v128) = v62;
      v66 = (__int64 *)byte_18087A509;
      v67 = "Failed to get the module file name";
    }
    else
    {
      v68 = GetLastError();
      v69 = v68 < 0;
      if ( v68 > 0 )
        v69 = 1;
      if ( !v69 || (unsigned int)dword_1808B5850 <= 3 )
        goto LABEL_89;
      *(_QWORD *)&v133 = "InitializeInstance";
      v70 = GetLastError();
      if ( v70 > 0 )
        v70 = (unsigned __int16)v70 | 0x80070000;
      LODWORD(v128) = v70;
      v66 = qword_18087B2B0;
      v67 = "Failed to get module handle to itself.";
    }
    v131 = v67;
    v130 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v63,
      (_DWORD)v66,
      v64,
      v65,
      (__int64)&v130,
      (__int64)&v131,
      (__int64)&v128,
      (__int64)&v133);
LABEL_89:
    v71 = wcsrchr(Filename, 0x5Cu);
    v75 = v71;
    if ( v71 )
    {
      v75 = v71 + 1;
      v71[1] = 0;
      v76 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v76 < 0 )
      {
        v72 = dword_1808B5850;
        v75 = 0;
        if ( (unsigned int)dword_1808B5850 > 3 )
        {
          LODWORD(v128) = v76;
          *(_QWORD *)&v133 = "InitializeInstance";
          v131 = "StringCchCat of file path failed";
          v130 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1808B5850,
            (unsigned int)byte_180879EC1,
            v73,
            v74,
            (__int64)&v130,
            (__int64)&v131,
            (__int64)&v128,
            (__int64)&v133);
        }
      }
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v77 = Filename;
      if ( !v75 )
        v77 = (WCHAR *)L"rdpnanoTransport.dll";
      *(_QWORD *)&v133 = v77;
      v131 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v72,
        (unsigned int)&dword_18087AECC,
        v73,
        v74,
        (__int64)&v131,
        (__int64)&v133);
    }
    v78 = Filename;
    if ( !v75 )
      v78 = (WCHAR *)L"rdpnanoTransport.dll";
    LibraryW = LoadLibraryW(v78);
    *((_QWORD *)this + 76) = LibraryW;
    if ( LibraryW )
    {
      v82 = (__int64 *)((char *)this + 376);
      *((_QWORD *)this + 47) = 0;
      ProcAddress = GetProcAddress(LibraryW, "CreateRdpUdpStreamWrapper");
      if ( ProcAddress )
      {
        v84 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(11, (char *)this + 376);
        if ( v84 < 0 && (unsigned int)dword_1808B5850 > 3 )
        {
          LODWORD(v128) = v84;
          *(_QWORD *)&v133 = "InitializeInstance";
          v131 = "CreateRdpUdpStreamWrapper failed";
          v130 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1808B5850,
            (unsigned int)qword_180879E88,
            v85,
            v86,
            (__int64)&v130,
            (__int64)&v131,
            (__int64)&v128,
            (__int64)&v133);
        }
      }
      if ( *v82 )
      {
        if ( !*((_DWORD *)a5 + 6) )
          *((_DWORD *)this + 58) = 1;
        v90 = operator new(*((_QWORD *)this + 22) + 2050LL);
        *((_QWORD *)this + 69) = v90;
        if ( !v90 )
        {
          ClientEventLogCallback = -2147024882;
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v131 = "InitializeInstance";
            *(_QWORD *)&v133 = "SendBuffer allocation";
            LODWORD(v128) = 812;
            v132[0] = "Error condition failed";
            v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v129) = -2147024882;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              -2147024882,
              (unsigned int)word_18087A3FA,
              v91,
              v92,
              (__int64)v132,
              (__int64)&v129,
              (__int64)&v130,
              (__int64)&v128,
              (__int64)&v131,
              (__int64)&v133);
          }
          goto LABEL_5;
        }
        v93 = operator new(0x28u);
        if ( v93 )
        {
          v96 = *(_OWORD *)((char *)this + 564);
          v93[4] = 0;
          *v93 = &CRdpUdpStreamWrapperCallback::`vftable';
          v93[1] = (char *)this - 64;
          *((_OWORD *)v93 + 1) = v96;
        }
        else
        {
          v93 = 0;
        }
        v129 = 564;
        *((_QWORD *)this + 77) = v93;
        if ( !v93 )
        {
          ClientEventLogCallback = -2147024882;
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v131 = "InitializeInstance";
            *(_QWORD *)&v133 = "CRdpUdpStreamWrapperCallback allocation";
            LODWORD(v128) = 815;
            v132[0] = "Error condition failed";
            v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v129) = -2147024882;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              -2147024882,
              (unsigned int)byte_180879F21,
              v94,
              v95,
              (__int64)v132,
              (__int64)&v129,
              (__int64)&v130,
              (__int64)&v128,
              (__int64)&v131,
              (__int64)&v133);
          }
          goto LABEL_5;
        }
        v128 = 0;
        HIWORD(v128) = htons(1u);
        for ( i = 0; i < 8; ++i )
        {
          if ( *((_BYTE *)&v128 + i) == 1 )
            break;
        }
        v98 = *v82;
        v99 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int128 *, __int64))(*(_QWORD *)v98 + 32LL);
        v100 = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v135 + 80LL))(v135);
        v101 = *((_QWORD *)this + 77);
        LOBYTE(v102) = *((_DWORD *)this + 48) != 0;
        v133 = *(_OWORD *)((char *)this + v129);
        ClientEventLogCallback = v99(v98, v102, v101, i, &v133, v100);
        if ( ClientEventLogCallback < 0 )
        {
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v131 = "InitializeInstance";
            *(_QWORD *)&v133 = "RdpUdpStreamWrapper Initialize failed";
            LODWORD(v128) = 831;
            v132[0] = "Error HResult failed";
            v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v129) = ClientEventLogCallback;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v103,
              (unsigned int)&dword_18087A2F4,
              v24,
              v104,
              (__int64)v132,
              (__int64)&v129,
              (__int64)&v130,
              (__int64)&v128,
              (__int64)&v131,
              (__int64)&v133);
          }
          goto LABEL_5;
        }
        v11 = (char *)this - 64;
LABEL_128:
        v105 = (struct _GUID *)*((unsigned int *)v11 + 49);
        v133 = *(_OWORD *)((char *)this + 564);
        RDPTransportTraceLogging::LogRDPTransportUDPProfile((RDPTransportTraceLogging *)&v133, v105, v24);
        goto LABEL_129;
      }
      FreeLibrary(*((HMODULE *)this + 76));
      *((_QWORD *)this + 76) = 0;
      if ( (unsigned int)dword_1808B5850 > 3 )
      {
        LODWORD(v129) = *v42;
        *(_QWORD *)&v133 = "Failed to get UDP-Nano wrapper with an expected interface version. Fall back to UDP v2";
        LODWORD(v128) = 11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v87,
          (unsigned int)byte_18087A2B5,
          v88,
          v89,
          (__int64)&v133,
          (__int64)&v129,
          (__int64)&v128);
      }
    }
    else if ( (unsigned int)dword_1808B5850 > 3 )
    {
      LODWORD(v128) = *v42;
      *(_QWORD *)&v133 = "Failed to loadLibrary RdpNanoTransport.dll for URCP. Fall back to UDP v2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)&word_18087979E,
        v80,
        v81,
        (__int64)&v133,
        (__int64)&v128);
    }
    v15 = a5;
    goto LABEL_134;
  }
  if ( v58 < 0x101 )
  {
    if ( v58 < 0x100 )
    {
LABEL_135:
      v110 = (CFecEncoder *)operator new(0x1260u);
      if ( v110 )
        v113 = CFecEncoder::CFecEncoder(v110);
      else
        v113 = 0;
      *((_QWORD *)this + 31) = v113;
      if ( !v113 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v131 = "InitializeInstance";
          *(_QWORD *)&v133 = "CFecEncoder allocation";
          LODWORD(v128) = 847;
          v132[0] = "Error condition failed";
          v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v129) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)qword_18087B1B0,
            v111,
            v112,
            (__int64)v132,
            (__int64)&v129,
            (__int64)&v130,
            (__int64)&v128,
            (__int64)&v131,
            (__int64)&v133);
        }
        goto LABEL_5;
      }
      ClientEventLogCallback = CFecEncoder::Initialize(
                                 v113,
                                 (CRdpUdpStream *)((char *)this + 128),
                                 *((struct CRdpUdpTimer **)this + 33),
                                 *((struct IRdpUdpControlEvents **)this + 14));
      if ( ClientEventLogCallback < 0 )
      {
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v131 = "InitializeInstance";
          *(_QWORD *)&v133 = "FecEncoder initialization failed";
          LODWORD(v128) = 849;
          v132[0] = "Error HResult failed";
          v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v129) = ClientEventLogCallback;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v114,
            (unsigned int)qword_18087ADF8,
            v115,
            v116,
            (__int64)v132,
            (__int64)&v129,
            (__int64)&v130,
            (__int64)&v128,
            (__int64)&v131,
            (__int64)&v133);
        }
        goto LABEL_5;
      }
      v117 = (CFecDecoder *)operator new(0x190u);
      if ( v117 )
        v117 = CFecDecoder::CFecDecoder(v117);
      *((_QWORD *)this + 32) = v117;
      if ( !v117 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v131 = "InitializeInstance";
          *(_QWORD *)&v133 = "CFecDecoder allocation";
          LODWORD(v128) = 853;
          v132[0] = "Error condition failed";
          v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v129) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)word_180879A6A,
            v118,
            v119,
            (__int64)v132,
            (__int64)&v129,
            (__int64)&v130,
            (__int64)&v128,
            (__int64)&v131,
            (__int64)&v133);
        }
        goto LABEL_5;
      }
      ClientEventLogCallback = CFecDecoder::Initialize(
                                 v117,
                                 (CRdpUdpStream *)((char *)this + 128),
                                 *((struct CRdpUdpTimer **)this + 33),
                                 *((struct IRdpUdpControlEvents **)this + 14));
      if ( ClientEventLogCallback < 0 )
      {
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v131 = "InitializeInstance";
          *(_QWORD *)&v133 = "FecDecoder initialization failed";
          LODWORD(v128) = 855;
          v132[0] = "Error HResult failed";
          v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v129) = ClientEventLogCallback;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v120,
            (unsigned int)byte_18087B36B,
            v121,
            v122,
            (__int64)v132,
            (__int64)&v129,
            (__int64)&v130,
            (__int64)&v128,
            (__int64)&v131,
            (__int64)&v133);
        }
        goto LABEL_5;
      }
      v123 = operator new(*((_QWORD *)this + 22) + 2050LL);
      *((_QWORD *)this + 69) = v123;
      if ( !v123 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v131 = "InitializeInstance";
          *(_QWORD *)&v133 = "SendBuffer allocation";
          LODWORD(v128) = 861;
          v132[0] = "Error condition failed";
          v130 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v129) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)&word_180879916,
            v24,
            v124,
            (__int64)v132,
            (__int64)&v129,
            (__int64)&v130,
            (__int64)&v128,
            (__int64)&v131,
            (__int64)&v133);
        }
        goto LABEL_5;
      }
      goto LABEL_155;
    }
LABEL_134:
    *((_DWORD *)this + 33) = 2;
    goto LABEL_135;
  }
LABEL_155:
  if ( !*((_DWORD *)v15 + 6) )
    *((_DWORD *)this + 58) = 1;
LABEL_157:
  v11 = (char *)this - 64;
  if ( ClientEventLogCallback >= 0 )
    goto LABEL_128;
LABEL_158:
  if ( *((_DWORD *)v11 + 64) )
    CRdpUdpStream::LogUDPClientStateTransition(v11, 3);
  else
    CRdpUdpStream::LogUDPStateTransition(v11, 0, 8, 8, ClientEventLogCallback);
  v106 = (HMODULE)*((_QWORD *)this + 76);
  if ( v106 )
  {
    FreeLibrary(v106);
    *((_QWORD *)this + 76) = 0;
  }
LABEL_129:
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    LODWORD(v129) = *((_DWORD *)this + 74);
    *(_QWORD *)&v133 = "UDP Stream Initialization done";
    LODWORD(v128) = ClientEventLogCallback;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v106,
      (unsigned int)&byte_18087B5FF,
      v107,
      v108,
      (__int64)&v133,
      (__int64)&v129,
      (__int64)&v128);
  }
  return (unsigned int)ClientEventLogCallback;
}

```

## disassembly

```asm
0x18040c210  mov     rax, rsp
0x18040c213  mov     [rax+10h], rbx
0x18040c217  push    rbp
0x18040c218  push    rsi
0x18040c219  push    rdi
0x18040c21a  push    r12
0x18040c21c  push    r13
0x18040c21e  push    r14
0x18040c220  push    r15
0x18040c222  lea     rbp, [rax-248h]
0x18040c229  sub     rsp, 310h
0x18040c230  movaps  xmmword ptr [rax-48h], xmm6
0x18040c234  mov     rax, cs:__security_cookie
0x18040c23b  xor     rax, rsp
0x18040c23e  mov     [rbp+240h+var_50], rax
0x18040c245  mov     rax, [rbp+240h+arg_20]
0x18040c24c  mov     rbx, r8
0x18040c24f  mov     [rbp+240h+var_2A8], r9
0x18040c253  mov     r13, rdx
0x18040c256  mov     qword ptr [rbp+240h+var_2C0], rbx
0x18040c25a  mov     rsi, rcx
0x18040c25d  mov     r14d, 2
0x18040c263  test    rax, rax
0x18040c266  jnz     loc_18040C30B
0x18040c26c  mov     eax, cs:dword_1808B5850
0x18040c272  mov     edi, 80004003h
0x18040c277  mov     ebx, edi
0x18040c279  cmp     eax, r14d
0x18040c27c  jbe     loc_18040C302
0x18040c282  lea     rax, aPsettingsIsNul; "pSettings is NULL"
0x18040c289  mov     dword ptr [rbp+240h+phModule], 204h
0x18040c290  mov     [rbp+240h+var_2A8], rax
0x18040c294  lea     r15, aInitializeinst_1; "InitializeInstance"
0x18040c29b  lea     rax, aErrorCondition; "Error condition failed"
0x18040c2a2  mov     [rsp+340h+var_2F0], r15
0x18040c2a7  mov     [rsp+340h+var_2E0], rax
0x18040c2ac  lea     r12, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18040c2b3  lea     rax, [rbp+240h+var_2A8]
0x18040c2b7  mov     [rsp+340h+var_2F8], rax
0x18040c2bc  lea     rdx, byte_18087A91F
0x18040c2c3  lea     rax, [rsp+340h+var_2F0]
0x18040c2c8  mov     [rsp+340h+var_300], rax
0x18040c2cd  lea     rax, [rbp+240h+phModule]
0x18040c2d1  mov     [rsp+340h+var_308], rax
0x18040c2d6  lea     rax, [rsp+340h+var_2D0]
0x18040c2db  mov     [rsp+340h+var_310], rax
0x18040c2e0  lea     rax, [rsp+340h+var_2E8]
0x18040c2e5  mov     [rsp+340h+var_318], rax
0x18040c2ea  lea     rax, [rsp+340h+var_2E0]
0x18040c2ef  mov     dword ptr [rsp+340h+var_2E8], edi
0x18040c2f3  mov     [rsp+340h+var_2D0], r12
0x18040c2f8  mov     [rsp+340h+var_320], rax
0x18040c2fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18040c302  lea     rax, [rsi-40h]
0x18040c306  jmp     loc_18040D771
0x18040c30b  cmp     dword ptr [rax+8], 0
0x18040c30f  lea     r15, aInitializeinst_1; "InitializeInstance"
0x18040c316  lea     r12, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18040c31d  jnz     loc_18040C62E
0x18040c323  mov     edi, 80004003h
0x18040c328  test    r13, r13
0x18040c32b  jnz     short loc_18040C3AA
0x18040c32d  mov     eax, cs:dword_1808B5850
0x18040c333  cmp     eax, r14d
0x18040c336  jbe     short loc_18040C3AA
0x18040c338  mov     eax, [rcx+80h]
0x18040c33e  lea     rdx, qword_18087B018
0x18040c345  mov     dword ptr [rsp+340h+var_2E8], eax
0x18040c349  lea     rax, aStreamworkerIs; "StreamWorker is invalid"
0x18040c350  mov     [rsp+340h+var_2D8], rax
0x18040c355  lea     rax, [rsp+340h+var_2E8]
0x18040c35a  mov     [rsp+340h+var_2F8], rax
0x18040c35f  lea     rax, [rsp+340h+var_2E0]
0x18040c364  mov     [rsp+340h+var_300], rax
0x18040c369  lea     rax, [rbp+240h+phModule]
0x18040c36d  mov     [rsp+340h+var_308], rax
0x18040c372  lea     rax, [rsp+340h+var_2D0]
0x18040c377  mov     [rsp+340h+var_310], rax
0x18040c37c  lea     rax, [rsp+340h+var_2F0]
0x18040c381  mov     [rsp+340h+var_318], rax
0x18040c386  lea     rax, [rsp+340h+var_2D8]
0x18040c38b  mov     [rsp+340h+var_320], rax
0x18040c390  mov     [rsp+340h+var_2E0], r15
0x18040c395  mov     dword ptr [rbp+240h+phModule], 20Dh
0x18040c39c  mov     [rsp+340h+var_2D0], r12
0x18040c3a1  mov     dword ptr [rsp+340h+var_2F0], edi
0x18040c3a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18040c3aa  test    rbx, rbx
0x18040c3ad  jnz     short loc_18040C42C
0x18040c3af  mov     eax, cs:dword_1808B5850
0x18040c3b5  cmp     eax, r14d
0x18040c3b8  jbe     short loc_18040C42C
0x18040c3ba  mov     eax, [rsi+80h]
0x18040c3c0  lea     rdx, word_180879BD6
0x18040c3c7  mov     dword ptr [rsp+340h+var_2F0], eax
0x18040c3cb  lea     rax, aMSpendpointinf; "m_spEndpointInfo is invalid"
0x18040c3d2  mov     [rsp+340h+var_2D0], rax
0x18040c3d7  lea     rax, [rsp+340h+var_2F0]
0x18040c3dc  mov     [rsp+340h+var_2F8], rax
0x18040c3e1  lea     rax, [rsp+340h+var_2D8]
0x18040c3e6  mov     [rsp+340h+var_300], rax
0x18040c3eb  lea     rax, [rsp+340h+var_2E8]
0x18040c3f0  mov     [rsp+340h+var_308], rax
0x18040c3f5  lea     rax, [rsp+340h+var_2E0]
0x18040c3fa  mov     [rsp+340h+var_310], rax
0x18040c3ff  lea     rax, [rbp+240h+phModule]
0x18040c403  mov     [rsp+340h+var_318], rax
0x18040c408  lea     rax, [rsp+340h+var_2D0]
0x18040c40d  mov     [rsp+340h+var_320], rax
0x18040c412  mov     [rsp+340h+var_2D8], r15
0x18040c417  mov     dword ptr [rsp+340h+var_2E8], 211h
0x18040c41f  mov     [rsp+340h+var_2E0], r12
0x18040c424  mov     dword ptr [rbp+240h+phModule], edi
0x18040c427  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18040c42c  mov     rax, [rbp+240h+var_2A8]
0x18040c430  test    rax, rax
0x18040c433  jnz     loc_18040C4BA
0x18040c439  mov     eax, cs:dword_1808B5850
0x18040c43f  cmp     eax, r14d
0x18040c442  jbe     short loc_18040C4B6
0x18040c444  mov     eax, [rsi+80h]
0x18040c44a  lea     rdx, byte_1808797CB
0x18040c451  mov     dword ptr [rsp+340h+var_2F0], eax
0x18040c455  lea     rax, aMSpconnectionI; "m_spConnection is invalid"
0x18040c45c  mov     [rsp+340h+var_2D0], rax
0x18040c461  lea     rax, [rsp+340h+var_2F0]
0x18040c466  mov     [rsp+340h+var_2F8], rax
0x18040c46b  lea     rax, [rsp+340h+var_2D8]
0x18040c470  mov     [rsp+340h+var_300], rax
0x18040c475  lea     rax, [rsp+340h+var_2E8]
0x18040c47a  mov     [rsp+340h+var_308], rax
0x18040c47f  lea     rax, [rsp+340h+var_2E0]
0x18040c484  mov     [rsp+340h+var_310], rax
0x18040c489  lea     rax, [rbp+240h+phModule]
0x18040c48d  mov     [rsp+340h+var_318], rax
0x18040c492  lea     rax, [rsp+340h+var_2D0]
0x18040c497  mov     [rsp+340h+var_320], rax
0x18040c49c  mov     [rsp+340h+var_2D8], r15
0x18040c4a1  mov     dword ptr [rsp+340h+var_2E8], 215h
0x18040c4a9  mov     [rsp+340h+var_2E0], r12
0x18040c4ae  mov     dword ptr [rbp+240h+phModule], edi
0x18040c4b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18040c4b6  mov     rax, [rbp+240h+var_2A8]
0x18040c4ba  test    r13, r13
0x18040c4bd  jnz     short loc_18040C536
0x18040c4bf  mov     eax, cs:dword_1808B5850
0x18040c4c5  mov     ebx, edi
0x18040c4c7  cmp     eax, r14d
0x18040c4ca  jbe     loc_18040C302
0x18040c4d0  lea     rax, aPworkerIsNull; "pWorker is NULL"
0x18040c4d7  mov     [rsp+340h+var_2E0], r15
0x18040c4dc  mov     [rsp+340h+var_2D8], rax
0x18040c4e1  lea     rdx, byte_1808794CF
0x18040c4e8  lea     rax, aErrorCondition; "Error condition failed"
0x18040c4ef  mov     dword ptr [rsp+340h+var_2F0], 218h
0x18040c4f7  mov     [rbp+240h+var_2A8], rax
0x18040c4fb  lea     rax, [rsp+340h+var_2D8]
0x18040c500  mov     [rsp+340h+var_2F8], rax
0x18040c505  lea     rax, [rsp+340h+var_2E0]
0x18040c50a  mov     [rsp+340h+var_300], rax
0x18040c50f  lea     rax, [rsp+340h+var_2F0]
0x18040c514  mov     [rsp+340h+var_308], rax
0x18040c519  lea     rax, [rsp+340h+var_2D0]
0x18040c51e  mov     [rsp+340h+var_310], rax
0x18040c523  lea     rax, [rsp+340h+var_2E8]
0x18040c528  mov     [rsp+340h+var_318], rax
0x18040c52d  lea     rax, [rbp+240h+var_2A8]
0x18040c531  jmp     loc_18040C2EF
0x18040c536  test    rbx, rbx
0x18040c539  jnz     short loc_18040C5B2
0x18040c53b  mov     eax, cs:dword_1808B5850
0x18040c541  mov     ebx, edi
0x18040c543  cmp     eax, r14d
0x18040c546  jbe     loc_18040C302
0x18040c54c  lea     rax, aPendpointinfoI; "pEndpointInfo is NULL"
0x18040c553  mov     [rsp+340h+var_2E0], r15
0x18040c558  mov     [rsp+340h+var_2D8], rax
0x18040c55d  lea     rdx, word_180879DAE
0x18040c564  lea     rax, aErrorCondition; "Error condition failed"
0x18040c56b  mov     dword ptr [rsp+340h+var_2F0], 219h
0x18040c573  mov     [rbp+240h+var_2A8], rax
0x18040c577  lea     rax, [rsp+340h+var_2D8]
0x18040c57c  mov     [rsp+340h+var_2F8], rax
0x18040c581  lea     rax, [rsp+340h+var_2E0]
0x18040c586  mov     [rsp+340h+var_300], rax
0x18040c58b  lea     rax, [rsp+340h+var_2F0]
0x18040c590  mov     [rsp+340h+var_308], rax
0x18040c595  lea     rax, [rsp+340h+var_2D0]
0x18040c59a  mov     [rsp+340h+var_310], rax
0x18040c59f  lea     rax, [rsp+340h+var_2E8]
0x18040c5a4  mov     [rsp+340h+var_318], rax
0x18040c5a9  lea     rax, [rbp+240h+var_2A8]
0x18040c5ad  jmp     loc_18040C2EF
0x18040c5b2  test    rax, rax
0x18040c5b5  jnz     short loc_18040C62E
0x18040c5b7  mov     eax, cs:dword_1808B5850
0x18040c5bd  mov     ebx, edi
0x18040c5bf  cmp     eax, r14d
0x18040c5c2  jbe     loc_18040C302
0x18040c5c8  lea     rax, aPsocketIsNull; "pSocket is NULL"
0x18040c5cf  mov     [rsp+340h+var_2E0], r15
0x18040c5d4  mov     [rsp+340h+var_2D8], rax
0x18040c5d9  lea     rdx, word_18087B11A
0x18040c5e0  lea     rax, aErrorCondition; "Error condition failed"
0x18040c5e7  mov     dword ptr [rsp+340h+var_2F0], 21Ah
0x18040c5ef  mov     [rbp+240h+var_2A8], rax
0x18040c5f3  lea     rax, [rsp+340h+var_2D8]
0x18040c5f8  mov     [rsp+340h+var_2F8], rax
0x18040c5fd  lea     rax, [rsp+340h+var_2E0]
0x18040c602  mov     [rsp+340h+var_300], rax
0x18040c607  lea     rax, [rsp+340h+var_2F0]
0x18040c60c  mov     [rsp+340h+var_308], rax
0x18040c611  lea     rax, [rsp+340h+var_2D0]
0x18040c616  mov     [rsp+340h+var_310], rax
0x18040c61b  lea     rax, [rsp+340h+var_2E8]
0x18040c620  mov     [rsp+340h+var_318], rax
0x18040c625  lea     rax, [rbp+240h+var_2A8]
0x18040c629  jmp     loc_18040C2EF
0x18040c62e  lea     rcx, [rsi+5Ch]; this
0x18040c632  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x18040c637  lea     rbx, [rsi+30h]
0x18040c63b  cmp     r13, [rbx]
0x18040c63e  jz      short loc_18040C653
0x18040c640  mov     rcx, rbx; void *
0x18040c643  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x18040c648  mov     rcx, rbx
0x18040c64b  mov     [rbx], r13
0x18040c64e  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x18040c653  mov     rdi, qword ptr [rbp+240h+var_2C0]
0x18040c657  lea     rbx, [rsi+40h]
0x18040c65b  cmp     rdi, [rbx]
0x18040c65e  jz      short loc_18040C673
0x18040c660  mov     rcx, rbx; void *
0x18040c663  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x18040c668  mov     rcx, rbx
0x18040c66b  mov     [rbx], rdi
0x18040c66e  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x18040c673  mov     rdi, [rbp+240h+var_2A8]
0x18040c677  lea     rbx, [rsi+48h]
0x18040c67b  cmp     rdi, [rbx]
0x18040c67e  jz      short loc_18040C693
0x18040c680  mov     rcx, rbx; void *
0x18040c683  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x18040c688  mov     rcx, rbx
0x18040c68b  mov     [rbx], rdi
0x18040c68e  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x18040c693  lea     rcx, [rsi+5Ch]; this
0x18040c697  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18040c69c  mov     rdi, [rbp+240h+arg_20]
0x18040c6a3  lea     rcx, [rsi-40h]; this
0x18040c6a7  cmp     dword ptr [rdi+18h], 0
0x18040c6ab  jz      short loc_18040C6DD
0x18040c6ad  call    ?CreateClientEventLogCallback@CRdpUdpStream@@IEAAJXZ; CRdpUdpStream::CreateClientEventLogCallback(void)
0x18040c6b2  mov     ebx, eax
0x18040c6b4  test    eax, eax
0x18040c6b6  jns     short loc_18040C730
0x18040c6b8  mov     eax, cs:dword_1808B5850
0x18040c6be  cmp     eax, 4
0x18040c6c1  jbe     short loc_18040C72E
0x18040c6c3  mov     eax, [rsi+80h]
0x18040c6c9  lea     rdx, word_18087AD22
0x18040c6d0  mov     dword ptr [rsp+340h+var_2F0], eax
0x18040c6d4  lea     rax, aUdpStreamFaile; "UDP stream failed to create client stat"...
0x18040c6db  jmp     short loc_18040C70B
0x18040c6dd  call    ?CreateServerEventLogCallback@CRdpUdpStream@@IEAAJXZ; CRdpUdpStream::CreateServerEventLogCallback(void)
0x18040c6e2  mov     ebx, eax
0x18040c6e4  test    eax, eax
0x18040c6e6  jns     short loc_18040C730
0x18040c6e8  mov     eax, cs:dword_1808B5850
0x18040c6ee  cmp     eax, 4
0x18040c6f1  jbe     short loc_18040C72E
0x18040c6f3  mov     eax, [rsi+80h]
0x18040c6f9  lea     rdx, dword_180879734
0x18040c700  mov     dword ptr [rsp+340h+var_2F0], eax
0x18040c704  lea     rax, aUdpStreamFaile_0; "UDP stream failed to create server stat"...
0x18040c70b  mov     qword ptr [rbp+240h+var_2C0], rax
0x18040c70f  lea     rcx, dword_1808B5850
0x18040c716  lea     rax, [rsp+340h+var_2F0]
0x18040c71b  mov     [rsp+340h+var_318], rax
0x18040c720  lea     rax, [rbp+240h+var_2C0]
0x18040c724  mov     [rsp+340h+var_320], rax
0x18040c729  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18040c72e  xor     ebx, ebx
0x18040c730  xor     r9d, r9d; lpName
0x18040c733  xor     r8d, r8d; bInitialState
0x18040c736  xor     edx, edx; bManualReset
0x18040c738  xor     ecx, ecx; lpEventAttributes
0x18040c73a  call    cs:__imp_CreateEventW
0x18040c740  xor     ecx, ecx; this
0x18040c742  mov     [rsi+180h], rax
0x18040c749  test    rax, rax
0x18040c74c  jnz     loc_18040C7EF
0x18040c752  call    cs:__imp_GetLastError
0x18040c758  mov     ebx, eax
0x18040c75a  test    eax, eax
0x18040c75c  jle     short loc_18040C767
0x18040c75e  movzx   ebx, ax
0x18040c761  or      ebx, 80070000h
0x18040c767  mov     eax, cs:dword_1808B5850
0x18040c76d  cmp     eax, r14d
  ... truncated ...
```
