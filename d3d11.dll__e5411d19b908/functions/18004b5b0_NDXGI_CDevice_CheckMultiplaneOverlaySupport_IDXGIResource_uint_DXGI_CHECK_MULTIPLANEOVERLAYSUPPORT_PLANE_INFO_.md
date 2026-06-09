# NDXGI::CDevice::CheckMultiplaneOverlaySupport(IDXGIResource *,uint,DXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO const *,int *,int *,void *)

- ea: `0x18004b5b0`
- end: `0x18004ba18`
- name: `?CheckMultiplaneOverlaySupport@CDevice@NDXGI@@UEAAJPEAUIDXGIResource@@IPEBUDXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO@@PEAH2PEAX@Z`
- size: `1128`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct IDXGIResource *, unsigned int, const struct DXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO *, int *, int *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800bc5e0`

## callees

- `0x18001e2a0`
- `0x180020ca0`
- `0x180021b90`
- `0x180022400`
- `0x180022630`
- `0x1800229a0`
- `0x18002bd20`
- `0x18002d0f0`
- `0x18002e160`
- `0x180034550`
- `0x18004b5b0`
- `0x18004ba20`
- `0x1800964b0`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800ba210`
- `0x1800ba340`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCheckMultiPlaneOverlaySupport3` at `0x18004b77a`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-3!__imp_D3DKMTCheckSinglePlaneForMultiPlaneOverlaySupport` at `0x18004b864`

## string_xrefs

- `0x18004b9ef`: `CheckMultiplaneOverlaySupport failed: PostCompositionCount is > 0 for single plane static check.`

## pseudocode

```c

```
