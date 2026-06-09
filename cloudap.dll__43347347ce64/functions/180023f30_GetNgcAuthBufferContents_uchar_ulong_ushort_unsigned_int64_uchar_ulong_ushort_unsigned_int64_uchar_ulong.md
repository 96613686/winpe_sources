# GetNgcAuthBufferContents(uchar *,ulong,ushort * *,unsigned __int64 *,uchar * *,ulong *,ushort * *,unsigned __int64 *,uchar * *,ulong *)

- ea: `0x180023f30`
- end: `0x1800243c0`
- name: `?GetNgcAuthBufferContents@@YAJPEAEKPEAPEAGPEA_KPEAPEAEPEAK1234@Z`
- size: `1168`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned __int64 *, HLOCAL, unsigned int *Source, unsigned __int16 **, unsigned __int64 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001e130`

## callees

- `0x180007720`
- `0x180007fc0`
- `0x18000a600`
- `0x180023f30`
- `0x1800293c0`
- `0x180043158`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024268`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024268`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x180023ff9`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x180023ff9`
- `cryptngc!NgcUnpackCredData` at `0x180023fac`
- `cryptngc!NgcUnpackCredData` at `0x180023fac`

## string_xrefs

- `0x180024322`: `CopyToMidlHeap`
- `0x18002416b`: `CopyStringToMidlHeap`
- `0x1800241b2`: `CopyStringToMidlHeap`

## pseudocode

```c

```
