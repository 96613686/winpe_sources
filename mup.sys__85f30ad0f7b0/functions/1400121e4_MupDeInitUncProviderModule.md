# MupDeInitUncProviderModule

- ea: `0x1400121e4`
- end: `0x1400122e8`
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
- `0x1400121e4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012264`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012264`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400122b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400122b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001224f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001224f`
- `ntoskrnl!ZwClose` at `0x140012220`
- `ntoskrnl!ZwClose` at `0x140012238`
- `ntoskrnl!ZwClose` at `0x140012220`
- `ntoskrnl!ZwClose` at `0x140012238`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400122c2`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400122d5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400122d5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400121f1`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400121f1`

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
0x1400121e4  push    rdi
0x1400121e6  sub     rsp, 20h
0x1400121ea  lea     rcx, UncProviderModuleRundownRef; RunRef
0x1400121f1  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400121f8  nop     dword ptr [rax+rax+00h]
0x1400121fd  lea     rcx, ProviderOrderRefreshTimer
0x140012204  call    RfsTimerCleanup
0x140012209  cmp     cs:MupiOrderKeyHandleValid, 0
0x140012210  jz      short loc_14001222C
0x140012212  mov     rcx, cs:MupiOrderKeyHandle; Handle
0x140012219  mov     cs:MupiOrderKeyHandleValid, 0
0x140012220  call    cs:__imp_ZwClose
0x140012227  nop     dword ptr [rax+rax+00h]
0x14001222c  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; Handle
0x140012233  test    rcx, rcx
0x140012236  jz      short loc_14001224F
0x140012238  call    cs:__imp_ZwClose
0x14001223f  nop     dword ptr [rax+rax+00h]
0x140012244  mov     cs:MupiNetworkProviderOrderKeyHandle, 0
0x14001224f  call    cs:__imp_KeEnterCriticalRegion
0x140012256  nop     dword ptr [rax+rax+00h]
0x14001225b  mov     dl, 1; Wait
0x14001225d  lea     rcx, Resource; Resource
0x140012264  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001226b  nop     dword ptr [rax+rax+00h]
0x140012270  lea     rdi, qword_14000A768
0x140012277  mov     rcx, cs:qword_14000A768
0x14001227e  cmp     rcx, rdi
0x140012281  jz      short loc_1400122AF
0x140012283  cmp     [rcx+8], rdi
0x140012287  jnz     short loc_1400122A8
0x140012289  mov     rax, [rcx]
0x14001228c  cmp     [rax+8], rcx
0x140012290  jnz     short loc_1400122A8
0x140012292  mov     cs:qword_14000A768, rax
0x140012299  add     rcx, 0FFFFFFFFFFFFFFF8h; P
0x14001229d  mov     [rax+8], rdi
0x1400122a1  call    MupiFreeProvider
0x1400122a6  jmp     short loc_140012277
0x1400122a8  mov     ecx, 3
0x1400122ad  int     29h; Win8: RtlFailFast(ecx)
0x1400122af  lea     rcx, Resource; Resource
0x1400122b6  call    cs:__imp_ExReleaseResourceLite
0x1400122bd  nop     dword ptr [rax+rax+00h]
0x1400122c2  call    cs:__imp_KeLeaveCriticalRegion
0x1400122c9  nop     dword ptr [rax+rax+00h]
0x1400122ce  lea     rcx, Resource; Resource
0x1400122d5  call    cs:__imp_ExDeleteResourceLite
0x1400122dc  nop     dword ptr [rax+rax+00h]
0x1400122e1  add     rsp, 20h
0x1400122e5  pop     rdi
0x1400122e6  retn
```
