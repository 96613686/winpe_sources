# Microsoft.Crm.Application.Platform.ServiceCommands.InitializeFromCommand::Execute

- ea: `0x90480`
- end: `0x90556`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.InitializeFromCommand::Execute`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5a460`

## callees

- `0xbd0`
- `0xc30`
- `0x106f0`
- `0x10a10`
- `0x475c0`
- `0x5b850`
- `0x5bdd0`
- `0x5c2f0`
- `0x5ea70`
- `0x90480`
- `0x90d80`
- `0x90e30`
- `0x90e70`

## string_xrefs

- `0x904ea`: `InitializeFromCommand: No mapping exists to entity of type {0} from entity of type {1}.`
- `0x90517`: `InitializeFromCommand: Created entity of type {0} from entity of type {1} and id {2}.`
- `0x90538`: `InitializeFromCommand: EntityXml of newly created entity: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x90480  ldsfld   string [mscorlib]System.String::Empty
0x90485  stloc.1
0x90486  ldsfld   string [mscorlib]System.String::Empty
0x9048b  stloc.2
0x9048c  ldarg.0
0x9048d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_XrmRequestInternal()
0x90492  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromRequest
0x90497  dup
0x90498  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromRequest::get_TargetEntityName()
0x9049d  stloc.2
0x9049e  dup
0x9049f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromRequest::get_EntityMoniker()
0x904a4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x904a9  stloc.1
0x904aa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromRequest::get_EntityMoniker()
0x904af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x904b4  stloc.3
0x904b5  ldarg.0
0x904b6  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x904bb  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromResponse
0x904c0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InitializeFromResponse::get_Entity()
0x904c5  ldarg.0
0x904c6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x904cb  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity platformEntity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x904d0  stloc.0
0x904d1  leave.s  loc_90509
0x904d3  ldarg.0
0x904d4  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x904d9  newobj   instance void Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x904de  callvirt instance int32 Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x904e3  ldc.i4   0x80040E01
0x904e8  bne.un.s loc_90507
0x904ea  ldstr    aInitializefrom_0// "InitializeFromCommand: No mapping exist"...
0x904ef  ldc.i4.2
0x904f0  newarr   [mscorlib]System.Object
0x904f5  dup
0x904f6  ldc.i4.0
0x904f7  ldloc.2
0x904f8  stelem.ref
0x904f9  dup
0x904fa  ldc.i4.1
0x904fb  ldloc.1
0x904fc  stelem.ref
0x904fd  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x90502  ldnull
0x90503  stloc.s  4
0x90505  leave.s  loc_90553
0x90507  rethrow
0x90509  ldloc.0
0x9050a  ldc.i4.1
0x9050b  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool value)
0x90510  ldloc.0
0x90511  ldc.i4.1
0x90512  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_DisableCurrencyDefaulting(bool value)
0x90517  ldstr    aInitializefrom_1// "InitializeFromCommand: Created entity o"...
0x9051c  ldc.i4.3
0x9051d  newarr   [mscorlib]System.Object
0x90522  dup
0x90523  ldc.i4.0
0x90524  ldloc.2
0x90525  stelem.ref
0x90526  dup
0x90527  ldc.i4.1
0x90528  ldloc.1
0x90529  stelem.ref
0x9052a  dup
0x9052b  ldc.i4.2
0x9052c  ldloc.3
0x9052d  call     string Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid guid)
0x90532  stelem.ref
0x90533  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x90538  ldstr    aInitializefrom_2// "InitializeFromCommand: EntityXml of new"...
0x9053d  ldc.i4.1
0x9053e  newarr   [mscorlib]System.Object
0x90543  dup
0x90544  ldc.i4.0
0x90545  ldloc.0
0x90546  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x9054b  stelem.ref
0x9054c  call     void Microsoft.Crm.Util::TraceVerbose(string message, object[] args)
0x90551  ldloc.0
0x90552  ret
0x90553  ldloc.s  4
0x90555  ret
```
