# CClfsLogFcbPhysical::MapCacheData(_FILE_OBJECT * const,_CLS_LSN const &,ulong,uchar,void * &,void * &)

- ea: `0x140015c0c`
- end: `0x140015de4`
- name: `?MapCacheData@CClfsLogFcbPhysical@@AEAAJQEAU_FILE_OBJECT@@AEBT_CLS_LSN@@KEAEAPEAX2@Z`
- size: `472`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *const@<rdx>, const union _CLS_LSN *@<r8>, unsigned int@<r9d>, char, void **, void **)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400496d4`
- `0x1400664b0`
- `0x140067854`
- `0x1400683b8`

## callees

- `0x140005840`
- `0x140010148`
- `0x140015c0c`
- `0x140017f20`
- `0x140058660`
- `0x140066e00`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140019975`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140019975`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140015c71`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140015c71`
- `ntoskrnl!CcMapData` at `0x140015d5b`
- `ntoskrnl!CcMapData` at `0x140015d5b`

## pseudocode

```c

```
