# <>c::<Initialize>b__4_0

- ea: `0x85e80`
- end: `0x86532`
- name: `<>c::<Initialize>b__4_0`
- size: `1714`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2e00`
- `0x2e20`
- `0x2e40`
- `0x2e60`
- `0x2e80`
- `0x2ea0`
- `0x2ec0`
- `0x2ee0`
- `0x2f00`
- `0x2f20`
- `0x2f40`
- `0x2f60`
- `0x2f80`
- `0x2fa0`
- `0x2fc0`
- `0x2fe0`
- `0x3000`
- `0x3020`
- `0x3040`
- `0x3060`
- `0x3080`
- `0x30a0`
- `0x30c0`
- `0x30e0`
- `0x3100`
- `0x3120`
- `0x3140`
- `0x3160`
- `0x3180`
- `0x31a0`
- `0x31c0`
- `0x31e0`
- `0x3200`
- `0x3220`
- `0x85e80`

## string_xrefs

- `0x85ea2`: `ComponentType`
- `0x85f75`: `UseForceUpdateAlways`
- `0x85f87`: `UseForceUpdateAlways`
- `0x85faa`: `UseForceDeleteForSolutionUpdate`
- `0x85fbc`: `UseForceDeleteForSolutionUpdate`
- `0x86014`: `AllowDeleteBaseSolutionRowAndFakeDeleteInSolutionUpgrade`
- `0x86026`: `AllowDeleteBaseSolutionRowAndFakeDeleteInSolutionUpgrade`
- `0x86049`: `AllowRecreateForLogicallyDeletedRowInActiveSolution`
- `0x8605b`: `AllowRecreateForLogicallyDeletedRowInActiveSolution`
- `0x86222`: `GroupParentComponentAttributeName`
- `0x86234`: `GroupParentComponentAttributeName`
- `0x86256`: `GroupParentComponentType`
- `0x86268`: `GroupParentComponentType`
- `0x86290`: `ViewableDescendentComponentType`
- `0x862a2`: `ViewableDescendentComponentType`
- `0x862ca`: `DescendentIsViewableComponent`
- `0x862dc`: `DescendentIsViewableComponent`
- `0x86367`: `HasIsRenameableAttribute`
- `0x86379`: `HasIsRenameableAttribute`
- `0x8639c`: `AlwaysRemoveActiveCustomizationsOnUninstall`
- `0x863ae`: `AlwaysRemoveActiveCustomizationsOnUninstall`
- `0x86406`: `AllowOverwriteCustomizations`
- `0x86418`: `AllowOverwriteCustomizations`
- `0x86490`: `CanBeAddedToSolutionComponents`
- `0x864a2`: `CanBeAddedToSolutionComponents`
- `0x864c5`: `RootComponent`
- `0x864d7`: `RootComponent`

## pseudocode

```c

