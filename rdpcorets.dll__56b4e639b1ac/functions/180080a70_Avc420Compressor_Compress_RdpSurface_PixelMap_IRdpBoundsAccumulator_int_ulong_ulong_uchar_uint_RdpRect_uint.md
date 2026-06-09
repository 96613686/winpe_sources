# Avc420Compressor::Compress(RdpSurface *,PixelMap *,IRdpBoundsAccumulator *,int,ulong,ulong,uchar *,uint *,RdpRect *,uint)

- ea: `0x180080a70`
- end: `0x18008140b`
- name: `?Compress@Avc420Compressor@@UEAAJPEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpBoundsAccumulator@@HKKPEAEPEAIPEAURdpRect@@I@Z`
- size: `2459`
- prototype: `int(Avc420Compressor *__hidden this, struct RdpSurface *, struct PixelMap *, struct IRdpBoundsAccumulator *, int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, struct RdpRect *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180083ca0`

## callees

- `0x1800065c0`
- `0x1800071c0`
- `0x1800071f0`
- `0x1800093f0`
- `0x180009470`
- `0x180017928`
- `0x1800194b0`
- `0x180019758`
- `0x180025b80`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x1800598d0`
- `0x18007a800`
- `0x18007d060`
- `0x180080a70`
- `0x180081ba8`
- `0x1800b8804`
- `0x1800d9cc0`
- `0x1800d9cf4`
- `0x1800d9de0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800813c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800813c0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080b57`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080bc2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080c28`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080d48`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080e5b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080f1d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080ff8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081053`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008109e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081108`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008115d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800811f9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800812ac`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008132f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080b57`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080bc2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080c28`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080d48`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080e5b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080f1d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180080ff8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081053`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008109e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081108`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008115d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800811f9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800812ac`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008132f`

## string_xrefs

- `0x180080b62`: `GetSourceForCompress failed`
- `0x180081003`: `Compress using MFT encoder failed`
- `0x180081204`: `Compress using RDP SW encoder failed`

## pseudocode

```c

```
