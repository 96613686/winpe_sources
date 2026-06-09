# Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::DoesComponentExists

- ea: `0x144d0`
- end: `0x14818`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::DoesComponentExists`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12d60`
- `0x144d0`
- `0x14820`
- `0x14840`
- `0x14880`
- `0x148d0`
- `0x14940`

## string_xrefs

- `0x1453a`: `RibbonCommand`
- `0x1454e`: `ribboncommandid`
- `0x14791`: `ribboncommandid`
- `0x1455f`: `command`
- `0x145a9`: `contextgroupxml`

## pseudocode

```c

```

## disassembly

```asm
0x144d0  ldarg.1
0x144d1  ldstr    aType_0// "type"
0x144d6  ldc.i4.0
0x144d7  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetIntegerAttribute(class [System.Xml]System.Xml.XmlNode, string, int32)
0x144dc  stloc.0
0x144dd  ldarg.1
0x144de  ldstr    aSchemaname_1// "schemaName"
0x144e3  ldnull
0x144e4  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x144e9  stloc.1
0x144ea  ldnull
0x144eb  stloc.s  5
0x144ed  ldnull
0x144ee  stloc.s  6
0x144f0  ldloc.1
0x144f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x144f6  brfalse.s loc_144FA
0x144f8  ldc.i4.0
0x144f9  ret
0x144fa  ldloc.0
0x144fb  ldc.i4.s 0x30
0x144fd  sub
0x144fe  switch   loc_14528, loc_14572, loc_145BC, loc_146BF, loc_14657, loc_146BF, loc_146BF, loc_145F1
0x14523  br       loc_146BF
0x14528  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonCommandService::.ctor()
0x1452d  stloc.s  5
0x1452f  ldarg.0
0x14530  ldloc.1
0x14531  ldloca.s 2
0x14533  ldloca.s 4
0x14535  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::ParseTwoPartSchemaName(string schemaName, [out] string& part1, [out] string& part2)
0x1453a  ldstr    aRibboncommand// "RibbonCommand"
0x1453f  ldarg.3
0x14540  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14545  stloc.s  6
0x14547  ldloc.s  6
0x14549  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1454e  ldstr    aRibboncommandi// "ribboncommandid"
0x14553  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14558  ldloc.s  6
0x1455a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1455f  ldstr    aCommand// "command"
0x14564  ldc.i4.0
0x14565  ldloc.s  4
0x14567  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1456c  pop
0x1456d  br       loc_146DB
0x14572  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonContextGroupService::.ctor()
0x14577  stloc.s  5
0x14579  ldarg.0
0x1457a  ldloc.1
0x1457b  ldloca.s 2
0x1457d  ldloca.s 4
0x1457f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::ParseTwoPartSchemaName(string schemaName, [out] string& part1, [out] string& part2)
0x14584  ldstr    aRibboncontextg// "RibbonContextGroup"
0x14589  ldarg.3
0x1458a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1458f  stloc.s  6
0x14591  ldloc.s  6
0x14593  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14598  ldstr    aRibboncontextg_0// "ribboncontextgroupid"
0x1459d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x145a2  ldloc.s  6
0x145a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x145a9  ldstr    aContextgroupxm// "contextgroupxml"
0x145ae  ldc.i4.0
0x145af  ldloc.s  4
0x145b1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x145b6  pop
0x145b7  br       loc_146DB
0x145bc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonCustomizationService::.ctor()
0x145c1  stloc.s  5
0x145c3  ldarg.0
0x145c4  ldloc.1
0x145c5  ldloca.s 2
0x145c7  ldloca.s 4
0x145c9  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::ParseTwoPartSchemaName(string schemaName, [out] string& part1, [out] string& part2)
0x145ce  ldstr    aRibboncustomiz// "RibbonCustomization"
0x145d3  ldarg.3
0x145d4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x145d9  stloc.s  6
0x145db  ldloc.s  6
0x145dd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x145e2  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x145e7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x145ec  br       loc_146DB
0x145f1  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonDiffService::.ctor()
0x145f6  stloc.s  5
0x145f8  ldarg.0
0x145f9  ldloc.1
0x145fa  ldloca.s 2
0x145fc  ldloca.s 3
0x145fe  ldloca.s 4
0x14600  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::ParseThreePartSchemaName(string schemaName, [out] string& part1, [out] string& part2, [out] string& part3)
0x14605  ldstr    aRibbondiff// "RibbonDiff"
0x1460a  ldarg.3
0x1460b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14610  stloc.s  6
0x14612  ldloc.s  6
0x14614  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14619  ldstr    aRibbondiffid// "ribbondiffid"
0x1461e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14623  ldloc.s  6
0x14625  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1462a  ldstr    aDiffid// "diffid"
0x1462f  ldc.i4.0
0x14630  ldloc.s  4
0x14632  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14637  pop
0x14638  ldloc.s  6
0x1463a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1463f  ldstr    aDifftype// "difftype"
0x14644  ldc.i4.8
0x14645  ldarg.0
0x14646  ldloc.3
0x14647  call     instance int32[] Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::GetDiffTypeFromNodeName(string diffType)
0x1464c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x14651  pop
0x14652  br       loc_146DB
0x14657  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonRuleService::.ctor()
0x1465c  stloc.s  5
0x1465e  ldarg.0
0x1465f  ldloc.1
0x14660  ldloca.s 2
0x14662  ldloca.s 3
0x14664  ldloca.s 4
0x14666  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::ParseThreePartSchemaName(string schemaName, [out] string& part1, [out] string& part2, [out] string& part3)
0x1466b  ldstr    aRibbonrule// "RibbonRule"
0x14670  ldarg.3
0x14671  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14676  stloc.s  6
0x14678  ldloc.s  6
0x1467a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1467f  ldstr    aRibbonruleid// "ribbonruleid"
0x14684  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14689  ldloc.s  6
0x1468b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x14690  ldstr    aRuleid// "ruleid"
0x14695  ldc.i4.0
0x14696  ldloc.s  4
0x14698  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1469d  pop
0x1469e  ldloc.s  6
0x146a0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x146a5  ldstr    aRuletype// "ruletype"
0x146aa  ldc.i4.0
0x146ab  ldarg.0
0x146ac  ldloc.3
0x146ad  call     instance int32 Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::GetRuleTypeFromNodeName(string ruleType)
0x146b2  box      [mscorlib]System.Int32
0x146b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x146bc  pop
0x146bd  br.s     loc_146DB
0x146bf  ldc.i4.0
0x146c0  ldstr    a0EntitiesAreNo// "{0} entities are not expected to be inv"...
0x146c5  ldc.i4.1
0x146c6  newarr   [mscorlib]System.Object
0x146cb  dup
0x146cc  ldc.i4.0
0x146cd  ldloc.0
0x146ce  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x146d3  stelem.ref
0x146d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x146d9  ldc.i4.0
0x146da  ret
0x146db  ldarg.0
0x146dc  ldloc.s  6
0x146de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x146e3  ldloc.2
0x146e4  ldarg.3
0x146e5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::AddEntityNameCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression criteria, string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x146ea  ldarg.2
0x146eb  brfalse  loc_14805
0x146f0  ldloc.s  6
0x146f2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x146f7  ldstr    aIsmanaged// "ismanaged"
0x146fc  ldc.i4.0
0x146fd  ldc.i4.1
0x146fe  box      [mscorlib]System.Boolean
0x14703  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14708  pop
0x14709  ldloc.s  5
0x1470b  ldloc.s  6
0x1470d  ldarg.3
0x1470e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14713  stloc.s  7
0x14715  ldloc.s  5
0x14717  ldloc.s  6
0x14719  ldarg.3
0x1471a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1471f  stloc.s  8
0x14721  ldloc.s  7
0x14723  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14728  ldc.i4.0
0x14729  ble      loc_14803
0x1472e  ldloc.s  8
0x14730  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14735  brfalse  loc_14803
0x1473a  ldnull
0x1473b  stloc.s  9
0x1473d  ldloc.s  7
0x1473f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14744  ldc.i4.0
0x14745  ble.s    loc_14753
0x14747  ldloc.s  7
0x14749  ldc.i4.0
0x1474a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1474f  stloc.s  9
0x14751  br.s     loc_1475D
0x14753  ldloc.s  8
0x14755  ldc.i4.0
0x14756  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1475b  stloc.s  9
0x1475d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14762  stloc.s  0xA
0x14764  ldloc.0
0x14765  ldc.i4.s 0x30
0x14767  sub
0x14768  switch   loc_1478F, loc_147A4, loc_147B9, loc_147F6, loc_147E3, loc_147F6, loc_147F6, loc_147CE
0x1478d  br.s     loc_147F6
0x1478f  ldloc.s  9
0x14791  ldstr    aRibboncommandi// "ribboncommandid"
0x14796  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1479b  unbox.any [mscorlib]System.Guid
0x147a0  stloc.s  0xA
0x147a2  br.s     loc_147F6
0x147a4  ldloc.s  9
0x147a6  ldstr    aRibboncontextg_0// "ribboncontextgroupid"
0x147ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x147b0  unbox.any [mscorlib]System.Guid
0x147b5  stloc.s  0xA
0x147b7  br.s     loc_147F6
0x147b9  ldloc.s  9
0x147bb  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x147c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x147c5  unbox.any [mscorlib]System.Guid
0x147ca  stloc.s  0xA
0x147cc  br.s     loc_147F6
0x147ce  ldloc.s  9
0x147d0  ldstr    aRibbondiffid// "ribbondiffid"
0x147d5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x147da  unbox.any [mscorlib]System.Guid
0x147df  stloc.s  0xA
0x147e1  br.s     loc_147F6
0x147e3  ldloc.s  9
0x147e5  ldstr    aRibbonruleid// "ribbonruleid"
0x147ea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x147ef  unbox.any [mscorlib]System.Guid
0x147f4  stloc.s  0xA
0x147f6  ldarg.1
0x147f7  ldloc.0
0x147f8  ldloc.s  0xA
0x147fa  ldarg.s  4
0x147fc  ldarg.3
0x147fd  call     bool Microsoft.Crm.Tools.ImportExportPublish.Helper::HasTheSamePublisher(class [System.Xml]System.Xml.XmlNode requiredNode, int32 componentType, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid publisherId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14802  ret
0x14803  ldc.i4.0
0x14804  ret
0x14805  ldloc.s  5
0x14807  ldloc.s  6
0x14809  ldarg.3
0x1480a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1480f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14814  ldc.i4.0
0x14815  cgt
0x14817  ret
```
