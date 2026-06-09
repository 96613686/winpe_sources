# DumpSystemMemoryInfoStream(void *)

- ea: `0x1802044b0`
- end: `0x180204f0e`
- name: `?DumpSystemMemoryInfoStream@@YAXPEAX@Z`
- size: `2654`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180202c20`

## callees

- `0x1800727b8`
- `0x1802044b0`
- `0x18020f3bc`

## string_xrefs

- `0x1802045ed`: `  FileCacheInfo\n`
- `0x1802046db`: `CommittedPages`
- `0x1802047f2`: `CommittedPages`
- `0x1802046f3`: `CommitLimit`
- `0x18020470e`: `PeakCommitment`
- `0x18020481e`: `PeakCommitment`
- `0x18020474a`: `IoReadTransferCount`
- `0x180204762`: `IoWriteTransferCount`
- `0x180204792`: `IoReadOperationCount`
- `0x1802047aa`: `IoWriteOperationCount`
- `0x180204862`: `CopyOnWriteCount`
- `0x180204892`: `CacheTransitionCount`
- `0x1802048c2`: `PageReadCount`
- `0x1802048da`: `PageReadIoCount`
- `0x1802048f2`: `CacheReadCount`
- `0x18020490a`: `CacheIoCount`
- `0x180204922`: `DirtyPagesWriteCount`
- `0x18020493a`: `DirtyWriteIoCount`
- `0x180204952`: `MappedPagesWriteCount`
- `0x18020496a`: `MappedWriteIoCount`
- `0x180204a12`: `FreeSystemPtes`
- `0x180204a2a`: `ResidentSystemCodePage`
- `0x180204a72`: `NonPagedPoolLookasideHits`
- `0x180204a8a`: `PagedPoolLookasideHits`
- `0x180204aba`: `ResidentSystemCachePage`
- `0x180204ad2`: `ResidentPagedPoolPage`
- `0x180204aea`: `ResidentSystemDriverPage`
- `0x180204b02`: `CcFastReadNoWait`
- `0x180204b1a`: `CcFastReadWait`
- `0x180204b32`: `CcFastReadResourceMiss`
- `0x180204b4a`: `CcFastReadNotPossible`
- `0x180204b62`: `CcFastMdlReadNoWait`
- `0x180204b7a`: `CcFastMdlReadWait`
- `0x180204b92`: `CcFastMdlReadResourceMiss`
- `0x180204baa`: `CcFastMdlReadNotPossible`
- `0x180204c3a`: `CcPinReadNoWait`
- `0x180204c52`: `CcPinReadWait`
- `0x180204c6a`: `CcPinReadNoWaitMiss`
- `0x180204c82`: `CcPinReadWaitMiss`
- `0x180204c9a`: `CcCopyReadNoWait`
- `0x180204cb2`: `CcCopyReadWait`
- `0x180204cca`: `CcCopyReadNoWaitMiss`
- `0x180204ce2`: `CcCopyReadWaitMiss`
- `0x180204cfa`: `CcMdlReadNoWait`
- `0x180204d12`: `CcMdlReadWait`
- `0x180204d2a`: `CcMdlReadNoWaitMiss`
- `0x180204d42`: `CcMdlReadWaitMiss`
- `0x180204d5a`: `CcReadAheadIos`
- `0x180204d72`: `CcLazyWriteIos`
- `0x180204d8a`: `CcLazyWritePages`
- `0x180204e62`: `ResidentAvailablePages`
- `0x180204e7a`: `SharedCommittedPages`
- `0x180204eb6`: `PfnDatabaseCommittedPages`
- `0x180204ed4`: `SystemPageTableCommittedPages`

## pseudocode

```c
void __fastcall DumpSystemMemoryInfoStream(_QWORD *a1)
{
  if ( a1 )
  {
    dprintf(L"  %*s: %32u\n", 4294967254LL, L"Revision", *(unsigned __int16 *)a1);
    dprintf(L"  %*s: %#32x\n", 4294967254LL, L"Flags", *((unsigned __int16 *)a1 + 1));
    dprintf(L"  BasicInfo\n");
    PrintValue(qword_180613A10, 0, L"TimerResolution", *((unsigned int *)a1 + 1));
    PrintValue(qword_180613A10, 1, L"PageSize", *((unsigned int *)a1 + 2));
    PrintValue(qword_180613A10, 0, L"NumberOfPhysicalPages", *((unsigned int *)a1 + 3));
    PrintValue(qword_180613A10, 1, L"LowestPhysicalPageNumber", *((unsigned int *)a1 + 4));
    PrintValue(qword_180613A10, 1, L"HighestPhysicalPageNumber", *((unsigned int *)a1 + 5));
    PrintValue(qword_180613A10, 1, L"AllocationGranularity", *((unsigned int *)a1 + 6));
    PrintValue(qword_180613A10, 1, L"MinimumUserModeAddress", *(_QWORD *)((char *)a1 + 28));
    PrintValue(qword_180613A10, 1, L"MaximumUserModeAddress", *(_QWORD *)((char *)a1 + 36));
    PrintValue(qword_180613A10, 1, L"ActiveProcessorsAffinityMask", *(_QWORD *)((char *)a1 + 44));
    PrintValue(qword_180613A10, 0, L"NumberOfProcessors", *((unsigned int *)a1 + 13));
    dprintf(L"  FileCacheInfo\n");
    PrintValue(qword_180613A10, 0, L"CurrentSize", a1[7]);
    PrintValue(qword_180613A10, 0, L"PeakSize", a1[8]);
    PrintValue(qword_180613A10, 0, L"PageFaultCount", *((unsigned int *)a1 + 18));
    PrintValue(qword_180613A10, 1, L"MinimumWorkingSet", *(_QWORD *)((char *)a1 + 76));
    PrintValue(qword_180613A10, 1, L"MaximumWorkingSet", *(_QWORD *)((char *)a1 + 84));
    PrintValue(qword_180613A10, 0, L"CurrentSizeIncludingTransitionInPages", *(_QWORD *)((char *)a1 + 92));
    PrintValue(qword_180613A10, 0, L"PeakSizeIncludingTransitionInPages", *(_QWORD *)((char *)a1 + 100));
    PrintValue(qword_180613A10, 0, L"TransitionRePurposeCount", *((unsigned int *)a1 + 27));
    PrintValue(qword_180613A10, 1, L"Flags", *((unsigned int *)a1 + 28));
    dprintf(L"  BasicPerfInfo\n");
    PrintValue(qword_180613A10, 0, L"AvailablePages", *(_QWORD *)((char *)a1 + 116));
    PrintValue(qword_180613A10, 0, L"CommittedPages", *(_QWORD *)((char *)a1 + 124));
    PrintValue(qword_180613A10, 0, L"CommitLimit", *(_QWORD *)((char *)a1 + 132));
    PrintValue(qword_180613A10, 0, L"PeakCommitment", *(_QWORD *)((char *)a1 + 140));
    dprintf(L"  PerfInfo\n");
    PrintValue(qword_180613A10, 0, L"IdleProcessTime", *(_QWORD *)((char *)a1 + 148));
    PrintValue(qword_180613A10, 0, L"IoReadTransferCount", *(_QWORD *)((char *)a1 + 156));
    PrintValue(qword_180613A10, 0, L"IoWriteTransferCount", *(_QWORD *)((char *)a1 + 164));
    PrintValue(qword_180613A10, 0, L"IoOtherTransferCount", *(_QWORD *)((char *)a1 + 172));
    PrintValue(qword_180613A10, 0, L"IoReadOperationCount", *((unsigned int *)a1 + 45));
    PrintValue(qword_180613A10, 0, L"IoWriteOperationCount", *((unsigned int *)a1 + 46));
    PrintValue(qword_180613A10, 0, L"IoOtherOperationCount", *((unsigned int *)a1 + 47));
    PrintValue(qword_180613A10, 0, L"AvailablePages", *((unsigned int *)a1 + 48));
    PrintValue(qword_180613A10, 0, L"CommittedPages", *((unsigned int *)a1 + 49));
    PrintValue(qword_180613A10, 0, L"CommitLimit", *((unsigned int *)a1 + 50));
    PrintValue(qword_180613A10, 0, L"PeakCommitment", *((unsigned int *)a1 + 51));
    PrintValue(qword_180613A10, 0, L"CommitLimit", *((unsigned int *)a1 + 50));
    PrintValue(qword_180613A10, 0, L"PageFaultCount", *((unsigned int *)a1 + 52));
    PrintValue(qword_180613A10, 0, L"CopyOnWriteCount", *((unsigned int *)a1 + 53));
    PrintValue(qword_180613A10, 0, L"TransitionCount", *((unsigned int *)a1 + 54));
    PrintValue(qword_180613A10, 0, L"CacheTransitionCount", *((unsigned int *)a1 + 55));
    PrintValue(qword_180613A10, 0, L"DemandZeroCount", *((unsigned int *)a1 + 56));
    PrintValue(qword_180613A10, 0, L"PageReadCount", *((unsigned int *)a1 + 57));
    PrintValue(qword_180613A10, 0, L"PageReadIoCount", *((unsigned int *)a1 + 58));
    PrintValue(qword_180613A10, 0, L"CacheReadCount", *((unsigned int *)a1 + 59));
    PrintValue(qword_180613A10, 0, L"CacheIoCount", *((unsigned int *)a1 + 60));
    PrintValue(qword_180613A10, 0, L"DirtyPagesWriteCount", *((unsigned int *)a1 + 61));
    PrintValue(qword_180613A10, 0, L"DirtyWriteIoCount", *((unsigned int *)a1 + 62));
    PrintValue(qword_180613A10, 0, L"MappedPagesWriteCount", *((unsigned int *)a1 + 63));
    PrintValue(qword_180613A10, 0, L"MappedWriteIoCount", *((unsigned int *)a1 + 64));
    PrintValue(qword_180613A10, 0, L"PagedPoolPages", *((unsigned int *)a1 + 65));
    PrintValue(qword_180613A10, 0, L"NonPagedPoolPages", *((unsigned int *)a1 + 66));
    PrintValue(qword_180613A10, 0, L"PagedPoolAllocs", *((unsigned int *)a1 + 67));
    PrintValue(qword_180613A10, 0, L"PagedPoolFrees", *((unsigned int *)a1 + 68));
    PrintValue(qword_180613A10, 0, L"NonPagedPoolAllocs", *((unsigned int *)a1 + 69));
    PrintValue(qword_180613A10, 0, L"NonPagedPoolFrees", *((unsigned int *)a1 + 70));
    PrintValue(qword_180613A10, 0, L"FreeSystemPtes", *((unsigned int *)a1 + 71));
    PrintValue(qword_180613A10, 0, L"ResidentSystemCodePage", *((unsigned int *)a1 + 72));
    PrintValue(qword_180613A10, 0, L"TotalSystemDriverPages", *((unsigned int *)a1 + 73));
    PrintValue(qword_180613A10, 0, L"TotalSystemCodePages", *((unsigned int *)a1 + 74));
    PrintValue(qword_180613A10, 0, L"NonPagedPoolLookasideHits", *((unsigned int *)a1 + 75));
    PrintValue(qword_180613A10, 0, L"PagedPoolLookasideHits", *((unsigned int *)a1 + 76));
    PrintValue(qword_180613A10, 0, L"AvailablePagedPoolPages", *((unsigned int *)a1 + 77));
    PrintValue(qword_180613A10, 0, L"ResidentSystemCachePage", *((unsigned int *)a1 + 78));
    PrintValue(qword_180613A10, 0, L"ResidentPagedPoolPage", *((unsigned int *)a1 + 79));
    PrintValue(qword_180613A10, 0, L"ResidentSystemDriverPage", *((unsigned int *)a1 + 80));
    PrintValue(qword_180613A10, 0, L"CcFastReadNoWait", *((unsigned int *)a1 + 81));
    PrintValue(qword_180613A10, 0, L"CcFastReadWait", *((unsigned int *)a1 + 82));
    PrintValue(qword_180613A10, 0, L"CcFastReadResourceMiss", *((unsigned int *)a1 + 83));
    PrintValue(qword_180613A10, 0, L"CcFastReadNotPossible", *((unsigned int *)a1 + 84));
    PrintValue(qword_180613A10, 0, L"CcFastMdlReadNoWait", *((unsigned int *)a1 + 85));
    PrintValue(qword_180613A10, 0, L"CcFastMdlReadWait", *((unsigned int *)a1 + 86));
    PrintValue(qword_180613A10, 0, L"CcFastMdlReadResourceMiss", *((unsigned int *)a1 + 87));
    PrintValue(qword_180613A10, 0, L"CcFastMdlReadNotPossible", *((unsigned int *)a1 + 88));
    PrintValue(qword_180613A10, 0, L"CcMapDataNoWait", *((unsigned int *)a1 + 89));
    PrintValue(qword_180613A10, 0, L"CcMapDataWait", *((unsigned int *)a1 + 90));
    PrintValue(qword_180613A10, 0, L"CcMapDataNoWaitMiss", *((unsigned int *)a1 + 91));
    PrintValue(qword_180613A10, 0, L"CcMapDataWaitMiss", *((unsigned int *)a1 + 92));
    PrintValue(qword_180613A10, 0, L"CcPinMappedDataCount", *((unsigned int *)a1 + 93));
    PrintValue(qword_180613A10, 0, L"CcPinReadNoWait", *((unsigned int *)a1 + 94));
    PrintValue(qword_180613A10, 0, L"CcPinReadWait", *((unsigned int *)a1 + 95));
    PrintValue(qword_180613A10, 0, L"CcPinReadNoWaitMiss", *((unsigned int *)a1 + 96));
    PrintValue(qword_180613A10, 0, L"CcPinReadWaitMiss", *((unsigned int *)a1 + 97));
    PrintValue(qword_180613A10, 0, L"CcCopyReadNoWait", *((unsigned int *)a1 + 98));
    PrintValue(qword_180613A10, 0, L"CcCopyReadWait", *((unsigned int *)a1 + 99));
    PrintValue(qword_180613A10, 0, L"CcCopyReadNoWaitMiss", *((unsigned int *)a1 + 100));
    PrintValue(qword_180613A10, 0, L"CcCopyReadWaitMiss", *((unsigned int *)a1 + 101));
    PrintValue(qword_180613A10, 0, L"CcMdlReadNoWait", *((unsigned int *)a1 + 102));
    PrintValue(qword_180613A10, 0, L"CcMdlReadWait", *((unsigned int *)a1 + 103));
    PrintValue(qword_180613A10, 0, L"CcMdlReadNoWaitMiss", *((unsigned int *)a1 + 104));
    PrintValue(qword_180613A10, 0, L"CcMdlReadWaitMiss", *((unsigned int *)a1 + 105));
    PrintValue(qword_180613A10, 0, L"CcReadAheadIos", *((unsigned int *)a1 + 106));
    PrintValue(qword_180613A10, 0, L"CcLazyWriteIos", *((unsigned int *)a1 + 107));
    PrintValue(qword_180613A10, 0, L"CcLazyWritePages", *((unsigned int *)a1 + 108));
    PrintValue(qword_180613A10, 0, L"CcDataFlushes", *((unsigned int *)a1 + 109));
    PrintValue(qword_180613A10, 0, L"CcDataPages", *((unsigned int *)a1 + 110));
    PrintValue(qword_180613A10, 0, L"ContextSwitches", *((unsigned int *)a1 + 111));
    PrintValue(qword_180613A10, 0, L"FirstLevelTbFills", *((unsigned int *)a1 + 112));
    PrintValue(qword_180613A10, 0, L"SecondLevelTbFills", *((unsigned int *)a1 + 113));
    PrintValue(qword_180613A10, 0, L"SystemCalls", *((unsigned int *)a1 + 114));
    PrintValue(qword_180613A10, 0, L"CcTotalDirtyPages", *(_QWORD *)((char *)a1 + 460));
    PrintValue(qword_180613A10, 0, L"CcDirtyPageThreshold", *(_QWORD *)((char *)a1 + 468));
    PrintValue(qword_180613A10, 0, L"ResidentAvailablePages", *(_QWORD *)((char *)a1 + 476));
    PrintValue(qword_180613A10, 0, L"SharedCommittedPages", *(_QWORD *)((char *)a1 + 484));
    if ( *(_WORD *)a1 >= 2u )
    {
      if ( (*((_BYTE *)a1 + 2) & 0x10) != 0 )
      {
        PrintValue(qword_180613A10, 0, L"MdlPagesAllocated", *(_QWORD *)((char *)a1 + 492));
        PrintValue(qword_180613A10, 0, L"PfnDatabaseCommittedPages", *(_QWORD *)((char *)a1 + 500));
      }
      if ( (*((_BYTE *)a1 + 2) & 0x20) != 0 )
      {
        PrintValue(qword_180613A10, 0, L"SystemPageTableCommittedPages", *(_QWORD *)((char *)a1 + 508));
        PrintValue(qword_180613A10, 0, L"ContiguousPagesAllocated", *(_QWORD *)((char *)a1 + 516));
      }
    }
  }
}

