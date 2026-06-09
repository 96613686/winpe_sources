# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write460_workflow

- ea: `0x2e650`
- end: `0x2e8c5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write460_workflow`
- size: `629`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38270`
- `0x57770`

## callees

- `0x5cf0`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x167c0`
- `0x16a10`
- `0x16cb0`
- `0x2e650`
- `0x2e8d0`

## string_xrefs

- `0x2e695`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e6a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e6bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e6d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e6eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e703`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e719`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e731`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e749`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e761`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e777`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e78f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e7a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e7bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e7d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e7ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e807`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e81d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e835`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e84d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e865`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e87d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e895`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e8ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e6ce`: `createdby`
- `0x2e6e6`: `createdon`
- `0x2e7d2`: `plugintypeid`

## pseudocode

```c

```

## disassembly

```asm
0x2e650  ldarg.3
0x2e651  brtrue.s loc_2E660
0x2e653  ldarg.s  4
0x2e655  brfalse.s loc_2E65F
0x2e657  ldarg.0
0x2e658  ldarg.1
0x2e659  ldarg.2
0x2e65a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2e65f  ret
0x2e660  ldarg.s  5
0x2e662  brtrue.s loc_2E680
0x2e664  ldarg.3
0x2e665  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e66a  stloc.0
0x2e66b  ldloc.0
0x2e66c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow
0x2e671  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e676  beq.s    loc_2E680
0x2e678  ldarg.0
0x2e679  ldarg.3
0x2e67a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2e67f  throw
0x2e680  ldarg.0
0x2e681  ldarg.1
0x2e682  ldarg.2
0x2e683  ldarg.3
0x2e684  ldc.i4.0
0x2e685  ldnull
0x2e686  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2e68b  ldarg.s  5
0x2e68d  brfalse.s loc_2E69F
0x2e68f  ldarg.0
0x2e690  ldstr    aWorkflow// "workflow"
0x2e695  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e69a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2e69f  ldarg.0
0x2e6a0  ldstr    aActiveworkflow// "activeworkflowid"
0x2e6a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e6aa  ldarg.3
0x2e6ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_activeworkflowid()
0x2e6b0  ldc.i4.0
0x2e6b1  ldc.i4.0
0x2e6b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e6b7  ldarg.0
0x2e6b8  ldstr    aActivities// "activities"
0x2e6bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e6c2  ldarg.3
0x2e6c3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_activities()
0x2e6c8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e6cd  ldarg.0
0x2e6ce  ldstr    aCreatedby// "createdby"
0x2e6d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e6d8  ldarg.3
0x2e6d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_createdby()
0x2e6de  ldc.i4.0
0x2e6df  ldc.i4.0
0x2e6e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e6e5  ldarg.0
0x2e6e6  ldstr    aCreatedon// "createdon"
0x2e6eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e6f0  ldarg.3
0x2e6f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_createdon()
0x2e6f6  ldc.i4.0
0x2e6f7  ldc.i4.0
0x2e6f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e6fd  ldarg.0
0x2e6fe  ldstr    aDescription_0// "description"
0x2e703  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e708  ldarg.3
0x2e709  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_description()
0x2e70e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e713  ldarg.0
0x2e714  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x2e719  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e71e  ldarg.3
0x2e71f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_iscrmuiworkflow()
0x2e724  ldc.i4.0
0x2e725  ldc.i4.0
0x2e726  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2e72b  ldarg.0
0x2e72c  ldstr    aModifiedby// "modifiedby"
0x2e731  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e736  ldarg.3
0x2e737  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_modifiedby()
0x2e73c  ldc.i4.0
0x2e73d  ldc.i4.0
0x2e73e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e743  ldarg.0
0x2e744  ldstr    aModifiedon// "modifiedon"
0x2e749  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e74e  ldarg.3
0x2e74f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_modifiedon()
0x2e754  ldc.i4.0
0x2e755  ldc.i4.0
0x2e756  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e75b  ldarg.0
0x2e75c  ldstr    aName// "name"
0x2e761  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e766  ldarg.3
0x2e767  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_name()
0x2e76c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e771  ldarg.0
0x2e772  ldstr    aOndemand// "ondemand"
0x2e777  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e77c  ldarg.3
0x2e77d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_ondemand()
0x2e782  ldc.i4.0
0x2e783  ldc.i4.0
0x2e784  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2e789  ldarg.0
0x2e78a  ldstr    aOwnerid// "ownerid"
0x2e78f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e794  ldarg.3
0x2e795  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_ownerid()
0x2e79a  ldc.i4.0
0x2e79b  ldc.i4.0
0x2e79c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2e7a1  ldarg.0
0x2e7a2  ldstr    aOwningbusiness// "owningbusinessunit"
0x2e7a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e7ac  ldarg.3
0x2e7ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_owningbusinessunit()
0x2e7b2  ldc.i4.0
0x2e7b3  ldc.i4.0
0x2e7b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e7b9  ldarg.0
0x2e7ba  ldstr    aParentworkflow// "parentworkflowid"
0x2e7bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e7c4  ldarg.3
0x2e7c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_parentworkflowid()
0x2e7ca  ldc.i4.0
0x2e7cb  ldc.i4.0
0x2e7cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e7d1  ldarg.0
0x2e7d2  ldstr    aPlugintypeid// "plugintypeid"
0x2e7d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e7dc  ldarg.3
0x2e7dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_plugintypeid()
0x2e7e2  ldc.i4.0
0x2e7e3  ldc.i4.0
0x2e7e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e7e9  ldarg.0
0x2e7ea  ldstr    aPrimaryentity// "primaryentity"
0x2e7ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e7f4  ldarg.3
0x2e7f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_primaryentity()
0x2e7fa  ldc.i4.0
0x2e7fb  ldc.i4.0
0x2e7fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x2e801  ldarg.0
0x2e802  ldstr    aRules// "rules"
0x2e807  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e80c  ldarg.3
0x2e80d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_rules()
0x2e812  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e817  ldarg.0
0x2e818  ldstr    aScope// "scope"
0x2e81d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e822  ldarg.3
0x2e823  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_scope()
0x2e828  ldc.i4.0
0x2e829  ldc.i4.0
0x2e82a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2e82f  ldarg.0
0x2e830  ldstr    aStatecode// "statecode"
0x2e835  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e83a  ldarg.3
0x2e83b  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.WorkflowStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_statecode()
0x2e840  ldc.i4.0
0x2e841  ldc.i4.0
0x2e842  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write459_WorkflowStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.WorkflowStateInfo o, bool isNullable, bool needType)
0x2e847  ldarg.0
0x2e848  ldstr    aStatuscode// "statuscode"
0x2e84d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e852  ldarg.3
0x2e853  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_statuscode()
0x2e858  ldc.i4.0
0x2e859  ldc.i4.0
0x2e85a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2e85f  ldarg.0
0x2e860  ldstr    aSubprocess// "subprocess"
0x2e865  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e86a  ldarg.3
0x2e86b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_subprocess()
0x2e870  ldc.i4.0
0x2e871  ldc.i4.0
0x2e872  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2e877  ldarg.0
0x2e878  ldstr    aType_0// "type"
0x2e87d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e882  ldarg.3
0x2e883  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_type()
0x2e888  ldc.i4.0
0x2e889  ldc.i4.0
0x2e88a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2e88f  ldarg.0
0x2e890  ldstr    aUidata// "uidata"
0x2e895  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e89a  ldarg.3
0x2e89b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_uidata()
0x2e8a0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e8a5  ldarg.0
0x2e8a6  ldstr    aWorkflowid// "workflowid"
0x2e8ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e8b0  ldarg.3
0x2e8b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflow::get_workflowid()
0x2e8b6  ldc.i4.0
0x2e8b7  ldc.i4.0
0x2e8b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2e8bd  ldarg.0
0x2e8be  ldarg.3
0x2e8bf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2e8c4  ret
```
