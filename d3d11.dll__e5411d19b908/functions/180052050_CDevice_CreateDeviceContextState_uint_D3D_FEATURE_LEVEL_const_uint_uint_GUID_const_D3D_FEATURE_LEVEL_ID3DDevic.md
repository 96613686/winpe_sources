# CDevice::CreateDeviceContextState(uint,D3D_FEATURE_LEVEL const *,uint,uint,_GUID const &,D3D_FEATURE_LEVEL *,ID3DDeviceContextState * *)

- ea: `0x180052050`
- end: `0x1800522c8`
- name: `?CreateDeviceContextState@CDevice@@UEAAJIPEBW4D3D_FEATURE_LEVEL@@IIAEBU_GUID@@PEAW42@PEAPEAUID3DDeviceContextState@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(CDevice *__hidden this, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, unsigned int, const struct _GUID *, enum D3D_FEATURE_LEVEL *, struct ID3DDeviceContextState **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180052050`
- `0x1800522d0`
- `0x18005237c`
- `0x1800526e8`
- `0x1800a11c8`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180052272`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180052272`

## string_xrefs

- `0x18005224a`: `\nD3D11 ERROR: D3D11.1 header version mismatch.\nThe application was compiled against and will only work with D3D11_SDK_VERSION (%d), but the currently installed runtime is version (%d).\nRecompile the application against the appropriate SDK for the installed runtime.\n\n`

## pseudocode

```c

```
