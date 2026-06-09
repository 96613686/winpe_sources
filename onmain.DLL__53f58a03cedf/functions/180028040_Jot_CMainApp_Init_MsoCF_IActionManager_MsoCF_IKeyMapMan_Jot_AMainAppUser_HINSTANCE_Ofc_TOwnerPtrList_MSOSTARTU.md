# Jot::CMainApp::Init(MsoCF::IActionManager *,MsoCF::IKeyMapMan *,Jot::AMainAppUser *,HINSTANCE__ *,Ofc::TOwnerPtrList<MSOSTARTUPACTION> &,bool,Jot::IBootStatus &,ulong,bool *)

- ea: `0x180028040`
- end: `0x180028d8a`
- name: `?Init@CMainApp@Jot@@UEAAXPEAUIActionManager@MsoCF@@PEAUIKeyMapMan@4@PEAUAMainAppUser@2@PEAUHINSTANCE__@@AEAV?$TOwnerPtrList@UMSOSTARTUPACTION@@@Ofc@@_NAEAVIBootStatus@2@KPEA_N@Z`
- size: `3402`
- prototype: ``
- caller_count: `1`
- callee_count: `82`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027ec0`

## callees

- `0x18001fa90`
- `0x180021a10`
- `0x180025ce0`
- `0x180028040`
- `0x180029850`
- `0x180029980`
- `0x180029a3c`
- `0x180029bc0`
- `0x180029bf8`
- `0x180029db8`
- `0x180029e0c`
- `0x180029f44`
- `0x18002a070`
- `0x18002ac90`
- `0x18002af70`
- `0x18002b244`
- `0x18002c04c`
- `0x18002c288`
- `0x18002ce58`
- `0x18002cef4`
- `0x18002d100`
- `0x18002d6b4`
- `0x18002d840`
- `0x18002da60`
- `0x18002dbb0`
- `0x18002e010`
- `0x18002e520`
- `0x18002e698`
- `0x18002efb0`
- `0x18002f710`
- `0x18002f854`
- `0x18002fa9c`
- `0x18002fb48`
- `0x18002ff00`
- `0x1800314b8`
- `0x180032260`
- `0x180036850`
- `0x180038370`
- `0x1800384d0`
- `0x180038514`
- `0x1800385f4`
- `0x180038624`
- `0x180038664`
- `0x180039e00`
- `0x1800400a0`
- `0x180043948`
- `0x1800472d8`
- `0x1800474c8`
- `0x180047ad8`
- `0x180048060`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x180028271`
- `KERNEL32!InitializeSListHead` at `0x180028271`
- `KERNEL32!SetErrorMode` at `0x180028607`
- `KERNEL32!SetErrorMode` at `0x180028607`
- `USER32!RegisterWindowMessageW` at `0x1800288de`
- `USER32!RegisterWindowMessageW` at `0x1800288de`
- `mso40uiWin32Client!__imp_?FormattedTextInit@FormattedText@Mso@@YA_NXZ` at `0x180028457`
- `mso40uiWin32Client!__imp_?FormattedTextInit@FormattedText@Mso@@YA_NXZ` at `0x180028457`
- `Mso30Win32Client!Mso30Win32Client_56738` at `0x180028c4a`
- `Mso30Win32Client!Mso30Win32Client_56738` at `0x180028c4a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180028d61`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180028d61`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028996`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028b5d`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028bc0`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028996`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028b5d`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x180028bc0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18002898c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180028b53`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180028bb6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18002898c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180028b53`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180028bb6`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028979`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028b41`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028ba4`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028979`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028b41`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x180028ba4`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180028563`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180028563`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1800286de`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1800286de`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x1800280fb`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x1800280fb`

## string_xrefs

- `0x180028630`: `/backuppath`
- `0x180028399`: `ONMain.DLL boot started at |0`
- `0x1800288d7`: `WM_JOT_MAINTHREAD_APC`

## pseudocode

```c
void __fastcall Jot::CMainApp::Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        Jot::CClipboardActor *a4,
        __int64 a5,
        __int64 a6,
        char a7,
        Jot::PagePreviews *a8,
        int a9,
        _BYTE *a10)
{
  __int64 v13; // rax
  Jot::System *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdi
  unsigned __int64 v18; // rdx
  unsigned int v19; // r8d
  Jot::CConcurrentScheduler *v20; // rax
  unsigned __int64 v21; // rdx
  unsigned int v22; // r8d
  Jot::CConcurrentScheduler *v23; // rax
  void *v24; // rbx
  Jot::CMainAppSecondInstanceBlocker *v25; // r15
  Jot::Crypto *v26; // rcx
  unsigned int v27; // edx
  Jot *v28; // rcx
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  const struct MsoCF::PropertySpaceInfo *v31; // rdx
  const struct MsoCF::PropertySpaceInfo *v32; // rdx
  const struct MsoCF::PropertySpaceInfo *v33; // rdx
  const struct MsoCF::PropertySpaceInfo *v34; // rdx
  unsigned __int64 v35; // rdx
  Mso::FormattedText *v36; // rcx
  unsigned int v37; // r8d
  __int64 v38; // rcx
  void *v39; // rbx
  __int64 Instance; // rax
  __int64 v41; // rbx
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  unsigned int v44; // r8d
  Jot::CAsyncManagerBase *v45; // rax
  Jot::CAsyncManagerBase *v46; // rbx
  Jot::SystemStateTracker *v47; // rcx
  Jot::LiveSyncIdleTracker *v48; // rcx
  OneNote::Privacy *v49; // rcx
  bool v50; // al
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  const wchar_t *v55; // rax
  Jot::SafeBoot *v56; // rcx
  __int64 v57; // rax
  unsigned __int64 v58; // rdx
  unsigned int v59; // r8d
  _DWORD *v60; // rax
  unsigned __int64 v61; // rdx
  unsigned int v62; // r8d
  _DWORD *v63; // rbx
  _BYTE *v64; // rax
  unsigned __int64 v65; // rdx
  __int64 v66; // r8
  _BYTE *v67; // rbx
  __int64 v68; // r10
  _DWORD *v69; // rdi
  Jot::CRoamingManager *v70; // rax
  void (__fastcall ***v71)(_QWORD); // rbx
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rax
  struct MsoCF::IActionContext *v75; // rbx
  Mso::Async *v76; // rcx
  Mso::Async::Details *v77; // rax
  struct Mso::Async::IDispatchQueue *v78; // rdx
  __int64 (__fastcall ***v79)(); // rcx
  __int64 v80; // rax
  __int64 v81; // rax
  _QWORD *v82; // rax
  __int64 v83; // rax
  Jot::PagePreviews *v84; // rdi
  struct Jot::IRootGraphSpace *v85; // rdx
  __int64 (__fastcall ***v86)(); // rdi
  Mso::Async *v87; // rcx
  Mso::Async::Details *v88; // rax
  struct Mso::Async::IDispatchQueue *v89; // rdx
  Mso::Async *v90; // rcx
  Mso::Async::Details *v91; // rax
  struct Mso::Async::IDispatchQueue *v92; // rdx
  Jot *v93; // rcx
  struct Jot::CNetworkStatus *OneNoteDotComNetworkStatusInstance; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 *v99; // rax
  __int64 v100; // r8
  void (__fastcall ***v101)(_QWORD, __int64); // rcx
  __int64 v102; // rax
  __int64 v103; // rax
  Jot::ClassNotebook *v104; // rcx
  __int64 (__fastcall *v105)(void *); // rdx
  int v106; // [rsp+28h] [rbp-11D0h]
  int v107; // [rsp+28h] [rbp-11D0h]
  int v108; // [rsp+30h] [rbp-11C8h]
  int v109; // [rsp+30h] [rbp-11C8h]
  int v110; // [rsp+38h] [rbp-11C0h]
  int v111; // [rsp+38h] [rbp-11C0h]
  int v112; // [rsp+40h] [rbp-11B8h]
  int v113; // [rsp+40h] [rbp-11B8h]
  _BYTE v114[8]; // [rsp+50h] [rbp-11A8h] BYREF
  __int64 (__fastcall ***v115)(); // [rsp+58h] [rbp-11A0h] BYREF
  Jot::PagePreviews *v116; // [rsp+60h] [rbp-1198h] BYREF
  char ***v117; // [rsp+68h] [rbp-1190h] BYREF
  const char *v118; // [rsp+70h] [rbp-1188h]
  __int64 v119[2]; // [rsp+78h] [rbp-1180h] BYREF
  _BYTE v120[8]; // [rsp+88h] [rbp-1170h] BYREF
  _BYTE *v121; // [rsp+90h] [rbp-1168h] BYREF
  struct MsoCF::IActionContext *v122; // [rsp+98h] [rbp-1160h] BYREF
  __int64 v123; // [rsp+A0h] [rbp-1158h] BYREF
  int v124; // [rsp+A8h] [rbp-1150h] BYREF
  int v125; // [rsp+ACh] [rbp-114Ch] BYREF
  _BYTE v126[8]; // [rsp+B0h] [rbp-1148h] BYREF
  _BYTE v127[16]; // [rsp+B8h] [rbp-1140h] BYREF
  _QWORD v128[5]; // [rsp+C8h] [rbp-1130h] BYREF
  __int16 v129; // [rsp+F0h] [rbp-1108h]
  _BYTE v130[4272]; // [rsp+100h] [rbp-10F8h] BYREF

  v115 = (__int64 (__fastcall ***)())a1;
  v123 = a6;
  v116 = a8;
  v121 = a10;
  Mso::Telemetry::EventFlags::EventFlags(&v122, 4);
  v117 = &off_1810B79B0;
  v118 = "OneNoteTTV";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v127,
    (const struct Mso::Telemetry::EventName *)&v117,
    (const struct Mso::Telemetry::EventFlags *)&v122);
  v13 = Mso::Telemetry::Activity::Detach(v127, v119);
  Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(a1 + 728, v13);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v119);
  Jot::Telemetry::BootLogger::g_mainappInitStarted = Jot::System::MsecsSinceProcessLaunch(v14);
  byte_181510100 = 1;
  dword_181510101 = *(_DWORD *)((char *)&v118 + 1);
  word_181510105 = *(_WORD *)((char *)&v118 + 5);
  byte_181510107 = HIBYTE(v118);
  sub_18002A070(v120);
  v117 = &off_1810AFEE0;
  v118 = "SampledAppLaunch";
  Jot::Logging::LogTraceTag<>(587792521, &v117, 50);
  qword_181533688 = a4;
  MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(a1 + 32, a2);
  *(_QWORD *)(a1 + 296) = a5;
  v122 = (struct MsoCF::IActionContext *)(a1 + 344);
  *(_BYTE *)(a1 + 344) = a7;
  LOBYTE(v15) = 10;
  LOBYTE(v16) = -65;
  Mso::Telemetry::EventFlags::EventFlags(v126, v16, 2, v15);
  v114[0] = (*(__int64 (__fastcall **)(Jot::CClipboardActor *))(*(_QWORD *)qword_181533688 + 424LL))(qword_181533688);
  v128[0] = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v128[1] = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'};
  v128[2] = L"MainAppDDPIAwarenessSet";
  v17 = -1;
  v128[3] = -1;
  v128[4] = v114;
  v129 = 4;
  v117 = &off_1810AFEE0;
  v118 = "AppLaunch";
  Mso::Telemetry::SendTelemetryEvent<Jot::Logging::ErrorData>(&v117, v126, v128);
  InitializeSListHead(&ListHead);
  v20 = (Jot::CConcurrentScheduler *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xA8, v18, v19);
  v119[0] = (__int64)v20;
  if ( v20 )
    v23 = (Jot::CConcurrentScheduler *)Jot::CConcurrentScheduler::CConcurrentScheduler(v20, 0xAu);
  else
    v23 = 0;
  qword_181500EA8 = v23;
  _InterlockedIncrement(&MsoCF::CPropertyGlobals::g_cRef);
  v24 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)1, v21, v22);
  v119[0] = (__int64)v24;
  if ( v24 )
  {
    if ( qword_181533688 )
      (*(void (__fastcall **)(Jot::CClipboardActor *))(*(_QWORD *)qword_181533688 + 288LL))(qword_181533688);
  }
  else
  {
    v24 = 0;
  }
  v119[0] = 0;
  v25 = *(Jot::CMainAppSecondInstanceBlocker **)(a1 + 672);
  *(_QWORD *)(a1 + 672) = v24;
  if ( v25 )
  {
    Jot::CMainAppSecondInstanceBlocker::~CMainAppSecondInstanceBlocker(v25);
    operator delete(v25);
  }
  std::unique_ptr<Jot::CMainAppSecondInstanceBlocker>::~unique_ptr<Jot::CMainAppSecondInstanceBlocker>(v119);
  Jot::Crypto::InitSessionSalt(v26);
  Jot::LogBegin(v28, v27);
  if ( Jot::ShouldLogTtid((Jot *)0x40B3DC, 0x10064u, 2u, v29) )
    Jot::Log_Impl<wchar_t [81],>((Jot *)0x40B3DC, 0x10064u);
  if ( Jot::ShouldLogTtid((Jot *)0x4C0648, 0x10064u, 2u, v30) )
  {
    v119[0] = MsoCF::CFileTimeAPIs::GetCurrentTick();
    Jot::Log_Impl<wchar_t [30],MsoCF::CTickCountBase<MsoCF::CFileTimeAPIs>>((Jot *)0x4C0648, 0x10064u, (__int64)v119);
  }
  qword_1815100C0 = (__int64)Jot::OnErrorExceptionThrow;
  MsoCF::RegisterPropertySpace((MsoCF *)&Jot::PropertySpace_JotMain::g_prspi, v31);
  MsoCF::RegisterPropertySpace((MsoCF *)&Jot::PropertySpace_Jot11::g_prspi, v32);
  MsoCF::RegisterPropertySpace((MsoCF *)&Jot::PropertySpace_Jot14::g_prspi, v33);
  MsoCF::RegisterPropertySpace((MsoCF *)&Jot::PropertySpace_Jot_1::g_prspi, v34);
  Jot::CMainApp::InitActions((Jot::CMainApp *)a1);
  if ( !Jot::s_spEventManager )
  {
    v39 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x570, v35, v37);
    v119[0] = (__int64)v39;
    if ( v39 )
      `eh vector constructor iterator'(
        v39,
        0x10u,
        0x57u,
        MsoCF::CArray<Jot::EventSinkInfo>::CArray<Jot::EventSinkInfo>,
        Ofc::TArray<Jot::CHTMLExporter::CharFormatProp>::~TArray<Jot::CHTMLExporter::CharFormatProp>);
    else
      v39 = 0;
    MsoCF::COwnerPtr<Jot::CEventManager,MsoCF::COwnerPtr_Delete_Auto<Jot::CEventManager>>::Attach(v38, v39);
  }
  Mso::FormattedText::FormattedTextInit(v36);
  Jot::CBackgroundScheduler::BeginForThread(0, 1);
  Instance = MsoCF::CJotComObject<Jot::CLoggingTagResetOnRegistryModification,MsoCF::CAllocatorOnNew>::CreateInstance();
  v41 = Instance;
  if ( Instance )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)Instance + 8LL))(Instance);
  v42 = qword_1815011D8;
  qword_1815011D8 = v41;
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v41 = qword_1815011D8;
  }
  (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v41 + 144LL))(v41, &vmsoridOneNoteLoggingHook, 0);
  v45 = (Jot::CAsyncManagerBase *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x88, v43, v44);
  v46 = v45;
  v119[0] = (__int64)v45;
  if ( v45 )
  {
    Jot::CAsyncManagerBase::CAsyncManagerBase(v45);
    *(_QWORD *)v46 = &Jot::CAsyncManager::`vftable';
  }
  else
  {
    v46 = 0;
  }
  if ( v46 )
    (**(void (__fastcall ***)(Jot::CAsyncManagerBase *))v46)(v46);
  v47 = *(Jot::SystemStateTracker **)(a1 + 560);
  *(_QWORD *)(a1 + 560) = v46;
  if ( v47 )
    (*(void (__fastcall **)(Jot::SystemStateTracker *))(*(_QWORD *)v47 + 8LL))(v47);
  Jot::SystemStateTracker::InitializeApp(v47);
  Jot::LiveSyncIdleTracker::Initialize(v48);
  Jot::SafeBoot::CrashCounter::Start((Jot::SafeBoot::CrashCounter *)&off_18150F328);
  Jot::SafeBoot::CrashCounter::Start((Jot::SafeBoot::CrashCounter *)&off_1815011B0);
  if ( byte_18150F318 < 0 )
    v50 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18150F318);
  else
    v50 = byte_18150F318 != 0;
  if ( !v50 && OneNote::Privacy::UserContentServiceAllowed(v49) )
  {
    std::make_shared<OneNote::SIGSEventLogger::AuthSIGSHandler,>(&v117);
    v51 = std::make_unique<OneNote::SIGSEventLogger::CSIGSLogger,std::shared_ptr<OneNote::SIGSEventLogger::AuthSIGSHandler> &,0>(
            v119,
            &v117);
    std::unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>::operator=<std::default_delete<OneNote::SIGSEventLogger::CSIGSLogger>,0>(
      a1 + 192,
      v51);
    std::unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>::~unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>(v119);
    v52 = std::make_shared<Jot::SIGSEventTrigger::CSIGSTrigger,>(v119);
    std::shared_ptr<Microsoft::Office::AugLoop::SlideDetection::Rectangle>::operator=(a1 + 200, v52);
    std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v119);
    v53 = std::make_unique<Jot::SIGSEventTrigger::CCopilotSIGSTrigger,,0>(v119);
    std::unique_ptr<Jot::SIGSEventTrigger::CCopilotSIGSTrigger>::operator=<std::default_delete<Jot::SIGSEventTrigger::CCopilotSIGSTrigger>,0>(
      a1 + 216,
      v53);
    std::unique_ptr<Jot::SIGSEventTrigger::CCopilotSIGSTrigger>::~unique_ptr<Jot::SIGSEventTrigger::CCopilotSIGSTrigger>(v119);
    std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(&v117);
  }
  SetErrorMode(0x8001u);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>(v130);
  LOBYTE(v54) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(Jot::CClipboardActor *, const wchar_t *, __int64, _BYTE *))(*(_QWORD *)qword_181533688 + 208LL))(
         qword_181533688,
         L"/backuppath",
         v54,
         v130) )
  {
    v55 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v130);
    if ( v55 )
    {
      do
        ++v17;
      while ( v55[v17] );
      if ( (unsigned int)(v17 - 1) <= 0x103 )
      {
        MsoWzCopy(v55, &qword_1815AD7D0, 2084);
        byte_1815AF401 = 1;
      }
    }
  }
  Jot::CMainApp::ProcessStartupActions(a1, v123);
  if ( !*(_BYTE *)v122 && Jot::SafeBoot::ShouldShowDialog(v56) )
  {
    (*(void (__fastcall **)(Jot::CClipboardActor *, _QWORD))(*(_QWORD *)qword_181533688 + 384LL))(qword_181533688, 0);
    v114[0] = 0;
    Jot::CSafeBoot::PerformSafeBoot((Jot::CSafeBoot *)v114);
    MsoRegDeleteValue((const struct _msoreg *)&vmsoridOneNoteShouldForceSafeBoot);
    v117 = &off_181293E90;
    v118 = "SafeBootUIMoshDisplaySafeBootBlockingDialog";
    Jot::Logging::LogTraceTag<>(20820098, &v117, 50);
    *(_BYTE *)(a1 + 280) = v114[0];
  }
  v57 = std::make_shared<Jot::CNoteTagManager,>(&v117);
  std::shared_ptr<Microsoft::Office::AugLoop::SlideDetection::Rectangle>::operator=(a1 + 16, v57);
  std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(&v117);
  Jot::INotebookManager::CreateNotebookManager();
  v60 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v58, v59);
  v123 = (__int64)v60;
  if ( v60 )
  {
    *(_QWORD *)v60 = 0;
    v60[2] = 0;
    v60[3] = 0x80000000;
  }
  else
  {
    v60 = 0;
  }
  v63 = *(_DWORD **)(a1 + 72);
  if ( v60 != v63 || !v60 )
  {
    *(_QWORD *)(a1 + 72) = v60;
    if ( v63 )
    {
      Ofc::TArray<Jot::COutlineStyle>::~TArray<Jot::COutlineStyle>(v63);
      operator delete(v63);
    }
  }
  v64 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x38, v61, v62);
  v67 = v64;
  v123 = (__int64)v64;
  if ( v64 )
  {
    v119[0] = (__int64)(v64 + 8);
    *((_QWORD *)v64 + 1) = v64 + 24;
    *((_DWORD *)v64 + 4) = 0;
    *((_DWORD *)v64 + 12) = 0;
    *((_QWORD *)v64 + 3) = &off_1815119B0;
    *((_QWORD *)v64 + 4) = 0;
    *((_DWORD *)v64 + 10) = 0;
    LODWORD(v121) = 0;
    v66 = *(unsigned int *)SafeInt<unsigned int,safeint_exception_handlers::SafeInt_InvalidParameter>::operator*(
                             &v121,
                             &v115,
                             548);
    if ( (unsigned int)v66 > 0x7FFFFFFF )
      __fastfail(5u);
    if ( (int)v66 > *(_DWORD *)(v68 + 16) )
      (***(void (__fastcall ****)(_QWORD, __int64, __int64, _QWORD))v68)(*(_QWORD *)v68, v68, v66, 0);
    *v67 = 0;
  }
  else
  {
    v67 = 0;
  }
  v69 = *(_DWORD **)(a1 + 80);
  if ( v67 != (_BYTE *)v69 || !v67 )
  {
    *(_QWORD *)(a1 + 80) = v67;
    if ( v69 )
    {
      v69[4] = 0;
      MsoCF::CAtomicBuffer<MsoCF::ExtendedGUID>::~CAtomicBuffer<MsoCF::ExtendedGUID>(v69 + 6);
      operator delete(v69);
    }
  }
  v70 = (Jot::CRoamingManager *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x78, v65, v66);
  v123 = (__int64)v70;
  if ( v70 )
    v71 = (void (__fastcall ***)(_QWORD))Jot::CRoamingManager::CRoamingManager(v70);
  else
    v71 = 0;
  if ( v71 )
    (**v71)(v71);
  v72 = *(_QWORD *)(a1 + 336);
  *(_QWORD *)(a1 + 336) = v71;
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 8LL))(v72);
  v73 = (_QWORD *)sub_1800314B8();
  (*(void (__fastcall **)(_QWORD, Jot::PagePreviews *, _BYTE *))(*(_QWORD *)*v73 + 16LL))(*v73, v116, a10);
  if ( Jot::WM_JOT_MAINTHREAD_APC == -1 )
    Jot::WM_JOT_MAINTHREAD_APC = RegisterWindowMessageW(L"WM_JOT_MAINTHREAD_APC");
  v122 = 0;
  Jot::CGlobalContext::CreateInstance(&v122);
  v125 = 131742;
  v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_181534870 + 496LL))(qword_181534870);
  v75 = v122;
  (*(void (__fastcall **)(__int64, int *, struct MsoCF::IActionContext *, __int64, int, _BYTE, char, _BYTE, _BYTE))(*(_QWORD *)v74 + 256LL))(
    v74,
    &v125,
    v122,
    1,
    4000,
    0,
    1,
    0,
    0);
  v115 = &off_1810C6B68;
  v77 = Mso::Async::CurrentQueue(v76);
  if ( !v77 )
    CrashWithRecovery(0x110B458u, 0);
  v116 = Mso::Async::Details::AsIdle(v77, v78);
  Mso::Async::PostTimer<Mso::Async::IDispatchQueue *>(4000, &v116, &v115);
  v79 = v115;
  if ( v115 )
  {
    v115 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v79)[2])(v79);
  }
  LODWORD(v121) = 132321;
  v80 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_181534870 + 496LL))(qword_181534870);
  LOBYTE(v112) = 0;
  LOBYTE(v110) = 0;
  LOBYTE(v108) = 1;
  LOBYTE(v106) = 0;
  (*(void (__fastcall **)(__int64, _BYTE **, struct MsoCF::IActionContext *, __int64, int, int, int, int, int))(*(_QWORD *)v80 + 256LL))(
    v80,
    &v121,
    v75,
    64,
    10000,
    v106,
    v108,
    v110,
    v112);
  v124 = 132814;
  v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 496LL))(a1);
  LOBYTE(v113) = 1;
  LOBYTE(v111) = 0;
  LOBYTE(v109) = 1;
  LOBYTE(v107) = 1;
  *(_QWORD *)(a1 + 608) = (*(__int64 (__fastcall **)(__int64, int *, struct MsoCF::IActionContext *, _QWORD, _DWORD, int, int, int, int))(*(_QWORD *)v81 + 256LL))(
                            v81,
                            &v124,
                            v75,
                            0,
                            0,
                            v107,
                            v109,
                            v111,
                            v113);
  v82 = (_QWORD *)sub_1800314B8();
  v83 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v82 + 152LL))(*v82);
  MsoCF::QI_OrThrow<Jot::IRootGraphSpace,&__s_GUID const _GUID_68c5e87c_4325_419b_b8a3_a56d57c8996e>(&v116, v83);
  v84 = v116;
  Jot::PagePreviews::Initialize(v116, v85);
  if ( v84 )
    (*(void (__fastcall **)(Jot::PagePreviews *))(*(_QWORD *)v84 + 16LL))(v84);
  if ( !a10 || !*a10 )
  {
    v115 = 0;
    ATL::CComObject<Jot::CONNoteLinkContentService>::CreateInstance(&v115);
    v86 = v115;
    if ( v115 )
      ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v115)[1])(v115);
    v87 = *(Mso::Async **)(a1 + 568);
    *(_QWORD *)(a1 + 568) = v86;
    if ( v87 )
      (*(void (__fastcall **)(Mso::Async *))(*(_QWORD *)v87 + 16LL))(v87);
    v115 = &off_1810C6B98;
    v88 = Mso::Async::CurrentQueue(v87);
    if ( !v88 )
      CrashWithRecovery(0x110B458u, 0);
    v116 = Mso::Async::Details::AsIdle(v88, v89);
    Mso::Async::PostTimer<Mso::Async::IDispatchQueue *>(30000, &v116, &v115);
    v90 = (Mso::Async *)v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(Mso::Async *))(*(_QWORD *)v90 + 16LL))(v90);
    }
    v115 = &off_1810C6BC8;
    v91 = Mso::Async::CurrentQueue(v90);
    if ( !v91 )
      CrashWithRecovery(0x110B458u, 0);
    v116 = Mso::Async::Details::AsIdle(v91, v92);
    Mso::Async::PostTimer<Mso::Async::IDispatchQueue *>(5000, &v116, &v115);
    v93 = (Jot *)v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v93 + 16LL))(v93);
    }
    v116 = (Jot::PagePreviews *)a1;
    OneNoteDotComNetworkStatusInstance = Jot::GetOneNoteDotComNetworkStatusInstance(v93);
    v95 = (**(__int64 (__fastcall ***)(struct Jot::CNetworkStatus *))OneNoteDotComNetworkStatusInstance)(OneNoteDotComNetworkStatusInstance);
    v96 = sub_180048060(&v123, v95, &v116);
    Jot::CAsyncResultCancelAndWaitOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=<Jot::IAsyncWithResult<void>>(
      a1 + 632,
      v96);
    Jot::CAsyncResultCancelAndWaitOnDestroyPtr<Jot::IAsyncResult>::~CAsyncResultCancelAndWaitOnDestroyPtr<Jot::IAsyncResult>(&v123);
    v97 = Mso30Win32Client_56738();
    v98 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 24LL))(v97);
    sub_1800474C8(v98, &v116);
    v99 = (__int64 *)Jot::CreateAugmentationManager(&v116);
    v100 = *v99;
    *v99 = 0;
    v101 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 224);
    *(_QWORD *)(a1 + 224) = v100;
    if ( v101 )
      (**v101)(v101, 1);
    std::unique_ptr<Jot::CTableRowMoveSubTool>::~unique_ptr<Jot::CTableRowMoveSubTool>(&v116);
    v102 = std::make_unique<Jot::DocumentService,,0>(&v116);
    std::unique_ptr<Jot::DocumentService>::operator=<std::default_delete<Jot::DocumentService>,0>(a1 + 160, v102);
    std::unique_ptr<Jot::DocumentService>::~unique_ptr<Jot::DocumentService>(&v116);
    v103 = std::make_unique<Jot::LoopLink,Jot::DocumentService &,0>(&v116, *(_QWORD *)(a1 + 160));
    std::unique_ptr<Jot::LoopLink>::operator=<std::default_delete<Jot::LoopLink>,0>(a1 + 152, v103);
    std::unique_ptr<Jot::LoopLink>::~unique_ptr<Jot::LoopLink>(&v116);
    Jot::ClassNotebook::EnsureClassNotebookStateAtBoot(v104);
  }
  if ( v75 )
  {
    v105 = *(__int64 (__fastcall **)(void *))(*(_QWORD *)v75 + 16LL);
    if ( v105 == MsoCF::CJotComObject<Jot::CPersistablePropertyContainer,MsoCF::CAllocatorOnNew>::Release )
    {
      MsoCF::CJotComObject<Jot::CPersistablePropertyContainer,MsoCF::CAllocatorOnNew>::Release(v75);
    }
    else if ( v105 == MsoCF::CJotComObjectForMakeComObject<Jot::CAsyncResult_ResultKnownSynchronously_T<std::vector<MsoCF::CIRef<Jot::IAsyncWithResult<void>>>>>::Release )
    {
      MsoCF::CJotComObjectForMakeComObject<Jot::CAsyncResult_ResultKnownSynchronously_T<std::vector<MsoCF::CIRef<Jot::IAsyncWithResult<void>>>>>::Release(v75);
    }
    else
    {
      (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v75 + 16LL))(v75);
    }
  }
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>(v130);
  sub_1800483A4(v120);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v127);
}

