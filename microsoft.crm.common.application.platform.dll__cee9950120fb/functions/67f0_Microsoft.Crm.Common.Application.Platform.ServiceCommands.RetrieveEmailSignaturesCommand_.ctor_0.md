# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::.ctor_0

- ea: `0x67f0`
- end: `0x68c3`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::.ctor_0`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3140`
- `0x67e0`

## callees

- `0x67f0`
- `0x68e0`

## string_xrefs

- `0x682f`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x67f0  ldarg.0
0x67f1  ldstr    aEmailsignature// "emailsignature"
0x67f6  ldarg.s  4
0x67f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x67fd  ldarg.s  4
0x67ff  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6804  ldstr    aEmailsignature// "emailsignature"
0x6809  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x680e  stloc.0
0x680f  ldc.i4.4
0x6810  newarr   [mscorlib]System.String
0x6815  dup
0x6816  ldc.i4.0
0x6817  ldstr    aEmailsignature_0// "emailsignatureid"
0x681c  stelem.ref
0x681d  dup
0x681e  ldc.i4.1
0x681f  ldstr    aTitle// "title"
0x6824  stelem.ref
0x6825  dup
0x6826  ldc.i4.2
0x6827  ldstr    aDescription// "description"
0x682c  stelem.ref
0x682d  dup
0x682e  ldc.i4.3
0x682f  ldstr    aCreatedon// "createdon"
0x6834  stelem.ref
0x6835  stloc.1
0x6836  ldloc.0
0x6837  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x683c  ldloc.1
0x683d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x6842  ldarg.3
0x6843  callvirt instance string [mscorlib]System.String::ToLower()
0x6848  ldstr    aQueue// "queue"
0x684d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6852  brfalse.s loc_6863
0x6854  ldarga.s 2
0x6856  ldarg.0
0x6857  ldarg.3
0x6858  ldarg.2
0x6859  call     instance string Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::GetOwnerId(string entityName, valuetype [mscorlib]System.Guid entityId)
0x685e  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6863  ldloc.0
0x6864  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x6869  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x686e  ldstr    aOwnerid// "ownerid"
0x6873  ldc.i4.0
0x6874  ldarga.s 2
0x6876  constrained. [mscorlib]System.Guid
0x687c  callvirt instance string [mscorlib]System.Object::ToString()
0x6881  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6886  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x688b  ldarg.1
0x688c  ldc.i4.m1
0x688d  beq.s    loc_68BB
0x688f  ldloc.0
0x6890  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x6895  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x689a  ldstr    aLanguagecode// "languagecode"
0x689f  ldc.i4.0
0x68a0  ldarga.s 1
0x68a2  ldstr    aD// "D"
0x68a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68ac  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x68b1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x68b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x68bb  ldarg.0
0x68bc  ldloc.0
0x68bd  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::CreateQueryRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x68c2  ret
```
