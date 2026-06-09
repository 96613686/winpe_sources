# CClfsAuthContainer::CommitPatchSegment(_CLFS_PATCH_BUILDER_CONTEXT &,_KEVENT *,_CLFS_IO_WORKITEM *,uchar *,ulong)

- ea: `0x14003a3f0`
- end: `0x14003a526`
- name: `?CommitPatchSegment@CClfsAuthContainer@@AEAAJAEAU_CLFS_PATCH_BUILDER_CONTEXT@@PEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@PEAEK@Z`
- size: `310`
- prototype: `int(CClfsAuthContainer *__hidden this, struct _CLFS_PATCH_BUILDER_CONTEXT *, struct _KEVENT *, struct _CLFS_IO_WORKITEM *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013108`
- `0x140039e1c`

## callees

- `0x14000d084`
- `0x14003a3f0`
- `0x14006a9b0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14003a506`
- `ntoskrnl!IoQueueWorkItem` at `0x14007d8c1`
- `ntoskrnl!IoQueueWorkItem` at `0x14003a506`
- `ntoskrnl!IoQueueWorkItem` at `0x14007d8c1`
- `cng!BCryptHashData` at `0x14003a467`
- `cng!BCryptHashData` at `0x14003a467`

## pseudocode

```c

```
