# SampDsSetInformationAlias(void *,_DSNAME *,ulong,SAMP_CALL_MAPPING *,SAMP_ATTRIBUTE_MAPPING *)

- ea: `0x1804051d8`
- end: `0x18040549d`
- name: `?SampDsSetInformationAlias@@YAJPEAXPEAU_DSNAME@@KPEAUSAMP_CALL_MAPPING@@PEAUSAMP_ATTRIBUTE_MAPPING@@@Z`
- size: `709`
- prototype: `int(void *, struct _DSNAME *, unsigned int, struct SAMP_CALL_MAPPING *, struct SAMP_ATTRIBUTE_MAPPING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180403960`

## callees

- `0x1804051d8`
- `0x180406908`
- `0x180406944`
- `0x180406c08`
- `0x1804076fc`

## import_xrefs

- `SAMSRV!SampChangeAliasAccountName` at `0x1804053b2`
- `SAMSRV!SampChangeAliasAccountName` at `0x1804053b2`
- `SAMSRV!SampAuditAccountNameChange` at `0x18040546a`
- `SAMSRV!SampAuditAccountNameChange` at `0x18040546a`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405384`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405415`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405384`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x180405415`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x1804053fd`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x1804053fd`
- `SAMSRV!SampFreeUnicodeString` at `0x180405421`
- `SAMSRV!SampFreeUnicodeString` at `0x18040547a`
- `SAMSRV!SampFreeUnicodeString` at `0x180405421`
- `SAMSRV!SampFreeUnicodeString` at `0x18040547a`
- `SAMSRV!SampDeReferenceContext` at `0x180405430`
- `SAMSRV!SampDeReferenceContext` at `0x180405444`
- `SAMSRV!SampDeReferenceContext` at `0x180405430`
- `SAMSRV!SampDeReferenceContext` at `0x180405444`
- `SAMSRV!SampLookupContext` at `0x180405287`
- `SAMSRV!SampLookupContext` at `0x180405287`
- `SAMSRV!SampWriteGroupType` at `0x180405326`
- `SAMSRV!SampWriteGroupType` at `0x180405326`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405221`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405221`
- `SAMSRV!SampDecrementActiveThreads` at `0x180405470`
- `SAMSRV!SampDecrementActiveThreads` at `0x180405470`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x180405455`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x180405455`

## pseudocode

```c

```
