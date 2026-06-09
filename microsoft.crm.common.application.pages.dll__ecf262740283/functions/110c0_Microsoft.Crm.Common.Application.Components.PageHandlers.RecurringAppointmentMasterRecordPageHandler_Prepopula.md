# Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::PrepopulateForm

- ea: `0x110c0`
- end: `0x11233`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::PrepopulateForm`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10ff0`

## callees

- `0x110c0`
- `0x11240`
- `0x11510`

## string_xrefs

- `0x110cb`: `appointmentXml`
- `0x110e1`: `recurrenceXml`

## pseudocode

```c

```

## disassembly

```asm
0x110c0  ldarg.0
0x110c1  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x110c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x110cb  ldstr    aAppointmentxml// "appointmentXml"
0x110d0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x110d5  stloc.0
0x110d6  ldarg.0
0x110d7  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x110dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x110e1  ldstr    aRecurrencexml// "recurrenceXml"
0x110e6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x110eb  stloc.1
0x110ec  ldloc.1
0x110ed  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x110f2  brtrue.s loc_11100
0x110f4  ldarg.0
0x110f5  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x110fa  ldloc.1
0x110fb  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x11100  ldloc.0
0x11101  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11106  brtrue   loc_11232
0x1110b  ldarg.0
0x1110c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::GetDictionaryForLinkedAttribute()
0x11111  stloc.2
0x11112  ldstr    aAppointment// "appointment"
0x11117  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1111c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11121  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11126  stloc.3
0x11127  ldloc.3
0x11128  ldloc.0
0x11129  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x1112e  ldloc.3
0x1112f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x11134  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x11139  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x1113e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x11143  stloc.s  5
0x11145  br       loc_111E0
0x1114a  ldloc.s  5
0x1114c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11151  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x11156  stloc.s  6
0x11158  ldloc.s  6
0x1115a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x1115f  stloc.s  7
0x11161  ldloc.s  7
0x11163  stloc.s  8
0x11165  ldloc.s  6
0x11167  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomField()
0x1116c  brfalse.s loc_1118C
0x1116e  ldloc.2
0x1116f  ldloc.s  6
0x11171  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x11176  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0x1117b  brfalse.s loc_1118C
0x1117d  ldloc.2
0x1117e  ldloc.s  6
0x11180  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x11185  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0x1118a  stloc.s  8
0x1118c  ldloc.s  6
0x1118e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsPrimaryKey()
0x11193  brtrue.s loc_111E0
0x11195  ldarg.0
0x11196  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1119b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x111a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x111a5  ldloc.s  8
0x111a7  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x111ac  brfalse.s loc_111E0
0x111ae  ldloc.s  6
0x111b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x111b5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x111ba  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x111bf  brfalse.s loc_111E0
0x111c1  ldloc.3
0x111c2  ldloc.s  7
0x111c4  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x111c9  brfalse.s loc_111E0
0x111cb  ldarg.0
0x111cc  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x111d1  ldloc.s  8
0x111d3  ldloc.3
0x111d4  ldloc.s  7
0x111d6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x111db  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x111e0  ldloc.s  5
0x111e2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x111e7  brtrue   loc_1114A
0x111ec  leave.s  loc_11203
0x111ee  ldloc.s  5
0x111f0  isinst   [mscorlib]System.IDisposable
0x111f5  stloc.s  9
0x111f7  ldloc.s  9
0x111f9  brfalse.s loc_11202
0x111fb  ldloc.s  9
0x111fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11202  endfinally
0x11203  ldloc.3
0x11204  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x11209  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1120e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x11213  stloc.s  4
0x11215  ldloc.3
0x11216  ldloc.s  4
0x11218  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x1121d  brfalse.s loc_11232
0x1121f  ldarg.0
0x11220  ldloc.3
0x11221  ldloc.s  4
0x11223  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x11228  unbox.any [mscorlib]System.Guid
0x1122d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_appointmentId
0x11232  ret
```
