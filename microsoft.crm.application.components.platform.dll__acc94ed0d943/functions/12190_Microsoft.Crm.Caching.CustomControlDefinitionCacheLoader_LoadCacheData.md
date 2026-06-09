# Microsoft.Crm.Caching.CustomControlDefinitionCacheLoader::LoadCacheData

- ea: `0x12190`
- end: `0x12241`
- name: `Microsoft.Crm.Caching.CustomControlDefinitionCacheLoader::LoadCacheData`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12190`
- `0x5be20`
- `0x94440`
- `0x94500`

## string_xrefs

- `0x121b4`: `manifest`
- `0x12204`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x12190  ldstr    aGetcustomcontr_0// "GetCustomControlDefinition"
0x12195  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x1219a  stloc.0
0x1219b  ldloc.0
0x1219c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x121a1  ldnull
0x121a2  stloc.1
0x121a3  ldstr    aCustomcontrol// "customcontrol"
0x121a8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x121ad  stloc.2
0x121ae  ldloc.2
0x121af  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x121b4  ldstr    aManifest// "manifest"
0x121b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x121be  ldloc.2
0x121bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x121c4  ldstr    aCustomcontroli// "customcontrolid"
0x121c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x121ce  ldloc.2
0x121cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x121d4  ldstr    aName// "name"
0x121d9  ldc.i4.0
0x121da  ldc.i4.1
0x121db  newarr   [mscorlib]System.Object
0x121e0  dup
0x121e1  ldc.i4.0
0x121e2  ldarg.1
0x121e3  stelem.ref
0x121e4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x121e9  ldloc.2
0x121ea  ldarg.2
0x121eb  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x121f0  callvirt instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x121f5  stloc.3
0x121f6  ldloc.3
0x121f7  call     T0x2B000021
0x121fc  brfalse.s loc_12239
0x121fe  ldloc.3
0x121ff  call     T0x2B000022
0x12204  ldstr    aManifest// "manifest"
0x12209  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1220e  castclass [mscorlib]System.String
0x12213  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x12218  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifestHelper::ParseAndGetCustomControlDefinition(class [System.Xml]System.Xml.XmlDocument)
0x1221d  stloc.1
0x1221e  ldloc.1
0x1221f  ldloc.3
0x12220  call     T0x2B000022
0x12225  ldstr    aCustomcontroli// "customcontrolid"
0x1222a  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1222f  unbox.any [mscorlib]System.Guid
0x12234  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::set_CustomControlId(valuetype [mscorlib]System.Guid)
0x12239  ldloc.0
0x1223a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x1223f  ldloc.1
0x12240  ret
```
