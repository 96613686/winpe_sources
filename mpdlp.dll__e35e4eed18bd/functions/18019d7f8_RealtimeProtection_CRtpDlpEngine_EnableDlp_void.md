# RealtimeProtection::CRtpDlpEngine::EnableDlp(void)

- ea: `0x18019d7f8`
- end: `0x18019e5e6`
- name: `?EnableDlp@CRtpDlpEngine@RealtimeProtection@@QEAAJXZ`
- size: `3566`
- prototype: `__int64 __fastcall(RealtimeProtection::CRtpDlpEngine *__hidden this)`
- caller_count: `1`
- callee_count: `68`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180143ef0`

## callees

- `0x180005c28`
- `0x180008ec8`
- `0x18001ec00`
- `0x18001fc30`
- `0x180022050`
- `0x180022070`
- `0x180028d80`
- `0x180029830`
- `0x180034420`
- `0x180038450`
- `0x18003ee0c`
- `0x180054320`
- `0x1800543e0`
- `0x180068cd0`
- `0x180079c34`
- `0x180079dc0`
- `0x18007a790`
- `0x18007aebc`
- `0x18007b130`
- `0x18007ba1c`
- `0x18007bbfc`
- `0x18007c09c`
- `0x18007c40c`
- `0x18007c518`
- `0x18007c86c`
- `0x18007d5bc`
- `0x18007d76c`
- `0x1800809d0`
- `0x180088d30`
- `0x1800890e0`
- `0x180089510`
- `0x180094e70`
- `0x180096a40`
- `0x1800984f0`
- `0x18009d558`
- `0x18009f730`
- `0x1800ab660`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x1800c96e8`
- `0x180104b10`
- `0x18010a18c`
- `0x18010ce3c`
- `0x18010ce44`
- `0x18014edf8`
- `0x18015bee8`
- `0x180161464`
- `0x18016a8d4`
- `0x18019d7f8`
- `0x18019fa0c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d8cb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d913`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d962`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019dec9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d8cb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d913`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019d962`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18019dec9`
- `KERNEL32!GetTickCount64` at `0x18019e269`
- `KERNEL32!GetTickCount64` at `0x18019e269`

## string_xrefs

