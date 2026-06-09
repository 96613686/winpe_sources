# Microsoft.Crm.Tools.Admin.NonPlatformSolutionEntities::.cctor

- ea: `0x103d0`
- end: `0x1041d`
- name: `Microsoft.Crm.Tools.Admin.NonPlatformSolutionEntities::.cctor`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x103e1`: `topicmodelconfiguration`
- `0x103ec`: `contracttemplate`
- `0x103f7`: `recommendationmodel`
- `0x10402`: `recommendationmodelmapping`
- `0x1040d`: `recommendationmodelmapping`

## pseudocode

```c

```

## disassembly

```asm
0x103d0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x103d5  dup
0x103d6  ldstr    aTextanalyticse// "textanalyticsentitymapping"
0x103db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x103e0  dup
0x103e1  ldstr    aTopicmodelconf// "topicmodelconfiguration"
0x103e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x103eb  dup
0x103ec  ldstr    aContracttempla// "contracttemplate"
0x103f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x103f6  dup
0x103f7  ldstr    aRecommendation// "recommendationmodel"
0x103fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10401  dup
0x10402  ldstr    aRecommendation_0// "recommendationmodelmapping"
0x10407  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1040c  dup
0x1040d  ldstr    aRecommendation_0// "recommendationmodelmapping"
0x10412  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10417  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Admin.NonPlatformSolutionEntities::Entities
0x1041c  ret
```
