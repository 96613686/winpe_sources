# Microsoft.Crm.Application.Controls.OfficeWaffleInfo::.cctor

- ea: `0x5ff80`
- end: `0x5ffdb`
- name: `Microsoft.Crm.Application.Controls.OfficeWaffleInfo::.cctor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5ff8b`: `https://portal.devfabric.bosxlab.com:443/shell/ShellService.svc`
- `0x5ff9b`: `https://suite.officeppe.net:443/shell/shellservice.svc`
- `0x5ffab`: `https://suite.office.net:443/shell/ShellService.svc`
- `0x5ffcb`: `https://suite.office.net:443/shell/ShellService.svc`
- `0x5ffbb`: `https://suite.officeppe.net:443/shell/ShellService.svc`

## pseudocode

```c

```

## disassembly

```asm
0x5ff80  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x5ff85  dup
0x5ff86  ldstr    aTest// "test"
0x5ff8b  ldstr    aHttpsPortalDev// "https://portal.devfabric.bosxlab.com:44"...
0x5ff90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5ff95  dup
0x5ff96  ldstr    aPpe// "ppe"
0x5ff9b  ldstr    aHttpsSuiteOffi// "https://suite.officeppe.net:443/shell/s"...
0x5ffa0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5ffa5  dup
0x5ffa6  ldstr    aProd// "prod"
0x5ffab  ldstr    aHttpsSuiteOffi_0// "https://suite.office.net:443/shell/Shel"...
0x5ffb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5ffb5  dup
0x5ffb6  ldstr    aInt// "int"
0x5ffbb  ldstr    aHttpsSuiteOffi_1// "https://suite.officeppe.net:443/shell/S"...
0x5ffc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5ffc5  dup
0x5ffc6  ldstr    aGcc// "gcc"
0x5ffcb  ldstr    aHttpsSuiteOffi_0// "https://suite.office.net:443/shell/Shel"...
0x5ffd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5ffd5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Controls.OfficeWaffleInfo::_shellServices
0x5ffda  ret
```
