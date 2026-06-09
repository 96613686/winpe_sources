# Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::MoveUserImportMapsToActiveSolution

- ea: `0xabf0`
- end: `0xac67`
- name: `Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::MoveUserImportMapsToActiveSolution`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xabe0`

## callees

- `0xac70`

## string_xrefs

- `0xac38`: `UPDATE {0} SET SolutionId='{1}' WHERE SolutionId='{2}'`

## pseudocode

```c

```

## disassembly

```asm
0xabf0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xabf5  dup
0xabf6  ldstr    aImportmapbase// "ImportMapBase"
0xabfb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac00  dup
0xac01  ldstr    aColumnmappingb// "ColumnMappingBase"
0xac06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac0b  dup
0xac0c  ldstr    aTransformation// "TransformationMappingBase"
0xac11  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac16  dup
0xac17  ldstr    aTransformation_0// "TransformationParameterMappingBase"
0xac1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac21  dup
0xac22  ldstr    aLookupmappingb// "LookUpMappingBase"
0xac27  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac2c  dup
0xac2d  ldstr    aOwnermappingba// "OwnerMappingBase"
0xac32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac37  stloc.0
0xac38  ldstr    aUpdate0SetSolu// "UPDATE {0} SET SolutionId='{1}' WHERE S"...
0xac3d  ldarg.0
0xac3e  ldfld    string Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::_tableVariableToReplace
0xac43  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0xac48  box      [mscorlib]System.Guid
0xac4d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0xac52  box      [mscorlib]System.Guid
0xac57  call     string [mscorlib]System.String::Format(string, object, object, object)
0xac5c  stloc.1
0xac5d  ldarg.0
0xac5e  ldloc.0
0xac5f  ldloc.1
0xac60  ldarg.1
0xac61  call     instance void Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::ApplyQueryOnTables(class [mscorlib]System.Collections.Generic.List`1<string> tables, string query, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xac66  ret
```
