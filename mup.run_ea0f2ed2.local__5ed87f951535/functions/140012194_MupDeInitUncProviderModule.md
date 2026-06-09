# MupDeInitUncProviderModule

- ea: `0x140012194`
- end: `0x140012298`
- name: `MupDeInitUncProviderModule`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010f18`

## callees

- `0x1400051f0`
- `0x14000f644`
- `0x140012194`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012214`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012214`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012266`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012266`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121ff`
- `ntoskrnl!ZwClose` at `0x1400121d0`
- `ntoskrnl!ZwClose` at `0x1400121e8`
- `ntoskrnl!ZwClose` at `0x1400121d0`
- `ntoskrnl!ZwClose` at `0x1400121e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012272`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012272`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012285`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012285`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400121a1`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400121a1`

## pseudocode

```c
NTSTATUS MupDeInitUncProviderModule()
{
  __int64 v0; // rcx
  __int64 v1; // rax

  ExWaitForRundownProtectionRelease(&UncProviderModuleRundownRef);
  RfsTimerCleanup(ProviderOrderRefreshTimer);
  if ( MupiOrderKeyHandleValid )
  {
    MupiOrderKeyHandleValid = 0;
    ZwClose(MupiOrderKeyHandle);
  }
  if ( MupiNetworkProviderOrderKeyHandle )
  {
    ZwClose(MupiNetworkProviderOrderKeyHandle);
    MupiNetworkProviderOrderKeyHandle = 0;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  while ( 1 )
  {
    v0 = qword_14000A768;
    if ( (__int64 *)qword_14000A768 == &qword_14000A768 )
      break;
    if ( *(__int64 **)(qword_14000A768 + 8) != &qword_14000A768
      || (v1 = *(_QWORD *)qword_14000A768, *(_QWORD *)(*(_QWORD *)qword_14000A768 + 8LL) != qword_14000A768) )
    {
      __fastfail(3u);
    }
    qword_14000A768 = *(_QWORD *)qword_14000A768;
    *(_QWORD *)(v1 + 8) = &qword_14000A768;
    MupiFreeProvider((PVOID)(v0 - 8));
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  return ExDeleteResourceLite(&Resource);
}

```

## disassembly

```asm
0x140012194  push    rdi
0x140012196  sub     rsp, 20h
0x14001219a  lea     rcx, UncProviderModuleRundownRef; RunRef
0x1400121a1  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400121a8  nop     dword ptr [rax+rax+00h]
0x1400121ad  lea     rcx, ProviderOrderRefreshTimer
0x1400121b4  call    RfsTimerCleanup
0x1400121b9  cmp     cs:MupiOrderKeyHandleValid, 0
0x1400121c0  jz      short loc_1400121DC
0x1400121c2  mov     rcx, cs:MupiOrderKeyHandle; Handle
0x1400121c9  mov     cs:MupiOrderKeyHandleValid, 0
0x1400121d0  call    cs:__imp_ZwClose
0x1400121d7  nop     dword ptr [rax+rax+00h]
0x1400121dc  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; Handle
0x1400121e3  test    rcx, rcx
0x1400121e6  jz      short loc_1400121FF
0x1400121e8  call    cs:__imp_ZwClose
0x1400121ef  nop     dword ptr [rax+rax+00h]
0x1400121f4  mov     cs:MupiNetworkProviderOrderKeyHandle, 0
0x1400121ff  call    cs:__imp_KeEnterCriticalRegion
0x140012206  nop     dword ptr [rax+rax+00h]
0x14001220b  mov     dl, 1; Wait
0x14001220d  lea     rcx, Resource; Resource
0x140012214  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001221b  nop     dword ptr [rax+rax+00h]
0x140012220  lea     rdi, qword_14000A768
0x140012227  mov     rcx, cs:qword_14000A768
0x14001222e  cmp     rcx, rdi
0x140012231  jz      short loc_14001225F
0x140012233  cmp     [rcx+8], rdi
0x140012237  jnz     short loc_140012258
0x140012239  mov     rax, [rcx]
0x14001223c  cmp     [rax+8], rcx
0x140012240  jnz     short loc_140012258
0x140012242  mov     cs:qword_14000A768, rax
0x140012249  add     rcx, 0FFFFFFFFFFFFFFF8h; P
0x14001224d  mov     [rax+8], rdi
0x140012251  call    MupiFreeProvider
0x140012256  jmp     short loc_140012227
0x140012258  mov     ecx, 3
0x14001225d  int     29h; Win8: RtlFailFast(ecx)
0x14001225f  lea     rcx, Resource; Resource
0x140012266  call    cs:__imp_ExReleaseResourceLite
0x14001226d  nop     dword ptr [rax+rax+00h]
0x140012272  call    cs:__imp_KeLeaveCriticalRegion
0x140012279  nop     dword ptr [rax+rax+00h]
0x14001227e  lea     rcx, Resource; Resource
0x140012285  call    cs:__imp_ExDeleteResourceLite
0x14001228c  nop     dword ptr [rax+rax+00h]
0x140012291  add     rsp, 20h
0x140012295  pop     rdi
0x140012296  retn
```
