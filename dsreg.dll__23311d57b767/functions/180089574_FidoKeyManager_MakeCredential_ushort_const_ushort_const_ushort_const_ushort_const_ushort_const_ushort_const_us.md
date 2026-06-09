# FidoKeyManager::MakeCredential(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,FidoKey * *,ulong *)

- ea: `0x180089574`
- end: `0x180089f79`
- name: `?MakeCredential@FidoKeyManager@@SAJPEBG0000000K0000PEAPEAVFidoKey@@PEAK@Z`
- size: `2565`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct FidoKey **, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x180086538`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180017944`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x18003ee18`
- `0x18003f3dc`
- `0x180044300`
- `0x180044d30`
- `0x18004651c`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x180085590`
- `0x180087198`
- `0x1800891a8`
- `0x180089328`
- `0x180089398`
- `0x1800893dc`
- `0x180089574`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180089ec1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180089ec1`
- `webauthn!WebAuthNGetCoseAlgorithmIdentifier` at `0x180089988`
- `webauthn!WebAuthNGetCoseAlgorithmIdentifier` at `0x180089988`
- `webauthn!WebAuthNFreeCredentialAttestation` at `0x180089dec`
- `webauthn!WebAuthNFreeCredentialAttestation` at `0x180089dec`
- `webauthn!WebAuthNCtapMakeCredential` at `0x180089b3d`
- `webauthn!WebAuthNCtapMakeCredential` at `0x180089b3d`
- `RPCRT4!UuidFromStringW` at `0x18008987f`
- `RPCRT4!UuidFromStringW` at `0x18008987f`

## string_xrefs

- `0x1800897d5`: `authToken`
- `0x1800897e8`: `authToken`
- `0x180089a4d`: `FidoRequestSerializer::CreateClientData`
- `0x1800898f1`: `Azure Active Directory`
- `0x180089a69`: `%s: The size of ClientDataJson is larger than the maximum integer value.`

## pseudocode

```c

```
