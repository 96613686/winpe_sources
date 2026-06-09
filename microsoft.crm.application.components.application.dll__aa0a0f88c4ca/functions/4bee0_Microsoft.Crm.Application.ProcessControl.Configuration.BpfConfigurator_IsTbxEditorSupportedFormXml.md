# Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::IsTbxEditorSupportedFormXml

- ea: `0x4bee0`
- end: `0x4c02c`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::IsTbxEditorSupportedFormXml`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4b990`

## callees

- `0x4bee0`

## string_xrefs

- `0x4bf33`: `formxml`
- `0x4bf77`: `formxml`
- `0x4bf97`: `formxml`
- `0x4bf13`: `componentstate`
- `0x4bfb9`: `TaskBasedFlowXml.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x4bee0  ldarg.1
0x4bee1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_FormId()
0x4bee6  stloc.0
0x4bee7  ldstr    aSystemform// "systemform"
0x4beec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4bef1  stloc.1
0x4bef2  ldloc.1
0x4bef3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4bef8  ldstr    aFormid// "formid"
0x4befd  ldc.i4.0
0x4befe  ldc.i4.1
0x4beff  newarr   [mscorlib]System.Object
0x4bf04  dup
0x4bf05  ldc.i4.0
0x4bf06  ldloc.0
0x4bf07  stelem.ref
0x4bf08  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x4bf0d  ldloc.1
0x4bf0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4bf13  ldstr    aComponentstate// "componentstate"
0x4bf18  ldc.i4.0
0x4bf19  ldc.i4.1
0x4bf1a  newarr   [mscorlib]System.Object
0x4bf1f  dup
0x4bf20  ldc.i4.0
0x4bf21  ldc.i4.0
0x4bf22  box      [mscorlib]System.Int32
0x4bf27  stelem.ref
0x4bf28  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x4bf2d  ldloc.1
0x4bf2e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4bf33  ldstr    aFormxml// "formxml"
0x4bf38  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x4bf3d  ldloc.1
0x4bf3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4bf43  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4bf48  stloc.2
0x4bf49  ldloc.2
0x4bf4a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x4bf4f  ldc.i4.0
0x4bf50  cgt
0x4bf52  ldstr    aExpectedToFind// "Expected to find at least one form; fou"...
0x4bf57  ldc.i4.1
0x4bf58  newarr   [mscorlib]System.Object
0x4bf5d  dup
0x4bf5e  ldc.i4.0
0x4bf5f  ldloc.2
0x4bf60  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x4bf65  box      [mscorlib]System.Int32
0x4bf6a  stelem.ref
0x4bf6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x4bf70  ldloc.2
0x4bf71  ldc.i4.0
0x4bf72  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x4bf77  ldstr    aFormxml// "formxml"
0x4bf7c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4bf81  castclass [mscorlib]System.String
0x4bf86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4bf8b  brtrue   loc_4C027
0x4bf90  ldloc.2
0x4bf91  ldc.i4.0
0x4bf92  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x4bf97  ldstr    aFormxml// "formxml"
0x4bf9c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4bfa1  isinst   [mscorlib]System.String
0x4bfa6  stloc.3
0x4bfa7  ldloc.3
0x4bfa8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4bfad  brtrue.s loc_4C027
0x4bfaf  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::.ctor()
0x4bfb4  stloc.s  4
0x4bfb6  ldloc.s  4
0x4bfb8  ldnull
0x4bfb9  ldstr    aTaskbasedflowx// "TaskBasedFlowXml.xsd"
0x4bfbe  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0x4bfc3  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x4bfc8  pop
0x4bfc9  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x4bfce  stloc.s  5
0x4bfd0  ldloc.s  5
0x4bfd2  ldc.i4.4
0x4bfd3  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0x4bfd8  ldloc.s  5
0x4bfda  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x4bfdf  ldloc.s  4
0x4bfe1  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchemaSet)
0x4bfe6  ldloc.3
0x4bfe7  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4bfec  newobj   instance void [System.Xml]System.Xml.XmlNodeReader::.ctor(class [System.Xml]System.Xml.XmlNode)
0x4bff1  stloc.s  6
0x4bff3  ldloc.s  6
0x4bff5  ldloc.s  5
0x4bff7  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x4bffc  stloc.s  7
0x4bffe  ldloc.s  7
0x4c000  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x4c005  brtrue.s loc_4BFFE
0x4c007  leave.s  loc_4C027
0x4c009  pop
0x4c00a  ldc.i4.0
0x4c00b  stloc.s  8
0x4c00d  leave.s  loc_4C029
0x4c00f  ldloc.s  7
0x4c011  brfalse.s loc_4C01A
0x4c013  ldloc.s  7
0x4c015  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c01a  endfinally
0x4c01b  ldloc.s  6
0x4c01d  brfalse.s loc_4C026
0x4c01f  ldloc.s  6
0x4c021  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c026  endfinally
0x4c027  ldc.i4.1
0x4c028  ret
0x4c029  ldloc.s  8
0x4c02b  ret
```
