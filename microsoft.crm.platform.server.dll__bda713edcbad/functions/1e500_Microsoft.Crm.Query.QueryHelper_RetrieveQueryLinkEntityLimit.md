# Microsoft.Crm.Query.QueryHelper::RetrieveQueryLinkEntityLimit

- ea: `0x1e500`
- end: `0x1e55c`
- name: `Microsoft.Crm.Query.QueryHelper::RetrieveQueryLinkEntityLimit`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17660`
- `0x878e0`

## callees

- `0x1e500`
- `0x1e630`

## string_xrefs

- `0x1e514`: `QueryLinkEntityLimit`
- `0x1e538`: `QueryLinkEntityLimit`
- `0x1e545`: `QueryLinkEntityLimit`
- `0x1e51e`: `RetrieveQueryLinkEntityLimit`

## pseudocode

```c

```

## disassembly

```asm
0x1e500  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x1e505  brtrue.s loc_1E545
0x1e507  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x1e50c  brtrue.s loc_1E545
0x1e50e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x1e513  ldarg.0
0x1e514  ldstr    aQuerylinkentit// "QueryLinkEntityLimit"
0x1e519  ldc.i4   0x245
0x1e51e  ldstr    aRetrievequeryl// "RetrieveQueryLinkEntityLimit"
0x1e523  ldstr    aDA1SSrcManaged_3// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x1e528  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x1e52d  stloc.0
0x1e52e  ldloc.0
0x1e52f  brfalse.s loc_1E538
0x1e531  ldloc.0
0x1e532  unbox.any [mscorlib]System.Int32
0x1e537  ret
0x1e538  ldstr    aQuerylinkentit// "QueryLinkEntityLimit"
0x1e53d  ldc.i4.s 0xA
0x1e53f  call     int32 Microsoft.Crm.Query.QueryHelper::GetMaxQuerySetting(string settingName, int32 defaultValue)
0x1e544  ret
0x1e545  ldstr    aQuerylinkentit// "QueryLinkEntityLimit"
0x1e54a  ldc.i4.s 0xA
0x1e54c  box      [mscorlib]System.Int32
0x1e551  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1e556  unbox.any [mscorlib]System.Int32
0x1e55b  ret
```
