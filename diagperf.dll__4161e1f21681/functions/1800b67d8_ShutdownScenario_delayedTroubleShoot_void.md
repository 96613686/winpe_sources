# ShutdownScenario::delayedTroubleShoot(void *)

- ea: `0x1800b67d8`
- end: `0x1800b6dc9`
- name: `?delayedTroubleShoot@ShutdownScenario@@AEAAJPEAX@Z`
- size: `1521`
- prototype: `__int64 __fastcall(ShutdownScenario *__hidden this, void *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b580`

## callees

- `0x18001769c`
- `0x1800193d4`
- `0x18001a008`
- `0x1800282a4`
- `0x18002b1b0`
- `0x18003268c`
- `0x180034d78`
- `0x18003de84`
- `0x18003df28`
- `0x18003f7f4`
- `0x180043030`
- `0x18006be3c`
- `0x1800b5f00`
- `0x1800b6070`
- `0x1800b61b0`
- `0x1800b63f0`
- `0x1800b67d8`
- `0x1800b6dd0`
- `0x1800c94fc`
- `0x1800c96e0`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6838`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800b682e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800b682e`

## string_xrefs

- `0x1800b6851`: `\system32\wdi\LogFiles\ShutdownPerfDiagLogger.etl`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall ShutdownScenario::delayedTroubleShoot(ShutdownScenario *this, void *a2)
{
  size_t v2; // r9
  signed int LastError; // eax
  const unsigned __int16 *v4; // r8
  int v5; // ebx
  bool v6; // sf
  const unsigned __int16 *v8; // r8
  HINSTANCE v9; // rdx
  void **v10; // r9
  int v11; // ebx
  int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  const struct PerfDiagShutdown::CTraceContext *v14; // r8
  const unsigned __int16 *v15; // r9
  unsigned int v16; // ebx
  __int64 v17; // rdx
  char *v18; // rcx
  __int64 *v19; // rax
  int v20; // ebx
  int v21; // ebx
  struct PerfDiagShutdown::CPayloadDegradation *v22; // r9
  const struct PerfDiagShutdown::CPayloadDegradation *v23; // r9
  ShutdownScenario *v24; // rcx
  void *v25; // [rsp+28h] [rbp-8C0h]
  struct _GUID v26; // [rsp+30h] [rbp-8B8h] BYREF
  struct _EVENT_DESCRIPTOR *v27; // [rsp+40h] [rbp-8A8h] BYREF
  void **v28; // [rsp+48h] [rbp-8A0h] BYREF
  int v29; // [rsp+50h] [rbp-898h]
  int v30; // [rsp+54h] [rbp-894h]
  int v31; // [rsp+58h] [rbp-890h]
  int v32; // [rsp+5Ch] [rbp-88Ch]
  _OWORD v33[4]; // [rsp+60h] [rbp-888h] BYREF
  _OWORD v34[4]; // [rsp+A0h] [rbp-848h] BYREF
  _BYTE v35[80]; // [rsp+E0h] [rbp-808h] BYREF
  _BYTE v36[64]; // [rsp+130h] [rbp-7B8h] BYREF
  __int64 (__fastcall **v37)(_QWORD, HKEY *, LPCWSTR *); // [rsp+170h] [rbp-778h] BYREF
  int v38; // [rsp+178h] [rbp-770h]
  int v39; // [rsp+17Ch] [rbp-76Ch]
  int v40; // [rsp+180h] [rbp-768h]
  int v41; // [rsp+184h] [rbp-764h]
  int v42; // [rsp+188h] [rbp-760h]
  int v43; // [rsp+18Ch] [rbp-75Ch]
  char v44; // [rsp+194h] [rbp-754h] BYREF
  struct _EVENT_DESCRIPTOR Buffer[33]; // [rsp+6C0h] [rbp-228h] BYREF

  *(_QWORD *)v26.Data4 = &PerfDiagShutdown::CRuntimeInformationConfig::`vftable';
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemWindowsDirectoryW(&Buffer[0].Id, 0x104u) )
  {
    v5 = StringCchCatW(&Buffer[0].Id, 0x104u, L"\\system32\\wdi\\LogFiles\\ShutdownPerfDiagLogger.etl", v2);
    v6 = v5 < 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = v5 < 0;
  }
  if ( v6 )
  {
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return (unsigned int)v5;
  }
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Shutdown_LocatedCKCL_Info, Buffer, v4);
  if ( (int)Performance::RegistryTransferable<PerfDiagShutdown::CRuntimeInformationConfig>::readWriteImpl(v26.Data4, 0) < 0 )
  {
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return 2237009925LL;
  }
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Shutdown_LocatedPossibleDCL_Info, v27, v8);
  *(_QWORD *)&v26.Data1 = 0;
  memset(v33, 0, sizeof(v33));
  v11 = XPerfCore::XPerfCoreCreateAddInManager((XPerfCore *)hInstance, v9, &v26, v10);
  if ( v11 < 0
    || (v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v26.Data1 + 24LL))(*(_QWORD *)&v26.Data1, 0),
        v11 < 0)
    || (v11 = PerfDiagShutdown::CTraceContext::Open(
                (PerfDiagShutdown::CTraceContext *)v33,
                *(struct XPerfCore::IAddInManager **)&v26.Data1,
                &Buffer[0].Id,
                &v27->Id)) != 0 )
  {
    PerfDiagShutdown::CTraceContext::~CTraceContext((PerfDiagShutdown::CTraceContext *)v33);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v26);
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return (unsigned int)v11;
  }
  PerfDiagShutdown::CAnalysisContext::CAnalysisContext((PerfDiagShutdown::CAnalysisContext *)v36);
  v12 = Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(
          &v37,
          0);
  v16 = v12;
  if ( v12 == -2147024894 )
  {
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Shutdown_RestoringConfig_Info, v13);
    v38 = 5;
    v39 = 5;
    v40 = 5;
    v17 = 3;
    v41 = 3;
    v42 = 3;
    v43 = 3;
    v18 = &v44;
    v19 = qword_1800E9BB0;
    do
    {
      *(_OWORD *)v18 = *(_OWORD *)v19;
      *((_OWORD *)v18 + 1) = *((_OWORD *)v19 + 1);
      *((_OWORD *)v18 + 2) = *((_OWORD *)v19 + 2);
      *((_OWORD *)v18 + 3) = *((_OWORD *)v19 + 3);
      *((_OWORD *)v18 + 4) = *((_OWORD *)v19 + 4);
      *((_OWORD *)v18 + 5) = *((_OWORD *)v19 + 5);
      *((_OWORD *)v18 + 6) = *((_OWORD *)v19 + 6);
      *((_OWORD *)v18 + 7) = *((_OWORD *)v19 + 7);
      v18 += 128;
      v19 += 16;
      --v17;
    }
    while ( v17 );
    *(_OWORD *)v18 = *(_OWORD *)v19;
    *((_OWORD *)v18 + 1) = *((_OWORD *)v19 + 1);
    *((_OWORD *)v18 + 2) = *((_OWORD *)v19 + 2);
    *((_OWORD *)v18 + 3) = *((_OWORD *)v19 + 3);
    *((_OWORD *)v18 + 4) = *((_OWORD *)v19 + 4);
    *((_DWORD *)v18 + 20) = *((_DWORD *)v19 + 20);
    v20 = Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(
            &v37,
            1);
    if ( v20 < 0 )
      goto LABEL_18;
  }
  else if ( v12 < 0 )
  {
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Shutdown_LoadConfig_Failed,
      (const struct _EVENT_DESCRIPTOR *)(unsigned int)v12,
      0,
      v15);
    PerfDiagShutdown::CAnalysisContext::~CAnalysisContext((PerfDiagShutdown::CAnalysisContext *)v36);
    PerfDiagShutdown::CTraceContext::~CTraceContext((PerfDiagShutdown::CTraceContext *)v33);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v26);
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return v16;
  }
  v20 = PerfDiagShutdown::DetectRegressions(
          (PerfDiagShutdown *)v36,
          (struct PerfDiagShutdown::CAnalysisContext *)v33,
          v14);
  if ( (unsigned int)v20 > 1 )
  {
LABEL_18:
    PerfDiagShutdown::CAnalysisContext::~CAnalysisContext((PerfDiagShutdown::CAnalysisContext *)v36);
    PerfDiagShutdown::CTraceContext::~CTraceContext((PerfDiagShutdown::CTraceContext *)v33);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v26);
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return (unsigned int)v20;
  }
  memset_0(v35, 0, 0x4Cu);
  memset(v34, 0, 48);
  v28 = &PerfDiagShutdown::CSeverityConfig::`vftable';
  v29 = 60;
  v30 = 120;
  v31 = 30;
  v32 = 60;
  v21 = Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(
          (__int64 (__fastcall ***)(_QWORD, HKEY *, LPCWSTR *))&v28,
          0);
  if ( v21 >= 0
    && (v21 = PerfDiagShutdown::FillInOutputRecords(
                (PerfDiagShutdown *)v36,
                (struct PerfDiagShutdown::CAnalysisContext *)v35,
                (struct PerfDiagShutdown::CPayloadInfo *)v34,
                v22),
        v21 >= 0)
    && (v21 = PerfDiagShutdown::OutputSqmEventLog(
                (PerfDiagShutdown *)&v28,
                (const struct PerfDiagShutdown::CSeverityConfig *)v35,
                (const struct PerfDiagShutdown::CPayloadInfo *)v34,
                v23),
        v21 >= 0) )
  {
    ShutdownScenario::detectResolution(
      v24,
      (const struct PerfDiagShutdown::CAnalysisContext *)v36,
      (const struct PerfDiagShutdown::CPayloadInfo *)v35,
      (const struct PerfDiagShutdown::CPayloadDegradation *)v34,
      (const struct PerfDiagShutdown::CSeverityConfig *)&v28,
      v25);
    XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples::~CProcessorSamples((XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples *)v34);
    PerfDiagShutdown::CAnalysisContext::~CAnalysisContext((PerfDiagShutdown::CAnalysisContext *)v36);
    PerfDiagShutdown::CTraceContext::~CTraceContext((PerfDiagShutdown::CTraceContext *)v33);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v26);
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return 0;
  }
  else
  {
    XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples::~CProcessorSamples((XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples *)v34);
    PerfDiagShutdown::CAnalysisContext::~CAnalysisContext((PerfDiagShutdown::CAnalysisContext *)v36);
    PerfDiagShutdown::CTraceContext::~CTraceContext((PerfDiagShutdown::CTraceContext *)v33);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v26);
    ATL::CStringData::Release((ATL::CStringData *)&v27[-2].Keyword);
    return (unsigned int)v21;
  }
}

