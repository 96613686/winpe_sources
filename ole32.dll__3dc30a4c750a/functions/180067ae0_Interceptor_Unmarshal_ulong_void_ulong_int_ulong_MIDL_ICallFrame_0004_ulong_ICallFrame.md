# Interceptor::Unmarshal(ulong,void *,ulong,int,ulong,__MIDL_ICallFrame_0004 *,ulong *,ICallFrame * *)

- ea: `0x180067ae0`
- end: `0x1800681e5`
- name: `?Unmarshal@Interceptor@@EEAAJKPEAXKHKPEAU__MIDL_ICallFrame_0004@@PEAKPEAPEAUICallFrame@@@Z`
- size: `1797`
- prototype: `HRESULT __fastcall(Interceptor *this, unsigned int iMethod, void *pBuffer, unsigned int cbBuffer, int fForceBufferCopy, unsigned int dataRep, __MIDL_ICallFrame_0004 *pctx, unsigned int *pcbUnmarshalled, ICallFrame **ppFrame)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014ec8`
- `0x180017894`
- `0x18001eb8c`
- `0x18001ebc0`
- `0x180020850`
- `0x18003f9c0`
- `0x18003fa30`
- `0x180052390`
- `0x180053014`
- `0x180066f5c`
- `0x180067ae0`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800680e1`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800680e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067e73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067e73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180067c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180067c3b`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x180067f00`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x180067f1d`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x180067f00`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x180067f1d`
- `RPCRT4!NdrGetSimpleTypeBufferSize` at `0x180067f43`
- `RPCRT4!NdrGetSimpleTypeBufferSize` at `0x180067f43`
- `RPCRT4!NdrUnmarshallBasetypeInline` at `0x180067f63`
- `RPCRT4!NdrUnmarshallBasetypeInline` at `0x180067f63`
- `RPCRT4!NdrTypeUnmarshall` at `0x180067fd9`
- `RPCRT4!NdrTypeUnmarshall` at `0x180067fd9`
- `RPCRT4!NdrOutInit` at `0x18006809e`
- `RPCRT4!NdrOutInit` at `0x18006809e`
- `RPCRT4!NdrCorrelationInitialize` at `0x180067e89`
- `RPCRT4!NdrCorrelationInitialize` at `0x180067e89`
- `api-ms-win-core-com-private-l1-1-0!NdrExtStubInitialize` at `0x180067e04`
- `api-ms-win-core-com-private-l1-1-0!NdrExtStubInitialize` at `0x180067e04`
- `api-ms-win-core-com-private-l1-1-0!InternalCallFrameExceptionFilter` at `0x1800ccf68`
- `api-ms-win-core-com-private-l1-1-0!InternalCallFrameExceptionFilter` at `0x1800ccf68`

## pseudocode

```c

```
