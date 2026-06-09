# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetColumnNameForSpecifiedConversionRule

- ea: `0x32a0`
- end: `0x32e6`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetColumnNameForSpecifiedConversionRule`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x36b0`

## callees

- `0x32a0`

## string_xrefs

- `0x32b4`: `CreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x32a0  ldarg.1
0x32a1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::op_Implicit(string)
0x32a6  stloc.0
0x32a7  ldloc.0
0x32a8  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::CreatedByTimeZone
0x32ad  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::op_Equality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule)
0x32b2  brfalse.s loc_32BA
0x32b4  ldstr    aCreatedby_0// "CreatedBy"
0x32b9  ret
0x32ba  ldloc.0
0x32bb  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::LastUpdatedByTimeZone
0x32c0  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::op_Equality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule)
0x32c5  brfalse.s loc_32CD
0x32c7  ldstr    aModifiedby_0// "ModifiedBy"
0x32cc  ret
0x32cd  ldloc.0
0x32ce  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::OwnerTimeZone
0x32d3  call     bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::op_Equality(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule)
0x32d8  brfalse.s loc_32E0
0x32da  ldstr    aOwnerid_0// "OwnerId"
0x32df  ret
0x32e0  ldsfld   string [mscorlib]System.String::Empty
0x32e5  ret
```
