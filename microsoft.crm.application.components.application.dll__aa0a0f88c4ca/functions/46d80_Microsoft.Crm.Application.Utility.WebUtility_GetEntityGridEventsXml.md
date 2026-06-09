# Microsoft.Crm.Application.Utility.WebUtility::GetEntityGridEventsXml

- ea: `0x46d80`
- end: `0x46e2d`
- name: `Microsoft.Crm.Application.Utility.WebUtility::GetEntityGridEventsXml`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x46d80`

## string_xrefs

- `0x46d88`: `eventsxml`
- `0x46dfc`: `eventsxml`
- `0x46e09`: `eventsxml`
- `0x46e18`: `eventsxml`
- `0x46d94`: `customcontroldefaultconfig`

## pseudocode

```c

```

## disassembly

```asm
0x46d80  ldc.i4.1
0x46d81  newarr   [mscorlib]System.String
0x46d86  dup
0x46d87  ldc.i4.0
0x46d88  ldstr    aEventsxml// "eventsxml"
0x46d8d  stelem.ref
0x46d8e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x46d93  stloc.0
0x46d94  ldstr    aCustomcontrold// "customcontroldefaultconfig"
0x46d99  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x46d9e  dup
0x46d9f  ldloc.0
0x46da0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x46da5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46daa  stloc.1
0x46dab  ldloc.1
0x46dac  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x46db1  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x46db6  ldc.i4.0
0x46db7  ldarg.0
0x46db8  box      [mscorlib]System.Int32
0x46dbd  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46dc2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46dc7  pop
0x46dc8  dup
0x46dc9  ldloc.1
0x46dca  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46dcf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x46dd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x46dd9  stloc.2
0x46dda  ldloc.2
0x46ddb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x46de0  brtrue.s loc_46DE4
0x46de2  ldnull
0x46de3  ret
0x46de4  ldloc.2
0x46de5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_Entities()
0x46dea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x46def  ldc.i4.0
0x46df0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x46df5  stloc.3
0x46df6  ldloc.3
0x46df7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x46dfc  ldstr    aEventsxml// "eventsxml"
0x46e01  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x46e06  brfalse.s loc_46E15
0x46e08  ldloc.3
0x46e09  ldstr    aEventsxml// "eventsxml"
0x46e0e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x46e13  brtrue.s loc_46E17
0x46e15  ldnull
0x46e16  ret
0x46e17  ldloc.3
0x46e18  ldstr    aEventsxml// "eventsxml"
0x46e1d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x46e22  castclass [mscorlib]System.String
0x46e27  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x46e2c  ret
```
