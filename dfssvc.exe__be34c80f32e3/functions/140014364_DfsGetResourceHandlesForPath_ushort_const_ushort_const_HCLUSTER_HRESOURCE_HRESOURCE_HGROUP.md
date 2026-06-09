# DfsGetResourceHandlesForPath(ushort const *,ushort const *,_HCLUSTER *,_HRESOURCE * *,_HRESOURCE * *,_HGROUP * *)

- ea: `0x140014364`
- end: `0x14001442d`
- name: `?DfsGetResourceHandlesForPath@@YAKPEBG0PEAU_HCLUSTER@@PEAPEAU_HRESOURCE@@2PEAPEAU_HGROUP@@@Z`
- size: `201`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *lpInBuffer, HCLUSTER hCluster, struct _HRESOURCE **, struct _HRESOURCE **, struct _HGROUP **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012f74`

## callees

- `0x140013cec`
- `0x140013ef4`
- `0x140014364`

## import_xrefs

- `CLUSAPI!CloseClusterResource` at `0x1400143d1`
- `CLUSAPI!CloseClusterResource` at `0x1400143e9`
- `CLUSAPI!CloseClusterResource` at `0x1400143d1`
- `CLUSAPI!CloseClusterResource` at `0x1400143e9`
- `CLUSAPI!CloseClusterGroup` at `0x140014401`
- `CLUSAPI!CloseClusterGroup` at `0x140014401`

## pseudocode

```c

```
