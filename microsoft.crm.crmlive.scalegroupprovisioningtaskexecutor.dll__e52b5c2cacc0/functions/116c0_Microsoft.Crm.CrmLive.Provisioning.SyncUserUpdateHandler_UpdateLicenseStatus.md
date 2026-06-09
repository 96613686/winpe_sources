# Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateLicenseStatus

- ea: `0x116c0`
- end: `0x11759`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateLicenseStatus`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x11170`

## callees

- `0xff90`
- `0xffb0`
- `0xffd0`
- `0x10050`
- `0x10070`
- `0x10ec0`
- `0x116c0`
- `0x11770`

## string_xrefs

- `0x1173c`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x116c0  ldarg.2
0x116c1  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::IsUserLicensedInCrm(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity crmUser)
0x116c6  stloc.0
0x116c7  ldc.i4.0
0x116c8  stloc.1
0x116c9  ldarg.1
0x116ca  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsCrmServiceAdmin()
0x116cf  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x116d4  brfalse.s loc_116DE
0x116d6  ldarg.1
0x116d7  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_ShouldSync()
0x116dc  br.s     loc_116DF
0x116de  ldc.i4.0
0x116df  stloc.2
0x116e0  ldarg.1
0x116e1  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsSoftDelete()
0x116e6  brtrue.s loc_116FD
0x116e8  ldarg.3
0x116e9  ldarg.1
0x116ea  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x116ef  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x116f4  ldloc.2
0x116f5  or
0x116f6  ceq
0x116f8  ldc.i4.0
0x116f9  ceq
0x116fb  br.s     loc_116FE
0x116fd  ldc.i4.1
0x116fe  stloc.3
0x116ff  ldc.i4.0
0x11700  stloc.s  4
0x11702  ldarg.1
0x11703  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsSoftDelete()
0x11708  brtrue.s loc_11724
0x1170a  ldarg.1
0x1170b  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x11710  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x11715  brtrue.s loc_1171F
0x11717  ldarg.1
0x11718  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x1171d  br.s     loc_11720
0x1171f  ldc.i4.1
0x11720  ldloc.2
0x11721  or
0x11722  br.s     loc_11725
0x11724  ldc.i4.0
0x11725  stloc.s  4
0x11727  ldarg.1
0x11728  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x1172d  ldloc.0
0x1172e  ceq
0x11730  ldc.i4.0
0x11731  ceq
0x11733  ldloc.3
0x11734  or
0x11735  brfalse.s loc_11757
0x11737  ldarg.0
0x11738  ldarg.1
0x11739  ldloc.s  4
0x1173b  ldarg.2
0x1173c  ldstr    aAccessmode// "accessmode"
0x11741  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11746  unbox.any [mscorlib]System.Int32
0x1174b  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x11750  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserHandlerBase::ChangeCrmUserLicenseStatus(class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto data, bool active, valuetype [mscorlib]System.Nullable`1<int32> accessMode)
0x11755  ldc.i4.1
0x11756  stloc.1
0x11757  ldloc.1
0x11758  ret
```
