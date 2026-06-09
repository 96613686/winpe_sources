# Microsoft.Crm.Metadata.AttributeService::UpdateCurrencyRollupFieldToDecimal

- ea: `0x25140`
- end: `0x25215`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateCurrencyRollupFieldToDecimal`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x25140`
- `0x761b0`

## string_xrefs

- `0x25171`: `rollupPropertiesService`
- `0x251fe`: `AttributeService.UpdateCurrencyRollupFieldsToDecimal caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x25140  newobj   instance void <>c__DisplayClass184_0::.ctor()
0x25145  stloc.0
0x25146  ldloc.0
0x25147  ldarg.0
0x25148  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x2514d  ldloc.0
0x2514e  ldarg.2
0x2514f  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x25154  ldloc.0
0x25155  ldarg.1
0x25156  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService <>c__DisplayClass184_0::rollupPropertiesService
0x2515b  ldloc.0
0x2515c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x25161  ldstr    aAttributemetad// "attributeMetadata"
0x25166  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2516b  ldloc.0
0x2516c  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService <>c__DisplayClass184_0::rollupPropertiesService
0x25171  ldstr    aRollupproperti_0// "rollupPropertiesService"
0x25176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2517b  ldloc.0
0x2517c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x25181  ldstr    aContext// "context"
0x25186  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2518b  ldloc.0
0x2518c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x25191  ldstr    aAttributetypei// "attributetypeid"
0x25196  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2519b  unbox.any [mscorlib]System.Guid
0x251a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x251a5  ldstr    aMoney// "money"
0x251aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x251af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x251b4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x251b9  brfalse.s loc_251BC
0x251bb  ret
0x251bc  ldloc.0
0x251bd  ldsfld   string [mscorlib]System.String::Empty
0x251c2  stfld    string <>c__DisplayClass184_0::tableColumnName
0x251c7  ldloc.0
0x251c8  ldsfld   string [mscorlib]System.String::Empty
0x251cd  stfld    string <>c__DisplayClass184_0::tableName
0x251d2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x251d7  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupFieldUpdateToDecimalActivityType>::get_Instance()
0x251dc  ldloc.0
0x251dd  ldftn    instance void <>c__DisplayClass184_0::<UpdateCurrencyRollupFieldToDecimal>b__0()
0x251e3  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x251e8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x251ed  leave.s  loc_25214
0x251ef  stloc.1
0x251f0  ldloc.1
0x251f1  ldloc.0
0x251f2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x251f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x251fc  ldc.i4.s 0x19
0x251fe  ldstr    aAttributeservi_5// "AttributeService.UpdateCurrencyRollupFi"...
0x25203  ldc.i4.1
0x25204  newarr   [mscorlib]System.Object
0x25209  dup
0x2520a  ldc.i4.0
0x2520b  ldloc.1
0x2520c  stelem.ref
0x2520d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25212  leave.s  loc_25214
0x25214  ret
```
