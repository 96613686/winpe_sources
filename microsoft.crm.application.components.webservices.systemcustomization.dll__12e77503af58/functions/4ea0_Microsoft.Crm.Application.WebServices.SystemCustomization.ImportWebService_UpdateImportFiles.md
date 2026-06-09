# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateImportFiles

- ea: `0x4ea0`
- end: `0x501a`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateImportFiles`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4ac0`

## callees

- `0x4ea0`
- `0x5980`

## pseudocode

```c

```

## disassembly

```asm
0x4ea0  ldarg.3
0x4ea1  ldarg.1
0x4ea2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x4ea7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::RetrieveImportFiles(valuetype [mscorlib]System.Guid)
0x4eac  ldarg.2
0x4ead  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4eb2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4eb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_MapXml()
0x4ebc  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4ec1  stloc.0
0x4ec2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x4ec7  stloc.1
0x4ec8  br       loc_5002
0x4ecd  ldloc.1
0x4ece  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x4ed3  stloc.2
0x4ed4  ldloc.2
0x4ed5  ldstr    aEnableduplicat// "enableduplicatedetection"
0x4eda  ldarg.1
0x4edb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_DuplicateDetection()
0x4ee0  box      [mscorlib]System.Boolean
0x4ee5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4eea  ldloc.2
0x4eeb  ldstr    aUsesystemmap// "usesystemmap"
0x4ef0  ldc.i4.0
0x4ef1  box      [mscorlib]System.Boolean
0x4ef6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4efb  ldloc.2
0x4efc  ldstr    aImportmapid// "importmapid"
0x4f01  ldarg.1
0x4f02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x4f07  box      [mscorlib]System.Guid
0x4f0c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4f11  ldloc.2
0x4f12  ldstr    aSourceentityna// "sourceentityname"
0x4f17  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4f1c  castclass [mscorlib]System.String
0x4f21  stloc.3
0x4f22  ldarg.0
0x4f23  ldloc.0
0x4f24  ldloc.2
0x4f25  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetMapXmlNode(class [System.Xml]System.Xml.XmlDocument xmlMapDocument, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity importFile)
0x4f2a  stloc.s  4
0x4f2c  ldloc.s  4
0x4f2e  ldnull
0x4f2f  cgt.un
0x4f31  ldstr    aEntityNodeFor0// "Entity node for {0} not found in map"
0x4f36  ldc.i4.1
0x4f37  newarr   [mscorlib]System.Object
0x4f3c  dup
0x4f3d  ldc.i4.0
0x4f3e  ldloc.3
0x4f3f  stelem.ref
0x4f40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x4f45  ldsfld   string [mscorlib]System.String::Empty
0x4f4a  stloc.s  5
0x4f4c  ldloc.s  4
0x4f4e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f53  ldstr    aTargetentityna_0// "TargetEntityName"
0x4f58  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4f5d  brfalse.s loc_4F77
0x4f5f  ldloc.s  4
0x4f61  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f66  ldstr    aTargetentityna_0// "TargetEntityName"
0x4f6b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4f70  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4f75  stloc.s  5
0x4f77  ldloc.2
0x4f78  ldstr    aTargetentityna// "targetentityname"
0x4f7d  ldloc.s  5
0x4f7f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4f84  ldloc.s  4
0x4f86  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f8b  ldstr    aProcesscode// "ProcessCode"
0x4f90  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4f95  brfalse.s loc_4FE6
0x4f97  ldloc.s  4
0x4f99  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4f9e  ldstr    aProcesscode// "ProcessCode"
0x4fa3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4fa8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4fad  ldc.i4.0
0x4fae  stloc.s  6
0x4fb0  ldloca.s 6
0x4fb2  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x4fb8  callvirt instance string [mscorlib]System.Object::ToString()
0x4fbd  ldc.i4.5
0x4fbe  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4fc3  brtrue.s loc_4FE6
0x4fc5  ldstr    aImportfile// "importfile"
0x4fca  ldloc.2
0x4fcb  ldstr    aImportfileid// "importfileid"
0x4fd0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4fd5  unbox.any [mscorlib]System.Guid
0x4fda  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4fdf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4fe4  br.s     loc_5002
0x4fe6  ldloc.2
0x4fe7  ldstr    aRecordsownerid// "recordsownerid"
0x4fec  ldarg.1
0x4fed  callvirt instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EntityReference [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_DefaultOwner()
0x4ff2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4ff7  ldloc.2
0x4ff8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4ffd  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5002  ldloc.1
0x5003  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5008  brtrue   loc_4ECD
0x500d  leave.s  loc_5019
0x500f  ldloc.1
0x5010  brfalse.s loc_5018
0x5012  ldloc.1
0x5013  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5018  endfinally
0x5019  ret
```
