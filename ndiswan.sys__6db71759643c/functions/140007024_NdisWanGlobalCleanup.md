# NdisWanGlobalCleanup

- ea: `0x140007024`
- end: `0x140007214`
- name: `NdisWanGlobalCleanup`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140026c00`
- `0x140039008`

## callees

- `0x140007024`
- `0x140012174`
- `0x14003709c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140007179`
- `ntoskrnl!ExDeleteResourceLite` at `0x140007179`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071ed`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007140`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007153`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007166`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000718c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000719f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400071b2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007140`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007153`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007166`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000718c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000719f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400071b2`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x140007121`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x140007121`
- `NDIS!NdisDeregisterProtocolDriver` at `0x140007102`
- `NDIS!NdisDeregisterProtocolDriver` at `0x140007102`
- `NDIS!NdisDeregisterProtocol` at `0x1400070e3`
- `NDIS!NdisDeregisterProtocol` at `0x1400070e3`
- `NDIS!NdisFreeRWLock` at `0x1400070bf`
- `NDIS!NdisFreeRWLock` at `0x1400070bf`
- `NDIS!NdisFreeNetBufferListPool` at `0x140007062`
- `NDIS!NdisFreeNetBufferListPool` at `0x140007081`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400070a0`
- `NDIS!NdisFreeNetBufferListPool` at `0x140007062`
- `NDIS!NdisFreeNetBufferListPool` at `0x140007081`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400070a0`
- `NDIS!NdisDeregisterDeviceEx` at `0x14000703c`
- `NDIS!NdisDeregisterDeviceEx` at `0x14000703c`

## pseudocode

```c
void NdisWanGlobalCleanup()
{
  int v0; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  if ( *(&pDeviceObject + 1) )
  {
    NdisDeregisterDeviceEx(*(&pDeviceObject + 1));
    *(_OWORD *)&pDeviceObject = 0u;
  }
  if ( IoPacketPool )
  {
    NdisFreeNetBufferListPool(IoPacketPool);
    IoPacketPool = 0;
  }
  if ( SendPacketPool )
  {
    NdisFreeNetBufferListPool(SendPacketPool);
    SendPacketPool = 0;
  }
  if ( RecvPacketPool )
  {
    NdisFreeNetBufferListPool(RecvPacketPool);
    RecvPacketPool = 0;
  }
  if ( ConnTableLock )
  {
    NdisFreeRWLock(ConnTableLock);
    ConnTableLock = 0;
  }
  if ( qword_14001E2E8 )
  {
    NdisDeregisterProtocol(&v0);
    qword_14001E2E8 = 0;
  }
  if ( NdisProtocolHandle )
  {
    NdisDeregisterProtocolDriver(NdisProtocolHandle);
    NdisProtocolHandle = 0;
  }
  if ( NdisMiniportDriverHandle )
  {
    NdisMDeregisterMiniportDriver(NdisMiniportDriverHandle);
    NdisMiniportDriverHandle = 0;
  }
  WanDeleteECP();
  ExDeleteNPagedLookasideList(&BundleCBList);
  ExDeleteNPagedLookasideList(&LinkProtoCBList);
  ExDeleteNPagedLookasideList(&RecvHeaderLookaside);
  ExDeleteResourceLite(&QoSPolicyResourceLock);
  ExDeleteNPagedLookasideList(&WanRequestLegacyList);
  ExDeleteNPagedLookasideList(&AfSapVcCBList);
  ExDeleteNPagedLookasideList(&WorkItemList);
  if ( ConnectionTable )
  {
    ExFreePoolWithTag(ConnectionTable, 0);
    ConnectionTable = 0;
  }
  if ( ProtocolInfoTable )
  {
    ExFreePoolWithTag(ProtocolInfoTable, 0);
    ProtocolInfoTable = 0;
  }
  if ( QoSModuleInitialized )
    BwcDeinit();
}

