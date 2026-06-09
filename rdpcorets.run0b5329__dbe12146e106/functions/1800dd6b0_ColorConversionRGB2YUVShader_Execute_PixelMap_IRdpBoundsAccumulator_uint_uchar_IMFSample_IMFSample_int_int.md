# ColorConversionRGB2YUVShader::Execute(PixelMap &,IRdpBoundsAccumulator *,uint,uchar *,IMFSample * *,IMFSample * *,int *,int)

- ea: `0x1800dd6b0`
- end: `0x1800dda5b`
- name: `?Execute@ColorConversionRGB2YUVShader@@UEAAJAEAVPixelMap@@PEAVIRdpBoundsAccumulator@@IPEAEPEAPEAUIMFSample@@3PEAHH@Z`
- size: `939`
- prototype: `__int64 __usercall@<rax>(ColorConversionRGB2YUVShader *__hidden this@<rcx>, struct PixelMap *@<rdx>, struct IRdpBoundsAccumulator *@<r8>, unsigned int@<r9d>, unsigned __int8 *, struct IMFSample **, struct IMFSample **, int *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x18002e600`
- `0x1800598d0`
- `0x1800dd0c4`
- `0x1800dd294`
- `0x1800dd500`
- `0x1800dd6b0`
- `0x1800de378`
- `0x1801496fc`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd6ff`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd759`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd798`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd7f7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd845`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd89b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd8f9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd95a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd9ab`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd6ff`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd759`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd798`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd7f7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd845`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd89b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd8f9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd95a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dd9ab`

## string_xrefs

- `0x1800dd764`: `CreateRGBTextureAndSRV failed`
- `0x1800dd904`: `CreateMFSampleYUVOutput failed`
- `0x1800dd850`: `CopyPixelMapToTexture failed`
- `0x1800dd965`: `CreateMFSampleYUVOutput (Chroma) failed`

## pseudocode

```c

```
