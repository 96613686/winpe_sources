# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetInvokeSdkMessageParameterValue

- ea: `0x6680`
- end: `0x6ab4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetInvokeSdkMessageParameterValue`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6360`

## callees

- `0x6680`

## pseudocode

```c

```

## disassembly

```asm
0x6680  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6685  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x668a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x668f  stloc.0
0x6690  ldarg.1
0x6691  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6696  ldtoken  [mscorlib]System.String
0x669b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66a0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x66a5  brfalse.s loc_66AE
0x66a7  ldarg.2
0x66a8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x66ad  ret
0x66ae  ldarg.1
0x66af  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x66b4  ldtoken  [mscorlib]System.Guid
0x66b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66be  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x66c3  brfalse.s loc_66DD
0x66c5  ldarg.2
0x66c6  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x66cb  pop
0x66cc  ldarg.2
0x66cd  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x66d2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x66d7  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier::.ctor(valuetype [mscorlib]System.Guid)
0x66dc  ret
0x66dd  ldarg.1
0x66de  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x66e3  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x66e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66ed  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x66f2  brfalse.s loc_670C
0x66f4  ldarg.2
0x66f5  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x66fa  ldc.i4.s 0x6F
0x66fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6701  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x6706  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber::.ctor(int32)
0x670b  ret
0x670c  ldarg.1
0x670d  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6712  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal
0x6717  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x671c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6721  brfalse.s loc_6739
0x6723  ldarg.2
0x6724  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6729  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x672e  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x6733  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal::.ctor(valuetype [mscorlib]System.Decimal)
0x6738  ret
0x6739  ldarg.1
0x673a  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x673f  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble
0x6744  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6749  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x674e  brfalse.s loc_6766
0x6750  ldarg.2
0x6751  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6756  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x675b  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x6760  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble::.ctor(float64)
0x6765  ret
0x6766  ldarg.1
0x6767  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x676c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat
0x6771  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6776  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x677b  brfalse.s loc_6793
0x677d  ldarg.2
0x677e  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6783  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6788  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x678d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat::.ctor(float64)
0x6792  ret
0x6793  ldarg.1
0x6794  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6799  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney
0x679e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67a3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67a8  brfalse.s loc_67C0
0x67aa  ldarg.2
0x67ab  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x67b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67b5  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x67ba  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney::.ctor(valuetype [mscorlib]System.Decimal)
0x67bf  ret
0x67c0  ldarg.1
0x67c1  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x67c6  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean
0x67cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67d0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67d5  brfalse.s loc_67E8
0x67d7  ldarg.2
0x67d8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x67dd  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x67e2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean::.ctor(bool)
0x67e7  ret
0x67e8  ldarg.1
0x67e9  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x67ee  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime
0x67f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67f8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67fd  brfalse.s loc_6845
0x67ff  ldarg.2
0x6800  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6805  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x680a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x680f  stloc.1
0x6810  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6815  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x681a  ldloc.1
0x681b  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToUniversalTime(valuetype [mscorlib]System.DateTime)
0x6820  stloc.2
0x6821  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6826  ldstr    a0SZ// "{0:s}Z"
0x682b  ldc.i4.1
0x682c  newarr   [mscorlib]System.Object
0x6831  dup
0x6832  ldc.i4.0
0x6833  ldloc.2
0x6834  box      [mscorlib]System.DateTime
0x6839  stelem.ref
0x683a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x683f  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::.ctor(string)
0x6844  ret
0x6845  ldarg.1
0x6846  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x684b  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x6850  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6855  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x685a  brfalse.s loc_68A8
0x685c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor()
0x6861  ldarg.2
0x6862  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x6867  pop
0x6868  dup
0x6869  ldarg.2
0x686a  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x686f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6874  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x6879  ldarg.2
0x687a  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x687f  pop
0x6880  ldarg.2
0x6881  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6886  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x688b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6890  stloc.3
0x6891  dup
0x6892  ldloc.3
0x6893  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6898  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x689d  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x68a2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x68a7  ret
0x68a8  ldarg.1
0x68a9  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x68ae  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer
0x68b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68b8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x68bd  brfalse.s loc_690D
0x68bf  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer::.ctor()
0x68c4  ldarg.2
0x68c5  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x68ca  pop
0x68cb  dup
0x68cc  ldarg.2
0x68cd  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x68d2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x68d7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x68dc  ldarg.2
0x68dd  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x68e2  pop
0x68e3  ldarg.2
0x68e4  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x68e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68ee  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x68f3  stloc.s  4
0x68f5  dup
0x68f6  ldloc.s  4
0x68f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x68fd  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6902  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6907  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x690c  ret
0x690d  ldarg.1
0x690e  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6913  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner
0x6918  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x691d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6922  brfalse.s loc_6972
0x6924  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner::.ctor()
0x6929  ldarg.2
0x692a  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x692f  pop
0x6930  dup
0x6931  ldarg.2
0x6932  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6937  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x693c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x6941  ldarg.2
0x6942  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x6947  pop
0x6948  ldarg.2
0x6949  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x694e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6953  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6958  stloc.s  5
0x695a  dup
0x695b  ldloc.s  5
0x695d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6962  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6967  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x696c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x6971  ret
0x6972  ldarg.1
0x6973  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6978  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status
0x697d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6982  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6987  brfalse  loc_6A12
0x698c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::.ctor()
0x6991  stloc.s  6
0x6993  ldloc.s  6
0x6995  ldarg.2
0x6996  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x699b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69a0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x69a5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_Value(int32)
0x69aa  ldarg.1
0x69ab  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x69b0  ldc.i4.0
0x69b1  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x69b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69bb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69c0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x69c5  ldarg.1
0x69c6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_AttributeName()
0x69cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x69d0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x69d5  stloc.s  7
0x69d7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x69dc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x69e1  stloc.s  8
0x69e3  ldloc.s  6
0x69e5  ldloc.s  7
0x69e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x69ec  ldloc.s  6
0x69ee  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::get_Value()
0x69f3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x69f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x69fd  ldloc.s  8
0x69ff  ldloc.0
0x6a00  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a05  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x6a0a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_name(string)
0x6a0f  ldloc.s  6
0x6a11  ret
0x6a12  ldarg.1
0x6a13  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x6a18  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist
0x6a1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a22  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6a27  brfalse  loc_6AB2
0x6a2c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::.ctor()
0x6a31  stloc.s  9
0x6a33  ldloc.s  9
0x6a35  ldarg.2
0x6a36  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x6a3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6a40  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6a45  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::set_Value(int32)
0x6a4a  ldarg.1
0x6a4b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x6a50  ldc.i4.0
0x6a51  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x6a56  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a5b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a60  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6a65  ldarg.1
0x6a66  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_AttributeName()
0x6a6b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x6a70  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x6a75  stloc.s  0xA
0x6a77  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x6a7c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x6a81  stloc.s  0xB
0x6a83  ldloc.s  9
0x6a85  ldloc.s  0xA
0x6a87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x6a8c  ldloc.s  9
0x6a8e  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::get_Value()
0x6a93  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x6a98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x6a9d  ldloc.s  0xB
0x6a9f  ldloc.0
0x6aa0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6aa5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
  ... truncated ...
```
