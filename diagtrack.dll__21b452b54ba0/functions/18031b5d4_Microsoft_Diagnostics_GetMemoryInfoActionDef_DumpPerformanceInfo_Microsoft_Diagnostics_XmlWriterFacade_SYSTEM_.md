# Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(Microsoft::Diagnostics::XmlWriterFacade &,_SYSTEM_PERFORMANCE_INFORMATION const &,_PERFORMANCE_INFORMATION const &,_EDP_ENFORCEMENT_LEVEL)

- ea: `0x18031b5d4`
- end: `0x18031cca8`
- name: `?DumpPerformanceInfo@GetMemoryInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@AEBU_SYSTEM_PERFORMANCE_INFORMATION@@AEBU_PERFORMANCE_INFORMATION@@W4_EDP_ENFORCEMENT_LEVEL@@@Z`
- size: `5844`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18031ea00`

## callees

- `0x18001a8f0`
- `0x18001b24c`
- `0x18002b318`
- `0x180312c78`
- `0x18031310c`
- `0x18031321c`

## string_xrefs

- `0x18031b6ff`: `IoReadOperationCount`
- `0x18031b73f`: `IoWriteOperationCount`
- `0x18031b5f4`: `systemperformanceinfo`
- `0x18031b68f`: `IoWriteTransferCount`
- `0x18031b657`: `IoReadTransferCount`
- `0x18031b8ed`: `CopyOnWriteCount`
- `0x18031b967`: `CacheTransitionCount`
- `0x18031b7f6`: `CommittedPages`
- `0x18031b873`: `PeakCommitment`
- `0x18031b833`: `CommitLimit`
- `0x18031bb12`: `DirtyWriteIoCount`
- `0x18031bad5`: `DirtyPagesWriteCount`
- `0x18031bb8c`: `MappedWriteIoCount`
- `0x18031bb4f`: `MappedPagesWriteCount`
- `0x18031ba1e`: `PageReadIoCount`
- `0x18031b9e1`: `PageReadCount`
- `0x18031ba98`: `CacheIoCount`
- `0x18031ba5b`: `CacheReadCount`
- `0x18031bd7d`: `ResidentSystemCodePage`
- `0x18031bd3d`: `FreeSystemPtes`
- `0x18031befd`: `ResidentSystemCachePage`
- `0x18031bf7d`: `ResidentSystemDriverPage`
- `0x18031bf3d`: `ResidentPagedPoolPage`
- `0x18031be7d`: `PagedPoolLookasideHits`
- `0x18031be3d`: `NonPagedPoolLookasideHits`
- `0x18031c0fd`: `CcFastMdlReadWait`
- `0x18031c0bd`: `CcFastMdlReadNoWait`
- `0x18031c17d`: `CcFastMdlReadNotPossible`
- `0x18031c13d`: `CcFastMdlReadResourceMiss`
- `0x18031bffd`: `CcFastReadWait`
- `0x18031bfbd`: `CcFastReadNoWait`
- `0x18031c07d`: `CcFastReadNotPossible`
- `0x18031c03d`: `CcFastReadResourceMiss`
- `0x18031c2fd`: `CcPinReadNoWait`
- `0x18031c37d`: `CcPinReadNoWaitMiss`
- `0x18031c33d`: `CcPinReadWait`
- `0x18031c4fd`: `CcMdlReadNoWait`
- `0x18031c4bd`: `CcCopyReadWaitMiss`
- `0x18031c57d`: `CcMdlReadNoWaitMiss`
- `0x18031c53d`: `CcMdlReadWait`
- `0x18031c3fd`: `CcCopyReadNoWait`
- `0x18031c3bd`: `CcPinReadWaitMiss`
- `0x18031c47d`: `CcCopyReadNoWaitMiss`
- `0x18031c43d`: `CcCopyReadWait`
- `0x18031c5fd`: `CcReadAheadIos`
- `0x18031c5bd`: `CcMdlReadWaitMiss`
- `0x18031c67d`: `CcLazyWritePages`
- `0x18031c63d`: `CcLazyWriteIos`
- `0x18031c938`: `CommitTotal`
- `0x18031c8f8`: `SharedCommittedPages`
- `0x18031c9ae`: `CommitPeak`
- `0x18031c8bd`: `ResidentAvailablePages`
- `0x18031cc10`: `ThreadCount`
- `0x18031ca65`: `SystemCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  const wchar_t *v8; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+38h] [rbp-30h]
  const wchar_t *v10; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h]
  _BYTE v12[24]; // [rsp+50h] [rbp-18h] BYREF
  int v13; // [rsp+C8h] [rbp+60h] BYREF

  v8 = L"systemperformanceinfo";
  v9 = std::_WChar_traits<wchar_t>::length(L"systemperformanceinfo");
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a1, v12, &v8);
  v8 = L"IdleProcessTime";
  v9 = std::_WChar_traits<wchar_t>::length(L"IdleProcessTime");
  v10 = L"info";
  v11 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v10, &v8, a2);
  v10 = L"IoReadTransferCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoReadTransferCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 8);
  v10 = L"IoWriteTransferCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoWriteTransferCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 16);
  v10 = L"IoOtherTransferCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoOtherTransferCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 24);
  v10 = L"IoReadOperationCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoReadOperationCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 32,
    0);
  v10 = L"IoWriteOperationCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoWriteOperationCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 36,
    0);
  v10 = L"IoOtherOperationCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"IoOtherOperationCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 40,
    0);
  v10 = L"AvailablePages";
  v11 = std::_WChar_traits<wchar_t>::length(L"AvailablePages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 44,
    0);
  v10 = L"CommittedPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"CommittedPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 48,
    0);
  v10 = L"CommitLimit";
  v11 = std::_WChar_traits<wchar_t>::length(L"CommitLimit");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 52,
    0);
  v10 = L"PeakCommitment";
  v11 = std::_WChar_traits<wchar_t>::length(L"PeakCommitment");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 56,
    0);
  v10 = L"PageFaultCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"PageFaultCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 60,
    0);
  v10 = L"CopyOnWriteCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"CopyOnWriteCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 64,
    0);
  v10 = L"TransitionCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"TransitionCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 68,
    0);
  v10 = L"CacheTransitionCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"CacheTransitionCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 72,
    0);
  v10 = L"DemandZeroCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"DemandZeroCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 76,
    0);
  v10 = L"PageReadCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"PageReadCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 80,
    0);
  v10 = L"PageReadIoCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"PageReadIoCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 84,
    0);
  v10 = L"CacheReadCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"CacheReadCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 88,
    0);
  v10 = L"CacheIoCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"CacheIoCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 92,
    0);
  v10 = L"DirtyPagesWriteCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"DirtyPagesWriteCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 96,
    0);
  v10 = L"DirtyWriteIoCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"DirtyWriteIoCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 100,
    0);
  v10 = L"MappedPagesWriteCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"MappedPagesWriteCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 104,
    0);
  v10 = L"MappedWriteIoCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"MappedWriteIoCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 108,
    0);
  v10 = L"PagedPoolPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"PagedPoolPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 112,
    0);
  v10 = L"NonPagedPoolPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 116,
    0);
  v10 = L"PagedPoolAllocs";
  v11 = std::_WChar_traits<wchar_t>::length(L"PagedPoolAllocs");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 120,
    0);
  v10 = L"PagedPoolFrees";
  v11 = std::_WChar_traits<wchar_t>::length(L"PagedPoolFrees");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 124,
    0);
  v10 = L"NonPagedPoolAllocs";
  v11 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolAllocs");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 128,
    0);
  v10 = L"NonPagedPoolFrees";
  v11 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolFrees");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 132,
    0);
  v10 = L"FreeSystemPtes";
  v11 = std::_WChar_traits<wchar_t>::length(L"FreeSystemPtes");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 136,
    0);
  v10 = L"ResidentSystemCodePage";
  v11 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemCodePage");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 140,
    0);
  v10 = L"TotalSystemDriverPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"TotalSystemDriverPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 144,
    0);
  v10 = L"TotalSystemCodePages";
  v11 = std::_WChar_traits<wchar_t>::length(L"TotalSystemCodePages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 148,
    0);
  v10 = L"NonPagedPoolLookasideHits";
  v11 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolLookasideHits");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 152,
    0);
  v10 = L"PagedPoolLookasideHits";
  v11 = std::_WChar_traits<wchar_t>::length(L"PagedPoolLookasideHits");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 156,
    0);
  v10 = L"AvailablePagedPoolPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"AvailablePagedPoolPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 160,
    0);
  v10 = L"ResidentSystemCachePage";
  v11 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemCachePage");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 164,
    0);
  v10 = L"ResidentPagedPoolPage";
  v11 = std::_WChar_traits<wchar_t>::length(L"ResidentPagedPoolPage");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 168,
    0);
  v10 = L"ResidentSystemDriverPage";
  v11 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemDriverPage");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 172,
    0);
  v10 = L"CcFastReadNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastReadNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 176,
    0);
  v10 = L"CcFastReadWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastReadWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 180,
    0);
  v10 = L"CcFastReadResourceMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastReadResourceMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 184,
    0);
  v10 = L"CcFastReadNotPossible";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastReadNotPossible");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 188,
    0);
  v10 = L"CcFastMdlReadNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 192,
    0);
  v10 = L"CcFastMdlReadWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 196,
    0);
  v10 = L"CcFastMdlReadResourceMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadResourceMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 200,
    0);
  v10 = L"CcFastMdlReadNotPossible";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadNotPossible");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 204,
    0);
  v10 = L"CcMapDataNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMapDataNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 208,
    0);
  v10 = L"CcMapDataWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMapDataWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 212,
    0);
  v10 = L"CcMapDataNoWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMapDataNoWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 216,
    0);
  v10 = L"CcMapDataWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMapDataWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 220,
    0);
  v10 = L"CcPinMappedDataCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcPinMappedDataCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 224,
    0);
  v10 = L"CcPinReadNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcPinReadNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 228,
    0);
  v10 = L"CcPinReadWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcPinReadWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 232,
    0);
  v10 = L"CcPinReadNoWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcPinReadNoWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 236,
    0);
  v10 = L"CcPinReadWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcPinReadWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 240,
    0);
  v10 = L"CcCopyReadNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 244,
    0);
  v10 = L"CcCopyReadWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 248,
    0);
  v10 = L"CcCopyReadNoWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadNoWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 252,
    0);
  v10 = L"CcCopyReadWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 256,
    0);
  v10 = L"CcMdlReadNoWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadNoWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 260,
    0);
  v10 = L"CcMdlReadWait";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadWait");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 264,
    0);
  v10 = L"CcMdlReadNoWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadNoWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 268,
    0);
  v10 = L"CcMdlReadWaitMiss";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadWaitMiss");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 272,
    0);
  v10 = L"CcReadAheadIos";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcReadAheadIos");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 276,
    0);
  v10 = L"CcLazyWriteIos";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcLazyWriteIos");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 280,
    0);
  v10 = L"CcLazyWritePages";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcLazyWritePages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 284,
    0);
  v10 = L"CcDataFlushes";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcDataFlushes");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 288,
    0);
  v10 = L"CcDataPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcDataPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 292,
    0);
  v10 = L"ContextSwitches";
  v11 = std::_WChar_traits<wchar_t>::length(L"ContextSwitches");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 296,
    0);
  v10 = L"FirstLevelTbFills";
  v11 = std::_WChar_traits<wchar_t>::length(L"FirstLevelTbFills");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 300,
    0);
  v10 = L"SecondLevelTbFills";
  v11 = std::_WChar_traits<wchar_t>::length(L"SecondLevelTbFills");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 304,
    0);
  v10 = L"SystemCalls";
  v11 = std::_WChar_traits<wchar_t>::length(L"SystemCalls");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 308,
    0);
  v10 = L"CcTotalDirtyPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcTotalDirtyPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 312,
    0);
  v10 = L"CcDirtyPageThreshold";
  v11 = std::_WChar_traits<wchar_t>::length(L"CcDirtyPageThreshold");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 320,
    0);
  v10 = L"ResidentAvailablePages";
  v11 = std::_WChar_traits<wchar_t>::length(L"ResidentAvailablePages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v8, &v10, a2 + 328);
  v10 = L"SharedCommittedPages";
  v11 = std::_WChar_traits<wchar_t>::length(L"SharedCommittedPages");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a2 + 336,
    0);
  v10 = L"CommitTotal";
  v11 = std::_WChar_traits<wchar_t>::length(L"CommitTotal");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 8,
    0);
  v10 = L"CommitLimit";
  v11 = std::_WChar_traits<wchar_t>::length(L"CommitLimit");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 16,
    0);
  v10 = L"CommitPeak";
  v11 = std::_WChar_traits<wchar_t>::length(L"CommitPeak");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 24,
    0);
  v10 = L"PhysicalTotal";
  v11 = std::_WChar_traits<wchar_t>::length(L"PhysicalTotal");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 32,
    0);
  v10 = L"PhysicalAvailable";
  v11 = std::_WChar_traits<wchar_t>::length(L"PhysicalAvailable");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 40,
    0);
  v10 = L"SystemCache";
  v11 = std::_WChar_traits<wchar_t>::length(L"SystemCache");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 48,
    0);
  v10 = L"KernelTotal";
  v11 = std::_WChar_traits<wchar_t>::length(L"KernelTotal");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 56,
    0);
  v10 = L"KernelPaged";
  v11 = std::_WChar_traits<wchar_t>::length(L"KernelPaged");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 64,
    0);
  v10 = L"KernelNonpaged";
  v11 = std::_WChar_traits<wchar_t>::length(L"KernelNonpaged");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 72,
    0);
  v10 = L"PageSize";
  v11 = std::_WChar_traits<wchar_t>::length(L"PageSize");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 80,
    0);
  v10 = L"HandleCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"HandleCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 88,
    0);
  v10 = L"ProcessCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"ProcessCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 92,
    0);
  v10 = L"ThreadCount";
  v11 = std::_WChar_traits<wchar_t>::length(L"ThreadCount");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    a3 + 96,
    0);
  v13 = a4;
  v10 = L"EdpEnforcement";
  v11 = std::_WChar_traits<wchar_t>::length(L"EdpEnforcement");
  v8 = L"info";
  v9 = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v10,
    (unsigned int)&v13,
    0);
  Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v12);
}

