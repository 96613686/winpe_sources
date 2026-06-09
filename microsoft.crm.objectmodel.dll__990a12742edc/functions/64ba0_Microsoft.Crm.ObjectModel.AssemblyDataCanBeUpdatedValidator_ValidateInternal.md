# Microsoft.Crm.ObjectModel.AssemblyDataCanBeUpdatedValidator::ValidateInternal

- ea: `0x64ba0`
- end: `0x64e8a`
- name: `Microsoft.Crm.ObjectModel.AssemblyDataCanBeUpdatedValidator::ValidateInternal`
- size: `746`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x64ba0`
- `0x682f0`
- `0x68370`
- `0xe5600`
- `0xe5650`
- `0xe5660`
- `0xe5670`
- `0x1388d0`

## string_xrefs

- `0x64db7`: `pluginassemblyid`
- `0x64bfc`: `publickeytoken`
- `0x64cf2`: `publickeytoken`
- `0x64d07`: `publickeytoken`
- `0x64d7c`: `PluginType`
- `0x64ba5`: `PluginAssembly`
- `0x64c26`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x64ba0  newobj   instance void Microsoft.Crm.ObjectModel.PluginAssemblyService::.ctor()
0x64ba5  ldstr    aPluginassembly_0// "PluginAssembly"
0x64baa  ldarg.0
0x64bab  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64bb0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x64bb5  stloc.0
0x64bb6  ldloc.0
0x64bb7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64bbc  ldstr    aMajor// "major"
0x64bc1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64bc6  ldloc.0
0x64bc7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64bcc  ldstr    aMinor// "minor"
0x64bd1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64bd6  ldloc.0
0x64bd7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64bdc  ldstr    aName// "name"
0x64be1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64be6  ldloc.0
0x64be7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64bec  ldstr    aCulture// "culture"
0x64bf1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64bf6  ldloc.0
0x64bf7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64bfc  ldstr    aPublickeytoken// "publickeytoken"
0x64c01  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64c06  ldloc.0
0x64c07  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64c0c  ldstr    aIsolationmode// "isolationmode"
0x64c11  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64c16  ldarg.0
0x64c17  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64c1c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x64c21  unbox.any [mscorlib]System.Guid
0x64c26  ldstr    aPluginassembly_0// "PluginAssembly"
0x64c2b  ldarg.0
0x64c2c  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64c31  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x64c36  stloc.1
0x64c37  ldloc.1
0x64c38  ldloc.0
0x64c39  ldarg.0
0x64c3a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64c3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64c44  stloc.2
0x64c45  ldloc.2
0x64c46  ldstr    aMajor// "major"
0x64c4b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64c50  unbox.any [mscorlib]System.Int32
0x64c55  ldarg.0
0x64c56  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64c5b  ldstr    aMajor// "major"
0x64c60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64c65  unbox.any [mscorlib]System.Int32
0x64c6a  bne.un   loc_64D1D
0x64c6f  ldloc.2
0x64c70  ldstr    aMinor// "minor"
0x64c75  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64c7a  unbox.any [mscorlib]System.Int32
0x64c7f  ldarg.0
0x64c80  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64c85  ldstr    aMinor// "minor"
0x64c8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64c8f  unbox.any [mscorlib]System.Int32
0x64c94  bne.un   loc_64D1D
0x64c99  ldloc.2
0x64c9a  ldstr    aName// "name"
0x64c9f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64ca4  castclass [mscorlib]System.String
0x64ca9  ldarg.0
0x64caa  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64caf  ldstr    aName// "name"
0x64cb4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64cb9  castclass [mscorlib]System.String
0x64cbe  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x64cc3  brtrue.s loc_64D1D
0x64cc5  ldloc.2
0x64cc6  ldstr    aCulture// "culture"
0x64ccb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64cd0  castclass [mscorlib]System.String
0x64cd5  ldarg.0
0x64cd6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64cdb  ldstr    aCulture// "culture"
0x64ce0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64ce5  castclass [mscorlib]System.String
0x64cea  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x64cef  brtrue.s loc_64D1D
0x64cf1  ldloc.2
0x64cf2  ldstr    aPublickeytoken// "publickeytoken"
0x64cf7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64cfc  castclass [mscorlib]System.String
0x64d01  ldarg.0
0x64d02  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64d07  ldstr    aPublickeytoken// "publickeytoken"
0x64d0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64d11  castclass [mscorlib]System.String
0x64d16  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x64d1b  brfalse.s loc_64D2E
0x64d1d  ldc.i4   0x8004418B
0x64d22  ldc.i4.0
0x64d23  newarr   [mscorlib]System.Object
0x64d28  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x64d2d  throw
0x64d2e  ldloc.2
0x64d2f  ldstr    aIsolationmode// "isolationmode"
0x64d34  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64d39  unbox.any [mscorlib]System.Int32
0x64d3e  stloc.3
0x64d3f  ldarg.0
0x64d40  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64d45  ldstr    aIsolationmode// "isolationmode"
0x64d4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64d4f  unbox.any [mscorlib]System.Int32
0x64d54  stloc.s  4
0x64d56  ldloc.3
0x64d57  ldc.i4.3
0x64d58  beq.s    loc_64D5F
0x64d5a  ldloc.s  4
0x64d5c  ldc.i4.3
0x64d5d  bne.un.s loc_64D75
0x64d5f  ldloc.3
0x64d60  ldloc.s  4
0x64d62  beq.s    loc_64D75
0x64d64  ldc.i4   0x8004418B
0x64d69  ldc.i4.0
0x64d6a  newarr   [mscorlib]System.Object
0x64d6f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x64d74  throw
0x64d75  newobj   instance void Microsoft.Crm.ObjectModel.PluginTypeService::.ctor()
0x64d7a  stloc.s  5
0x64d7c  ldstr    aPlugintype// "PluginType"
0x64d81  ldarg.0
0x64d82  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64d87  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x64d8c  stloc.s  6
0x64d8e  ldloc.s  6
0x64d90  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64d95  ldstr    aTypename// "typename"
0x64d9a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64d9f  ldloc.s  6
0x64da1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64da6  ldstr    aIsworkflowacti// "isworkflowactivity"
0x64dab  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x64db0  ldloc.s  6
0x64db2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x64db7  ldstr    aPluginassembly// "pluginassemblyid"
0x64dbc  ldc.i4.0
0x64dbd  ldarg.0
0x64dbe  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64dc3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x64dc8  unbox.any [mscorlib]System.Guid
0x64dcd  box      [mscorlib]System.Guid
0x64dd2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x64dd7  pop
0x64dd8  ldloc.s  5
0x64dda  ldloc.s  6
0x64ddc  ldarg.0
0x64ddd  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64de2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64de7  stloc.s  7
0x64de9  ldloc.s  7
0x64deb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x64df0  ldc.i4.0
0x64df1  ble      loc_64E89
0x64df6  ldloc.s  7
0x64df8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x64dfd  stloc.s  8
0x64dff  br.s     loc_64E69
0x64e01  ldloc.s  8
0x64e03  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x64e08  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x64e0d  stloc.s  9
0x64e0f  ldnull
0x64e10  stloc.s  0xA
0x64e12  ldnull
0x64e13  stloc.s  0xB
0x64e15  ldloc.s  5
0x64e17  ldloc.s  9
0x64e19  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType
0x64e1e  ldarg.0
0x64e1f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64e24  ldloca.s 0xB
0x64e26  ldloca.s 0xA
0x64e28  ldarg.0
0x64e29  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64e2e  callvirt instance void class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<class Microsoft.Crm.ObjectModel.UpgradingOff>::SetIsWorkFlowActivityAttribute(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo&, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata&, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64e33  ldarg.0
0x64e34  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x64e39  ldarg.0
0x64e3a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64e3f  ldloc.s  9
0x64e41  ldloc.s  9
0x64e43  ldstr    aIsworkflowacti// "isworkflowactivity"
0x64e48  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64e4d  unbox.any [mscorlib]System.Boolean
0x64e52  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x64e57  ldarg.0
0x64e58  call     instance class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssemblyMetadata()
0x64e5d  ldloc.s  0xB
0x64e5f  newobj   instance void Microsoft.Crm.ObjectModel.PluginTypeValidator::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity pluginAssembly, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity pluginType, valuetype [mscorlib]System.Nullable`1<bool> isWorkflowActivity, class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata parentAssemblyMetadata, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo customActivityInfo)
0x64e64  callvirt instance void Microsoft.Crm.ObjectModel.PluginValidatorBase::Validate()
0x64e69  ldloc.s  8
0x64e6b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64e70  brtrue.s loc_64E01
0x64e72  leave.s  loc_64E89
0x64e74  ldloc.s  8
0x64e76  isinst   [mscorlib]System.IDisposable
0x64e7b  stloc.s  0xC
0x64e7d  ldloc.s  0xC
0x64e7f  brfalse.s loc_64E88
0x64e81  ldloc.s  0xC
0x64e83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64e88  endfinally
0x64e89  ret
```
