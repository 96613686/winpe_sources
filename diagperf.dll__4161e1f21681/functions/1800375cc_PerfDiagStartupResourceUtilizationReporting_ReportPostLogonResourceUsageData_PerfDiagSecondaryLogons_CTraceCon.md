# PerfDiagStartupResourceUtilizationReporting::ReportPostLogonResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>(PerfDiagSecondaryLogons::CTraceContext const *,PerfDiagSecondaryLogons::CAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>> &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &)

- ea: `0x1800375cc`
- end: `0x180037b96`
- name: `??$ReportPostLogonResourceUsageData@VCTraceContext@PerfDiagSecondaryLogons@@UCAnalysisContext@2@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagSecondaryLogons@@PEBUCAnalysisContext@2@AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3@Z`
- size: `1482`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `reparse_path, service_task`

## callers

- `0x1800c6c24`

## callees

- `0x180007fe4`
- `0x180015d80`
- `0x1800163c8`
- `0x18001769c`
- `0x180017758`
- `0x1800177b4`
- `0x180017b2c`
- `0x180018438`
- `0x180018944`
- `0x1800189ec`
- `0x180018b10`
- `0x180018de4`
- `0x1800282a4`
- `0x18002b098`
- `0x18002b1b0`
- `0x18002ecc4`
- `0x1800375cc`
- `0x180037b9c`
- `0x180037bcc`
- `0x180037cb0`
- `0x180037da4`
- `0x180037eb0`
- `0x180037f98`
- `0x18003c3ec`
- `0x18003c48c`
- `0x18003cc3c`
- `0x18003df28`
- `0x18003e344`
- `0x1800415b4`
- `0x18004410c`
- `0x1800c46fc`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037656`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800376d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037656`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800376d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::ReportPostLogonResourceUsageData<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext>(
        __int64 a1,
        int a2,
        __int64 **a3,
        __int64 *a4,
        __int64 *a5)
{
  int v5; // ebx
  __int64 v9; // rdi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  int v11; // ebx
  const unsigned __int16 *v12; // r9
  __int64 v14; // r8
  int BootPrefetcher; // r15d
  __int64 v16; // r14
  __int64 v17; // rbx
  unsigned __int64 v18; // rsi
  unsigned __int64 DataForProcess; // rdi
  const wchar_t *v20; // rdx
  __int64 Lower; // rax
  __int64 Buffer; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rdx
  __int64 i; // rax
  __int64 v32; // rbx
  __int64 j; // rax
  char v34; // bl
  int v35; // [rsp+20h] [rbp-1B8h]
  __int16 BootCKCLTraceSizeMB; // [rsp+40h] [rbp-198h]
  int v37; // [rsp+44h] [rbp-194h]
  __int64 v38; // [rsp+48h] [rbp-190h] BYREF
  unsigned __int64 v39; // [rsp+50h] [rbp-188h]
  __int64 v40; // [rsp+58h] [rbp-180h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-178h] BYREF
  __int64 v42; // [rsp+70h] [rbp-168h] BYREF
  __int64 v43; // [rsp+78h] [rbp-160h] BYREF
  __int64 v44; // [rsp+80h] [rbp-158h]
  _QWORD v45[2]; // [rsp+88h] [rbp-150h] BYREF
  int v46[4]; // [rsp+98h] [rbp-140h] BYREF
  unsigned int v47[2]; // [rsp+A8h] [rbp-130h]
  unsigned int v48[2]; // [rsp+B0h] [rbp-128h]
  unsigned int v49[2]; // [rsp+B8h] [rbp-120h]
  unsigned int v50[2]; // [rsp+C0h] [rbp-118h]
  unsigned int v51[2]; // [rsp+C8h] [rbp-110h]
  __int64 v52; // [rsp+D0h] [rbp-108h] BYREF
  _QWORD v53[2]; // [rsp+D8h] [rbp-100h] BYREF
  _BYTE v54[24]; // [rsp+E8h] [rbp-F0h] BYREF
  _BYTE v55[64]; // [rsp+100h] [rbp-D8h] BYREF
  _BYTE v56[80]; // [rsp+140h] [rbp-98h] BYREF

  v5 = (int)a4;
  v9 = *a5;
  v40 = *a4;
  std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,PerfDiagStartupResourceUtilizationReporting::ReadAheadHistoryType>::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,PerfDiagStartupResourceUtilizationReporting::ReadAheadHistoryType>(v41);
  std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(v45);
  std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(v46);
  v38 = 0;
  BootCKCLTraceSizeMB = PerfDiagStartupResourceUtilizationReporting::GetBootCKCLTraceSizeMB();
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Start, v10);
  GetTickCount();
  try
  {
    v11 = PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>(
            a1,
            a2,
            (_DWORD)a3,
            v5,
            (__int64)a5,
            (__int64)v46);
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Stop,
      (const struct _EVENT_DESCRIPTOR *)(unsigned int)v11,
      0,
      v12);
  }
  catch ( std::bad_alloc )
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v38);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v46);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v45);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(v41);
    return 2147942414LL;
  }
  if ( v11 >= 0 )
  {
    GetTickCount();
    BootPrefetcher = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v38);
    if ( BootPrefetcher >= 0 )
    {
      v16 = (v9 - v40) / 1000000;
      v37 = 0;
      v44 = 0;
      v17 = **a3;
      while ( (__int64 *)v17 != *a3 )
      {
        v18 = *(_QWORD *)(v17 + 40);
        v39 = v18;
        v53[0] = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(a1 + 80) + 24LL))(
                   *(_QWORD *)(a1 + 80),
                   v18);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v43);
        if ( (unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagSecondaryLogons::CTraceContext>(
                             a1,
                             v18,
                             &v43) )
        {
          DataForProcess = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::GetDataForProcess(
                             (PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v38,
                             (const struct XPerfAddIn::IProcessInfoSource::ProcessData *)v18);
          v39 = DataForProcess
              + *(_QWORD *)std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64>::operator[]((int)v46)
              + *(unsigned int *)(v17 + 64);
          *(_QWORD *)v47 = *(_QWORD *)(v17 + 72) / 1000000LL;
          *(_QWORD *)v48 = *(_QWORD *)(v17 + 80) / 1000000LL;
          *(_QWORD *)v49 = *(_QWORD *)(v17 + 88) / 1000000LL;
          *(_QWORD *)v50 = *(_QWORD *)(v17 + 96) / 1000000LL;
          *(_QWORD *)v51 = *(_QWORD *)(v17 + 48) / 1000000LL;
          v37 += v51[0];
          v44 += v39;
          v20 = L"unknown";
          if ( *(_QWORD *)(v18 + 24) )
            v20 = *(const wchar_t **)(v18 + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v40,
            v20);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v52,
            v53[0]);
          Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v52);
          Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(Lower);
          v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v40);
          v24 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v23);
          PerfDiagBoot::CPostLogonProcess::NormalizeProcessName(&v42, v24, Buffer);
          v25 = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v42);
          v26 = PerfDiagBoot::CPostLogonProcess::ProcessInfo::ProcessInfo(
                  (PerfDiagBoot::CPostLogonProcess::ProcessInfo *)v55,
                  v25,
                  v47[0],
                  v48[0],
                  v49[0],
                  v50[0],
                  v51[0],
                  v39);
          v27 = std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(
                  v56,
                  &v42,
                  v26);
          v28 = std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::insert<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>(
                  v45,
                  v54,
                  v27);
          v29 = *(_QWORD *)v28;
          LOBYTE(Buffer) = *(_BYTE *)(v28 + 8);
          std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(v56);
          LOBYTE(v30) = 1;
          std::wstring::_Tidy(v55, v30, 0);
          if ( !(_BYTE)Buffer )
          {
            *(_DWORD *)(v29 + 72) += v47[0];
            *(_DWORD *)(v29 + 76) += v48[0];
            *(_DWORD *)(v29 + 80) += v49[0];
            *(_DWORD *)(v29 + 84) += v50[0];
            *(_DWORD *)(v29 + 88) += v51[0];
            *(_QWORD *)(v29 + 96) += v39;
          }
          ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
        }
        ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
        if ( !*(_BYTE *)(v17 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v17 + 16) + 25LL) )
          {
            for ( i = *(_QWORD *)(v17 + 8); !*(_BYTE *)(i + 25) && v17 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v17 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
          }
          v17 = i;
        }
      }
      v32 = *(_QWORD *)v45[0];
      while ( v32 != v45[0] )
      {
        LOBYTE(v35) = byte_180101F26;
        std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::_Insert_nohint<PerfDiagBoot::CPostLogonProcess::ProcessInfo const &,std::_Nil>(
          v41,
          v54,
          v14,
          v32 + 40,
          v35);
        if ( !*(_BYTE *)(v32 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v32 + 16) + 25LL) )
          {
            for ( j = *(_QWORD *)(v32 + 8); !*(_BYTE *)(j + 25) && v32 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
              v32 = j;
          }
          else
          {
            j = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
          }
          v32 = j;
        }
      }
      v34 = 0;
      if ( v41[1] )
        v34 = *(_DWORD *)(*(_QWORD *)v41[0] + 64LL)
            + *(_DWORD *)(*(_QWORD *)v41[0] + 68LL)
            + *(_DWORD *)(*(_QWORD *)v41[0] + 72LL)
            + *(_DWORD *)(*(_QWORD *)v41[0] + 76LL) != 0;
      std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(
        v53,
        v41);
      PerfDiagBoot::CPostLogonProcess::PackAndUploadTopPostLogonProcesses(
        (unsigned int)v53,
        v37,
        v44,
        v16,
        BootCKCLTraceSizeMB,
        v34);
    }
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v38);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v46);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v45);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(v41);
    return (unsigned int)BootPrefetcher;
  }
  else
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v38);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v46);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v45);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(v41);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x1800375cc  push    rbx
0x1800375ce  push    rsi
0x1800375cf  push    rdi
0x1800375d0  push    r12
0x1800375d2  push    r13
0x1800375d4  push    r14
0x1800375d6  push    r15
0x1800375d8  sub     rsp, 1A0h
0x1800375df  mov     rax, cs:__security_cookie
0x1800375e6  xor     rax, rsp
0x1800375e9  mov     [rsp+1D8h+var_48], rax
0x1800375f1  mov     rbx, r9
0x1800375f4  mov     r12, r8
0x1800375f7  mov     r14, rdx
0x1800375fa  mov     r13, rcx
0x1800375fd  mov     rsi, [rsp+1D8h+arg_20]
0x180037605  mov     rdi, [rsi]
0x180037608  mov     rax, [r9]
0x18003760b  mov     [rsp+1D8h+var_180], rax
0x180037610  lea     rcx, [rsp+1D8h+var_178]
0x180037615  call    ??0?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@UReadAheadHistoryType@PerfDiagStartupResourceUtilizationReporting@@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@UReadAheadHistoryType@PerfDiagStartupResourceUtilizationReporting@@@std@@@7@@std@@QEAA@XZ; std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,PerfDiagStartupResourceUtilizationReporting::ReadAheadHistoryType>::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,PerfDiagStartupResourceUtilizationReporting::ReadAheadHistoryType>(void)
0x18003761a  nop
0x18003761b  lea     rcx, [rsp+1D8h+var_150]
0x180037623  call    ??0?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@@std@@QEAA@XZ; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(void)
0x180037628  nop
0x180037629  lea     rcx, [rsp+1D8h+var_140]
0x180037631  call    ??0?$map@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@U?$less@PEBUThreadData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUThreadData@IProcessInfoSource@XPerfAddIn@@VTimeStampDelta@XPerfCore@@@std@@@7@@std@@QEAA@XZ; std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>(void)
0x180037636  nop
0x180037637  mov     [rsp+1D8h+var_190], 0
0x180037640  call    PerfDiagStartupResourceUtilizationReporting__GetBootCKCLTraceSizeMB
0x180037645  mov     [rsp+1D8h+var_198], ax
0x18003764a  lea     rcx, PDEvt_Boot_RurReadAhead_Start; this
0x180037651  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x180037656  call    cs:__imp_GetTickCount
0x18003765c  lea     rax, [rsp+1D8h+var_140]
0x180037664  mov     qword ptr [rsp+1D8h+var_1B0], rax
0x180037669  mov     qword ptr [rsp+1D8h+var_1B8], rsi
0x18003766e  mov     r9, rbx
0x180037671  mov     r8, r12
0x180037674  mov     rdx, r14
0x180037677  mov     rcx, r13
0x18003767a  call    ??$GetReadAheadAmounts@VCTraceContext@PerfDiagSecondaryLogons@@UCAnalysisContext@2@V?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagSecondaryLogons@@PEBUCAnalysisContext@2@AEBV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@@5@@Z; PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagSecondaryLogons::CTraceContext,PerfDiagSecondaryLogons::CAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>(PerfDiagSecondaryLogons::CTraceContext const *,PerfDiagSecondaryLogons::CAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo> const &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64> &)
0x18003767f  mov     ebx, eax
0x180037681  xor     r8d, r8d; unsigned int
0x180037684  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x180037686  lea     rcx, PDEvt_Boot_RurReadAhead_Stop; this
0x18003768d  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x180037692  xor     esi, esi
0x180037694  test    ebx, ebx
0x180037696  jns     short loc_1800376D0
0x180037698  lea     rcx, [rsp+1D8h+var_190]; this
0x18003769d  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x1800376a2  nop
0x1800376a3  lea     rcx, [rsp+1D8h+var_140]
0x1800376ab  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x1800376b0  nop
0x1800376b1  lea     rcx, [rsp+1D8h+var_150]
0x1800376b9  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(void)
0x1800376be  nop
0x1800376bf  lea     rcx, [rsp+1D8h+var_178]
0x1800376c4  call    ??1?$_Tree@V?$_Tset_traits@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$greater@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(void)
0x1800376c9  mov     eax, ebx
0x1800376cb  jmp     loc_180037B73
0x1800376d0  call    cs:__imp_GetTickCount
0x1800376d6  nop
0x1800376d7  lea     rcx, [rsp+1D8h+var_190]; this
0x1800376dc  call    ?QueryBootPrefetcher@BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAAJXZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher(void)
0x1800376e1  mov     r15d, eax
0x1800376e4  test    eax, eax
0x1800376e6  jns     short loc_180037721
0x1800376e8  lea     rcx, [rsp+1D8h+var_190]; this
0x1800376ed  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x1800376f2  nop
0x1800376f3  lea     rcx, [rsp+1D8h+var_140]
0x1800376fb  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x180037700  nop
0x180037701  lea     rcx, [rsp+1D8h+var_150]
0x180037709  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(void)
0x18003770e  nop
0x18003770f  lea     rcx, [rsp+1D8h+var_178]
0x180037714  call    ??1?$_Tree@V?$_Tset_traits@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$greater@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(void)
0x180037719  mov     eax, r15d
0x18003771c  jmp     loc_180037B73
0x180037721  sub     rdi, [rsp+1D8h+var_180]
0x180037726  mov     rax, 431BDE82D7B634DBh
0x180037730  imul    rdi
0x180037733  mov     r14, rdx
0x180037736  sar     r14, 12h
0x18003773a  mov     rax, r14
0x18003773d  shr     rax, 3Fh
0x180037741  add     r14, rax
0x180037744  mov     [rsp+1D8h+var_194], esi
0x180037748  mov     [rsp+1D8h+var_158], rsi
0x180037750  mov     rbx, [r12]
0x180037754  mov     rbx, [rbx]
0x180037757  cmp     rbx, [r12]
0x18003775b  jz      loc_180037A6B
0x180037761  mov     rsi, [rbx+28h]
0x180037765  mov     [rsp+1D8h+var_188], rsi
0x18003776a  mov     rcx, [r13+50h]
0x18003776e  mov     rax, [rcx]
0x180037771  mov     rdx, rsi
0x180037774  mov     rax, [rax+18h]
0x180037778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003777d  mov     [rsp+1D8h+var_100], rax
0x180037785  lea     rcx, [rsp+1D8h+var_160]
0x18003778a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003778f  nop
0x180037790  lea     r8, [rsp+1D8h+var_160]
0x180037795  mov     rdx, rsi
0x180037798  mov     rcx, r13
0x18003779b  call    ??$GetProcessStartTime@VCTraceContext@PerfDiagSecondaryLogons@@@PerfDiagStartupResourceUtilizationReporting@@YAHPEBVCTraceContext@PerfDiagSecondaryLogons@@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagSecondaryLogons::CTraceContext>(PerfDiagSecondaryLogons::CTraceContext const *,XPerfAddIn::IProcessInfoSource::ProcessData const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800377a0  test    eax, eax
0x1800377a2  jz      loc_180037A1F
0x1800377a8  mov     rdx, rsi; struct XPerfAddIn::IProcessInfoSource::ProcessData *
0x1800377ab  lea     rcx, [rsp+1D8h+var_190]; this
0x1800377b0  call    ?GetDataForProcess@BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA_KPEBUProcessData@IProcessInfoSource@XPerfAddIn@@@Z; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::GetDataForProcess(XPerfAddIn::IProcessInfoSource::ProcessData const *)
0x1800377b5  mov     rdi, rax
0x1800377b8  lea     rdx, [rsp+1D8h+var_188]
0x1800377bd  lea     rcx, [rsp+1D8h+var_140]; int
0x1800377c5  call    ??A?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@@std@@QEAAAEA_KAEBQEBUProcessData@IProcessInfoSource@XPerfAddIn@@@Z; std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64>::operator[](XPerfAddIn::IProcessInfoSource::ProcessData const * const &)
0x1800377ca  mov     r8d, [rbx+40h]
0x1800377ce  add     r8, [rax]
0x1800377d1  add     r8, rdi
0x1800377d4  mov     [rsp+1D8h+var_188], r8
0x1800377d9  mov     r9, 431BDE82D7B634DBh
0x1800377e3  mov     rax, r9
0x1800377e6  imul    qword ptr [rbx+48h]
0x1800377ea  mov     rcx, rdx
0x1800377ed  sar     rcx, 12h
0x1800377f1  mov     rax, rcx
0x1800377f4  shr     rax, 3Fh
0x1800377f8  add     rcx, rax
0x1800377fb  mov     qword ptr [rsp+1D8h+var_130], rcx
0x180037803  mov     rax, r9
0x180037806  imul    qword ptr [rbx+50h]
0x18003780a  mov     rcx, rdx
0x18003780d  sar     rcx, 12h
0x180037811  mov     rax, rcx
0x180037814  shr     rax, 3Fh
0x180037818  add     rcx, rax
0x18003781b  mov     qword ptr [rsp+1D8h+var_128], rcx
0x180037823  mov     rax, r9
0x180037826  imul    qword ptr [rbx+58h]
0x18003782a  mov     rcx, rdx
0x18003782d  sar     rcx, 12h
0x180037831  mov     rax, rcx
0x180037834  shr     rax, 3Fh
0x180037838  add     rcx, rax
0x18003783b  mov     qword ptr [rsp+1D8h+var_120], rcx
0x180037843  mov     rax, r9
0x180037846  imul    qword ptr [rbx+60h]
0x18003784a  mov     rcx, rdx
0x18003784d  sar     rcx, 12h
0x180037851  mov     rax, rcx
0x180037854  shr     rax, 3Fh
0x180037858  add     rcx, rax
0x18003785b  mov     qword ptr [rsp+1D8h+var_118], rcx
0x180037863  mov     rax, r9
0x180037866  imul    qword ptr [rbx+30h]
0x18003786a  mov     rcx, rdx
0x18003786d  sar     rcx, 12h
0x180037871  mov     rax, rcx
0x180037874  shr     rax, 3Fh
0x180037878  add     rcx, rax
0x18003787b  mov     qword ptr [rsp+1D8h+var_110], rcx
0x180037883  add     [rsp+1D8h+var_194], ecx
0x180037887  add     [rsp+1D8h+var_158], r8
0x18003788f  lea     rdx, aUnknown_0; "unknown"
0x180037896  cmp     qword ptr [rsi+18h], 0
0x18003789b  cmovnz  rdx, [rsi+18h]
0x1800378a0  lea     rcx, [rsp+1D8h+var_180]
0x1800378a5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800378aa  nop
0x1800378ab  mov     rdx, [rsp+1D8h+var_100]
0x1800378b3  lea     rcx, [rsp+1D8h+var_108]
0x1800378bb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800378c0  nop
0x1800378c1  lea     rcx, [rsp+1D8h+var_108]
0x1800378c9  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1800378ce  mov     rcx, rax
0x1800378d1  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800378d6  mov     rdi, rax
0x1800378d9  lea     rcx, [rsp+1D8h+var_180]
0x1800378de  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1800378e3  mov     rcx, rax
0x1800378e6  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800378eb  mov     r8, rdi
0x1800378ee  mov     rdx, rax
0x1800378f1  lea     rcx, [rsp+1D8h+var_168]
0x1800378f6  call    ?NormalizeProcessName@CPostLogonProcess@PerfDiagBoot@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG0@Z; PerfDiagBoot::CPostLogonProcess::NormalizeProcessName(ushort const *,ushort const *)
0x1800378fb  nop
0x1800378fc  lea     rcx, [rsp+1D8h+var_168]
0x180037901  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180037906  mov     rdx, rax; unsigned __int16 *
0x180037909  mov     rax, [rsp+1D8h+var_188]
0x18003790e  mov     [rsp+1D8h+var_1A0], rax; unsigned __int64
0x180037913  mov     rax, qword ptr [rsp+1D8h+var_110]
0x18003791b  mov     [rsp+1D8h+var_1A8], eax; unsigned int
0x18003791f  mov     rax, qword ptr [rsp+1D8h+var_118]
0x180037927  mov     [rsp+1D8h+var_1B0], eax; unsigned int
0x18003792b  mov     rax, qword ptr [rsp+1D8h+var_120]
0x180037933  mov     [rsp+1D8h+var_1B8], eax; unsigned int
0x180037937  mov     r9d, [rsp+1D8h+var_128]; unsigned int
0x18003793f  mov     r8d, [rsp+1D8h+var_130]; unsigned int
0x180037947  lea     rcx, [rsp+1D8h+var_D8]; this
0x18003794f  call    ??0ProcessInfo@CPostLogonProcess@PerfDiagBoot@@QEAA@PEAGKKKKK_K@Z; PerfDiagBoot::CPostLogonProcess::ProcessInfo::ProcessInfo(ushort *,ulong,ulong,ulong,ulong,ulong,unsigned __int64)
0x180037954  nop
0x180037955  mov     r8, rax
0x180037958  lea     rdx, [rsp+1D8h+var_168]
0x18003795d  lea     rcx, [rsp+1D8h+var_98]
0x180037965  call    ??$?0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@QEAA@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEAUProcessInfo@CPostLogonProcess@PerfDiagBoot@@PEAPEAX@Z; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,PerfDiagBoot::CPostLogonProcess::ProcessInfo &&,void * *)
0x18003796a  nop
0x18003796b  mov     r8, rax
0x18003796e  lea     rdx, [rsp+1D8h+var_F0]
0x180037976  lea     rcx, [rsp+1D8h+var_150]
0x18003797e  call    ??$insert@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::insert<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo> &&)
0x180037983  mov     rsi, [rax]
0x180037986  mov     dil, [rax+8]
0x18003798a  lea     rcx, [rsp+1D8h+var_98]
0x180037992  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>(void)
0x180037997  nop
0x180037998  xor     r8d, r8d
0x18003799b  mov     dl, 1
0x18003799d  lea     rcx, [rsp+1D8h+var_D8]
0x1800379a5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800379aa  test    dil, dil
0x1800379ad  jnz     short loc_1800379EF
0x1800379af  mov     rax, qword ptr [rsp+1D8h+var_130]
0x1800379b7  add     [rsi+48h], eax
0x1800379ba  mov     rax, qword ptr [rsp+1D8h+var_128]
0x1800379c2  add     [rsi+4Ch], eax
0x1800379c5  mov     rax, qword ptr [rsp+1D8h+var_120]
0x1800379cd  add     [rsi+50h], eax
0x1800379d0  mov     rax, qword ptr [rsp+1D8h+var_118]
0x1800379d8  add     [rsi+54h], eax
0x1800379db  mov     rax, qword ptr [rsp+1D8h+var_110]
0x1800379e3  add     [rsi+58h], eax
0x1800379e6  mov     rax, [rsp+1D8h+var_188]
0x1800379eb  add     [rsi+60h], rax
0x1800379ef  mov     rcx, [rsp+1D8h+var_168]
0x1800379f4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800379f8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800379fd  nop
0x1800379fe  mov     rcx, [rsp+1D8h+var_108]
0x180037a06  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180037a0a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037a0f  nop
0x180037a10  mov     rcx, [rsp+1D8h+var_180]
0x180037a15  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180037a19  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037a1e  nop
0x180037a1f  mov     rcx, [rsp+1D8h+var_160]
0x180037a24  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180037a28  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037a2d  xor     esi, esi
0x180037a2f  cmp     [rbx+19h], sil
0x180037a33  jnz     loc_180037757
0x180037a39  mov     rcx, [rbx+10h]
0x180037a3d  cmp     [rcx+19h], sil
0x180037a41  jnz     short loc_180037A4A
0x180037a43  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$set@PEAUVARange@IProcessInfoSource@XPerfAddIn@@U?$less@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@5@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KV?$set@PEAUVARange@IProcessInfoSource@XPerfAddIn@@U?$less@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@5@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>,void *> *)
0x180037a48  jmp     short loc_180037A63
0x180037a4a  mov     rax, [rbx+8]
0x180037a4e  jmp     short loc_180037A5D
0x180037a50  cmp     rbx, [rax+10h]
0x180037a54  jnz     short loc_180037A63
0x180037a56  mov     rbx, rax
0x180037a59  mov     rax, [rax+8]
0x180037a5d  cmp     [rax+19h], sil
0x180037a61  jz      short loc_180037A50
0x180037a63  mov     rbx, rax
0x180037a66  jmp     loc_180037757
0x180037a6b  mov     rbx, [rsp+1D8h+var_150]
0x180037a73  mov     rbx, [rbx]
0x180037a76  cmp     rbx, [rsp+1D8h+var_150]
0x180037a7e  jz      short loc_180037AD5
0x180037a80  lea     r9, [rbx+28h]
0x180037a84  mov     al, cs:byte_180101F26
0x180037a8a  mov     byte ptr [rsp+1D8h+var_1B8], al
0x180037a8e  lea     rdx, [rsp+1D8h+var_F0]
0x180037a96  lea     rcx, [rsp+1D8h+var_178]
0x180037a9b  call    ??$_Insert_nohint@AEBUProcessInfo@CPostLogonProcess@PerfDiagBoot@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$greater@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@5@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@std@@@std@@_N@1@_NAEBUProcessInfo@CPostLogonProcess@PerfDiagBoot@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::_Insert_nohint<PerfDiagBoot::CPostLogonProcess::ProcessInfo const &,std::_Nil>(bool,PerfDiagBoot::CPostLogonProcess::ProcessInfo const &,std::_Nil)
0x180037aa0  cmp     [rbx+19h], sil
0x180037aa4  jnz     short loc_180037A76
0x180037aa6  mov     rcx, [rbx+10h]
0x180037aaa  cmp     [rcx+19h], sil
0x180037aae  jnz     short loc_180037AB7
0x180037ab0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$set@PEAUVARange@IProcessInfoSource@XPerfAddIn@@U?$less@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@5@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KV?$set@PEAUVARange@IProcessInfoSource@XPerfAddIn@@U?$less@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@PEAUVARange@IProcessInfoSource@XPerfAddIn@@@5@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>,void *> *)
0x180037ab5  jmp     short loc_180037AD0
0x180037ab7  mov     rax, [rbx+8]
0x180037abb  jmp     short loc_180037ACA
0x180037abd  cmp     rbx, [rax+10h]
0x180037ac1  jnz     short loc_180037AD0
0x180037ac3  mov     rbx, rax
0x180037ac6  mov     rax, [rax+8]
0x180037aca  cmp     [rax+19h], sil
0x180037ace  jz      short loc_180037ABD
0x180037ad0  mov     rbx, rax
0x180037ad3  jmp     short loc_180037A76
  ... truncated ...
```