```

## disassembly

```asm
0x18031b5d4  push    rbp
0x18031b5d6  push    rbx
0x18031b5d7  push    rsi
0x18031b5d8  push    rdi
0x18031b5d9  push    r12
0x18031b5db  push    r13
0x18031b5dd  push    r14
0x18031b5df  push    r15
0x18031b5e1  mov     rbp, rsp
0x18031b5e4  sub     rsp, 68h
0x18031b5e8  mov     esi, r9d
0x18031b5eb  mov     rdi, r8
0x18031b5ee  mov     rbx, rdx
0x18031b5f1  mov     r14, rcx
0x18031b5f4  lea     rcx, aSystemperforma; "systemperformanceinfo"
0x18031b5fb  mov     [rbp+var_38], rcx
0x18031b5ff  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b604  mov     [rbp+var_30], rax
0x18031b608  lea     r8, [rbp+var_38]
0x18031b60c  lea     rdx, [rbp+var_18]
0x18031b610  mov     rcx, r14
0x18031b613  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x18031b618  nop
0x18031b619  lea     rcx, aIdleprocesstim; "IdleProcessTime"
0x18031b620  mov     [rbp+var_38], rcx
0x18031b624  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b629  mov     [rbp+var_30], rax
0x18031b62d  lea     r13, aInfo_0; "info"
0x18031b634  mov     [rbp+var_28], r13
0x18031b638  mov     rcx, r13
0x18031b63b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b640  mov     [rbp+var_20], rax
0x18031b644  mov     r9, rbx
0x18031b647  lea     r8, [rbp+var_38]
0x18031b64b  lea     rdx, [rbp+var_28]
0x18031b64f  mov     rcx, r14
0x18031b652  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b657  lea     rcx, aIoreadtransfer; "IoReadTransferCount"
0x18031b65e  mov     [rbp+var_28], rcx
0x18031b662  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b667  mov     [rbp+var_20], rax
0x18031b66b  mov     [rbp+var_38], r13
0x18031b66f  mov     rcx, r13
0x18031b672  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b677  mov     [rbp+var_30], rax
0x18031b67b  lea     r9, [rbx+8]
0x18031b67f  lea     r8, [rbp+var_28]
0x18031b683  lea     rdx, [rbp+var_38]
0x18031b687  mov     rcx, r14
0x18031b68a  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b68f  lea     rcx, aIowritetransfe; "IoWriteTransferCount"
0x18031b696  mov     [rbp+var_28], rcx
0x18031b69a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b69f  mov     [rbp+var_20], rax
0x18031b6a3  mov     [rbp+var_38], r13
0x18031b6a7  mov     rcx, r13
0x18031b6aa  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6af  mov     [rbp+var_30], rax
0x18031b6b3  lea     r9, [rbx+10h]
0x18031b6b7  lea     r8, [rbp+var_28]
0x18031b6bb  lea     rdx, [rbp+var_38]
0x18031b6bf  mov     rcx, r14
0x18031b6c2  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b6c7  lea     rcx, aIoothertransfe; "IoOtherTransferCount"
0x18031b6ce  mov     [rbp+var_28], rcx
0x18031b6d2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6d7  mov     [rbp+var_20], rax
0x18031b6db  mov     [rbp+var_38], r13
0x18031b6df  mov     rcx, r13
0x18031b6e2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6e7  mov     [rbp+var_30], rax
0x18031b6eb  lea     r9, [rbx+18h]
0x18031b6ef  lea     r8, [rbp+var_28]
0x18031b6f3  lea     rdx, [rbp+var_38]
0x18031b6f7  mov     rcx, r14
0x18031b6fa  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b6ff  lea     rcx, aIoreadoperatio; "IoReadOperationCount"
0x18031b706  mov     [rbp+var_28], rcx
0x18031b70a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b70f  mov     [rbp+var_20], rax
0x18031b713  mov     [rbp+var_38], r13
0x18031b717  mov     rcx, r13
0x18031b71a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b71f  mov     [rbp+var_30], rax
0x18031b723  lea     r9, [rbx+20h]
0x18031b727  xor     r12d, r12d
0x18031b72a  mov     [rsp+68h+var_48], r12b
0x18031b72f  lea     r8, [rbp+var_28]
0x18031b733  lea     rdx, [rbp+var_38]
0x18031b737  mov     rcx, r14
0x18031b73a  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b73f  lea     rcx, aIowriteoperati; "IoWriteOperationCount"
0x18031b746  mov     [rbp+var_28], rcx
0x18031b74a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b74f  mov     [rbp+var_20], rax
0x18031b753  mov     [rbp+var_38], r13
0x18031b757  mov     rcx, r13
0x18031b75a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b75f  mov     [rbp+var_30], rax
0x18031b763  lea     r9, [rbx+24h]
0x18031b767  mov     [rsp+68h+var_48], r12b
0x18031b76c  lea     r8, [rbp+var_28]
0x18031b770  lea     rdx, [rbp+var_38]
0x18031b774  mov     rcx, r14
0x18031b777  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b77c  lea     rcx, aIootheroperati; "IoOtherOperationCount"
0x18031b783  mov     [rbp+var_28], rcx
0x18031b787  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b78c  mov     [rbp+var_20], rax
0x18031b790  mov     [rbp+var_38], r13
0x18031b794  mov     rcx, r13
0x18031b797  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b79c  mov     [rbp+var_30], rax
0x18031b7a0  lea     r9, [rbx+28h]
0x18031b7a4  mov     [rsp+68h+var_48], r12b
0x18031b7a9  lea     r8, [rbp+var_28]
0x18031b7ad  lea     rdx, [rbp+var_38]
0x18031b7b1  mov     rcx, r14
0x18031b7b4  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b7b9  lea     rcx, aAvailablepages; "AvailablePages"
0x18031b7c0  mov     [rbp+var_28], rcx
0x18031b7c4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b7c9  mov     [rbp+var_20], rax
0x18031b7cd  mov     [rbp+var_38], r13
0x18031b7d1  mov     rcx, r13
0x18031b7d4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b7d9  mov     [rbp+var_30], rax
0x18031b7dd  lea     r9, [rbx+2Ch]
0x18031b7e1  mov     [rsp+68h+var_48], r12b
0x18031b7e6  lea     r8, [rbp+var_28]
0x18031b7ea  lea     rdx, [rbp+var_38]
0x18031b7ee  mov     rcx, r14
0x18031b7f1  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b7f6  lea     rcx, aCommittedpages; "CommittedPages"
0x18031b7fd  mov     [rbp+var_28], rcx
0x18031b801  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b806  mov     [rbp+var_20], rax
0x18031b80a  mov     [rbp+var_38], r13
0x18031b80e  mov     rcx, r13
0x18031b811  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b816  mov     [rbp+var_30], rax
0x18031b81a  lea     r9, [rbx+30h]
0x18031b81e  mov     [rsp+68h+var_48], r12b
0x18031b823  lea     r8, [rbp+var_28]
0x18031b827  lea     rdx, [rbp+var_38]
0x18031b82b  mov     rcx, r14
0x18031b82e  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b833  lea     r15, aCommitlimit; "CommitLimit"
0x18031b83a  mov     [rbp+var_28], r15
0x18031b83e  mov     rcx, r15
0x18031b841  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b846  mov     [rbp+var_20], rax
0x18031b84a  mov     [rbp+var_38], r13
0x18031b84e  mov     rcx, r13
0x18031b851  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b856  mov     [rbp+var_30], rax
0x18031b85a  lea     r9, [rbx+34h]
0x18031b85e  mov     [rsp+68h+var_48], r12b
0x18031b863  lea     r8, [rbp+var_28]
0x18031b867  lea     rdx, [rbp+var_38]
0x18031b86b  mov     rcx, r14
0x18031b86e  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b873  lea     rcx, aPeakcommitment; "PeakCommitment"
0x18031b87a  mov     [rbp+var_28], rcx
0x18031b87e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b883  mov     [rbp+var_20], rax
0x18031b887  mov     [rbp+var_38], r13
0x18031b88b  mov     rcx, r13
0x18031b88e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b893  mov     [rbp+var_30], rax
0x18031b897  lea     r9, [rbx+38h]
0x18031b89b  mov     [rsp+68h+var_48], r12b
0x18031b8a0  lea     r8, [rbp+var_28]
0x18031b8a4  lea     rdx, [rbp+var_38]
0x18031b8a8  mov     rcx, r14
0x18031b8ab  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b8b0  lea     rcx, aPagefaultcount; "PageFaultCount"
0x18031b8b7  mov     [rbp+var_28], rcx
0x18031b8bb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8c0  mov     [rbp+var_20], rax
0x18031b8c4  mov     [rbp+var_38], r13
0x18031b8c8  mov     rcx, r13
0x18031b8cb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8d0  mov     [rbp+var_30], rax
0x18031b8d4  lea     r9, [rbx+3Ch]
0x18031b8d8  mov     [rsp+68h+var_48], r12b
0x18031b8dd  lea     r8, [rbp+var_28]
0x18031b8e1  lea     rdx, [rbp+var_38]
0x18031b8e5  mov     rcx, r14
0x18031b8e8  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b8ed  lea     rcx, aCopyonwritecou; "CopyOnWriteCount"
0x18031b8f4  mov     [rbp+var_28], rcx
0x18031b8f8  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8fd  mov     [rbp+var_20], rax
0x18031b901  mov     [rbp+var_38], r13
0x18031b905  mov     rcx, r13
0x18031b908  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b90d  mov     [rbp+var_30], rax
0x18031b911  lea     r9, [rbx+40h]
0x18031b915  mov     [rsp+68h+var_48], r12b
0x18031b91a  lea     r8, [rbp+var_28]
0x18031b91e  lea     rdx, [rbp+var_38]
0x18031b922  mov     rcx, r14
0x18031b925  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b92a  lea     rcx, aTransitioncoun; "TransitionCount"
0x18031b931  mov     [rbp+var_28], rcx
0x18031b935  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b93a  mov     [rbp+var_20], rax
0x18031b93e  mov     [rbp+var_38], r13
0x18031b942  mov     rcx, r13
0x18031b945  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b94a  mov     [rbp+var_30], rax
0x18031b94e  lea     r9, [rbx+44h]
0x18031b952  mov     [rsp+68h+var_48], r12b
0x18031b957  lea     r8, [rbp+var_28]
0x18031b95b  lea     rdx, [rbp+var_38]
0x18031b95f  mov     rcx, r14
0x18031b962  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b967  lea     rcx, aCachetransitio; "CacheTransitionCount"
0x18031b96e  mov     [rbp+var_28], rcx
0x18031b972  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b977  mov     [rbp+var_20], rax
0x18031b97b  mov     [rbp+var_38], r13
0x18031b97f  mov     rcx, r13
0x18031b982  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b987  mov     [rbp+var_30], rax
0x18031b98b  lea     r9, [rbx+48h]
0x18031b98f  mov     [rsp+68h+var_48], r12b
0x18031b994  lea     r8, [rbp+var_28]
0x18031b998  lea     rdx, [rbp+var_38]
0x18031b99c  mov     rcx, r14
0x18031b99f  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b9a4  lea     rcx, aDemandzerocoun; "DemandZeroCount"
0x18031b9ab  mov     [rbp+var_28], rcx
0x18031b9af  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9b4  mov     [rbp+var_20], rax
0x18031b9b8  mov     [rbp+var_38], r13
0x18031b9bc  mov     rcx, r13
0x18031b9bf  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9c4  mov     [rbp+var_30], rax
0x18031b9c8  lea     r9, [rbx+4Ch]
0x18031b9cc  mov     [rsp+68h+var_48], r12b
0x18031b9d1  lea     r8, [rbp+var_28]
0x18031b9d5  lea     rdx, [rbp+var_38]
0x18031b9d9  mov     rcx, r14
0x18031b9dc  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b9e1  lea     rcx, aPagereadcount; "PageReadCount"
0x18031b9e8  mov     [rbp+var_28], rcx
0x18031b9ec  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9f1  mov     [rbp+var_20], rax
0x18031b9f5  mov     [rbp+var_38], r13
0x18031b9f9  mov     rcx, r13
0x18031b9fc  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba01  mov     [rbp+var_30], rax
0x18031ba05  lea     r9, [rbx+50h]
0x18031ba09  mov     [rsp+68h+var_48], r12b
0x18031ba0e  lea     r8, [rbp+var_28]
0x18031ba12  lea     rdx, [rbp+var_38]
0x18031ba16  mov     rcx, r14
0x18031ba19  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba1e  lea     rcx, aPagereadiocoun; "PageReadIoCount"
0x18031ba25  mov     [rbp+var_28], rcx
0x18031ba29  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba2e  mov     [rbp+var_20], rax
0x18031ba32  mov     [rbp+var_38], r13
0x18031ba36  mov     rcx, r13
0x18031ba39  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba3e  mov     [rbp+var_30], rax
0x18031ba42  lea     r9, [rbx+54h]
0x18031ba46  mov     [rsp+68h+var_48], r12b
0x18031ba4b  lea     r8, [rbp+var_28]
0x18031ba4f  lea     rdx, [rbp+var_38]
0x18031ba53  mov     rcx, r14
0x18031ba56  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba5b  lea     rcx, aCachereadcount; "CacheReadCount"
0x18031ba62  mov     [rbp+var_28], rcx
0x18031ba66  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba6b  mov     [rbp+var_20], rax
0x18031ba6f  mov     [rbp+var_38], r13
0x18031ba73  mov     rcx, r13
0x18031ba76  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba7b  mov     [rbp+var_30], rax
0x18031ba7f  lea     r9, [rbx+58h]
0x18031ba83  mov     [rsp+68h+var_48], r12b
0x18031ba88  lea     r8, [rbp+var_28]
0x18031ba8c  lea     rdx, [rbp+var_38]
0x18031ba90  mov     rcx, r14
0x18031ba93  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba98  lea     rcx, aCacheiocount; "CacheIoCount"
0x18031ba9f  mov     [rbp+var_28], rcx
0x18031baa3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031baa8  mov     [rbp+var_20], rax
0x18031baac  mov     [rbp+var_38], r13
0x18031bab0  mov     rcx, r13
0x18031bab3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031bab8  mov     [rbp+var_30], rax
0x18031babc  lea     r9, [rbx+5Ch]
0x18031bac0  mov     [rsp+68h+var_48], r12b
0x18031bac5  lea     r8, [rbp+var_28]
0x18031bac9  lea     rdx, [rbp+var_38]
  ... truncated ...
```
