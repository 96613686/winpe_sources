# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::RemapDocuments

- ea: `0x4b50`
- end: `0x4c6c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::RemapDocuments`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4ac0`

## callees

- `0x4b50`
- `0x5980`

## string_xrefs

- `0x4b59`: `Only Xlsx files can have ImportType == ImportType.XlsxCreateUpdate`
- `0x4bc2`: `Only Xlsx files can have ImportType == ImportType.XlsxCreateUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x4b50  ldarg.1
0x4b51  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x4b56  ldc.i4.4
0x4b57  ceq
0x4b59  ldstr    aOnlyXlsxFilesC// "Only Xlsx files can have ImportType == "...
0x4b5e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4b63  ldarg.2
0x4b64  ldarg.1
0x4b65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x4b6a  ldc.i4.5
0x4b6b  newarr   [mscorlib]System.String
0x4b70  dup
0x4b71  ldc.i4.0
0x4b72  ldstr    aTargetentityna// "targetentityname"
0x4b77  stelem.ref
0x4b78  dup
0x4b79  ldc.i4.1
0x4b7a  ldstr    aContent// "content"
0x4b7f  stelem.ref
0x4b80  dup
0x4b81  ldc.i4.2
0x4b82  ldstr    aFiletypecode// "filetypecode"
0x4b87  stelem.ref
0x4b88  dup
0x4b89  ldc.i4.3
0x4b8a  ldstr    aSourceentityna// "sourceentityname"
0x4b8f  stelem.ref
0x4b90  dup
0x4b91  ldc.i4.4
0x4b92  ldstr    aImportmapid// "importmapid"
0x4b97  stelem.ref
0x4b98  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::RetrieveImportFiles(valuetype [mscorlib]System.Guid, string[])
0x4b9d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x4ba2  stloc.0
0x4ba3  br       loc_4C54
0x4ba8  ldloc.0
0x4ba9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x4bae  stloc.1
0x4baf  ldloc.1
0x4bb0  ldstr    aFiletypecode// "filetypecode"
0x4bb5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4bba  unbox.any [mscorlib]System.Int32
0x4bbf  ldc.i4.3
0x4bc0  ceq
0x4bc2  ldstr    aOnlyXlsxFilesC// "Only Xlsx files can have ImportType == "...
0x4bc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4bcc  ldloc.1
0x4bcd  ldstr    aFiletypecode// "filetypecode"
0x4bd2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4bd7  unbox.any [mscorlib]System.Int32
0x4bdc  ldc.i4.3
0x4bdd  bne.un.s loc_4C54
0x4bdf  ldloc.1
0x4be0  ldstr    aImportmapid// "importmapid"
0x4be5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4bea  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x4bef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x4bf4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x4bf9  ldc.i4.0
0x4bfa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4bff  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportMappingCommand::.ctor(valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportMappingCommand::Execute()
0x4c09  stloc.2
0x4c0a  ldloc.2
0x4c0b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4c10  stloc.3
0x4c11  ldarg.0
0x4c12  ldloc.3
0x4c13  ldloc.1
0x4c14  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetMapXmlNode(class [System.Xml]System.Xml.XmlDocument xmlMapDocument, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity importFile)
0x4c19  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4c1e  stloc.2
0x4c1f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportFileService::.ctor()
0x4c24  ldloc.1
0x4c25  ldstr    aContent// "content"
0x4c2a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4c2f  castclass [mscorlib]System.String
0x4c34  ldloc.2
0x4c35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c3a  call     instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportFileService::RemapFile(string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c3f  stloc.s  4
0x4c41  ldloc.1
0x4c42  ldstr    aContent// "content"
0x4c47  ldloc.s  4
0x4c49  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4c4e  ldloc.1
0x4c4f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x4c54  ldloc.0
0x4c55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c5a  brtrue   loc_4BA8
0x4c5f  leave.s  loc_4C6B
0x4c61  ldloc.0
0x4c62  brfalse.s loc_4C6A
0x4c64  ldloc.0
0x4c65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c6a  endfinally
0x4c6b  ret
```
