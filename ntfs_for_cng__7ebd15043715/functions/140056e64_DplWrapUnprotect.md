# DplWrapUnprotect

- ea: `0x140056e64`
- end: `0x140057860`
- name: `DplWrapUnprotect`
- size: `2556`
- prototype: `__int64 __fastcall(UCHAR *, ULONG, const void *, unsigned int, _OWORD *, ULONG pbOutput, void *, ULONG *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1401161e0`

## callees

- `0x140056220`
- `0x140056e64`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x140147658`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057655`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005767d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400576d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057729`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005775f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005779e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400577cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400577fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057834`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c967`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c9a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c9fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005caa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cba5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057655`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005767d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400576d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057729`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005775f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005779e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400577cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400577fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057834`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c967`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c9a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c9fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ca61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005caa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cb63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cba5`
- `ntoskrnl!ExAllocatePool2` at `0x140056f55`
- `ntoskrnl!ExAllocatePool2` at `0x140056f8a`
- `ntoskrnl!ExAllocatePool2` at `0x140056fb2`
- `ntoskrnl!ExAllocatePool2` at `0x14005713c`
- `ntoskrnl!ExAllocatePool2` at `0x1400571fa`
- `ntoskrnl!ExAllocatePool2` at `0x14005725e`
- `ntoskrnl!ExAllocatePool2` at `0x1400573fb`
- `ntoskrnl!ExAllocatePool2` at `0x140057449`
- `ntoskrnl!ExAllocatePool2` at `0x14005748d`
- `ntoskrnl!ExAllocatePool2` at `0x140056f55`
- `ntoskrnl!ExAllocatePool2` at `0x140056f8a`
- `ntoskrnl!ExAllocatePool2` at `0x140056fb2`
- `ntoskrnl!ExAllocatePool2` at `0x14005713c`
- `ntoskrnl!ExAllocatePool2` at `0x1400571fa`
- `ntoskrnl!ExAllocatePool2` at `0x14005725e`
- `ntoskrnl!ExAllocatePool2` at `0x1400573fb`
- `ntoskrnl!ExAllocatePool2` at `0x140057449`
- `ntoskrnl!ExAllocatePool2` at `0x14005748d`
- `ksecdd!BCryptDecrypt` at `0x140057567`
- `ksecdd!BCryptDecrypt` at `0x140057567`
- `ksecdd!BCryptGetProperty` at `0x1400571d1`
- `ksecdd!BCryptGetProperty` at `0x1400571d1`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400574d2`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400574d2`
- `ksecdd!BCryptCreateHash` at `0x1400572a6`
- `ksecdd!BCryptCreateHash` at `0x1400572a6`
- `ksecdd!BCryptHashData` at `0x1400572d6`
- `ksecdd!BCryptHashData` at `0x1400572d6`
- `ksecdd!BCryptDestroyHash` at `0x1400576e9`
- `ksecdd!BCryptDestroyHash` at `0x14005ca1f`
- `ksecdd!BCryptDestroyHash` at `0x1400576e9`
- `ksecdd!BCryptDestroyHash` at `0x14005ca1f`
- `ksecdd!BCryptFinishHash` at `0x14005730e`
- `ksecdd!BCryptFinishHash` at `0x14005730e`
- `ksecdd!BCryptDestroyKey` at `0x140057586`
- `ksecdd!BCryptDestroyKey` at `0x140057693`
- `ksecdd!BCryptDestroyKey` at `0x14005c9bd`
- `ksecdd!BCryptDestroyKey` at `0x140057586`
- `ksecdd!BCryptDestroyKey` at `0x140057693`
- `ksecdd!BCryptDestroyKey` at `0x14005c9bd`

## pseudocode

```c

```
