# Microsoft.Crm.Caching.CustomControlDefinitionWebServiceCacheLoader::LoadCacheData

- ea: `0x122a0`
- end: `0x1234c`
- name: `Microsoft.Crm.Caching.CustomControlDefinitionWebServiceCacheLoader::LoadCacheData`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x122a0`
- `0x59880`
- `0x5be20`

## string_xrefs

- `0x122c4`: `manifest`
- `0x1230f`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x122a0  ldstr    aGetcustomcontr_0// "GetCustomControlDefinition"
0x122a5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x122aa  stloc.0
0x122ab  ldloc.0
0x122ac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x122b1  ldnull
0x122b2  stloc.1
0x122b3  ldstr    aCustomcontrol// "customcontrol"
0x122b8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x122bd  stloc.2
0x122be  ldloc.2
0x122bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x122c4  ldstr    aManifest// "manifest"
0x122c9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x122ce  ldloc.2
0x122cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x122d4  ldstr    aCustomcontroli// "customcontrolid"
0x122d9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x122de  ldloc.2
0x122df  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x122e4  ldstr    aName// "name"
0x122e9  ldc.i4.0
0x122ea  ldc.i4.1
0x122eb  newarr   [mscorlib]System.Object
0x122f0  dup
0x122f1  ldc.i4.0
0x122f2  ldarg.1
0x122f3  stelem.ref
0x122f4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x122f9  ldloc.2
0x122fa  ldarg.2
0x122fb  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12300  stloc.3
0x12301  ldloc.3
0x12302  call     T0x2B000021
0x12307  brfalse.s loc_12344
0x12309  ldloc.3
0x1230a  call     T0x2B000022
0x1230f  ldstr    aManifest// "manifest"
0x12314  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x12319  castclass [mscorlib]System.String
0x1231e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x12323  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifestHelper::ParseAndGetCustomControlDefinition(class [System.Xml]System.Xml.XmlDocument)
0x12328  stloc.1
0x12329  ldloc.1
0x1232a  ldloc.3
0x1232b  call     T0x2B000022
0x12330  ldstr    aCustomcontroli// "customcontrolid"
0x12335  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1233a  unbox.any [mscorlib]System.Guid
0x1233f  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::set_CustomControlId(valuetype [mscorlib]System.Guid)
0x12344  ldloc.0
0x12345  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x1234a  ldloc.1
0x1234b  ret
```
