# NgcRequestSerializer::CreateHeader(_GUID const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18008504c`
- end: `0x1800851a5`
- name: `?CreateHeader@NgcRequestSerializer@@SAJPEBU_GUID@@PEBG1PEAPEAG@Z`
- size: `345`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007f394`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x18001035c`
- `0x180012cf0`
- `0x1800307c4`
- `0x18008504c`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180085169`
- `RPCRT4!RpcStringFreeW` at `0x180085169`
- `RPCRT4!UuidToStringW` at `0x1800850b5`
- `RPCRT4!UuidToStringW` at `0x1800850b5`

## string_xrefs

- `0x18008507a`: `NgcRequestSerializer::CreateHeader`
- `0x180085099`: `NgcRequestSerializer::CreateHeader`
- `0x18008514b`: `NgcRequestSerializer::CreateHeader`
- `0x18008511c`: `Accept: application/json\nreturn-client-request-id: true\nclient-request-Id: %s\nAuthorization: Bearer %s\napi-version: %s\n`

## pseudocode

```c

```
