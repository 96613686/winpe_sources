# Microsoft.Crm.Common.Application.Platform.Email::CreateForward

- ea: `0x3890`
- end: `0x39bb`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateForward`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x31a0`
- `0x34b0`
- `0x3890`
- `0x39c0`
- `0x3a30`
- `0x3ad0`

## string_xrefs

- `0x38ba`: `<columnset><column>subject</column><column>description</column><column>compressed</column><column>actualend</column><column>from</column><column>to</column><column>cc</column></columnset>`

## pseudocode

```c

```

## disassembly

```asm
0x3890  ldarg.0
0x3891  ldarg.1
0x3892  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateForwardInternal(string forwardFromEmailId)
0x3897  ldstr    aEmail// "email"
0x389c  ldarg.0
0x389d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x38a2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x38a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38ac  newobj   instance void Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x38b1  stloc.0
0x38b2  ldloc.0
0x38b3  ldarg.1
0x38b4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x38b9  ldloc.0
0x38ba  ldstr    aColumnsetColum// "<columnset><column>subject</column><col"...
0x38bf  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x38c4  ldarg.0
0x38c5  ldstr    aDescription// "description"
0x38ca  ldloc.0
0x38cb  callvirt instance string Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody()
0x38d0  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x38d5  ldarg.0
0x38d6  ldarg.1
0x38d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x38dc  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetParentActivityIdAndClearCorrelationFields(valuetype [mscorlib]System.Guid parentId)
0x38e1  ldarg.0
0x38e2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::CreateAndRetrieve()
0x38e7  ldarg.0
0x38e8  ldstr    aActivityid// "activityid"
0x38ed  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x38f2  unbox.any [mscorlib]System.Guid
0x38f7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x38fc  stloc.1
0x38fd  ldc.i4.1
0x38fe  newarr   [mscorlib]System.String
0x3903  dup
0x3904  ldc.i4.0
0x3905  ldstr    aActivitymimeat// "activitymimeattachmentid"
0x390a  stelem.ref
0x390b  stloc.2
0x390c  ldstr    aActivitymimeat_0// "activitymimeattachment"
0x3911  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x3916  dup
0x3917  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x391c  ldloc.2
0x391d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x3922  dup
0x3923  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x3928  ldc.i4.0
0x3929  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x392e  dup
0x392f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x3934  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x3939  ldstr    aActivityid// "activityid"
0x393e  ldc.i4.0
0x393f  ldarg.1
0x3940  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x3945  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x394a  pop
0x394b  dup
0x394c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x3951  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x3956  ldstr    aObjecttypecode// "objecttypecode"
0x395b  ldc.i4.0
0x395c  ldc.i4   0x106A
0x3961  box      [mscorlib]System.Int32
0x3966  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x396b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3970  pop
0x3971  ldarg.0
0x3972  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3977  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x397c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3981  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x3986  stloc.3
0x3987  br.s     loc_39A6
0x3989  ldloc.3
0x398a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x398f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x3994  ldloc.1
0x3995  ldarg.0
0x3996  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x399b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x39a0  call     string Microsoft.Crm.Common.Application.Platform.Email::CopyAttachment(string copyId, string activityId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x39a5  pop
0x39a6  ldloc.3
0x39a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x39ac  brtrue.s loc_3989
0x39ae  leave.s  loc_39BA
0x39b0  ldloc.3
0x39b1  brfalse.s loc_39B9
0x39b3  ldloc.3
0x39b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39b9  endfinally
0x39ba  ret
```
