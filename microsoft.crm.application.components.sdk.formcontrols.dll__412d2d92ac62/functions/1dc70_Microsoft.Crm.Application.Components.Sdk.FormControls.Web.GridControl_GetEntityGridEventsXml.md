# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetEntityGridEventsXml

- ea: `0x1dc70`
- end: `0x1dd1d`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetEntityGridEventsXml`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d330`

## callees

- `0x1dc70`

## string_xrefs

- `0x1dc78`: `eventsxml`
- `0x1dcec`: `eventsxml`
- `0x1dcf9`: `eventsxml`
- `0x1dd08`: `eventsxml`
- `0x1dc84`: `customcontroldefaultconfig`

## pseudocode

```c

```

## disassembly

```asm
0x1dc70  ldc.i4.1
0x1dc71  newarr   [mscorlib]System.String
0x1dc76  dup
0x1dc77  ldc.i4.0
0x1dc78  ldstr    aEventsxml// "eventsxml"
0x1dc7d  stelem.ref
0x1dc7e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x1dc83  stloc.0
0x1dc84  ldstr    aCustomcontrold// "customcontroldefaultconfig"
0x1dc89  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1dc8e  dup
0x1dc8f  ldloc.0
0x1dc90  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x1dc95  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x1dc9a  stloc.1
0x1dc9b  ldloc.1
0x1dc9c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x1dca1  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1dca6  ldc.i4.0
0x1dca7  ldarg.0
0x1dca8  box      [mscorlib]System.Int32
0x1dcad  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x1dcb2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1dcb7  pop
0x1dcb8  dup
0x1dcb9  ldloc.1
0x1dcba  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x1dcbf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1dcc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1dcc9  stloc.2
0x1dcca  ldloc.2
0x1dccb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1dcd0  brtrue.s loc_1DCD4
0x1dcd2  ldnull
0x1dcd3  ret
0x1dcd4  ldloc.2
0x1dcd5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_Entities()
0x1dcda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1dcdf  ldc.i4.0
0x1dce0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1dce5  stloc.3
0x1dce6  ldloc.3
0x1dce7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1dcec  ldstr    aEventsxml// "eventsxml"
0x1dcf1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1dcf6  brfalse.s loc_1DD05
0x1dcf8  ldloc.3
0x1dcf9  ldstr    aEventsxml// "eventsxml"
0x1dcfe  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1dd03  brtrue.s loc_1DD07
0x1dd05  ldnull
0x1dd06  ret
0x1dd07  ldloc.3
0x1dd08  ldstr    aEventsxml// "eventsxml"
0x1dd0d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1dd12  castclass [mscorlib]System.String
0x1dd17  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1dd1c  ret
```
