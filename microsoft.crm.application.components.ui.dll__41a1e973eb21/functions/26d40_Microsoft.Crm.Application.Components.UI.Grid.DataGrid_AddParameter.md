# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter

- ea: `0x26d40`
- end: `0x26d7e`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter`
- size: `62`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x27000`
- `0x27090`
- `0x27100`
- `0x27190`
- `0x27200`
- `0x27250`
- `0x27380`
- `0x27420`
- `0x27480`
- `0x274d0`
- `0x27520`

## callees

- `0x26d40`

## pseudocode

```c

```

## disassembly

```asm
0x26d40  ldarg.0
0x26d41  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x26d46  brtrue.s loc_26D54
0x26d48  ldarg.0
0x26d49  ldc.i4.4
0x26d4a  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x26d4f  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x26d54  ldarg.0
0x26d55  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x26d5a  ldarg.1
0x26d5b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x26d60  brtrue.s loc_26D70
0x26d62  ldarg.0
0x26d63  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x26d68  ldarg.1
0x26d69  ldarg.2
0x26d6a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x26d6f  ret
0x26d70  ldarg.0
0x26d71  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x26d76  ldarg.1
0x26d77  ldarg.2
0x26d78  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x26d7d  ret
```
