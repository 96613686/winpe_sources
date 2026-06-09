# BootScenario::PerformTroubleshooting(void *)

- ea: `0x1800279d8`
- end: `0x18002829e`
- name: `?PerformTroubleshooting@BootScenario@@AEAAJPEAX@Z`
- size: `2246`
- prototype: `__int64 __fastcall(BootScenario *__hidden this, void *)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b4f00`

## callees

- `0x18001782c`
- `0x180017948`
- `0x1800193d4`
- `0x1800279d8`
- `0x1800282a4`
- `0x180031e34`
- `0x18003268c`
- `0x180032ab0`
- `0x180035228`
- `0x180039298`
- `0x18003d1a0`
- `0x18003de84`
- `0x18003df28`
- `0x1800410cc`
- `0x180041a40`
- `0x180041e28`
- `0x180041fd8`
- `0x1800421b8`
- `0x180043030`
- `0x1800b457c`
- `0x1800b4658`
- `0x1800b46d8`
- `0x1800b49d4`
- `0x1800c2950`
- `0x1800c29ac`
- `0x1800c2df8`
- `0x1800c3350`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800cf140`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002803e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002803e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180027a2e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180027c82`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002804e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180027a2e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180027c82`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002804e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180027ad9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180027ad9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180027ec3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180027ec3`
- `KERNEL32!LocalFree` at `0x180027f4a`
- `KERNEL32!LocalFree` at `0x180027f4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall BootScenario::PerformTroubleshooting(BootScenario *this, void *a2)
{
  HANDLE CurrentThread; // rax
  int v4; // ebx
  HINSTANCE v5; // rdx
  void **v6; // r9
  int v7; // edi
  size_t v8; // r9
  int Error; // eax
  int v11; // edi
  const unsigned __int16 *v12; // r9
  unsigned int v13; // edi
  HANDLE v14; // rax
  int *v15; // rax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  const struct _EVENT_DESCRIPTOR *v17; // rdi
  const struct PerfDiagBoot::CTraceContext *v18; // r9
  const unsigned __int16 *v19; // r9
  unsigned int *v20; // r14
  int UserSIDFromTrace; // edi
  const struct PerfDiagBoot::CTraceContext *v22; // r9
  signed int LastError; // eax
  unsigned int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // rcx
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  const struct PerfDiagBoot::CTraceContext *v28; // r9
  const struct _EVENT_DESCRIPTOR *v29; // rdi
  const unsigned __int16 *v30; // r9
  HANDLE v31; // rax
  int v32; // ebx
  struct PerfDiagBoot::CPayloadDegradation *v33; // r9
  const struct PerfDiagBoot::CPayloadDegradation *v34; // r9
  bool v35; // [rsp+20h] [rbp-1268h]
  struct PerfDiagBoot::CSeverityConfig *v36; // [rsp+20h] [rbp-1268h]
  unsigned int v37; // [rsp+28h] [rbp-1260h]
  void *v38; // [rsp+28h] [rbp-1260h]
  int v39; // [rsp+30h] [rbp-1258h] BYREF
  struct _GUID v40; // [rsp+38h] [rbp-1250h] BYREF
  PSID Sid; // [rsp+48h] [rbp-1240h] BYREF
  void **v42; // [rsp+50h] [rbp-1238h] BYREF
  int v43; // [rsp+58h] [rbp-1230h]
  int v44; // [rsp+5Ch] [rbp-122Ch]
  int v45; // [rsp+60h] [rbp-1228h]
  int v46; // [rsp+64h] [rbp-1224h]
  _BYTE v47[24]; // [rsp+68h] [rbp-1220h] BYREF
  unsigned int v48[4]; // [rsp+80h] [rbp-1208h] BYREF
  __int64 v49; // [rsp+90h] [rbp-11F8h]
  _BYTE v50[144]; // [rsp+110h] [rbp-1178h] BYREF
  _BYTE v51[240]; // [rsp+1A0h] [rbp-10E8h] BYREF
  _BYTE v52[64]; // [rsp+290h] [rbp-FF8h] BYREF
  _BYTE v53[8]; // [rsp+2D0h] [rbp-FB8h] BYREF
  _QWORD v54[123]; // [rsp+2D8h] [rbp-FB0h] BYREF
  _BYTE v55[1256]; // [rsp+6B0h] [rbp-BD8h] BYREF
  _BYTE v56[8]; // [rsp+B98h] [rbp-6F0h] BYREF
  _QWORD v57[42]; // [rsp+BA0h] [rbp-6E8h] BYREF
  _BYTE v58[600]; // [rsp+CF0h] [rbp-598h] BYREF
  PSID v59; // [rsp+F48h] [rbp-340h]
  __int64 v60; // [rsp+F50h] [rbp-338h] BYREF
  _BYTE v61[32]; // [rsp+F58h] [rbp-330h] BYREF
  int v62; // [rsp+F78h] [rbp-310h]
  int v63; // [rsp+F7Ch] [rbp-30Ch]
  FILETIME v64; // [rsp+F80h] [rbp-308h]
  _BYTE v65[192]; // [rsp+F90h] [rbp-2F8h] BYREF
  WCHAR Buffer[264]; // [rsp+1050h] [rbp-238h] BYREF

  Sid = 0;
  *(_QWORD *)v40.Data4 = 0;
  CurrentThread = GetCurrentThread();
  v4 = 0x20000;
  if ( !SetThreadPriority(CurrentThread, 0x10000) )
    v4 = 0x7FFFFFFF;
  v39 = v4;
  *(_QWORD *)&v40.Data1 = 0;
  v7 = XPerfCore::XPerfCoreCreateAddInManager((XPerfCore *)hInstance, v5, &v40, v6);
  if ( v7 < 0
    || (v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v40.Data1 + 24LL))(*(_QWORD *)&v40.Data1, 0),
        v7 < 0)
    || ((memset_0(Buffer, 0, 0x208u), GetSystemDirectoryW(Buffer, 0x104u))
      ? (Error = StringCchCatW(Buffer, 0x104u, L"\\WDI\\LogFiles\\BootPerfDiagLogger.etl", v8))
      : (Error = ATL::AtlHresultFromLastError()),
        v7 = Error,
        Error < 0) )
  {
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
    return (unsigned int)v7;
  }
  PerfDiagBoot::CAnalysisContext::CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
  v11 = Performance::RegistryTransferable<PerfDiagBoot::CSharedRegistryConfig>::readWriteImpl(v61, 0);
  if ( v11 < 0
    || (v11 = (*(__int64 (__fastcall **)(_QWORD *))(v54[0] + 16LL))(v54), v11 < 0)
    || (v11 = (*(__int64 (__fastcall **)(_QWORD *))(v57[0] + 16LL))(v57), v11 < 0) )
  {
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
    return (unsigned int)v11;
  }
  PerfDiagBoot::CTraceContext::CTraceContext((PerfDiagBoot::CTraceContext *)v48);
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( !*((_DWORD *)v12 - 4) )
    v12 = (const unsigned __int16 *)*((_QWORD *)this + 8);
  v13 = PerfDiagBoot::CTraceContext::Open(
          (PerfDiagBoot::CTraceContext *)v48,
          *(struct XPerfCore::IAddInManager **)&v40.Data1,
          Buffer,
          v12);
  if ( v13 )
  {
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    if ( *(_QWORD *)&v40.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v40.Data1 + 16LL))(*(_QWORD *)&v40.Data1);
    v14 = GetCurrentThread();
    if ( v4 != 0x7FFFFFFF )
      SetThreadPriority(v14, v4);
    return v13;
  }
  v15 = (int *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v49 + 192LL))(v49, v47);
  v62 = *v15;
  v63 = v15[1];
  LODWORD(v17) = PerfDiagBoot::Impl::getSystemScenarioArchivePath(v55);
  if ( (int)v17 < 0
    || (PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_ProcessingSystem_Start, v16),
        v17 = (const struct _EVENT_DESCRIPTOR *)(unsigned int)PerfDiagBoot::DetectRegressions(
                                                                (PerfDiagBoot *)v53,
                                                                (struct PerfDiagBoot::CSystemAnalysisContext *)v61,
                                                                (const struct PerfDiagBoot::CSharedRegistryConfig *)v48,
                                                                v18,
                                                                v35),
        PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_ProcessingSystem_Stop, v17, 0, v19),
        (unsigned int)v17 > 1) )
  {
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
    return (unsigned int)v17;
  }
  PerfDiagBoot::CTraceContext::CTraceContext((PerfDiagBoot::CTraceContext *)v50);
  if ( *(_DWORD *)(*((_QWORD *)this + 7) - 16LL) )
  {
    UserSIDFromTrace = PerfDiagBoot::CTraceContext::Open(
                         (PerfDiagBoot::CTraceContext *)v50,
                         *(struct XPerfCore::IAddInManager **)&v40.Data1,
                         Buffer,
                         *((const unsigned __int16 **)this + 8));
    if ( UserSIDFromTrace )
      goto LABEL_35;
    v20 = (unsigned int *)v50;
  }
  else
  {
    v20 = v48;
  }
  v64 = *(FILETIME *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v20 + 2) + 208LL))(
                       *((_QWORD *)v20 + 2),
                       v47);
  PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End = v64;
  UserSIDFromTrace = PerfDiagBoot::Impl::getUserSIDFromTrace(
                       (PerfDiagBoot::Impl *)&Sid,
                       (const struct _SID **)*((unsigned int *)this + 18),
                       (unsigned int)v48,
                       v22);
  if ( UserSIDFromTrace )
    goto LABEL_35;
  v59 = Sid;
  if ( !ConvertSidToStringSidW(Sid, (LPWSTR *)v40.Data4) )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v50);
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
    return v24;
  }
  v25 = (unsigned int)ATL::CSimpleStringT<unsigned short,0>::StringLength(*(_QWORD *)v40.Data4);
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v60, v26, v25);
  LocalFree(*(HLOCAL *)v40.Data4);
  *(_QWORD *)v40.Data4 = 0;
  UserSIDFromTrace = PerfDiagBoot::Impl::getUserScenarioArchivePath(v58, v60);
  if ( UserSIDFromTrace < 0 )
  {
LABEL_35:
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v50);
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
    return (unsigned int)UserSIDFromTrace;
  }
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_ProcessingUser_Start, v27);
  v29 = (const struct _EVENT_DESCRIPTOR *)(unsigned int)PerfDiagBoot::DetectRegressions(
                                                          (PerfDiagBoot *)v56,
                                                          (struct PerfDiagBoot::CUserAnalysisContext *)v61,
                                                          (const struct PerfDiagBoot::CSharedRegistryConfig *)v20,
                                                          v28,
                                                          *((_DWORD *)this + 18),
                                                          v37);
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_ProcessingUser_Stop, v29, 0, v30);
  if ( (unsigned int)v29 <= 1 )
  {
    memset_0(v65, 0, 0xB8u);
    PerfDiagBoot::CPayloadDegradation::CPayloadDegradation((PerfDiagBoot::CPayloadDegradation *)v51);
    v42 = &PerfDiagBoot::CSeverityConfig::`vftable';
    v43 = 60;
    v44 = 30;
    v45 = 120;
    v46 = 60;
    v32 = Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(
            &v42,
            0);
    if ( v32 >= 0
      && (v32 = PerfDiagBoot::FillInOutputRecords(
                  (PerfDiagBoot *)v52,
                  (struct PerfDiagBoot::CAnalysisContext *)v65,
                  (struct PerfDiagBoot::CPayloadInfo *)v51,
                  v33),
          v32 >= 0)
      && (v32 = PerfDiagBoot::OutputSqmEventLog(
                  (PerfDiagBoot *)&v42,
                  (const struct PerfDiagBoot::CSeverityConfig *)v65,
                  (const struct PerfDiagBoot::CPayloadInfo *)v51,
                  v34),
          v32 >= 0) )
    {
      PerfDiagBoot::DetectResolution(
        (PerfDiagBoot *)v52,
        (const struct PerfDiagBoot::CAnalysisContext *)v65,
        (const struct PerfDiagBoot::CPayloadInfo *)v51,
        (const struct PerfDiagBoot::CPayloadDegradation *)&v42,
        v36,
        v38);
      PerfDiagBoot::CPayloadDegradation::~CPayloadDegradation((PerfDiagBoot::CPayloadDegradation *)v51);
      PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v50);
      PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
      PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
      ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
      PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
      return 0;
    }
    else
    {
      PerfDiagBoot::CPayloadDegradation::~CPayloadDegradation((PerfDiagBoot::CPayloadDegradation *)v51);
      PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v50);
      PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
      PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
      ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v40);
      PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v39);
      return (unsigned int)v32;
    }
  }
  else
  {
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v50);
    PerfDiagBoot::CTraceContext::~CTraceContext((PerfDiagBoot::CTraceContext *)v48);
    PerfDiagBoot::CAnalysisContext::~CAnalysisContext((PerfDiagBoot::CAnalysisContext *)v52);
    if ( *(_QWORD *)&v40.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v40.Data1 + 16LL))(*(_QWORD *)&v40.Data1);
    v31 = GetCurrentThread();
    if ( v4 != 0x7FFFFFFF )
      SetThreadPriority(v31, v4);
    return (unsigned int)v29;
  }
}

