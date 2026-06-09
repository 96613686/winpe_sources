# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate

- ea: `0x12b30`
- end: `0x12c51`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10bc0`

## callees

- `0x12110`
- `0x12520`
- `0x12b30`
- `0x12c60`
- `0x12ca0`

## pseudocode

```c

```

## disassembly

```asm
0x12b30  ldarg.3
0x12b31  ldstr    aSlaid// "slaid"
0x12b36  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetEntityReferenceId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName)
0x12b3b  stloc.0
0x12b3c  ldarg.s  4
0x12b3e  ldstr    aSlaid// "slaid"
0x12b43  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetEntityReferenceId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName)
0x12b48  stloc.1
0x12b49  ldloca.s 1
0x12b4b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12b50  brfalse.s loc_12B84
0x12b52  ldloc.1
0x12b53  stloc.s  4
0x12b55  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12b5a  stloc.s  5
0x12b5c  ldloca.s 4
0x12b5e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12b63  brtrue.s loc_12B68
0x12b65  ldc.i4.1
0x12b66  br.s     loc_12B85
0x12b68  ldloca.s 4
0x12b6a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12b6f  brtrue.s loc_12B74
0x12b71  ldc.i4.0
0x12b72  br.s     loc_12B85
0x12b74  ldloca.s 4
0x12b76  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x12b7b  ldloc.s  5
0x12b7d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12b82  br.s     loc_12B85
0x12b84  ldc.i4.0
0x12b85  ldloca.s 0
0x12b87  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12b8c  brfalse.s loc_12BC8
0x12b8e  ldloc.1
0x12b8f  stloc.s  4
0x12b91  ldloc.0
0x12b92  stloc.s  6
0x12b94  ldloca.s 4
0x12b96  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12b9b  ldloca.s 6
0x12b9d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12ba2  beq.s    loc_12BA7
0x12ba4  ldc.i4.1
0x12ba5  br.s     loc_12BC9
0x12ba7  ldloca.s 4
0x12ba9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12bae  brtrue.s loc_12BB3
0x12bb0  ldc.i4.0
0x12bb1  br.s     loc_12BC9
0x12bb3  ldloca.s 4
0x12bb5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x12bba  ldloca.s 6
0x12bbc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x12bc1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12bc6  br.s     loc_12BC9
0x12bc8  ldc.i4.0
0x12bc9  stloc.2
0x12bca  ldnull
0x12bcb  stloc.3
0x12bcc  brfalse.s loc_12C44
0x12bce  ldloc.2
0x12bcf  brtrue.s loc_12C44
0x12bd1  ldarg.1
0x12bd2  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x12bd7  stloc.s  7
0x12bd9  ldloc.s  7
0x12bdb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12be0  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CanAutoApplySLA(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12be5  ldc.i4.0
0x12be6  stloc.s  8
0x12be8  brfalse.s loc_12C13
0x12bea  ldarg.3
0x12beb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12bf0  ldstr    aEntitlementid// "entitlementid"
0x12bf5  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12bfa  brtrue.s loc_12C16
0x12bfc  ldarg.3
0x12bfd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12c02  ldstr    aCustomerid// "customerid"
0x12c07  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12c0c  brtrue.s loc_12C16
0x12c0e  ldc.i4.1
0x12c0f  stloc.s  8
0x12c11  br.s     loc_12C16
0x12c13  ldc.i4.1
0x12c14  stloc.s  8
0x12c16  ldloc.s  8
0x12c18  brfalse.s loc_12C44
0x12c1a  ldloc.1
0x12c1b  ldloc.s  7
0x12c1d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12c22  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::RetriveSLA(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> SLAId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12c27  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x12c2c  stloc.3
0x12c2d  ldloc.3
0x12c2e  brfalse.s loc_12C44
0x12c30  ldloc.3
0x12c31  ldstr    aStatecode// "statecode"
0x12c36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12c3b  unbox.any [mscorlib]System.Int32
0x12c40  brtrue.s loc_12C44
0x12c42  ldnull
0x12c43  stloc.3
0x12c44  ldarg.0
0x12c45  ldarg.1
0x12c46  ldarg.2
0x12c47  ldloc.3
0x12c48  ldarg.3
0x12c49  ldarg.s  4
0x12c4b  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement newEntitlement, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity)
0x12c50  ret
```
