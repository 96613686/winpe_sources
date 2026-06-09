# Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyEntity

- ea: `0x3320`
- end: `0x33a5`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyEntity`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x30f0`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldarg.1
0x3321  ldarg.0
0x3322  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x3327  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x332c  ldarg.1
0x332d  ldarg.0
0x332e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x3333  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x3338  ldarg.1
0x3339  ldarg.0
0x333a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x333f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_EntityState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>)
0x3344  ldarg.1
0x3345  ldarg.0
0x3346  callvirt instance class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_ExtensionData()
0x334b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_ExtensionData(class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject)
0x3350  ldarg.1
0x3351  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3356  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Clear()
0x335b  ldarg.0
0x335c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3361  ldarg.1
0x3362  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3367  call     T0x2B000007
0x336c  ldarg.1
0x336d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x3372  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::Clear()
0x3377  ldarg.0
0x3378  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x337d  ldarg.1
0x337e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x3383  call     T0x2B000009
0x3388  ldarg.1
0x3389  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x338e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::Clear()
0x3393  ldarg.0
0x3394  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x3399  ldarg.1
0x339a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x339f  call     T0x2B00000A
0x33a4  ret
```
