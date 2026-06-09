# Microsoft.Crm.Application.Utility.MetadataHelper::get_ServiceLookupAttributeMetadataFormatter

- ea: `0x3b940`
- end: `0x3b95f`
- name: `Microsoft.Crm.Application.Utility.MetadataHelper::get_ServiceLookupAttributeMetadataFormatter`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3c900`

## string_xrefs

- `0x3b940`: `Microsoft.Crm.Service.Application.Components.Platform`
- `0x3b94a`: `Microsoft.Crm.Service.Application.Utility.ServiceLookupAttributeMetadataFormatter`

## pseudocode

```c

```

## disassembly

```asm
0x3b940  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Compo"...
0x3b945  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x3b94a  ldstr    aMicrosoftCrmSe_2// "Microsoft.Crm.Service.Application.Utili"...
0x3b94f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x3b954  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3b959  castclass Microsoft.Crm.Application.Utility.IServiceLookupAttributeMetadataFormatter
0x3b95e  ret
```
