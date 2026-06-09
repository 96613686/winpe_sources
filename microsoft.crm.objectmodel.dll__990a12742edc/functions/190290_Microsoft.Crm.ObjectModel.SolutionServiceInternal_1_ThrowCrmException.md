# Microsoft.Crm.ObjectModel.SolutionServiceInternal`1::ThrowCrmException

- ea: `0x190290`
- end: `0x190495`
- name: `Microsoft.Crm.ObjectModel.SolutionServiceInternal`1::ThrowCrmException`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x11f810`
- `0x11f910`
- `0x11f960`
- `0x11fa30`
- `0x11fa70`
- `0x11fa90`
- `0x11faf0`
- `0x190290`

## string_xrefs

- `0x19032f`: `requiredcomponentobjectid`
- `0x190313`: `requiredcomponenttype`
- `0x1902f7`: `dependentcomponentobjectid`
- `0x1902db`: `dependentcomponenttype`
- `0x190484`: `componentType`
- `0x19034a`: `requiredcomponentparentid`
- `0x190290`: `Solution dependencies exist, cannot uninstall.`
- `0x19038e`: `RequiredComponentObject details: Id : {0}, Type : {1}, ParentId : {2}, DependentComponentObject details : ObjectName : {3}, Id : {4}, Type : {5}, ParentComponentDisplayName : {6}`

## pseudocode

```c

```

## disassembly

```asm
0x190290  ldstr    aSolutionDepend// "Solution dependencies exist, cannot uni"...
0x190295  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x19029a  stloc.0
0x19029b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1902a0  stloc.1
0x1902a1  ldloc.0
0x1902a2  ldstr    aDependencycoun// "DependencyCount : {0}"
0x1902a7  ldarg.1
0x1902a8  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1902ad  box      [mscorlib]System.Int32
0x1902b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1902b7  pop
0x1902b8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1902bd  stloc.2
0x1902be  ldarg.1
0x1902bf  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1902c4  stloc.3
0x1902c5  br       loc_190409
0x1902ca  ldloc.3
0x1902cb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1902d0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1902d5  dup
0x1902d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1902db  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1902e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1902e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1902ea  unbox.any [mscorlib]System.Int32
0x1902ef  stloc.s  4
0x1902f1  dup
0x1902f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1902f7  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1902fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x190301  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x190306  unbox.any [mscorlib]System.Guid
0x19030b  stloc.s  5
0x19030d  dup
0x19030e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x190313  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x190318  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x19031d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x190322  unbox.any [mscorlib]System.Int32
0x190327  stloc.s  6
0x190329  dup
0x19032a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x19032f  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x190334  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x190339  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x19033e  unbox.any [mscorlib]System.Guid
0x190343  stloc.s  7
0x190345  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x19034a  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x19034f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x190354  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x190359  unbox.any [mscorlib]System.Guid
0x19035e  stloc.s  8
0x190360  ldloc.s  4
0x190362  ldloc.s  5
0x190364  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x190369  ldc.i4.0
0x19036a  newobj   instance void Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(int32 type, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid parentObjectId, int32 key)
0x19036f  stloc.s  9
0x190371  ldloc.s  4
0x190373  ldloca.s 0xA
0x190375  call     bool Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::TryRetrieveHelper(int32 componentType, [out] class Microsoft.Crm.ObjectModel.IImportExportDependencyHelper& helper)
0x19037a  brfalse.s loc_190386
0x19037c  ldloc.s  0xA
0x19037e  ldloc.s  9
0x190380  ldarg.2
0x190381  callvirt instance void Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::FillComponentInfoForExport(class Microsoft.Crm.ObjectModel.ComponentInfo component, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x190386  ldloc.0
0x190387  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x19038c  pop
0x19038d  ldloc.0
0x19038e  ldstr    aRequiredcompon_14// "RequiredComponentObject details: Id : {"...
0x190393  ldc.i4.7
0x190394  newarr   [mscorlib]System.Object
0x190399  dup
0x19039a  ldc.i4.0
0x19039b  ldloc.s  7
0x19039d  box      [mscorlib]System.Guid
0x1903a2  stelem.ref
0x1903a3  dup
0x1903a4  ldc.i4.1
0x1903a5  ldloc.s  6
0x1903a7  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x1903ac  stelem.ref
0x1903ad  dup
0x1903ae  ldc.i4.2
0x1903af  ldloc.s  8
0x1903b1  box      [mscorlib]System.Guid
0x1903b6  stelem.ref
0x1903b7  dup
0x1903b8  ldc.i4.3
0x1903b9  ldloc.s  9
0x1903bb  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x1903c0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1903c5  brtrue.s loc_1903D0
0x1903c7  ldloc.s  9
0x1903c9  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x1903ce  br.s     loc_1903D7
0x1903d0  ldloc.s  9
0x1903d2  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_DisplayName()
0x1903d7  stelem.ref
0x1903d8  dup
0x1903d9  ldc.i4.4
0x1903da  ldloc.s  5
0x1903dc  box      [mscorlib]System.Guid
0x1903e1  stelem.ref
0x1903e2  dup
0x1903e3  ldc.i4.5
0x1903e4  ldloc.s  9
0x1903e6  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentTypeName()
0x1903eb  stelem.ref
0x1903ec  dup
0x1903ed  ldc.i4.6
0x1903ee  ldloc.s  9
0x1903f0  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_ParentDisplayName()
0x1903f5  stelem.ref
0x1903f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x1903fb  pop
0x1903fc  ldloc.2
0x1903fd  ldloc.s  9
0x1903ff  callvirt instance string Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentTypeName()
0x190404  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x190409  ldloc.3
0x19040a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19040f  brtrue   loc_1902CA
0x190414  leave.s  loc_19042A
0x190416  ldloc.3
0x190417  isinst   [mscorlib]System.IDisposable
0x19041c  stloc.s  0xB
0x19041e  ldloc.s  0xB
0x190420  brfalse.s loc_190429
0x190422  ldloc.s  0xB
0x190424  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x190429  endfinally
0x19042a  ldloc.2
0x19042b  call     T0x2B0000DA
0x190430  ldc.i4.s 0x64
0x190432  call     T0x2B000040
0x190437  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x19043c  stloc.s  0xC
0x19043e  br.s     loc_190457
0x190440  ldloc.s  0xC
0x190442  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x190447  stloc.s  0xD
0x190449  ldloc.1
0x19044a  ldstr    a0_3// "{0},"
0x19044f  ldloc.s  0xD
0x190451  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x190456  pop
0x190457  ldloc.s  0xC
0x190459  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19045e  brtrue.s loc_190440
0x190460  leave.s  loc_19046E
0x190462  ldloc.s  0xC
0x190464  brfalse.s loc_19046D
0x190466  ldloc.s  0xC
0x190468  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19046d  endfinally
0x19046e  ldloc.0
0x19046f  callvirt instance string [mscorlib]System.Object::ToString()
0x190474  ldc.i4   0x8004F01D
0x190479  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19047e  dup
0x19047f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x190484  ldstr    aComponenttype_0// "componentType"
0x190489  ldloc.1
0x19048a  callvirt instance string [mscorlib]System.Object::ToString()
0x19048f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x190494  throw
```
