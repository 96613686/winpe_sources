# Microsoft.Crm.Sdk.CrmSchemaFixer::.cctor

- ea: `0xa5d0`
- end: `0xa6bb`
- name: `Microsoft.Crm.Sdk.CrmSchemaFixer::.cctor`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update, broker_com_uri`

## string_xrefs

- `0xa5df`: `Create`
- `0xa5ff`: `Delete`
- `0xa69f`: `Update`
- `0xa5ef`: `CreateResponse`
- `0xa60f`: `DeleteResponse`
- `0xa6af`: `UpdateResponse`

## pseudocode

```c

```

## disassembly

```asm
0xa5d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xa5d5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa5da  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa5df  ldstr    aCreate// "Create"
0xa5e4  ldnull
0xa5e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa5ea  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa5ef  ldstr    aCreateresponse// "CreateResponse"
0xa5f4  ldnull
0xa5f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa5fa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa5ff  ldstr    aDelete// "Delete"
0xa604  ldnull
0xa605  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa60a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa60f  ldstr    aDeleteresponse// "DeleteResponse"
0xa614  ldnull
0xa615  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa61a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa61f  ldstr    aExecute// "Execute"
0xa624  ldnull
0xa625  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa62a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa62f  ldstr    aExecuterespons// "ExecuteResponse"
0xa634  ldnull
0xa635  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa63a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa63f  ldstr    aFetch// "Fetch"
0xa644  ldnull
0xa645  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa64a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa64f  ldstr    aFetchresponse// "FetchResponse"
0xa654  ldnull
0xa655  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa65a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa65f  ldstr    aRetrieve// "Retrieve"
0xa664  ldnull
0xa665  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa66a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa66f  ldstr    aRetrieverespon// "RetrieveResponse"
0xa674  ldnull
0xa675  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa67a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa67f  ldstr    aRetrievemultip// "RetrieveMultiple"
0xa684  ldnull
0xa685  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa68a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa68f  ldstr    aRetrievemultip_0// "RetrieveMultipleResponse"
0xa694  ldnull
0xa695  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa69a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa69f  ldstr    aUpdate// "Update"
0xa6a4  ldnull
0xa6a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa6aa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sdk.CrmSchemaFixer::_elementsToKeep
0xa6af  ldstr    aUpdateresponse// "UpdateResponse"
0xa6b4  ldnull
0xa6b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa6ba  ret
```
