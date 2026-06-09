# Microsoft.Crm.Application.Platform.EntityProxy::SetDisabled

- ea: `0x5dfd0`
- end: `0x5e3b8`
- name: `Microsoft.Crm.Application.Platform.EntityProxy::SetDisabled`
- size: `1000`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5dfa0`

## callees

- `0x3aa00`
- `0x5b890`
- `0x5b8a0`
- `0x5bab0`
- `0x5bae0`
- `0x5be20`
- `0x5cfc0`
- `0x5dfd0`
- `0x5ea60`
- `0x6a330`
- `0x9ca50`

## string_xrefs

- `0x5e114`: `pluginassembly`
- `0x5e129`: `plugintype`
- `0x5e13e`: `plugintypestatistic`
- `0x5e17d`: `sdkmessageprocessingstepsecureconfig`
- `0x5e192`: `serviceendpoint`
- `0x5e210`: `azureserviceconnection`
- `0x5e266`: `_isReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x5dfd0  ldarg.0
0x5dfd1  ldstr    aStatecode// "statecode"
0x5dfd6  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5dfdb  isinst   [mscorlib]System.String
0x5dfe0  stloc.0
0x5dfe1  ldarg.0
0x5dfe2  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5dfe7  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5dfec  stloc.1
0x5dfed  ldloc.1
0x5dfee  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x5dff3  stloc.2
0x5dff4  ldloc.2
0x5dff5  ldc.i4   0x85C81DB1
0x5dffa  bgt.un.s loc_5E068
0x5dffc  ldloc.2
0x5dffd  ldc.i4   0x11165F7E
0x5e002  bgt.un.s loc_5E02A
0x5e004  ldloc.2
0x5e005  ldc.i4   0x9B85041
0x5e00a  beq      loc_5E0E9
0x5e00f  ldloc.2
0x5e010  ldc.i4   0xDE2124B
0x5e015  beq      loc_5E1D0
0x5e01a  ldloc.2
0x5e01b  ldc.i4   0x11165F7E
0x5e020  beq      loc_5E0FE
0x5e025  br       loc_5E326
0x5e02a  ldloc.2
0x5e02b  ldc.i4   0x53BA4A2C
0x5e030  bgt.un.s loc_5E04D
0x5e032  ldloc.2
0x5e033  ldc.i4   0x3A55551C
0x5e038  beq      loc_5E13D
0x5e03d  ldloc.2
0x5e03e  ldc.i4   0x53BA4A2C
0x5e043  beq      loc_5E17C
0x5e048  br       loc_5E326
0x5e04d  ldloc.2
0x5e04e  ldc.i4   0x6284C13A
0x5e053  beq      loc_5E128
0x5e058  ldloc.2
0x5e059  ldc.i4   0x85C81DB1
0x5e05e  beq      loc_5E1FA
0x5e063  br       loc_5E326
0x5e068  ldloc.2
0x5e069  ldc.i4   0xBBD3CCE3
0x5e06e  bgt.un.s loc_5E0AE
0x5e070  ldloc.2
0x5e071  ldc.i4   0x934F4E0A
0x5e076  bgt.un.s loc_5E093
0x5e078  ldloc.2
0x5e079  ldc.i4   0x88E38EDB
0x5e07e  beq      loc_5E1A6
0x5e083  ldloc.2
0x5e084  ldc.i4   0x934F4E0A
0x5e089  beq      loc_5E1E5
0x5e08e  br       loc_5E326
0x5e093  ldloc.2
0x5e094  ldc.i4   0xB263A6F3
0x5e099  beq      loc_5E152
0x5e09e  ldloc.2
0x5e09f  ldc.i4   0xBBD3CCE3
0x5e0a4  beq      loc_5E20F
0x5e0a9  br       loc_5E326
0x5e0ae  ldloc.2
0x5e0af  ldc.i4   0xD3BBAFB5
0x5e0b4  bgt.un.s loc_5E0D1
0x5e0b6  ldloc.2
0x5e0b7  ldc.i4   0xD1036208
0x5e0bc  beq      loc_5E167
0x5e0c1  ldloc.2
0x5e0c2  ldc.i4   0xD3BBAFB5
0x5e0c7  beq      loc_5E191
0x5e0cc  br       loc_5E326
0x5e0d1  ldloc.2
0x5e0d2  ldc.i4   0xD64AD14A
0x5e0d7  beq.s    loc_5E113
0x5e0d9  ldloc.2
0x5e0da  ldc.i4   0xE4D40093
0x5e0df  beq      loc_5E1BB
0x5e0e4  br       loc_5E326
0x5e0e9  ldloc.1
0x5e0ea  ldstr    aBusinessunit// "businessunit"
0x5e0ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e0f4  brtrue   loc_5E224
0x5e0f9  br       loc_5E326
0x5e0fe  ldloc.1
0x5e0ff  ldstr    aSolution_0// "solution"
0x5e104  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e109  brtrue   loc_5E23B
0x5e10e  br       loc_5E326
0x5e113  ldloc.1
0x5e114  ldstr    aPluginassembly// "pluginassembly"
0x5e119  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e11e  brtrue   loc_5E252
0x5e123  br       loc_5E326
0x5e128  ldloc.1
0x5e129  ldstr    aPlugintype// "plugintype"
0x5e12e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e133  brtrue   loc_5E252
0x5e138  br       loc_5E326
0x5e13d  ldloc.1
0x5e13e  ldstr    aPlugintypestat// "plugintypestatistic"
0x5e143  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e148  brtrue   loc_5E252
0x5e14d  br       loc_5E326
0x5e152  ldloc.1
0x5e153  ldstr    aSdkmessageproc// "sdkmessageprocessingstep"
0x5e158  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e15d  brtrue   loc_5E252
0x5e162  br       loc_5E326
0x5e167  ldloc.1
0x5e168  ldstr    aSdkmessageproc_0// "sdkmessageprocessingstepimage"
0x5e16d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e172  brtrue   loc_5E252
0x5e177  br       loc_5E326
0x5e17c  ldloc.1
0x5e17d  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepsecureconfig"
0x5e182  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e187  brtrue   loc_5E252
0x5e18c  br       loc_5E326
0x5e191  ldloc.1
0x5e192  ldstr    aServiceendpoin// "serviceendpoint"
0x5e197  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e19c  brtrue   loc_5E252
0x5e1a1  br       loc_5E326
0x5e1a6  ldloc.1
0x5e1a7  ldstr    aDynamicpropert// "dynamicproperty"
0x5e1ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e1b1  brtrue   loc_5E25A
0x5e1b6  br       loc_5E326
0x5e1bb  ldloc.1
0x5e1bc  ldstr    aProductassocia_0// "productassociation"
0x5e1c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e1c6  brtrue   loc_5E295
0x5e1cb  br       loc_5E326
0x5e1d0  ldloc.1
0x5e1d1  ldstr    aKnowledgeartic// "knowledgearticle"
0x5e1d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e1db  brtrue   loc_5E2C2
0x5e1e0  br       loc_5E326
0x5e1e5  ldloc.1
0x5e1e6  ldstr    aPosition// "position"
0x5e1eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e1f0  brtrue   loc_5E2CA
0x5e1f5  br       loc_5E326
0x5e1fa  ldloc.1
0x5e1fb  ldstr    aTopicmodel// "topicmodel"
0x5e200  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e205  brtrue   loc_5E2D2
0x5e20a  br       loc_5E326
0x5e20f  ldloc.1
0x5e210  ldstr    aAzureserviceco// "azureserviceconnection"
0x5e215  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e21a  brtrue   loc_5E2FC
0x5e21f  br       loc_5E326
0x5e224  ldarg.0
0x5e225  ldarg.0
0x5e226  ldstr    aIsdisabled// "isdisabled"
0x5e22b  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5e230  unbox.any [mscorlib]System.Boolean
0x5e235  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e23a  ret
0x5e23b  ldarg.0
0x5e23c  ldarg.0
0x5e23d  ldstr    aIsmanaged// "ismanaged"
0x5e242  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5e247  unbox.any [mscorlib]System.Boolean
0x5e24c  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e251  ret
0x5e252  ldarg.0
0x5e253  ldc.i4.1
0x5e254  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e259  ret
0x5e25a  ldc.i4.0
0x5e25b  stloc.3
0x5e25c  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x5e261  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequestBase::get_QueryString()
0x5e266  ldstr    aIsreadonly// "_isReadOnly"
0x5e26b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x5e270  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x5e275  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x5e27a  stloc.s  4
0x5e27c  ldloc.s  4
0x5e27e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e283  brtrue.s loc_5E28D
0x5e285  ldloc.s  4
0x5e287  call     bool [mscorlib]System.Boolean::Parse(string)
0x5e28c  stloc.3
0x5e28d  ldarg.0
0x5e28e  ldloc.3
0x5e28f  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e294  ret
0x5e295  ldloc.0
0x5e296  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e29b  brtrue.s loc_5E2BA
0x5e29d  ldarg.0
0x5e29e  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5e2a3  ldloc.0
0x5e2a4  call     int32 Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string entityName, string state)
0x5e2a9  stloc.s  5
0x5e2ab  ldarg.0
0x5e2ac  ldloc.s  5
0x5e2ae  ldc.i4.2
0x5e2af  ceq
0x5e2b1  ldc.i4.0
0x5e2b2  ceq
0x5e2b4  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2b9  ret
0x5e2ba  ldarg.0
0x5e2bb  ldc.i4.0
0x5e2bc  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2c1  ret
0x5e2c2  ldarg.0
0x5e2c3  ldc.i4.1
0x5e2c4  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2c9  ret
0x5e2ca  ldarg.0
0x5e2cb  ldc.i4.0
0x5e2cc  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2d1  ret
0x5e2d2  ldloc.0
0x5e2d3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e2d8  brtrue.s loc_5E2F4
0x5e2da  ldarg.0
0x5e2db  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5e2e0  ldloc.0
0x5e2e1  call     int32 Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string entityName, string state)
0x5e2e6  stloc.s  6
0x5e2e8  ldarg.0
0x5e2e9  ldloc.s  6
0x5e2eb  ldc.i4.0
0x5e2ec  ceq
0x5e2ee  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2f3  ret
0x5e2f4  ldarg.0
0x5e2f5  ldc.i4.1
0x5e2f6  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e2fb  ret
0x5e2fc  ldloc.0
0x5e2fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e302  brtrue.s loc_5E31E
0x5e304  ldarg.0
0x5e305  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5e30a  ldloc.0
0x5e30b  call     int32 Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string entityName, string state)
0x5e310  stloc.s  7
0x5e312  ldarg.0
0x5e313  ldloc.s  7
0x5e315  ldc.i4.0
0x5e316  ceq
0x5e318  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e31d  ret
0x5e31e  ldarg.0
0x5e31f  ldc.i4.1
0x5e320  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e325  ret
0x5e326  ldarg.0
0x5e327  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5e32c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x5e331  ldstr    aStatecode// "statecode"
0x5e336  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5e33b  brfalse.s loc_5E35C
0x5e33d  ldloc.0
0x5e33e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e343  brtrue.s loc_5E35C
0x5e345  ldarg.0
0x5e346  ldarg.0
0x5e347  call     instance string Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x5e34c  ldloc.0
0x5e34d  call     int32 Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string entityName, string state)
0x5e352  ldc.i4.0
0x5e353  cgt.un
0x5e355  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e35a  br.s     loc_5E363
0x5e35c  ldarg.0
0x5e35d  ldc.i4.0
0x5e35e  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool value)
0x5e363  ldarg.0
0x5e364  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5e369  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5e36e  ldstr    aWorkflow// "workflow"
0x5e373  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e378  brtrue.s loc_5E3A8
0x5e37a  ldarg.0
0x5e37b  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5e380  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5e385  ldstr    aKnowledgesearc// "knowledgesearchmodel"
0x5e38a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e38f  brtrue.s loc_5E3A8
0x5e391  ldarg.0
0x5e392  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5e397  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x5e39c  ldstr    aAdvancedsimila// "advancedsimilarityrule"
0x5e3a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e3a6  brfalse.s loc_5E3B7
0x5e3a8  ldarg.0
0x5e3a9  ldarg.0
0x5e3aa  call     instance bool Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
  ... truncated ...
```
