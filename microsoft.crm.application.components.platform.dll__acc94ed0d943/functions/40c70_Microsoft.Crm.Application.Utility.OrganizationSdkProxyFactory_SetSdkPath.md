# Microsoft.Crm.Application.Utility.OrganizationSdkProxyFactory::SetSdkPath

- ea: `0x40c70`
- end: `0x40cb6`
- name: `Microsoft.Crm.Application.Utility.OrganizationSdkProxyFactory::SetSdkPath`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x40b70`

## callees

- `0x39d70`
- `0x40c70`
- `0x446d0`
- `0x44940`

## string_xrefs

- `0x40c94`: `/XrmServices/2011/Organization.svc`
- `0x40ca6`: `/XrmServices/2011/Organization.svc`

## pseudocode

```c

```

## disassembly

```asm
0x40c70  call     bool Microsoft.Crm.Application.Utility.Util::IsLive()
0x40c75  brtrue.s loc_40C93
0x40c77  call     bool Microsoft.Crm.Application.Utility.Util::IsPathBasedURLsEnabled()
0x40c7c  brfalse.s loc_40C93
0x40c7e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x40c83  brfalse.s loc_40C9F
0x40c85  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInOfflineClientContext()
0x40c8a  brfalse.s loc_40C9F
0x40c8c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInPostOfflineUpgradeContext()
0x40c91  brtrue.s loc_40C9F
0x40c93  ldarg.0
0x40c94  ldstr    aXrmservices201// "/XrmServices/2011/Organization.svc"
0x40c99  callvirt instance void Microsoft.Crm.Application.Utility.CrmUri::set_Path(string value)
0x40c9e  ret
0x40c9f  ldarg.0
0x40ca0  ldstr    asc_AFF5A// "/"
0x40ca5  ldarg.1
0x40ca6  ldstr    aXrmservices201// "/XrmServices/2011/Organization.svc"
0x40cab  call     string [mscorlib]System.String::Concat(string, string, string)
0x40cb0  callvirt instance void Microsoft.Crm.Application.Utility.CrmUri::set_Path(string value)
0x40cb5  ret
```
