# Microsoft.Crm.ObjectModel.AppModuleService::GetUpdatedAppModuleDescriptor

- ea: `0x8ff50`
- end: `0x900d6`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::GetUpdatedAppModuleDescriptor`
- size: `390`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8ff20`
- `0x90790`

## callees

- `0x8ff50`
- `0x900e0`

## string_xrefs

- `0x8ffa5`: `descriptor`
- `0x8ffd3`: `descriptor`
- `0x90006`: `descriptor`
- `0x9005f`: `descriptor`
- `0x8ff58`: `AppModuleService.GetUpdatedAppModuleDescriptor(): START`
- `0x9001d`: `AppModuleService.GetUpdatedAppModuleDescriptor(): Existing AppModule with [appModuleId:{0}] not found.`
- `0x90040`: `AppModuleService.GetUpdatedAppModuleDescriptor(): [fetchPersistedDescriptor:{0}] [appId:{1}] [{2}:{3}]`
- `0x90087`: `AppModuleService.GetUpdatedAppModuleDescriptor(): Current appModuleDescriptor is null or empty.`
- `0x900ac`: `AppModuleService.GetUpdatedAppModuleDescriptor(): appModule is null`
- `0x900c4`: `AppModuleService.GetUpdatedAppModuleDescriptor(): END`

## pseudocode

```c

```

## disassembly

```asm
0x8ff50  ldarg.2
0x8ff51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8ff56  ldc.i4.s 0x47
0x8ff58  ldstr    aAppmoduleservi_9// "AppModuleService.GetUpdatedAppModuleDes"...
0x8ff5d  ldc.i4.0
0x8ff5e  newarr   [mscorlib]System.Object
0x8ff63  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8ff68  ldsfld   string [mscorlib]System.String::Empty
0x8ff6d  stloc.0
0x8ff6e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ff73  stloc.1
0x8ff74  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::.ctor()
0x8ff79  stloc.2
0x8ff7a  ldarg.1
0x8ff7b  brfalse  loc_900A4
0x8ff80  ldarg.1
0x8ff81  ldstr    aAppmoduleid// "appmoduleid"
0x8ff86  ldloca.s 1
0x8ff88  callvirt T0x2B0000EF
0x8ff8d  pop
0x8ff8e  ldarg.3
0x8ff8f  brfalse  loc_90038
0x8ff94  ldloc.1
0x8ff95  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ff9a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ff9f  brfalse  loc_90038
0x8ffa4  ldarg.1
0x8ffa5  ldstr    aDescriptor// "descriptor"
0x8ffaa  ldloca.s 0
0x8ffac  callvirt T0x2B0000F0
0x8ffb1  brtrue   loc_90038
0x8ffb6  ldstr    aAppmodule// "AppModule"
0x8ffbb  ldc.i4.3
0x8ffbc  newarr   [mscorlib]System.String
0x8ffc1  dup
0x8ffc2  ldc.i4.0
0x8ffc3  ldstr    aAppmoduleid// "appmoduleid"
0x8ffc8  stelem.ref
0x8ffc9  dup
0x8ffca  ldc.i4.1
0x8ffcb  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x8ffd0  stelem.ref
0x8ffd1  dup
0x8ffd2  ldc.i4.2
0x8ffd3  ldstr    aDescriptor// "descriptor"
0x8ffd8  stelem.ref
0x8ffd9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x8ffde  ldarg.2
0x8ffdf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8ffe4  stloc.3
0x8ffe5  ldarg.0
0x8ffe6  ldloc.1
0x8ffe7  ldstr    aAppmodule// "AppModule"
0x8ffec  ldarg.2
0x8ffed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fff2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x8fff7  ldloc.3
0x8fff8  ldarg.2
0x8fff9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fffe  stloc.s  4
0x90000  ldloc.s  4
0x90002  brfalse.s loc_90015
0x90004  ldloc.s  4
0x90006  ldstr    aDescriptor// "descriptor"
0x9000b  ldloca.s 0
0x9000d  callvirt T0x2B0000F0
0x90012  pop
0x90013  br.s     loc_9006E
0x90015  ldarg.2
0x90016  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9001b  ldc.i4.s 0x47
0x9001d  ldstr    aAppmoduleservi_10// "AppModuleService.GetUpdatedAppModuleDes"...
0x90022  ldc.i4.1
0x90023  newarr   [mscorlib]System.Object
0x90028  dup
0x90029  ldc.i4.0
0x9002a  ldloc.1
0x9002b  box      [mscorlib]System.Guid
0x90030  stelem.ref
0x90031  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90036  br.s     loc_9006E
0x90038  ldarg.2
0x90039  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9003e  ldc.i4.s 0x47
0x90040  ldstr    aAppmoduleservi_11// "AppModuleService.GetUpdatedAppModuleDes"...
0x90045  ldc.i4.4
0x90046  newarr   [mscorlib]System.Object
0x9004b  dup
0x9004c  ldc.i4.0
0x9004d  ldarg.3
0x9004e  box      [mscorlib]System.Boolean
0x90053  stelem.ref
0x90054  dup
0x90055  ldc.i4.1
0x90056  ldloc.1
0x90057  box      [mscorlib]System.Guid
0x9005c  stelem.ref
0x9005d  dup
0x9005e  ldc.i4.2
0x9005f  ldstr    aDescriptor// "descriptor"
0x90064  stelem.ref
0x90065  dup
0x90066  ldc.i4.3
0x90067  ldloc.0
0x90068  stelem.ref
0x90069  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9006e  ldloc.0
0x9006f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x90074  brtrue.s loc_9007F
0x90076  ldloc.0
0x90077  call     T0x2B000159
0x9007c  stloc.2
0x9007d  br.s     loc_90097
0x9007f  ldarg.2
0x90080  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90085  ldc.i4.s 0x47
0x90087  ldstr    aAppmoduleservi_12// "AppModuleService.GetUpdatedAppModuleDes"...
0x9008c  ldc.i4.0
0x9008d  newarr   [mscorlib]System.Object
0x90092  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90097  ldarg.0
0x90098  ldarg.1
0x90099  ldloc.2
0x9009a  ldc.i4.1
0x9009b  ldarg.2
0x9009c  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor Microsoft.Crm.ObjectModel.AppModuleService::populateDescriptorAppInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor appModuleDescriptor, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState appComponentState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x900a1  pop
0x900a2  br.s     loc_900BC
0x900a4  ldarg.2
0x900a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x900aa  ldc.i4.s 0x47
0x900ac  ldstr    aAppmoduleservi_13// "AppModuleService.GetUpdatedAppModuleDes"...
0x900b1  ldc.i4.0
0x900b2  newarr   [mscorlib]System.Object
0x900b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x900bc  ldarg.2
0x900bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x900c2  ldc.i4.s 0x47
0x900c4  ldstr    aAppmoduleservi_14// "AppModuleService.GetUpdatedAppModuleDes"...
0x900c9  ldc.i4.0
0x900ca  newarr   [mscorlib]System.Object
0x900cf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x900d4  ldloc.2
0x900d5  ret
```
