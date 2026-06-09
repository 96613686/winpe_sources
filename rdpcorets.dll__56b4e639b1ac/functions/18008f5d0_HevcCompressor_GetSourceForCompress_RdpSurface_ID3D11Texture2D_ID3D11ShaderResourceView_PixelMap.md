# HevcCompressor::GetSourceForCompress(RdpSurface *,ID3D11Texture2D * *,ID3D11ShaderResourceView * *,PixelMap * *)

- ea: `0x18008f5d0`
- end: `0x18008f83b`
- name: `?GetSourceForCompress@HevcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAUID3D11Texture2D@@PEAPEAUID3D11ShaderResourceView@@PEAPEAVPixelMap@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(HevcCompressor *__hidden this, struct RdpSurface *, struct ID3D11Texture2D **, struct ID3D11ShaderResourceView **, struct PixelMap **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180092110`

## callees

- `0x180009628`
- `0x18002e600`
- `0x180032f60`
- `0x18008e730`
- `0x18008f5d0`
- `0x1800e5410`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f643`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f6cc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f7d5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f643`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f6cc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008f7d5`
- `RDPSERVERBASE!?GetEncodingPixelMap@RdpSurface@@QEAAJPEAPEAVPixelMap@@@Z` at `0x18008f7aa`
- `RDPSERVERBASE!?GetEncodingPixelMap@RdpSurface@@QEAAJPEAPEAVPixelMap@@@Z` at `0x18008f7aa`

## string_xrefs

- `0x18008f720`: `ShaderResourceView not found during initialization, non-fatal`
- `0x18008f77d`: `DX texture not found during compress, non-fatal`

## pseudocode

```c

```