```

## disassembly

```asm
0x1800b67d8  push    rbx
0x1800b67da  sub     rsp, 8E0h
0x1800b67e1  mov     rax, cs:__security_cookie
0x1800b67e8  xor     rax, rsp
0x1800b67eb  mov     [rsp+8E8h+var_18], rax
0x1800b67f3  lea     rax, ??_7CRuntimeInformationConfig@PerfDiagShutdown@@6B@; const PerfDiagShutdown::CRuntimeInformationConfig::`vftable'
0x1800b67fa  mov     qword ptr [rsp+8E8h+var_8B8.Data4], rax
0x1800b67ff  lea     rcx, [rsp+8E8h+var_8A8]
0x1800b6804  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800b6809  nop
0x1800b680a  xor     edx, edx; Val
0x1800b680c  mov     r8d, 208h; Size
0x1800b6812  lea     rcx, [rsp+8E8h+Buffer]; void *
0x1800b681a  call    memset_0
0x1800b681f  mov     ebx, 104h
0x1800b6824  mov     edx, ebx; uSize
0x1800b6826  lea     rcx, [rsp+8E8h+Buffer]; lpBuffer
0x1800b682e  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800b6834  test    eax, eax
0x1800b6836  jnz     short loc_1800B6851
0x1800b6838  call    cs:__imp_GetLastError
0x1800b683e  mov     ebx, eax
0x1800b6840  test    eax, eax
0x1800b6842  jle     short loc_1800B684D
0x1800b6844  movzx   ebx, ax
0x1800b6847  or      ebx, 80070000h
0x1800b684d  test    ebx, ebx
0x1800b684f  jmp     short loc_1800B686C
0x1800b6851  lea     r8, aSystem32WdiLog; "\\system32\\wdi\\LogFiles\\ShutdownPerf"...
0x1800b6858  mov     rdx, rbx; unsigned __int64
0x1800b685b  lea     rcx, [rsp+8E8h+Buffer]; unsigned __int16 *
0x1800b6863  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b6868  mov     ebx, eax
0x1800b686a  test    eax, eax
0x1800b686c  jns     short loc_1800B6883
0x1800b686e  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6873  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6877  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b687c  mov     eax, ebx
0x1800b687e  jmp     loc_1800B6DAF
0x1800b6883  lea     rdx, [rsp+8E8h+Buffer]; struct _EVENT_DESCRIPTOR *
0x1800b688b  lea     rcx, PDEvt_Shutdown_LocatedCKCL_Info; this
0x1800b6892  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ushort const *)
0x1800b6897  xor     edx, edx
0x1800b6899  lea     rcx, [rsp+8E8h+var_8B8.Data4]
0x1800b689e  call    ?readWriteImpl@?$RegistryTransferable@VCRuntimeInformationConfig@PerfDiagShutdown@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagShutdown::CRuntimeInformationConfig>::readWriteImpl(bool)
0x1800b68a3  test    eax, eax
0x1800b68a5  jns     short loc_1800B68BF
0x1800b68a7  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b68ac  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b68b0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b68b5  mov     eax, 85561005h
0x1800b68ba  jmp     loc_1800B6DAF
0x1800b68bf  mov     rdx, [rsp+8E8h+var_8A8]; struct _EVENT_DESCRIPTOR *
0x1800b68c4  lea     rcx, PDEvt_Shutdown_LocatedPossibleDCL_Info; this
0x1800b68cb  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ushort const *)
0x1800b68d0  mov     qword ptr [rsp+8E8h+var_8B8.Data1], 0
0x1800b68d9  xorps   xmm0, xmm0
0x1800b68dc  movdqa  [rsp+8E8h+var_888], xmm0
0x1800b68e2  xorps   xmm1, xmm1
0x1800b68e5  movdqa  [rsp+8E8h+var_878], xmm1
0x1800b68eb  movdqa  [rsp+8E8h+var_868], xmm0
0x1800b68f4  movdqa  [rsp+8E8h+var_858], xmm1
0x1800b68fd  lea     r8, [rsp+8E8h+var_8B8]; struct _GUID *
0x1800b6902  mov     rcx, cs:hInstance; this
0x1800b6909  call    ?XPerfCoreCreateAddInManager@XPerfCore@@YAJPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z; XPerfCore::XPerfCoreCreateAddInManager(HINSTANCE__ *,_GUID const &,void * *)
0x1800b690e  mov     ebx, eax
0x1800b6910  test    eax, eax
0x1800b6912  jns     short loc_1800B693F
0x1800b6914  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6919  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b691e  nop
0x1800b691f  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6924  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6929  nop
0x1800b692a  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b692f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6933  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6938  mov     eax, ebx
0x1800b693a  jmp     loc_1800B6DAF
0x1800b693f  mov     rcx, qword ptr [rsp+8E8h+var_8B8.Data1]
0x1800b6944  mov     rax, [rcx]
0x1800b6947  xor     edx, edx
0x1800b6949  mov     rax, [rax+18h]
0x1800b694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6952  mov     ebx, eax
0x1800b6954  test    eax, eax
0x1800b6956  jns     short loc_1800B6983
0x1800b6958  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b695d  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6962  nop
0x1800b6963  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6968  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b696d  nop
0x1800b696e  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6973  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6977  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b697c  mov     eax, ebx
0x1800b697e  jmp     loc_1800B6DAF
0x1800b6983  mov     r9, [rsp+8E8h+var_8A8]; unsigned __int16 *
0x1800b6988  lea     r8, [rsp+8E8h+Buffer]; unsigned __int16 *
0x1800b6990  mov     rdx, qword ptr [rsp+8E8h+var_8B8.Data1]; struct XPerfCore::IAddInManager *
0x1800b6995  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b699a  call    ?Open@CTraceContext@PerfDiagShutdown@@QEAAJPEAUIAddInManager@XPerfCore@@PEBG1@Z; PerfDiagShutdown::CTraceContext::Open(XPerfCore::IAddInManager *,ushort const *,ushort const *)
0x1800b699f  mov     ebx, eax
0x1800b69a1  test    eax, eax
0x1800b69a3  jz      short loc_1800B69D0
0x1800b69a5  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b69aa  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b69af  nop
0x1800b69b0  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b69b5  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b69ba  nop
0x1800b69bb  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b69c0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b69c4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b69c9  mov     eax, ebx
0x1800b69cb  jmp     loc_1800B6DAF
0x1800b69d0  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b69d8  call    ??0CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::CAnalysisContext(void)
0x1800b69dd  nop
0x1800b69de  xor     edx, edx
0x1800b69e0  lea     rcx, [rsp+8E8h+var_778]
0x1800b69e8  call    ?readWriteImpl@?$RegistryTransferable@V?$CRegistryConfigBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@@PerfDiagBoot@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(bool)
0x1800b69ed  mov     ebx, eax
0x1800b69ef  cmp     eax, 80070002h
0x1800b69f4  jnz     loc_1800B6B13
0x1800b69fa  lea     rcx, PDEvt_Shutdown_RestoringConfig_Info; this
0x1800b6a01  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x1800b6a06  mov     eax, 5
0x1800b6a0b  mov     [rsp+8E8h+var_770], eax
0x1800b6a12  mov     [rsp+8E8h+var_76C], eax
0x1800b6a19  mov     [rsp+8E8h+var_768], eax
0x1800b6a20  lea     edx, [rax-2]
0x1800b6a23  mov     [rsp+8E8h+var_764], edx
0x1800b6a2a  mov     [rsp+8E8h+var_760], edx
0x1800b6a31  mov     [rsp+8E8h+var_75C], edx
0x1800b6a38  lea     rcx, [rsp+8E8h+var_754]
0x1800b6a40  lea     rax, qword_1800E9BB0
0x1800b6a47  lea     r8d, [rdx+7Dh]
0x1800b6a4b  movups  xmm0, xmmword ptr [rax]
0x1800b6a4e  movups  xmmword ptr [rcx], xmm0
0x1800b6a51  movups  xmm1, xmmword ptr [rax+10h]
0x1800b6a55  movups  xmmword ptr [rcx+10h], xmm1
0x1800b6a59  movups  xmm0, xmmword ptr [rax+20h]
0x1800b6a5d  movups  xmmword ptr [rcx+20h], xmm0
0x1800b6a61  movups  xmm1, xmmword ptr [rax+30h]
0x1800b6a65  movups  xmmword ptr [rcx+30h], xmm1
0x1800b6a69  movups  xmm0, xmmword ptr [rax+40h]
0x1800b6a6d  movups  xmmword ptr [rcx+40h], xmm0
0x1800b6a71  movups  xmm1, xmmword ptr [rax+50h]
0x1800b6a75  movups  xmmword ptr [rcx+50h], xmm1
0x1800b6a79  movups  xmm0, xmmword ptr [rax+60h]
0x1800b6a7d  movups  xmmword ptr [rcx+60h], xmm0
0x1800b6a81  movups  xmm1, xmmword ptr [rax+70h]
0x1800b6a85  movups  xmmword ptr [rcx+70h], xmm1
0x1800b6a89  add     rcx, r8
0x1800b6a8c  add     rax, r8
0x1800b6a8f  sub     rdx, 1
0x1800b6a93  jnz     short loc_1800B6A4B
0x1800b6a95  movups  xmm0, xmmword ptr [rax]
0x1800b6a98  movups  xmmword ptr [rcx], xmm0
0x1800b6a9b  movups  xmm1, xmmword ptr [rax+10h]
0x1800b6a9f  movups  xmmword ptr [rcx+10h], xmm1
0x1800b6aa3  movups  xmm0, xmmword ptr [rax+20h]
0x1800b6aa7  movups  xmmword ptr [rcx+20h], xmm0
0x1800b6aab  movups  xmm1, xmmword ptr [rax+30h]
0x1800b6aaf  movups  xmmword ptr [rcx+30h], xmm1
0x1800b6ab3  movups  xmm0, xmmword ptr [rax+40h]
0x1800b6ab7  movups  xmmword ptr [rcx+40h], xmm0
0x1800b6abb  mov     eax, [rax+50h]
0x1800b6abe  mov     [rcx+50h], eax
0x1800b6ac1  mov     dl, 1
0x1800b6ac3  lea     rcx, [rsp+8E8h+var_778]
0x1800b6acb  call    ?readWriteImpl@?$RegistryTransferable@V?$CRegistryConfigBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@@PerfDiagBoot@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(bool)
0x1800b6ad0  mov     ebx, eax
0x1800b6ad2  test    eax, eax
0x1800b6ad4  jns     loc_1800B6B62
0x1800b6ada  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6ae2  call    ??1CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::~CAnalysisContext(void)
0x1800b6ae7  nop
0x1800b6ae8  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6aed  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6af2  nop
0x1800b6af3  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6af8  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6afd  nop
0x1800b6afe  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6b03  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6b07  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6b0c  mov     eax, ebx
0x1800b6b0e  jmp     loc_1800B6DAF
0x1800b6b13  test    ebx, ebx
0x1800b6b15  jns     short loc_1800B6B62
0x1800b6b17  xor     r8d, r8d; unsigned int
0x1800b6b1a  mov     edx, ebx; struct _EVENT_DESCRIPTOR *
0x1800b6b1c  lea     rcx, PDEvt_Shutdown_LoadConfig_Failed; this
0x1800b6b23  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b6b28  nop
0x1800b6b29  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6b31  call    ??1CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::~CAnalysisContext(void)
0x1800b6b36  nop
0x1800b6b37  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6b3c  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6b41  nop
0x1800b6b42  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6b47  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6b4c  nop
0x1800b6b4d  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6b52  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6b56  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6b5b  mov     eax, ebx
0x1800b6b5d  jmp     loc_1800B6DAF
0x1800b6b62  lea     rdx, [rsp+8E8h+var_888]; struct PerfDiagShutdown::CAnalysisContext *
0x1800b6b67  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6b6f  call    ?DetectRegressions@PerfDiagShutdown@@YAJAEAUCAnalysisContext@1@AEBVCTraceContext@1@_N@Z; PerfDiagShutdown::DetectRegressions(PerfDiagShutdown::CAnalysisContext &,PerfDiagShutdown::CTraceContext const &,bool)
0x1800b6b74  mov     ebx, eax
0x1800b6b76  cmp     eax, 1
0x1800b6b79  jbe     short loc_1800B6BB4
0x1800b6b7b  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6b83  call    ??1CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::~CAnalysisContext(void)
0x1800b6b88  nop
0x1800b6b89  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6b8e  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6b93  nop
0x1800b6b94  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6b99  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6b9e  nop
0x1800b6b9f  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6ba4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6ba8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6bad  mov     eax, ebx
0x1800b6baf  jmp     loc_1800B6DAF
0x1800b6bb4  xor     edx, edx; Val
0x1800b6bb6  lea     r8d, [rdx+4Ch]; Size
0x1800b6bba  lea     rcx, [rsp+8E8h+var_808]; void *
0x1800b6bc2  call    memset_0
0x1800b6bc7  xorps   xmm0, xmm0
0x1800b6bca  movdqu  [rsp+8E8h+var_848], xmm0
0x1800b6bd3  xorps   xmm1, xmm1
0x1800b6bd6  movdqu  [rsp+8E8h+var_838], xmm1
0x1800b6bdf  movdqu  [rsp+8E8h+var_828], xmm0
0x1800b6be8  lea     rax, ??_7CSeverityConfig@PerfDiagShutdown@@6B@; const PerfDiagShutdown::CSeverityConfig::`vftable'
0x1800b6bef  mov     [rsp+8E8h+var_8A0], rax
0x1800b6bf4  mov     eax, 3Ch ; '<'
0x1800b6bf9  mov     [rsp+8E8h+var_898], eax
0x1800b6bfd  mov     [rsp+8E8h+var_894], 78h ; 'x'
0x1800b6c05  mov     [rsp+8E8h+var_890], 1Eh
0x1800b6c0d  mov     [rsp+8E8h+var_88C], eax
0x1800b6c11  xor     edx, edx
0x1800b6c13  lea     rcx, [rsp+8E8h+var_8A0]
0x1800b6c18  call    ?readWriteImpl@?$RegistryTransferable@V?$CRegistryConfigBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@@PerfDiagBoot@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(bool)
0x1800b6c1d  mov     ebx, eax
0x1800b6c1f  test    eax, eax
0x1800b6c21  jns     short loc_1800B6C6A
0x1800b6c23  lea     rcx, [rsp+8E8h+var_848]; this
0x1800b6c2b  call    ??1CProcessorSamples@CSampledProfileInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples::~CProcessorSamples(void)
0x1800b6c30  nop
0x1800b6c31  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6c39  call    ??1CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::~CAnalysisContext(void)
0x1800b6c3e  nop
0x1800b6c3f  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6c44  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6c49  nop
0x1800b6c4a  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6c4f  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6c54  nop
0x1800b6c55  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6c5a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6c5e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6c63  mov     eax, ebx
0x1800b6c65  jmp     loc_1800B6DAF
0x1800b6c6a  lea     r8, [rsp+8E8h+var_848]; struct PerfDiagShutdown::CPayloadInfo *
0x1800b6c72  lea     rdx, [rsp+8E8h+var_808]; struct PerfDiagShutdown::CAnalysisContext *
0x1800b6c7a  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6c82  call    ?FillInOutputRecords@PerfDiagShutdown@@YAJAEAUCAnalysisContext@1@AEAUCPayloadInfo@1@AEAUCPayloadDegradation@1@@Z; PerfDiagShutdown::FillInOutputRecords(PerfDiagShutdown::CAnalysisContext &,PerfDiagShutdown::CPayloadInfo &,PerfDiagShutdown::CPayloadDegradation &)
0x1800b6c87  mov     ebx, eax
0x1800b6c89  test    eax, eax
0x1800b6c8b  jns     short loc_1800B6CD4
0x1800b6c8d  lea     rcx, [rsp+8E8h+var_848]; this
0x1800b6c95  call    ??1CProcessorSamples@CSampledProfileInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::CSampledProfileInfoSource::CProcessorSamples::~CProcessorSamples(void)
0x1800b6c9a  nop
0x1800b6c9b  lea     rcx, [rsp+8E8h+var_7B8]; this
0x1800b6ca3  call    ??1CAnalysisContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CAnalysisContext::~CAnalysisContext(void)
0x1800b6ca8  nop
0x1800b6ca9  lea     rcx, [rsp+8E8h+var_888]; this
0x1800b6cae  call    ??1CTraceContext@PerfDiagShutdown@@QEAA@XZ; PerfDiagShutdown::CTraceContext::~CTraceContext(void)
0x1800b6cb3  nop
0x1800b6cb4  lea     rcx, [rsp+8E8h+var_8B8]
0x1800b6cb9  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x1800b6cbe  nop
0x1800b6cbf  mov     rcx, [rsp+8E8h+var_8A8]
0x1800b6cc4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800b6cc8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800b6ccd  mov     eax, ebx
0x1800b6ccf  jmp     loc_1800B6DAF
0x1800b6cd4  lea     r8, [rsp+8E8h+var_848]; struct PerfDiagShutdown::CPayloadInfo *
0x1800b6cdc  lea     rdx, [rsp+8E8h+var_808]; struct PerfDiagShutdown::CSeverityConfig *
0x1800b6ce4  lea     rcx, [rsp+8E8h+var_8A0]; this
0x1800b6ce9  call    ?OutputSqmEventLog@PerfDiagShutdown@@YAJAEBVCSeverityConfig@1@AEBUCPayloadInfo@1@AEBUCPayloadDegradation@1@@Z; PerfDiagShutdown::OutputSqmEventLog(PerfDiagShutdown::CSeverityConfig const &,PerfDiagShutdown::CPayloadInfo const &,PerfDiagShutdown::CPayloadDegradation const &)
  ... truncated ...
```
