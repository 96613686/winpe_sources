# UnmarshalTaskParametersFromStream(IStream *,ushort * *,ITaskHandlerStatus * *)

- ea: `0x180037a14`
- end: `0x180037b19`
- name: `?UnmarshalTaskParametersFromStream@@YAJPEAUIStream@@PEAPEAGPEAPEAUITaskHandlerStatus@@@Z`
- size: `261`
- prototype: `HRESULT __fastcall(IStream *pStream, wchar_t **Data, ITaskHandlerStatus **ppTaskHandlerStatus)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180036d38`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x1800193d8`
- `0x180037a14`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180037af8`
- `OLEAUT32!__imp_SysFreeString` at `0x180037af8`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180037ac1`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180037ac1`

## pseudocode

```c

```
