# Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::FillCommandDefNodes

- ea: `0x74f70`
- end: `0x75060`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::FillCommandDefNodes`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x74bb0`

## callees

- `0x74cf0`
- `0x74f70`

## string_xrefs

- `0x74f76`: `RibbonCommand`
- `0x74fd8`: `command`
- `0x74f95`: `commanddefinition`
- `0x75009`: `commanddefinition`

## pseudocode

```c

```

## disassembly

```asm
0x74f70  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonCommandService::.ctor()
0x74f75  stloc.0
0x74f76  ldstr    aRibboncommand// "RibbonCommand"
0x74f7b  ldarg.0
0x74f7c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::_context
0x74f81  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x74f86  stloc.1
0x74f87  ldloc.1
0x74f88  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x74f8d  ldc.i4.1
0x74f8e  newarr   [mscorlib]System.String
0x74f93  dup
0x74f94  ldc.i4.0
0x74f95  ldstr    aCommanddefinit_2// "commanddefinition"
0x74f9a  stelem.ref
0x74f9b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x74fa0  ldloc.1
0x74fa1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x74fa6  ldstr    aSolutionid// "solutionid"
0x74fab  ldc.i4.0
0x74fac  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x74fb1  box      [mscorlib]System.Guid
0x74fb6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x74fbb  pop
0x74fbc  ldloc.1
0x74fbd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x74fc2  ldstr    aEntity// "entity"
0x74fc7  ldarg.0
0x74fc8  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::_entityLogicalName
0x74fcd  call     void Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::AddNullStringCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression criteria, string attributeName, string attributeValue)
0x74fd2  ldloc.1
0x74fd3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x74fd8  ldstr    aCommand// "command"
0x74fdd  ldc.i4.0
0x74fde  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x74fe3  ldloc.0
0x74fe4  ldloc.1
0x74fe5  ldarg.0
0x74fe6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::_context
0x74feb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x74ff0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x74ff5  stloc.2
0x74ff6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x74ffb  stloc.3
0x74ffc  br.s     loc_7502C
0x74ffe  ldloc.3
0x74fff  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x75004  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RibbonCommand
0x75009  ldstr    aCommanddefinit_2// "commanddefinition"
0x7500e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x75013  castclass [mscorlib]System.String
0x75018  stloc.s  4
0x7501a  ldloc.s  4
0x7501c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75021  brtrue.s loc_7502C
0x75023  ldloc.2
0x75024  ldloc.s  4
0x75026  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7502b  pop
0x7502c  ldloc.3
0x7502d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x75032  brtrue.s loc_74FFE
0x75034  leave.s  loc_7504A
0x75036  ldloc.3
0x75037  isinst   [mscorlib]System.IDisposable
0x7503c  stloc.s  5
0x7503e  ldloc.s  5
0x75040  brfalse.s loc_75049
0x75042  ldloc.s  5
0x75044  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75049  endfinally
0x7504a  ldloc.2
0x7504b  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x75050  ldc.i4.0
0x75051  ble.s    loc_7505F
0x75053  ldarg.1
0x75054  ldloc.2
0x75055  callvirt instance string [mscorlib]System.Object::ToString()
0x7505a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x7505f  ret
```