```

## disassembly

```asm
0x140007024  push    rbx
0x140007026  sub     rsp, 20h
0x14000702a  mov     rcx, qword ptr cs:pDeviceObject+8; NdisDeviceHandle
0x140007031  xor     ebx, ebx
0x140007033  mov     [rsp+28h+arg_0], ebx
0x140007037  test    rcx, rcx
0x14000703a  jz      short loc_140007056
0x14000703c  call    cs:__imp_NdisDeregisterDeviceEx
0x140007043  nop     dword ptr [rax+rax+00h]
0x140007048  mov     qword ptr cs:pDeviceObject+8, rbx
0x14000704f  mov     qword ptr cs:pDeviceObject, rbx
0x140007056  mov     rcx, cs:IoPacketPool; PoolHandle
0x14000705d  test    rcx, rcx
0x140007060  jz      short loc_140007075
0x140007062  call    cs:__imp_NdisFreeNetBufferListPool
0x140007069  nop     dword ptr [rax+rax+00h]
0x14000706e  mov     cs:IoPacketPool, rbx
0x140007075  mov     rcx, cs:SendPacketPool; PoolHandle
0x14000707c  test    rcx, rcx
0x14000707f  jz      short loc_140007094
0x140007081  call    cs:__imp_NdisFreeNetBufferListPool
0x140007088  nop     dword ptr [rax+rax+00h]
0x14000708d  mov     cs:SendPacketPool, rbx
0x140007094  mov     rcx, cs:RecvPacketPool; PoolHandle
0x14000709b  test    rcx, rcx
0x14000709e  jz      short loc_1400070B3
0x1400070a0  call    cs:__imp_NdisFreeNetBufferListPool
0x1400070a7  nop     dword ptr [rax+rax+00h]
0x1400070ac  mov     cs:RecvPacketPool, rbx
0x1400070b3  mov     rcx, cs:ConnTableLock; Lock
0x1400070ba  test    rcx, rcx
0x1400070bd  jz      short loc_1400070D2
0x1400070bf  call    cs:__imp_NdisFreeRWLock
0x1400070c6  nop     dword ptr [rax+rax+00h]
0x1400070cb  mov     cs:ConnTableLock, rbx
0x1400070d2  mov     rdx, cs:qword_14001E2E8
0x1400070d9  test    rdx, rdx
0x1400070dc  jz      short loc_1400070F6
0x1400070de  lea     rcx, [rsp+28h+arg_0]
0x1400070e3  call    cs:__imp_NdisDeregisterProtocol
0x1400070ea  nop     dword ptr [rax+rax+00h]
0x1400070ef  mov     cs:qword_14001E2E8, rbx
0x1400070f6  mov     rcx, cs:NdisProtocolHandle; NdisProtocolHandle
0x1400070fd  test    rcx, rcx
0x140007100  jz      short loc_140007115
0x140007102  call    cs:__imp_NdisDeregisterProtocolDriver
0x140007109  nop     dword ptr [rax+rax+00h]
0x14000710e  mov     cs:NdisProtocolHandle, rbx
0x140007115  mov     rcx, cs:NdisMiniportDriverHandle; NdisMiniportDriverHandle
0x14000711c  test    rcx, rcx
0x14000711f  jz      short loc_140007134
0x140007121  call    cs:__imp_NdisMDeregisterMiniportDriver
0x140007128  nop     dword ptr [rax+rax+00h]
0x14000712d  mov     cs:NdisMiniportDriverHandle, rbx
0x140007134  call    WanDeleteECP
0x140007139  lea     rcx, BundleCBList; Lookaside
0x140007140  call    cs:__imp_ExDeleteNPagedLookasideList
0x140007147  nop     dword ptr [rax+rax+00h]
0x14000714c  lea     rcx, LinkProtoCBList; Lookaside
0x140007153  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000715a  nop     dword ptr [rax+rax+00h]
0x14000715f  lea     rcx, RecvHeaderLookaside; Lookaside
0x140007166  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000716d  nop     dword ptr [rax+rax+00h]
0x140007172  lea     rcx, QoSPolicyResourceLock; Resource
0x140007179  call    cs:__imp_ExDeleteResourceLite
0x140007180  nop     dword ptr [rax+rax+00h]
0x140007185  lea     rcx, WanRequestLegacyList; Lookaside
0x14000718c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140007193  nop     dword ptr [rax+rax+00h]
0x140007198  lea     rcx, AfSapVcCBList; Lookaside
0x14000719f  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400071a6  nop     dword ptr [rax+rax+00h]
0x1400071ab  lea     rcx, WorkItemList; Lookaside
0x1400071b2  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400071b9  nop     dword ptr [rax+rax+00h]
0x1400071be  mov     rcx, cs:ConnectionTable; P
0x1400071c5  test    rcx, rcx
0x1400071c8  jz      short loc_1400071DF
0x1400071ca  xor     edx, edx; Tag
0x1400071cc  call    cs:__imp_ExFreePoolWithTag
0x1400071d3  nop     dword ptr [rax+rax+00h]
0x1400071d8  mov     cs:ConnectionTable, rbx
0x1400071df  mov     rcx, cs:ProtocolInfoTable; P
0x1400071e6  test    rcx, rcx
0x1400071e9  jz      short loc_140007200
0x1400071eb  xor     edx, edx; Tag
0x1400071ed  call    cs:__imp_ExFreePoolWithTag
0x1400071f4  nop     dword ptr [rax+rax+00h]
0x1400071f9  mov     cs:ProtocolInfoTable, rbx
0x140007200  cmp     cs:QoSModuleInitialized, bl
0x140007206  jz      short loc_14000720D
0x140007208  call    BwcDeinit
0x14000720d  add     rsp, 20h
0x140007211  pop     rbx
0x140007212  retn
```
