# Microsoft.Crm.Workflow.InteractionActivityResult::InteractionActivityResponseXml

- ea: `0xe820`
- end: `0xe8d1`
- name: `Microsoft.Crm.Workflow.InteractionActivityResult::InteractionActivityResponseXml`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x188b0`

## callees

- `0xe2b0`
- `0xe670`
- `0xe6b0`
- `0xe6f0`
- `0xe820`
- `0xeda0`
- `0xeec0`

## pseudocode

```c

```

## disassembly

```asm
0xe820  ldc.i4.6
0xe821  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(int32)
0xe826  stloc.0
0xe827  ldloc.0
0xe828  ldstr    aPrompttext// "promptText"
0xe82d  ldarg.0
0xe82e  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_PromptText()
0xe833  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe838  ldarg.1
0xe839  brfalse.s loc_E8B5
0xe83b  ldloc.0
0xe83c  ldstr    aLabel// "label"
0xe841  ldarg.0
0xe842  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_Label()
0xe847  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe84c  ldloc.0
0xe84d  ldstr    aType// "type"
0xe852  ldarg.0
0xe853  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe858  call     string Microsoft.Crm.Workflow.PageTypeConvertors::GetResponseMetadata(int32 responseMetadataType)
0xe85d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe862  ldarg.0
0xe863  call     instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0xe868  brfalse.s loc_E8A3
0xe86a  ldarg.0
0xe86b  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe870  ldc.i4.4
0xe871  beq.s    loc_E87C
0xe873  ldarg.0
0xe874  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe879  ldc.i4.3
0xe87a  bne.un.s loc_E88B
0xe87c  ldarg.0
0xe87d  ldloc.0
0xe87e  ldarg.0
0xe87f  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe884  call     instance void Microsoft.Crm.Workflow.InteractionActivityResult::PopulateAttributesForDateTime(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> attributes, int32 responseMetadataType)
0xe889  br.s     loc_E8C5
0xe88b  ldloc.0
0xe88c  ldstr    aValue// "value"
0xe891  ldarg.0
0xe892  call     instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0xe897  callvirt instance string [mscorlib]System.Object::ToString()
0xe89c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe8a1  br.s     loc_E8C5
0xe8a3  ldloc.0
0xe8a4  ldstr    aValue// "value"
0xe8a9  ldstr    asc_30690// ""
0xe8ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe8b3  br.s     loc_E8C5
0xe8b5  ldloc.0
0xe8b6  ldstr    aDonotlogrespon// "donotlogresponse"
0xe8bb  ldstr    aTrue// "true"
0xe8c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xe8c5  ldstr    aInteractionres// "interactionResponse"
0xe8ca  ldloc.0
0xe8cb  call     string Microsoft.Crm.Workflow.XmlUtility::BuildXmlNode(string elementName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> attributes)
0xe8d0  ret
```
