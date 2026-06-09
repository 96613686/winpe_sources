# Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::.cctor

- ea: `0x7af0`
- end: `0x7b2d`
- name: `Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x7aff`: `CreatedByTimeZone`
- `0x7b1d`: `LastUpdatedByTimeZone`

## pseudocode

```c

```

## disassembly

```asm
0x7af0  ldstr    aSpecifictimezo// "SpecificTimeZone"
0x7af5  call     T0x2B00000C
0x7afa  stsfld   class Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::SpecificTimeZone
0x7aff  ldstr    aCreatedbytimez// "CreatedByTimeZone"
0x7b04  call     T0x2B00000C
0x7b09  stsfld   class Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::CreatedByTimeZone
0x7b0e  ldstr    aOwnertimezone// "OwnerTimeZone"
0x7b13  call     T0x2B00000C
0x7b18  stsfld   class Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::OwnerTimeZone
0x7b1d  ldstr    aLastupdatedbyt// "LastUpdatedByTimeZone"
0x7b22  call     T0x2B00000C
0x7b27  stsfld   class Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::LastUpdatedByTimeZone
0x7b2c  ret
```
