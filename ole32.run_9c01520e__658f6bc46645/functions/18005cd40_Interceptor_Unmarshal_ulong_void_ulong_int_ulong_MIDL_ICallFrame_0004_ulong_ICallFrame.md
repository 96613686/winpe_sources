# Interceptor::Unmarshal(ulong,void *,ulong,int,ulong,__MIDL_ICallFrame_0004 *,ulong *,ICallFrame * *)

- ea: `0x18005cd40`
- end: `0x18005d49d`
- name: `?Unmarshal@Interceptor@@EEAAJKPEAXKHKPEAU__MIDL_ICallFrame_0004@@PEAKPEAPEAUICallFrame@@@Z`
- size: `1885`
- prototype: `HRESULT __fastcall(Interceptor *this, unsigned int iMethod, void *pBuffer, unsigned int cbBuffer, int fForceBufferCopy, unsigned int dataRep, __MIDL_ICallFrame_0004 *pctx, unsigned int *pcbUnmarshalled, ICallFrame **ppFrame)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014c68`
- `0x180020b10`
- `0x180021a70`
- `0x180021ab0`
- `0x180025f64`
- `0x1800429f8`
- `0x180042a68`
- `0x180046460`
- `0x180047484`
- `0x180059d90`
- `0x18005cd40`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18005d381`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18005d381`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005d0f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005d0f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ceae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ceae`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x18005d188`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x18005d1a3`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x18005d188`
- `RPCRT4!NdrGetSimpleTypeBufferAlignment` at `0x18005d1a3`
- `RPCRT4!NdrGetSimpleTypeBufferSize` at `0x18005d1cb`
- `RPCRT4!NdrGetSimpleTypeBufferSize` at `0x18005d1cb`
- `RPCRT4!NdrUnmarshallBasetypeInline` at `0x18005d1ed`
- `RPCRT4!NdrUnmarshallBasetypeInline` at `0x18005d1ed`
- `RPCRT4!NdrTypeUnmarshall` at `0x18005d266`
- `RPCRT4!NdrTypeUnmarshall` at `0x18005d266`
- `RPCRT4!NdrOutInit` at `0x18005d335`
- `RPCRT4!NdrOutInit` at `0x18005d335`
- `RPCRT4!NdrCorrelationInitialize` at `0x18005d10d`
- `RPCRT4!NdrCorrelationInitialize` at `0x18005d10d`
- `api-ms-win-core-com-private-l1-1-0!NdrExtStubInitialize` at `0x18005d074`
- `api-ms-win-core-com-private-l1-1-0!NdrExtStubInitialize` at `0x18005d074`
- `api-ms-win-core-com-private-l1-1-0!InternalCallFrameExceptionFilter` at `0x1800d7106`
- `api-ms-win-core-com-private-l1-1-0!InternalCallFrameExceptionFilter` at `0x1800d7106`

## pseudocode

```c

```
