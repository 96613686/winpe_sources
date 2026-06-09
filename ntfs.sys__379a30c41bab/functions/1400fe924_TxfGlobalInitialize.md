# TxfGlobalInitialize

- ea: `0x1400fe924`
- end: `0x1400fee52`
- name: `TxfGlobalInitialize`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1402d3458`

## callees

- `0x140059740`
- `0x1400fee58`
- `0x140104290`
- `0x1401044ac`
- `0x1401046c4`
- `0x1401048b0`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe986`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9bd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9f9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea35`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea70`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feaac`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feae7`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb23`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb5f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febd2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec0a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec46`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec7f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecb6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecea`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed22`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed5a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed96`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fedd2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe986`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9bd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9f9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea35`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea70`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feaac`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feae7`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb23`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb5f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febd2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec0a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec46`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec7f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecb6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecea`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed22`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed5a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed96`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fedd2`
- `ntoskrnl!KeInitializeEvent` at `0x1400fedfb`
- `ntoskrnl!KeInitializeEvent` at `0x1400fedfb`

## pseudocode

```c
__int64 TxfGlobalInitialize()
{
  __int64 *v0; // rbx

  v0 = (__int64 *)TxfData;
  memset((char *)&(*TxfData)[0] + 4, 0, 0xCCu);
  *(_DWORD *)v0 = 13633296;
  ExInitializeLookasideListEx(&TransObjectLookasideList, 0, 0, PoolType, 1u, 0x1C8u, 0x72747854u, 0);
  ExInitializeLookasideListEx(&TxfTransSyncLookasideList, 0, 0, (POOL_TYPE)512, 1u, 0xD0u, 0x73747854u, 0);
  ExInitializeLookasideListEx(&TxfFcbLookasideList, 0, 0, PoolType, 1u, 0xA0u, 0x63667854u, 0);
  ExInitializeLookasideListEx(&TxfLargeFcbLookasideList, 0, 0, PoolType, 1u, 0xF0u, 0x666C7854u, 0);
  ExInitializeLookasideListEx(&TxfFcbExtensionLookasideList, 0, 0, PoolType, 1u, 0x50u, 0x65667854u, 0);
  ExInitializeLookasideListEx(&TxfDefaultReaderSectionLookasideList, 0, 0, PoolType, 1u, 0x10u, 0x72647854u, 0);
  ExInitializeLookasideListEx(&TxfFoLookasideList, 0, 0, PoolType, 1u, 0x48u, 0x6F667854u, 0);
  ExInitializeLookasideListEx(&TxfIsoSnapshotLookasideList, 0, 0, PoolType, 1u, 0x40u, 0x73697854u, 0);
  ExInitializeLookasideListEx(&TxfVscbLookasideList, 0, 0, PoolType, 1u, 0x138u, 0x6C767854u, 0);
  ExInitializeLookasideListEx(&TxfVscbFileSizesLookasideList, 0, 0, PoolType, 1u, 0x18u, 0x66767854u, 0);
  ExInitializeLookasideListEx(&TxfFcbInfoLookasideList, 0, 0, PoolType, 1u, 0x50u, 0x69667854u, 0);
  ExInitializeLookasideListEx(&TxfFcbCleanupLookasideList, 0, 0, PoolType, 1u, 0x48u, 0x6C667854u, 0);
  ExInitializeLookasideListEx(&TxfDeletedLinkLookasideList, 0, 0, PoolType, 1u, 0x28u, 0x6C647854u, 0);
  ExInitializeLookasideListEx(&TxfFcbQuotaInfoLookasideList, 0, 0, PoolType, 1u, 0x18u, 0x71667854u, 0);
  ExInitializeLookasideListEx(&TxfVscbQuotaInfoLookasideList, 0, 0, PoolType, 1u, 0x20u, 0x71667854u, 0);
  ExInitializeLookasideListEx(&TxfQuotaControlLookasideList, 0, 0, PoolType, 1u, 0x18u, 0x71667854u, 0);
  ExInitializeLookasideListEx(&TxfTransCancelListLookasideList, 0, 0, PoolType, 1u, 0x20u, 0x63747854u, 0);
  ExInitializeLookasideListEx(&TxfCancelLsnLookasideList, 0, 0, PoolType, 1u, 0x20u, 0x736C7854u, 0);
  ExInitializeLookasideListEx(&TxfSavepointLookasideList, 0, 0, PoolType, 1u, 0x30u, 0x70737854u, 0);
  ExInitializeLookasideListEx(&TxfTopsRangeEntryLookasideList, 0, 0, PoolType, 1u, 0x60u, 0x65727854u, 0);
  *((_DWORD *)v0 + 18) = 1;
  v0[10] = 0;
  *((_DWORD *)v0 + 22) = 0;
  KeInitializeEvent((PRKEVENT)v0 + 4, SynchronizationEvent, 0);
  v0[6] = 0;
  v0[5] = (__int64)TxfDelayedWorkItemRoutine;
  v0[3] = 0;
  v0[8] = (__int64)(v0 + 7);
  v0[7] = (__int64)(v0 + 7);
  TxfCreateCCORCTableForRedoCreateNewFile();
  TxfCreateCCORCTableForRedoAddTxfId();
  TxfCreateCCORCTableForDoAddNameWork();
  TxfCreateCCORCTableForSetShortNameWork();
  return TxfCreateCCORCTableForDoRemoveNameWork();
}

```

