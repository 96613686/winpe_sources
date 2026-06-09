# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::LogCreateEntity

- ea: `0x2910`
- end: `0x29f1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::LogCreateEntity`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## string_xrefs

- `0x29d5`: `CreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2910  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::.ctor()
0x2915  stloc.0
0x2916  ldloc.0
0x2917  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x291c  dup
0x291d  ldstr    aIsauditenabled// "IsAuditEnabled"
0x2922  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x2927  dup
0x2928  ldarg.0
0x2929  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_IsAuditEnabled()
0x292e  stloc.2
0x292f  ldloca.s 2
0x2931  call     instance string [mscorlib]System.Boolean::ToString()
0x2936  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x293b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x2940  ldloc.0
0x2941  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x2946  dup
0x2947  ldstr    aIsretrieveaudi// "IsRetrieveAuditEnabled"
0x294c  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x2951  dup
0x2952  ldarg.0
0x2953  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_IsRetrieveAuditEnabled()
0x2958  stloc.2
0x2959  ldloca.s 2
0x295b  call     instance string [mscorlib]System.Boolean::ToString()
0x2960  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x2965  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x296a  ldloc.0
0x296b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x2970  dup
0x2971  ldstr    aIsretrievemult// "IsRetrieveMultipleAuditEnabled"
0x2976  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x297b  dup
0x297c  ldarg.0
0x297d  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_IsRetrieveMultipleAuditEnabled()
0x2982  stloc.2
0x2983  ldloca.s 2
0x2985  call     instance string [mscorlib]System.Boolean::ToString()
0x298a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x298f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x2994  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::.ctor()
0x2999  stloc.1
0x299a  ldloc.1
0x299b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x29a5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_SystemUserId(valuetype [mscorlib]System.Guid)
0x29aa  ldloc.1
0x29ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x29b5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x29ba  ldloc.1
0x29bb  ldloc.0
0x29bc  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Fields(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>)
0x29c1  ldloc.1
0x29c2  ldarg.0
0x29c3  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_LogicalName()
0x29c8  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityName(string)
0x29cd  ldloc.1
0x29ce  ldarg.1
0x29cf  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityId(valuetype [mscorlib]System.Guid)
0x29d4  ldloc.1
0x29d5  ldstr    aCreateentity// "CreateEntity"
0x29da  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Operation(string)
0x29df  ldloc.1
0x29e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::get_OrganizationId()
0x29e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x29ea  ldloc.1
0x29eb  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLogging::LogRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData)
0x29f0  ret
```
