# <>c::<DisableYammer>b__99_0

- ea: `0x32880`
- end: `0x328f5`
- name: `<>c::<DisableYammer>b__99_0`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x328ae`: `yammernetworkpermalink`
- `0x328de`: `yammeroauthaccesstokenexpired`

## pseudocode

```c

```

## disassembly

```asm
0x32880  ldstr    aOrganization// "Organization"
0x32885  ldarg.1
0x32886  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3288b  ldarg.1
0x3288c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x32891  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization::.ctor(valuetype [mscorlib]System.Guid)
0x32896  stloc.0
0x32897  ldloc.0
0x32898  ldstr    aOrganizationid_1// "organizationid"
0x3289d  ldarg.1
0x3289e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x328a3  box      [mscorlib]System.Guid
0x328a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x328ad  ldloc.0
0x328ae  ldstr    aYammernetworkp// "yammernetworkpermalink"
0x328b3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x328b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x328bd  ldloc.0
0x328be  ldstr    aYammergroupid// "yammergroupid"
0x328c3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x328c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x328cd  ldloc.0
0x328ce  ldstr    aYammerpostmeth// "yammerpostmethod"
0x328d3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x328d8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x328dd  ldloc.0
0x328de  ldstr    aYammeroauthacc// "yammeroauthaccesstokenexpired"
0x328e3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x328e8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x328ed  ldloc.0
0x328ee  ldarg.1
0x328ef  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x328f4  ret
```
