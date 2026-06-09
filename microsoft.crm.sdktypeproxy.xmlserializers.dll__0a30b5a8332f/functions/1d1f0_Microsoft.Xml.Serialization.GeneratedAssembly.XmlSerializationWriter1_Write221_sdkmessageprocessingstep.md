# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write221_sdkmessageprocessingstep

- ea: `0x1d1f0`
- end: `0x1d469`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write221_sdkmessageprocessingstep`
- size: `633`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35e20`
- `0x551d0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x16cb0`
- `0x1d1f0`
- `0x1d470`

## string_xrefs

- `0x1d235`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d245`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d25b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d273`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d28b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d2a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d2b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d2cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d2e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d2ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d317`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d32f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d347`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d35f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d377`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d38f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d3a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d3bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d3d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d3ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d407`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d41f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d437`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d44f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d256`: `createdby`
- `0x1d26e`: `createdon`
- `0x1d3ea`: `sdkmessageprocessingstepsecureconfigid`
- `0x1d240`: `configuration`
- `0x1d2ca`: `impersonatinguserid`
- `0x1d35a`: `plugintypeid`

## pseudocode

```c

```

## disassembly

```asm
0x1d1f0  ldarg.3
0x1d1f1  brtrue.s loc_1D200
0x1d1f3  ldarg.s  4
0x1d1f5  brfalse.s loc_1D1FF
0x1d1f7  ldarg.0
0x1d1f8  ldarg.1
0x1d1f9  ldarg.2
0x1d1fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1d1ff  ret
0x1d200  ldarg.s  5
0x1d202  brtrue.s loc_1D220
0x1d204  ldarg.3
0x1d205  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d20a  stloc.0
0x1d20b  ldloc.0
0x1d20c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep
0x1d211  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d216  beq.s    loc_1D220
0x1d218  ldarg.0
0x1d219  ldarg.3
0x1d21a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1d21f  throw
0x1d220  ldarg.0
0x1d221  ldarg.1
0x1d222  ldarg.2
0x1d223  ldarg.3
0x1d224  ldc.i4.0
0x1d225  ldnull
0x1d226  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1d22b  ldarg.s  5
0x1d22d  brfalse.s loc_1D23F
0x1d22f  ldarg.0
0x1d230  ldstr    aSdkmessageproc_2// "sdkmessageprocessingstep"
0x1d235  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d23a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1d23f  ldarg.0
0x1d240  ldstr    aConfiguration// "configuration"
0x1d245  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d24a  ldarg.3
0x1d24b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_configuration()
0x1d250  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d255  ldarg.0
0x1d256  ldstr    aCreatedby// "createdby"
0x1d25b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d260  ldarg.3
0x1d261  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_createdby()
0x1d266  ldc.i4.0
0x1d267  ldc.i4.0
0x1d268  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d26d  ldarg.0
0x1d26e  ldstr    aCreatedon// "createdon"
0x1d273  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d278  ldarg.3
0x1d279  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_createdon()
0x1d27e  ldc.i4.0
0x1d27f  ldc.i4.0
0x1d280  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d285  ldarg.0
0x1d286  ldstr    aCustomizationl// "customizationlevel"
0x1d28b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d290  ldarg.3
0x1d291  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_customizationlevel()
0x1d296  ldc.i4.0
0x1d297  ldc.i4.0
0x1d298  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d29d  ldarg.0
0x1d29e  ldstr    aDescription_0// "description"
0x1d2a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d2a8  ldarg.3
0x1d2a9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_description()
0x1d2ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d2b3  ldarg.0
0x1d2b4  ldstr    aFilteringattri_0// "filteringattributes"
0x1d2b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d2be  ldarg.3
0x1d2bf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_filteringattributes()
0x1d2c4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d2c9  ldarg.0
0x1d2ca  ldstr    aImpersonatingu_0// "impersonatinguserid"
0x1d2cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d2d4  ldarg.3
0x1d2d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_impersonatinguserid()
0x1d2da  ldc.i4.0
0x1d2db  ldc.i4.0
0x1d2dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d2e1  ldarg.0
0x1d2e2  ldstr    aInvocationsour_0// "invocationsource"
0x1d2e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d2ec  ldarg.3
0x1d2ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_invocationsource()
0x1d2f2  ldc.i4.0
0x1d2f3  ldc.i4.0
0x1d2f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1d2f9  ldarg.0
0x1d2fa  ldstr    aMode_0// "mode"
0x1d2ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d304  ldarg.3
0x1d305  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_mode()
0x1d30a  ldc.i4.0
0x1d30b  ldc.i4.0
0x1d30c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1d311  ldarg.0
0x1d312  ldstr    aModifiedby// "modifiedby"
0x1d317  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d31c  ldarg.3
0x1d31d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_modifiedby()
0x1d322  ldc.i4.0
0x1d323  ldc.i4.0
0x1d324  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d329  ldarg.0
0x1d32a  ldstr    aModifiedon// "modifiedon"
0x1d32f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d334  ldarg.3
0x1d335  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_modifiedon()
0x1d33a  ldc.i4.0
0x1d33b  ldc.i4.0
0x1d33c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d341  ldarg.0
0x1d342  ldstr    aOrganizationid// "organizationid"
0x1d347  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d34c  ldarg.3
0x1d34d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_organizationid()
0x1d352  ldc.i4.0
0x1d353  ldc.i4.0
0x1d354  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d359  ldarg.0
0x1d35a  ldstr    aPlugintypeid// "plugintypeid"
0x1d35f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d364  ldarg.3
0x1d365  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_plugintypeid()
0x1d36a  ldc.i4.0
0x1d36b  ldc.i4.0
0x1d36c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d371  ldarg.0
0x1d372  ldstr    aRank// "rank"
0x1d377  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d37c  ldarg.3
0x1d37d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_rank()
0x1d382  ldc.i4.0
0x1d383  ldc.i4.0
0x1d384  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d389  ldarg.0
0x1d38a  ldstr    aSdkmessagefilt_0// "sdkmessagefilterid"
0x1d38f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d394  ldarg.3
0x1d395  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_sdkmessagefilterid()
0x1d39a  ldc.i4.0
0x1d39b  ldc.i4.0
0x1d39c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d3a1  ldarg.0
0x1d3a2  ldstr    aSdkmessageid// "sdkmessageid"
0x1d3a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d3ac  ldarg.3
0x1d3ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_sdkmessageid()
0x1d3b2  ldc.i4.0
0x1d3b3  ldc.i4.0
0x1d3b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d3b9  ldarg.0
0x1d3ba  ldstr    aSdkmessageproc_7// "sdkmessageprocessingstepid"
0x1d3bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d3c4  ldarg.3
0x1d3c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_sdkmessageprocessingstepid()
0x1d3ca  ldc.i4.0
0x1d3cb  ldc.i4.0
0x1d3cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1d3d1  ldarg.0
0x1d3d2  ldstr    aSdkmessageproc_10// "sdkmessageprocessingstepidunique"
0x1d3d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d3dc  ldarg.3
0x1d3dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_sdkmessageprocessingstepidunique()
0x1d3e2  ldc.i4.0
0x1d3e3  ldc.i4.0
0x1d3e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1d3e9  ldarg.0
0x1d3ea  ldstr    aSdkmessageproc_5// "sdkmessageprocessingstepsecureconfigid"
0x1d3ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d3f4  ldarg.3
0x1d3f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_sdkmessageprocessingstepsecureconfigid()
0x1d3fa  ldc.i4.0
0x1d3fb  ldc.i4.0
0x1d3fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d401  ldarg.0
0x1d402  ldstr    aStage_0// "stage"
0x1d407  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d40c  ldarg.3
0x1d40d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_stage()
0x1d412  ldc.i4.0
0x1d413  ldc.i4.0
0x1d414  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1d419  ldarg.0
0x1d41a  ldstr    aStatecode// "statecode"
0x1d41f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d424  ldarg.3
0x1d425  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SdkMessageProcessingStepStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_statecode()
0x1d42a  ldc.i4.0
0x1d42b  ldc.i4.0
0x1d42c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write220_Item(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SdkMessageProcessingStepStateInfo o, bool isNullable, bool needType)
0x1d431  ldarg.0
0x1d432  ldstr    aStatuscode// "statuscode"
0x1d437  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d43c  ldarg.3
0x1d43d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_statuscode()
0x1d442  ldc.i4.0
0x1d443  ldc.i4.0
0x1d444  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1d449  ldarg.0
0x1d44a  ldstr    aSupporteddeplo_0// "supporteddeployment"
0x1d44f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d454  ldarg.3
0x1d455  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.sdkmessageprocessingstep::get_supporteddeployment()
0x1d45a  ldc.i4.0
0x1d45b  ldc.i4.0
0x1d45c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1d461  ldarg.0
0x1d462  ldarg.3
0x1d463  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1d468  ret
```
