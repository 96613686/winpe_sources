# TxfGlobalInitialize

- ea: `0x1400fe8d4`
- end: `0x1400fee02`
- name: `TxfGlobalInitialize`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1402d3458`

## callees

- `0x1400596c0`
- `0x1400fee08`
- `0x140104240`
- `0x14010445c`
- `0x140104674`
- `0x140104860`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe936`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe96d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9a9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9e5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea20`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea5c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea97`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fead3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb0f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb4a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb82`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febba`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febf6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec2f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec66`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecd2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed0a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed46`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed82`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe936`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe96d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9a9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fe9e5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea20`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea5c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fea97`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fead3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb0f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb4a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400feb82`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febba`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400febf6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec2f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec66`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fec9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fecd2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed0a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed46`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400fed82`
- `ntoskrnl!KeInitializeEvent` at `0x1400fedab`
- `ntoskrnl!KeInitializeEvent` at `0x1400fedab`

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
0x1400fe8d4  push    rbx
0x1400fe8d6  push    rbp
0x1400fe8d7  push    rsi
0x1400fe8d8  push    rdi
0x1400fe8d9  push    r14
0x1400fe8db  sub     rsp, 40h
0x1400fe8df  mov     rbx, cs:TxfData
0x1400fe8e6  xor     edx, edx; Val
0x1400fe8e8  mov     r8d, 0CCh; Size
0x1400fe8ee  lea     rcx, [rbx+4]; void *
0x1400fe8f2  call    memset
0x1400fe8f7  xor     eax, eax
0x1400fe8f9  mov     dword ptr [rbx], 0D00710h
0x1400fe8ff  mov     r9d, cs:PoolType; PoolType
0x1400fe906  lea     rcx, TransObjectLookasideList; Lookaside
0x1400fe90d  mov     [rsp+68h+Depth], ax; Depth
0x1400fe912  xor     r8d, r8d; Free
0x1400fe915  mov     [rsp+68h+Tag], 72747854h; Tag
0x1400fe91d  xor     edx, edx; Allocate
0x1400fe91f  lea     r14d, [rax+1]
0x1400fe923  mov     [rsp+68h+Size], 1C8h; Size
0x1400fe92c  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe931  mov     edi, 0D0h
0x1400fe936  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe93d  nop     dword ptr [rax+rax+00h]
0x1400fe942  xor     eax, eax
0x1400fe944  lea     rcx, TxfTransSyncLookasideList; Lookaside
0x1400fe94b  mov     [rsp+68h+Depth], ax; Depth
0x1400fe950  mov     r9d, 200h; PoolType
0x1400fe956  mov     [rsp+68h+Tag], 73747854h; Tag
0x1400fe95e  xor     r8d, r8d; Free
0x1400fe961  mov     [rsp+68h+Size], rdi; Size
0x1400fe966  xor     edx, edx; Allocate
0x1400fe968  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe96d  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe974  nop     dword ptr [rax+rax+00h]
0x1400fe979  mov     r9d, cs:PoolType; PoolType
0x1400fe980  lea     rcx, TxfFcbLookasideList; Lookaside
0x1400fe987  xor     eax, eax
0x1400fe989  xor     r8d, r8d; Free
0x1400fe98c  mov     [rsp+68h+Depth], ax; Depth
0x1400fe991  xor     edx, edx; Allocate
0x1400fe993  mov     [rsp+68h+Tag], 63667854h; Tag
0x1400fe99b  mov     [rsp+68h+Size], 0A0h; Size
0x1400fe9a4  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe9a9  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe9b0  nop     dword ptr [rax+rax+00h]
0x1400fe9b5  mov     r9d, cs:PoolType; PoolType
0x1400fe9bc  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x1400fe9c3  xor     eax, eax
0x1400fe9c5  xor     r8d, r8d; Free
0x1400fe9c8  mov     [rsp+68h+Depth], ax; Depth
0x1400fe9cd  xor     edx, edx; Allocate
0x1400fe9cf  mov     [rsp+68h+Tag], 666C7854h; Tag
0x1400fe9d7  mov     [rsp+68h+Size], 0F0h; Size
0x1400fe9e0  mov     [rsp+68h+Flags], r14d; Flags
0x1400fe9e5  call    cs:__imp_ExInitializeLookasideListEx
0x1400fe9ec  nop     dword ptr [rax+rax+00h]
0x1400fe9f1  mov     r9d, cs:PoolType; PoolType
0x1400fe9f8  lea     esi, [rdi-80h]
0x1400fe9fb  xor     eax, eax
0x1400fe9fd  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x1400fea04  mov     [rsp+68h+Depth], ax; Depth
0x1400fea09  xor     r8d, r8d; Free
0x1400fea0c  mov     [rsp+68h+Tag], 65667854h; Tag
0x1400fea14  xor     edx, edx; Allocate
0x1400fea16  mov     [rsp+68h+Size], rsi; Size
0x1400fea1b  mov     [rsp+68h+Flags], r14d; Flags
0x1400fea20  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea27  nop     dword ptr [rax+rax+00h]
0x1400fea2c  mov     r9d, cs:PoolType; PoolType
0x1400fea33  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x1400fea3a  xor     eax, eax
0x1400fea3c  xor     r8d, r8d; Free
0x1400fea3f  mov     [rsp+68h+Depth], ax; Depth
0x1400fea44  xor     edx, edx; Allocate
0x1400fea46  mov     [rsp+68h+Tag], 72647854h; Tag
0x1400fea4e  mov     [rsp+68h+Size], 10h; Size
0x1400fea57  mov     [rsp+68h+Flags], r14d; Flags
0x1400fea5c  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea63  nop     dword ptr [rax+rax+00h]
0x1400fea68  mov     r9d, cs:PoolType; PoolType
0x1400fea6f  lea     edi, [rsi-8]
0x1400fea72  xor     eax, eax
0x1400fea74  lea     rcx, TxfFoLookasideList; Lookaside
0x1400fea7b  mov     [rsp+68h+Depth], ax; Depth
0x1400fea80  xor     r8d, r8d; Free
0x1400fea83  mov     [rsp+68h+Tag], 6F667854h; Tag
0x1400fea8b  xor     edx, edx; Allocate
0x1400fea8d  mov     [rsp+68h+Size], rdi; Size
0x1400fea92  mov     [rsp+68h+Flags], r14d; Flags
0x1400fea97  call    cs:__imp_ExInitializeLookasideListEx
0x1400fea9e  nop     dword ptr [rax+rax+00h]
0x1400feaa3  xor     eax, eax
0x1400feaa5  mov     r9d, cs:PoolType; PoolType
0x1400feaac  lea     rcx, TxfIsoSnapshotLookasideList; Lookaside
0x1400feab3  mov     [rsp+68h+Depth], ax; Depth
0x1400feab8  xor     r8d, r8d; Free
0x1400feabb  mov     [rsp+68h+Tag], 73697854h; Tag
0x1400feac3  xor     edx, edx; Allocate
0x1400feac5  mov     [rsp+68h+Size], 40h ; '@'; Size
0x1400feace  mov     [rsp+68h+Flags], r14d; Flags
0x1400fead3  call    cs:__imp_ExInitializeLookasideListEx
0x1400feada  nop     dword ptr [rax+rax+00h]
0x1400feadf  mov     r9d, cs:PoolType; PoolType
0x1400feae6  lea     rcx, TxfVscbLookasideList; Lookaside
0x1400feaed  xor     eax, eax
0x1400feaef  xor     r8d, r8d; Free
0x1400feaf2  mov     [rsp+68h+Depth], ax; Depth
0x1400feaf7  xor     edx, edx; Allocate
0x1400feaf9  mov     [rsp+68h+Tag], 6C767854h; Tag
0x1400feb01  mov     [rsp+68h+Size], 138h; Size
0x1400feb0a  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb0f  call    cs:__imp_ExInitializeLookasideListEx
0x1400feb16  nop     dword ptr [rax+rax+00h]
0x1400feb1b  mov     r9d, cs:PoolType; PoolType
0x1400feb22  lea     ebp, [rsi-38h]
0x1400feb25  xor     eax, eax
0x1400feb27  lea     rcx, TxfVscbFileSizesLookasideList; Lookaside
0x1400feb2e  mov     [rsp+68h+Depth], ax; Depth
0x1400feb33  xor     r8d, r8d; Free
0x1400feb36  mov     [rsp+68h+Tag], 66767854h; Tag
0x1400feb3e  xor     edx, edx; Allocate
0x1400feb40  mov     [rsp+68h+Size], rbp; Size
0x1400feb45  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb4a  call    cs:__imp_ExInitializeLookasideListEx
0x1400feb51  nop     dword ptr [rax+rax+00h]
0x1400feb56  mov     r9d, cs:PoolType; PoolType
0x1400feb5d  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x1400feb64  xor     eax, eax
0x1400feb66  xor     r8d, r8d; Free
0x1400feb69  mov     [rsp+68h+Depth], ax; Depth
0x1400feb6e  xor     edx, edx; Allocate
0x1400feb70  mov     [rsp+68h+Tag], 69667854h; Tag
0x1400feb78  mov     [rsp+68h+Size], rsi; Size
0x1400feb7d  mov     [rsp+68h+Flags], r14d; Flags
0x1400feb82  call    cs:__imp_ExInitializeLookasideListEx
0x1400feb89  nop     dword ptr [rax+rax+00h]
0x1400feb8e  mov     r9d, cs:PoolType; PoolType
0x1400feb95  lea     rcx, TxfFcbCleanupLookasideList; Lookaside
0x1400feb9c  xor     eax, eax
0x1400feb9e  xor     r8d, r8d; Free
0x1400feba1  mov     [rsp+68h+Depth], ax; Depth
0x1400feba6  xor     edx, edx; Allocate
0x1400feba8  mov     [rsp+68h+Tag], 6C667854h; Tag
0x1400febb0  mov     [rsp+68h+Size], rdi; Size
0x1400febb5  mov     [rsp+68h+Flags], r14d; Flags
0x1400febba  call    cs:__imp_ExInitializeLookasideListEx
0x1400febc1  nop     dword ptr [rax+rax+00h]
0x1400febc6  mov     r9d, cs:PoolType; PoolType
0x1400febcd  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1400febd4  xor     eax, eax
0x1400febd6  xor     r8d, r8d; Free
0x1400febd9  mov     [rsp+68h+Depth], ax; Depth
0x1400febde  xor     edx, edx; Allocate
0x1400febe0  mov     [rsp+68h+Tag], 6C647854h; Tag
0x1400febe8  mov     [rsp+68h+Size], 28h ; '('; Size
0x1400febf1  mov     [rsp+68h+Flags], r14d; Flags
0x1400febf6  call    cs:__imp_ExInitializeLookasideListEx
0x1400febfd  nop     dword ptr [rax+rax+00h]
0x1400fec02  mov     r9d, cs:PoolType; PoolType
0x1400fec09  lea     rcx, TxfFcbQuotaInfoLookasideList; Lookaside
0x1400fec10  xor     eax, eax
0x1400fec12  mov     edi, 71667854h
0x1400fec17  mov     [rsp+68h+Depth], ax; Depth
0x1400fec1c  xor     r8d, r8d; Free
0x1400fec1f  mov     [rsp+68h+Tag], edi; Tag
0x1400fec23  xor     edx, edx; Allocate
0x1400fec25  mov     [rsp+68h+Size], rbp; Size
0x1400fec2a  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec2f  call    cs:__imp_ExInitializeLookasideListEx
0x1400fec36  nop     dword ptr [rax+rax+00h]
0x1400fec3b  mov     r9d, cs:PoolType; PoolType
0x1400fec42  lea     esi, [rbp+8]
0x1400fec45  xor     eax, eax
0x1400fec47  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x1400fec4e  mov     [rsp+68h+Depth], ax; Depth
0x1400fec53  xor     r8d, r8d; Free
0x1400fec56  mov     [rsp+68h+Tag], edi; Tag
0x1400fec5a  xor     edx, edx; Allocate
0x1400fec5c  mov     [rsp+68h+Size], rsi; Size
0x1400fec61  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec66  call    cs:__imp_ExInitializeLookasideListEx
0x1400fec6d  nop     dword ptr [rax+rax+00h]
0x1400fec72  mov     r9d, cs:PoolType; PoolType
0x1400fec79  lea     rcx, TxfQuotaControlLookasideList; Lookaside
0x1400fec80  xor     eax, eax
0x1400fec82  xor     r8d, r8d; Free
0x1400fec85  mov     [rsp+68h+Depth], ax; Depth
0x1400fec8a  xor     edx, edx; Allocate
0x1400fec8c  mov     [rsp+68h+Tag], edi; Tag
0x1400fec90  mov     [rsp+68h+Size], rbp; Size
0x1400fec95  mov     [rsp+68h+Flags], r14d; Flags
0x1400fec9a  call    cs:__imp_ExInitializeLookasideListEx
0x1400feca1  nop     dword ptr [rax+rax+00h]
0x1400feca6  mov     r9d, cs:PoolType; PoolType
0x1400fecad  lea     rcx, TxfTransCancelListLookasideList; Lookaside
0x1400fecb4  xor     eax, eax
0x1400fecb6  xor     r8d, r8d; Free
0x1400fecb9  mov     [rsp+68h+Depth], ax; Depth
0x1400fecbe  xor     edx, edx; Allocate
0x1400fecc0  mov     [rsp+68h+Tag], 63747854h; Tag
0x1400fecc8  mov     [rsp+68h+Size], rsi; Size
0x1400feccd  mov     [rsp+68h+Flags], r14d; Flags
0x1400fecd2  call    cs:__imp_ExInitializeLookasideListEx
0x1400fecd9  nop     dword ptr [rax+rax+00h]
0x1400fecde  mov     r9d, cs:PoolType; PoolType
0x1400fece5  lea     rcx, TxfCancelLsnLookasideList; Lookaside
0x1400fecec  xor     eax, eax
0x1400fecee  xor     r8d, r8d; Free
0x1400fecf1  mov     [rsp+68h+Depth], ax; Depth
0x1400fecf6  xor     edx, edx; Allocate
0x1400fecf8  mov     [rsp+68h+Tag], 736C7854h; Tag
0x1400fed00  mov     [rsp+68h+Size], rsi; Size
0x1400fed05  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed0a  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed11  nop     dword ptr [rax+rax+00h]
0x1400fed16  mov     r9d, cs:PoolType; PoolType
0x1400fed1d  lea     rcx, TxfSavepointLookasideList; Lookaside
0x1400fed24  xor     eax, eax
0x1400fed26  xor     r8d, r8d; Free
0x1400fed29  mov     [rsp+68h+Depth], ax; Depth
0x1400fed2e  xor     edx, edx; Allocate
0x1400fed30  mov     [rsp+68h+Tag], 70737854h; Tag
0x1400fed38  mov     [rsp+68h+Size], 30h ; '0'; Size
0x1400fed41  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed46  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed4d  nop     dword ptr [rax+rax+00h]
0x1400fed52  mov     r9d, cs:PoolType; PoolType
0x1400fed59  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x1400fed60  xor     eax, eax
0x1400fed62  xor     r8d, r8d; Free
0x1400fed65  mov     [rsp+68h+Depth], ax; Depth
0x1400fed6a  xor     edx, edx; Allocate
0x1400fed6c  mov     [rsp+68h+Tag], 65727854h; Tag
0x1400fed74  mov     [rsp+68h+Size], 60h ; '`'; Size
0x1400fed7d  mov     [rsp+68h+Flags], r14d; Flags
0x1400fed82  call    cs:__imp_ExInitializeLookasideListEx
0x1400fed89  nop     dword ptr [rax+rax+00h]
0x1400fed8e  lea     rcx, [rbx+60h]; Event
0x1400fed92  mov     [rbx+48h], r14d
0x1400fed96  xor     r8d, r8d; State
0x1400fed99  mov     qword ptr [rbx+50h], 0
0x1400feda1  mov     edx, r14d; Type
0x1400feda4  mov     dword ptr [rbx+58h], 0
0x1400fedab  call    cs:__imp_KeInitializeEvent
0x1400fedb2  nop     dword ptr [rax+rax+00h]
0x1400fedb7  mov     qword ptr [rbx+30h], 0
0x1400fedbf  lea     rax, TxfDelayedWorkItemRoutine
0x1400fedc6  mov     [rbx+28h], rax
0x1400fedca  lea     rax, [rbx+38h]
0x1400fedce  mov     qword ptr [rbx+18h], 0
0x1400fedd6  mov     [rax+8], rax
0x1400fedda  mov     [rax], rax
0x1400feddd  call    TxfCreateCCORCTableForRedoCreateNewFile
0x1400fede2  call    TxfCreateCCORCTableForRedoAddTxfId
0x1400fede7  call    TxfCreateCCORCTableForDoAddNameWork
0x1400fedec  call    TxfCreateCCORCTableForSetShortNameWork
0x1400fedf1  call    TxfCreateCCORCTableForDoRemoveNameWork
0x1400fedf6  add     rsp, 40h
0x1400fedfa  pop     r14
0x1400fedfc  pop     rdi
0x1400fedfd  pop     rsi
0x1400fedfe  pop     rbp
0x1400fedff  pop     rbx
0x1400fee00  retn
```