```

## disassembly

```asm
0x180028040  push    rbx
0x180028042  push    rsi
0x180028043  push    rdi
0x180028044  push    r12
0x180028046  push    r13
0x180028048  push    r14
0x18002804a  push    r15
0x18002804c  mov     eax, 11C0h
0x180028051  call    _alloca_probe
0x180028056  sub     rsp, rax
0x180028059  mov     rax, cs:__security_cookie
0x180028060  xor     rax, rsp
0x180028063  mov     [rsp+11F8h+var_48], rax
0x18002806b  mov     rdi, r9
0x18002806e  mov     rbx, rdx
0x180028071  mov     r14, rcx
0x180028074  mov     [rsp+11F8h+var_11A0], rcx
0x180028079  mov     rax, [rsp+11F8h+arg_28]
0x180028081  mov     [rsp+11F8h+var_1158], rax
0x180028089  mov     rax, [rsp+11F8h+arg_38]
0x180028091  mov     [rsp+11F8h+var_1198], rax
0x180028096  mov     r12, [rsp+11F8h+arg_48]
0x18002809e  mov     [rsp+11F8h+var_1168], r12
0x1800280a6  xor     esi, esi
0x1800280a8  lea     r13d, [rsi+4]
0x1800280ac  mov     edx, r13d
0x1800280af  lea     rcx, [rsp+11F8h+var_1160]
0x1800280b7  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x1800280bc  lea     rax, off_1810B79B0
0x1800280c3  mov     [rsp+11F8h+var_1190], rax
0x1800280c8  lea     rax, aOnenotettv; "OneNoteTTV"
0x1800280cf  mov     [rsp+11F8h+var_1188], rax
0x1800280d4  lea     r8, [rsp+11F8h+var_1160]; struct Mso::Telemetry::EventFlags *
0x1800280dc  lea     rdx, [rsp+11F8h+var_1190]; struct Mso::Telemetry::EventName *
0x1800280e1  lea     rcx, [rsp+11F8h+var_1140]; this
0x1800280e9  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x1800280ee  lea     rdx, [rsp+11F8h+var_1180]
0x1800280f3  lea     rcx, [rsp+11F8h+var_1140]
0x1800280fb  call    cs:__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ; Mso::Telemetry::Activity::Detach(void)
0x180028101  lea     rcx, [r14+2D8h]
0x180028108  mov     rdx, rax
0x18002810b  call    ??4?$TCntPtr@VIDispatchQueue@Async@Mso@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(Mso::TCntPtr<Mso::Async::IDispatchQueue> &&)
0x180028110  lea     rcx, [rsp+11F8h+var_1180]
0x180028115  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18002811a  call    ?MsecsSinceProcessLaunch@System@Jot@@YA_KXZ; Jot::System::MsecsSinceProcessLaunch(void)
0x18002811f  mov     cs:?g_mainappInitStarted@BootLogger@Telemetry@Jot@@3V?$optional@_K@std@@A, rax; std::optional<unsigned __int64> Jot::Telemetry::BootLogger::g_mainappInitStarted
0x180028126  mov     cs:byte_181510100, 1
0x18002812d  mov     eax, dword ptr [rsp+11F8h+var_1188+1]
0x180028131  mov     cs:dword_181510101, eax
0x180028137  movzx   eax, word ptr [rsp+11F8h+var_1188+5]
0x18002813c  mov     cs:word_181510105, ax
0x180028143  mov     al, byte ptr [rsp+11F8h+var_1188+7]
0x180028147  mov     cs:byte_181510107, al
0x18002814d  lea     rcx, [rsp+11F8h+var_1170]
0x180028155  call    sub_18002A070
0x18002815a  lea     r15, off_1810AFEE0
0x180028161  mov     [rsp+11F8h+var_1190], r15
0x180028166  lea     rax, aSampledapplaun; "SampledAppLaunch"
0x18002816d  mov     [rsp+11F8h+var_1188], rax
0x180028172  lea     r8d, [rsi+32h]
0x180028176  lea     rdx, [rsp+11F8h+var_1190]
0x18002817b  mov     ecx, 23090089h
0x180028180  call    ??$LogTraceTag@$$V@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@W4TraceLevel@01@@Z; Jot::Logging::LogTraceTag<>(ulong,Mso::Telemetry::EventName const &,Jot::Logging::TraceLevel)
0x180028185  mov     cs:qword_181533688, rdi
0x18002818c  lea     rcx, [r14+20h]
0x180028190  mov     rdx, rbx
0x180028193  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x180028198  mov     rax, [rsp+11F8h+arg_20]
0x1800281a0  mov     [r14+128h], rax
0x1800281a7  lea     rcx, [r14+158h]
0x1800281ae  mov     [rsp+11F8h+var_1160], rcx
0x1800281b6  mov     al, [rsp+11F8h+arg_30]
0x1800281bd  mov     [rcx], al
0x1800281bf  lea     r8d, [rsi+2]
0x1800281c3  mov     r9b, 0Ah
0x1800281c6  mov     dl, 0BFh
0x1800281c8  lea     rcx, [rsp+11F8h+var_1148]
0x1800281d0  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@W4DiagnosticLevel@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories,Mso::Telemetry::DiagnosticLevel)
0x1800281d5  mov     rcx, cs:qword_181533688
0x1800281dc  mov     rax, [rcx]
0x1800281df  mov     rax, [rax+1A8h]
0x1800281e6  call    cs:__guard_dispatch_icall_fptr
0x1800281ec  mov     [rsp+11F8h+var_11A8], al
0x1800281f0  lea     rax, ??_7?$StructuredTraceImplementation@_N@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1800281f7  mov     [rsp+11F8h+var_1130], rax
0x1800281ff  lea     rax, ??_7?$StructuredTraceImplementation@_N@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'}
0x180028206  mov     [rsp+11F8h+var_1128], rax
0x18002820e  lea     rax, aMainappddpiawa; "MainAppDDPIAwarenessSet"
0x180028215  mov     [rsp+11F8h+var_1120], rax
0x18002821d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028221  mov     [rsp+11F8h+var_1118], rdi
0x180028229  lea     rax, [rsp+11F8h+var_11A8]
0x18002822e  mov     [rsp+11F8h+var_1110], rax
0x180028236  mov     [rsp+11F8h+var_1108], r13w
0x18002823f  mov     [rsp+11F8h+var_1190], r15
0x180028244  lea     rax, aApplaunch; "AppLaunch"
0x18002824b  mov     [rsp+11F8h+var_1188], rax
0x180028250  lea     r8, [rsp+11F8h+var_1130]
0x180028258  lea     rdx, [rsp+11F8h+var_1148]
0x180028260  lea     rcx, [rsp+11F8h+var_1190]
0x180028265  call    ??$SendTelemetryEvent@VErrorData@Logging@Jot@@@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@$$QEAVErrorData@Logging@Jot@@@Z; Mso::Telemetry::SendTelemetryEvent<Jot::Logging::ErrorData>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Jot::Logging::ErrorData &&)
0x18002826a  lea     rcx, ListHead; ListHead
0x180028271  call    cs:__imp_InitializeSListHead
0x180028277  mov     ecx, 0A8h; this
0x18002827c  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180028281  mov     [rsp+11F8h+var_1180], rax
0x180028286  test    rax, rax
0x180028289  jz      short loc_180028298
0x18002828b  lea     edx, [rsi+0Ah]; unsigned __int64
0x18002828e  mov     rcx, rax; this
0x180028291  call    ??0CConcurrentScheduler@Jot@@QEAA@_K@Z; Jot::CConcurrentScheduler::CConcurrentScheduler(unsigned __int64)
0x180028296  jmp     short loc_18002829B
0x180028298  mov     rax, rsi
0x18002829b  mov     cs:qword_181500EA8, rax
0x1800282a2  lock inc cs:?g_cRef@CPropertyGlobals@MsoCF@@0V?$CGlobal@J@2@A; MsoCF::CGlobal<long> MsoCF::CPropertyGlobals::g_cRef
0x1800282a9  mov     ecx, 1; this
0x1800282ae  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800282b3  mov     rbx, rax
0x1800282b6  mov     [rsp+11F8h+var_1180], rax
0x1800282bb  test    rax, rax
0x1800282be  jz      short loc_1800282DE
0x1800282c0  mov     rcx, cs:qword_181533688
0x1800282c7  test    rcx, rcx
0x1800282ca  jz      short loc_1800282E1
0x1800282cc  mov     rdx, [rcx]
0x1800282cf  mov     rax, [rdx+120h]
0x1800282d6  call    cs:__guard_dispatch_icall_fptr
0x1800282dc  jmp     short loc_1800282E1
0x1800282de  mov     rbx, rsi
0x1800282e1  mov     [rsp+11F8h+var_1180], rsi
0x1800282e6  mov     r15, [r14+2A0h]
0x1800282ed  mov     [r14+2A0h], rbx
0x1800282f4  test    r15, r15
0x1800282f7  jz      short loc_180028309
0x1800282f9  mov     rcx, r15; this
0x1800282fc  call    ??1CMainAppSecondInstanceBlocker@Jot@@QEAA@XZ; Jot::CMainAppSecondInstanceBlocker::~CMainAppSecondInstanceBlocker(void)
0x180028301  mov     rcx, r15; void *
0x180028304  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028309  lea     rcx, [rsp+11F8h+var_1180]
0x18002830e  call    ??1?$unique_ptr@VCMainAppSecondInstanceBlocker@Jot@@U?$default_delete@VCMainAppSecondInstanceBlocker@Jot@@@std@@@std@@QEAA@XZ; std::unique_ptr<Jot::CMainAppSecondInstanceBlocker>::~unique_ptr<Jot::CMainAppSecondInstanceBlocker>(void)
0x180028313  call    ?InitSessionSalt@Crypto@Jot@@YAXXZ; Jot::Crypto::InitSessionSalt(void)
0x180028318  call    ?LogBegin@Jot@@YAXK@Z; Jot::LogBegin(ulong)
0x18002831d  nop
0x18002831e  xchg    ax, ax
0x180028320  mov     ebx, 10064h
0x180028325  mov     r8d, 2; unsigned int
0x18002832b  mov     edx, ebx; unsigned int
0x18002832d  mov     r15d, 40B3DCh
0x180028333  mov     ecx, r15d; this
0x180028336  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x18002833b  test    al, al
0x18002833d  jz      short loc_180028351
0x18002833f  lea     r9, asc_1810BA2E0; "***************************************"...
0x180028346  mov     edx, ebx; unsigned int
0x180028348  mov     ecx, r15d; this
0x18002834b  call    ??$Log_Impl@$$BY0FB@_W$$V@Jot@@YAXKIW4LogMessageSeverity@0@AEAY0FB@$$CB_W@Z; Jot::Log_Impl<wchar_t [81],>(ulong,uint,Jot::LogMessageSeverity,wchar_t const (&)[81])
0x180028350  nop
0x180028351  jmp     short loc_18002836B
0x180028353  xor     esi, esi
0x180028355  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028359  mov     ebx, 10064h
0x18002835e  mov     r14, [rsp+11F8h+var_11A0]
0x180028363  mov     r12, [rsp+11F8h+var_1168]
0x18002836b  mov     r8d, 2; unsigned int
0x180028371  mov     edx, ebx; unsigned int
0x180028373  mov     r15d, 4C0648h
0x180028379  mov     ecx, r15d; this
0x18002837c  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x180028381  test    al, al
0x180028383  jz      short loc_1800283AB
0x180028385  call    ?GetCurrentTick@CFileTimeAPIs@MsoCF@@SA_KXZ; MsoCF::CFileTimeAPIs::GetCurrentTick(void)
0x18002838a  mov     [rsp+11F8h+var_1180], rax
0x18002838f  lea     rax, [rsp+11F8h+var_1180]
0x180028394  mov     [rsp+11F8h+var_11D8], rax; __int64
0x180028399  lea     r9, aOnmainDllBootS_0; "ONMain.DLL boot started at |0"
0x1800283a0  mov     edx, ebx; unsigned int
0x1800283a2  mov     ecx, r15d; this
0x1800283a5  call    ??$Log_Impl@$$BY0BO@_WV?$CTickCountBase@UCFileTimeAPIs@MsoCF@@@MsoCF@@@Jot@@YAXKIW4LogMessageSeverity@0@AEAY0BO@$$CB_WAEBV?$CTickCountBase@UCFileTimeAPIs@MsoCF@@@MsoCF@@@Z; Jot::Log_Impl<wchar_t [30],MsoCF::CTickCountBase<MsoCF::CFileTimeAPIs>>(ulong,uint,Jot::LogMessageSeverity,wchar_t const (&)[30],MsoCF::CTickCountBase<MsoCF::CFileTimeAPIs> const &)
0x1800283aa  nop
0x1800283ab  jmp     short loc_1800283C0
0x1800283ad  xor     esi, esi
0x1800283af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800283b3  mov     r14, [rsp+11F8h+var_11A0]
0x1800283b8  mov     r12, [rsp+11F8h+var_1168]
0x1800283c0  lea     rax, ?OnErrorExceptionThrow@Jot@@YAXPEAUIError@MsoCF@@_K@Z; Jot::OnErrorExceptionThrow(MsoCF::IError *,unsigned __int64)
0x1800283c7  mov     cs:qword_1815100C0, rax
0x1800283ce  lea     rcx, ?g_prspi@PropertySpace_JotMain@Jot@@3UPropertySpaceInfo@MsoCF@@B; this
0x1800283d5  call    ?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z; MsoCF::RegisterPropertySpace(MsoCF::PropertySpaceInfo const *)
0x1800283da  lea     rcx, ?g_prspi@PropertySpace_Jot11@Jot@@3UPropertySpaceInfo@MsoCF@@B; this
0x1800283e1  call    ?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z; MsoCF::RegisterPropertySpace(MsoCF::PropertySpaceInfo const *)
0x1800283e6  lea     rcx, ?g_prspi@PropertySpace_Jot14@Jot@@3UPropertySpaceInfo@MsoCF@@B; this
0x1800283ed  call    ?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z; MsoCF::RegisterPropertySpace(MsoCF::PropertySpaceInfo const *)
0x1800283f2  lea     rcx, ?g_prspi@PropertySpace_Jot_1@Jot@@3UPropertySpaceInfo@MsoCF@@B; this
0x1800283f9  call    ?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z; MsoCF::RegisterPropertySpace(MsoCF::PropertySpaceInfo const *)
0x1800283fe  mov     rcx, r14; this
0x180028401  call    ?InitActions@CMainApp@Jot@@QEAAXXZ; Jot::CMainApp::InitActions(void)
0x180028406  cmp     cs:?s_spEventManager@Jot@@3V?$COwnerPtr@VCEventManager@Jot@@V?$COwnerPtr_Delete_Auto@VCEventManager@Jot@@@MsoCF@@@MsoCF@@A, rsi; MsoCF::COwnerPtr<Jot::CEventManager,MsoCF::COwnerPtr_Delete_Auto<Jot::CEventManager>> Jot::s_spEventManager
0x18002840d  jnz     short loc_180028457
0x18002840f  mov     ecx, 570h; this
0x180028414  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180028419  mov     rbx, rax
0x18002841c  mov     [rsp+11F8h+var_1180], rax
0x180028421  test    rax, rax
0x180028424  jz      short loc_18002844C
0x180028426  lea     rax, ??1?$TArray@UCharFormatProp@CHTMLExporter@Jot@@@Ofc@@QEAA@XZ; Ofc::TArray<Jot::CHTMLExporter::CharFormatProp>::~TArray<Jot::CHTMLExporter::CharFormatProp>(void)
0x18002842d  mov     [rsp+11F8h+var_11D8], rax; void (*)(void *)
0x180028432  lea     r9, ??0?$CArray@UEventSinkInfo@Jot@@@MsoCF@@QEAA@XZ; void (*)(void *)
0x180028439  mov     edx, 10h; unsigned __int64
0x18002843e  lea     r8d, [rdx+47h]; unsigned __int64
0x180028442  mov     rcx, rbx; void *
0x180028445  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002844a  jmp     short loc_18002844F
0x18002844c  mov     rbx, rsi
0x18002844f  mov     rdx, rbx
0x180028452  call    ?Attach@?$COwnerPtr@VCEventManager@Jot@@V?$COwnerPtr_Delete_Auto@VCEventManager@Jot@@@MsoCF@@@MsoCF@@QEAAXPEAVCEventManager@Jot@@@Z; MsoCF::COwnerPtr<Jot::CEventManager,MsoCF::COwnerPtr_Delete_Auto<Jot::CEventManager>>::Attach(Jot::CEventManager *)
0x180028457  call    cs:__imp_?FormattedTextInit@FormattedText@Mso@@YA_NXZ; Mso::FormattedText::FormattedTextInit(void)
0x18002845d  mov     dl, 1; bool
0x18002845f  xor     ecx, ecx; bool
0x180028461  call    ?BeginForThread@CBackgroundScheduler@Jot@@SAX_N0@Z; Jot::CBackgroundScheduler::BeginForThread(bool,bool)
0x180028466  call    ?CreateInstance@?$CJotComObject@VCLoggingTagResetOnRegistryModification@Jot@@VCAllocatorOnNew@MsoCF@@@MsoCF@@SAPEAVCLoggingTagResetOnRegistryModification@Jot@@AEAVCAllocatorOnNew@2@_N@Z; MsoCF::CJotComObject<Jot::CLoggingTagResetOnRegistryModification,MsoCF::CAllocatorOnNew>::CreateInstance(MsoCF::CAllocatorOnNew &,bool)
0x18002846b  mov     rbx, rax
0x18002846e  test    rax, rax
0x180028471  jz      short loc_180028483
0x180028473  mov     rax, [rax]
0x180028476  mov     rcx, rbx
0x180028479  mov     rax, [rax+8]
0x18002847d  call    cs:__guard_dispatch_icall_fptr
0x180028483  mov     rcx, cs:qword_1815011D8
0x18002848a  mov     cs:qword_1815011D8, rbx
0x180028491  test    rcx, rcx
0x180028494  jz      short loc_1800284AA
0x180028496  mov     rax, [rcx]
0x180028499  mov     rax, [rax+10h]
0x18002849d  call    cs:__guard_dispatch_icall_fptr
0x1800284a3  mov     rbx, cs:qword_1815011D8
0x1800284aa  mov     rax, [rbx]
0x1800284ad  xor     r8d, r8d
0x1800284b0  lea     rdx, ?vmsoridOneNoteLoggingHook@@3U_msoreg@@B; _msoreg const vmsoridOneNoteLoggingHook
0x1800284b7  mov     rcx, rbx
0x1800284ba  mov     rax, [rax+90h]
0x1800284c1  call    cs:__guard_dispatch_icall_fptr
0x1800284c7  mov     ecx, 88h; this
0x1800284cc  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800284d1  mov     rbx, rax
0x1800284d4  mov     [rsp+11F8h+var_1180], rax
0x1800284d9  test    rax, rax
0x1800284dc  jz      short loc_1800284F2
0x1800284de  mov     rcx, rax; this
0x1800284e1  call    ??0CAsyncManagerBase@Jot@@QEAA@XZ; Jot::CAsyncManagerBase::CAsyncManagerBase(void)
0x1800284e6  lea     rax, ??_7CAsyncManager@Jot@@6B@; const Jot::CAsyncManager::`vftable'
0x1800284ed  mov     [rbx], rax
0x1800284f0  jmp     short loc_1800284F5
0x1800284f2  mov     rbx, rsi
0x1800284f5  test    rbx, rbx
0x1800284f8  jz      short loc_18002850A
0x1800284fa  mov     rax, [rbx]
0x1800284fd  mov     rcx, rbx
0x180028500  mov     rax, [rax]
0x180028503  call    cs:__guard_dispatch_icall_fptr
0x180028509  nop
0x18002850a  mov     rcx, [r14+230h]
0x180028511  mov     [r14+230h], rbx
0x180028518  test    rcx, rcx
0x18002851b  jz      short loc_18002852B
0x18002851d  mov     rax, [rcx]
0x180028520  mov     rax, [rax+8]
0x180028524  call    cs:__guard_dispatch_icall_fptr
0x18002852a  nop
0x18002852b  call    ?InitializeApp@SystemStateTracker@Jot@@YAXXZ; Jot::SystemStateTracker::InitializeApp(void)
0x180028530  call    ?Initialize@LiveSyncIdleTracker@Jot@@YAXXZ; Jot::LiveSyncIdleTracker::Initialize(void)
0x180028535  lea     rcx, off_18150F328; this
0x18002853c  call    ?Start@CrashCounter@SafeBoot@Jot@@QEAAXXZ; Jot::SafeBoot::CrashCounter::Start(void)
0x180028541  lea     rcx, off_1815011B0; this
0x180028548  call    ?Start@CrashCounter@SafeBoot@Jot@@QEAAXXZ; Jot::SafeBoot::CrashCounter::Start(void)
0x18002854d  mov     al, cs:byte_18150F318
0x180028553  test    al, al
0x180028555  js      short loc_18002855C
0x180028557  setnz   al
0x18002855a  jmp     short loc_180028569
0x18002855c  lea     rcx, byte_18150F318
0x180028563  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x180028569  test    al, al
0x18002856b  jnz     loc_180028602
0x180028571  call    ?UserContentServiceAllowed@Privacy@OneNote@@YA_NXZ; OneNote::Privacy::UserContentServiceAllowed(void)
0x180028576  test    al, al
0x180028578  jz      loc_180028602
0x18002857e  lea     rcx, [rsp+11F8h+var_1190]
0x180028583  call    ??$make_shared@VAuthSIGSHandler@SIGSEventLogger@OneNote@@$$V@std@@YA?AV?$shared_ptr@VAuthSIGSHandler@SIGSEventLogger@OneNote@@@0@XZ; std::make_shared<OneNote::SIGSEventLogger::AuthSIGSHandler,>(void)
0x180028588  nop
0x180028589  lea     rdx, [rsp+11F8h+var_1190]
0x18002858e  lea     rcx, [rsp+11F8h+var_1180]
0x180028593  call    ??$make_unique@VCSIGSLogger@SIGSEventLogger@OneNote@@AEAV?$shared_ptr@VAuthSIGSHandler@SIGSEventLogger@OneNote@@@std@@$0A@@std@@YA?AV?$unique_ptr@VCSIGSLogger@SIGSEventLogger@OneNote@@U?$default_delete@VCSIGSLogger@SIGSEventLogger@OneNote@@@std@@@0@AEAV?$shared_ptr@VAuthSIGSHandler@SIGSEventLogger@OneNote@@@0@@Z; std::make_unique<OneNote::SIGSEventLogger::CSIGSLogger,std::shared_ptr<OneNote::SIGSEventLogger::AuthSIGSHandler> &,0>(std::shared_ptr<OneNote::SIGSEventLogger::AuthSIGSHandler> &)
0x180028598  lea     rcx, [r14+0C0h]
0x18002859f  mov     rdx, rax
0x1800285a2  call    ??$?4U?$default_delete@VCSIGSLogger@SIGSEventLogger@OneNote@@@std@@$0A@@?$unique_ptr@VCSIGSLogger@SIGSEventLogger@OneNote@@U?$default_delete@VCSIGSLogger@SIGSEventLogger@OneNote@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>::operator=<std::default_delete<OneNote::SIGSEventLogger::CSIGSLogger>,0>(std::unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger> &&)
0x1800285a7  lea     rcx, [rsp+11F8h+var_1180]
0x1800285ac  call    ??1?$unique_ptr@VCSIGSLogger@SIGSEventLogger@OneNote@@U?$default_delete@VCSIGSLogger@SIGSEventLogger@OneNote@@@std@@@std@@QEAA@XZ; std::unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>::~unique_ptr<OneNote::SIGSEventLogger::CSIGSLogger>(void)
0x1800285b1  lea     rcx, [rsp+11F8h+var_1180]
0x1800285b6  call    ??$make_shared@VCSIGSTrigger@SIGSEventTrigger@Jot@@$$V@std@@YA?AV?$shared_ptr@VCSIGSTrigger@SIGSEventTrigger@Jot@@@0@XZ; std::make_shared<Jot::SIGSEventTrigger::CSIGSTrigger,>(void)
0x1800285bb  lea     rcx, [r14+0C8h]
  ... truncated ...
```
