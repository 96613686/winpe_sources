# CPiecesToStreamProcessor::_FlushPendingWrites(DestinationFileRange const &,std::map<unsigned __int64,CPiecesToStreamProcessor::PendingWrite,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CPiecesToStreamProcessor::PendingWrite>>> &,uint &)

- ea: `0x1800f6664`
- end: `0x1800f687f`
- name: `?_FlushPendingWrites@CPiecesToStreamProcessor@@AEAAJAEBUDestinationFileRange@@AEAV?$map@_KUPendingWrite@CPiecesToStreamProcessor@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUPendingWrite@CPiecesToStreamProcessor@@@std@@@4@@std@@AEAI@Z`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800f638c`

## callees

- `0x18001e77c`
- `0x180020c58`
- `0x1800a1ea4`
- `0x1800f6664`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f66c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f678c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f66c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f678c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f66e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f67af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f66e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f67af`

## string_xrefs

- `0x1800f6717`: `CPiecesToStreamProcessor::_FlushPendingWrites`
- `0x1800f670a`: `PSP: Flushing range {%llu, %llu} with nextWriteOffset = %llu`

## pseudocode

```c

```
