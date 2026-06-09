# Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.GetResource

- ea: `0x7fd0`
- end: `0x8107`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::System.Data.Services.IUpdatable.GetResource`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7040`
- `0x7fd0`
- `0x88f0`
- `0x8ac0`

## string_xrefs

- `0x801c`: `Invalid Uri specified. The query '{0}' must refer to a single resource`
- `0x806e`: `Invalid Uri specified. The query '{0}' must refer to a single resource`
- `0x80ab`: `Invalid Uri specified.  The query '{0}' does not refer to a resource of type {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x7fd0  ldarg.1
0x7fd1  callvirt instance class [System.Core]System.Linq.IQueryProvider [System.Core]System.Linq.IQueryable::get_Provider()
0x7fd6  isinst   Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider
0x7fdb  stloc.0
0x7fdc  ldloc.0
0x7fdd  brfalse  loc_8105
0x7fe2  ldloc.0
0x7fe3  ldarg.1
0x7fe4  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.IQueryable::get_Expression()
0x7fe9  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::TranslateExpression(class [System.Core]System.Linq.Expressions.Expression expression)
0x7fee  stloc.1
0x7fef  ldloc.0
0x7ff0  ldloc.1
0x7ff1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Linq.QueryProvider::Translate(class [System.Core]System.Linq.Expressions.Expression)
0x7ff6  stloc.2
0x7ff7  ldloc.2
0x7ff8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7ffd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x8002  brfalse.s loc_8017
0x8004  ldloc.2
0x8005  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x800a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x800f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::get_Count()
0x8014  ldc.i4.1
0x8015  beq.s    loc_803B
0x8017  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x801c  ldstr    aInvalidUriSpec// "Invalid Uri specified. The query '{0}' "...
0x8021  ldc.i4.1
0x8022  newarr   [mscorlib]System.Object
0x8027  dup
0x8028  ldc.i4.0
0x8029  ldarg.1
0x802a  callvirt instance string [mscorlib]System.Object::ToString()
0x802f  stelem.ref
0x8030  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8035  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x803a  throw
0x803b  ldloc.2
0x803c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x8041  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x8046  ldc.i4.0
0x8047  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::get_Item(!!T0)
0x804c  stloc.3
0x804d  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationDataService::GetOrganizationContext()
0x8052  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8057  ldloc.2
0x8058  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x805d  ldc.i4.1
0x805e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8063  stloc.s  4
0x8065  ldloc.s  4
0x8067  brtrue.s loc_808D
0x8069  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x806e  ldstr    aInvalidUriSpec// "Invalid Uri specified. The query '{0}' "...
0x8073  ldc.i4.1
0x8074  newarr   [mscorlib]System.Object
0x8079  dup
0x807a  ldc.i4.0
0x807b  ldarg.1
0x807c  callvirt instance string [mscorlib]System.Object::ToString()
0x8081  stelem.ref
0x8082  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8087  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x808c  throw
0x808d  ldloc.3
0x808e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_AttributeName()
0x8093  ldloc.s  4
0x8095  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x809a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x809f  call     bool [mscorlib]System.String::Equals(string, string)
0x80a4  brtrue.s loc_80CE
0x80a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80ab  ldstr    aInvalidUriSpec_0// "Invalid Uri specified.  The query '{0}'"...
0x80b0  ldc.i4.2
0x80b1  newarr   [mscorlib]System.Object
0x80b6  dup
0x80b7  ldc.i4.0
0x80b8  ldarg.1
0x80b9  callvirt instance string [mscorlib]System.Object::ToString()
0x80be  stelem.ref
0x80bf  dup
0x80c0  ldc.i4.1
0x80c1  ldarg.2
0x80c2  stelem.ref
0x80c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x80cd  throw
0x80ce  ldloc.3
0x80cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x80d4  ldc.i4.0
0x80d5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Item(!!T0)
0x80da  unbox.any [mscorlib]System.Guid
0x80df  stloc.s  5
0x80e1  ldloc.s  4
0x80e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x80e8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x80ed  stloc.s  6
0x80ef  ldloc.s  6
0x80f1  ldloc.s  5
0x80f3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x80f8  ldarg.0
0x80f9  ldloc.s  6
0x80fb  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OrganizationDataServiceUpdateProvider::EnsureAttached(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x8100  stloc.s  6
0x8102  ldloc.s  6
0x8104  ret
0x8105  ldnull
0x8106  ret
```
