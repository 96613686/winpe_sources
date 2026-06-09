# Microsoft.Crm.ObjectModel.WorkflowActivityValidator::CheckDuplicateActivityName_0

- ea: `0x69f30`
- end: `0x6a0df`
- name: `Microsoft.Crm.ObjectModel.WorkflowActivityValidator::CheckDuplicateActivityName_0`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x69f10`
- `0x6a2c0`

## callees

- `0x69f30`
- `0x1388d0`

## string_xrefs

- `0x6a030`: `plugintypeid`
- `0x69f8a`: `pluginassemblyid`
- `0x69f8f`: `pluginassemblyid`
- `0x69fc6`: `pluginassemblyid`
- `0x69fe6`: `pluginassemblyid`
- `0x69fee`: `publickeytoken`
- `0x69f77`: `PluginType`
- `0x69f85`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x69f30  ldarg.s  4
0x69f32  brtrue.s loc_69F3D
0x69f34  ldarg.3
0x69f35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69f3a  brfalse.s loc_69F3D
0x69f3c  ret
0x69f3d  ldarg.s  4
0x69f3f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69f44  brfalse.s loc_69F5E
0x69f46  ldarg.3
0x69f47  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69f4c  brtrue.s loc_69F5E
0x69f4e  ldstr    aActivityGroupN// "Activity group name cannot be specified"...
0x69f53  ldc.i4   0x8004501D
0x69f58  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x69f5d  throw
0x69f5e  ldarg.s  4
0x69f60  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x69f65  brfalse.s loc_69F77
0x69f67  ldstr    aActivityNameCa// "Activity name cannot be a whitespace"
0x69f6c  ldc.i4   0x8004501D
0x69f71  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x69f76  throw
0x69f77  ldstr    aPlugintype// "PluginType"
0x69f7c  ldarg.s  6
0x69f7e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x69f83  stloc.0
0x69f84  ldloc.0
0x69f85  ldstr    aPluginassembly_0// "PluginAssembly"
0x69f8a  ldstr    aPluginassembly// "pluginassemblyid"
0x69f8f  ldstr    aPluginassembly// "pluginassemblyid"
0x69f94  ldc.i4.0
0x69f95  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x69f9a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x69f9f  ldstr    aName// "name"
0x69fa4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x69fa9  ldloc.0
0x69faa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x69faf  ldstr    aIsworkflowacti// "isworkflowactivity"
0x69fb4  ldc.i4.0
0x69fb5  ldstr    a1// "1"
0x69fba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x69fbf  pop
0x69fc0  ldloc.0
0x69fc1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x69fc6  ldstr    aPluginassembly// "pluginassemblyid"
0x69fcb  ldc.i4.0
0x69fcc  ldarg.2
0x69fcd  box      [mscorlib]System.Guid
0x69fd2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x69fd7  pop
0x69fd8  ldloc.0
0x69fd9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x69fde  ldc.i4.7
0x69fdf  newarr   [mscorlib]System.String
0x69fe4  dup
0x69fe5  ldc.i4.0
0x69fe6  ldstr    aPluginassembly// "pluginassemblyid"
0x69feb  stelem.ref
0x69fec  dup
0x69fed  ldc.i4.1
0x69fee  ldstr    aPublickeytoken// "publickeytoken"
0x69ff3  stelem.ref
0x69ff4  dup
0x69ff5  ldc.i4.2
0x69ff6  ldstr    aVersion// "version"
0x69ffb  stelem.ref
0x69ffc  dup
0x69ffd  ldc.i4.3
0x69ffe  ldstr    aTypename// "typename"
0x6a003  stelem.ref
0x6a004  dup
0x6a005  ldc.i4.4
0x6a006  ldstr    aCulture// "culture"
0x6a00b  stelem.ref
0x6a00c  dup
0x6a00d  ldc.i4.5
0x6a00e  ldstr    aName// "name"
0x6a013  stelem.ref
0x6a014  dup
0x6a015  ldc.i4.6
0x6a016  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x6a01b  stelem.ref
0x6a01c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x6a021  ldarga.s 1
0x6a023  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x6a028  brfalse.s loc_6A048
0x6a02a  ldloc.0
0x6a02b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6a030  ldstr    aPlugintypeid// "plugintypeid"
0x6a035  ldc.i4.1
0x6a036  ldarga.s 1
0x6a038  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x6a03d  box      [mscorlib]System.Guid
0x6a042  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6a047  pop
0x6a048  newobj   instance void Microsoft.Crm.ObjectModel.PluginTypeService::.ctor()
0x6a04d  ldloc.0
0x6a04e  ldarg.s  6
0x6a050  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6a055  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6a05a  stloc.1
0x6a05b  br.s     loc_6A0C3
0x6a05d  ldloc.1
0x6a05e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6a063  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6a068  stloc.2
0x6a069  ldloc.2
0x6a06a  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x6a06f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6a074  isinst   [mscorlib]System.String
0x6a079  ldarg.3
0x6a07a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a07f  brfalse.s loc_6A0C3
0x6a081  ldloc.2
0x6a082  ldstr    aName// "name"
0x6a087  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6a08c  isinst   [mscorlib]System.String
0x6a091  ldarg.s  4
0x6a093  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a098  brfalse.s loc_6A0C3
0x6a09a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6a09f  ldstr    aDuplicateWorkf// "Duplicate workflow activity group name:"...
0x6a0a4  ldc.i4.2
0x6a0a5  newarr   [mscorlib]System.Object
0x6a0aa  dup
0x6a0ab  ldc.i4.0
0x6a0ac  ldarg.3
0x6a0ad  stelem.ref
0x6a0ae  dup
0x6a0af  ldc.i4.1
0x6a0b0  ldarg.s  4
0x6a0b2  stelem.ref
0x6a0b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6a0b8  ldc.i4   0x8004501D
0x6a0bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6a0c2  throw
0x6a0c3  ldloc.1
0x6a0c4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a0c9  brtrue.s loc_6A05D
0x6a0cb  leave.s  loc_6A0DE
0x6a0cd  ldloc.1
0x6a0ce  isinst   [mscorlib]System.IDisposable
0x6a0d3  stloc.3
0x6a0d4  ldloc.3
0x6a0d5  brfalse.s loc_6A0DD
0x6a0d7  ldloc.3
0x6a0d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a0dd  endfinally
0x6a0de  ret
```
