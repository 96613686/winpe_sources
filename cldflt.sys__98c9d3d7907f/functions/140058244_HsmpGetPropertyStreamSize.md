# HsmpGetPropertyStreamSize

- ea: `0x140058244`
- end: `0x1400583fc`
- name: `HsmpGetPropertyStreamSize`
- size: `440`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140058404`

## callees

- `0x14001e140`
- `0x140058244`
- `0x14005e7e4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400582b2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400582b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005836b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005836b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005835f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005835f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400582a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400582a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14005834a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005834a`
- `FLTMGR!FltClose` at `0x140058336`
- `FLTMGR!FltClose` at `0x140058336`
- `FLTMGR!FltQueryInformationFile` at `0x1400583c3`
- `FLTMGR!FltQueryInformationFile` at `0x1400583c3`

## pseudocode

```c

```