```

## disassembly

```asm
0x1802044b0  test    rcx, rcx
0x1802044b3  jz      locret_180204F0C
0x1802044b9  mov     [rsp+arg_0], rbx
0x1802044be  mov     [rsp+arg_8], rsi
0x1802044c3  push    rdi
0x1802044c4  sub     rsp, 20h
0x1802044c8  movzx   r9d, word ptr [rcx]
0x1802044cc  lea     r8, aRevision; "Revision"
0x1802044d3  mov     rbx, rcx
0x1802044d6  mov     edi, 0FFFFFFD6h
0x1802044db  mov     edx, edi
0x1802044dd  lea     rcx, aS32u; "  %*s: %32u\n"
0x1802044e4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802044e9  movzx   r9d, word ptr [rbx+2]
0x1802044ee  lea     r8, aFlags; "Flags"
0x1802044f5  mov     edx, edi
0x1802044f7  lea     rcx, aS32x; "  %*s: %#32x\n"
0x1802044fe  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180204503  lea     rcx, aBasicinfo; "  BasicInfo\n"
0x18020450a  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18020450f  mov     r9d, [rbx+4]
0x180204513  lea     rsi, qword_180613A10
0x18020451a  mov     rcx, rsi
0x18020451d  lea     r8, aTimerresolutio; "TimerResolution"
0x180204524  xor     edx, edx
0x180204526  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020452b  mov     r9d, [rbx+8]
0x18020452f  lea     r8, aPagesize_0; "PageSize"
0x180204536  mov     edi, 1
0x18020453b  mov     rcx, rsi
0x18020453e  mov     edx, edi
0x180204540  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204545  mov     r9d, [rbx+0Ch]
0x180204549  lea     r8, aNumberofphysic; "NumberOfPhysicalPages"
0x180204550  xor     edx, edx
0x180204552  mov     rcx, rsi
0x180204555  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020455a  mov     r9d, [rbx+10h]
0x18020455e  lea     r8, aLowestphysical; "LowestPhysicalPageNumber"
0x180204565  mov     edx, edi
0x180204567  mov     rcx, rsi
0x18020456a  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020456f  mov     r9d, [rbx+14h]
0x180204573  lea     r8, aHighestphysica_0; "HighestPhysicalPageNumber"
0x18020457a  mov     edx, edi
0x18020457c  mov     rcx, rsi
0x18020457f  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204584  mov     r9d, [rbx+18h]
0x180204588  lea     r8, aAllocationgran; "AllocationGranularity"
0x18020458f  mov     edx, edi
0x180204591  mov     rcx, rsi
0x180204594  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204599  mov     r9, [rbx+1Ch]
0x18020459d  lea     r8, aMinimumusermod; "MinimumUserModeAddress"
0x1802045a4  mov     edx, edi
0x1802045a6  mov     rcx, rsi
0x1802045a9  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802045ae  mov     r9, [rbx+24h]
0x1802045b2  lea     r8, aMaximumusermod; "MaximumUserModeAddress"
0x1802045b9  mov     edx, edi
0x1802045bb  mov     rcx, rsi
0x1802045be  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802045c3  mov     r9, [rbx+2Ch]
0x1802045c7  lea     r8, aActiveprocesso; "ActiveProcessorsAffinityMask"
0x1802045ce  mov     edx, edi
0x1802045d0  mov     rcx, rsi
0x1802045d3  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802045d8  mov     r9d, [rbx+34h]
0x1802045dc  lea     r8, aNumberofproces_0; "NumberOfProcessors"
0x1802045e3  xor     edx, edx
0x1802045e5  mov     rcx, rsi
0x1802045e8  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802045ed  lea     rcx, aFilecacheinfo; "  FileCacheInfo\n"
0x1802045f4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802045f9  mov     r9, [rbx+38h]
0x1802045fd  lea     r8, aCurrentsize; "CurrentSize"
0x180204604  xor     edx, edx
0x180204606  mov     rcx, rsi
0x180204609  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020460e  mov     r9, [rbx+40h]
0x180204612  lea     r8, aPeaksize; "PeakSize"
0x180204619  xor     edx, edx
0x18020461b  mov     rcx, rsi
0x18020461e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204623  mov     r9d, [rbx+48h]
0x180204627  lea     r8, aPagefaultcount; "PageFaultCount"
0x18020462e  xor     edx, edx
0x180204630  mov     rcx, rsi
0x180204633  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204638  mov     r9, [rbx+4Ch]
0x18020463c  lea     r8, aMinimumworking; "MinimumWorkingSet"
0x180204643  mov     edx, edi
0x180204645  mov     rcx, rsi
0x180204648  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020464d  mov     r9, [rbx+54h]
0x180204651  lea     r8, aMaximumworking; "MaximumWorkingSet"
0x180204658  mov     edx, edi
0x18020465a  mov     rcx, rsi
0x18020465d  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204662  mov     r9, [rbx+5Ch]
0x180204666  lea     r8, aCurrentsizeinc; "CurrentSizeIncludingTransitionInPages"
0x18020466d  xor     edx, edx
0x18020466f  mov     rcx, rsi
0x180204672  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204677  mov     r9, [rbx+64h]
0x18020467b  lea     r8, aPeaksizeinclud; "PeakSizeIncludingTransitionInPages"
0x180204682  xor     edx, edx
0x180204684  mov     rcx, rsi
0x180204687  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020468c  mov     r9d, [rbx+6Ch]
0x180204690  lea     r8, aTransitionrepu; "TransitionRePurposeCount"
0x180204697  xor     edx, edx
0x180204699  mov     rcx, rsi
0x18020469c  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802046a1  mov     r9d, [rbx+70h]
0x1802046a5  lea     r8, aFlags; "Flags"
0x1802046ac  mov     edx, edi
0x1802046ae  mov     rcx, rsi
0x1802046b1  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802046b6  lea     rcx, aBasicperfinfo; "  BasicPerfInfo\n"
0x1802046bd  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802046c2  mov     r9, [rbx+74h]
0x1802046c6  lea     r8, aAvailablepages; "AvailablePages"
0x1802046cd  xor     edx, edx
0x1802046cf  mov     rcx, rsi
0x1802046d2  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802046d7  mov     r9, [rbx+7Ch]
0x1802046db  lea     r8, aCommittedpages; "CommittedPages"
0x1802046e2  xor     edx, edx
0x1802046e4  mov     rcx, rsi
0x1802046e7  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802046ec  mov     r9, [rbx+84h]
0x1802046f3  lea     rdi, aCommitlimit; "CommitLimit"
0x1802046fa  mov     r8, rdi
0x1802046fd  xor     edx, edx
0x1802046ff  mov     rcx, rsi
0x180204702  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204707  mov     r9, [rbx+8Ch]
0x18020470e  lea     r8, aPeakcommitment; "PeakCommitment"
0x180204715  xor     edx, edx
0x180204717  mov     rcx, rsi
0x18020471a  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020471f  lea     rcx, aPerfinfo; "  PerfInfo\n"
0x180204726  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18020472b  mov     r9, [rbx+94h]
0x180204732  lea     r8, aIdleprocesstim; "IdleProcessTime"
0x180204739  xor     edx, edx
0x18020473b  mov     rcx, rsi
0x18020473e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204743  mov     r9, [rbx+9Ch]
0x18020474a  lea     r8, aIoreadtransfer; "IoReadTransferCount"
0x180204751  xor     edx, edx
0x180204753  mov     rcx, rsi
0x180204756  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020475b  mov     r9, [rbx+0A4h]
0x180204762  lea     r8, aIowritetransfe; "IoWriteTransferCount"
0x180204769  xor     edx, edx
0x18020476b  mov     rcx, rsi
0x18020476e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204773  mov     r9, [rbx+0ACh]
0x18020477a  lea     r8, aIoothertransfe; "IoOtherTransferCount"
0x180204781  xor     edx, edx
0x180204783  mov     rcx, rsi
0x180204786  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020478b  mov     r9d, [rbx+0B4h]
0x180204792  lea     r8, aIoreadoperatio; "IoReadOperationCount"
0x180204799  xor     edx, edx
0x18020479b  mov     rcx, rsi
0x18020479e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802047a3  mov     r9d, [rbx+0B8h]
0x1802047aa  lea     r8, aIowriteoperati; "IoWriteOperationCount"
0x1802047b1  xor     edx, edx
0x1802047b3  mov     rcx, rsi
0x1802047b6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802047bb  mov     r9d, [rbx+0BCh]
0x1802047c2  lea     r8, aIootheroperati; "IoOtherOperationCount"
0x1802047c9  xor     edx, edx
0x1802047cb  mov     rcx, rsi
0x1802047ce  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802047d3  mov     r9d, [rbx+0C0h]
0x1802047da  lea     r8, aAvailablepages; "AvailablePages"
0x1802047e1  xor     edx, edx
0x1802047e3  mov     rcx, rsi
0x1802047e6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802047eb  mov     r9d, [rbx+0C4h]
0x1802047f2  lea     r8, aCommittedpages; "CommittedPages"
0x1802047f9  xor     edx, edx
0x1802047fb  mov     rcx, rsi
0x1802047fe  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204803  mov     r9d, [rbx+0C8h]
0x18020480a  mov     r8, rdi
0x18020480d  xor     edx, edx
0x18020480f  mov     rcx, rsi
0x180204812  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204817  mov     r9d, [rbx+0CCh]
0x18020481e  lea     r8, aPeakcommitment; "PeakCommitment"
0x180204825  xor     edx, edx
0x180204827  mov     rcx, rsi
0x18020482a  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020482f  mov     r9d, [rbx+0C8h]
0x180204836  mov     r8, rdi
0x180204839  xor     edx, edx
0x18020483b  mov     rcx, rsi
0x18020483e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204843  mov     r9d, [rbx+0D0h]
0x18020484a  lea     r8, aPagefaultcount; "PageFaultCount"
0x180204851  xor     edx, edx
0x180204853  mov     rcx, rsi
0x180204856  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020485b  mov     r9d, [rbx+0D4h]
0x180204862  lea     r8, aCopyonwritecou; "CopyOnWriteCount"
0x180204869  xor     edx, edx
0x18020486b  mov     rcx, rsi
0x18020486e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204873  mov     r9d, [rbx+0D8h]
0x18020487a  lea     r8, aTransitioncoun; "TransitionCount"
0x180204881  xor     edx, edx
0x180204883  mov     rcx, rsi
0x180204886  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020488b  mov     r9d, [rbx+0DCh]
0x180204892  lea     r8, aCachetransitio; "CacheTransitionCount"
0x180204899  xor     edx, edx
0x18020489b  mov     rcx, rsi
0x18020489e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802048a3  mov     r9d, [rbx+0E0h]
0x1802048aa  lea     r8, aDemandzerocoun; "DemandZeroCount"
0x1802048b1  xor     edx, edx
0x1802048b3  mov     rcx, rsi
0x1802048b6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802048bb  mov     r9d, [rbx+0E4h]
0x1802048c2  lea     r8, aPagereadcount; "PageReadCount"
0x1802048c9  xor     edx, edx
0x1802048cb  mov     rcx, rsi
0x1802048ce  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802048d3  mov     r9d, [rbx+0E8h]
0x1802048da  lea     r8, aPagereadiocoun; "PageReadIoCount"
0x1802048e1  xor     edx, edx
0x1802048e3  mov     rcx, rsi
0x1802048e6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802048eb  mov     r9d, [rbx+0ECh]
0x1802048f2  lea     r8, aCachereadcount; "CacheReadCount"
0x1802048f9  xor     edx, edx
0x1802048fb  mov     rcx, rsi
0x1802048fe  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204903  mov     r9d, [rbx+0F0h]
0x18020490a  lea     r8, aCacheiocount; "CacheIoCount"
0x180204911  xor     edx, edx
0x180204913  mov     rcx, rsi
0x180204916  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020491b  mov     r9d, [rbx+0F4h]
0x180204922  lea     r8, aDirtypageswrit; "DirtyPagesWriteCount"
0x180204929  xor     edx, edx
0x18020492b  mov     rcx, rsi
0x18020492e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204933  mov     r9d, [rbx+0F8h]
0x18020493a  lea     r8, aDirtywriteioco; "DirtyWriteIoCount"
0x180204941  xor     edx, edx
0x180204943  mov     rcx, rsi
0x180204946  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020494b  mov     r9d, [rbx+0FCh]
0x180204952  lea     r8, aMappedpageswri; "MappedPagesWriteCount"
0x180204959  xor     edx, edx
0x18020495b  mov     rcx, rsi
0x18020495e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204963  mov     r9d, [rbx+100h]
0x18020496a  lea     r8, aMappedwriteioc; "MappedWriteIoCount"
0x180204971  xor     edx, edx
0x180204973  mov     rcx, rsi
0x180204976  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x18020497b  mov     r9d, [rbx+104h]
0x180204982  lea     r8, aPagedpoolpages; "PagedPoolPages"
0x180204989  xor     edx, edx
0x18020498b  mov     rcx, rsi
0x18020498e  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204993  mov     r9d, [rbx+108h]
0x18020499a  lea     r8, aNonpagedpoolpa; "NonPagedPoolPages"
0x1802049a1  xor     edx, edx
0x1802049a3  mov     rcx, rsi
0x1802049a6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802049ab  mov     r9d, [rbx+10Ch]
0x1802049b2  lea     r8, aPagedpoolalloc; "PagedPoolAllocs"
0x1802049b9  xor     edx, edx
0x1802049bb  mov     rcx, rsi
0x1802049be  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802049c3  mov     r9d, [rbx+110h]
0x1802049ca  lea     r8, aPagedpoolfrees; "PagedPoolFrees"
0x1802049d1  xor     edx, edx
0x1802049d3  mov     rcx, rsi
0x1802049d6  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802049db  mov     r9d, [rbx+114h]
0x1802049e2  lea     r8, aNonpagedpoolal; "NonPagedPoolAllocs"
0x1802049e9  xor     edx, edx
0x1802049eb  mov     rcx, rsi
0x1802049ee  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x1802049f3  mov     r9d, [rbx+118h]
0x1802049fa  lea     r8, aNonpagedpoolfr; "NonPagedPoolFrees"
0x180204a01  xor     edx, edx
0x180204a03  mov     rcx, rsi
0x180204a06  call    ?PrintValue@@YAXAEBUFormatData@@W4FormatType@@PEBG_K@Z; PrintValue(FormatData const &,FormatType,ushort const *,unsigned __int64)
0x180204a0b  mov     r9d, [rbx+11Ch]
  ... truncated ...
```
