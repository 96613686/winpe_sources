# Microsoft.Crm.Asynchronous.ServerConfiguration::RaiseOrganizationsChangedEvent

- ea: `0xcb40`
- end: `0xcb77`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::RaiseOrganizationsChangedEvent`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc9d0`

## callees

- `0x7e80`
- `0xc120`
- `0xcb40`
- `0x11cf0`

## pseudocode

```c

```

## disassembly

```asm
0xcb40  ldarg.1
0xcb41  brfalse.s loc_CB5C
0xcb43  ldarg.0
0xcb44  ldfld    class Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.ServerConfiguration::backlogAnalyzer
0xcb49  brfalse.s loc_CB5C
0xcb4b  ldarg.0
0xcb4c  ldfld    class Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.ServerConfiguration::backlogAnalyzer
0xcb51  ldarg.0
0xcb52  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::get_AllOrganizationsToMonitor()
0xcb57  callvirt instance void Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer::UpdateOrganizations(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> organizations)
0xcb5c  ldarg.0
0xcb5d  ldfld    class [mscorlib]System.EventHandler Microsoft.Crm.Asynchronous.ServerConfiguration::OrganizationsChanged
0xcb62  brfalse.s loc_CB76
0xcb64  ldarg.0
0xcb65  ldfld    class [mscorlib]System.EventHandler Microsoft.Crm.Asynchronous.ServerConfiguration::OrganizationsChanged
0xcb6a  ldarg.0
0xcb6b  ldarg.1
0xcb6c  newobj   instance void Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> inactiveOrganizations)
0xcb71  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0xcb76  ret
```
