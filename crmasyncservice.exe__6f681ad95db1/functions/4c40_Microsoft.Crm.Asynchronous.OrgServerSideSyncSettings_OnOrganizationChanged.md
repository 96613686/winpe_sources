# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::OnOrganizationChanged

- ea: `0x4c40`
- end: `0x4c91`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::OnOrganizationChanged`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4c40`
- `0x4ca0`
- `0x4cb0`

## pseudocode

```c

```

## disassembly

```asm
0x4c40  ldarg.1
0x4c41  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs
0x4c46  stloc.0
0x4c47  ldloc.0
0x4c48  brfalse.s loc_4C90
0x4c4a  ldloc.0
0x4c4b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::get_InactiveOrganizations()
0x4c50  brfalse.s loc_4C90
0x4c52  ldloc.0
0x4c53  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::get_InactiveOrganizations()
0x4c58  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Keys()
0x4c5d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0x4c62  stloc.1
0x4c63  br.s     loc_4C77
0x4c65  ldloca.s 1
0x4c67  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0x4c6c  dup
0x4c6d  call     void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromOrgSettingsLightCache(valuetype [mscorlib]System.Guid organizationId)
0x4c72  call     void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromQueueSettingsCache(valuetype [mscorlib]System.Guid organizationId)
0x4c77  ldloca.s 1
0x4c79  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::MoveNext()
0x4c7e  brtrue.s loc_4C65
0x4c80  leave.s  loc_4C90
0x4c82  ldloca.s 1
0x4c84  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>
0x4c8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c8f  endfinally
0x4c90  ret
```
