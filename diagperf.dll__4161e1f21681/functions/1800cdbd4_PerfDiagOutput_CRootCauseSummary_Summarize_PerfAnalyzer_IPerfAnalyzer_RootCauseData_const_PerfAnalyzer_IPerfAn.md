# PerfDiagOutput::CRootCauseSummary::Summarize(PerfAnalyzer::IPerfAnalyzer::RootCauseData const *,PerfAnalyzer::IPerfAnalyzer const *,XPerfAddIn::IProcessInfoSource *,XPerfCore::IPathRegistry *,PerfDiagShared::Serializer::CStringInterner &)

- ea: `0x1800cdbd4`
- end: `0x1800ce745`
- name: `?Summarize@CRootCauseSummary@PerfDiagOutput@@QEAAJPEBURootCauseData@IPerfAnalyzer@PerfAnalyzer@@PEBU45@PEAUIProcessInfoSource@XPerfAddIn@@PEAUIPathRegistry@XPerfCore@@AEAVCStringInterner@Serializer@PerfDiagShared@@@Z`
- size: `2929`
- prototype: `__int64 __fastcall(PerfDiagOutput::CRootCauseSummary *__hidden this, const struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *, const struct PerfAnalyzer::IPerfAnalyzer *, struct XPerfAddIn::IProcessInfoSource *, struct XPerfCore::IPathRegistry *, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config`

## callers

- `0x1800b0880`

## callees

