# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentLookupFilter::GetOrgData

- ea: `0xc9220`
- end: `0xc9b6c`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentLookupFilter::GetOrgData`
- size: `2380`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc8e30`

## callees

- `0x7c10`
- `0xc9220`
- `0xc9b70`
- `0xf4210`

## string_xrefs

- `0xc94e6`: `roletemplateid`
- `0xc950d`: `roletemplateid`
- `0xc938f`: `componentSubFilter`
- `0xc93a6`: `componentSubFilter`
- `0xc9652`: `componentSubFilter`
- `0xc9669`: `componentSubFilter`
- `0xc980f`: `componentSubFilter`
- `0xc9826`: `componentSubFilter`
- `0xc9959`: `componentSubFilter`
- `0xc9970`: `componentSubFilter`
- `0xc958c`: `fieldsecurityprofileid`

## pseudocode

```c

```

## disassembly

```asm
0xc9220  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::.ctor()
0xc9225  stloc.0
0xc9226  ldarg.1
0xc9227  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xc922c  stloc.s  8
0xc922e  br.s     loc_C9252
0xc9230  ldloc.s  8
0xc9232  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xc9237  stloc.s  9
0xc9239  ldloc.0
0xc923a  ldloc.s  9
0xc923c  ldstr    aObjectid// "objectid"
0xc9241  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc9246  unbox.any [mscorlib]System.Guid
0xc924b  ldloc.s  9
0xc924d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::Add(var<u1>, !!T0)
0xc9252  ldloc.s  8
0xc9254  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc9259  brtrue.s loc_C9230
0xc925b  leave.s  loc_C9269
0xc925d  ldloc.s  8
0xc925f  brfalse.s loc_C9268
0xc9261  ldloc.s  8
0xc9263  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc9268  endfinally
0xc9269  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xc926e  stloc.1
0xc926f  ldc.i4.0
0xc9270  stloc.s  0xA
0xc9272  br.s     loc_C92A4
0xc9274  ldarg.1
0xc9275  ldloc.s  0xA
0xc9277  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc927c  stloc.s  0xB
0xc927e  ldloc.1
0xc927f  ldloc.s  0xB
0xc9281  ldstr    aObjectid// "objectid"
0xc9286  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc928b  unbox.any [mscorlib]System.Guid
0xc9290  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xc9295  ldloc.s  0xA
0xc9297  ldc.i4   0x7D0
0xc929c  bgt.s    loc_C92AE
0xc929e  ldloc.s  0xA
0xc92a0  ldc.i4.1
0xc92a1  add
0xc92a2  stloc.s  0xA
0xc92a4  ldloc.s  0xA
0xc92a6  ldarg.1
0xc92a7  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xc92ac  blt.s    loc_C9274
0xc92ae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xc92b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xc92b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xc92bd  stloc.2
0xc92be  ldloc.2
0xc92bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc92c4  ldarg.2
0xc92c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xc92ca  stloc.3
0xc92cb  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0xc92d0  stloc.s  4
0xc92d2  ldloc.s  4
0xc92d4  ldloc.3
0xc92d5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xc92da  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0xc92df  ldc.i4.2
0xc92e0  newarr   [mscorlib]System.String
0xc92e5  dup
0xc92e6  ldc.i4.0
0xc92e7  ldloc.3
0xc92e8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xc92ed  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xc92f2  stelem.ref
0xc92f3  dup
0xc92f4  ldc.i4.1
0xc92f5  ldloc.3
0xc92f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xc92fb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xc9300  stelem.ref
0xc9301  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xc9306  stloc.s  5
0xc9308  ldloc.3
0xc9309  ldstr    aDescription// "description"
0xc930e  ldc.i4.1
0xc930f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc9314  brfalse.s loc_C9322
0xc9316  ldloc.s  5
0xc9318  ldstr    aDescription// "description"
0xc931d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xc9322  ldloc.3
0xc9323  ldstr    aIscustomizable// "iscustomizable"
0xc9328  ldc.i4.1
0xc9329  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc932e  brfalse.s loc_C933C
0xc9330  ldloc.s  5
0xc9332  ldstr    aIscustomizable// "iscustomizable"
0xc9337  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xc933c  ldloc.3
0xc933d  ldstr    aIsmanaged// "ismanaged"
0xc9342  ldc.i4.1
0xc9343  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc9348  brfalse.s loc_C9356
0xc934a  ldloc.s  5
0xc934c  ldstr    aIsmanaged// "ismanaged"
0xc9351  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xc9356  ldloc.1
0xc9357  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xc935c  ldc.i4.0
0xc935d  ble.s    loc_C937E
0xc935f  ldloc.s  4
0xc9361  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc9366  ldloc.3
0xc9367  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xc936c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xc9371  ldc.i4.s 9
0xc9373  ldloc.1
0xc9374  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0xc9379  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xc937e  ldc.i4.0
0xc937f  stloc.s  6
0xc9381  ldarg.0
0xc9382  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc9387  brfalse.s loc_C93BC
0xc9389  ldarg.0
0xc938a  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc938f  ldstr    aComponentsubfi// "componentSubFilter"
0xc9394  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc9399  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc939e  brtrue.s loc_C93BC
0xc93a0  ldarg.0
0xc93a1  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc93a6  ldstr    aComponentsubfi// "componentSubFilter"
0xc93ab  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc93b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc93b5  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xc93ba  stloc.s  6
0xc93bc  ldarg.2
0xc93bd  ldc.i4   0x125F
0xc93c2  bgt      loc_C944B
0xc93c7  ldarg.2
0xc93c8  ldc.i4   0x7DA
0xc93cd  bgt.s    loc_C940D
0xc93cf  ldarg.2
0xc93d0  ldc.i4   0x40C
0xc93d5  bgt.s    loc_C93F2
0xc93d7  ldarg.2
0xc93d8  ldc.i4   0x406
0xc93dd  beq      loc_C95AC
0xc93e2  ldarg.2
0xc93e3  ldc.i4   0x40C
0xc93e8  beq      loc_C94DA
0xc93ed  br       loc_C9932
0xc93f2  ldarg.2
0xc93f3  ldc.i4   0x4B0
0xc93f8  beq      loc_C9580
0xc93fd  ldarg.2
0xc93fe  ldc.i4   0x7DA
0xc9403  beq      loc_C95BC
0xc9408  br       loc_C9932
0xc940d  ldarg.2
0xc940e  ldc.i4   0x11FD
0xc9413  bgt.s    loc_C9430
0xc9415  ldarg.2
0xc9416  ldc.i4   0xBBD
0xc941b  beq      loc_C9992
0xc9420  ldarg.2
0xc9421  ldc.i4   0x11FD
0xc9426  beq      loc_C95F9
0xc942b  br       loc_C9932
0xc9430  ldarg.2
0xc9431  ldc.i4   0x1200
0xc9436  beq      loc_C95F9
0xc943b  ldarg.2
0xc943c  ldc.i4   0x125F
0xc9441  beq      loc_C9641
0xc9446  br       loc_C9932
0xc944b  ldarg.2
0xc944c  ldc.i4   0x2454
0xc9451  bgt.s    loc_C9491
0xc9453  ldarg.2
0xc9454  ldc.i4   0x238C
0xc9459  bgt.s    loc_C9476
0xc945b  ldarg.2
0xc945c  ldc.i4   0x1FF5
0xc9461  beq      loc_C9992
0xc9466  ldarg.2
0xc9467  ldc.i4   0x238C
0xc946c  beq      loc_C95BC
0xc9471  br       loc_C9932
0xc9476  ldarg.2
0xc9477  ldc.i4   0x2392
0xc947c  beq      loc_C95BC
0xc9481  ldarg.2
0xc9482  ldc.i4   0x2454
0xc9487  beq      loc_C9992
0xc948c  br       loc_C9932
0xc9491  ldarg.2
0xc9492  ldc.i4   0x24B8
0xc9497  bgt.s    loc_C94B4
0xc9499  ldarg.2
0xc949a  ldc.i4   0x2475
0xc949f  beq      loc_C97DB
0xc94a4  ldarg.2
0xc94a5  ldc.i4   0x24B8
0xc94aa  beq      loc_C9992
0xc94af  br       loc_C9932
0xc94b4  ldarg.2
0xc94b5  ldc.i4   0x2616
0xc94ba  beq      loc_C9992
0xc94bf  ldarg.2
0xc94c0  ldc.i4   0x2619
0xc94c5  beq      loc_C9927
0xc94ca  ldarg.2
0xc94cb  ldc.i4   0x268A
0xc94d0  beq      loc_C98DC
0xc94d5  br       loc_C9932
0xc94da  ldloc.s  4
0xc94dc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc94e1  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc94e6  ldstr    aRoletemplateid// "roletemplateid"
0xc94eb  ldc.i4.1
0xc94ec  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Utility.SolutionUtil::SupportUserRoleId
0xc94f1  box      [mscorlib]System.Guid
0xc94f6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc94fb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc9500  pop
0xc9501  ldloc.s  4
0xc9503  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc9508  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc950d  ldstr    aRoletemplateid// "roletemplateid"
0xc9512  ldc.i4.1
0xc9513  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Utility.SolutionUtil::SystemAdminRoleId
0xc9518  box      [mscorlib]System.Guid
0xc951d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc9522  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc9527  pop
0xc9528  ldloc.s  4
0xc952a  ldstr    aBusinessunit// "businessunit"
0xc952f  ldstr    aBusinessunitid// "businessunitid"
0xc9534  ldstr    aBusinessunitid// "businessunitid"
0xc9539  ldc.i4.0
0xc953a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0xc953f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xc9544  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc9549  ldstr    aParentbusiness// "parentbusinessunitid"
0xc954e  ldc.i4.s 0xC
0xc9550  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0xc9555  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc955a  pop
0xc955b  ldloc.s  6
0xc955d  ldc.i4.1
0xc955e  bne.un   loc_C9992
0xc9563  ldloc.3
0xc9564  ldstr    aIscustomizable// "iscustomizable"
0xc9569  ldc.i4.1
0xc956a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc956f  brfalse  loc_C9992
0xc9574  ldloc.s  4
0xc9576  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.SolutionFilter::AddCustomizableFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression)
0xc957b  br       loc_C9992
0xc9580  ldloc.s  4
0xc9582  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc9587  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc958c  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xc9591  ldc.i4.1
0xc9592  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SystemFieldSecurityProfileId
0xc9597  box      [mscorlib]System.Guid
0xc959c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc95a1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc95a6  pop
0xc95a7  br       loc_C9992
0xc95ac  ldarg.0
0xc95ad  ldloc.3
0xc95ae  ldloc.s  4
0xc95b0  ldloc.s  6
0xc95b2  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentLookupFilter::GetOrgDataSystemFormHelper(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata meta, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression expression, int32 subFilter)
0xc95b7  br       loc_C9992
0xc95bc  ldloc.s  4
0xc95be  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc95c3  ldstr    aIspersonal// "ispersonal"
0xc95c8  ldc.i4.1
0xc95c9  ldc.i4.1
0xc95ca  box      [mscorlib]System.Boolean
0xc95cf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xc95d4  ldloc.s  6
0xc95d6  ldc.i4.1
0xc95d7  bne.un   loc_C9992
0xc95dc  ldloc.3
0xc95dd  ldstr    aIscustomizable// "iscustomizable"
0xc95e2  ldc.i4.1
0xc95e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc95e8  brfalse  loc_C9992
0xc95ed  ldloc.s  4
0xc95ef  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.SolutionFilter::AddCustomizableFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression)
0xc95f4  br       loc_C9992
0xc95f9  ldloc.s  4
0xc95fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xc9600  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xc9605  ldstr    aIshidden_0// "ishidden"
  ... truncated ...
```
