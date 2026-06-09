# Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::SetAdminModeForTenantAdminInCrm

- ea: `0x117a0`
- end: `0x1183f`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::SetAdminModeForTenantAdminInCrm`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x11170`

## callees

- `0x117a0`

## string_xrefs

- `0x117a1`: `accessmode`
- `0x117b8`: `accessmode`
- `0x1180c`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x117a0  ldarg.0
0x117a1  ldstr    aAccessmode// "accessmode"
0x117a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x117ab  unbox.any [mscorlib]System.Int32
0x117b0  ldc.i4.4
0x117b1  bne.un.s loc_117B4
0x117b3  ret
0x117b4  ldarg.2
0x117b5  brfalse.s loc_1180B
0x117b7  ldarg.0
0x117b8  ldstr    aAccessmode// "accessmode"
0x117bd  ldarg.1
0x117be  brtrue.s loc_117C3
0x117c0  ldc.i4.1
0x117c1  br.s     loc_117C4
0x117c3  ldc.i4.0
0x117c4  box      [mscorlib]System.Int32
0x117c9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x117ce  ldarg.0
0x117cf  ldstr    aSetupuser// "setupuser"
0x117d4  ldarg.1
0x117d5  ldc.i4.0
0x117d6  ceq
0x117d8  box      [mscorlib]System.Boolean
0x117dd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x117e2  ldarg.0
0x117e3  ldstr    aIsdisabled// "isdisabled"
0x117e8  ldc.i4.0
0x117e9  box      [mscorlib]System.Boolean
0x117ee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x117f3  ldarg.0
0x117f4  ldstr    aCaltype// "caltype"
0x117f9  ldarg.1
0x117fa  brtrue.s loc_117FF
0x117fc  ldc.i4.1
0x117fd  br.s     loc_11800
0x117ff  ldc.i4.0
0x11800  box      [mscorlib]System.Int32
0x11805  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1180a  ret
0x1180b  ldarg.0
0x1180c  ldstr    aAccessmode// "accessmode"
0x11811  ldc.i4.0
0x11812  box      [mscorlib]System.Int32
0x11817  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1181c  ldarg.0
0x1181d  ldstr    aSetupuser// "setupuser"
0x11822  ldc.i4.0
0x11823  box      [mscorlib]System.Boolean
0x11828  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1182d  ldarg.0
0x1182e  ldstr    aCaltype// "caltype"
0x11833  ldc.i4.0
0x11834  box      [mscorlib]System.Int32
0x11839  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1183e  ret
```
