# Microsoft.Crm.Metadata.SecurityHelper::ShouldGenerateCrudPrivilegeForVirtualEntity

- ea: `0x59a00`
- end: `0x59aa4`
- name: `Microsoft.Crm.Metadata.SecurityHelper::ShouldGenerateCrudPrivilegeForVirtualEntity`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x599e0`

## callees

- `0x59a00`
- `0x77d10`

## string_xrefs

- `0x59a2d`: `retrieveplugin`
- `0x59a35`: `retrievemultipleplugin`
- `0x59a4a`: `createplugin`
- `0x59a5f`: `deleteplugin`
- `0x59a74`: `updateplugin`

## pseudocode

```c

```

## disassembly

```asm
0x59a00  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x59a05  stloc.0
0x59a06  ldloc.0
0x59a07  ldarg.0
0x59a08  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity <>c__DisplayClass10_0::provider
0x59a0d  ldloc.0
0x59a0e  ldstr    aC191997900214f// "c1919979-0021-4f11-a587-a8f904bdfdf9"
0x59a13  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x59a18  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass10_0::notImplementedPluginId
0x59a1d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::.ctor()
0x59a22  stloc.3
0x59a23  ldloc.3
0x59a24  ldc.i4.1
0x59a25  ldc.i4.2
0x59a26  newarr   [mscorlib]System.String
0x59a2b  dup
0x59a2c  ldc.i4.0
0x59a2d  ldstr    aRetrieveplugin// "retrieveplugin"
0x59a32  stelem.ref
0x59a33  dup
0x59a34  ldc.i4.1
0x59a35  ldstr    aRetrievemultip_0// "retrievemultipleplugin"
0x59a3a  stelem.ref
0x59a3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::Add(var<u1>, !!T0)
0x59a40  ldloc.3
0x59a41  ldc.i4.0
0x59a42  ldc.i4.1
0x59a43  newarr   [mscorlib]System.String
0x59a48  dup
0x59a49  ldc.i4.0
0x59a4a  ldstr    aCreateplugin// "createplugin"
0x59a4f  stelem.ref
0x59a50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::Add(var<u1>, !!T0)
0x59a55  ldloc.3
0x59a56  ldc.i4.3
0x59a57  ldc.i4.1
0x59a58  newarr   [mscorlib]System.String
0x59a5d  dup
0x59a5e  ldc.i4.0
0x59a5f  ldstr    aDeleteplugin// "deleteplugin"
0x59a64  stelem.ref
0x59a65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::Add(var<u1>, !!T0)
0x59a6a  ldloc.3
0x59a6b  ldc.i4.2
0x59a6c  ldc.i4.1
0x59a6d  newarr   [mscorlib]System.String
0x59a72  dup
0x59a73  ldc.i4.0
0x59a74  ldstr    aUpdateplugin// "updateplugin"
0x59a79  stelem.ref
0x59a7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::Add(var<u1>, !!T0)
0x59a7f  ldloc.3
0x59a80  ldc.i4.0
0x59a81  stloc.1
0x59a82  ldarg.1
0x59a83  ldloca.s 2
0x59a85  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, string[]>::TryGetValue(var<u1>, !!T0)
0x59a8a  brfalse.s loc_59AA2
0x59a8c  ldloc.2
0x59a8d  ldloc.0
0x59a8e  ldftn    instance bool <>c__DisplayClass10_0::<ShouldGenerateCrudPrivilegeForVirtualEntity>b__0(string providerColumnName)
0x59a94  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x59a99  call     T0x2B000047
0x59a9e  ldc.i4.0
0x59a9f  ceq
0x59aa1  stloc.1
0x59aa2  ldloc.1
0x59aa3  ret
```
