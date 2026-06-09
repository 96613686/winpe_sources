# Microsoft.Crm.Setup.Common.CommonResource::.cctor

- ea: `0xfd0`
- end: `0xfef`
- name: `Microsoft.Crm.Setup.Common.CommonResource::.cctor`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0xfd0`: `Microsoft.Crm.Setup.Common.CommonResource`

## pseudocode

```c

```

## disassembly

```asm
0xfd0  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Setup.Common.CommonResour"...
0xfd5  ldtoken  Microsoft.Crm.Setup.Common.CommonResource
0xfda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfdf  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xfe4  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xfe9  stsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.CommonResource::resourceManager
0xfee  ret
```
