# Microsoft.Crm.Metadata.OrganizationUIHelper::CreateForm

- ea: `0x3dcb0`
- end: `0x3df73`
- name: `Microsoft.Crm.Metadata.OrganizationUIHelper::CreateForm`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3dc80`
- `0x40440`

## callees

- `0x2d530`
- `0x3dcb0`
- `0x3dfd0`
- `0x3ef90`
- `0x3f860`
- `0x3fee0`
- `0x43de0`

## string_xrefs

- `0x3dcbc`: `service`
- `0x3dcb1`: `entityCreateInfo`
- `0x3dd8d`: `formxml`
- `0x3dde8`: `formxml`
- `0x3de43`: `formxml`
- `0x3de98`: `formxml`
- `0x3df00`: `CreateForm`
- `0x3df05`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityWrappers.cs`
- `0x3df56`: `TODO: This code has to be removed in Couple of Weeks. MaxObjectTypeCode is {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3dcb0  ldarg.1
0x3dcb1  ldstr    aEntitycreatein// "entityCreateInfo"
0x3dcb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3dcbb  ldarg.3
0x3dcbc  ldstr    aService// "service"
0x3dcc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3dcc6  ldarg.s  4
0x3dcc8  ldstr    aContext// "context"
0x3dccd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3dcd2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::.ctor()
0x3dcd7  stloc.0
0x3dcd8  ldarg.s  4
0x3dcda  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3dcdf  stloc.1
0x3dce0  ldarg.s  4
0x3dce2  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrganizationBaseLanguage::GetOrganizationBaseLanguage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3dce7  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x3dcec  stloc.2
0x3dced  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3dcf2  stloc.3
0x3dcf3  ldloc.1
0x3dcf4  ldstr    aFormid// "formid"
0x3dcf9  ldloc.3
0x3dcfa  box      [mscorlib]System.Guid
0x3dcff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dd04  ldloc.1
0x3dd05  ldstr    aName// "name"
0x3dd0a  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x3dd0f  ldstr    aSystemformForm// "SystemForm.FormName"
0x3dd14  ldloc.2
0x3dd15  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3dd1a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dd1f  ldloc.1
0x3dd20  ldstr    aObjecttypecode_0// "objecttypecode"
0x3dd25  ldarg.1
0x3dd26  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x3dd2b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x3dd30  box      [mscorlib]System.Int32
0x3dd35  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dd3a  ldloc.1
0x3dd3b  ldstr    aType// "type"
0x3dd40  ldarg.2
0x3dd41  box      [mscorlib]System.Int32
0x3dd46  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dd4b  ldarg.2
0x3dd4c  ldc.i4.2
0x3dd4d  sub
0x3dd4e  switch   loc_3DD71, loc_3DEB2, loc_3DE7C, loc_3DEB2, loc_3DE27
0x3dd67  ldarg.2
0x3dd68  ldc.i4.s 0xB
0x3dd6a  beq.s    loc_3DDCC
0x3dd6c  br       loc_3DEB2
0x3dd71  ldloc.1
0x3dd72  ldstr    aDescription_0// "description"
0x3dd77  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x3dd7c  ldstr    aSystemformForm_0// "SystemForm.FormDescription.Main"
0x3dd81  ldloc.2
0x3dd82  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3dd87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dd8c  ldloc.1
0x3dd8d  ldstr    aFormxml// "formxml"
0x3dd92  ldarg.0
0x3dd93  ldarg.1
0x3dd94  ldloc.0
0x3dd95  ldarg.s  4
0x3dd97  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultFormXml(class Microsoft.Crm.Metadata.EntityCreateInfo entityCreateInfo, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3dd9c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3dda1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dda6  ldarg.1
0x3dda7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x3ddac  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x3ddb1  brfalse  loc_3DEBD
0x3ddb6  ldloc.1
0x3ddb7  ldstr    aFormpresentati// "formpresentation"
0x3ddbc  ldc.i4.1
0x3ddbd  box      [mscorlib]System.Int32
0x3ddc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3ddc7  br       loc_3DEBD
0x3ddcc  ldloc.1
0x3ddcd  ldstr    aDescription_0// "description"
0x3ddd2  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x3ddd7  ldstr    aSystemformForm_1// "SystemForm.FormDescription.Card"
0x3dddc  ldloc.2
0x3dddd  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3dde2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3dde7  ldloc.1
0x3dde8  ldstr    aFormxml// "formxml"
0x3dded  ldarg.0
0x3ddee  ldarg.1
0x3ddef  ldloc.0
0x3ddf0  ldarg.s  4
0x3ddf2  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultCardFormXml(class Microsoft.Crm.Metadata.EntityCreateInfo entityCreateInfo, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3ddf7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3ddfc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de01  ldarg.1
0x3de02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x3de07  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x3de0c  brfalse  loc_3DEBD
0x3de11  ldloc.1
0x3de12  ldstr    aFormpresentati// "formpresentation"
0x3de17  ldc.i4.1
0x3de18  box      [mscorlib]System.Int32
0x3de1d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de22  br       loc_3DEBD
0x3de27  ldloc.1
0x3de28  ldstr    aDescription_0// "description"
0x3de2d  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x3de32  ldstr    aSystemformForm_2// "SystemForm.FormDescription.Quick"
0x3de37  ldloc.2
0x3de38  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3de3d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de42  ldloc.1
0x3de43  ldstr    aFormxml// "formxml"
0x3de48  ldarg.0
0x3de49  ldarg.1
0x3de4a  ldloc.0
0x3de4b  ldarg.s  4
0x3de4d  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultQuickViewFormXml(class Microsoft.Crm.Metadata.EntityCreateInfo entityCreateInfo, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3de52  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3de57  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de5c  ldarg.1
0x3de5d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x3de62  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x3de67  brfalse.s loc_3DEBD
0x3de69  ldloc.1
0x3de6a  ldstr    aFormpresentati// "formpresentation"
0x3de6f  ldc.i4.1
0x3de70  box      [mscorlib]System.Int32
0x3de75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de7a  br.s     loc_3DEBD
0x3de7c  ldloc.1
0x3de7d  ldstr    aDescription_0// "description"
0x3de82  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Metadata.LocalizationHelper::get_Resources()
0x3de87  ldstr    aSystemformForm_3// "SystemForm.FormDescription.Preview"
0x3de8c  ldloc.2
0x3de8d  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3de92  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3de97  ldloc.1
0x3de98  ldstr    aFormxml// "formxml"
0x3de9d  ldarg.0
0x3de9e  ldloc.0
0x3de9f  ldarg.s  4
0x3dea1  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultPreviewXml(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3dea6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3deab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3deb0  br.s     loc_3DEBD
0x3deb2  ldstr    aDefaultFormCon// "Default form constructor is not defined"...
0x3deb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3debc  throw
0x3debd  ldarg.3
0x3debe  ldloc.1
0x3debf  ldloc.0
0x3dec0  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::ToArray()
0x3dec5  ldarg.s  4
0x3dec7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::CreateForNewEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3decc  pop
0x3decd  leave    loc_3DF72
0x3ded2  stloc.s  4
0x3ded4  ldc.i4.0
0x3ded5  stloc.s  5
0x3ded7  ldarg.s  4
0x3ded9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x3dede  stloc.s  6
0x3dee0  ldloc.s  6
0x3dee2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3dee7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3deec  pop
0x3deed  ldloc.s  6
0x3deef  ldstr    aSelectMaxObjec// "select MAX(ObjectTypeCode) as MaxOTC fr"...
0x3def4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3def9  ldloc.s  6
0x3defb  ldc.i4   0x8B
0x3df00  ldstr    aCreateform// "CreateForm"
0x3df05  ldstr    aDA1SSrcCoreObj_4// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x3df0a  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x3df0f  stloc.s  7
0x3df11  br.s     loc_3DF26
0x3df13  ldloc.s  7
0x3df15  ldstr    aMaxotc// "MaxOTC"
0x3df1a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3df1f  unbox.any [mscorlib]System.Int32
0x3df24  stloc.s  5
0x3df26  ldloc.s  7
0x3df28  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x3df2d  brtrue.s loc_3DF13
0x3df2f  leave.s  loc_3DF3D
0x3df31  ldloc.s  7
0x3df33  brfalse.s loc_3DF3C
0x3df35  ldloc.s  7
0x3df37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3df3c  endfinally
0x3df3d  leave.s  loc_3DF4B
0x3df3f  ldloc.s  6
0x3df41  brfalse.s loc_3DF4A
0x3df43  ldloc.s  6
0x3df45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3df4a  endfinally
0x3df4b  ldloc.s  4
0x3df4d  ldarg.s  4
0x3df4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3df54  ldc.i4.s 0x19
0x3df56  ldstr    aTodoThisCodeHa// "TODO: This code has to be removed in Co"...
0x3df5b  ldc.i4.1
0x3df5c  newarr   [mscorlib]System.Object
0x3df61  dup
0x3df62  ldc.i4.0
0x3df63  ldloc.s  5
0x3df65  box      [mscorlib]System.Int32
0x3df6a  stelem.ref
0x3df6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3df70  rethrow
0x3df72  ret
```
