# PerfDiagStartupResourceUtilizationReporting::ReportPostLogonResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>(PerfDiagBoot::CTraceContext const *,PerfDiagBoot::CUserAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>> &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &)

- ea: `0x180016dec`
- end: `0x180017606`
- name: `??$ReportPostLogonResourceUsageData@VCTraceContext@PerfDiagBoot@@UCUserAnalysisContext@2@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagBoot@@PEBUCUserAnalysisContext@2@AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3@Z`
- size: `2074`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x180030840`

## callees

- `0x180002460`
- `0x180014880`
- `0x180015f94`
- `0x180016dec`
- `0x18001760c`
- `0x18001769c`
- `0x1800176cc`
- `0x180017758`
- `0x1800177b4`
- `0x1800179b0`
- `0x180017b2c`
- `0x180018044`
- `0x180018350`
- `0x180018660`
- `0x1800186b0`
- `0x180018708`
- `0x180018b10`
- `0x1800282a4`
- `0x18002ecc4`
- `0x180037bcc`
- `0x180037c70`
- `0x180037cb0`
- `0x180037ce0`
- `0x180037da4`
- `0x180037dec`
- `0x180037eb0`
- `0x180037ee0`
- `0x180037f98`
- `0x18003862c`
- `0x18003c41c`
- `0x18003cc3c`
- `0x18003df28`
- `0x1800415b4`
- `0x18004410c`
- `0x180056c14`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016ea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016f14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016ea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016f14`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::ReportPostLogonResourceUsageData<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext>(
        __int64 a1,
        int a2,
        __int64 **a3,
        __int64 *a4,
        __int64 *a5)
{
  int v5; // ebx
  __int64 v8; // r15
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  int v10; // ebx
  const unsigned __int16 *v11; // r9
  __int64 v13; // r8
  int BootPrefetcher; // r12d
  __int64 *v15; // rbx
  unsigned int *v16; // r14
  unsigned __int64 v17; // rsi
  unsigned int *v18; // r8
  unsigned int *v19; // rcx
  __int64 v20; // r15
  __int64 *v21; // rax
  _QWORD *v22; // rdi
  void *v23; // rax
  __int64 v24; // r15
  const wchar_t *v25; // rdx
  __int64 Lower; // rax
  __int64 Buffer; // rdi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  int v33; // edi
  int v34; // esi
  __int64 v35; // rax
  int v36; // r8d
  __int64 v37; // rax
  __int64 *i; // rax
  __int64 *v39; // rcx
  __int64 v40; // rdi
  __int64 *v41; // rbx
  __int64 *j; // rax
  __int64 *v43; // rcx
  char v44; // bl
  int v45; // [rsp+20h] [rbp-1D8h]
  __int16 BootCKCLTraceSizeMB; // [rsp+40h] [rbp-1B8h]
  int v47; // [rsp+44h] [rbp-1B4h]
  void *v48[2]; // [rsp+48h] [rbp-1B0h] BYREF
  void *v49[2]; // [rsp+58h] [rbp-1A0h] BYREF
  void *v50; // [rsp+68h] [rbp-190h] BYREF
  __int64 v51; // [rsp+70h] [rbp-188h]
  __int64 v52; // [rsp+78h] [rbp-180h] BYREF
  void *v53; // [rsp+80h] [rbp-178h] BYREF
  __int64 v54; // [rsp+88h] [rbp-170h] BYREF
  __int64 v55; // [rsp+90h] [rbp-168h] BYREF
  __int64 v56; // [rsp+98h] [rbp-160h]
  __int64 v57; // [rsp+A0h] [rbp-158h] BYREF
  char v58; // [rsp+A8h] [rbp-150h]
  __int64 v59; // [rsp+B0h] [rbp-148h]
  __int64 v60; // [rsp+B8h] [rbp-140h]
  __int64 v61; // [rsp+C0h] [rbp-138h]
  __int64 v62; // [rsp+C8h] [rbp-130h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-128h] BYREF
  int v64[2]; // [rsp+D8h] [rbp-120h] BYREF
  __int64 v65; // [rsp+E0h] [rbp-118h]
  __int64 v66; // [rsp+E8h] [rbp-110h]
  __int64 v67; // [rsp+F0h] [rbp-108h]
  __int64 v68; // [rsp+F8h] [rbp-100h]
  __int64 v69; // [rsp+100h] [rbp-F8h]
  _QWORD v70[3]; // [rsp+108h] [rbp-F0h] BYREF
  void *v71[3]; // [rsp+120h] [rbp-D8h] BYREF
  unsigned __int64 v72; // [rsp+138h] [rbp-C0h]
  int v73; // [rsp+140h] [rbp-B8h]
  int v74; // [rsp+144h] [rbp-B4h]
  int v75; // [rsp+148h] [rbp-B0h]
  int v76; // [rsp+14Ch] [rbp-ACh]
  int v77; // [rsp+150h] [rbp-A8h]
  __int64 v78; // [rsp+158h] [rbp-A0h]
  __int64 v79; // [rsp+160h] [rbp-98h] BYREF
  void *Block[9]; // [rsp+168h] [rbp-90h] BYREF

  v5 = (int)a4;
  v8 = a1;
  v68 = a1;
  v69 = *a5;
  v54 = *a4;
  v51 = 0;
  v50 = (void *)std::_Tree_alloc<0,std::_Tree_base_types<PerfDiagBoot::CPostLogonProcess::ProcessInfo>>::_Buyheadnode();
  v49[1] = 0;
  v49[0] = (void *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>>::_Buyheadnode();
  v48[1] = 0;
  v48[0] = (void *)std::_Tree_alloc<0,std::_Tree_base_types<XPerfCore::CStageEventSinkRegistryEntry>>::_Buyheadnode();
  v53 = 0;
  BootCKCLTraceSizeMB = PerfDiagStartupResourceUtilizationReporting::GetBootCKCLTraceSizeMB();
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Start, v9);
  GetTickCount();
  try
  {
    v10 = PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>(
            v8,
            a2,
            (_DWORD)a3,
            v5,
            (__int64)a5,
            (unsigned int)v48);
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Boot_RurReadAhead_Stop,
      (const struct _EVENT_DESCRIPTOR *)(unsigned int)v10,
      0,
      v11);
  }
  catch ( std::bad_alloc )
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v53);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v48);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v49);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(&v50);
    return 2147942414LL;
  }
  if ( v10 < 0 )
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v53);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v48);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v49);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(&v50);
    return (unsigned int)v10;
  }
  GetTickCount();
  BootPrefetcher = PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v53);
  if ( BootPrefetcher < 0 )
  {
    PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData((PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *)&v53);
    std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(v48);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(v49);
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(&v50);
    return (unsigned int)BootPrefetcher;
  }
  v47 = 0;
  v56 = 0;
  v15 = (__int64 *)**a3;
  v16 = (unsigned int *)v53;
  while ( v15 != *a3 )
  {
    v17 = v15[5];
    v65 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v8 + 104) + 24LL))(
            *(_QWORD *)(v8 + 104),
            v17);
    v55 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagBoot::CTraceContext>(
                         v8,
                         v17,
                         &v55) )
    {
      if ( !v16 || (v18 = &v16[4 * v16[6] + 8 + 2 * v16[6]], v19 = v16 + 8, v16 + 8 == v18) )
      {
LABEL_14:
        v20 = 0;
      }
      else
      {
        while ( (*(_QWORD *)v19 & 0xFFFFFFFFFFFFLL) != ((*(_QWORD *)(v17 + 16)
                                                       ^ *(unsigned int *)(v17 + 32))
                                                      & 0xFFFFFFFFFFFFLL) )
        {
          v19 += 6;
          if ( v19 == v18 )
            goto LABEL_14;
        }
        v20 = *((_QWORD *)v19 + 1);
      }
      v21 = (__int64 *)*((_QWORD *)v48[0] + 1);
      v22 = v48[0];
      while ( !*((_BYTE *)v21 + 25) )
      {
        if ( v21[4] >= v17 )
        {
          v22 = v21;
          v21 = (__int64 *)*v21;
        }
        else
        {
          v21 = (__int64 *)v21[2];
        }
      }
      if ( v22 == v48[0] || v17 < v22[4] )
      {
        v70[0] = v17;
        v70[1] = 0;
        v23 = (void *)std::_Tree_buy<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::ProcessInfo *>>::_Buynode<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo *>>(
                        (__int64)v48,
                        v70);
        std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::_Insert_hint<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64> &,std::_Tree_node<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>,void *> *>(
          (int)v48,
          (int)v64,
          (int)v22,
          v23);
        v22 = *(_QWORD **)v64;
      }
      v61 = v20 + v22[5] + *((unsigned int *)v15 + 16);
      v66 = v15[9] / 1000000;
      v67 = v15[10] / 1000000;
      v59 = v15[11] / 1000000;
      v60 = v15[12] / 1000000;
      v24 = v15[6] / 1000000;
      v47 += v24;
      v56 += v61;
      v25 = L"unknown";
      if ( *(_QWORD *)(v17 + 24) )
        v25 = *(const wchar_t **)(v17 + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v63,
        v25);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v62,
        v65);
      Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v62);
      Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(Lower);
      v28 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v63);
      v29 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v28);
      PerfDiagBoot::CPostLogonProcess::NormalizeProcessName(&v52, v29, Buffer);
      v30 = v52;
      if ( *(int *)(v52 - 8) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v52, *(unsigned int *)(v52 - 16));
        v30 = v52;
      }
      v72 = 7;
      v71[2] = 0;
      LOWORD(v71[0]) = 0;
      v31 = std::char_traits<unsigned short>::length(v30);
      std::wstring::assign(v71, v32, v31);
      v33 = v66;
      v73 = v66;
      v34 = v67;
      v74 = v67;
      v75 = v59;
      v76 = v60;
      v77 = v24;
      v78 = v61;
      v79 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v52 - 24) + 24;
      PerfDiagBoot::CPostLogonProcess::ProcessInfo::ProcessInfo(Block, v71);
      v35 = std::_Tree_buy<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>::_Buynode<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>(
              v49,
              &v79);
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::_Insert_nohint<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo> &,std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>,void *> *>(
        (unsigned int)v49,
        (unsigned int)&v57,
        v36,
        v35 + 32,
        v35);
      if ( Block[3] >= (void *)8 )
        operator delete(Block[0]);
      ATL::CStringData::Release((ATL::CStringData *)(v79 - 24));
      if ( v72 >= 8 )
        operator delete(v71[0]);
      if ( !v58 )
      {
        v37 = v57;
        *(_DWORD *)(v57 + 72) += v33;
        *(_DWORD *)(v37 + 76) += v34;
        *(_DWORD *)(v37 + 80) += v59;
        *(_DWORD *)(v37 + 84) += v60;
        *(_DWORD *)(v37 + 88) += v24;
        *(_QWORD *)(v37 + 96) += v61;
      }
      ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v62 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
      v8 = v68;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v55 - 24));
    if ( !*((_BYTE *)v15 + 25) )
    {
      i = (__int64 *)v15[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v15 = i;
LABEL_44:
        v15 = i;
      }
      else
      {
        v39 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_44;
        do
        {
          v15 = v39;
          v39 = (__int64 *)*v39;
        }
        while ( !*((_BYTE *)v39 + 25) );
      }
    }
  }
  v40 = (v69 - v54) / 1000000;
  v41 = *(__int64 **)v49[0];
  while ( v41 != v49[0] )
  {
    LOBYTE(v45) = byte_180101F26;
    std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::_Insert_nohint<PerfDiagBoot::CPostLogonProcess::ProcessInfo const &,std::_Nil>(
      &v50,
      &v57,
      v13,
      v41 + 5,
      v45);
    if ( !*((_BYTE *)v41 + 25) )
    {
      j = (__int64 *)v41[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( j = (__int64 *)v41[1]; !*((_BYTE *)j + 25) && v41 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v41 = j;
LABEL_56:
        v41 = j;
      }
      else
      {
        v43 = (__int64 *)*j;
        if ( *(_BYTE *)(*j + 25) )
          goto LABEL_56;
        do
        {
          v41 = v43;
          v43 = (__int64 *)*v43;
        }
        while ( !*((_BYTE *)v43 + 25) );
      }
    }
  }
  v44 = 0;
  if ( v51 )
    v44 = *(_DWORD *)(*(_QWORD *)v50 + 64LL)
        + *(_DWORD *)(*(_QWORD *)v50 + 68LL)
        + *(_DWORD *)(*(_QWORD *)v50 + 72LL)
        + *(_DWORD *)(*(_QWORD *)v50 + 76LL) != 0;
  std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(
    &v57,
    &v50);
  PerfDiagBoot::CPostLogonProcess::PackAndUploadTopPostLogonProcesses(
    (unsigned int)&v57,
    v47,
    v56,
    v40,
    BootCKCLTraceSizeMB,
    v44);
  if ( v16 )
    operator delete(v16);
  std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::erase(
    v48,
    &v54,
    *(_QWORD *)v48[0],
    v48[0]);
  operator delete(v48[0]);
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::erase(
    v49,
    &v54,
    *(_QWORD *)v49[0],
    v49[0]);
  operator delete(v49[0]);
  std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::erase(
    &v50,
    &v54,
    *(_QWORD *)v50,
    v50);
  operator delete(v50);
  return (unsigned int)BootPrefetcher;
}

