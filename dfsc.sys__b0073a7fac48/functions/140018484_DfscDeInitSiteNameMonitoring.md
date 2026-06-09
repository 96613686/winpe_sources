# DfscDeInitSiteNameMonitoring

- ea: `0x140018484`
- end: `0x14001853e`
- name: `DfscDeInitSiteNameMonitoring`
- size: `186`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012930`

## callees

- `0x140018484`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400184b5`
- `ntoskrnl!ZwClose` at `0x1400184cd`
- `ntoskrnl!ZwClose` at `0x1400184b5`
- `ntoskrnl!ZwClose` at `0x1400184cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018519`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018519`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001850d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001850d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001849d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001849d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018488`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400184e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400184e7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001852c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001852c`

## pseudocode

```c
NTSTATUS DfscDeInitSiteNameMonitoring()
{
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( SiteNameRegKeyMonitor )
    ZwClose(SiteNameRegKeyMonitor);
  if ( DAConnectivityMonitor )
    ZwClose(DAConnectivityMonitor);
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
    *(_DWORD *)&DestinationString.Length = 0;
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  return ExDeleteResourceLite(&Resource);
}

```

## disassembly

```asm
0x140018484  sub     rsp, 28h
0x140018488  call    cs:__imp_KeEnterCriticalRegion
0x14001848f  nop     dword ptr [rax+rax+00h]
0x140018494  mov     dl, 1; Wait
0x140018496  lea     rcx, Resource; Resource
0x14001849d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400184a4  nop     dword ptr [rax+rax+00h]
0x1400184a9  mov     rcx, cs:SiteNameRegKeyMonitor; Handle
0x1400184b0  test    rcx, rcx
0x1400184b3  jz      short loc_1400184C1
0x1400184b5  call    cs:__imp_ZwClose
0x1400184bc  nop     dword ptr [rax+rax+00h]
0x1400184c1  mov     rcx, cs:DAConnectivityMonitor; Handle
0x1400184c8  test    rcx, rcx
0x1400184cb  jz      short loc_1400184D9
0x1400184cd  call    cs:__imp_ZwClose
0x1400184d4  nop     dword ptr [rax+rax+00h]
0x1400184d9  mov     rcx, cs:DestinationString.Buffer; P
0x1400184e0  test    rcx, rcx
0x1400184e3  jz      short loc_140018506
0x1400184e5  xor     edx, edx; Tag
0x1400184e7  call    cs:__imp_ExFreePoolWithTag
0x1400184ee  nop     dword ptr [rax+rax+00h]
0x1400184f3  xor     eax, eax
0x1400184f5  mov     cs:DestinationString.Buffer, 0
0x140018500  mov     dword ptr cs:DestinationString.Length, eax
0x140018506  lea     rcx, Resource; Resource
0x14001850d  call    cs:__imp_ExReleaseResourceLite
0x140018514  nop     dword ptr [rax+rax+00h]
0x140018519  call    cs:__imp_KeLeaveCriticalRegion
0x140018520  nop     dword ptr [rax+rax+00h]
0x140018525  lea     rcx, Resource; Resource
0x14001852c  call    cs:__imp_ExDeleteResourceLite
0x140018533  nop     dword ptr [rax+rax+00h]
0x140018538  add     rsp, 28h
0x14001853c  retn
```
