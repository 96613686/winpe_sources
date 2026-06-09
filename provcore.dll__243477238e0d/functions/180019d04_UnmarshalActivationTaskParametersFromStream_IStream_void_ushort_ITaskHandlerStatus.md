# UnmarshalActivationTaskParametersFromStream(IStream *,void * &,ushort * *,ITaskHandlerStatus * *)

- ea: `0x180019d04`
- end: `0x180019e9b`
- name: `?UnmarshalActivationTaskParametersFromStream@@YAJPEAUIStream@@AEAPEAXPEAPEAGPEAPEAUITaskHandlerStatus@@@Z`
- size: `407`
- prototype: `HRESULT __fastcall(IStream *pStream, void **CancelEvent, wchar_t **Data, ITaskHandlerStatus **ppTaskHandlerStatus)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017d2c`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012748`
- `0x180012770`
- `0x1800193d8`
- `0x180019d04`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019e7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e7a`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180019e4f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180019e4f`

## pseudocode

```c

```
