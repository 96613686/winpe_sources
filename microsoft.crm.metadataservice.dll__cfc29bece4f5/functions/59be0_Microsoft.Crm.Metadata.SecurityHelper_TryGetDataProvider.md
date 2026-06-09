# Microsoft.Crm.Metadata.SecurityHelper::TryGetDataProvider

- ea: `0x59be0`
- end: `0x59c53`
- name: `Microsoft.Crm.Metadata.SecurityHelper::TryGetDataProvider`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x59be0`

## string_xrefs

- `0x59c06`: `retrieveplugin`
- `0x59c0e`: `retrievemultipleplugin`
- `0x59c16`: `createplugin`
- `0x59c1e`: `deleteplugin`
- `0x59c26`: `updateplugin`

## pseudocode

```c

```

## disassembly

```asm
0x59be0  ldstr    aEntitydataprov// "EntityDataProvider"
0x59be5  ldarg.1
0x59be6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59beb  stloc.0
0x59bec  ldstr    aEntitydataprov// "EntityDataProvider"
0x59bf1  ldarg.1
0x59bf2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x59bf7  stloc.1
0x59bf8  ldloc.1
0x59bf9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x59bfe  ldc.i4.5
0x59bff  newarr   [mscorlib]System.String
0x59c04  dup
0x59c05  ldc.i4.0
0x59c06  ldstr    aRetrieveplugin// "retrieveplugin"
0x59c0b  stelem.ref
0x59c0c  dup
0x59c0d  ldc.i4.1
0x59c0e  ldstr    aRetrievemultip_0// "retrievemultipleplugin"
0x59c13  stelem.ref
0x59c14  dup
0x59c15  ldc.i4.2
0x59c16  ldstr    aCreateplugin// "createplugin"
0x59c1b  stelem.ref
0x59c1c  dup
0x59c1d  ldc.i4.3
0x59c1e  ldstr    aDeleteplugin// "deleteplugin"
0x59c23  stelem.ref
0x59c24  dup
0x59c25  ldc.i4.4
0x59c26  ldstr    aUpdateplugin// "updateplugin"
0x59c2b  stelem.ref
0x59c2c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x59c31  ldloc.0
0x59c32  ldarga.s 0
0x59c34  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x59c39  ldstr    aEntitydataprov// "EntityDataProvider"
0x59c3e  ldarg.1
0x59c3f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59c44  ldloc.1
0x59c45  ldarg.1
0x59c46  ldloca.s 2
0x59c48  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryRetrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity&)
0x59c4d  brtrue.s loc_59C51
0x59c4f  ldc.i4.1
0x59c50  ret
0x59c51  ldc.i4.0
0x59c52  ret
```
