# Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::GetConvertRuleItemProperties

- ea: `0x91280`
- end: `0x91351`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::GetConvertRuleItemProperties`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x91090`

## callees

- `0x91280`
- `0x91450`

## string_xrefs

- `0x912e4`: `ConditionXml`
- `0x912e9`: `conditionxml`
- `0x91308`: `PropertiesXml`
- `0x9130d`: `propertiesxml`

## pseudocode

```c

```

## disassembly

```asm
0x91280  ldarg.0
0x91281  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x91286  brtrue   loc_9134A
0x9128b  ldarg.0
0x9128c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::.ctor()
0x91291  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x91296  ldarg.0
0x91297  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x9129c  ldstr    aDescription_0// "Description"
0x912a1  ldstr    aDescription// "description"
0x912a6  ldtoken  [mscorlib]System.String
0x912ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x912b0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x912b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::Add(var<u1>)
0x912ba  ldarg.0
0x912bb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x912c0  ldstr    aConvertruleid_0// "ConvertRuleId"
0x912c5  ldstr    aConvertruleid// "convertruleid"
0x912ca  ldtoken  [mscorlib]System.Guid
0x912cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x912d4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x912d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::Add(var<u1>)
0x912de  ldarg.0
0x912df  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x912e4  ldstr    aConditionxml// "ConditionXml"
0x912e9  ldstr    aConditionxml_0// "conditionxml"
0x912ee  ldtoken  [mscorlib]System.String
0x912f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x912f8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x912fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::Add(var<u1>)
0x91302  ldarg.0
0x91303  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x91308  ldstr    aPropertiesxml// "PropertiesXml"
0x9130d  ldstr    aPropertiesxml_0// "propertiesxml"
0x91312  ldtoken  [mscorlib]System.String
0x91317  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9131c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x91321  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::Add(var<u1>)
0x91326  ldarg.0
0x91327  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x9132c  ldstr    aWorkflowid// "WorkflowId"
0x91331  ldstr    aWorkflowid_0// "workflowid"
0x91336  ldtoken  [mscorlib]System.Guid
0x9133b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91340  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x91345  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap>::Add(var<u1>)
0x9134a  ldarg.0
0x9134b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemConvertor::_convertRuleItemProperties
0x91350  ret
```
