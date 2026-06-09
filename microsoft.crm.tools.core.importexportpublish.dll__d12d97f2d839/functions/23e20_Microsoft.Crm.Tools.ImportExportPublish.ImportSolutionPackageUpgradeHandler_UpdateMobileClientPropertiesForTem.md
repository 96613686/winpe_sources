# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateMobileClientPropertiesForTemplate

- ea: `0x23e20`
- end: `0x23e6d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdateMobileClientPropertiesForTemplate`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x24080`
- `0x63db0`

## string_xrefs

- `0x23e21`: `Template`
- `0x23e36`: `Template`
- `0x23e3b`: `IsReadOnlyInMobileClient`

## pseudocode

```c

```

## disassembly

```asm
0x23e20  ldarg.1
0x23e21  ldstr    aTemplate// "Template"
0x23e26  ldstr    aIsvisibleinmob_1// "IsVisibleInMobileClient"
0x23e2b  ldstr    a1// "1"
0x23e30  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntity(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityName, string propertyName, string value)
0x23e35  ldarg.1
0x23e36  ldstr    aTemplate// "Template"
0x23e3b  ldstr    aIsreadonlyinmo// "IsReadOnlyInMobileClient"
0x23e40  ldstr    a1// "1"
0x23e45  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionPackageUpgradeHandler::UpdatePropertyForEntity(class [System.Xml]System.Xml.XmlDocument customizationDoc, string entityName, string propertyName, string value)
0x23e4a  ldarg.s  6
0x23e4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23e51  ldstr    aExecutingSolut// "Executing solution package Upgrade hand"...
0x23e56  ldc.i4.1
0x23e57  newarr   [mscorlib]System.Object
0x23e5c  dup
0x23e5d  ldc.i4.0
0x23e5e  ldarg.s  4
0x23e60  stelem.ref
0x23e61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23e66  ldc.i4.1
0x23e67  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x23e6c  ret
```
