# CDXGISwapChain::CheckMultiplaneOverlaySupportInternal(IDXGIDeviceInternal3 *,uint,DXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO const *,int *,int *,int *)

- ea: `0x180039550`
- end: `0x180039db2`
- name: `?CheckMultiplaneOverlaySupportInternal@CDXGISwapChain@@QEAAJPEAUIDXGIDeviceInternal3@@IPEBUDXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO@@PEAH22@Z`
- size: `2146`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, struct IDXGIDeviceInternal3 *, unsigned int, const struct DXGI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039050`
- `0x18006e5b8`

## callees

- `0x18000c6b0`
- `0x18000ce70`
- `0x180039550`
- `0x180075fa0`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180039700`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180039c13`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180039700`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180039c13`

## string_xrefs

- `0x180039aec`: `CheckMultiplaneOverlaySupportInternal failed: fullscreen post composition is not allowed for planes other than 0`
- `0x180039a66`: `CheckMultiplaneOverlaySupportInternal failed: Process is not DWM nor fullscreen app nor on CASO path`

## pseudocode

```c

```
