# MRxSmbStopTransport

- ea: `0x14004157c`
- end: `0x1400416d8`
- name: `MRxSmbStopTransport`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14003cad0`

## callees

- `0x14004157c`
- `0x14007e008`
- `0x140084d4c`
- `0x14008ff70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004166f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004166f`
- `ntoskrnl!ObfDereferenceObject` at `0x140041655`
- `ntoskrnl!ObfDereferenceObject` at `0x140041655`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004169e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004169e`
- `TDI!TdiDeregisterPnPHandlers` at `0x140041590`
- `TDI!TdiDeregisterPnPHandlers` at `0x140041590`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400415b8`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400415e0`
- `NETIO!NsiDeregisterChangeNotification` at `0x14004160b`
- `NETIO!NsiDeregisterChangeNotification` at `0x140041636`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400415b8`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400415e0`
- `NETIO!NsiDeregisterChangeNotification` at `0x14004160b`
- `NETIO!NsiDeregisterChangeNotification` at `0x140041636`

## pseudocode

```c
__int64 MRxSmbStopTransport()
{
  PVOID v0; // rbx
  KIRQL v1; // al

  v0 = 0;
  if ( MRxSmbTdiNotificationHandle )
  {
    TdiDeregisterPnPHandlers(MRxSmbTdiNotificationHandle);
    MRxSmbTdiNotificationHandle = 0;
  }
  if ( MRxSmbRdmaNotificationHandle )
  {
    NsiDeregisterChangeNotification(&NPI_MS_FLRDMA_MODULEID, 0);
    MRxSmbRdmaNotificationHandle = 0;
  }
  if ( MRxSmbRssNotificationHandle )
  {
    NsiDeregisterChangeNotification(NPI_MS_RSS_MODULEID, 0);
    MRxSmbRssNotificationHandle = 0;
  }
  if ( MRxSmbIPv6NsiHandle )
  {
    NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 10);
    MRxSmbIPv6NsiHandle = 0;
  }
  if ( MRxSmbIPv4NsiHandle )
  {
    NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10);
    MRxSmbIPv4NsiHandle = 0;
  }
  if ( MRxSmbWmiDataBlock )
  {
    ObfDereferenceObject(MRxSmbWmiDataBlock);
    MRxSmbWmiDataBlock = 0;
  }
  v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( qword_1400709C0 )
  {
    v0 = qword_1400709C0;
    qword_1400709C0 = 0;
  }
  KeReleaseSpinLock(&SpinLock, v1);
  if ( v0 )
    SmbCeDereferenceTransportArray(v0);
  SmbCeDiscardUnavailableServerList(MRxSmbHostUnavailableServers);
  SmbCeDiscardInvalidAuthEntryList(MRxSmbHostInvalidAuthEntries);
  return 0;
}

```

## disassembly

```asm
0x14004157c  push    rbx
0x14004157e  sub     rsp, 20h
0x140041582  mov     rcx, cs:MRxSmbTdiNotificationHandle; BindingHandle
0x140041589  xor     ebx, ebx
0x14004158b  test    rcx, rcx
0x14004158e  jz      short loc_1400415A3
0x140041590  call    cs:__imp_TdiDeregisterPnPHandlers
0x140041597  nop     dword ptr [rax+rax+00h]
0x14004159c  mov     cs:MRxSmbTdiNotificationHandle, rbx
0x1400415a3  mov     r8, cs:MRxSmbRdmaNotificationHandle
0x1400415aa  test    r8, r8
0x1400415ad  jz      short loc_1400415CB
0x1400415af  xor     edx, edx
0x1400415b1  lea     rcx, NPI_MS_FLRDMA_MODULEID
0x1400415b8  call    cs:__imp_NsiDeregisterChangeNotification
0x1400415bf  nop     dword ptr [rax+rax+00h]
0x1400415c4  mov     cs:MRxSmbRdmaNotificationHandle, rbx
0x1400415cb  mov     r8, cs:MRxSmbRssNotificationHandle
0x1400415d2  test    r8, r8
0x1400415d5  jz      short loc_1400415F3
0x1400415d7  xor     edx, edx
0x1400415d9  lea     rcx, NPI_MS_RSS_MODULEID
0x1400415e0  call    cs:__imp_NsiDeregisterChangeNotification
0x1400415e7  nop     dword ptr [rax+rax+00h]
0x1400415ec  mov     cs:MRxSmbRssNotificationHandle, rbx
0x1400415f3  mov     r8, cs:MRxSmbIPv6NsiHandle
0x1400415fa  test    r8, r8
0x1400415fd  jz      short loc_14004161E
0x1400415ff  mov     edx, 0Ah
0x140041604  lea     rcx, NPI_MS_IPV6_MODULEID
0x14004160b  call    cs:__imp_NsiDeregisterChangeNotification
0x140041612  nop     dword ptr [rax+rax+00h]
0x140041617  mov     cs:MRxSmbIPv6NsiHandle, rbx
0x14004161e  mov     r8, cs:MRxSmbIPv4NsiHandle
0x140041625  test    r8, r8
0x140041628  jz      short loc_140041649
0x14004162a  mov     edx, 0Ah
0x14004162f  lea     rcx, NPI_MS_IPV4_MODULEID
0x140041636  call    cs:__imp_NsiDeregisterChangeNotification
0x14004163d  nop     dword ptr [rax+rax+00h]
0x140041642  mov     cs:MRxSmbIPv4NsiHandle, rbx
0x140041649  mov     rcx, cs:MRxSmbWmiDataBlock; Object
0x140041650  test    rcx, rcx
0x140041653  jz      short loc_140041668
0x140041655  call    cs:__imp_ObfDereferenceObject
0x14004165c  nop     dword ptr [rax+rax+00h]
0x140041661  mov     cs:MRxSmbWmiDataBlock, rbx
0x140041668  lea     rcx, SpinLock; SpinLock
0x14004166f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140041676  nop     dword ptr [rax+rax+00h]
0x14004167b  mov     rdx, cs:qword_1400709C0
0x140041682  test    rdx, rdx
0x140041685  jz      short loc_140041695
0x140041687  mov     rbx, rdx
0x14004168a  mov     cs:qword_1400709C0, 0
0x140041695  mov     dl, al; NewIrql
0x140041697  lea     rcx, SpinLock; SpinLock
0x14004169e  call    cs:__imp_KeReleaseSpinLock
0x1400416a5  nop     dword ptr [rax+rax+00h]
0x1400416aa  test    rbx, rbx
0x1400416ad  jz      short loc_1400416B7
0x1400416af  mov     rcx, rbx; P
0x1400416b2  call    SmbCeDereferenceTransportArray
0x1400416b7  lea     rcx, MRxSmbHostUnavailableServers
0x1400416be  call    SmbCeDiscardUnavailableServerList
0x1400416c3  lea     rcx, MRxSmbHostInvalidAuthEntries
0x1400416ca  call    SmbCeDiscardInvalidAuthEntryList
0x1400416cf  xor     eax, eax
0x1400416d1  add     rsp, 20h
0x1400416d5  pop     rbx
0x1400416d6  retn
```