- `0x18001769c`
- `0x18001e180`
- `0x180026800`
- `0x18002b1b0`
- `0x18002be58`
- `0x1800368d8`
- `0x180056bc8`
- `0x18006dfdc`
- `0x1800ae20c`
- `0x1800c3820`
- `0x1800c3dc4`
- `0x1800c4130`
- `0x1800c45c0`
- `0x1800cba20`
- `0x1800cbba0`
- `0x1800cbd0c`
- `0x1800cbe20`
- `0x1800cbf60`
- `0x1800cd67c`
- `0x1800cd728`
- `0x1800cd7d0`
- `0x1800cd820`
- `0x1800cda84`
- `0x1800cdbd4`
- `0x1800ce84c`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdca5`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1800cdc9b`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1800cdc9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PerfDiagOutput::CRootCauseSummary::Summarize(
        PerfDiagOutput::CRootCauseSummary *this,
        const struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *a2,
        const struct PerfAnalyzer::IPerfAnalyzer *a3,
        struct XPerfAddIn::IProcessInfoSource *a4,
        struct XPerfCore::IPathRegistry *a5,
        struct PerfDiagShared::Serializer::CStringInterner *a6)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 v11; // rsi
  __int64 v12; // r12
  unsigned __int64 k; // rdx
  __int64 v14; // r8
  signed int LastError; // eax
  signed int v16; // r15d
  const struct PerfAnalyzer::IPerfAnalyzer *v17; // r13
  __int64 v18; // rsi
  struct XPerfCore::IPathRegistry *v19; // r13
  __int64 v20; // rbx
  unsigned __int64 v21; // r15
  unsigned __int16 *v22; // rdi
  const struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *v23; // rcx
  _DWORD *v24; // r12
  __int64 v25; // r15
  double v26; // xmm6_8
  double v27; // xmm7_8
  unsigned __int64 v28; // r13
  __int64 v29; // r11
  unsigned __int16 *v30; // rdx
  const struct XPerfAddIn::IProcessInfoSource::ProcessData *v31; // r8
  wchar_t *v32; // r15
  PerfDiagShared::CLocalNtImageFileVersionDecoder *v33; // rax
  __int64 *v34; // rax
  const unsigned __int16 *v35; // rax
  double v36; // xmm0_8
  unsigned __int64 v37; // rcx
  double v38; // xmm0_8
  double v39; // xmm0_8
  double v40; // xmm1_8
  __int64 v41; // r15
  __int64 v42; // r13
  const unsigned __int16 *v43; // rax
  PerfDiagShared::CLocalNtImageFileVersionDecoder *v44; // rax
  __int64 *DriverFileVersion; // rax
  __int64 j; // r13
  __int64 v47; // r8
  const unsigned __int16 *v48; // rax
  PerfDiagShared::CLocalNtImageFileVersionDecoder *v49; // rax
  __int64 *v50; // rax
  __int64 v51; // r15
  __int64 v52; // r13
  const unsigned __int16 *v53; // rax
  PerfDiagShared::CLocalNtImageFileVersionDecoder *v54; // rax
  __int64 *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  unsigned int i; // r12d
  unsigned int *v60; // rdx
  const struct XPerfAddIn::IProcessInfoSource::ProcessData *v61; // r8
  unsigned __int16 *v62; // rax
  PerfDiagShared::CLocalNtImageFileVersionDecoder *v63; // rax
  __int64 *FileVersion; // rax
  __int64 v66; // [rsp+30h] [rbp-1E8h] BYREF
  struct PerfDiagShared::Serializer::CStringInterner *v67; // [rsp+38h] [rbp-1E0h]
  struct XPerfCore::IPathRegistry *v68; // [rsp+40h] [rbp-1D8h]
  int v69; // [rsp+48h] [rbp-1D0h]
  const struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *v70; // [rsp+50h] [rbp-1C8h]
  PerfDiagOutput::CRootCauseSummary *v71; // [rsp+58h] [rbp-1C0h]
  unsigned __int16 *v72; // [rsp+60h] [rbp-1B8h] BYREF
  unsigned int *v73; // [rsp+68h] [rbp-1B0h] BYREF
  unsigned __int16 *v74; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v75; // [rsp+78h] [rbp-1A0h]
  _BYTE v76[8]; // [rsp+80h] [rbp-198h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-190h]
  __int64 v78; // [rsp+98h] [rbp-180h]
  __int64 v79; // [rsp+A0h] [rbp-178h]
  __int64 v80; // [rsp+A8h] [rbp-170h]
  __int64 v81; // [rsp+B0h] [rbp-168h]
  __int64 v82; // [rsp+B8h] [rbp-160h]
  double v83; // [rsp+C0h] [rbp-158h]
  double v84; // [rsp+D0h] [rbp-148h]
  unsigned __int64 ullTotalPhys; // [rsp+E0h] [rbp-138h]
  const struct PerfAnalyzer::IPerfAnalyzer *v86; // [rsp+E8h] [rbp-130h]
  unsigned __int64 v87; // [rsp+F0h] [rbp-128h]
  const struct PerfAnalyzer::IPerfAnalyzer *v88; // [rsp+F8h] [rbp-120h]
  int v89; // [rsp+100h] [rbp-118h] BYREF
  double v90; // [rsp+108h] [rbp-110h]
  _QWORD v91[3]; // [rsp+128h] [rbp-F0h] BYREF
  __int128 v92; // [rsp+140h] [rbp-D8h] BYREF
  __int64 v93; // [rsp+150h] [rbp-C8h]
  int v94; // [rsp+158h] [rbp-C0h]
  _MEMORYSTATUSEX Buffer; // [rsp+160h] [rbp-B8h] BYREF

  v86 = a3;
  v70 = a2;
  v71 = this;
  v88 = a3;
  v68 = a5;
  v67 = a6;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v72);
  v73 = 0;
  v8 = *((_QWORD *)a2 + 5);
  v9 = *((_QWORD *)a2 + 4);
  v10 = *((_QWORD *)a2 + 6);
  v11 = *((_QWORD *)a2 + 7);
  v12 = *((_QWORD *)a2 + 8);
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( !GlobalMemoryStatusEx(&Buffer) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v17 = v86;
LABEL_108:
    v22 = v72;
    goto LABEL_114;
  }
  v69 = 0;
  v18 = v8 + v9 + v10 + v12 + v11;
  ullTotalPhys = Buffer.ullTotalPhys;
  v91[0] = a4;
  v19 = v68;
  v91[1] = v68;
  v91[2] = v67;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v20 = 0;
  v66 = 0;
  v21 = 0;
  v22 = v72;
  v23 = v70;
  try
  {
    while ( 1 )
    {
      v87 = v21;
      if ( v21 >= *((_QWORD *)v23 + 1) )
      {
        std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::~auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>(
          &v66,
          k,
          v14,
          0xAAAAAAAAAAAAAAABuLL);
        ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v92);
        PerfDiagOutput::CRootCauseSummary::PruneLists(v71, v18);
        v16 = v69;
        v17 = v86;
        goto LABEL_114;
      }
      v24 = (_DWORD *)((char *)v23 + *((_QWORD *)v23 + 2 * v21 + 46));
      v25 = *((_QWORD *)v23 + 2 * v21 + 45);
      v75 = v25;
      switch ( v25 )
      {
        case 1LL:
        case 2LL:
          v17 = v86;
          v16 = (*(__int64 (__fastcall **)(const struct PerfAnalyzer::IPerfAnalyzer *, unsigned int **, _DWORD *))(*(_QWORD *)v86 + 48LL))(
                  v86,
                  &v73,
                  v24);
          v69 = v16;
          if ( v16 < 0 )
          {
            std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::~auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>(
              &v66,
              v56,
              v57,
              v58);
            ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v92);
            goto LABEL_114;
          }
          if ( !v73 )
          {
            v16 = -2147467261;
            std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::~auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>(
              &v66,
              v56,
              v57,
              v58);
            ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::~CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>(&v92);
            goto LABEL_114;
          }
          std::_Sort<PerfAnalyzer::IPerfAnalyzer::Contention::Blocker *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::Contention::Blocker const &,PerfAnalyzer::IPerfAnalyzer::Contention::Blocker const &)>(
            v73 + 4,
            &v73[4 * *v73 + 4],
            (16 * (*v73 + 1LL) - 16) >> 4);
          for ( i = 0; ; ++i )
          {
            v60 = v73;
            if ( i >= *v73 )
              break;
            v61 = *(const struct XPerfAddIn::IProcessInfoSource::ProcessData **)&v73[4 * i + 6];
            v62 = 0;
            v74 = 0;
            if ( v61 )
            {
              PerfDiagShared::CProcessImageNameLocator::GetProcessImageName(
                (PerfDiagShared::CProcessImageNameLocator *)v91,
                (const unsigned __int16 **)&v74,
                v61);
              v60 = v73;
              v62 = v74;
            }
            PerfDiagOutput::CRootCauseBlocker::CRootCauseBlocker(v76, v62, v18, *(_QWORD *)&v60[4 * i + 4]);
            if ( v83 < 5.0 )
              break;
            if ( Str )
            {
              if ( !v20 )
              {
                v63 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)operator new(0x88u);
                if ( v63 )
                  v63 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(
                                                                             v63,
                                                                             v67);
                std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(&v66, v63);
                v20 = v66;
              }
              FileVersion = (__int64 *)PerfDiagShared::CLocalNtImageFileVersionDecoder::GetFileVersion(v20, &v89, Str);
              v80 = *FileVersion;
              v78 = FileVersion[2];
              v79 = FileVersion[1];
              v81 = FileVersion[3];
              v82 = FileVersion[4];
            }
            if ( v75 == 1 )
            {
              std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back(v71, v76);
            }
            else if ( v75 == 2 )
            {
              std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back((char *)v71 + 48, v76);
            }
          }
          (*(void (__fastcall **)(const struct PerfAnalyzer::IPerfAnalyzer *))(*(_QWORD *)v17 + 56LL))(v17);
          v73 = 0;
          break;
        case 4LL:
          std::_Sort<PerfAnalyzer::IPerfAnalyzer::Fragmentation::FragmentedFileInfo *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::Fragmentation::FragmentedFileInfo const &,PerfAnalyzer::IPerfAnalyzer::Fragmentation::FragmentedFileInfo const &)>(
            v24 + 8,
            &v24[8 * *v24 + 8 + 2 * *v24],
            0xCCCCCCCCCCCCCCCDuLL * ((8 * ((unsigned int)*v24 + 4 * ((unsigned int)*v24 + 1LL)) - 32) >> 3));
          v51 = 0;
          while ( (unsigned int)v51 < *v24 )
          {
            PerfDiagOutput::GetPathName(&v72, v19, *(_QWORD *)&v24[10 * v51 + 12]);
            v52 = *(_QWORD *)&v24[10 * v51 + 8];
            v22 = v72;
            if ( *((_DWORD *)v72 - 4) )
              v53 = PerfDiagShared::Serializer::CStringInterner::Intern(v67, v72);
            else
              v53 = 0;
            PerfDiagOutput::CRootCauseBlocker::CRootCauseBlocker(v76, v53, v18, v52);
            if ( Str )
            {
              if ( !v20 )
              {
                v54 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)operator new(0x88u);
                if ( v54 )
                  v54 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(
                                                                             v54,
                                                                             v67);
                std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(&v66, v54);
                v20 = v66;
              }
              v55 = (__int64 *)PerfDiagShared::CLocalNtImageFileVersionDecoder::GetFileVersion(v20, &v89, Str);
              v80 = *v55;
              v78 = v55[2];
              v79 = v55[1];
              v81 = v55[3];
              v82 = v55[4];
            }
            std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back((char *)v71 + 120, v76);
            v51 = (unsigned int)(v51 + 1);
            v19 = v68;
          }
          goto LABEL_105;
        case 5LL:
        case 6LL:
          std::_Sort<XPerfAddIn::IDpcIsrInfoSource::TimeByModule *,__int64,bool (*)(XPerfAddIn::IDpcIsrInfoSource::TimeByModule const &,XPerfAddIn::IDpcIsrInfoSource::TimeByModule const &)>(
            v24 + 6,
            &v24[6 * *v24 + 6],
            0xAAAAAAAAAAAAAAABuLL * ((24 * ((unsigned int)*v24 + 1LL) - 24) >> 3));
          for ( j = 0; (unsigned int)j < *v24; j = (unsigned int)(j + 1) )
          {
            v47 = *(_QWORD *)&v24[6 * j + 8];
            v48 = 0;
            if ( v47 )
            {
              PerfDiagOutput::GetPathName(&v72, v68, *(_QWORD *)(v47 + 56));
              v22 = v72;
              if ( *((_DWORD *)v72 - 4) )
                v48 = PerfDiagShared::Serializer::CStringInterner::Intern(v67, v72);
              else
                v48 = 0;
            }
            PerfDiagOutput::CRootCauseBlocker::CRootCauseBlocker(v76, v48, v18, *(_QWORD *)&v24[6 * j + 6]);
            if ( v83 < 5.0 )
              break;
            if ( Str )
            {
              if ( !v20 )
              {
                v49 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)operator new(0x88u);
                if ( v49 )
                  v49 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(
                                                                             v49,
                                                                             v67);
                std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(&v66, v49);
                v20 = v66;
              }
              v50 = (__int64 *)PerfDiagShared::CLocalNtImageFileVersionDecoder::GetFileVersion(v20, &v89, Str);
              v80 = *v50;
              v78 = v50[2];
              v79 = v50[1];
              v81 = v50[3];
              v82 = v50[4];
            }
            if ( v75 == 6 )
            {
              std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back((char *)v71 + 72, v76);
            }
            else if ( v75 == 5 )
            {
              std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back((char *)v71 + 24, v76);
            }
          }
          break;
        case 7LL:
          std::_Sort<PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &,PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &)>(
            v24 + 2,
            &v24[12 * *v24 + 2],
            0xAAAAAAAAAAAAAAABuLL * ((48LL * (unsigned int)*v24) >> 4));
          v41 = 0;
          while ( (unsigned int)v41 < *v24 )
          {
            PerfDiagOutput::GetPathName(&v72, v19, *(_QWORD *)&v24[12 * v41 + 2]);
            v42 = *(_QWORD *)&v24[12 * v41 + 10];
            v22 = v72;
            if ( *((_DWORD *)v72 - 4) )
              v43 = PerfDiagShared::Serializer::CStringInterner::Intern(v67, v72);
            else
              v43 = 0;
            PerfDiagOutput::CRootCauseBlocker::CRootCauseBlocker(v76, v43, v18, v42);
            if ( Str )
            {
              if ( !v20 )
              {
                v44 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)operator new(0x88u);
                if ( v44 )
                  v44 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(
                                                                             v44,
                                                                             v67);
                std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(&v66, v44);
                v20 = v66;
              }
              DriverFileVersion = (__int64 *)PerfDiagShared::CLocalNtImageFileVersionDecoder::GetDriverFileVersion(
                                               v20,
                                               &v89,
                                               Str);
              v80 = *DriverFileVersion;
              v78 = DriverFileVersion[2];
              v79 = DriverFileVersion[1];
              v81 = DriverFileVersion[3];
              v82 = DriverFileVersion[4];
            }
            std::vector<XPerfAddIn::IDXVA2InfoSource::CDXVA2Fxn>::push_back((char *)v71 + 96, v76);
            v41 = (unsigned int)(v41 + 1);
            v19 = v68;
          }
          goto LABEL_105;
        case 8LL:
          v26 = 0.0;
          v27 = 0.0;
          std::_Sort<PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &,PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &)>(
            v24 + 4,
            &v24[26 * *(_QWORD *)v24 + 4],
            0x4EC4EC4EC4EC4EC5LL * ((104LL * *(_QWORD *)v24) >> 3));
          v28 = 0;
          v29 = ullTotalPhys;
          while ( v28 < *(_QWORD *)v24 )
          {
            v30 = 0;
            v74 = 0;
            v31 = *(const struct XPerfAddIn::IProcessInfoSource::ProcessData **)&v24[26 * v28 + 4];
            if ( v31 )
            {
              PerfDiagShared::CProcessImageNameLocator::GetProcessImageName(
                (PerfDiagShared::CProcessImageNameLocator *)v91,
                (const unsigned __int16 **)&v74,
                v31);
              v30 = v74;
              v29 = ullTotalPhys;
            }
            PerfDiagOutput::CRootCausePageFault::CRootCausePageFault(
              (PerfDiagOutput::CRootCausePageFault *)v76,
              v30,
              *(_QWORD *)&v24[26 * v28 + 20],
              *(_QWORD *)&v24[26 * v28 + 10],
              *(_DWORD *)(*(_QWORD *)&v24[26 * v28 + 4] + 32LL),
              v29);
            if ( v84 < 5.0 )
              break;
            v32 = Str;
            if ( Str )
            {
              if ( !v20 )
              {
                v33 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)operator new(0x88u);
                if ( v33 )
                  v33 = (PerfDiagShared::CLocalNtImageFileVersionDecoder *)PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(
                                                                             v33,
                                                                             v67);
                std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(&v66, v33);
                v20 = v66;
              }
              v34 = (__int64 *)PerfDiagShared::CLocalNtImageFileVersionDecoder::GetFileVersion(v20, &v89, v32);
              v80 = *v34;
              v78 = v34[2];
              v79 = v34[1];
              v81 = v34[3];
              v82 = v34[4];
              v35 = (const unsigned __int16 *)PerfDiagOutput::FilenameFromPath(v32);
              Str = (wchar_t *)PerfDiagShared::Serializer::CStringInterner::Intern(v67, v35);
            }
            std::vector<PerfDiagOutput::CRootCausePageFault>::push_back((char *)v71 + 144, v76);
            v27 = v27 + (double)SLODWORD(v83);
            v29 = ullTotalPhys;
            v36 = (ullTotalPhys & 0x8000000000000000uLL) != 0LL
                ? (double)(int)(ullTotalPhys & 1 | (ullTotalPhys >> 1))
                + (double)(int)(ullTotalPhys & 1 | (ullTotalPhys >> 1))
                : (double)(int)ullTotalPhys;
            v26 = v27 * 100.0 / v36;
            if ( v26 > 50.0 )
              break;
            ++v28;
          }
          if ( v26 < 50.0 )
          {
            v37 = 0;
            for ( k = 0; k < *(_QWORD *)v24; ++k )
              v37 += *(_QWORD *)&v24[26 * k + 20];
            v89 = v37 >> 10;
            if ( (v37 & 0x8000000000000000uLL) != 0LL )
              v38 = (double)(int)(v37 & 1 | (v37 >> 1)) + (double)(int)(v37 & 1 | (v37 >> 1));
            else
              v38 = (double)(int)v37;
            v39 = v38 * 100.0;
            if ( v29 < 0 )
              v40 = (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1))
                  + (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1));
            else
              v40 = (double)(int)v29;
            v90 = v39 / v40;
            if ( v39 / v40 > 65.0 )
              std::vector<XPerfAddIn::ISysConfigInfoSource::PnPRecord>::push_back((char *)v71 + 168, &v89);
          }
          break;
        default:
          goto LABEL_106;
      }
      v19 = v68;
