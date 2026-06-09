# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddFromClause_0

- ea: `0x24ef0`
- end: `0x25389`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddFromClause_0`
- size: `1177`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x2b9a0`

## callees

- `0x14730`
- `0x18590`
- `0x1b0c0`
- `0x1b0d0`
- `0x1b0e0`
- `0x1b100`
- `0x1b220`
- `0x1b240`
- `0x1b260`
- `0x23c10`
- `0x23c50`
- `0x23e80`
- `0x23f60`
- `0x23fb0`
- `0x23fc0`
- `0x23fd0`
- `0x24ef0`
- `0x26600`
- `0x26890`
- `0x26d40`
- `0x27530`
- `0x27e60`
- `0x27f40`
- `0x28400`
- `0x28820`
- `0x288a0`
- `0x29bd0`
- `0x2a850`
- `0x2b4a0`
- `0x882a0`
- `0x882c0`
- `0x883f0`
- `0x88450`
- `0x88520`
- `0x88540`
- `0x88610`

## string_xrefs

- `0x24ef1`: `linkEntity`
- `0x25147`: `While generating the FROM clause for a link entity the current predicate builder is not a LinkEntityPredicateBuilder`

## pseudocode

```c

```

## disassembly

```asm
0x24ef0  ldarg.1
0x24ef1  ldstr    aLinkentity// "linkEntity"
0x24ef6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x24efb  ldarg.0
0x24efc  ldarg.1
0x24efd  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x24f02  callvirt instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::ValidateTableAliasIsUniqueAndAddToTableAliasCollection(string tableAlias)
0x24f07  ldarg.1
0x24f08  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.LinkEntityExpression::get_ParentLinkEntity()
0x24f0d  brfalse.s loc_24F1D
0x24f0f  ldarg.1
0x24f10  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.LinkEntityExpression::get_ParentLinkEntity()
0x24f15  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x24f1a  stloc.0
0x24f1b  br.s     loc_24F29
0x24f1d  ldarg.1
0x24f1e  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.LinkEntityExpression::get_ParentEntity()
0x24f23  callvirt instance string Microsoft.Crm.Query.EntityExpression::get_TableAlias()
0x24f28  stloc.0
0x24f29  ldnull
0x24f2a  stloc.1
0x24f2b  ldsfld   string [mscorlib]System.String::Empty
0x24f30  stloc.2
0x24f31  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x24f36  stloc.3
0x24f37  ldarg.1
0x24f38  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x24f3d  ldarg.0
0x24f3e  callvirt instance valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeRetrieveBehavior()
0x24f43  ldarg.0
0x24f44  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x24f49  call     bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::NeedFieldLevelSecurityJoin(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior behavior, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x24f4e  brfalse.s loc_24FBD
0x24f50  ldarg.1
0x24f51  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x24f56  ldloc.0
0x24f57  ldarg.0
0x24f58  ldarg.1
0x24f59  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x24f5e  ldloc.0
0x24f5f  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetReferenceToAttributeWithTableAlias(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, string tableAlias)
0x24f64  ldc.i4.0
0x24f65  ldloca.s 1
0x24f67  ldarg.0
0x24f68  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x24f6d  ldarg.0
0x24f6e  callvirt instance valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeRetrieveBehavior()
0x24f73  ldarg.0
0x24f74  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_inLinkEntity
0x24f79  ldarg.0
0x24f7a  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_processingCondition
0x24f7f  ldarg.0
0x24f80  ldfld    class Microsoft.Crm.Query.AttributeExpression Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_currentAttributeExpression
0x24f85  ldarg.0
0x24f86  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x24f8b  ldarg.0
0x24f8c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CallerId()
0x24f91  ldarg.0
0x24f92  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x24f97  ldc.i4.0
0x24f98  call     string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetFieldLevelSecuritySql(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, string tableAlias, string attributeReferenceSql, valuetype Microsoft.Crm.Query.SecuredAttributeJoinType joinType, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo>& securedJoinInfo, class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior behavior, bool inLinkEntity, bool processingCondition, class Microsoft.Crm.Query.AttributeExpression currentAttributeExpression, class Microsoft.Crm.Query.QueryParameterManager parameters, valuetype [mscorlib]System.Guid callerId, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper securedAttributesWrapper, [opt] bool useScalarFunction)
0x24f9d  stloc.2
0x24f9e  ldloc.1
0x24f9f  brfalse  loc_25084
0x24fa4  ldloc.1
0x24fa5  ldloc.0
0x24fa6  ldarg.0
0x24fa7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CallerId()
0x24fac  ldloc.3
0x24fad  ldarg.0
0x24fae  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x24fb3  call     void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AppendSecuredAttributeJoins(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo> joinInfoDictionary, string tableAlias, valuetype [mscorlib]System.Guid callerId, class [mscorlib]System.Text.StringBuilder sb, class Microsoft.Crm.Query.QueryParameterManager queryParameters)
0x24fb8  br       loc_25084
0x24fbd  ldarg.1
0x24fbe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x24fc3  ldarg.0
0x24fc4  callvirt instance valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeRetrieveBehavior()
0x24fc9  ldarg.0
0x24fca  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x24fcf  call     bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::NeedFieldLevelSecurityJoin(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior behavior, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x24fd4  brfalse.s loc_25030
0x24fd6  ldarg.1
0x24fd7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x24fdc  ldarg.1
0x24fdd  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x24fe2  ldarg.0
0x24fe3  ldarg.1
0x24fe4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x24fe9  ldarg.1
0x24fea  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x24fef  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetReferenceToAttributeWithTableAlias(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, string tableAlias)
0x24ff4  ldc.i4.0
0x24ff5  ldloca.s 1
0x24ff7  ldarg.0
0x24ff8  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x24ffd  ldarg.0
0x24ffe  callvirt instance valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeRetrieveBehavior()
0x25003  ldarg.0
0x25004  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_inLinkEntity
0x25009  ldarg.0
0x2500a  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_processingCondition
0x2500f  ldarg.0
0x25010  ldfld    class Microsoft.Crm.Query.AttributeExpression Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_currentAttributeExpression
0x25015  ldarg.0
0x25016  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x2501b  ldarg.0
0x2501c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CallerId()
0x25021  ldarg.0
0x25022  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x25027  ldc.i4.1
0x25028  call     string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetFieldLevelSecuritySql(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, string tableAlias, string attributeReferenceSql, valuetype Microsoft.Crm.Query.SecuredAttributeJoinType joinType, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo>& securedJoinInfo, class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior behavior, bool inLinkEntity, bool processingCondition, class Microsoft.Crm.Query.AttributeExpression currentAttributeExpression, class Microsoft.Crm.Query.QueryParameterManager parameters, valuetype [mscorlib]System.Guid callerId, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper securedAttributesWrapper, [opt] bool useScalarFunction)
0x2502d  stloc.2
0x2502e  br.s     loc_25084
0x25030  ldarg.1
0x25031  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x25036  stloc.s  9
0x25038  ldarg.1
0x25039  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x2503e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x25043  ldstr    aOwningteam// "owningteam"
0x25048  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2504d  brtrue.s loc_25066
0x2504f  ldarg.1
0x25050  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x25055  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x2505a  ldstr    aOwninguser// "owninguser"
0x2505f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25064  brfalse.s loc_2507A
0x25066  ldloc.s  9
0x25068  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x2506d  ldstr    aOwnerid// "ownerid"
0x25072  ldc.i4.1
0x25073  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x25078  stloc.s  9
0x2507a  ldarg.0
0x2507b  ldloc.s  9
0x2507d  ldloc.0
0x2507e  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetReferenceToAttributeWithTableAlias(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, string tableAlias)
0x25083  stloc.2
0x25084  ldloc.3
0x25085  ldstr    a0_1// " {0} "
0x2508a  ldarg.1
0x2508b  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator Microsoft.Crm.Query.LinkEntityExpression::get_JoinOperator()
0x25090  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.QuerySerializationUtil::JoinOperatorToSqlString(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x25095  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x2509a  pop
0x2509b  ldloc.3
0x2509c  ldstr    a0As0// "{{0}} as \"{0}\""
0x250a1  ldarg.1
0x250a2  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x250a7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x250ac  pop
0x250ad  ldarg.0
0x250ae  ldloc.3
0x250af  callvirt instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::InjectTableHints(class [mscorlib]System.Text.StringBuilder sql)
0x250b4  ldarg.1
0x250b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x250ba  stloc.s  4
0x250bc  ldarg.1
0x250bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x250c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x250c7  ldstr    aOwningteam// "owningteam"
0x250cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x250d1  brtrue.s loc_250EA
0x250d3  ldarg.1
0x250d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x250d9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x250de  ldstr    aOwninguser// "owninguser"
0x250e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x250e8  brfalse.s loc_250FE
0x250ea  ldloc.s  4
0x250ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x250f1  ldstr    aOwnerid// "ownerid"
0x250f6  ldc.i4.1
0x250f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x250fc  stloc.s  4
0x250fe  ldloc.3
0x250ff  ldstr    aOn0123// " on ({0} {1} \"{2}\".{3}"
0x25104  ldc.i4.4
0x25105  newarr   [mscorlib]System.Object
0x2510a  dup
0x2510b  ldc.i4.0
0x2510c  ldloc.2
0x2510d  stelem.ref
0x2510e  dup
0x2510f  ldc.i4.1
0x25110  ldarg.1
0x25111  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Crm.Query.LinkEntityExpression::get_ConditionOperator()
0x25116  call     string Microsoft.Crm.Query.ConditionExpression::ConditionOperatorToSqlString(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator)
0x2511b  stelem.ref
0x2511c  dup
0x2511d  ldc.i4.2
0x2511e  ldarg.1
0x2511f  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x25124  stelem.ref
0x25125  dup
0x25126  ldc.i4.3
0x25127  ldarg.0
0x25128  ldloc.s  4
0x2512a  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetAttributeColumnName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x2512f  stelem.ref
0x25130  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x25135  pop
0x25136  ldarg.0
0x25137  call     instance class PredicateBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CurrentPredicateBuilder()
0x2513c  isinst   LinkEntityPredicateBuilder
0x25141  stloc.s  5
0x25143  ldloc.s  5
0x25145  brtrue.s loc_25157
0x25147  ldstr    aWhileGeneratin// "While generating the FROM clause for a "...
0x2514c  ldc.i4   0x80040216
0x25151  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x25156  throw
0x25157  ldloc.s  5
0x25159  callvirt instance string PredicateBuilder::GetSql()
0x2515e  stloc.s  6
0x25160  ldarg.0
0x25161  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_inLinkEntity
0x25166  brfalse.s loc_25192
0x25168  ldarg.0
0x25169  ldfld    int32 Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_localizedLabelJoinCounter
0x2516e  ldc.i4.m1
0x2516f  ble.s    loc_2517A
0x25171  ldloc.s  5
0x25173  callvirt instance bool PredicateBuilder::get_isLocalizedLabelPredicate()
0x25178  brtrue.s loc_2518F
0x2517a  ldarg.0
0x2517b  ldfld    int32 Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_multiSelectJoinCounter
0x25180  ldc.i4.m1
0x25181  ble.s    loc_2518C
0x25183  ldloc.s  5
0x25185  callvirt instance bool PredicateBuilder::get_isMultiSelectPredicate()
0x2518a  br.s     loc_25193
0x2518c  ldc.i4.0
0x2518d  br.s     loc_25193
0x2518f  ldc.i4.1
0x25190  br.s     loc_25193
0x25192  ldc.i4.0
0x25193  stloc.s  7
0x25195  ldloc.s  7
0x25197  brtrue.s loc_251B8
0x25199  ldloc.s  6
0x2519b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x251a0  ldc.i4.0
0x251a1  ble.s    loc_251B8
0x251a3  ldloc.3
0x251a4  ldstr    aAnd0// " and {0}"
0x251a9  ldloc.s  6
0x251ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x251b0  pop
0x251b1  ldloc.s  5
0x251b3  callvirt instance void LinkEntityPredicateBuilder::Reset()
0x251b8  ldloc.3
0x251b9  ldstr    asc_CC192// ")"
0x251be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x251c3  pop
0x251c4  ldarg.0
0x251c5  ldarg.1
0x251c6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetLinkEntityEntityMetadata(class Microsoft.Crm.Query.LinkEntityExpression linkEntity)
0x251cb  stloc.s  8
0x251cd  ldarg.0
0x251ce  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>> Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_MuiAttributes()
0x251d3  ldarg.1
0x251d4  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x251d9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>>::ContainsKey(var<u1>)
0x251de  brfalse.s loc_25258
0x251e0  ldarg.0
0x251e1  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_databaseQueryTarget
0x251e6  brfalse.s loc_25258
0x251e8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x251ed  stloc.s  0xA
0x251ef  ldarg.0
0x251f0  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>> Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_MuiAttributes()
0x251f5  ldarg.1
0x251f6  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x251fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>>::get_Item(void)
0x25200  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>::GetEnumerator()
0x25205  stloc.s  0xB
0x25207  br.s     loc_25236
0x25209  ldloca.s 0xB
0x2520b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>::get_Current()
0x25210  stloc.s  0xC
0x25212  ldloc.s  0xA
0x25214  ldarg.0
0x25215  ldloc.s  8
0x25217  ldloc.s  0xC
0x25219  ldarg.1
0x2521a  callvirt instance string Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x2521f  ldloc.s  8
0x25221  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x25226  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2522b  callvirt instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetLocalizedLabelJoinClause(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class Microsoft.Crm.Query.LocalizedLabelJoinInfo ll, string tableAlias, string entityPrimaryKey)
0x25230  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x25235  pop
0x25236  ldloca.s 0xB
0x25238  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>::MoveNext()
0x2523d  brtrue.s loc_25209
0x2523f  leave.s  loc_2524F
0x25241  ldloca.s 0xB
0x25243  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.LocalizedLabelJoinInfo>
  ... truncated ...
```
