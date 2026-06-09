# Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::SetActivitiesDateRangeFilter

- ea: `0x59680`
- end: `0x597ff`
- name: `Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::SetActivitiesDateRangeFilter`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x59310`

## callees

- `0x59680`

## string_xrefs

- `0x59700`: `scheduledstart`
- `0x59721`: `scheduledstart`
- `0x597c1`: `scheduledstart`
- `0x59760`: `scheduledend`
- `0x59782`: `scheduledend`
- `0x597e3`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x59680  ldarga.s 0
0x59682  ldstr    aS// "s"
0x59687  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5968c  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x59691  stloc.0
0x59692  ldarga.s 1
0x59694  ldstr    aS// "s"
0x59699  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5969e  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x596a3  stloc.1
0x596a4  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x596a9  stloc.2
0x596aa  ldarg.2
0x596ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x596b0  brtrue.s loc_596C7
0x596b2  ldarg.2
0x596b3  ldloc.2
0x596b4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x596b9  ldarg.2
0x596ba  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x596bf  ldc.i4.1
0x596c0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x596c5  br.s     loc_596E0
0x596c7  ldloc.2
0x596c8  ldc.i4.1
0x596c9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x596ce  ldarg.2
0x596cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x596d4  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x596d9  ldloc.2
0x596da  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x596df  pop
0x596e0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x596e5  stloc.3
0x596e6  ldloc.3
0x596e7  ldc.i4.0
0x596e8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x596ed  ldloc.2
0x596ee  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x596f3  ldloc.3
0x596f4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x596f9  pop
0x596fa  ldloc.3
0x596fb  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x59700  ldstr    aScheduledstart// "scheduledstart"
0x59705  ldc.i4.4
0x59706  ldc.i4.1
0x59707  newarr   [mscorlib]System.Object
0x5970c  dup
0x5970d  ldc.i4.0
0x5970e  ldloc.0
0x5970f  stelem.ref
0x59710  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59715  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5971a  pop
0x5971b  ldloc.3
0x5971c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x59721  ldstr    aScheduledstart// "scheduledstart"
0x59726  ldc.i4.3
0x59727  ldc.i4.1
0x59728  newarr   [mscorlib]System.Object
0x5972d  dup
0x5972e  ldc.i4.0
0x5972f  ldloc.1
0x59730  stelem.ref
0x59731  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59736  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5973b  pop
0x5973c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x59741  stloc.s  4
0x59743  ldloc.s  4
0x59745  ldc.i4.0
0x59746  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x5974b  ldloc.2
0x5974c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x59751  ldloc.s  4
0x59753  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x59758  pop
0x59759  ldloc.s  4
0x5975b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x59760  ldstr    aScheduledend// "scheduledend"
0x59765  ldc.i4.4
0x59766  ldc.i4.1
0x59767  newarr   [mscorlib]System.Object
0x5976c  dup
0x5976d  ldc.i4.0
0x5976e  ldloc.0
0x5976f  stelem.ref
0x59770  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59775  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5977a  pop
0x5977b  ldloc.s  4
0x5977d  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x59782  ldstr    aScheduledend// "scheduledend"
0x59787  ldc.i4.3
0x59788  ldc.i4.1
0x59789  newarr   [mscorlib]System.Object
0x5978e  dup
0x5978f  ldc.i4.0
0x59790  ldloc.1
0x59791  stelem.ref
0x59792  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59797  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5979c  pop
0x5979d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x597a2  stloc.s  5
0x597a4  ldloc.s  5
0x597a6  ldc.i4.0
0x597a7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x597ac  ldloc.2
0x597ad  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x597b2  ldloc.s  5
0x597b4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x597b9  pop
0x597ba  ldloc.s  5
0x597bc  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x597c1  ldstr    aScheduledstart// "scheduledstart"
0x597c6  ldc.i4.3
0x597c7  ldc.i4.1
0x597c8  newarr   [mscorlib]System.Object
0x597cd  dup
0x597ce  ldc.i4.0
0x597cf  ldloc.1
0x597d0  stelem.ref
0x597d1  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x597d6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x597db  pop
0x597dc  ldloc.s  5
0x597de  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x597e3  ldstr    aScheduledend// "scheduledend"
0x597e8  ldc.i4.4
0x597e9  ldc.i4.1
0x597ea  newarr   [mscorlib]System.Object
0x597ef  dup
0x597f0  ldc.i4.0
0x597f1  ldloc.0
0x597f2  stelem.ref
0x597f3  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x597f8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x597fd  pop
0x597fe  ret
```
