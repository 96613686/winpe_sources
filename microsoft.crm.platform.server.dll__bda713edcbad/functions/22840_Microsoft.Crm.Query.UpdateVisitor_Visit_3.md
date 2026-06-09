# Microsoft.Crm.Query.UpdateVisitor::Visit_3

- ea: `0x22840`
- end: `0x22a85`
- name: `Microsoft.Crm.Query.UpdateVisitor::Visit_3`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x142a0`
- `0x184b0`
- `0x18520`
- `0x18540`
- `0x1a5e0`
- `0x1a660`
- `0x1a6c0`
- `0x1a700`
- `0x1a840`
- `0x1a920`
- `0x1aa60`
- `0x1aa70`
- `0x1bd70`
- `0x1bdd0`
- `0x1eff0`
- `0x1f010`
- `0x22840`
- `0x22ad0`
- `0x22b90`

## string_xrefs

- `0x22864`: `update [{0}] set `
- `0x22906`: `update [{0}] set `

## pseudocode

```c

```

## disassembly

```asm
0x22840  ldc.i4.0
0x22841  stloc.0
0x22842  ldc.i4.0
0x22843  stloc.1
0x22844  ldarg.1
0x22845  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2284a  ldloca.s 0
0x2284c  ldloca.s 1
0x2284e  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::Evaluate(bool& hasBaseAttributes, bool& hasExtensionAttributes)
0x22853  ldloc.0
0x22854  brfalse  loc_228E4
0x22859  ldarg.0
0x2285a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x2285f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22864  ldstr    aUpdate0Set// "update [{0}] set "
0x22869  ldc.i4.1
0x2286a  newarr   [mscorlib]System.Object
0x2286f  dup
0x22870  ldc.i4.0
0x22871  ldarg.1
0x22872  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x22877  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x2287c  stelem.ref
0x2287d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x22882  pop
0x22883  ldarg.0
0x22884  ldc.i4.0
0x22885  stfld    bool Microsoft.Crm.Query.UpdateVisitor::processExtensionAttributes
0x2288a  ldarg.1
0x2288b  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22890  ldarg.0
0x22891  callvirt instance void Microsoft.Crm.Query.Expression::GetSql(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x22896  ldarg.1
0x22897  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2289c  callvirt instance class Microsoft.Crm.Query.ConditionExpressionCollection Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x228a1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x228a6  brtrue.s loc_228BA
0x228a8  ldarg.1
0x228a9  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x228ae  callvirt instance class Microsoft.Crm.Query.FilterExpressionCollection Microsoft.Crm.Query.FilterExpression::get_Filters()
0x228b3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.FilterExpression>::get_Count()
0x228b8  brfalse.s loc_228D7
0x228ba  ldarg.0
0x228bb  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x228c0  ldstr    aWhere// " where "
0x228c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x228ca  pop
0x228cb  ldarg.1
0x228cc  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x228d1  ldarg.0
0x228d2  callvirt instance void Microsoft.Crm.Query.Expression::GetSql(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x228d7  ldarg.0
0x228d8  ldarg.1
0x228d9  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x228de  ldc.i4.1
0x228df  call     instance void Microsoft.Crm.Query.UpdateVisitor::EnsureAllConditionsOnSameTable(class Microsoft.Crm.Query.FilterExpression filter, bool shouldBeOnPrimaryTable)
0x228e4  ldloc.1
0x228e5  brfalse  loc_229FD
0x228ea  ldloc.0
0x228eb  brfalse.s loc_228FB
0x228ed  ldarg.0
0x228ee  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x228f3  ldc.i4.s 0x3B
0x228f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x228fa  pop
0x228fb  ldarg.0
0x228fc  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22901  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22906  ldstr    aUpdate0Set// "update [{0}] set "
0x2290b  ldc.i4.1
0x2290c  newarr   [mscorlib]System.Object
0x22911  dup
0x22912  ldc.i4.0
0x22913  ldarg.1
0x22914  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x22919  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExtensionTableName()
0x2291e  stelem.ref
0x2291f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x22924  pop
0x22925  ldarg.0
0x22926  ldc.i4.1
0x22927  stfld    bool Microsoft.Crm.Query.UpdateVisitor::processExtensionAttributes
0x2292c  ldarg.1
0x2292d  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22932  ldarg.0
0x22933  callvirt instance void Microsoft.Crm.Query.Expression::GetSql(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x22938  ldarg.1
0x22939  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x2293e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSolutionAware()
0x22943  brfalse.s loc_2296D
0x22945  ldarg.0
0x22946  ldarg.1
0x22947  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2294c  call     instance bool Microsoft.Crm.Query.ExpressionVisitor::IncludesRowGuidCondition(class Microsoft.Crm.Query.FilterExpression filter)
0x22951  brtrue.s loc_2296D
0x22953  ldarg.0
0x22954  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22959  ldarg.0
0x2295a  ldarg.1
0x2295b  call     instance string Microsoft.Crm.Query.ExpressionVisitor::BuildSolutionAwareJoin(class Microsoft.Crm.Query.EntityExpression entity)
0x22960  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22965  pop
0x22966  ldarg.0
0x22967  ldc.i4.1
0x22968  stfld    bool Microsoft.Crm.Query.UpdateVisitor::addingSolutionAwareJoin
0x2296d  ldarg.1
0x2296e  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x22973  callvirt instance class Microsoft.Crm.Query.ConditionExpressionCollection Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x22978  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x2297d  brtrue.s loc_22991
0x2297f  ldarg.1
0x22980  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x22985  callvirt instance class Microsoft.Crm.Query.FilterExpressionCollection Microsoft.Crm.Query.FilterExpression::get_Filters()
0x2298a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.FilterExpression>::get_Count()
0x2298f  brfalse.s loc_229D0
0x22991  ldarg.0
0x22992  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22997  ldstr    aWhere// " where "
0x2299c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x229a1  pop
0x229a2  ldarg.1
0x229a3  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x229a8  ldarg.0
0x229a9  callvirt instance void Microsoft.Crm.Query.Expression::GetSql(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x229ae  ldarg.0
0x229af  ldfld    bool Microsoft.Crm.Query.UpdateVisitor::addingSolutionAwareJoin
0x229b4  brfalse.s loc_229F0
0x229b6  ldarg.0
0x229b7  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x229bc  ldarg.0
0x229bd  ldarg.1
0x229be  ldstr    aAnd// "and"
0x229c3  call     instance string Microsoft.Crm.Query.ExpressionVisitor::BuildSolutionAwareJoinCondition(class Microsoft.Crm.Query.EntityExpression entity, string prefix)
0x229c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x229cd  pop
0x229ce  br.s     loc_229F0
0x229d0  ldarg.0
0x229d1  ldfld    bool Microsoft.Crm.Query.UpdateVisitor::addingSolutionAwareJoin
0x229d6  brfalse.s loc_229F0
0x229d8  ldarg.0
0x229d9  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x229de  ldarg.0
0x229df  ldarg.1
0x229e0  ldstr    aWhere_0// "where"
0x229e5  call     instance string Microsoft.Crm.Query.ExpressionVisitor::BuildSolutionAwareJoinCondition(class Microsoft.Crm.Query.EntityExpression entity, string prefix)
0x229ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x229ef  pop
0x229f0  ldarg.0
0x229f1  ldarg.1
0x229f2  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x229f7  ldc.i4.0
0x229f8  call     instance void Microsoft.Crm.Query.UpdateVisitor::EnsureAllConditionsOnSameTable(class Microsoft.Crm.Query.FilterExpression filter, bool shouldBeOnPrimaryTable)
0x229fd  ldarg.0
0x229fe  ldfld    bool Microsoft.Crm.Query.UpdateVisitor::hasLocalizableAttributes
0x22a03  brfalse.s loc_22A5F
0x22a05  ldarg.1
0x22a06  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x22a0b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizableAttributeCount()
0x22a10  ldc.i4.0
0x22a11  ble.s    loc_22A5F
0x22a13  ldarg.1
0x22a14  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x22a19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UsesBusinessDataLabelTable()
0x22a1e  call     class Microsoft.Crm.Query.ILocalizedLabelQueryClauseBuilder Microsoft.Crm.Query.LocalizedLabelQueryClauseBuilder::GetInstance(bool usesBusinessDataLabelTable)
0x22a23  ldarg.0
0x22a24  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.UpdateVisitor::parameterManager
0x22a29  ldarg.1
0x22a2a  ldarg.1
0x22a2b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Query.ExpressionVisitor::GetPrimaryKeyAttributeValueFromCondition(class Microsoft.Crm.Query.EntityExpression entity)
0x22a30  ldarg.0
0x22a31  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.UpdateVisitor::executionContext
0x22a36  callvirt instance string Microsoft.Crm.Query.ILocalizedLabelQueryClauseBuilder::GetLocalizedLabelCreateOrUpdateSql(class Microsoft.Crm.Query.QueryParameterManager parameterManager, class Microsoft.Crm.Query.EntityExpression entityExpression, valuetype [mscorlib]System.Guid primaryKeyAttributeValue, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x22a3b  stloc.2
0x22a3c  ldloc.2
0x22a3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22a42  brtrue.s loc_22A52
0x22a44  ldarg.0
0x22a45  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22a4a  ldc.i4.s 0x3B
0x22a4c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x22a51  pop
0x22a52  ldarg.0
0x22a53  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22a58  ldloc.2
0x22a59  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22a5e  pop
0x22a5f  ldarg.0
0x22a60  ldfld    bool Microsoft.Crm.Query.UpdateVisitor::hasEncryptedAttributes
0x22a65  brfalse.s loc_22A84
0x22a67  ldarg.0
0x22a68  ldarg.1
0x22a69  call     instance void Microsoft.Crm.Query.UpdateVisitor::VerifyEncryptedEntityDoesNotUpdatePrimaryKey(class Microsoft.Crm.Query.EntityExpression entity)
0x22a6e  call     class Microsoft.Crm.Query.QuerySqlCellLevelEncryption Microsoft.Crm.Query.QuerySqlCellLevelEncryption::Instance()
0x22a73  ldarg.0
0x22a74  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.UpdateVisitor::sqlString
0x22a79  ldarg.1
0x22a7a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.Expression::get_OrganizationId()
0x22a7f  callvirt instance void Microsoft.Crm.Query.QuerySqlCellLevelEncryption::AddOpenAndCloseEncryptionChainCommand(class [mscorlib]System.Text.StringBuilder sqlString, valuetype [mscorlib]System.Guid organizationId)
0x22a84  ret
```
