# CreateRootSignatureHelper(ID3D12Device4 *,CD3DX12_VERSIONED_ROOT_SIGNATURE_DESC &,ID3D12RootSignature * *)

- ea: `0x1800b05bc`
- end: `0x1800b0724`
- name: `?CreateRootSignatureHelper@@YAJPEAUID3D12Device4@@AEAUCD3DX12_VERSIONED_ROOT_SIGNATURE_DESC@@PEAPEAUID3D12RootSignature@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(struct ID3D12Device4 *, struct CD3DX12_VERSIONED_ROOT_SIGNATURE_DESC *, struct ID3D12RootSignature **)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b072c`
- `0x1800b0f90`
- `0x1800ba7d4`
- `0x1800bb448`

## callees

- `0x180014750`
- `0x180067d2c`
- `0x1800697a8`
- `0x1800b05bc`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0609`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0609`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800b05ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800b05ef`

## string_xrefs

- `0x1800b061a`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x1800b066d`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x1800b05e8`: `d3d12.dll`

## pseudocode

```c

```