- `0x18019e08c`: `DLP::DlpUserAgent features value (adjusted): %lx`
- `0x18019e064`: `DLP::DlpUserAgent features value (featureControl): %lx`
- `0x18019dc1b`: `%programData%\Microsoft\Windows Defender\DLPCache\LLMContent`
- `0x18019dc8b`: `%programData%\Microsoft\Windows Defender\DLPCache\PublishingLicenses`
- `0x18019da26`: `AutoInjectEnforcementDll failed with HRESULT %#lx.`
- `0x18019da6d`: `ReadAppEnlightenmentConfig failed with HRESULT %#lx.`
- `0x18019db5a`: `CreateDlpCacheDirectories() Failed to create the dlp cache directories. hr %#lx.`
- `0x18019ddfe`: `ReadFileEvidenceConfig failed with HRESULT %#lx.`
- `0x18019de5a`: `ReadPasteToBrowserConfig failed with HRESULT %#lx.`
- `0x18019dea9`: `ReadPauseResumeConfig failed with HRESULT %#lx.`
- `0x18019dbab`: `%programData%\Microsoft\Windows Defender\DLPCache\SensitiveBuffer`
- `0x18019dcfb`: `%programData%\Microsoft\Windows Defender\DLPCache\FileEvidence`
- `0x18019e371`: `StartTenantLabelIdCacheTimer failed with HRESULT %#lx.`
- `0x18019e37d`: `%programData%\Microsoft\Windows Defender\DLPCache\RMSLabels`
- `0x18019e408`: `DlpRmsLabelCache::LoadFromCacheFolder failed with HRESULT %#lx.`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::EnableDlp(
        RealtimeProtection::CRtpDlpEngine *this,
        const wchar_t *a2)
{
  RealtimeProtection::DlpPlugin *v3; // rcx
  const wchar_t *v4; // rbx
  RealtimeProtection::CRtpDlpEngine *v5; // rcx
  RealtimeProtection::CDlpFilterManager *FilterManager; // rdi
  int v7; // eax
  EndpointDlp::Client *v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  bool v12; // dl
  RealtimeProtection::DlpProcessCache *v13; // rcx
  int v14; // eax
  unsigned int v15; // edx
  int v16; // eax
  unsigned int *v17; // rdx
  unsigned int v18; // edi
  int AppEnlightenmentConfig; // eax
  RealtimeProtection::DlpCloudConfig *v20; // rcx
  unsigned int v21; // edi
  int Instance; // eax
  bool *v23; // r9
  int v24; // eax
  bool *v25; // rdx
  int NetworkEnforcementState; // eax
  unsigned int *v27; // rdx
  bool v28; // r8
  int v29; // eax
  RealtimeProtection::DlpEngineUtils *v30; // rcx
  int DlpCacheDirectories; // eax
  const struct std::nothrow_t *v32; // rdx
  const wchar_t *v33; // r8
  char v34; // di
  void **v35; // rdi
  int v36; // eax
  const struct std::nothrow_t *v37; // rdx
  const wchar_t *v38; // r8
  char v39; // di
  void **v40; // rdi
  int v41; // eax
  const struct std::nothrow_t *v42; // rdx
  const wchar_t *v43; // r8
  char v44; // di
  void **v45; // rdi
  int v46; // eax
  const struct std::nothrow_t *v47; // rdx
  const wchar_t *v48; // r8
  char v49; // di
  void **v50; // rdi
  int v51; // eax
  const wchar_t *v52; // rdx
  unsigned int v53; // r15d
  unsigned int *v54; // rdx
  int FileEvidenceConfig; // eax
  unsigned int v56; // ebx
  int PasteToBrowserConfig; // eax
  unsigned int *v58; // r9
  unsigned int v59; // ebx
  int PauseResumeConfig; // eax
  RealtimeProtection::DlpEngineUtils *v61; // rcx
  unsigned int v62; // ebx
  RealtimeProtection::DlpEngineUtils *v63; // rcx
  int v64; // eax
  RealtimeProtection::DlpEngineUtils *v65; // rcx
  struct RealtimeProtection::DlpCEngine **v66; // rdx
  int IsIconOverlayEnabled; // eax
  unsigned int v68; // edx
  RealtimeProtection::DlpEngineUtils *v69; // rcx
  char v70; // bl
  int v71; // eax
  const wchar_t *v72; // r9
  RealtimeProtection::DlpEngineUtils *v73; // rcx
  int active; // eax
  _QWORD *v75; // rcx
  __int64 v76; // rdx
  int refreshed; // eax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  unsigned int v81; // ebx
  const wchar_t *FcValue; // rbx
  RealtimeProtection::DlpUtils *v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rbx
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  int v91; // eax
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  PSRWLOCK v95; // r15
  __int64 v96; // rbx
  int v97; // eax
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // r9
  PSRWLOCK v101; // r15
  int v102; // eax
  void *v103; // rbx
  RealtimeProtection::DlpPlugin *v104; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *PluginWorkItemQueue; // rax
  __int64 v106; // rax
  volatile signed __int32 *v107; // rbx
  RealtimeProtection::DlpPlugin *v108; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *v109; // rax
  PSRWLOCK v110; // rdi
  PSRWLOCK v111; // rdi
  int v112; // ebx
  int started; // edi
  __int64 v114; // rcx
  RealtimeProtection::CRtpDlpEngine *v115; // rcx
  __int64 v116; // rcx
  const wchar_t *v117; // rdx
  int v118; // r9d
  PSRWLOCK SRWLock[2]; // [rsp+A8h] [rbp-80h] BYREF
  _BYTE v121[8]; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v122; // [rsp+C0h] [rbp-68h] BYREF
  int v123; // [rsp+C8h] [rbp-60h] BYREF
  int v124; // [rsp+CCh] [rbp-5Ch] BYREF
  int v125; // [rsp+D0h] [rbp-58h] BYREF
  int v126; // [rsp+D4h] [rbp-54h] BYREF
  int v127; // [rsp+D8h] [rbp-50h] BYREF
  int v128; // [rsp+DCh] [rbp-4Ch] BYREF
  int v129; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v130; // [rsp+E8h] [rbp-40h] BYREF
  __int64 v131; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v132; // [rsp+F8h] [rbp-30h] BYREF
  __int64 v133; // [rsp+100h] [rbp-28h] BYREF
  __int64 v134; // [rsp+108h] [rbp-20h] BYREF
  __int64 v135; // [rsp+110h] [rbp-18h] BYREF
  _BYTE v136[16]; // [rsp+118h] [rbp-10h] BYREF
  wchar_t *v137[4]; // [rsp+128h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"Enter EnableDlp", a2);
  RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(v136, 1, 0xFFFFFFFFLL);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
    SRWLock,
    (char *)this + 16);
  if ( *((_DWORD *)this + 2) == 3 )
  {
    LODWORD(v4) = -2147483635;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147483661LL);
    goto LABEL_25;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    if ( LOBYTE(SRWLock[1]) )
      ReleaseSRWLockExclusive(SRWLock[0]);
    LODWORD(v4) = 1;
    goto LABEL_215;
  }
  FilterManager = RealtimeProtection::DlpPlugin::GetFilterManager(v3);
  if ( !FilterManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
    if ( LOBYTE(SRWLock[1]) )
      ReleaseSRWLockExclusive(SRWLock[0]);
    LODWORD(v4) = -2147483634;
    goto LABEL_215;
  }
  v7 = RealtimeProtection::CRtpDlpEngine::InitializeOnEnable(v5);
  LODWORD(v4) = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 48;
      v11 = (unsigned int)v7;
LABEL_24:
      WPP_SF_d(v9[2], v10, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v11);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  *((_DWORD *)this + 2) = 2;
  *((_DWORD *)this + 18) = 0;
  *((_BYTE *)this + 78) = EndpointDlp::Client::IsAnyFileEnabledForTenant(v8);
  v4 = (const wchar_t *)(unsigned int)RealtimeProtection::CDlpFilterManager::SetDlp(FilterManager, 1);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"Notified filter to set dlp true hr=0x%x.", v4);
  if ( (int)v4 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 49;
      v11 = (unsigned int)v4;
      goto LABEL_24;
    }
