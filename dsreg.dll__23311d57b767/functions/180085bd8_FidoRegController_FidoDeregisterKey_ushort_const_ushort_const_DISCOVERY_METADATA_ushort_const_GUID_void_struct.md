# FidoRegController::FidoDeregisterKey(ushort const *,ushort const *,_DISCOVERY_METADATA *,ushort const *,_GUID *,void (*)(struct_fido_reg_response,unsigned __int64,long),unsigned __int64)

- ea: `0x180085bd8`
- end: `0x1800860cd`
- name: `?FidoDeregisterKey@FidoRegController@@SAJPEBG0PEAU_DISCOVERY_METADATA@@0PEAU_GUID@@P6AXUstruct_fido_reg_response@@_KJ@Z4@Z`
- size: `1269`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, struct _DISCOVERY_METADATA *@<r8>, const unsigned __int16 *@<r9>, struct _GUID *, void (__high *)(struct struct_fido_reg_response, unsigned __int64, int), unsigned __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x18004a760`

## callees

- `0x1800011ec`
- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000f368`
- `0x180017bb0`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x180037930`
- `0x18003fb10`
- `0x180044300`
- `0x18004651c`
- `0x180046540`
- `0x180085bd8`
- `0x1800860d4`
- `0x180086cc8`
- `0x180088af8`
- `0x1800bf010`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180085d1c`
- `RPCRT4!RpcStringFreeW` at `0x180085d1c`
- `RPCRT4!UuidToStringW` at `0x180085c3f`
- `RPCRT4!UuidToStringW` at `0x180085c3f`

## string_xrefs

- `0x180085d57`: `CreateGuid`
- `0x180085dc8`: `pcszAuthToken`
- `0x180085de7`: `pcszAuthToken`
- `0x180085e9f`: `pRegistrationInfo->pszWebAuthNServiceVersion`
- `0x180085ebe`: `pRegistrationInfo->pszWebAuthNServiceVersion`
- `0x180085fb4`: `FidoRegController::GetDeleteEndpoint`

## pseudocode

```c

```