```

## disassembly

```asm
0x180016dec  push    rbx
0x180016dee  push    rsi
0x180016def  push    rdi
0x180016df0  push    r12
0x180016df2  push    r13
0x180016df4  push    r14
0x180016df6  push    r15
0x180016df8  sub     rsp, 1C0h
0x180016dff  mov     rax, cs:__security_cookie
0x180016e06  xor     rax, rsp
0x180016e09  mov     [rsp+1F8h+var_48], rax
0x180016e11  mov     rbx, r9
0x180016e14  mov     r13, r8
0x180016e17  mov     rsi, rdx
0x180016e1a  mov     r15, rcx
0x180016e1d  mov     [rsp+1F8h+var_100], rcx
0x180016e25  mov     rdi, [rsp+1F8h+arg_20]
0x180016e2d  mov     rax, [rdi]
0x180016e30  mov     [rsp+1F8h+var_F8], rax
0x180016e38  mov     rax, [r9]
0x180016e3b  mov     [rsp+1F8h+var_170], rax
0x180016e43  xor     r14d, r14d
0x180016e46  mov     [rsp+1F8h+var_190], r14
0x180016e4b  mov     [rsp+1F8h+var_188], r14
0x180016e50  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<PerfDiagBoot::CPostLogonProcess::ProcessInfo>>::_Buyheadnode(void)
0x180016e55  mov     [rsp+1F8h+var_190], rax
0x180016e5a  mov     [rsp+1F8h+var_1A0], r14
0x180016e5f  mov     [rsp+1F8h+var_198], r14
0x180016e64  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>>::_Buyheadnode(void)
0x180016e69  mov     [rsp+1F8h+var_1A0], rax
0x180016e6e  mov     [rsp+1F8h+var_1B0], r14
0x180016e73  mov     [rsp+1F8h+var_1A8], r14
0x180016e78  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@VCStageEventSinkRegistryEntry@XPerfCore@@V?$allocator@VCStageEventSinkRegistryEntry@XPerfCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@VCStageEventSinkRegistryEntry@XPerfCore@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<XPerfCore::CStageEventSinkRegistryEntry>>::_Buyheadnode(void)
0x180016e7d  mov     [rsp+1F8h+var_1B0], rax
0x180016e82  mov     [rsp+1F8h+var_178], r14
0x180016e8a  call    PerfDiagStartupResourceUtilizationReporting__GetBootCKCLTraceSizeMB
0x180016e8f  mov     [rsp+1F8h+var_1B8], ax
0x180016e94  lea     rcx, PDEvt_Boot_RurReadAhead_Start; this
0x180016e9b  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x180016ea0  call    cs:__imp_GetTickCount
0x180016ea6  lea     rax, [rsp+1F8h+var_1B0]
0x180016eab  mov     [rsp+1F8h+var_1D0], rax
0x180016eb0  mov     [rsp+1F8h+var_1D8], rdi
0x180016eb5  mov     r9, rbx
0x180016eb8  mov     r8, r13
0x180016ebb  mov     rdx, rsi
0x180016ebe  mov     rcx, r15
0x180016ec1  call    ??$GetReadAheadAmounts@VCTraceContext@PerfDiagBoot@@UCUserAnalysisContext@2@V?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@@PerfDiagStartupResourceUtilizationReporting@@YAJPEBVCTraceContext@PerfDiagBoot@@PEBUCUserAnalysisContext@2@AEBV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@U?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@USampledProcessInfo@IBootAnalysisServices@3@@std@@@7@@std@@AEBVTimeStamp@XPerfCore@@3AEAV?$map@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@@5@@Z; PerfDiagStartupResourceUtilizationReporting::GetReadAheadAmounts<PerfDiagBoot::CTraceContext,PerfDiagBoot::CUserAnalysisContext,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo>>(PerfDiagBoot::CTraceContext const *,PerfDiagBoot::CUserAnalysisContext const *,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::SampledProcessInfo> const &,XPerfCore::TimeStamp const &,XPerfCore::TimeStamp const &,std::map<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64> &)
0x180016ec6  mov     ebx, eax
0x180016ec8  xor     r8d, r8d; unsigned int
0x180016ecb  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x180016ecd  lea     rcx, PDEvt_Boot_RurReadAhead_Stop; this
0x180016ed4  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x180016ed9  xor     esi, esi
0x180016edb  test    ebx, ebx
0x180016edd  jns     short loc_180016F14
0x180016edf  lea     rcx, [rsp+1F8h+var_178]; this
0x180016ee7  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x180016eec  nop
0x180016eed  lea     rcx, [rsp+1F8h+var_1B0]
0x180016ef2  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x180016ef7  nop
0x180016ef8  lea     rcx, [rsp+1F8h+var_1A0]
0x180016efd  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(void)
0x180016f02  nop
0x180016f03  lea     rcx, [rsp+1F8h+var_190]
0x180016f08  call    ??1?$_Tree@V?$_Tset_traits@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$greater@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(void)
0x180016f0d  mov     eax, ebx
0x180016f0f  jmp     loc_1800175E3
0x180016f14  call    cs:__imp_GetTickCount
0x180016f1a  nop
0x180016f1b  lea     rcx, [rsp+1F8h+var_178]; this
0x180016f23  call    ?QueryBootPrefetcher@BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAAJXZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher(void)
0x180016f28  mov     r12d, eax
0x180016f2b  test    eax, eax
0x180016f2d  jns     short loc_180016F65
0x180016f2f  lea     rcx, [rsp+1F8h+var_178]; this
0x180016f37  call    ??1BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAA@XZ; PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::~BootPrefetcherData(void)
0x180016f3c  nop
0x180016f3d  lea     rcx, [rsp+1F8h+var_1B0]
0x180016f42  call    ??1?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>(void)
0x180016f47  nop
0x180016f48  lea     rcx, [rsp+1F8h+var_1A0]
0x180016f4d  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>(void)
0x180016f52  nop
0x180016f53  lea     rcx, [rsp+1F8h+var_190]
0x180016f58  call    ??1?$_Tree@V?$_Tset_traits@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$greater@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>::~_Tree<std::_Tset_traits<PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::greater<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,std::allocator<PerfDiagBoot::CPostLogonProcess::ProcessInfo>,0>>(void)
0x180016f5d  mov     eax, r12d
0x180016f60  jmp     loc_1800175E3
0x180016f65  mov     [rsp+1F8h+var_1B4], esi
0x180016f69  mov     [rsp+1F8h+var_160], rsi
0x180016f71  mov     rbx, [r13+0]
0x180016f75  mov     rbx, [rbx]
0x180016f78  mov     rdi, 0FFFFFFFFFFFFh
0x180016f82  mov     r14, [rsp+1F8h+var_178]
0x180016f8a  cmp     rbx, [r13+0]
0x180016f8e  jz      loc_18001741C
0x180016f94  mov     rsi, [rbx+28h]
0x180016f98  mov     rcx, [r15+68h]
0x180016f9c  mov     rax, [rcx]
0x180016f9f  mov     rdx, rsi
0x180016fa2  mov     rax, [rax+18h]
0x180016fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fab  mov     [rsp+1F8h+var_118], rax
0x180016fb3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016fba  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016fc1  mov     rax, [rax+18h]
0x180016fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fca  add     rax, 18h
0x180016fce  mov     [rsp+1F8h+var_168], rax
0x180016fd6  lea     r8, [rsp+1F8h+var_168]
0x180016fde  mov     rdx, rsi
0x180016fe1  mov     rcx, r15
0x180016fe4  call    ??$GetProcessStartTime@VCTraceContext@PerfDiagBoot@@@PerfDiagStartupResourceUtilizationReporting@@YAHPEBVCTraceContext@PerfDiagBoot@@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PerfDiagStartupResourceUtilizationReporting::GetProcessStartTime<PerfDiagBoot::CTraceContext>(PerfDiagBoot::CTraceContext const *,XPerfAddIn::IProcessInfoSource::ProcessData const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180016fe9  test    eax, eax
0x180016feb  jnz     short loc_180016FF2
0x180016fed  jmp     loc_1800173B7
0x180016ff2  test    r14, r14
0x180016ff5  jz      short loc_18001702E
0x180016ff7  mov     eax, [r14+18h]
0x180016ffb  lea     rcx, [rax+2]
0x180016fff  lea     rcx, [rax+rcx*2]
0x180017003  lea     r8, [r14+rcx*8]
0x180017007  lea     rcx, [r14+20h]
0x18001700b  cmp     rcx, r8
0x18001700e  jz      short loc_18001702E
0x180017010  mov     edx, [rsi+20h]
0x180017013  xor     rdx, [rsi+10h]
0x180017017  and     rdx, rdi
0x18001701a  mov     rax, [rcx]
0x18001701d  and     rax, rdi
0x180017020  cmp     rax, rdx
0x180017023  jz      short loc_18001703F
0x180017025  add     rcx, 18h
0x180017029  cmp     rcx, r8
0x18001702c  jnz     short loc_18001701A
0x18001702e  xor     r15d, r15d
0x180017031  mov     rcx, [rsp+1F8h+var_1B0]
0x180017036  mov     rax, [rcx+8]
0x18001703a  mov     rdi, rcx
0x18001703d  jmp     short loc_180017057
0x18001703f  mov     r15, [rcx+8]
0x180017043  jmp     short loc_180017031
0x180017045  cmp     [rax+20h], rsi
0x180017049  jnb     short loc_180017051
0x18001704b  mov     rax, [rax+10h]
0x18001704f  jmp     short loc_180017057
0x180017051  mov     rdi, rax
0x180017054  mov     rax, [rax]
0x180017057  cmp     byte ptr [rax+19h], 0
0x18001705b  jz      short loc_180017045
0x18001705d  cmp     rdi, rcx
0x180017060  jz      short loc_180017068
0x180017062  cmp     rsi, [rdi+20h]
0x180017066  jnb     short loc_1800170B4
0x180017068  mov     [rsp+1F8h+var_F0], rsi
0x180017070  mov     [rsp+1F8h+var_E8], 0
0x18001707c  lea     rdx, [rsp+1F8h+var_F0]
0x180017084  lea     rcx, [rsp+1F8h+var_1B0]
0x180017089  call    ??$_Buynode@U?$pair@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@PEAUProcessInfo@IBootAnalysisServices@3@@std@@@?$_Tree_buy@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@PEAUProcessInfo@IBootAnalysisServices@3@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@PEAUProcessInfo@IBootAnalysisServices@3@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@PEAUProcessInfo@IBootAnalysisServices@3@@std@@PEAX@1@$$QEAU?$pair@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@PEAUProcessInfo@IBootAnalysisServices@3@@1@@Z; std::_Tree_buy<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,XPerfAddIn::IBootAnalysisServices::ProcessInfo *>>::_Buynode<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo *>>(std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const *,XPerfAddIn::IBootAnalysisServices::ProcessInfo *> &&)
0x18001708e  lea     r9, [rax+20h]
0x180017092  mov     [rsp+1F8h+var_1D8], rax; void *
0x180017097  mov     r8, rdi; int
0x18001709a  lea     rdx, [rsp+1F8h+var_120]; int
0x1800170a2  lea     rcx, [rsp+1F8h+var_1B0]; int
0x1800170a7  call    ??$_Insert_hint@AEAU?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@PEAU?$_Tree_node@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@_KU?$less@PEBUProcessData@IProcessInfoSource@XPerfAddIn@@@std@@V?$allocator@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@5@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@@std@@@std@@@1@AEAU?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@1@PEAU?$_Tree_node@U?$pair@QEBUProcessData@IProcessInfoSource@XPerfAddIn@@_K@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<XPerfAddIn::IProcessInfoSource::ProcessData const *,unsigned __int64,std::less<XPerfAddIn::IProcessInfoSource::ProcessData const *>,std::allocator<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>,0>>::_Insert_hint<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64> &,std::_Tree_node<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>>>>,std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64> &,std::_Tree_node<std::pair<XPerfAddIn::IProcessInfoSource::ProcessData const * const,unsigned __int64>,void *> *)
0x1800170ac  mov     rdi, qword ptr [rsp+1F8h+var_120]
0x1800170b4  mov     r8d, [rbx+40h]
0x1800170b8  add     r8, [rdi+28h]
0x1800170bc  add     r8, r15
0x1800170bf  mov     [rsp+1F8h+var_138], r8
0x1800170c7  mov     r9, 431BDE82D7B634DBh
0x1800170d1  mov     rax, r9
0x1800170d4  imul    qword ptr [rbx+48h]
0x1800170d8  mov     rcx, rdx
0x1800170db  sar     rcx, 12h
0x1800170df  mov     rax, rcx
0x1800170e2  shr     rax, 3Fh
0x1800170e6  add     rcx, rax
0x1800170e9  mov     [rsp+1F8h+var_110], rcx
0x1800170f1  mov     rax, r9
0x1800170f4  imul    qword ptr [rbx+50h]
0x1800170f8  mov     rcx, rdx
0x1800170fb  sar     rcx, 12h
0x1800170ff  mov     rax, rcx
0x180017102  shr     rax, 3Fh
0x180017106  add     rcx, rax
0x180017109  mov     [rsp+1F8h+var_108], rcx
0x180017111  mov     rax, r9
0x180017114  imul    qword ptr [rbx+58h]
0x180017118  mov     rcx, rdx
0x18001711b  sar     rcx, 12h
0x18001711f  mov     rax, rcx
0x180017122  shr     rax, 3Fh
0x180017126  add     rcx, rax
0x180017129  mov     [rsp+1F8h+var_148], rcx
0x180017131  mov     rax, r9
0x180017134  imul    qword ptr [rbx+60h]
0x180017138  mov     rcx, rdx
0x18001713b  sar     rcx, 12h
0x18001713f  mov     rax, rcx
0x180017142  shr     rax, 3Fh
0x180017146  add     rcx, rax
0x180017149  mov     [rsp+1F8h+var_140], rcx
0x180017151  mov     rax, r9
0x180017154  imul    qword ptr [rbx+30h]
0x180017158  mov     r15, rdx
0x18001715b  sar     r15, 12h
0x18001715f  mov     rax, r15
0x180017162  shr     rax, 3Fh
0x180017166  add     r15, rax
0x180017169  add     [rsp+1F8h+var_1B4], r15d
0x18001716e  add     [rsp+1F8h+var_160], r8
0x180017176  lea     rdx, aUnknown_0; "unknown"
0x18001717d  cmp     qword ptr [rsi+18h], 0
0x180017182  cmovnz  rdx, [rsi+18h]
0x180017187  lea     rcx, [rsp+1F8h+var_128]
0x18001718f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180017194  nop
0x180017195  mov     rdx, [rsp+1F8h+var_118]
0x18001719d  lea     rcx, [rsp+1F8h+var_130]
0x1800171a5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800171aa  nop
0x1800171ab  lea     rcx, [rsp+1F8h+var_130]
0x1800171b3  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1800171b8  mov     rcx, rax
0x1800171bb  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800171c0  mov     rdi, rax
0x1800171c3  lea     rcx, [rsp+1F8h+var_128]
0x1800171cb  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1800171d0  mov     rcx, rax
0x1800171d3  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800171d8  mov     r8, rdi
0x1800171db  mov     rdx, rax
0x1800171de  lea     rcx, [rsp+1F8h+var_180]
0x1800171e3  call    ?NormalizeProcessName@CPostLogonProcess@PerfDiagBoot@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG0@Z; PerfDiagBoot::CPostLogonProcess::NormalizeProcessName(ushort const *,ushort const *)
0x1800171e8  nop
0x1800171e9  mov     rcx, [rsp+1F8h+var_180]
0x1800171ee  cmp     dword ptr [rcx-8], 1
0x1800171f2  jle     short loc_180017206
0x1800171f4  mov     edx, [rcx-10h]
0x1800171f7  lea     rcx, [rsp+1F8h+var_180]
0x1800171fc  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180017201  mov     rcx, [rsp+1F8h+var_180]
0x180017206  mov     [rsp+1F8h+var_C0], 7
0x180017212  mov     [rsp+1F8h+var_C8], 0
0x18001721e  xor     eax, eax
0x180017220  mov     word ptr [rsp+1F8h+var_D8], ax
0x180017228  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001722d  mov     r8, rax
0x180017230  mov     rdx, rcx
0x180017233  lea     rcx, [rsp+1F8h+var_D8]
0x18001723b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180017240  mov     rdi, [rsp+1F8h+var_110]
0x180017248  mov     [rsp+1F8h+var_B8], edi
0x18001724f  mov     rsi, [rsp+1F8h+var_108]
0x180017257  mov     [rsp+1F8h+var_B4], esi
0x18001725e  mov     rax, [rsp+1F8h+var_148]
0x180017266  mov     [rsp+1F8h+var_B0], eax
0x18001726d  mov     rax, [rsp+1F8h+var_140]
0x180017275  mov     [rsp+1F8h+var_AC], eax
0x18001727c  mov     [rsp+1F8h+var_A8], r15d
0x180017284  mov     rax, [rsp+1F8h+var_138]
0x18001728c  mov     [rsp+1F8h+var_A0], rax
0x180017294  mov     rcx, [rsp+1F8h+var_180]
0x180017299  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18001729d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800172a2  add     rax, 18h
0x1800172a6  mov     [rsp+1F8h+var_98], rax
0x1800172ae  lea     rdx, [rsp+1F8h+var_D8]
0x1800172b6  lea     rcx, [rsp+1F8h+Block]
0x1800172be  call    ??0ProcessInfo@CPostLogonProcess@PerfDiagBoot@@QEAA@$$QEAU012@@Z; PerfDiagBoot::CPostLogonProcess::ProcessInfo::ProcessInfo(PerfDiagBoot::CPostLogonProcess::ProcessInfo &&)
0x1800172c3  nop
0x1800172c4  lea     rdx, [rsp+1F8h+var_98]
0x1800172cc  lea     rcx, [rsp+1F8h+var_1A0]
0x1800172d1  call    ??$_Buynode@U?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@PEAX@1@$$QEAU?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@1@@Z; std::_Tree_buy<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>::_Buynode<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>(std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo> &&)
0x1800172d6  lea     r9, [rax+20h]
0x1800172da  mov     [rsp+1F8h+var_1D8], rax
0x1800172df  lea     rdx, [rsp+1F8h+var_158]
0x1800172e7  lea     rcx, [rsp+1F8h+var_1A0]
0x1800172ec  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UProcessInfo@CPostLogonProcess@PerfDiagBoot@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,PerfDiagBoot::CPostLogonProcess::ProcessInfo,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>>,0>>::_Insert_nohint<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>,void *> *>(bool,std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,PerfDiagBoot::CPostLogonProcess::ProcessInfo>,void *> *)
0x1800172f1  nop
0x1800172f2  cmp     [rsp+1F8h+var_78], 8
0x1800172fb  jb      short loc_18001730A
0x1800172fd  mov     rcx, [rsp+1F8h+Block]; Block
0x180017305  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001730a  mov     rcx, [rsp+1F8h+var_98]
0x180017312  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180017316  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001731b  nop
0x18001731c  cmp     [rsp+1F8h+var_C0], 8
0x180017325  jb      short loc_180017334
0x180017327  mov     rcx, [rsp+1F8h+var_D8]; Block
0x18001732f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017334  cmp     [rsp+1F8h+var_150], 0
0x18001733c  jnz     short loc_180017372
0x18001733e  mov     rax, [rsp+1F8h+var_158]
0x180017346  add     [rax+48h], edi
0x180017349  add     [rax+4Ch], esi
0x18001734c  mov     rcx, [rsp+1F8h+var_148]
  ... truncated ...
```