LABEL_25:
    if ( LOBYTE(SRWLock[1]) )
      ReleaseSRWLockExclusive(SRWLock[0]);
    goto LABEL_215;
  }
  LOBYTE(v13) = 1;
  v14 = RealtimeProtection::DlpProcessCache::SetQuarantineEngineStatus(v13, v12);
  if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      (unsigned int)v14);
  v16 = RealtimeProtection::DlpInjection::AutoInjectEnforcementDll(
          (RealtimeProtection::DlpInjection *)*((unsigned int *)this + 14),
          v15);
  v18 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v16);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"AutoInjectEnforcementDll failed with HRESULT %#lx.",
      (const wchar_t *)v18);
  }
  *((_BYTE *)this + 69) = 0;
  AppEnlightenmentConfig = RealtimeProtection::DlpEngineUtils::ReadAppEnlightenmentConfig(
                             (RealtimeProtection::CRtpDlpEngine *)((char *)this + 64),
                             v17);
  v21 = AppEnlightenmentConfig;
  if ( AppEnlightenmentConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)AppEnlightenmentConfig);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"ReadAppEnlightenmentConfig failed with HRESULT %#lx.",
      (const wchar_t *)v21);
  }
  Instance = RealtimeProtection::DlpCloudConfig::CreateInstance(v20);
  if ( Instance < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      (unsigned int)Instance);
  v24 = RealtimeProtection::DlpEngineUtils::SetJitStateInRegistry(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 76),
          (bool *)this + 80,
          (unsigned int *)((char *)this + 77),
          v23);
  if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      (unsigned int)v24);
  NetworkEnforcementState = RealtimeProtection::DlpEngineUtils::GetNetworkEnforcementState(
                              (RealtimeProtection::CRtpDlpEngine *)((char *)this + 93),
                              v25);
  if ( NetworkEnforcementState < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      (unsigned int)NetworkEnforcementState);
  }
  LOBYTE(v27) = *((_BYTE *)this + 78);
  v29 = RealtimeProtection::DlpEngineUtils::SetAnyFileStateInRegistry(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 84),
          v27,
          v28);
  if ( v29 < 0 )
  {
    v30 = (RealtimeProtection::DlpEngineUtils *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v29);
  }
  DlpCacheDirectories = RealtimeProtection::DlpEngineUtils::CreateDlpCacheDirectories(v30);
  v34 = DlpCacheDirectories;
  if ( DlpCacheDirectories < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"CreateDlpCacheDirectories() Failed to create the dlp cache directories. hr %#lx.",
      (const wchar_t *)(unsigned int)v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::EnableDlp",
        v34);
  }
  v35 = (void **)((char *)this + 152);
  if ( *((_QWORD *)this + 19) )
  {
    operator delete(*v35, v32);
    *v35 = 0;
  }
  v36 = CommonUtil::UtilExpandEnvironmentStrings(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 152),
          (wchar_t **)L"%programData%\\Microsoft\\Windows Defender\\DLPCache\\SensitiveBuffer",
          v33);
  v39 = v36;
  if ( v36 < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs Failed to expand environment strings hr:0x%x",
      "RealtimeProtection::CRtpDlpEngine::EnableDlp",
      (unsigned int)v36);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::EnableDlp",
        v39);
  }
  v40 = (void **)((char *)this + 160);
  if ( *((_QWORD *)this + 20) )
  {
    operator delete(*v40, v37);
    *v40 = 0;
  }
  v41 = CommonUtil::UtilExpandEnvironmentStrings(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 160),
          (wchar_t **)L"%programData%\\Microsoft\\Windows Defender\\DLPCache\\LLMContent",
          v38);
  v44 = v41;
  if ( v41 < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs Failed to expand environment strings hr:0x%x",
      "RealtimeProtection::CRtpDlpEngine::EnableDlp",
      (unsigned int)v41);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::EnableDlp",
        v44);
  }
  v45 = (void **)((char *)this + 168);
  if ( *((_QWORD *)this + 21) )
  {
    operator delete(*v45, v42);
    *v45 = 0;
  }
  v46 = CommonUtil::UtilExpandEnvironmentStrings(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 168),
          (wchar_t **)L"%programData%\\Microsoft\\Windows Defender\\DLPCache\\PublishingLicenses",
          v43);
  v49 = v46;
  if ( v46 < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::%hs Failed to expand environment strings hr:0x%x",
      "RealtimeProtection::CRtpDlpEngine::EnableDlp",
      (unsigned int)v46);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)"RealtimeProtection::CRtpDlpEngine::EnableDlp",
        v49);
  }
  v50 = (void **)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    operator delete(*v50, v47);
    *v50 = 0;
  }
  v51 = CommonUtil::UtilExpandEnvironmentStrings(
          (RealtimeProtection::CRtpDlpEngine *)((char *)this + 144),
          (wchar_t **)L"%programData%\\Microsoft\\Windows Defender\\DLPCache\\FileEvidence",
          v48);
  v53 = v51;
  if ( v51 >= 0 )
  {
    if ( *v50 )
    {
      if ( (int)RealtimeProtection::DlpFileEvidence::CreateInstance((wchar_t *)*v50, v52) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)v4);
      }
    }
    else
    {
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"DLP::After expand env strings for file evidence get nullptr",
        v52);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
    }
  }
  else
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DLP::Failed to expand environment strings hr:0x%x",
      (const wchar_t *)(unsigned int)v51);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v53);
  }
  FileEvidenceConfig = RealtimeProtection::DlpEngineUtils::ReadFileEvidenceConfig(
                         (RealtimeProtection::CRtpDlpEngine *)((char *)this + 88),
                         v54);
  v56 = FileEvidenceConfig;
  if ( FileEvidenceConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)FileEvidenceConfig);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"ReadFileEvidenceConfig failed with HRESULT %#lx.",
      (const wchar_t *)v56);
  }
  PasteToBrowserConfig = RealtimeProtection::DlpEngineUtils::ReadPasteToBrowserConfig(
                           (RealtimeProtection::CRtpDlpEngine *)((char *)this + 32),
                           (unsigned int *)this + 9,
                           (unsigned int *)this + 10,
                           (unsigned int *)this + 11,
                           (unsigned int *)this + 23);
  v59 = PasteToBrowserConfig;
  if ( PasteToBrowserConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)PasteToBrowserConfig);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"ReadPasteToBrowserConfig failed with HRESULT %#lx.",
      (const wchar_t *)v59);
  }
  PauseResumeConfig = RealtimeProtection::DlpEngineUtils::ReadPauseResumeConfig(
                        (RealtimeProtection::CRtpDlpEngine *)((char *)this + 94),
                        (bool *)this + 100,
                        (unsigned int *)this + 26,
                        v58);
  v62 = PauseResumeConfig;
  if ( PauseResumeConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)PauseResumeConfig);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"ReadPauseResumeConfig failed with HRESULT %#lx.",
      (const wchar_t *)v62);
  }
  RealtimeProtection::DlpEngineUtils::DlpSetCacheConfig(v61);
  RealtimeProtection::DlpEngineUtils::DlpSetCacheFileCloseCount(v63);
  if ( LOBYTE(SRWLock[1]) )
    ReleaseSRWLockExclusive(SRWLock[0]);
  v64 = RealtimeProtection::CRtpDlpEngine::OnSetEngine(this);
  LODWORD(v4) = v64;
  if ( v64 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v64);
    goto LABEL_215;
  }
  RealtimeProtection::DlpEngineUtils::RefreshPolicySettings(v65);
  v121[0] = 0;
  IsIconOverlayEnabled = RealtimeProtection::DlpEngineUtils::GetIsIconOverlayEnabled(
                           (RealtimeProtection::DlpEngineUtils *)v121,
                           v66);
  if ( IsIconOverlayEnabled < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)IsIconOverlayEnabled);
  }
  else
  {
    v70 = v121[0];
    if ( v121[0] )
      v71 = RealtimeProtection::DlpEngineUtils::RegisterDlpIconOverlay(v69);
    else
      v71 = RealtimeProtection::DlpEngineUtils::UnregisterDlpIconOverlay(v69);
    if ( v71 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v72 = L"RegisterDlpIconOverlay()";
        if ( !v70 )
          v72 = L"UnregisterDlpIconOverlay()";
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (_DWORD)v72,
          v71);
      }
    }
    else
    {
      *((_BYTE *)this + 68) = v70;
    }
  }
  v73 = (RealtimeProtection::DlpEngineUtils *)*((unsigned int *)this + 14);
  if ( ((unsigned __int8)v73 & 0x10) != 0 )
  {
    active = RealtimeProtection::DlpEngineUtils::DisableOfficeClipboardForActiveSessions(v73, v68);
    if ( active < 0 )
    {
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v76 = 70;
LABEL_141:
        WPP_SF_d(v75[2], v76, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, (unsigned int)active);
      }
    }
  }
  else
  {
    active = RealtimeProtection::DlpEngineUtils::RestoreOfficeClipboardForActiveSessions(v73);
    if ( active < 0 )
    {
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v76 = 71;
        goto LABEL_141;
      }
    }
  }
  refreshed = RealtimeProtection::CRtpDlpEngine::RefreshSpoolerEnlightenmentState(this);
  v81 = refreshed;
  if ( refreshed < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)refreshed);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"RefreshSpoolerEnlightenmentState failed with HRESULT %#lx.",
      (const wchar_t *)v81);
  }
  FcValue = (const wchar_t *)(unsigned int)RealtimeProtection::DlpPlugin::GetFcValue(57, v78, v79, v80);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::DlpUserAgent features value (featureControl): %lx",
    FcValue);
  v83 = (RealtimeProtection::DlpUtils *)(unsigned int)FcValue;
  if ( ((unsigned __int8)FcValue & 3) == 1 )
  {
    LOBYTE(v83) = (unsigned __int8)FcValue & 3;
    if ( RealtimeProtection::DlpUtils::IsWindowsServer(v83) )
      LODWORD(FcValue) = 0;
  }
  _InterlockedExchange((volatile __int32 *)this + 28, (__int32)FcValue);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::DlpUserAgent features value (adjusted): %lx",
    (const wchar_t *)(unsigned int)FcValue);
  _InterlockedExchange((volatile __int32 *)this + 29, RealtimeProtection::DlpPlugin::GetFcValue(83, v84, v85, v86));
  v87 = 900000;
  v91 = RealtimeProtection::DlpPlugin::GetFcValue(174, v88, v89, v90);
  if ( v91 )
    v87 = (unsigned int)(1000 * v91);
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent>>(SRWLock);
  v95 = SRWLock[0];
  if ( SRWLock[0] )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)&SRWLock[0][1]);
    v95->Ptr = (PVOID)v87;
    Mtx_unlock((_Mtx_t)&v95[1]);
  }
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  v96 = 15000;
  v97 = RealtimeProtection::DlpPlugin::GetFcValue(207, v92, v93, v94);
  if ( v97 )
    v96 = (unsigned int)(1000 * v97);
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent>>(SRWLock);
  v101 = SRWLock[0];
  if ( SRWLock[0] )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)&SRWLock[0][1]);
    v101->Ptr = (PVOID)v96;
    Mtx_unlock((_Mtx_t)&v101[1]);
  }
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  v122 = 43200000;
  v102 = RealtimeProtection::DlpPlugin::GetFcValue(216, v98, v99, v100);
  if ( v102 )
    v122 = (unsigned int)(1000 * v102);
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>>(SRWLock);
  if ( SRWLock[0] )
    RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>::set_throttle_timeout(
      SRWLock[0],
      &v122);
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  if ( (*((_DWORD *)this + 28) & 1) != 0 )
  {
    v103 = operator new(0x58u);
    memset(v103, 0, 0x58u);
    PluginWorkItemQueue = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v104);
    v106 = RealtimeProtection::CDlpUserAgentWorkItem::CDlpUserAgentWorkItem(
             (RealtimeProtection::CDlpUserAgentWorkItem *)v103,
             PluginWorkItemQueue,
             0,
             0,
             4u);
    if ( v106 )
      _InterlockedAdd((volatile signed __int32 *)(v106 + 8), 1u);
    v122 = v106;
    RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v106, 5);
    CommonUtil::AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>::~AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>(&v122);
  }
  if ( (*((_DWORD *)this + 28) & 1) != 0 && (*((_DWORD *)this + 28) & 8) != 0 )
  {
    v107 = (volatile signed __int32 *)operator new(0x48u);
    memset((void *)v107, 0, 0x48u);
    v109 = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v108);
    RealtimeProtection::CMpPluginWorkItemBase::CMpPluginWorkItemBase(v107, v109, 33);
    *(_QWORD *)v107 = &RealtimeProtection::CDlpLoadUserAgentProcessCacheWorkItem::`vftable';
    _InterlockedAdd(v107 + 2, 1u);
    v122 = (__int64)v107;
    RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v107, 9);
    *((_QWORD *)this + 15) = GetTickCount64();
    CommonUtil::AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>::~AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>(&v122);
  }
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent>>(SRWLock);
  v110 = SRWLock[0];
  if ( SRWLock[0] )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)&SRWLock[0][1]);
    v110->Ptr = (PVOID)3000;
    Mtx_unlock((_Mtx_t)&v110[1]);
  }
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent>>(SRWLock);
  v111 = SRWLock[0];
  if ( SRWLock[0] )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)&SRWLock[0][1]);
    v111->Ptr = (PVOID)2000;
    Mtx_unlock((_Mtx_t)&v111[1]);
  }
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  *(_OWORD *)SRWLock = 0;
  std::atomic_load<MipDlp::MipDlpManagerImpl>(SRWLock);
  v112 = -2147483634;
  if ( SRWLock[0] )
  {
    started = MipDlp::MipDlpManagerImpl::StartTenantLabelIdCacheTimer((MipDlp::MipDlpManagerImpl *)SRWLock[0]);
    if ( SRWLock[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
    if ( started >= 0 )
      goto LABEL_195;
  }
  else
  {
    if ( SRWLock[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
    started = -2147483634;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
      (unsigned int)started);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"StartTenantLabelIdCacheTimer failed with HRESULT %#lx.",
    (const wchar_t *)(unsigned int)started);
LABEL_195:
  std::wstring::wstring(v137, L"%programData%\\Microsoft\\Windows Defender\\DLPCache\\RMSLabels");
  if ( (unsigned __int8)Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::RecallFlags,void,void>(v114, 1) )
  {
    *(_OWORD *)SRWLock = 0;
    std::atomic_load<Dlp::DlpRmsLabelCache::RmsLabelCacheInstance>(SRWLock);
    if ( SRWLock[0] )
      v112 = Dlp::DlpRmsLabelCache::RmsLabelCacheInstance::LoadFromCacheFolder(
               (Dlp::DlpRmsLabelCache::RmsLabelCacheInstance *)SRWLock[0],
               v137);
    if ( SRWLock[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  }
  else
  {
    v112 = 0;
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v137);
  if ( v112 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v112);
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DlpRmsLabelCache::LoadFromCacheFolder failed with HRESULT %#lx.",
      (const wchar_t *)(unsigned int)v112);
  }
  RealtimeProtection::CRtpDlpEngine::SetDlpRenameAndCloseReportInDriver(v115);
  *((_BYTE *)this + 95) = Dlp::FeatureControl::GetFlag<enum Dlp::FeatureControl::QuarantineSettingFlags,void,void>(
                            v116,
                            1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"DLP enabled", v117);
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v137);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      v123 = *((_DWORD *)g_aAsimov + 18);
      v124 = *((_DWORD *)g_aAsimov + 17);
      v125 = *((_DWORD *)g_aAsimov + 16);
      v126 = *((unsigned __int8 *)g_aAsimov + 60);
      v127 = *((unsigned __int8 *)g_aAsimov + 59);
      v128 = *((unsigned __int8 *)g_aAsimov + 58);
      v129 = *((unsigned __int8 *)g_aAsimov + 57);
      LODWORD(v122) = *((unsigned __int8 *)g_aAsimov + 56);
      v130 = *((_QWORD *)g_aAsimov + 6);
      v131 = *((_QWORD *)g_aAsimov + 5);
      v132 = *((_QWORD *)g_aAsimov + 4);
      v133 = *((_QWORD *)g_aAsimov + 3);
      v134 = *((_QWORD *)g_aAsimov + 2);
      v135 = *((_QWORD *)g_aAsimov + 1);
      SRWLock[0] = (PSRWLOCK)0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v118,
        (int)&unk_1802C4340,
        (__int64)SRWLock,
        (__int64)&v135,
        (__int64)&v134,
        (__int64)&v133,
        (__int64)&v132,
        (__int64)&v131,
        (__int64)&v130,
        (__int64)&v122,
        (__int64)&v129,
        (__int64)&v128,
        (__int64)&v127,
        (__int64)&v126,
        (__int64)&v125,
        (__int64)&v124,
        (__int64)&v123);
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v137);
  }
  LODWORD(v4) = 0;
LABEL_215:
  RealtimeProtection::DlpAutoEtwPerfOperation::~DlpAutoEtwPerfOperation((RealtimeProtection::DlpAutoEtwPerfOperation *)v136);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18019d7f8  mov     rax, rsp
0x18019d7fb  mov     [rax+10h], rbx
0x18019d7ff  mov     [rax+18h], rsi
0x18019d803  mov     [rax+20h], rdi
0x18019d807  push    rbp
0x18019d808  push    r12
0x18019d80a  push    r13
0x18019d80c  push    r14
0x18019d80e  push    r15
0x18019d810  lea     rbp, [rax-48h]
0x18019d814  sub     rsp, 140h
0x18019d81b  mov     r14, rcx
0x18019d81e  lea     r13, WPP_GLOBAL_Control
0x18019d825  lea     r15, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18019d82c  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d833  cmp     rcx, r13
0x18019d836  jz      short loc_18019D84F
0x18019d838  test    byte ptr [rcx+1Ch], 4
0x18019d83c  jz      short loc_18019D84F
0x18019d83e  mov     edx, 2Dh ; '-'
0x18019d843  mov     r8, r15
0x18019d846  mov     rcx, [rcx+10h]
0x18019d84a  call    WPP_SF_
0x18019d84f  lea     rcx, aEnterEnabledlp; "Enter EnableDlp"
0x18019d856  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019d85b  xor     r9d, r9d
0x18019d85e  or      r8d, 0FFFFFFFFh
0x18019d862  lea     r12d, [r9+1]
0x18019d866  mov     edx, r12d
0x18019d869  lea     rcx, [rbp+40h+var_50]
0x18019d86d  call    ??0DlpAutoEtwPerfOperation@RealtimeProtection@@QEAA@W4DlpOperationType@@W4MpDlpOnOperationActionType@@W4DlpFileAccessCheckType@@@Z; RealtimeProtection::DlpAutoEtwPerfOperation::DlpAutoEtwPerfOperation(DlpOperationType,MpDlpOnOperationActionType,DlpFileAccessCheckType)
0x18019d872  lea     rdx, [r14+10h]
0x18019d876  lea     rcx, [rbp+40h+SRWLock]
0x18019d87a  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x18019d87f  cmp     dword ptr [r14+8], 3
0x18019d884  jnz     short loc_18019D8B8
0x18019d886  mov     ebx, 8000000Dh
0x18019d88b  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d892  cmp     rcx, r13
0x18019d895  jz      short loc_18019D8B1
0x18019d897  test    [rcx+1Ch], r12b
0x18019d89b  jz      short loc_18019D8B1
0x18019d89d  lea     edx, [r12+2Dh]
0x18019d8a2  mov     r9d, ebx
0x18019d8a5  mov     r8, r15
0x18019d8a8  mov     rcx, [rcx+10h]
0x18019d8ac  call    WPP_SF_d
0x18019d8b1  xor     esi, esi
0x18019d8b3  jmp     loc_18019D954
0x18019d8b8  cmp     dword ptr [r14+8], 2
0x18019d8bd  jnz     short loc_18019D8D9
0x18019d8bf  xor     esi, esi
0x18019d8c1  cmp     byte ptr [rbp+40h+SRWLock+8], sil
0x18019d8c5  jz      short loc_18019D8D1
0x18019d8c7  mov     rcx, [rbp+40h+SRWLock]; SRWLock
0x18019d8cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18019d8d1  mov     ebx, r12d
0x18019d8d4  jmp     loc_18019E5BA
0x18019d8d9  call    ?GetFilterManager@DlpPlugin@RealtimeProtection@@YAPEAVCDlpFilterManager@2@XZ; RealtimeProtection::DlpPlugin::GetFilterManager(void)
0x18019d8de  mov     rdi, rax
0x18019d8e1  xor     esi, esi
0x18019d8e3  test    rax, rax
0x18019d8e6  jnz     short loc_18019D923
0x18019d8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d8ef  cmp     rcx, r13
0x18019d8f2  jz      short loc_18019D909
0x18019d8f4  test    [rcx+1Ch], r12b
0x18019d8f8  jz      short loc_18019D909
0x18019d8fa  lea     edx, [rax+2Fh]
0x18019d8fd  mov     r8, r15
0x18019d900  mov     rcx, [rcx+10h]
0x18019d904  call    WPP_SF_
0x18019d909  cmp     byte ptr [rbp+40h+SRWLock+8], sil
0x18019d90d  jz      short loc_18019D919
0x18019d90f  mov     rcx, [rbp+40h+SRWLock]; SRWLock
0x18019d913  call    cs:__imp_ReleaseSRWLockExclusive
0x18019d919  mov     ebx, 8000000Eh
0x18019d91e  jmp     loc_18019E5BA
0x18019d923  call    ?InitializeOnEnable@CRtpDlpEngine@RealtimeProtection@@AEAAJXZ; RealtimeProtection::CRtpDlpEngine::InitializeOnEnable(void)
0x18019d928  mov     ebx, eax
0x18019d92a  test    eax, eax
0x18019d92c  jns     short loc_18019D96D
0x18019d92e  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d935  cmp     rcx, r13
0x18019d938  jz      short loc_18019D954
0x18019d93a  test    [rcx+1Ch], r12b
0x18019d93e  jz      short loc_18019D954
0x18019d940  mov     edx, 30h ; '0'
0x18019d945  mov     r9d, eax
0x18019d948  mov     r8, r15
0x18019d94b  mov     rcx, [rcx+10h]
0x18019d94f  call    WPP_SF_d
0x18019d954  cmp     byte ptr [rbp+40h+SRWLock+8], sil
0x18019d958  jz      loc_18019E5BA
0x18019d95e  mov     rcx, [rbp+40h+SRWLock]; SRWLock
0x18019d962  call    cs:__imp_ReleaseSRWLockExclusive
0x18019d968  jmp     loc_18019E5BA
0x18019d96d  mov     dword ptr [r14+8], 2
0x18019d975  mov     [r14+48h], esi
0x18019d979  call    ?IsAnyFileEnabledForTenant@Client@EndpointDlp@@YA_NXZ; EndpointDlp::Client::IsAnyFileEnabledForTenant(void)
0x18019d97e  mov     [r14+4Eh], al
0x18019d982  mov     dl, r12b; bool
0x18019d985  mov     rcx, rdi; this
0x18019d988  call    ?SetDlp@CDlpFilterManager@RealtimeProtection@@QEAAJ_N@Z; RealtimeProtection::CDlpFilterManager::SetDlp(bool)
0x18019d98d  mov     ebx, eax
0x18019d98f  mov     edx, eax; wchar_t *
0x18019d991  lea     rcx, aNotifiedFilter; "Notified filter to set dlp true hr=0x%x"...
0x18019d998  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019d99d  test    ebx, ebx
0x18019d99f  jns     short loc_18019D9BD
0x18019d9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d9a8  cmp     rcx, r13
0x18019d9ab  jz      short loc_18019D954
0x18019d9ad  test    [rcx+1Ch], r12b
0x18019d9b1  jz      short loc_18019D954
0x18019d9b3  mov     edx, 31h ; '1'
0x18019d9b8  mov     r9d, ebx
0x18019d9bb  jmp     short loc_18019D948
0x18019d9bd  mov     cl, r12b; this
0x18019d9c0  call    ?SetQuarantineEngineStatus@DlpProcessCache@RealtimeProtection@@YAJ_N@Z; RealtimeProtection::DlpProcessCache::SetQuarantineEngineStatus(bool)
0x18019d9c5  test    eax, eax
0x18019d9c7  jns     short loc_18019D9EF
0x18019d9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d9d0  cmp     rcx, r13
0x18019d9d3  jz      short loc_18019D9EF
0x18019d9d5  test    [rcx+1Ch], r12b
0x18019d9d9  jz      short loc_18019D9EF
0x18019d9db  mov     edx, 32h ; '2'
0x18019d9e0  mov     r9d, eax
0x18019d9e3  mov     r8, r15
0x18019d9e6  mov     rcx, [rcx+10h]
0x18019d9ea  call    WPP_SF_d
0x18019d9ef  mov     ecx, [r14+38h]; this
0x18019d9f3  call    ?AutoInjectEnforcementDll@DlpInjection@RealtimeProtection@@YAJK@Z; RealtimeProtection::DlpInjection::AutoInjectEnforcementDll(ulong)
0x18019d9f8  mov     edi, eax
0x18019d9fa  test    eax, eax
0x18019d9fc  jns     short loc_18019DA32
0x18019d9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18019da05  cmp     rcx, r13
0x18019da08  jz      short loc_18019DA24
0x18019da0a  test    [rcx+1Ch], r12b
0x18019da0e  jz      short loc_18019DA24
0x18019da10  mov     edx, 33h ; '3'
0x18019da15  mov     r9d, eax
0x18019da18  mov     r8, r15
0x18019da1b  mov     rcx, [rcx+10h]
0x18019da1f  call    WPP_SF_d
0x18019da24  mov     edx, edi; wchar_t *
0x18019da26  lea     rcx, aAutoinjectenfo; "AutoInjectEnforcementDll failed with HR"...
0x18019da2d  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019da32  mov     [r14+45h], sil
0x18019da36  lea     rcx, [r14+40h]; this
0x18019da3a  call    ?ReadAppEnlightenmentConfig@DlpEngineUtils@RealtimeProtection@@YAJAEAK@Z; RealtimeProtection::DlpEngineUtils::ReadAppEnlightenmentConfig(ulong &)
0x18019da3f  mov     edi, eax
0x18019da41  test    eax, eax
0x18019da43  jns     short loc_18019DA79
0x18019da45  mov     rcx, cs:WPP_GLOBAL_Control
0x18019da4c  cmp     rcx, r13
0x18019da4f  jz      short loc_18019DA6B
0x18019da51  test    [rcx+1Ch], r12b
0x18019da55  jz      short loc_18019DA6B
0x18019da57  mov     edx, 34h ; '4'
0x18019da5c  mov     r9d, eax
0x18019da5f  mov     r8, r15
0x18019da62  mov     rcx, [rcx+10h]
0x18019da66  call    WPP_SF_d
0x18019da6b  mov     edx, edi; wchar_t *
0x18019da6d  lea     rcx, aReadappenlight; "ReadAppEnlightenmentConfig failed with "...
0x18019da74  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019da79  call    ?CreateInstance@DlpCloudConfig@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpCloudConfig::CreateInstance(void)
0x18019da7e  test    eax, eax
0x18019da80  jns     short loc_18019DAA8
0x18019da82  mov     rcx, cs:WPP_GLOBAL_Control
0x18019da89  cmp     rcx, r13
0x18019da8c  jz      short loc_18019DAA8
0x18019da8e  test    [rcx+1Ch], r12b
0x18019da92  jz      short loc_18019DAA8
0x18019da94  mov     edx, 35h ; '5'
0x18019da99  mov     r9d, eax
0x18019da9c  mov     r8, r15
0x18019da9f  mov     rcx, [rcx+10h]
0x18019daa3  call    WPP_SF_d
0x18019daa8  lea     r8, [r14+4Dh]; unsigned int *
0x18019daac  lea     rdx, [r14+50h]; bool *
0x18019dab0  lea     rcx, [r14+4Ch]; this
0x18019dab4  call    ?SetJitStateInRegistry@DlpEngineUtils@RealtimeProtection@@YAJAEA_NAEAK0@Z; RealtimeProtection::DlpEngineUtils::SetJitStateInRegistry(bool &,ulong &,bool &)
0x18019dab9  test    eax, eax
0x18019dabb  jns     short loc_18019DAE3
0x18019dabd  mov     rcx, cs:WPP_GLOBAL_Control
0x18019dac4  cmp     rcx, r13
0x18019dac7  jz      short loc_18019DAE3
0x18019dac9  test    [rcx+1Ch], r12b
0x18019dacd  jz      short loc_18019DAE3
0x18019dacf  mov     edx, 36h ; '6'
0x18019dad4  mov     r9d, eax
0x18019dad7  mov     r8, r15
0x18019dada  mov     rcx, [rcx+10h]
0x18019dade  call    WPP_SF_d
0x18019dae3  lea     rcx, [r14+5Dh]; this
0x18019dae7  call    ?GetNetworkEnforcementState@DlpEngineUtils@RealtimeProtection@@YAJAEA_N@Z; RealtimeProtection::DlpEngineUtils::GetNetworkEnforcementState(bool &)
0x18019daec  test    eax, eax
0x18019daee  jns     short loc_18019DB16
0x18019daf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18019daf7  cmp     rcx, r13
0x18019dafa  jz      short loc_18019DB16
0x18019dafc  test    [rcx+1Ch], r12b
0x18019db00  jz      short loc_18019DB16
0x18019db02  mov     edx, 37h ; '7'
0x18019db07  mov     r9d, eax
0x18019db0a  mov     r8, r15
0x18019db0d  mov     rcx, [rcx+10h]
0x18019db11  call    WPP_SF_d
0x18019db16  lea     rcx, [r14+54h]; this
0x18019db1a  mov     dl, [r14+4Eh]; unsigned int *
0x18019db1e  call    ?SetAnyFileStateInRegistry@DlpEngineUtils@RealtimeProtection@@YAJAEAK_N@Z; RealtimeProtection::DlpEngineUtils::SetAnyFileStateInRegistry(ulong &,bool)
0x18019db23  test    eax, eax
0x18019db25  jns     short loc_18019DB4D
0x18019db27  mov     rcx, cs:WPP_GLOBAL_Control
0x18019db2e  cmp     rcx, r13
0x18019db31  jz      short loc_18019DB4D
0x18019db33  test    [rcx+1Ch], r12b
0x18019db37  jz      short loc_18019DB4D
0x18019db39  mov     edx, 38h ; '8'
0x18019db3e  mov     r9d, eax
0x18019db41  mov     r8, r15
0x18019db44  mov     rcx, [rcx+10h]
0x18019db48  call    WPP_SF_d
0x18019db4d  call    ?CreateDlpCacheDirectories@DlpEngineUtils@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpEngineUtils::CreateDlpCacheDirectories(void)
0x18019db52  mov     edi, eax
0x18019db54  test    eax, eax
0x18019db56  jns     short loc_18019DB94
0x18019db58  mov     edx, ebx; wchar_t *
0x18019db5a  lea     rcx, aCreatedlpcache; "CreateDlpCacheDirectories() Failed to c"...
0x18019db61  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019db66  mov     rcx, cs:WPP_GLOBAL_Control
0x18019db6d  cmp     rcx, r13
0x18019db70  jz      short loc_18019DB94
0x18019db72  test    [rcx+1Ch], r12b
0x18019db76  jz      short loc_18019DB94
0x18019db78  mov     edx, 39h ; '9'
0x18019db7d  mov     dword ptr [rsp+160h+var_140], edi
0x18019db81  lea     r9, aRealtimeprotec_16; "RealtimeProtection::CRtpDlpEngine::Enab"...
0x18019db88  mov     r8, r15
0x18019db8b  mov     rcx, [rcx+10h]
0x18019db8f  call    WPP_SF_sd
0x18019db94  lea     rdi, [r14+98h]
0x18019db9b  cmp     [rdi], rsi
0x18019db9e  jz      short loc_18019DBAB
0x18019dba0  mov     rcx, [rdi]; void *
0x18019dba3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019dba8  mov     [rdi], rsi
0x18019dbab  lea     rdx, aProgramdataMic_1; "%programData%\\Microsoft\\Windows Defen"...
0x18019dbb2  mov     rcx, rdi; this
0x18019dbb5  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilExpandEnvironmentStrings(wchar_t * *,wchar_t const *)
0x18019dbba  mov     edi, eax
0x18019dbbc  test    eax, eax
0x18019dbbe  jns     short loc_18019DC04
0x18019dbc0  mov     r8d, eax
0x18019dbc3  lea     rdx, aRealtimeprotec_16; "RealtimeProtection::CRtpDlpEngine::Enab"...
0x18019dbca  lea     rcx, aDlpHsFailedToE; "DLP::%hs Failed to expand environment s"...
0x18019dbd1  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019dbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18019dbdd  cmp     rcx, r13
0x18019dbe0  jz      short loc_18019DC04
0x18019dbe2  test    [rcx+1Ch], r12b
0x18019dbe6  jz      short loc_18019DC04
0x18019dbe8  mov     edx, 3Ah ; ':'
0x18019dbed  mov     dword ptr [rsp+160h+var_140], edi
0x18019dbf1  lea     r9, aRealtimeprotec_16; "RealtimeProtection::CRtpDlpEngine::Enab"...
0x18019dbf8  mov     r8, r15
0x18019dbfb  mov     rcx, [rcx+10h]
0x18019dbff  call    WPP_SF_sd
0x18019dc04  lea     rdi, [r14+0A0h]
0x18019dc0b  cmp     [rdi], rsi
0x18019dc0e  jz      short loc_18019DC1B
0x18019dc10  mov     rcx, [rdi]; void *
0x18019dc13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019dc18  mov     [rdi], rsi
0x18019dc1b  lea     rdx, aProgramdataMic_5; "%programData%\\Microsoft\\Windows Defen"...
0x18019dc22  mov     rcx, rdi; this
0x18019dc25  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilExpandEnvironmentStrings(wchar_t * *,wchar_t const *)
0x18019dc2a  mov     edi, eax
0x18019dc2c  test    eax, eax
0x18019dc2e  jns     short loc_18019DC74
0x18019dc30  mov     r8d, eax
0x18019dc33  lea     rdx, aRealtimeprotec_16; "RealtimeProtection::CRtpDlpEngine::Enab"...
0x18019dc3a  lea     rcx, aDlpHsFailedToE; "DLP::%hs Failed to expand environment s"...
0x18019dc41  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18019dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18019dc4d  cmp     rcx, r13
0x18019dc50  jz      short loc_18019DC74
0x18019dc52  test    [rcx+1Ch], r12b
0x18019dc56  jz      short loc_18019DC74
0x18019dc58  mov     edx, 3Bh ; ';'
0x18019dc5d  mov     dword ptr [rsp+160h+var_140], edi
0x18019dc61  lea     r9, aRealtimeprotec_16; "RealtimeProtection::CRtpDlpEngine::Enab"...
0x18019dc68  mov     r8, r15
0x18019dc6b  mov     rcx, [rcx+10h]
0x18019dc6f  call    WPP_SF_sd
0x18019dc74  lea     rdi, [r14+0A8h]
  ... truncated ...
```
