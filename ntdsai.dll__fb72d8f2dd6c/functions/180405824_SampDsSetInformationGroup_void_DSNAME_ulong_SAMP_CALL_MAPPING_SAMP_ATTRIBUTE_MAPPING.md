# SampDsSetInformationGroup(void *,_DSNAME *,ulong,SAMP_CALL_MAPPING *,SAMP_ATTRIBUTE_MAPPING *)

- ea: `0x180405824`
- end: `0x180405b26`
- name: `?SampDsSetInformationGroup@@YAJPEAXPEAU_DSNAME@@KPEAUSAMP_CALL_MAPPING@@PEAUSAMP_ATTRIBUTE_MAPPING@@@Z`
- size: `770`
- prototype: `int(void *, struct _DSNAME *, unsigned int, struct SAMP_CALL_MAPPING *, struct SAMP_ATTRIBUTE_MAPPING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180403960`

## callees

- `0x18001e090`
- `0x180405824`
- `0x180406908`
- `0x180406944`
- `0x18040720c`
- `0x1804076fc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180405a7b`
- `ntdll!RtlInitUnicodeString` at `0x180405a7b`
- `SAMSRV!SampAuditAccountNameChange` at `0x1804059a8`
- `SAMSRV!SampAuditAccountNameChange` at `0x1804059a8`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405a53`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405afa`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405a53`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405afa`
- `SAMSRV!SampChangeGroupAccountName` at `0x180405a8c`
- `SAMSRV!SampChangeGroupAccountName` at `0x180405a8c`
- `SAMSRV!SampRetrieveGroupV1Fixed` at `0x180405907`
- `SAMSRV!SampRetrieveGroupV1Fixed` at `0x180405907`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x180405ade`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x180405ade`
- `SAMSRV!SampFreeUnicodeString` at `0x1804059b8`
- `SAMSRV!SampFreeUnicodeString` at `0x180405b06`
- `SAMSRV!SampFreeUnicodeString` at `0x1804059b8`
- `SAMSRV!SampFreeUnicodeString` at `0x180405b06`
- `SAMSRV!SampDeReferenceContext` at `0x180405984`
- `SAMSRV!SampDeReferenceContext` at `0x180405b19`
- `SAMSRV!SampDeReferenceContext` at `0x180405984`
- `SAMSRV!SampDeReferenceContext` at `0x180405b19`
- `SAMSRV!SampLookupContext` at `0x1804058ed`
- `SAMSRV!SampLookupContext` at `0x1804058ed`
- `SAMSRV!SampWriteGroupType` at `0x1804059fe`
- `SAMSRV!SampWriteGroupType` at `0x1804059fe`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405884`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405884`
- `SAMSRV!SampDecrementActiveThreads` at `0x1804059ae`
- `SAMSRV!SampDecrementActiveThreads` at `0x1804059ae`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x180405993`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x180405993`

## pseudocode

```c

```
