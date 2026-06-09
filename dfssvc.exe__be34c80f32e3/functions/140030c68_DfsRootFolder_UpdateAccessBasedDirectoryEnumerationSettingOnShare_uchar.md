# DfsRootFolder::UpdateAccessBasedDirectoryEnumerationSettingOnShare(uchar)

- ea: `0x140030c68`
- end: `0x140030de3`
- name: `?UpdateAccessBasedDirectoryEnumerationSettingOnShare@DfsRootFolder@@QEAAKE@Z`
- size: `379`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140030e44`
- `0x140031108`

## callees

- `0x140005b90`
- `0x1400096ac`
- `0x140030c68`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x140030d59`
- `netutils!NetApiBufferFree` at `0x140030d59`
- `srvcli!NetShareGetInfo` at `0x140030cfc`
- `srvcli!NetShareGetInfo` at `0x140030cfc`
- `srvcli!NetShareSetInfo` at `0x140030d46`
- `srvcli!NetShareSetInfo` at `0x140030d46`

## pseudocode

```c

```
