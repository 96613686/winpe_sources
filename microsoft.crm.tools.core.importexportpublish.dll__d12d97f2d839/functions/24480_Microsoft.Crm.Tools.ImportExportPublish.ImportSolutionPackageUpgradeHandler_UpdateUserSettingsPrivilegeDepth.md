# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateUserSettingsPrivilegeDepth

- ea: `0x24480`
- end: `0x245e3`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateUserSettingsPrivilegeDepth`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x24480`
- `0x63db0`
- `0x95e90`

## string_xrefs

- `0x24492`: `prvCreateUserSettings`
- `0x244aa`: `prvDeleteUserSettings`
- `0x244b6`: `prvReadUserSettings`
- `0x244c2`: `prvWriteUserSettings`
- `0x244d3`: `ImportExportXml/Roles/Role/RolePrivileges/RolePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x24480  newobj   instance void <>c__DisplayClass69_0::.ctor()
0x24485  stloc.0
0x24486  ldloc.0
0x24487  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x2448c  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x24491  dup
0x24492  ldstr    aPrvcreateusers// "prvCreateUserSettings"
0x24497  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x2449c  pop
0x2449d  dup
0x2449e  ldstr    aPrvappendtouse// "prvAppendToUserSettings"
0x244a3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x244a8  pop
0x244a9  dup
0x244aa  ldstr    aPrvdeleteusers// "prvDeleteUserSettings"
0x244af  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x244b4  pop
0x244b5  dup
0x244b6  ldstr    aPrvreaduserset// "prvReadUserSettings"
0x244bb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x244c0  pop
0x244c1  dup
0x244c2  ldstr    aPrvwriteuserse// "prvWriteUserSettings"
0x244c7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x244cc  pop
0x244cd  stfld    class [System.Core]System.Collections.Generic.HashSet`1<string> <>c__DisplayClass69_0::userSettingsPrivilegesForUpdate
0x244d2  ldarg.1
0x244d3  ldstr    aImportexportxm_63// "ImportExportXml/Roles/Role/RolePrivileg"...
0x244d8  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x244dd  stloc.1
0x244de  ldloc.1
0x244df  brfalse  loc_245C0
0x244e4  ldloc.1
0x244e5  call     T0x2B000023
0x244ea  ldloc.0
0x244eb  ldfld    class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool> <>c__DisplayClass69_0::<>9__0
0x244f0  dup
0x244f1  brtrue.s loc_24509
0x244f3  pop
0x244f4  ldloc.0
0x244f5  ldloc.0
0x244f6  ldftn    instance bool <>c__DisplayClass69_0::<UpdateUserSettingsPrivilegeDepth>b__0(class [System.Xml]System.Xml.XmlNode rolePrivilegeNode)
0x244fc  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool>::.ctor(object, native int)
0x24501  dup
0x24502  stloc.3
0x24503  stfld    class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool> <>c__DisplayClass69_0::<>9__0
0x24508  ldloc.3
0x24509  call     T0x2B000024
0x2450e  ldsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>> <>c::<>9__69_1
0x24513  dup
0x24514  brtrue.s loc_2452D
0x24516  pop
0x24517  ldsfld   class <>c <>c::<>9
0x2451c  ldftn    instance class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth> <>c::<UpdateUserSettingsPrivilegeDepth>b__69_1(class [System.Xml]System.Xml.XmlNode rolePrivilegeNode)
0x24522  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>>::.ctor(object, native int)
0x24527  dup
0x24528  stsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>> <>c::<>9__69_1
0x2452d  call     T0x2B000025
0x24532  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, bool> <>c::<>9__69_2
0x24537  dup
0x24538  brtrue.s loc_24551
0x2453a  pop
0x2453b  ldsfld   class <>c <>c::<>9
0x24540  ldftn    instance bool <>c::<UpdateUserSettingsPrivilegeDepth>b__69_2(class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth> <>h__TransparentIdentifier0)
0x24546  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, bool>::.ctor(object, native int)
0x2454b  dup
0x2454c  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, bool> <>c::<>9__69_2
0x24551  call     T0x2B000026
0x24556  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, class [System.Xml]System.Xml.XmlNode> <>c::<>9__69_3
0x2455b  dup
0x2455c  brtrue.s loc_24575
0x2455e  pop
0x2455f  ldsfld   class <>c <>c::<>9
0x24564  ldftn    instance class [System.Xml]System.Xml.XmlNode <>c::<UpdateUserSettingsPrivilegeDepth>b__69_3(class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth> <>h__TransparentIdentifier0)
0x2456a  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, class [System.Xml]System.Xml.XmlNode>::.ctor(object, native int)
0x2456f  dup
0x24570  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml]System.Xml.XmlNode, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>, class [System.Xml]System.Xml.XmlNode> <>c::<>9__69_3
0x24575  call     T0x2B000027
0x2457a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlNode>::GetEnumerator()
0x2457f  stloc.2
0x24580  br.s     loc_245AC
0x24582  ldloc.2
0x24583  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlNode>::get_Current()
0x24588  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2458d  ldstr    aLevel// "level"
0x24592  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x24597  ldc.i4.1
0x24598  stloc.s  4
0x2459a  ldloca.s 4
0x2459c  constrained. [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth
0x245a2  callvirt instance string [mscorlib]System.Object::ToString()
0x245a7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x245ac  ldloc.2
0x245ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x245b2  brtrue.s loc_24582
0x245b4  leave.s  loc_245C0
0x245b6  ldloc.2
0x245b7  brfalse.s loc_245BF
0x245b9  ldloc.2
0x245ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x245bf  endfinally
0x245c0  ldarg.s  6
0x245c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x245c7  ldstr    aExecutingSolut// "Executing solution package Upgrade hand"...
0x245cc  ldc.i4.1
0x245cd  newarr   [mscorlib]System.Object
0x245d2  dup
0x245d3  ldc.i4.0
0x245d4  ldarg.s  4
0x245d6  stelem.ref
0x245d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x245dc  ldc.i4.1
0x245dd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x245e2  ret
```
