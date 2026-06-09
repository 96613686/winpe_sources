# Microsoft.Crm.CrmLive.Provisioning.Organization::.cctor

- ea: `0x18470`
- end: `0x1851e`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::.cctor`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18470`

## string_xrefs

- `0x18492`: `SqlAccessGroup`
- `0x1849a`: `PrivilegedUserGroup`

## pseudocode

```c

```

## disassembly

```asm
0x18470  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x18475  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.CrmLive.Provisioning.Organization::_config
0x1847a  ldc.i4.7
0x1847b  newarr   [mscorlib]System.String
0x18480  dup
0x18481  ldc.i4.0
0x18482  ldstr    aPrivreportingg// "PrivReportingGroup"
0x18487  stelem.ref
0x18488  dup
0x18489  ldc.i4.1
0x1848a  ldstr    aReportinggroup// "ReportingGroup"
0x1848f  stelem.ref
0x18490  dup
0x18491  ldc.i4.2
0x18492  ldstr    aSqlaccessgroup// "SqlAccessGroup"
0x18497  stelem.ref
0x18498  dup
0x18499  ldc.i4.3
0x1849a  ldstr    aPrivilegeduser// "PrivilegedUserGroup"
0x1849f  stelem.ref
0x184a0  dup
0x184a1  ldc.i4.4
0x184a2  ldstr    aReportserverur// "ReportServerUrl"
0x184a7  stelem.ref
0x184a8  dup
0x184a9  ldc.i4.5
0x184aa  ldstr    aCrmserver// "CrmServer"
0x184af  stelem.ref
0x184b0  dup
0x184b1  ldc.i4.6
0x184b2  ldstr    aSqlserver// "SqlServer"
0x184b7  stelem.ref
0x184b8  stsfld   string[] Microsoft.Crm.CrmLive.Provisioning.Organization::_settings
0x184bd  ldsfld   string[] Microsoft.Crm.CrmLive.Provisioning.Organization::_settings
0x184c2  stloc.0
0x184c3  ldc.i4.0
0x184c4  stloc.1
0x184c5  br.s     loc_18517
0x184c7  ldloc.0
0x184c8  ldloc.1
0x184c9  ldelem.ref
0x184ca  stloc.2
0x184cb  ldstr    aSettingoverrid// "SettingOverride_"
0x184d0  ldloc.2
0x184d1  call     string [mscorlib]System.String::Concat(string, string)
0x184d6  ldsfld   string [mscorlib]System.String::Empty
0x184db  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x184e0  castclass [mscorlib]System.String
0x184e5  stloc.3
0x184e6  ldloc.3
0x184e7  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x184ec  brtrue.s loc_184FC
0x184ee  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.CrmLive.Provisioning.Organization::_config
0x184f3  ldloc.2
0x184f4  ldloc.3
0x184f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x184fa  br.s     loc_18513
0x184fc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.CrmLive.Provisioning.Organization::_config
0x18501  ldloc.2
0x18502  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x18507  ldloc.2
0x18508  ldc.i4.0
0x18509  callvirt T0x2B000011
0x1850e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x18513  ldloc.1
0x18514  ldc.i4.1
0x18515  add
0x18516  stloc.1
0x18517  ldloc.1
0x18518  ldloc.0
0x18519  ldlen
0x1851a  conv.i4
0x1851b  blt.s    loc_184C7
0x1851d  ret
```
