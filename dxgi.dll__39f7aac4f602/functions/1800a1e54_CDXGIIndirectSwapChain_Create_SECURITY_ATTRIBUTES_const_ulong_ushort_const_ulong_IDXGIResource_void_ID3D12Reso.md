# CDXGIIndirectSwapChain::Create(_SECURITY_ATTRIBUTES const *,ulong,ushort const *,ulong,IDXGIResource * *,void *,ID3D12Resource * *)

- ea: `0x1800a1e54`
- end: `0x1800a22ea`
- name: `?Create@CDXGIIndirectSwapChain@@AEAAXPEBU_SECURITY_ATTRIBUTES@@KPEBGKPEAPEAUIDXGIResource@@PEAXPEAPEAUID3D12Resource@@@Z`
- size: `1174`
- prototype: `void __usercall(CDXGIIndirectSwapChain *__hidden this@<rcx>, const struct _SECURITY_ATTRIBUTES *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, unsigned int, struct IDXGIResource **, void *, struct ID3D12Resource **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045080`

## callees

- `0x180010d40`
- `0x180014750`
- `0x18002b390`
- `0x180030320`
- `0x180031a78`
- `0x180031ab8`
- `0x180031d28`
- `0x180032ef0`
- `0x180076f20`
- `0x1800a1e54`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a2017`
- `ntdll!RtlInitUnicodeString` at `0x1800a2017`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x1800a204c`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x1800a204c`

## pseudocode

```c

```
