# DrawCompositionLine(HWND__ *,HDC__ *,HFONT__ *,ushort const *,uchar const *,uint,uint,uint,int)

- ea: `0x1801cddd8`
- end: `0x1801ce02b`
- name: `?DrawCompositionLine@@YAXPEAUHWND__@@PEAUHDC__@@PEAUHFONT__@@PEBGPEBEIIIH@Z`
- size: `595`
- prototype: `void(HWND, HDC, HFONT, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801ce350`

## callees

- `0x180016c78`
- `0x18006a640`
- `0x1800ecc64`
- `0x180114520`
- `0x1801cddd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cde6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cdfef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cde6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801cdfef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801cdffd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801cdffd`
- `GDI32!SetBkColor` at `0x1801cdf0e`
- `GDI32!SetBkColor` at `0x1801cdfe9`
- `GDI32!SetBkColor` at `0x1801cdf0e`
- `GDI32!SetBkColor` at `0x1801cdfe9`
- `GDI32!SetTextColor` at `0x1801cdeff`
- `GDI32!SetTextColor` at `0x1801cdfdd`
- `GDI32!SetTextColor` at `0x1801cdeff`
- `GDI32!SetTextColor` at `0x1801cdfdd`
- `GDI32!SelectObject` at `0x1801cdf1e`
- `GDI32!SelectObject` at `0x1801cdfd1`
- `GDI32!SelectObject` at `0x1801cdf1e`
- `GDI32!SelectObject` at `0x1801cdfd1`
- `USER32!DrawTextW` at `0x1801cdf68`
- `USER32!DrawTextW` at `0x1801cdf90`
- `USER32!DrawTextW` at `0x1801cdf68`
- `USER32!DrawTextW` at `0x1801cdf90`
- `USER32!SendMessageW` at `0x1801cdf36`
- `USER32!SendMessageW` at `0x1801cdf36`
- `USER32!GetSysColor` at `0x1801cdecd`
- `USER32!GetSysColor` at `0x1801cdedf`
- `USER32!GetSysColor` at `0x1801cdef0`
- `USER32!GetSysColor` at `0x1801cdecd`
- `USER32!GetSysColor` at `0x1801cdedf`
- `USER32!GetSysColor` at `0x1801cdef0`

## pseudocode

```c

```
