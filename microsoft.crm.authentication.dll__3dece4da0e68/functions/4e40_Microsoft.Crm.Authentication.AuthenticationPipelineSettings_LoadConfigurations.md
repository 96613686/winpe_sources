# Microsoft.Crm.Authentication.AuthenticationPipelineSettings::LoadConfigurations

- ea: `0x4e40`
- end: `0x4e87`
- name: `Microsoft.Crm.Authentication.AuthenticationPipelineSettings::LoadConfigurations`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3de0`
- `0x4e20`

## callees

- `0x4e40`
- `0x5060`
- `0x5080`

## pseudocode

```c

```

## disassembly

```asm
0x4e40  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x4e45  stloc.0
0x4e46  ldarg.0
0x4e47  brfalse.s loc_4E85
0x4e49  ldarg.0
0x4e4a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Authentication.AuthenticationConfigurationXml>::GetEnumerator()
0x4e4f  stloc.1
0x4e50  br.s     loc_4E6C
0x4e52  ldloca.s 1
0x4e54  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Authentication.AuthenticationConfigurationXml>::get_Current()
0x4e59  stloc.2
0x4e5a  ldloc.0
0x4e5b  ldloc.2
0x4e5c  callvirt instance string Microsoft.Crm.Authentication.AuthenticationConfigurationXml::get_Key()
0x4e61  ldloc.2
0x4e62  callvirt instance string Microsoft.Crm.Authentication.AuthenticationConfigurationXml::get_Value()
0x4e67  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x4e6c  ldloca.s 1
0x4e6e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Authentication.AuthenticationConfigurationXml>::MoveNext()
0x4e73  brtrue.s loc_4E52
0x4e75  leave.s  loc_4E85
0x4e77  ldloca.s 1
0x4e79  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Authentication.AuthenticationConfigurationXml>
0x4e7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e84  endfinally
0x4e85  ldloc.0
0x4e86  ret
```
