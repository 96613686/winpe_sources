# Microsoft.Crm.Common.Application.Platform.Queue::RetrieveQueueByObject

- ea: `0x48d0`
- end: `0x4979`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::RetrieveQueueByObject`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x48d0`
- `0x6930`

## pseudocode

```c

```

## disassembly

```asm
0x48d0  ldstr    aQueue// "queue"
0x48d5  ldarg.3
0x48d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x48db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x48e0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x48e5  stloc.0
0x48e6  ldloc.0
0x48e7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x48ec  ldarg.2
0x48ed  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x48f2  ldarg.0
0x48f3  ldarg.1
0x48f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x48f9  ldloc.0
0x48fa  ldarg.3
0x48fb  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::.ctor(valuetype [mscorlib]System.Guid itemId, string itemType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query2, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4900  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x4905  stloc.1
0x4906  ldloc.1
0x4907  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x490c  ldc.i4.1
0x490d  bne.un.s loc_4917
0x490f  ldloc.1
0x4910  ldc.i4.0
0x4911  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x4916  ret
0x4917  ldloc.1
0x4918  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x491d  brtrue.s loc_494C
0x491f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4924  ldstr    aQueueWasNotFou// "Queue was not found for {0} with ID {1}"...
0x4929  ldc.i4.2
0x492a  newarr   [mscorlib]System.Object
0x492f  dup
0x4930  ldc.i4.0
0x4931  ldarg.1
0x4932  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x4937  stelem.ref
0x4938  dup
0x4939  ldc.i4.1
0x493a  ldarg.0
0x493b  box      [mscorlib]System.Guid
0x4940  stelem.ref
0x4941  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4946  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x494b  throw
0x494c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4951  ldstr    aMoreThanOneQue// "More than one Queue was found for {0} w"...
0x4956  ldc.i4.2
0x4957  newarr   [mscorlib]System.Object
0x495c  dup
0x495d  ldc.i4.0
0x495e  ldarg.1
0x495f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x4964  stelem.ref
0x4965  dup
0x4966  ldc.i4.1
0x4967  ldarg.0
0x4968  box      [mscorlib]System.Guid
0x496d  stelem.ref
0x496e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4973  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4978  throw
```