```

## disassembly

```asm
0x85e80  newobj   instance void Microsoft.Crm.Dependency.ComponentDefinition::.ctor()
0x85e85  dup
0x85e86  ldarg.1
0x85e87  ldstr    aName_2// "Name"
0x85e8c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85e91  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85e96  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85e9b  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_Name(string value)
0x85ea0  dup
0x85ea1  ldarg.1
0x85ea2  ldstr    aComponenttype_1// "ComponentType"
0x85ea7  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85eac  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85eb1  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85eb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85ebb  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x85ec0  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_ComponentType(int32 value)
0x85ec5  dup
0x85ec6  ldarg.1
0x85ec7  ldstr    aMetadataobject_10// "MetadataObjectType"
0x85ecc  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85ed1  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85ed6  brfalse.s loc_85EF9
0x85ed8  ldarg.1
0x85ed9  ldstr    aMetadataobject_10// "MetadataObjectType"
0x85ede  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85ee3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85ee8  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85eed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85ef2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x85ef7  br.s     loc_85EFA
0x85ef9  ldc.i4.m1
0x85efa  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_MetadataObjectType(int32 value)
0x85eff  dup
0x85f00  ldarg.1
0x85f01  ldstr    aObjecttypecode_85// "ObjectTypeCode"
0x85f06  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f0b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f10  brfalse.s loc_85F33
0x85f12  ldarg.1
0x85f13  ldstr    aObjecttypecode_85// "ObjectTypeCode"
0x85f18  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f1d  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f22  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85f27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85f2c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x85f31  br.s     loc_85F34
0x85f33  ldc.i4.m1
0x85f34  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_ObjectTypeCode(int32 value)
0x85f39  dup
0x85f3a  ldarg.1
0x85f3b  ldstr    aLabeltypecode_0// "LabelTypeCode"
0x85f40  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f45  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f4a  brfalse.s loc_85F6D
0x85f4c  ldarg.1
0x85f4d  ldstr    aLabeltypecode_0// "LabelTypeCode"
0x85f52  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f57  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f5c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85f61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85f66  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x85f6b  br.s     loc_85F6E
0x85f6d  ldc.i4.m1
0x85f6e  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_LabelTypeCode(int32 value)
0x85f73  dup
0x85f74  ldarg.1
0x85f75  ldstr    aUseforceupdate// "UseForceUpdateAlways"
0x85f7a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f7f  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f84  brfalse.s loc_85FA2
0x85f86  ldarg.1
0x85f87  ldstr    aUseforceupdate// "UseForceUpdateAlways"
0x85f8c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85f91  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85f96  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85f9b  call     bool [mscorlib]System.Boolean::Parse(string)
0x85fa0  br.s     loc_85FA3
0x85fa2  ldc.i4.0
0x85fa3  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_UseForceUpdateAlways(bool value)
0x85fa8  dup
0x85fa9  ldarg.1
0x85faa  ldstr    aUseforcedelete// "UseForceDeleteForSolutionUpdate"
0x85faf  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85fb4  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85fb9  brfalse.s loc_85FD7
0x85fbb  ldarg.1
0x85fbc  ldstr    aUseforcedelete// "UseForceDeleteForSolutionUpdate"
0x85fc1  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85fc6  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85fcb  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x85fd0  call     bool [mscorlib]System.Boolean::Parse(string)
0x85fd5  br.s     loc_85FD8
0x85fd7  ldc.i4.0
0x85fd8  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_UseForceDeleteForSolutionUpdate(bool value)
0x85fdd  dup
0x85fde  ldarg.1
0x85fdf  ldstr    aUsesentinelrow// "UseSentinelRowInBaseSolution"
0x85fe4  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85fe9  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x85fee  brfalse.s loc_8600C
0x85ff0  ldarg.1
0x85ff1  ldstr    aUsesentinelrow// "UseSentinelRowInBaseSolution"
0x85ff6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x85ffb  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86000  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x86005  call     bool [mscorlib]System.Boolean::Parse(string)
0x8600a  br.s     loc_8600D
0x8600c  ldc.i4.0
0x8600d  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_UseSentinelRowInBaseSolution(bool value)
0x86012  dup
0x86013  ldarg.1
0x86014  ldstr    aAllowdeletebas// "AllowDeleteBaseSolutionRowAndFakeDelete"...
0x86019  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8601e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86023  brfalse.s loc_86041
0x86025  ldarg.1
0x86026  ldstr    aAllowdeletebas// "AllowDeleteBaseSolutionRowAndFakeDelete"...
0x8602b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86030  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86035  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x8603a  call     bool [mscorlib]System.Boolean::Parse(string)
0x8603f  br.s     loc_86042
0x86041  ldc.i4.0
0x86042  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_AllowDeleteBaseSolutionRowAndFakeDeleteInSolutionUpgrade(bool value)
0x86047  dup
0x86048  ldarg.1
0x86049  ldstr    aAllowrecreatef// "AllowRecreateForLogicallyDeletedRowInAc"...
0x8604e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86053  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86058  brfalse.s loc_86076
0x8605a  ldarg.1
0x8605b  ldstr    aAllowrecreatef// "AllowRecreateForLogicallyDeletedRowInAc"...
0x86060  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86065  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8606a  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x8606f  call     bool [mscorlib]System.Boolean::Parse(string)
0x86074  br.s     loc_86077
0x86076  ldc.i4.0
0x86077  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_AllowRecreateForLogicallyDeletedRowInActiveSolution(bool value)
0x8607c  dup
0x8607d  ldarg.1
0x8607e  ldstr    aIsviewable// "IsViewable"
0x86083  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86088  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8608d  brfalse.s loc_860AB
0x8608f  ldarg.1
0x86090  ldstr    aIsviewable// "IsViewable"
0x86095  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8609a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8609f  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x860a4  call     bool [mscorlib]System.Boolean::Parse(string)
0x860a9  br.s     loc_860AC
0x860ab  ldc.i4.0
0x860ac  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_IsViewable(bool value)
0x860b1  dup
0x860b2  ldarg.1
0x860b3  ldstr    aIsmergeable// "IsMergeable"
0x860b8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x860bd  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x860c2  brfalse.s loc_860E0
0x860c4  ldarg.1
0x860c5  ldstr    aIsmergeable// "IsMergeable"
0x860ca  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x860cf  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x860d4  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x860d9  call     bool [mscorlib]System.Boolean::Parse(string)
0x860de  br.s     loc_860E1
0x860e0  ldc.i4.0
0x860e1  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_IsMergeable(bool value)
0x860e6  dup
0x860e7  ldarg.1
0x860e8  ldstr    aDependencycalc// "DependencyCalculatorAssembly"
0x860ed  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x860f2  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x860f7  brfalse.s loc_86110
0x860f9  ldarg.1
0x860fa  ldstr    aDependencycalc// "DependencyCalculatorAssembly"
0x860ff  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86104  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86109  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x8610e  br.s     loc_86115
0x86110  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x86115  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_DependencyCalculatorAssembly(string value)
0x8611a  dup
0x8611b  ldarg.1
0x8611c  ldstr    aDependencycalc_0// "DependencyCalculatorClass"
0x86121  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86126  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8612b  brfalse.s loc_86144
0x8612d  ldarg.1
0x8612e  ldstr    aDependencycalc_0// "DependencyCalculatorClass"
0x86133  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86138  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8613d  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x86142  br.s     loc_86149
0x86144  ldstr    aMicrosoftCrmOb_7// "Microsoft.Crm.ObjectModel.EmptyDependen"...
0x86149  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_DependencyCalculatorClass(string value)
0x8614e  dup
0x8614f  ldarg.1
0x86150  ldstr    aDependencyhelp// "DependencyHelperClass"
0x86155  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8615a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8615f  brfalse.s loc_86178
0x86161  ldarg.1
0x86162  ldstr    aDependencyhelp// "DependencyHelperClass"
0x86167  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8616c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86171  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x86176  br.s     loc_8617D
0x86178  ldstr    aMicrosoftCrmOb_8// "Microsoft.Crm.ObjectModel.DependencyHel"...
0x8617d  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_DependencyHelperClass(string value)
0x86182  dup
0x86183  ldarg.1
0x86184  ldstr    aDependencydisa// "DependencyDisabled"
0x86189  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8618e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86193  brfalse.s loc_861B1
0x86195  ldarg.1
0x86196  ldstr    aDependencydisa// "DependencyDisabled"
0x8619b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x861a0  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x861a5  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x861aa  call     bool [mscorlib]System.Boolean::Parse(string)
0x861af  br.s     loc_861B2
0x861b1  ldc.i4.0
0x861b2  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_DependencyDisabled(bool value)
0x861b7  dup
0x861b8  ldarg.1
0x861b9  ldstr    aHasparent// "HasParent"
0x861be  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x861c3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x861c8  brfalse.s loc_861E6
0x861ca  ldarg.1
0x861cb  ldstr    aHasparent// "HasParent"
0x861d0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x861d5  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x861da  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x861df  call     bool [mscorlib]System.Boolean::Parse(string)
0x861e4  br.s     loc_861E7
0x861e6  ldc.i4.0
0x861e7  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_HasParent(bool value)
0x861ec  dup
0x861ed  ldarg.1
0x861ee  ldstr    aParentattribut_0// "ParentAttributeName"
0x861f3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x861f8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x861fd  brfalse.s loc_86216
0x861ff  ldarg.1
0x86200  ldstr    aParentattribut_0// "ParentAttributeName"
0x86205  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8620a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8620f  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x86214  br.s     loc_8621B
0x86216  ldsfld   string [mscorlib]System.String::Empty
0x8621b  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_ParentAttributeName(string value)
0x86220  dup
0x86221  ldarg.1
0x86222  ldstr    aGroupparentcom_5// "GroupParentComponentAttributeName"
0x86227  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8622c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86231  brfalse.s loc_8624A
0x86233  ldarg.1
0x86234  ldstr    aGroupparentcom_5// "GroupParentComponentAttributeName"
0x86239  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8623e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86243  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x86248  br.s     loc_8624F
0x8624a  ldsfld   string [mscorlib]System.String::Empty
0x8624f  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_GroupParentComponentAttributeName(string value)
0x86254  dup
0x86255  ldarg.1
0x86256  ldstr    aGroupparentcom_6// "GroupParentComponentType"
0x8625b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86260  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86265  brfalse.s loc_86288
0x86267  ldarg.1
0x86268  ldstr    aGroupparentcom_6// "GroupParentComponentType"
0x8626d  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x86272  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x86277  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x8627c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86281  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x86286  br.s     loc_86289
0x86288  ldc.i4.m1
0x86289  callvirt instance void Microsoft.Crm.Dependency.ComponentDefinition::set_GroupParentComponentType(int32 value)
0x8628e  dup
0x8628f  ldarg.1
0x86290  ldstr    aViewabledescen_0// "ViewableDescendentComponentType"
0x86295  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x8629a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x8629f  brfalse.s loc_862C2
0x862a1  ldarg.1
0x862a2  ldstr    aViewabledescen_0// "ViewableDescendentComponentType"
0x862a7  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x862ac  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x862b1  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x862b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x862bb  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x862c0  br.s     loc_862C3
  ... truncated ...
```
