# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::ComposeGenericEntityCollection

- ea: `0xe10`
- end: `0xe59`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::ComposeGenericEntityCollection`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xe10`

## pseudocode

```c

```

## disassembly

```asm
0xe10  nop
0xe11  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::.ctor()
0xe16  stloc.0
0xe17  nop
0xe18  ldarg.1
0xe19  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xe1e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xe23  stloc.1
0xe24  br.s     loc_E3E
0xe26  ldloc.1
0xe27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xe2c  stloc.2
0xe2d  nop
0xe2e  ldloc.0
0xe2f  ldarg.0
0xe30  ldloc.2
0xe31  ldarg.2
0xe32  call     T0x2B000012
0xe37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::Add(var<u1>)
0xe3c  nop
0xe3d  nop
0xe3e  ldloc.1
0xe3f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe44  brtrue.s loc_E26
0xe46  leave.s  loc_E53
0xe48  ldloc.1
0xe49  brfalse.s loc_E52
0xe4b  ldloc.1
0xe4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe51  nop
0xe52  endfinally
0xe53  ldloc.0
0xe54  stloc.3
0xe55  br.s     loc_E57
0xe57  ldloc.3
0xe58  ret
```
