# CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)

- ea: `0x180080094`
- end: `0x180080316`
- name: `?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z`
- size: `642`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int64@<rdx>, int@<r8d>, struct IConfigManager2URI *@<r9>, struct CConfigServiceProvider2Impl *, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007de20`
- `0x18007ea20`
- `0x18007eed0`
- `0x180080630`
- `0x180080ba8`
- `0x180080ff0`
- `0x1800817a8`

## callees

- `0x180008de0`
- `0x18000da10`
- `0x18000db08`
- `0x18001a4d4`
- `0x180080094`
- `0x180080cc0`
- `0x1800827e0`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800801cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800801cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800802c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800802c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800800ff`
- `OLEAUT32!__imp_VariantInit` at `0x180080111`
- `OLEAUT32!__imp_VariantInit` at `0x1800800ff`
- `OLEAUT32!__imp_VariantInit` at `0x180080111`
- `OLEAUT32!__imp_VariantClear` at `0x1800802d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800802d2`

## pseudocode

```c

```
