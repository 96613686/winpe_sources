# Microsoft.Crm.Asynchronous.ServerConfiguration::<HandleNotification>b__156_0

- ea: `0xd170`
- end: `0xd1e3`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::<HandleNotification>b__156_0`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xd170`

## string_xrefs

- `0xd1b6`: `Server configuration updated. There are {0} active organizations, {1} total.`

## pseudocode

```c

```

## disassembly

```asm
0xd170  ldc.i4.0
0xd171  stloc.0
0xd172  ldarg.0
0xd173  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xd178  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Values()
0xd17d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0xd182  stloc.1
0xd183  br.s     loc_D198
0xd185  ldloca.s 1
0xd187  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0xd18c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0xd191  ldc.i4.1
0xd192  bne.un.s loc_D198
0xd194  ldloc.0
0xd195  ldc.i4.1
0xd196  add
0xd197  stloc.0
0xd198  ldloca.s 1
0xd19a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::MoveNext()
0xd19f  brtrue.s loc_D185
0xd1a1  leave.s  loc_D1B1
0xd1a3  ldloca.s 1
0xd1a5  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>
0xd1ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1b0  endfinally
0xd1b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd1b6  ldstr    aServerConfigur// "Server configuration updated. There are"...
0xd1bb  ldc.i4.2
0xd1bc  newarr   [mscorlib]System.Object
0xd1c1  dup
0xd1c2  ldc.i4.0
0xd1c3  ldloc.0
0xd1c4  box      [mscorlib]System.Int32
0xd1c9  stelem.ref
0xd1ca  dup
0xd1cb  ldc.i4.1
0xd1cc  ldarg.0
0xd1cd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xd1d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Count()
0xd1d7  box      [mscorlib]System.Int32
0xd1dc  stelem.ref
0xd1dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd1e2  ret
```
