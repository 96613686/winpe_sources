# Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::InternalExecute

- ea: `0x1e90`
- end: `0x1f10`
- name: `Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::InternalExecute`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d00`
- `0x1d10`
- `0x1e90`
- `0x1f10`

## string_xrefs

- `0x1ea1`: `Could not retrieve the CRM Website path (ISV folder) from the registry.`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  call     instance string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::TryFindCRMWebPathFromRegistry()
0x1e96  stloc.0
0x1e97  ldloc.0
0x1e98  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1e9d  brfalse.s loc_1EB2
0x1e9f  ldarg.0
0x1ea0  ldarg.1
0x1ea1  ldstr    aCouldNotRetrie// "Could not retrieve the CRM Website path"...
0x1ea6  ldc.i4.0
0x1ea7  newarr   [mscorlib]System.Object
0x1eac  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x1eb1  ret
0x1eb2  ldloc.0
0x1eb3  ldstr    aIsv// "ISV"
0x1eb8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ebd  stloc.1
0x1ebe  ldloc.1
0x1ebf  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1ec4  brfalse.s loc_1F0F
0x1ec6  ldloc.1
0x1ec7  ldstr    asc_1C732// "*.*"
0x1ecc  ldc.i4.0
0x1ecd  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [mscorlib]System.IO.Directory::EnumerateFileSystemEntries(string, string, valuetype [mscorlib]System.IO.SearchOption)
0x1ed2  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__0_0
0x1ed7  dup
0x1ed8  brtrue.s loc_1EF1
0x1eda  pop
0x1edb  ldsfld   class <>c <>c::<>9
0x1ee0  ldftn    instance bool <>c::<InternalExecute>b__0_0(string fname)
0x1ee6  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x1eeb  dup
0x1eec  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__0_0
0x1ef1  call     T0x2B000001
0x1ef6  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1efb  brtrue.s loc_1F0F
0x1efd  ldarg.0
0x1efe  ldarg.1
0x1eff  ldstr    aIsvFolderUnder// "ISV folder under CRM Website contains o"...
0x1f04  ldc.i4.0
0x1f05  newarr   [mscorlib]System.Object
0x1f0a  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x1f0f  ret
```