```

## disassembly

```asm
0x1800279d8  mov     [rsp+arg_8], rbx
0x1800279dd  mov     [rsp+arg_10], rsi
0x1800279e2  push    rdi
0x1800279e3  push    r12
0x1800279e5  push    r14
0x1800279e7  mov     eax, 1270h
0x1800279ec  call    _alloca_probe
0x1800279f1  sub     rsp, rax
0x1800279f4  mov     rax, cs:__security_cookie
0x1800279fb  xor     rax, rsp
0x1800279fe  mov     [rsp+1288h+var_28], rax
0x180027a06  mov     rsi, rcx
0x180027a09  mov     [rsp+1288h+Sid], 0
0x180027a12  mov     qword ptr [rsp+1288h+var_1250.Data4], 0
0x180027a1b  call    cs:__imp_GetCurrentThread
0x180027a21  mov     ebx, 20000h
0x180027a26  mov     edx, 10000h; nPriority
0x180027a2b  mov     rcx, rax; hThread
0x180027a2e  call    cs:__imp_SetThreadPriority
0x180027a34  mov     r12d, 7FFFFFFFh
0x180027a3a  test    eax, eax
0x180027a3c  cmovz   ebx, r12d
0x180027a40  mov     [rsp+1288h+var_1258], ebx
0x180027a44  mov     qword ptr [rsp+1288h+var_1250.Data1], 0
0x180027a4d  lea     r8, [rsp+1288h+var_1250]; struct _GUID *
0x180027a52  mov     rcx, cs:hInstance; this
0x180027a59  call    ?XPerfCoreCreateAddInManager@XPerfCore@@YAJPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z; XPerfCore::XPerfCoreCreateAddInManager(HINSTANCE__ *,_GUID const &,void * *)
0x180027a5e  mov     edi, eax
0x180027a60  test    eax, eax
0x180027a62  jns     short loc_180027A80
0x180027a64  lea     rcx, [rsp+1288h+var_1250]
0x180027a69  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027a6e  nop
0x180027a6f  lea     rcx, [rsp+1288h+var_1258]; this
0x180027a74  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027a79  mov     eax, edi
0x180027a7b  jmp     loc_180028274
0x180027a80  mov     rcx, qword ptr [rsp+1288h+var_1250.Data1]
0x180027a85  mov     rax, [rcx]
0x180027a88  xor     edx, edx
0x180027a8a  mov     rax, [rax+18h]
0x180027a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a93  mov     edi, eax
0x180027a95  test    eax, eax
0x180027a97  jns     short loc_180027AB5
0x180027a99  lea     rcx, [rsp+1288h+var_1250]
0x180027a9e  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027aa3  nop
0x180027aa4  lea     rcx, [rsp+1288h+var_1258]; this
0x180027aa9  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027aae  mov     eax, edi
0x180027ab0  jmp     loc_180028274
0x180027ab5  xor     edx, edx; Val
0x180027ab7  mov     r8d, 208h; Size
0x180027abd  lea     rcx, [rsp+1288h+Buffer]; void *
0x180027ac5  call    memset_0
0x180027aca  mov     edi, 104h
0x180027acf  mov     edx, edi; uSize
0x180027ad1  lea     rcx, [rsp+1288h+Buffer]; lpBuffer
0x180027ad9  call    cs:__imp_GetSystemDirectoryW
0x180027adf  test    eax, eax
0x180027ae1  jnz     short loc_180027AEA
0x180027ae3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027ae8  jmp     short loc_180027B01
0x180027aea  lea     r8, aWdiLogfilesBoo; "\\WDI\\LogFiles\\BootPerfDiagLogger.etl"
0x180027af1  mov     rdx, rdi; unsigned __int64
0x180027af4  lea     rcx, [rsp+1288h+Buffer]; unsigned __int16 *
0x180027afc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027b01  test    eax, eax
0x180027b03  mov     edi, eax
0x180027b05  jns     short loc_180027B23
0x180027b07  lea     rcx, [rsp+1288h+var_1250]
0x180027b0c  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027b11  nop
0x180027b12  lea     rcx, [rsp+1288h+var_1258]; this
0x180027b17  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027b1c  mov     eax, edi
0x180027b1e  jmp     loc_180028274
0x180027b23  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027b2b  call    ??0CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::CAnalysisContext(void)
0x180027b30  nop
0x180027b31  xor     edx, edx
0x180027b33  lea     rcx, [rsp+1288h+var_330]
0x180027b3b  call    ?readWriteImpl@?$RegistryTransferable@VCSharedRegistryConfig@PerfDiagBoot@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagBoot::CSharedRegistryConfig>::readWriteImpl(bool)
0x180027b40  mov     edi, eax
0x180027b42  test    eax, eax
0x180027b44  jns     short loc_180027B70
0x180027b46  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027b4e  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027b53  nop
0x180027b54  lea     rcx, [rsp+1288h+var_1250]
0x180027b59  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027b5e  nop
0x180027b5f  lea     rcx, [rsp+1288h+var_1258]; this
0x180027b64  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027b69  mov     eax, edi
0x180027b6b  jmp     loc_180028274
0x180027b70  mov     rax, [rsp+1288h+var_FB0]
0x180027b78  lea     rcx, [rsp+1288h+var_FB0]
0x180027b80  mov     rax, [rax+10h]
0x180027b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b89  mov     edi, eax
0x180027b8b  test    eax, eax
0x180027b8d  jns     short loc_180027BB9
0x180027b8f  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027b97  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027b9c  nop
0x180027b9d  lea     rcx, [rsp+1288h+var_1250]
0x180027ba2  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027ba7  nop
0x180027ba8  lea     rcx, [rsp+1288h+var_1258]; this
0x180027bad  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027bb2  mov     eax, edi
0x180027bb4  jmp     loc_180028274
0x180027bb9  mov     rax, [rsp+1288h+var_6E8]
0x180027bc1  lea     rcx, [rsp+1288h+var_6E8]
0x180027bc9  mov     rax, [rax+10h]
0x180027bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bd2  mov     edi, eax
0x180027bd4  test    eax, eax
0x180027bd6  jns     short loc_180027C02
0x180027bd8  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027be0  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027be5  nop
0x180027be6  lea     rcx, [rsp+1288h+var_1250]
0x180027beb  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027bf0  nop
0x180027bf1  lea     rcx, [rsp+1288h+var_1258]; this
0x180027bf6  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027bfb  mov     eax, edi
0x180027bfd  jmp     loc_180028274
0x180027c02  lea     rcx, [rsp+1288h+var_1208]; this
0x180027c0a  call    ??0CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::CTraceContext(void)
0x180027c0f  nop
0x180027c10  mov     r9, [rsi+38h]
0x180027c14  cmp     dword ptr [r9-10h], 0
0x180027c19  jnz     short loc_180027C1F
0x180027c1b  mov     r9, [rsi+40h]; unsigned __int16 *
0x180027c1f  lea     r8, [rsp+1288h+Buffer]; unsigned __int16 *
0x180027c27  mov     rdx, qword ptr [rsp+1288h+var_1250.Data1]; struct XPerfCore::IAddInManager *
0x180027c2c  lea     rcx, [rsp+1288h+var_1208]; this
0x180027c34  call    ?Open@CTraceContext@PerfDiagBoot@@QEAAJPEAUIAddInManager@XPerfCore@@PEBG1@Z; PerfDiagBoot::CTraceContext::Open(XPerfCore::IAddInManager *,ushort const *,ushort const *)
0x180027c39  mov     edi, eax
0x180027c3b  test    eax, eax
0x180027c3d  jz      short loc_180027C8F
0x180027c3f  lea     rcx, [rsp+1288h+var_1208]; this
0x180027c47  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027c4c  nop
0x180027c4d  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027c55  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027c5a  nop
0x180027c5b  mov     rcx, qword ptr [rsp+1288h+var_1250.Data1]
0x180027c60  test    rcx, rcx
0x180027c63  jz      short loc_180027C72
0x180027c65  mov     rax, [rcx]
0x180027c68  mov     rax, [rax+10h]
0x180027c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c71  nop
0x180027c72  call    cs:__imp_GetCurrentThread
0x180027c78  cmp     ebx, r12d
0x180027c7b  jz      short loc_180027C88
0x180027c7d  mov     edx, ebx; nPriority
0x180027c7f  mov     rcx, rax; hThread
0x180027c82  call    cs:__imp_SetThreadPriority
0x180027c88  mov     eax, edi
0x180027c8a  jmp     loc_180028274
0x180027c8f  mov     rcx, [rsp+1288h+var_11F8]
0x180027c97  mov     rax, [rcx]
0x180027c9a  lea     rdx, [rsp+1288h+var_1220]
0x180027c9f  mov     rax, [rax+0C0h]
0x180027ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cab  mov     ecx, [rax]
0x180027cad  mov     [rsp+1288h+var_310], ecx
0x180027cb4  mov     eax, [rax+4]
0x180027cb7  mov     [rsp+1288h+var_30C], eax
0x180027cbe  lea     rcx, [rsp+1288h+var_BD8]
0x180027cc6  call    ?getSystemScenarioArchivePath@Impl@PerfDiagBoot@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PerfDiagBoot::Impl::getSystemScenarioArchivePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180027ccb  mov     edi, eax
0x180027ccd  test    eax, eax
0x180027ccf  jns     short loc_180027D09
0x180027cd1  lea     rcx, [rsp+1288h+var_1208]; this
0x180027cd9  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027cde  nop
0x180027cdf  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027ce7  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027cec  nop
0x180027ced  lea     rcx, [rsp+1288h+var_1250]
0x180027cf2  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027cf7  nop
0x180027cf8  lea     rcx, [rsp+1288h+var_1258]; this
0x180027cfd  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027d02  mov     eax, edi
0x180027d04  jmp     loc_180028274
0x180027d09  lea     rcx, PDEvt_Boot_ProcessingSystem_Start; this
0x180027d10  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x180027d15  lea     r8, [rsp+1288h+var_1208]; struct PerfDiagBoot::CSharedRegistryConfig *
0x180027d1d  lea     rdx, [rsp+1288h+var_330]; struct PerfDiagBoot::CSystemAnalysisContext *
0x180027d25  lea     rcx, [rsp+1288h+var_FB8]; this
0x180027d2d  call    ?DetectRegressions@PerfDiagBoot@@YAJAEAUCSystemAnalysisContext@1@AEBVCSharedRegistryConfig@1@AEBVCTraceContext@1@_N@Z; PerfDiagBoot::DetectRegressions(PerfDiagBoot::CSystemAnalysisContext &,PerfDiagBoot::CSharedRegistryConfig const &,PerfDiagBoot::CTraceContext const &,bool)
0x180027d32  mov     edi, eax
0x180027d34  xor     r8d, r8d; unsigned int
0x180027d37  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x180027d39  lea     rcx, PDEvt_Boot_ProcessingSystem_Stop; this
0x180027d40  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x180027d45  cmp     edi, 1
0x180027d48  jbe     short loc_180027D82
0x180027d4a  lea     rcx, [rsp+1288h+var_1208]; this
0x180027d52  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027d57  nop
0x180027d58  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027d60  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027d65  nop
0x180027d66  lea     rcx, [rsp+1288h+var_1250]
0x180027d6b  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027d70  nop
0x180027d71  lea     rcx, [rsp+1288h+var_1258]; this
0x180027d76  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027d7b  mov     eax, edi
0x180027d7d  jmp     loc_180028274
0x180027d82  lea     rcx, [rsp+1288h+var_1178]; this
0x180027d8a  call    ??0CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::CTraceContext(void)
0x180027d8f  nop
0x180027d90  mov     rax, [rsi+38h]
0x180027d94  cmp     dword ptr [rax-10h], 0
0x180027d98  jnz     short loc_180027DA4
0x180027d9a  lea     r14, [rsp+1288h+var_1208]
0x180027da2  jmp     short loc_180027E16
0x180027da4  mov     r9, [rsi+40h]; unsigned __int16 *
0x180027da8  lea     r8, [rsp+1288h+Buffer]; unsigned __int16 *
0x180027db0  mov     rdx, qword ptr [rsp+1288h+var_1250.Data1]; struct XPerfCore::IAddInManager *
0x180027db5  lea     rcx, [rsp+1288h+var_1178]; this
0x180027dbd  call    ?Open@CTraceContext@PerfDiagBoot@@QEAAJPEAUIAddInManager@XPerfCore@@PEBG1@Z; PerfDiagBoot::CTraceContext::Open(XPerfCore::IAddInManager *,ushort const *,ushort const *)
0x180027dc2  mov     edi, eax
0x180027dc4  test    eax, eax
0x180027dc6  jz      short loc_180027E0E
0x180027dc8  lea     rcx, [rsp+1288h+var_1178]; this
0x180027dd0  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027dd5  nop
0x180027dd6  lea     rcx, [rsp+1288h+var_1208]; this
0x180027dde  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027de3  nop
0x180027de4  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027dec  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027df1  nop
0x180027df2  lea     rcx, [rsp+1288h+var_1250]
0x180027df7  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027dfc  nop
0x180027dfd  lea     rcx, [rsp+1288h+var_1258]; this
0x180027e02  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027e07  mov     eax, edi
0x180027e09  jmp     loc_180028274
0x180027e0e  lea     r14, [rsp+1288h+var_1178]
0x180027e16  mov     rcx, [r14+10h]
0x180027e1a  mov     rax, [rcx]
0x180027e1d  lea     rdx, [rsp+1288h+var_1220]
0x180027e22  mov     rax, [rax+0D0h]
0x180027e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e2e  mov     ecx, [rax]
0x180027e30  mov     dword ptr [rsp+1288h+var_308], ecx
0x180027e37  mov     eax, [rax+4]
0x180027e3a  mov     dword ptr [rsp+1288h+var_308+4], eax
0x180027e41  mov     rax, [rsp+1288h+var_308]
0x180027e49  mov     qword ptr cs:?g_FileTime_Boot_End@BootSharedInformation@PerfDiagDm@@2U_FILETIME@@A.dwLowDateTime, rax; _FILETIME PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End ...
0x180027e50  lea     r8, [rsp+1288h+var_1208]; unsigned int
0x180027e58  mov     edx, [rsi+48h]; struct _SID **
0x180027e5b  lea     rcx, [rsp+1288h+Sid]; this
0x180027e60  call    ?getUserSIDFromTrace@Impl@PerfDiagBoot@@YAJAEAPEBU_SID@@KAEBVCTraceContext@2@@Z; PerfDiagBoot::Impl::getUserSIDFromTrace(_SID const * &,ulong,PerfDiagBoot::CTraceContext const &)
0x180027e65  mov     edi, eax
0x180027e67  test    eax, eax
0x180027e69  jz      short loc_180027EB1
0x180027e6b  lea     rcx, [rsp+1288h+var_1178]; this
0x180027e73  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027e78  nop
0x180027e79  lea     rcx, [rsp+1288h+var_1208]; this
0x180027e81  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
0x180027e86  nop
0x180027e87  lea     rcx, [rsp+1288h+var_FF8]; this
0x180027e8f  call    ??1CAnalysisContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CAnalysisContext::~CAnalysisContext(void)
0x180027e94  nop
0x180027e95  lea     rcx, [rsp+1288h+var_1250]
0x180027e9a  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180027e9f  nop
0x180027ea0  lea     rcx, [rsp+1288h+var_1258]; this
0x180027ea5  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180027eaa  mov     eax, edi
0x180027eac  jmp     loc_180028274
0x180027eb1  mov     rcx, [rsp+1288h+Sid]; Sid
0x180027eb6  mov     [rsp+1288h+var_340], rcx
0x180027ebe  lea     rdx, [rsp+1288h+var_1250.Data4]; StringSid
0x180027ec3  call    cs:__imp_ConvertSidToStringSidW
0x180027ec9  test    eax, eax
0x180027ecb  jnz     short loc_180027F28
0x180027ecd  call    cs:__imp_GetLastError
0x180027ed3  mov     ebx, eax
0x180027ed5  test    eax, eax
0x180027ed7  jle     short loc_180027EE2
0x180027ed9  movzx   ebx, ax
0x180027edc  or      ebx, 80070000h
0x180027ee2  lea     rcx, [rsp+1288h+var_1178]; this
0x180027eea  call    ??1CTraceContext@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CTraceContext::~CTraceContext(void)
  ... truncated ...
```
