# Microsoft.Crm.ServiceBus.TokenProvider::AccessControlPath

- ea: `0x5c50`
- end: `0x5c95`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::AccessControlPath`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x55a0`
- `0x5750`

## callees

- `0x5c50`

## pseudocode

```c

```

## disassembly

```asm
0x5c50  ldarg.1
0x5c51  call     class [System]System.Uri [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::CreateAccessControlUri(string)
0x5c56  stloc.0
0x5c57  ldarg.2
0x5c58  brtrue.s loc_5C93
0x5c5a  ldloc.0
0x5c5b  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0x5c60  stloc.1
0x5c61  ldloc.1
0x5c62  ldloc.0
0x5c63  callvirt instance string [System]System.Uri::get_Host()
0x5c68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c6d  ldstr    a0Sb// "{0}-sb"
0x5c72  ldc.i4.1
0x5c73  newarr   [mscorlib]System.Object
0x5c78  dup
0x5c79  ldc.i4.0
0x5c7a  ldarg.1
0x5c7b  stelem.ref
0x5c7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5c81  ldarg.1
0x5c82  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x5c87  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x5c8c  ldloc.1
0x5c8d  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x5c92  stloc.0
0x5c93  ldloc.0
0x5c94  ret
```
