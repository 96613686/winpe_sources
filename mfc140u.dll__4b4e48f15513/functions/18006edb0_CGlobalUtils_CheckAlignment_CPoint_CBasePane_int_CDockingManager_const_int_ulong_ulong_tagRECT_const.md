# CGlobalUtils::CheckAlignment(CPoint,CBasePane *,int,CDockingManager const *,int,ulong &,ulong,tagRECT const *)

- ea: `0x18006edb0`
- end: `0x18006f0e5`
- name: `?CheckAlignment@CGlobalUtils@@QEBAHVCPoint@@PEAVCBasePane@@HPEBVCDockingManager@@HAEAKKPEBUtagRECT@@@Z`
- size: `821`
- prototype: `int __fastcall(CGlobalUtils *this, CPoint point, CBasePane *pBar, int nSensitivity, const CDockingManager *pDockManager, int bOuterEdge, unsigned int *dwAlignment, unsigned int dwEnabledDockBars, const tagRECT *lpRectBounds)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180045480`
- `0x180049580`
- `0x180049c00`
- `0x18006f9c0`
- `0x1800958d0`

## callees

- `0x18006edb0`
- `0x18006f0f0`
- `0x18023f820`
- `0x180296d00`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetWindowRect` at `0x18006ee5c`
- `USER32!GetWindowRect` at `0x18006ee5c`
- `USER32!CopyRect` at `0x18006eed6`
- `USER32!CopyRect` at `0x18006eed6`
- `USER32!GetParent` at `0x18006ee01`
- `USER32!GetParent` at `0x18006ee01`
- `USER32!PtInRect` at `0x18006ef27`
- `USER32!PtInRect` at `0x18006ef52`
- `USER32!PtInRect` at `0x18006ef89`
- `USER32!PtInRect` at `0x18006efb2`
- `USER32!PtInRect` at `0x18006f03d`
- `USER32!PtInRect` at `0x18006f073`
- `USER32!PtInRect` at `0x18006f0b6`
- `USER32!PtInRect` at `0x18006ef27`
- `USER32!PtInRect` at `0x18006ef52`
- `USER32!PtInRect` at `0x18006ef89`
- `USER32!PtInRect` at `0x18006efb2`
- `USER32!PtInRect` at `0x18006f03d`
- `USER32!PtInRect` at `0x18006f073`
- `USER32!PtInRect` at `0x18006f0b6`

## pseudocode

```c

```
