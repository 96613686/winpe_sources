# Microsoft.Crm.Sandbox.SandboxHostManager::UpdateFCBFeatureFlags

- ea: `0x1600`
- end: `0x1641`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::UpdateFCBFeatureFlags`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1470`

## callees

- `0x1600`
- `0x1ac0`

## pseudocode

```c

```

## disassembly

```asm
0x1600  ldsfld   string[] Microsoft.Crm.Sandbox.SandboxHostManager::_fcbKeyNames
0x1605  stloc.0
0x1606  ldc.i4.0
0x1607  stloc.1
0x1608  br.s     loc_163A
0x160a  ldloc.0
0x160b  ldloc.1
0x160c  ldelem.ref
0x160d  stloc.2
0x160e  ldc.i4.0
0x160f  stloc.3
0x1610  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1615  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x161a  ldc.i4.2
0x161b  bne.un.s loc_162A
0x161d  ldloc.2
0x161e  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabled(string)
0x1623  brtrue.s loc_1628
0x1625  ldc.i4.0
0x1626  br.s     loc_1629
0x1628  ldc.i4.1
0x1629  stloc.3
0x162a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHostManager::get_SandboxAdditionalInfo()
0x162f  ldloc.2
0x1630  ldloc.3
0x1631  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x1636  ldloc.1
0x1637  ldc.i4.1
0x1638  add
0x1639  stloc.1
0x163a  ldloc.1
0x163b  ldloc.0
0x163c  ldlen
0x163d  conv.i4
0x163e  blt.s    loc_160A
0x1640  ret
```
