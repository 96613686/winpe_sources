# Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1::GetParentAssembly

- ea: `0x68c00`
- end: `0x68cea`
- name: `Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1::GetParentAssembly`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x68c00`

## string_xrefs

- `0x68c07`: `pluginassemblyid`
- `0x68c24`: `pluginassemblyid`
- `0x68caa`: `pluginassemblyid`
- `0x68cd3`: `pluginassemblyid`
- `0x68c74`: `publickeytoken`
- `0x68c39`: `PluginAssembly`
- `0x68cb9`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x68c00  ldarg.0
0x68c01  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::_pluginAssemblyCache
0x68c06  ldarg.1
0x68c07  ldstr    aPluginassembly// "pluginassemblyid"
0x68c0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68c11  unbox.any [mscorlib]System.Guid
0x68c16  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::ContainsKey(var<u1>)
0x68c1b  brfalse.s loc_68C39
0x68c1d  ldarg.0
0x68c1e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::_pluginAssemblyCache
0x68c23  ldarg.1
0x68c24  ldstr    aPluginassembly// "pluginassemblyid"
0x68c29  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68c2e  unbox.any [mscorlib]System.Guid
0x68c33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::get_Item(void)
0x68c38  ret
0x68c39  ldstr    aPluginassembly_0// "PluginAssembly"
0x68c3e  ldarg.2
0x68c3f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x68c44  stloc.0
0x68c45  ldloc.0
0x68c46  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x68c4b  ldc.i4.s 0xA
0x68c4d  newarr   [mscorlib]System.String
0x68c52  dup
0x68c53  ldc.i4.0
0x68c54  ldstr    aContent// "content"
0x68c59  stelem.ref
0x68c5a  dup
0x68c5b  ldc.i4.1
0x68c5c  ldstr    aPath// "path"
0x68c61  stelem.ref
0x68c62  dup
0x68c63  ldc.i4.2
0x68c64  ldstr    aVersion// "version"
0x68c69  stelem.ref
0x68c6a  dup
0x68c6b  ldc.i4.3
0x68c6c  ldstr    aCulture// "culture"
0x68c71  stelem.ref
0x68c72  dup
0x68c73  ldc.i4.4
0x68c74  ldstr    aPublickeytoken// "publickeytoken"
0x68c79  stelem.ref
0x68c7a  dup
0x68c7b  ldc.i4.5
0x68c7c  ldstr    aName// "name"
0x68c81  stelem.ref
0x68c82  dup
0x68c83  ldc.i4.6
0x68c84  ldstr    aSourcetype// "sourcetype"
0x68c89  stelem.ref
0x68c8a  dup
0x68c8b  ldc.i4.7
0x68c8c  ldstr    aCustomizationl// "customizationlevel"
0x68c91  stelem.ref
0x68c92  dup
0x68c93  ldc.i4.8
0x68c94  ldstr    aIsolationmode// "isolationmode"
0x68c99  stelem.ref
0x68c9a  dup
0x68c9b  ldc.i4.s 9
0x68c9d  ldstr    aIshidden// "ishidden"
0x68ca2  stelem.ref
0x68ca3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x68ca8  ldarg.0
0x68ca9  ldarg.1
0x68caa  ldstr    aPluginassembly// "pluginassemblyid"
0x68caf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68cb4  unbox.any [mscorlib]System.Guid
0x68cb9  ldstr    aPluginassembly_0// "PluginAssembly"
0x68cbe  ldarg.2
0x68cbf  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x68cc4  ldloc.0
0x68cc5  ldarg.2
0x68cc6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x68ccb  stloc.1
0x68ccc  ldarg.0
0x68ccd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::_pluginAssemblyCache
0x68cd2  ldarg.1
0x68cd3  ldstr    aPluginassembly// "pluginassemblyid"
0x68cd8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68cdd  unbox.any [mscorlib]System.Guid
0x68ce2  ldloc.1
0x68ce3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::set_Item(var<u1>, !!T0)
0x68ce8  ldloc.1
0x68ce9  ret
```