## disassembly

```asm
0x1400fe924  push    rbx
0x1400fe926  push    rbp
0x1400fe927  push    rsi
0x1400fe928  push    rdi
0x1400fe929  push    r14
0x1400fe92b  sub     rsp, 40h
0x1400fe92f  mov     rbx, cs:TxfData
0x1400fe936  xor     edx, edx; Val
0x1400fe938  mov     r8d, 0CCh; Size
0x1400fe93e  lea     rcx, [rbx+4]; void *
0x1400fe942  call    memset
0x1400fe947  xor     eax, eax
0x1400fe949  mov     dword ptr [rbx], 0D00710h
0x1400fe94f  mov     r9d, cs:PoolType; PoolType
0x1400fe956  lea     rcx, TransObjectLookasideList; Lookaside
0x1400fe95d  mov     [rsp+68h+Depth], ax; Depth
0x1400fe962  xor     r8d, r8d; Free
0x1400fe965  mov     [rsp+68h+Tag], 72747854h; Tag
0x1400fe96d  xor     edx, edx; Allocate
0x1400fe96f  lea     r14d, [rax+1]
0x1400fe973  mov     [rsp+68h+Size], 1C8h; Size
0x1400fe97c  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe981  mov     edi, 0D0h
0x1400fe986  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe98d  nop     dword ptr [rax+rax+00h]
0x1400fe992  xor     eax, eax
0x1400fe994  lea     rcx, TxfTransSyncLookasideList; Lookaside
0x1400fe99b  mov     [rsp+68h+Depth], ax; Depth
0x1400fe9a0  mov     r9d, 200h; PoolType
0x1400fe9a6  mov     [rsp+68h+Tag], 73747854h; Tag
0x1400fe9ae  xor     r8d, r8d; Free
0x1400fe9b1  mov     [rsp+68h+Size], rdi; Size
0x1400fe9b6  xor     edx, edx; Allocate
0x1400fe9b8  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe9bd  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe9c4  nop     dword ptr [rax+rax+00h]
0x1400fe9c9  mov     r9d, cs:PoolType; PoolType
0x1400fe9d0  lea     rcx, TxfFcbLookasideList; Lookaside
0x1400fe9d7  xor     eax, eax
0x1400fe9d9  xor     r8d, r8d; Free
0x1400fe9dc  mov     [rsp+68h+Depth], ax; Depth
0x1400fe9e1  xor     edx, edx; Allocate
0x1400fe9e3  mov     [rsp+68h+Tag], 63667854h; Tag
0x1400fe9eb  mov     [rsp+68h+Size], 0A0h; Size
0x1400fe9f4  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe9f9  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea00  nop     dword ptr [rax+rax+00h]
0x1400fea05  mov     r9d, cs:PoolType; PoolType
0x1400fea0c  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x1400fea13  xor     eax, eax
0x1400fea15  xor     r8d, r8d; Free
0x1400fea18  mov     [rsp+68h+Depth], ax; Depth
0x1400fea1d  xor     edx, edx; Allocate
0x1400fea1f  mov     [rsp+68h+Tag], 666C7854h; Tag
0x1400fea27  mov     [rsp+68h+Size], 0F0h; Size
0x1400fea30  mov     [rsp+68h+Flags], r14d; Flags
0x1400fea35  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea3c  nop     dword ptr [rax+rax+00h]
0x1400fea41  mov     r9d, cs:PoolType; PoolType
0x1400fea48  lea     esi, [rdi-80h]
0x1400fea4b  xor     eax, eax
0x1400fea4d  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x1400fea54  mov     [rsp+68h+Depth], ax; Depth
0x1400fea59  xor     r8d, r8d; Free
0x1400fea5c  mov     [rsp+68h+Tag], 65667854h; Tag
0x1400fea64  xor     edx, edx; Allocate
0x1400fea66  mov     [rsp+68h+Size], rsi; Size
0x1400fea6b  mov     [rsp+68h+Flags], r14d; Flags
0x1400fea70  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea77  nop     dword ptr [rax+rax+00h]
0x1400fea7c  mov     r9d, cs:PoolType; PoolType
0x1400fea83  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x1400fea8a  xor     eax, eax
0x1400fea8c  xor     r8d, r8d; Free
0x1400fea8f  mov     [rsp+68h+Depth], ax; Depth
0x1400fea94  xor     edx, edx; Allocate
0x1400fea96  mov     [rsp+68h+Tag], 72647854h; Tag
0x1400fea9e  mov     [rsp+68h+Size], 10h; Size
0x1400feaa7  mov     [rsp+68h+Flags], r14d; Flags
0x1400feaac  call    cs:__imp_ExInitializeLookasideListEx
0x1400feab3  nop     dword ptr [rax+rax+00h]
0x1400feab8  mov     r9d, cs:PoolType; PoolType
0x1400feabf  lea     edi, [rsi-8]
0x1400feac2  xor     eax, eax
0x1400feac4  lea     rcx, TxfFoLookasideList; Lookaside
0x1400feacb  mov     [rsp+68h+Depth], ax; Depth
0x1400fead0  xor     r8d, r8d; Free
0x1400fead3  mov     [rsp+68h+Tag], 6F667854h; Tag
0x1400feadb  xor     edx, edx; Allocate
0x1400feadd  mov     [rsp+68h+Size], rdi; Size
0x1400feae2  mov     [rsp+68h+Flags], r14d; Flags
0x1400feae7  call    cs:__imp_ExInitializeLookasideListEx
0x1400feaee  nop     dword ptr [rax+rax+00h]
0x1400feaf3  xor     eax, eax
0x1400feaf5  mov     r9d, cs:PoolType; PoolType
0x1400feafc  lea     rcx, TxfIsoSnapshotLookasideList; Lookaside
0x1400feb03  mov     [rsp+68h+Depth], ax; Depth
0x1400feb08  xor     r8d, r8d; Free
0x1400feb0b  mov     [rsp+68h+Tag], 73697854h; Tag
0x1400feb13  xor     edx, edx; Allocate
0x1400feb15  mov     [rsp+68h+Size], 40h ; '@'; Size
0x1400feb1e  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb23  call    cs:__imp_ExInitializeLookasideListEx
0x1400feb2a  nop     dword ptr [rax+rax+00h]
0x1400feb2f  mov     r9d, cs:PoolType; PoolType
0x1400feb36  lea     rcx, TxfVscbLookasideList; Lookaside
0x1400feb3d  xor     eax, eax
0x1400feb3f  xor     r8d, r8d; Free
0x1400feb42  mov     [rsp+68h+Depth], ax; Depth
0x1400feb47  xor     edx, edx; Allocate
0x1400feb49  mov     [rsp+68h+Tag], 6C767854h; Tag
0x1400feb51  mov     [rsp+68h+Size], 138h; Size
0x1400feb5a  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb5f  call    cs:__imp_ExInitializeLookasideListEx
0x1400feb66  nop     dword ptr [rax+rax+00h]
0x1400feb6b  mov     r9d, cs:PoolType; PoolType
0x1400feb72  lea     ebp, [rsi-38h]
0x1400feb75  xor     eax, eax
0x1400feb77  lea     rcx, TxfVscbFileSizesLookasideList; Lookaside
0x1400feb7e  mov     [rsp+68h+Depth], ax; Depth
0x1400feb83  xor     r8d, r8d; Free
0x1400feb86  mov     [rsp+68h+Tag], 66767854h; Tag
0x1400feb8e  xor     edx, edx; Allocate
0x1400feb90  mov     [rsp+68h+Size], rbp; Size
0x1400feb95  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb9a  call    cs:__imp_ExInitializeLookasideListEx
0x1400feba1  nop     dword ptr [rax+rax+00h]
0x1400feba6  mov     r9d, cs:PoolType; PoolType
0x1400febad  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x1400febb4  xor     eax, eax
0x1400febb6  xor     r8d, r8d; Free
0x1400febb9  mov     [rsp+68h+Depth], ax; Depth
0x1400febbe  xor     edx, edx; Allocate
0x1400febc0  mov     [rsp+68h+Tag], 69667854h; Tag
0x1400febc8  mov     [rsp+68h+Size], rsi; Size
0x1400febcd  mov     [rsp+68h+Flags], r14d; Flags
0x1400febd2  call    cs:__imp_ExInitializeLookasideListEx
0x1400febd9  nop     dword ptr [rax+rax+00h]
0x1400febde  mov     r9d, cs:PoolType; PoolType
0x1400febe5  lea     rcx, TxfFcbCleanupLookasideList; Lookaside
0x1400febec  xor     eax, eax
0x1400febee  xor     r8d, r8d; Free
0x1400febf1  mov     [rsp+68h+Depth], ax; Depth
0x1400febf6  xor     edx, edx; Allocate
0x1400febf8  mov     [rsp+68h+Tag], 6C667854h; Tag
0x1400fec00  mov     [rsp+68h+Size], rdi; Size
0x1400fec05  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec0a  call    cs:__imp_ExInitializeLookasideListEx
0x1400fec11  nop     dword ptr [rax+rax+00h]
0x1400fec16  mov     r9d, cs:PoolType; PoolType
0x1400fec1d  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1400fec24  xor     eax, eax
0x1400fec26  xor     r8d, r8d; Free
0x1400fec29  mov     [rsp+68h+Depth], ax; Depth
0x1400fec2e  xor     edx, edx; Allocate
0x1400fec30  mov     [rsp+68h+Tag], 6C647854h; Tag
0x1400fec38  mov     [rsp+68h+Size], 28h ; '('; Size
0x1400fec41  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec46  call    cs:__imp_ExInitializeLookasideListEx
0x1400fec4d  nop     dword ptr [rax+rax+00h]
0x1400fec52  mov     r9d, cs:PoolType; PoolType
0x1400fec59  lea     rcx, TxfFcbQuotaInfoLookasideList; Lookaside
0x1400fec60  xor     eax, eax
0x1400fec62  mov     edi, 71667854h
0x1400fec67  mov     [rsp+68h+Depth], ax; Depth
0x1400fec6c  xor     r8d, r8d; Free
0x1400fec6f  mov     [rsp+68h+Tag], edi; Tag
0x1400fec73  xor     edx, edx; Allocate
0x1400fec75  mov     [rsp+68h+Size], rbp; Size
0x1400fec7a  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec7f  call    cs:__imp_ExInitializeLookasideListEx
0x1400fec86  nop     dword ptr [rax+rax+00h]
0x1400fec8b  mov     r9d, cs:PoolType; PoolType
0x1400fec92  lea     esi, [rbp+8]
0x1400fec95  xor     eax, eax
0x1400fec97  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x1400fec9e  mov     [rsp+68h+Depth], ax; Depth
0x1400feca3  xor     r8d, r8d; Free
0x1400feca6  mov     [rsp+68h+Tag], edi; Tag
0x1400fecaa  xor     edx, edx; Allocate
0x1400fecac  mov     [rsp+68h+Size], rsi; Size
0x1400fecb1  mov     [rsp+68h+Flags], r14d; Flags
0x1400fecb6  call    cs:__imp_ExInitializeLookasideListEx
0x1400fecbd  nop     dword ptr [rax+rax+00h]
0x1400fecc2  mov     r9d, cs:PoolType; PoolType
0x1400fecc9  lea     rcx, TxfQuotaControlLookasideList; Lookaside
0x1400fecd0  xor     eax, eax
0x1400fecd2  xor     r8d, r8d; Free
0x1400fecd5  mov     [rsp+68h+Depth], ax; Depth
0x1400fecda  xor     edx, edx; Allocate
0x1400fecdc  mov     [rsp+68h+Tag], edi; Tag
0x1400fece0  mov     [rsp+68h+Size], rbp; Size
0x1400fece5  mov     [rsp+68h+Flags], r14d; Flags
0x1400fecea  call    cs:__imp_ExInitializeLookasideListEx
0x1400fecf1  nop     dword ptr [rax+rax+00h]
0x1400fecf6  mov     r9d, cs:PoolType; PoolType
0x1400fecfd  lea     rcx, TxfTransCancelListLookasideList; Lookaside
0x1400fed04  xor     eax, eax
0x1400fed06  xor     r8d, r8d; Free
0x1400fed09  mov     [rsp+68h+Depth], ax; Depth
0x1400fed0e  xor     edx, edx; Allocate
0x1400fed10  mov     [rsp+68h+Tag], 63747854h; Tag
0x1400fed18  mov     [rsp+68h+Size], rsi; Size
0x1400fed1d  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed22  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed29  nop     dword ptr [rax+rax+00h]
0x1400fed2e  mov     r9d, cs:PoolType; PoolType
0x1400fed35  lea     rcx, TxfCancelLsnLookasideList; Lookaside
0x1400fed3c  xor     eax, eax
0x1400fed3e  xor     r8d, r8d; Free
0x1400fed41  mov     [rsp+68h+Depth], ax; Depth
0x1400fed46  xor     edx, edx; Allocate
0x1400fed48  mov     [rsp+68h+Tag], 736C7854h; Tag
0x1400fed50  mov     [rsp+68h+Size], rsi; Size
0x1400fed55  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed5a  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed61  nop     dword ptr [rax+rax+00h]
0x1400fed66  mov     r9d, cs:PoolType; PoolType
0x1400fed6d  lea     rcx, TxfSavepointLookasideList; Lookaside
0x1400fed74  xor     eax, eax
0x1400fed76  xor     r8d, r8d; Free
0x1400fed79  mov     [rsp+68h+Depth], ax; Depth
0x1400fed7e  xor     edx, edx; Allocate
0x1400fed80  mov     [rsp+68h+Tag], 70737854h; Tag
0x1400fed88  mov     [rsp+68h+Size], 30h ; '0'; Size
0x1400fed91  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed96  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed9d  nop     dword ptr [rax+rax+00h]
0x1400feda2  mov     r9d, cs:PoolType; PoolType
0x1400feda9  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x1400fedb0  xor     eax, eax
0x1400fedb2  xor     r8d, r8d; Free
0x1400fedb5  mov     [rsp+68h+Depth], ax; Depth
0x1400fedba  xor     edx, edx; Allocate
0x1400fedbc  mov     [rsp+68h+Tag], 65727854h; Tag
0x1400fedc4  mov     [rsp+68h+Size], 60h ; '`'; Size
0x1400fedcd  mov     [rsp+68h+Flags], r14d; Flags
0x1400fedd2  call    cs:__imp_ExInitializeLookasideListEx
0x1400fedd9  nop     dword ptr [rax+rax+00h]
0x1400fedde  lea     rcx, [rbx+60h]; Event
0x1400fede2  mov     [rbx+48h], r14d
0x1400fede6  xor     r8d, r8d; State
0x1400fede9  mov     qword ptr [rbx+50h], 0
0x1400fedf1  mov     edx, r14d; Type
0x1400fedf4  mov     dword ptr [rbx+58h], 0
0x1400fedfb  call    cs:__imp_KeInitializeEvent
0x1400fee02  nop     dword ptr [rax+rax+00h]
0x1400fee07  mov     qword ptr [rbx+30h], 0
0x1400fee0f  lea     rax, TxfDelayedWorkItemRoutine
0x1400fee16  mov     [rbx+28h], rax
0x1400fee1a  lea     rax, [rbx+38h]
0x1400fee1e  mov     qword ptr [rbx+18h], 0
0x1400fee26  mov     [rax+8], rax
0x1400fee2a  mov     [rax], rax
0x1400fee2d  call    TxfCreateCCORCTableForRedoCreateNewFile
0x1400fee32  call    TxfCreateCCORCTableForRedoAddTxfId
0x1400fee37  call    TxfCreateCCORCTableForDoAddNameWork
0x1400fee3c  call    TxfCreateCCORCTableForSetShortNameWork
0x1400fee41  call    TxfCreateCCORCTableForDoRemoveNameWork
0x1400fee46  add     rsp, 40h
0x1400fee4a  pop     r14
0x1400fee4c  pop     rdi
0x1400fee4d  pop     rsi
0x1400fee4e  pop     rbp
0x1400fee4f  pop     rbx
0x1400fee50  retn
```
