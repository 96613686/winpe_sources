# Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.CreateResource

- ea: `0x7ef0`
- end: `0x7fa8`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.CreateResource`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7ef0`

## string_xrefs

- `0x7f8a`: `' is not a complex type.`

## pseudocode

```c

```

## disassembly

```asm
0x7ef0  ldnull
0x7ef1  stloc.0
0x7ef2  ldarg.0
0x7ef3  ldfld    class [System.Data.Services]System.Data.Services.Providers.IDataServiceMetadataProvider Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::_metadata
0x7ef8  ldarg.2
0x7ef9  ldloca.s 1
0x7efb  callvirt instance bool [System.Data.Services]System.Data.Services.Providers.IDataServiceMetadataProvider::TryResolveResourceType(string, class [System.Data.Services]System.Data.Services.Providers.ResourceType&)
0x7f00  brtrue.s loc_7F18
0x7f02  ldstr    aUnknownResourc// "Unknown resource type '"
0x7f07  ldarg.2
0x7f08  ldstr    asc_38B9C// "'."
0x7f0d  call     string [mscorlib]System.String::Concat(string, string, string)
0x7f12  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7f17  throw
0x7f18  ldarg.1
0x7f19  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7f1e  brtrue.s loc_7F7B
0x7f20  ldloc.1
0x7f21  callvirt instance valuetype [System.Data.Services]System.Data.Services.Providers.ResourceTypeKind [System.Data.Services]System.Data.Services.Providers.ResourceType::get_ResourceTypeKind()
0x7f26  brfalse.s loc_7F3E
0x7f28  ldstr    aTheSpecifiedRe// "The specified resource type '"
0x7f2d  ldarg.2
0x7f2e  ldstr    aIsNotAnEntityT// "' is not an entity type, but resource s"...
0x7f33  call     string [mscorlib]System.String::Concat(string, string, string)
0x7f38  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7f3d  throw
0x7f3e  ldloc.1
0x7f3f  callvirt instance object [System.Data.Services]System.Data.Services.Providers.ResourceType::get_CustomState()
0x7f44  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x7f49  dup
0x7f4a  ldstr    aEntitymetadata// "entityMetadata"
0x7f4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7f54  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7f59  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x7f5e  stloc.2
0x7f5f  ldloc.2
0x7f60  ldc.i4.1
0x7f61  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::.ctor(var<u1>)
0x7f66  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_EntityState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>)
0x7f6b  ldarg.0
0x7f6c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::_context
0x7f71  ldloc.2
0x7f72  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddObject(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x7f77  ldloc.2
0x7f78  stloc.0
0x7f79  br.s     loc_7FA6
0x7f7b  ldloc.1
0x7f7c  callvirt instance valuetype [System.Data.Services]System.Data.Services.Providers.ResourceTypeKind [System.Data.Services]System.Data.Services.Providers.ResourceType::get_ResourceTypeKind()
0x7f81  ldc.i4.1
0x7f82  beq.s    loc_7F9A
0x7f84  ldstr    aTheSpecifiedRe// "The specified resource type '"
0x7f89  ldarg.2
0x7f8a  ldstr    aIsNotAComplexT// "' is not a complex type."
0x7f8f  call     string [mscorlib]System.String::Concat(string, string, string)
0x7f94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7f99  throw
0x7f9a  ldloc.1
0x7f9b  callvirt instance class [mscorlib]System.Type [System.Data.Services]System.Data.Services.Providers.ResourceType::get_InstanceType()
0x7fa0  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x7fa5  stloc.0
0x7fa6  ldloc.0
0x7fa7  ret
```
