# Microsoft.Crm.ObjectModel.AssemblyMetadataValidator::ValidateInternal

- ea: `0x64eb0`
- end: `0x651c3`
- name: `Microsoft.Crm.ObjectModel.AssemblyMetadataValidator::ValidateInternal`
- size: `787`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x64eb0`
- `0x682f0`
- `0xe5650`
- `0xe5660`
- `0xe5670`

## string_xrefs

- `0x64eb6`: `pluginassemblyid`
- `0x64ec8`: `pluginassemblyid`
- `0x6511a`: `pluginassemblyid`
- `0x64ee5`: `publickeytoken`
- `0x64ef7`: `publickeytoken`
- `0x65147`: `publickeytoken`
- `0x65101`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x64eb0  ldarg.0
0x64eb1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64eb6  ldstr    aPluginassembly// "pluginassemblyid"
0x64ebb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64ec0  brtrue.s loc_64ED9
0x64ec2  ldarg.0
0x64ec3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64ec8  ldstr    aPluginassembly// "pluginassemblyid"
0x64ecd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64ed2  unbox.any [mscorlib]System.Guid
0x64ed7  br.s     loc_64EDE
0x64ed9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x64ede  stloc.0
0x64edf  ldarg.0
0x64ee0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64ee5  ldstr    aPublickeytoken// "publickeytoken"
0x64eea  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64eef  brtrue.s loc_64F08
0x64ef1  ldarg.0
0x64ef2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64ef7  ldstr    aPublickeytoken// "publickeytoken"
0x64efc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64f01  castclass [mscorlib]System.String
0x64f06  br.s     loc_64F0D
0x64f08  ldsfld   string [mscorlib]System.String::Empty
0x64f0d  stloc.1
0x64f0e  ldarg.0
0x64f0f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f14  ldstr    aName// "name"
0x64f19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64f1e  brtrue.s loc_64F37
0x64f20  ldarg.0
0x64f21  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f26  ldstr    aName// "name"
0x64f2b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64f30  castclass [mscorlib]System.String
0x64f35  br.s     loc_64F3C
0x64f37  ldsfld   string [mscorlib]System.String::Empty
0x64f3c  stloc.2
0x64f3d  ldarg.0
0x64f3e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f43  ldstr    aCulture// "culture"
0x64f48  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64f4d  brtrue.s loc_64F66
0x64f4f  ldarg.0
0x64f50  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f55  ldstr    aCulture// "culture"
0x64f5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64f5f  castclass [mscorlib]System.String
0x64f64  br.s     loc_64F6B
0x64f66  ldsfld   string [mscorlib]System.String::Empty
0x64f6b  stloc.3
0x64f6c  ldarg.0
0x64f6d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f72  ldstr    aMinor// "minor"
0x64f77  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64f7c  brtrue.s loc_64F95
0x64f7e  ldarg.0
0x64f7f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f84  ldstr    aMinor// "minor"
0x64f89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64f8e  unbox.any [mscorlib]System.Int32
0x64f93  br.s     loc_64F96
0x64f95  ldc.i4.0
0x64f96  stloc.s  4
0x64f98  ldarg.0
0x64f99  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64f9e  ldstr    aMajor// "major"
0x64fa3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x64fa8  brtrue.s loc_64FC1
0x64faa  ldarg.0
0x64fab  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64fb0  ldstr    aMajor// "major"
0x64fb5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64fba  unbox.any [mscorlib]System.Int32
0x64fbf  br.s     loc_64FC2
0x64fc1  ldc.i4.0
0x64fc2  stloc.s  5
0x64fc4  ldarg.0
0x64fc5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64fca  ldstr    aIsolationmode// "isolationmode"
0x64fcf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64fd4  unbox.any [mscorlib]System.Int32
0x64fd9  stloc.s  6
0x64fdb  ldarg.0
0x64fdc  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64fe1  ldstr    aSourcetype// "sourcetype"
0x64fe6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x64feb  unbox.any [mscorlib]System.Int32
0x64ff0  stloc.s  7
0x64ff2  ldarg.0
0x64ff3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x64ff8  ldstr    aPath// "path"
0x64ffd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x65002  brtrue.s loc_6501C
0x65004  ldarg.0
0x65005  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x6500a  ldstr    aPath// "path"
0x6500f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x65014  castclass [mscorlib]System.String
0x65019  pop
0x6501a  br.s     loc_65022
0x6501c  ldsfld   string [mscorlib]System.String::Empty
0x65021  pop
0x65022  ldarg.0
0x65023  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x65028  ldstr    aUrl// "url"
0x6502d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x65032  brtrue.s loc_6504C
0x65034  ldarg.0
0x65035  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssembly()
0x6503a  ldstr    aUrl// "url"
0x6503f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x65044  castclass [mscorlib]System.String
0x65049  pop
0x6504a  br.s     loc_65052
0x6504c  ldsfld   string [mscorlib]System.String::Empty
0x65051  pop
0x65052  ldloc.1
0x65053  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x65058  brtrue.s loc_65067
0x6505a  ldloc.1
0x6505b  ldstr    aNull// "null"
0x65060  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65065  brfalse.s loc_650BD
0x65067  ldloc.s  7
0x65069  ldc.i4.3
0x6506a  beq.s    loc_650BD
0x6506c  ldarg.0
0x6506d  call     instance class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata Microsoft.Crm.ObjectModel.PluginValidatorBase::get_PluginAssemblyMetadata()
0x65072  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata> [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypes()
0x65077  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata>::get_Values()
0x6507c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata>::GetEnumerator()
0x65081  stloc.s  9
0x65083  br.s     loc_650A4
0x65085  ldloca.s 9
0x65087  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata>::get_Current()
0x6508c  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata::get_IsV4WorkflowActivity()
0x65091  brtrue.s loc_650A4
0x65093  ldc.i4   0x8004416C
0x65098  ldc.i4.0
0x65099  newarr   [mscorlib]System.Object
0x6509e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x650a3  throw
0x650a4  ldloca.s 9
0x650a6  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata>::MoveNext()
0x650ab  brtrue.s loc_65085
0x650ad  leave.s  loc_650BD
0x650af  ldloca.s 9
0x650b1  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<unsigned int32, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata>
0x650b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x650bc  endfinally
0x650bd  ldloc.s  6
0x650bf  ldc.i4.1
0x650c0  beq.s    loc_650C7
0x650c2  ldloc.s  6
0x650c4  ldc.i4.2
0x650c5  bne.un.s loc_650E6
0x650c7  ldloc.s  7
0x650c9  brfalse.s loc_650FC
0x650cb  ldloc.s  7
0x650cd  ldc.i4.1
0x650ce  beq.s    loc_650FC
0x650d0  ldloc.s  7
0x650d2  ldc.i4.2
0x650d3  beq.s    loc_650FC
0x650d5  ldc.i4   0x8004417D
0x650da  ldc.i4.0
0x650db  newarr   [mscorlib]System.Object
0x650e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x650e5  throw
0x650e6  ldloc.s  7
0x650e8  ldc.i4.3
0x650e9  beq.s    loc_650FC
0x650eb  ldc.i4   0x8004417D
0x650f0  ldc.i4.0
0x650f1  newarr   [mscorlib]System.Object
0x650f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x650fb  throw
0x650fc  newobj   instance void Microsoft.Crm.ObjectModel.PluginAssemblyService::.ctor()
0x65101  ldstr    aPluginassembly_0// "PluginAssembly"
0x65106  ldarg.0
0x65107  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x6510c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x65111  stloc.s  8
0x65113  ldloc.s  8
0x65115  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6511a  ldstr    aPluginassembly// "pluginassemblyid"
0x6511f  ldc.i4.1
0x65120  ldloc.0
0x65121  box      [mscorlib]System.Guid
0x65126  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6512b  pop
0x6512c  ldloc.s  8
0x6512e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x65133  ldstr    aName// "name"
0x65138  ldc.i4.0
0x65139  ldloc.2
0x6513a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6513f  pop
0x65140  ldloc.s  8
0x65142  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x65147  ldstr    aPublickeytoken// "publickeytoken"
0x6514c  ldc.i4.0
0x6514d  ldloc.1
0x6514e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x65153  pop
0x65154  ldloc.s  8
0x65156  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6515b  ldstr    aCulture// "culture"
0x65160  ldc.i4.0
0x65161  ldloc.3
0x65162  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x65167  pop
0x65168  ldloc.s  8
0x6516a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6516f  ldstr    aMajor// "major"
0x65174  ldc.i4.0
0x65175  ldloc.s  5
0x65177  box      [mscorlib]System.Int32
0x6517c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x65181  pop
0x65182  ldloc.s  8
0x65184  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x65189  ldstr    aMinor// "minor"
0x6518e  ldc.i4.0
0x6518f  ldloc.s  4
0x65191  box      [mscorlib]System.Int32
0x65196  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6519b  pop
0x6519c  ldloc.s  8
0x6519e  ldarg.0
0x6519f  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.PluginValidatorBase::get_Context()
0x651a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x651a9  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x651ae  ldc.i4.0
0x651af  ble.s    loc_651C2
0x651b1  ldc.i4   0x8004417B
0x651b6  ldc.i4.0
0x651b7  newarr   [mscorlib]System.Object
0x651bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x651c1  throw
0x651c2  ret
```
