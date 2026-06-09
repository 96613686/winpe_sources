# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityHomeGridEvents

- ea: `0xbc70`
- end: `0xbd7e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityHomeGridEvents`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xbc70`

## string_xrefs

- `0xbcee`: `eventsxml`
- `0xbd53`: `eventsxml`
- `0xbd58`: `<customControlDefaultConfig>`
- `0xbd64`: `</customControlDefaultConfig>`
- `0xbc97`: `xmlns`
- `0xbcda`: `customcontroldefaultconfig`

## pseudocode

```c

```

## disassembly

```asm
0xbc70  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xbc75  ldarg.2
0xbc76  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbc7b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0xbc80  stloc.0
0xbc81  ldloc.0
0xbc82  brtrue.s loc_BC8F
0xbc84  ldstr    aUnableToFindEn// "Unable to find entity metadata"
0xbc89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xbc8e  throw
0xbc8f  ldarg.1
0xbc90  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xbc95  stloc.1
0xbc96  ldloc.1
0xbc97  ldstr    aXmlns// "xmlns"
0xbc9c  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0xbca1  stloc.2
0xbca2  ldloc.2
0xbca3  ldc.i4.m1
0xbca4  beq.s    loc_BCCA
0xbca6  ldloc.1
0xbca7  ldc.i4.0
0xbca8  ldloc.2
0xbca9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xbcae  stloc.s  6
0xbcb0  ldloc.1
0xbcb1  ldloc.2
0xbcb2  ldc.i4.5
0xbcb3  add
0xbcb4  callvirt instance string [mscorlib]System.String::Substring(int32)
0xbcb9  stloc.s  7
0xbcbb  ldloc.s  6
0xbcbd  ldstr    aNoneAttribute// "none-attribute"
0xbcc2  ldloc.s  7
0xbcc4  call     string [mscorlib]System.String::Concat(string, string, string)
0xbcc9  stloc.1
0xbcca  ldloc.1
0xbccb  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xbcd0  stloc.3
0xbcd1  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0xbcd6  stloc.s  4
0xbcd8  ldloc.s  4
0xbcda  ldstr    aCustomcontrold_2// "customcontroldefaultconfig"
0xbcdf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0xbce4  ldloc.s  4
0xbce6  ldc.i4.1
0xbce7  newarr   [mscorlib]System.String
0xbcec  dup
0xbced  ldc.i4.0
0xbcee  ldstr    aEventsxml// "eventsxml"
0xbcf3  stelem.ref
0xbcf4  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xbcf9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0xbcfe  ldloc.s  4
0xbd00  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xbd05  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xbd0a  ldstr    aPrimaryentityt// "primaryentitytypecode"
0xbd0f  ldc.i4.0
0xbd10  ldloc.0
0xbd11  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xbd16  box      [mscorlib]System.Int32
0xbd1b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0xbd20  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbd25  pop
0xbd26  ldloc.s  4
0xbd28  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbd2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbd32  stloc.s  5
0xbd34  ldloc.s  5
0xbd36  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xbd3b  brfalse.s loc_BD7D
0xbd3d  ldloc.s  5
0xbd3f  ldc.i4.0
0xbd40  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xbd45  ldloc.3
0xbd46  ldstr    aEntityForm_0// "/entity/form"
0xbd4b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xbd50  stloc.s  8
0xbd52  dup
0xbd53  ldstr    aEventsxml// "eventsxml"
0xbd58  ldstr    aCustomcontrold_0// "<customControlDefaultConfig>"
0xbd5d  ldloc.s  8
0xbd5f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xbd64  ldstr    aCustomcontrold_1// "</customControlDefaultConfig>"
0xbd69  call     string [mscorlib]System.String::Concat(string, string, string)
0xbd6e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xbd73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbd78  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbd7d  ret
```
