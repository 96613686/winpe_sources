# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivityToLead

- ea: `0x2340`
- end: `0x2412`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivityToLead`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2340`

## string_xrefs

- `0x2384`: `companyname`

## pseudocode

```c

```

## disassembly

```asm
0x2340  ldarg.s  7
0x2342  brfalse.s loc_2348
0x2344  ldarg.s  7
0x2346  br.s     loc_2351
0x2348  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x234d  stloc.s  5
0x234f  ldloc.s  5
0x2351  stloc.0
0x2352  ldstr    aLead// "lead"
0x2357  ldloc.0
0x2358  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x235d  stloc.1
0x235e  ldloc.1
0x235f  ldstr    aSubject// "subject"
0x2364  ldarg.2
0x2365  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x236a  ldloc.1
0x236b  ldstr    aFirstname// "firstname"
0x2370  ldarg.3
0x2371  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2376  ldloc.1
0x2377  ldstr    aLastname// "lastname"
0x237c  ldarg.s  4
0x237e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2383  ldloc.1
0x2384  ldstr    aCompanyname// "companyname"
0x2389  ldarg.s  5
0x238b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2390  ldloc.1
0x2391  ldstr    aEmailaddress1// "emailaddress1"
0x2396  ldarg.s  6
0x2398  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x239d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x23a2  stloc.2
0x23a3  ldloc.1
0x23a4  ldloc.2
0x23a5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create(valuetype [mscorlib]System.Guid)
0x23aa  ldloc.0
0x23ab  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23b0  ldarg.1
0x23b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x23b6  ldloca.s 3
0x23b8  ldarg.0
0x23b9  call     instance void [mscorlib]System.Guid::.ctor(string)
0x23be  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x23c3  ldloc.0
0x23c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23c9  dup
0x23ca  ldstr    aActivityid// "activityid"
0x23cf  ldloc.3
0x23d0  box      [mscorlib]System.Guid
0x23d5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x23da  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x23df  stloc.s  4
0x23e1  ldloc.s  4
0x23e3  ldloc.1
0x23e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x23e9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x23ee  ldloc.s  4
0x23f0  ldc.i4.4
0x23f1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x23f6  dup
0x23f7  ldstr    aRegardingobjec// "regardingobjectid"
0x23fc  ldloc.s  4
0x23fe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2403  ldc.i4.0
0x2404  ldloc.2
0x2405  ldloc.0
0x2406  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, bool, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x240b  ldloc.1
0x240c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x2411  ret
```