LABEL_105:
      v23 = v70;
LABEL_106:
      v21 = v87 + 1;
    }
  }
  catch ( std::bad_alloc )
  {
    v69 = -2147024882;
    v16 = -2147024882;
    v17 = v88;
    goto LABEL_108;
  }
LABEL_114:
  if ( v73 )
    (*(void (__fastcall **)(const struct PerfAnalyzer::IPerfAnalyzer *))(*(_QWORD *)v17 + 56LL))(v17);
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800cdbd4  mov     rax, rsp
0x1800cdbd7  mov     [rax+20h], rbx
0x1800cdbdb  push    rsi
0x1800cdbdc  push    rdi
0x1800cdbdd  push    r12
0x1800cdbdf  push    r13
0x1800cdbe1  push    r15
0x1800cdbe3  sub     rsp, 1F0h
0x1800cdbea  movaps  xmmword ptr [rax-38h], xmm6
0x1800cdbee  movaps  xmmword ptr [rax-48h], xmm7
0x1800cdbf2  movaps  xmmword ptr [rax-58h], xmm8
0x1800cdbf7  movaps  xmmword ptr [rax-68h], xmm9
0x1800cdbfc  mov     rax, cs:__security_cookie
0x1800cdc03  xor     rax, rsp
0x1800cdc06  mov     [rsp+218h+var_78], rax
0x1800cdc0e  mov     r13, r9
0x1800cdc11  mov     [rsp+218h+var_130], r8
0x1800cdc19  mov     r12, rdx
0x1800cdc1c  mov     [rsp+218h+var_1C8], rdx
0x1800cdc21  mov     [rsp+218h+var_1C0], rcx
0x1800cdc26  mov     [rsp+218h+var_120], r8
0x1800cdc2e  mov     rax, [rsp+218h+arg_20]
0x1800cdc36  mov     [rsp+218h+var_1D8], rax
0x1800cdc3b  mov     rax, [rsp+218h+arg_28]
0x1800cdc43  mov     [rsp+218h+var_1E0], rax
0x1800cdc48  lea     rcx, [rsp+218h+var_1B8]
0x1800cdc4d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800cdc52  nop
0x1800cdc53  mov     [rsp+218h+var_1B0], 0
0x1800cdc5c  mov     rbx, [r12+28h]
0x1800cdc61  mov     rdi, [r12+20h]
0x1800cdc66  mov     r15, [r12+30h]
0x1800cdc6b  mov     rsi, [r12+38h]
0x1800cdc70  mov     r12, [r12+40h]
0x1800cdc75  xor     edx, edx; Val
0x1800cdc77  lea     r8d, [rdx+40h]; Size
0x1800cdc7b  lea     rcx, [rsp+218h+Buffer]; void *
0x1800cdc83  call    memset_0
0x1800cdc88  mov     [rsp+218h+Buffer.dwLength], 40h ; '@'
0x1800cdc93  lea     rcx, [rsp+218h+Buffer]; lpBuffer
0x1800cdc9b  call    cs:__imp_GlobalMemoryStatusEx
0x1800cdca1  test    eax, eax
0x1800cdca3  jnz     short loc_1800CDCCA
0x1800cdca5  call    cs:__imp_GetLastError
0x1800cdcab  mov     r15d, eax
0x1800cdcae  test    eax, eax
0x1800cdcb0  jle     short loc_1800CDCBD
0x1800cdcb2  movzx   r15d, ax
0x1800cdcb6  or      r15d, 80070000h
0x1800cdcbd  mov     r13, [rsp+218h+var_130]
0x1800cdcc5  jmp     loc_1800CE6DD
0x1800cdcca  mov     [rsp+218h+var_1D0], 0
0x1800cdcd2  add     rsi, r12
0x1800cdcd5  add     rsi, r15
0x1800cdcd8  add     rsi, rdi
0x1800cdcdb  add     rsi, rbx
0x1800cdcde  mov     rax, [rsp+218h+Buffer.ullTotalPhys]
0x1800cdce6  mov     [rsp+218h+var_138], rax
0x1800cdcee  mov     [rsp+218h+var_F0], r13
0x1800cdcf6  mov     r13, [rsp+218h+var_1D8]
0x1800cdcfb  mov     [rsp+218h+var_E8], r13
0x1800cdd03  mov     rax, [rsp+218h+var_1E0]
0x1800cdd08  mov     [rsp+218h+var_E0], rax
0x1800cdd10  xorps   xmm0, xmm0
0x1800cdd13  movdqu  [rsp+218h+var_D8], xmm0
0x1800cdd1c  mov     [rsp+218h+var_C8], 0
0x1800cdd28  mov     [rsp+218h+var_C0], 0
0x1800cdd33  xor     ebx, ebx
0x1800cdd35  mov     [rsp+218h+var_1E8], rbx
0x1800cdd3a  xor     r15d, r15d
0x1800cdd3d  mov     r9, 0AAAAAAAAAAAAAAABh
0x1800cdd47  mov     rdi, [rsp+218h+var_1B8]
0x1800cdd4c  movsd   xmm8, cs:__real@4014000000000000
0x1800cdd55  movsd   xmm9, cs:__real@4049000000000000
0x1800cdd5e  mov     rcx, [rsp+218h+var_1C8]
0x1800cdd63  mov     [rsp+218h+var_128], r15
0x1800cdd6b  cmp     r15, [rcx+8]
0x1800cdd6f  jnb     loc_1800CE69B
0x1800cdd75  lea     rax, [r15+17h]
0x1800cdd79  add     rax, rax
0x1800cdd7c  mov     r12, [rcx+rax*8]
0x1800cdd80  add     r12, rcx
0x1800cdd83  mov     rax, r15
0x1800cdd86  add     rax, rax
0x1800cdd89  mov     r15, [rcx+rax*8+168h]
0x1800cdd91  mov     [rsp+218h+var_1A0], r15
0x1800cdd96  mov     rax, r15
0x1800cdd99  sub     rax, 1
0x1800cdd9d  jz      loc_1800CE47F
0x1800cdda3  sub     rax, 1
0x1800cdda7  jz      loc_1800CE47F
0x1800cddad  sub     rax, 2
0x1800cddb1  jz      loc_1800CE33B
0x1800cddb7  sub     rax, 1
0x1800cddbb  jz      loc_1800CE1BD
0x1800cddc1  sub     rax, 1
0x1800cddc5  jz      loc_1800CE1BD
0x1800cddcb  sub     rax, 1
0x1800cddcf  jz      loc_1800CE07D
0x1800cddd5  cmp     rax, 1
0x1800cddd9  jnz     loc_1800CE68B
0x1800cdddf  xorps   xmm6, xmm6
0x1800cdde2  xorps   xmm7, xmm7
0x1800cdde5  imul    rdx, [r12], 68h ; 'h'
0x1800cddea  add     rdx, 10h
0x1800cddee  add     rdx, r12
0x1800cddf1  lea     rcx, [r12+10h]
0x1800cddf6  mov     r8, rdx
0x1800cddf9  sub     r8, rcx
0x1800cddfc  sar     r8, 3
0x1800cde00  mov     rax, 4EC4EC4EC4EC4EC5h
0x1800cde0a  imul    r8, rax
0x1800cde0e  call    ??$_Sort@PEAUProcessPerfCounters@MemoryUsageInfo@IPerfAnalyzer@PerfAnalyzer@@_JP6A_NAEBU1234@0@Z@std@@YAXPEAUProcessPerfCounters@MemoryUsageInfo@IPerfAnalyzer@PerfAnalyzer@@0_JP6A_NAEBU1234@2@Z@Z; std::_Sort<PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &,PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &)>(PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters *,PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &,PerfAnalyzer::IPerfAnalyzer::MemoryUsageInfo::ProcessPerfCounters const &))
0x1800cde13  xor     r13d, r13d
0x1800cde16  mov     r11, [rsp+218h+var_138]
0x1800cde1e  cmp     r13, [r12]
0x1800cde22  jnb     loc_1800CDFBC
0x1800cde28  xor     edx, edx
0x1800cde2a  mov     [rsp+218h+var_1A8], rdx
0x1800cde2f  imul    r15, r13, 68h ; 'h'
0x1800cde33  mov     r8, [r15+r12+10h]; struct XPerfAddIn::IProcessInfoSource::ProcessData *
0x1800cde38  test    r8, r8
0x1800cde3b  jz      short loc_1800CDE5C
0x1800cde3d  lea     rdx, [rsp+218h+var_1A8]; unsigned __int16 **
0x1800cde42  lea     rcx, [rsp+218h+var_F0]; this
0x1800cde4a  call    ?GetProcessImageName@CProcessImageNameLocator@PerfDiagShared@@QEAAJAEAPEBGPEBUProcessData@IProcessInfoSource@XPerfAddIn@@@Z; PerfDiagShared::CProcessImageNameLocator::GetProcessImageName(ushort const * &,XPerfAddIn::IProcessInfoSource::ProcessData const *)
0x1800cde4f  mov     rdx, [rsp+218h+var_1A8]; unsigned __int16 *
0x1800cde54  mov     r11, [rsp+218h+var_138]
0x1800cde5c  mov     rax, [r15+r12+10h]
0x1800cde61  mov     [rsp+218h+var_1F0], r11; unsigned __int64
0x1800cde66  mov     eax, [rax+20h]
0x1800cde69  mov     [rsp+218h+var_1F8], eax; unsigned int
0x1800cde6d  mov     r9, [r15+r12+28h]; unsigned __int64
0x1800cde72  mov     r8, [r15+r12+50h]; unsigned __int64
0x1800cde77  lea     rcx, [rsp+218h+var_198]; this
0x1800cde7f  call    ??0CRootCausePageFault@PerfDiagOutput@@QEAA@PEBG_K1K1@Z; PerfDiagOutput::CRootCausePageFault::CRootCausePageFault(ushort const *,unsigned __int64,unsigned __int64,ulong,unsigned __int64)
0x1800cde84  comisd  xmm8, [rsp+218h+var_148]
0x1800cde8e  ja      loc_1800CDFBC
0x1800cde94  mov     r15, [rsp+218h+Str]
0x1800cde9c  test    r15, r15
0x1800cde9f  jz      loc_1800CDF43
0x1800cdea5  test    rbx, rbx
0x1800cdea8  jnz     short loc_1800CDED8
0x1800cdeaa  mov     ecx, 88h; Size
0x1800cdeaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cdeb4  test    rax, rax
0x1800cdeb7  jz      short loc_1800CDEC6
0x1800cdeb9  mov     rdx, [rsp+218h+var_1E0]; struct PerfDiagShared::Serializer::CStringInterner *
0x1800cdebe  mov     rcx, rax; this
0x1800cdec1  call    ??0CLocalNtImageFileVersionDecoder@PerfDiagShared@@QEAA@AEAVCStringInterner@Serializer@1@@Z; PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(PerfDiagShared::Serializer::CStringInterner &)
0x1800cdec6  mov     rdx, rax
0x1800cdec9  lea     rcx, [rsp+218h+var_1E8]
0x1800cdece  call    ?reset@?$auto_ptr@VCLocalNtImageFileVersionDecoder@PerfDiagShared@@@std@@QEAAXPEAVCLocalNtImageFileVersionDecoder@PerfDiagShared@@@Z; std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(PerfDiagShared::CLocalNtImageFileVersionDecoder *)
0x1800cded3  mov     rbx, [rsp+218h+var_1E8]
0x1800cded8  mov     r8, r15
0x1800cdedb  lea     rdx, [rsp+218h+var_118]
0x1800cdee3  mov     rcx, rbx
0x1800cdee6  call    ?GetFileVersion@CLocalNtImageFileVersionDecoder@PerfDiagShared@@QEAA?AUCFileVersion@2@PEBG@Z; PerfDiagShared::CLocalNtImageFileVersionDecoder::GetFileVersion(ushort const *)
0x1800cdeeb  mov     rcx, [rax]
0x1800cdeee  mov     [rsp+218h+var_170], rcx
0x1800cdef6  mov     rcx, [rax+10h]
0x1800cdefa  mov     [rsp+218h+var_180], rcx
0x1800cdf02  mov     rcx, [rax+8]
0x1800cdf06  mov     [rsp+218h+var_178], rcx
0x1800cdf0e  mov     rcx, [rax+18h]
0x1800cdf12  mov     [rsp+218h+var_168], rcx
0x1800cdf1a  mov     rax, [rax+20h]
0x1800cdf1e  mov     [rsp+218h+var_160], rax
0x1800cdf26  mov     rcx, r15; Str
0x1800cdf29  call    PerfDiagOutput__FilenameFromPath
0x1800cdf2e  mov     rdx, rax; unsigned __int16 *
0x1800cdf31  mov     rcx, [rsp+218h+var_1E0]; this
0x1800cdf36  call    ?Intern@CStringInterner@Serializer@PerfDiagShared@@QEAAPEBGPEBG@Z; PerfDiagShared::Serializer::CStringInterner::Intern(ushort const *)
0x1800cdf3b  mov     [rsp+218h+Str], rax
0x1800cdf43  mov     rcx, [rsp+218h+var_1C0]
0x1800cdf48  add     rcx, 90h
0x1800cdf4f  lea     rdx, [rsp+218h+var_198]
0x1800cdf57  call    ?push_back@?$vector@VCRootCausePageFault@PerfDiagOutput@@V?$allocator@VCRootCausePageFault@PerfDiagOutput@@@std@@@std@@QEAAXAEBVCRootCausePageFault@PerfDiagOutput@@@Z; std::vector<PerfDiagOutput::CRootCausePageFault>::push_back(PerfDiagOutput::CRootCausePageFault const &)
0x1800cdf5c  mov     eax, dword ptr [rsp+218h+var_158]
0x1800cdf63  xorps   xmm0, xmm0
0x1800cdf66  cvtsi2sd xmm0, rax
0x1800cdf6b  addsd   xmm7, xmm0
0x1800cdf6f  movaps  xmm6, xmm7
0x1800cdf72  mulsd   xmm6, cs:__real@4059000000000000
0x1800cdf7a  mov     r11, [rsp+218h+var_138]
0x1800cdf82  xorps   xmm0, xmm0
0x1800cdf85  test    r11, r11
0x1800cdf88  js      short loc_1800CDF91
0x1800cdf8a  cvtsi2sd xmm0, r11
0x1800cdf8f  jmp     short loc_1800CDFA9
0x1800cdf91  mov     rcx, r11
0x1800cdf94  shr     rcx, 1
0x1800cdf97  mov     rax, r11
0x1800cdf9a  and     eax, 1
0x1800cdf9d  or      rcx, rax
0x1800cdfa0  cvtsi2sd xmm0, rcx
0x1800cdfa5  addsd   xmm0, xmm0
0x1800cdfa9  divsd   xmm6, xmm0
0x1800cdfad  comisd  xmm6, xmm9
0x1800cdfb2  ja      short loc_1800CDFBC
0x1800cdfb4  inc     r13
0x1800cdfb7  jmp     loc_1800CDE1E
0x1800cdfbc  comisd  xmm9, xmm6
0x1800cdfc1  jbe     loc_1800CE677
0x1800cdfc7  xor     ecx, ecx
0x1800cdfc9  xor     edx, edx
0x1800cdfcb  cmp     [r12], rcx
0x1800cdfcf  jbe     short loc_1800CDFE3
0x1800cdfd1  imul    rax, rdx, 68h ; 'h'
0x1800cdfd5  add     rcx, [rax+r12+50h]
0x1800cdfda  inc     rdx
0x1800cdfdd  cmp     rdx, [r12]
0x1800cdfe1  jb      short loc_1800CDFD1
0x1800cdfe3  mov     rax, rcx
0x1800cdfe6  shr     rax, 0Ah
0x1800cdfea  mov     [rsp+218h+var_118], eax
0x1800cdff1  xorps   xmm0, xmm0
0x1800cdff4  test    rcx, rcx
0x1800cdff7  js      short loc_1800CE000
0x1800cdff9  cvtsi2sd xmm0, rcx
0x1800cdffe  jmp     short loc_1800CE015
0x1800ce000  mov     rax, rcx
0x1800ce003  shr     rax, 1
0x1800ce006  and     ecx, 1
0x1800ce009  or      rax, rcx
0x1800ce00c  cvtsi2sd xmm0, rax
0x1800ce011  addsd   xmm0, xmm0
0x1800ce015  mulsd   xmm0, cs:__real@4059000000000000
0x1800ce01d  xorps   xmm1, xmm1
0x1800ce020  test    r11, r11
0x1800ce023  js      short loc_1800CE02C
0x1800ce025  cvtsi2sd xmm1, r11
0x1800ce02a  jmp     short loc_1800CE044
0x1800ce02c  mov     rcx, r11
0x1800ce02f  shr     rcx, 1
0x1800ce032  mov     rax, r11
0x1800ce035  and     eax, 1
0x1800ce038  or      rcx, rax
0x1800ce03b  cvtsi2sd xmm1, rcx
0x1800ce040  addsd   xmm1, xmm1
0x1800ce044  divsd   xmm0, xmm1
0x1800ce048  movsd   [rsp+218h+var_110], xmm0
0x1800ce051  comisd  xmm0, cs:__real@4050400000000000
0x1800ce059  jbe     loc_1800CE677
0x1800ce05f  mov     rcx, [rsp+218h+var_1C0]
0x1800ce064  add     rcx, 0A8h
0x1800ce06b  lea     rdx, [rsp+218h+var_118]
0x1800ce073  call    ?push_back@?$vector@UPnPRecord@ISysConfigInfoSource@XPerfAddIn@@V?$allocator@UPnPRecord@ISysConfigInfoSource@XPerfAddIn@@@std@@@std@@QEAAXAEBUPnPRecord@ISysConfigInfoSource@XPerfAddIn@@@Z; std::vector<XPerfAddIn::ISysConfigInfoSource::PnPRecord>::push_back(XPerfAddIn::ISysConfigInfoSource::PnPRecord const &)
0x1800ce078  jmp     loc_1800CE677
0x1800ce07d  mov     eax, [r12]
0x1800ce081  lea     rdx, [rax+rax*2]
0x1800ce085  shl     rdx, 4
0x1800ce089  add     rdx, 8
0x1800ce08d  add     rdx, r12
0x1800ce090  lea     rcx, [r12+8]
0x1800ce095  mov     r8, rdx
0x1800ce098  sub     r8, rcx
0x1800ce09b  sar     r8, 4
0x1800ce09f  imul    r8, r9
0x1800ce0a3  call    ??$_Sort@PEAUIoStats@LongDiskIo@IPerfAnalyzer@PerfAnalyzer@@_JP6A_NAEBU1234@0@Z@std@@YAXPEAUIoStats@LongDiskIo@IPerfAnalyzer@PerfAnalyzer@@0_JP6A_NAEBU1234@2@Z@Z; std::_Sort<PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &,PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &)>(PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats *,PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats *,__int64,bool (*)(PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &,PerfAnalyzer::IPerfAnalyzer::LongDiskIo::IoStats const &))
0x1800ce0a8  xor     r15d, r15d
0x1800ce0ab  cmp     r15d, [r12]
0x1800ce0af  jnb     loc_1800CE67C
0x1800ce0b5  lea     rdi, [r15+r15*2]
0x1800ce0b9  add     rdi, rdi
0x1800ce0bc  mov     r8, [r12+rdi*8+8]
0x1800ce0c1  mov     rdx, r13
0x1800ce0c4  lea     rcx, [rsp+218h+var_1B8]
0x1800ce0c9  call    PerfDiagOutput__GetPathName
0x1800ce0ce  mov     r13, [r12+rdi*8+28h]
0x1800ce0d3  mov     rdi, [rsp+218h+var_1B8]
0x1800ce0d8  cmp     dword ptr [rdi-10h], 0
0x1800ce0dc  jz      short loc_1800CE0ED
0x1800ce0de  mov     rdx, rdi; unsigned __int16 *
0x1800ce0e1  mov     rcx, [rsp+218h+var_1E0]; this
0x1800ce0e6  call    ?Intern@CStringInterner@Serializer@PerfDiagShared@@QEAAPEBGPEBG@Z; PerfDiagShared::Serializer::CStringInterner::Intern(ushort const *)
0x1800ce0eb  jmp     short loc_1800CE0EF
0x1800ce0ed  xor     eax, eax
0x1800ce0ef  mov     r9, r13
0x1800ce0f2  mov     r8, rsi
0x1800ce0f5  mov     rdx, rax
0x1800ce0f8  lea     rcx, [rsp+218h+var_198]
0x1800ce100  call    ??0CRootCauseBlocker@PerfDiagOutput@@QEAA@PEBGVTimeStampDelta@XPerfCore@@1@Z; PerfDiagOutput::CRootCauseBlocker::CRootCauseBlocker(ushort const *,XPerfCore::TimeStampDelta,XPerfCore::TimeStampDelta)
0x1800ce105  cmp     [rsp+218h+Str], 0
0x1800ce10e  jz      loc_1800CE19A
0x1800ce114  test    rbx, rbx
0x1800ce117  jnz     short loc_1800CE147
0x1800ce119  mov     ecx, 88h; Size
0x1800ce11e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ce123  test    rax, rax
0x1800ce126  jz      short loc_1800CE135
0x1800ce128  mov     rdx, [rsp+218h+var_1E0]; struct PerfDiagShared::Serializer::CStringInterner *
0x1800ce12d  mov     rcx, rax; this
0x1800ce130  call    ??0CLocalNtImageFileVersionDecoder@PerfDiagShared@@QEAA@AEAVCStringInterner@Serializer@1@@Z; PerfDiagShared::CLocalNtImageFileVersionDecoder::CLocalNtImageFileVersionDecoder(PerfDiagShared::Serializer::CStringInterner &)
0x1800ce135  mov     rdx, rax
0x1800ce138  lea     rcx, [rsp+218h+var_1E8]
0x1800ce13d  call    ?reset@?$auto_ptr@VCLocalNtImageFileVersionDecoder@PerfDiagShared@@@std@@QEAAXPEAVCLocalNtImageFileVersionDecoder@PerfDiagShared@@@Z; std::auto_ptr<PerfDiagShared::CLocalNtImageFileVersionDecoder>::reset(PerfDiagShared::CLocalNtImageFileVersionDecoder *)
0x1800ce142  mov     rbx, [rsp+218h+var_1E8]
0x1800ce147  mov     r8, [rsp+218h+Str]
0x1800ce14f  lea     rdx, [rsp+218h+var_118]
  ... truncated ...
```
