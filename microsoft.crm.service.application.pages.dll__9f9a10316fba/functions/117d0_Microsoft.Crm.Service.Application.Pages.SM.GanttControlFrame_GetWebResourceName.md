# Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::GetWebResourceName

- ea: `0x117d0`
- end: `0x11859`
- name: `Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::GetWebResourceName`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11860`

## callees

- `0x117d0`

## pseudocode

```c

```

## disassembly

```asm
0x117d0  ldc.i4.1
0x117d1  newarr   [mscorlib]System.String
0x117d6  dup
0x117d7  ldc.i4.0
0x117d8  ldstr    aName// "name"
0x117dd  stelem.ref
0x117de  stloc.0
0x117df  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x117e4  stloc.1
0x117e5  ldloc.1
0x117e6  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x117eb  ldstr    aDisplayname// "displayname"
0x117f0  ldc.i4.0
0x117f1  ldarg.1
0x117f2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x117f7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x117fc  pop
0x117fd  ldstr    aWebresource// "webresource"
0x11802  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11807  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1180c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x11811  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x11816  ldloc.0
0x11817  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x1181c  stloc.2
0x1181d  dup
0x1181e  ldloc.2
0x1181f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x11824  dup
0x11825  ldloc.1
0x11826  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x1182b  ldc.i4.1
0x1182c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11831  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11836  stloc.3
0x11837  ldloc.3
0x11838  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1183d  ldc.i4.0
0x1183e  ble.s    loc_11857
0x11840  ldloc.3
0x11841  ldc.i4.0
0x11842  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x11847  ldstr    aName// "name"
0x1184c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x11851  callvirt instance string [mscorlib]System.Object::ToString()
0x11856  ret
0x11857  ldnull
0x11858  ret
```
