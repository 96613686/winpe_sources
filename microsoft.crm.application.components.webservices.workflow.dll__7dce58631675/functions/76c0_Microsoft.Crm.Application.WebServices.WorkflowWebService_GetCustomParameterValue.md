# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomParameterValue

- ea: `0x76c0`
- end: `0x7ac5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomParameterValue`
- size: `1029`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28b0`
- `0x6d70`

## callees

- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x76c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x76c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x76ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x76cf  stloc.0
0x76d0  ldarg.1
0x76d1  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x76d6  ldtoken  [mscorlib]System.String
0x76db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76e0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x76e5  brfalse.s loc_76EE
0x76e7  ldarg.2
0x76e8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x76ed  ret
0x76ee  ldarg.1
0x76ef  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x76f4  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x76f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76fe  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7703  brfalse.s loc_771D
0x7705  ldarg.2
0x7706  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x770b  ldc.i4.s 0x6F
0x770d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7712  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x7717  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber::.ctor(int32)
0x771c  ret
0x771d  ldarg.1
0x771e  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x7723  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal
0x7728  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x772d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7732  brfalse.s loc_774A
0x7734  ldarg.2
0x7735  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x773a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x773f  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x7744  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal::.ctor(valuetype [mscorlib]System.Decimal)
0x7749  ret
0x774a  ldarg.1
0x774b  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x7750  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble
0x7755  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x775a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x775f  brfalse.s loc_7777
0x7761  ldarg.2
0x7762  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7767  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x776c  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x7771  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble::.ctor(float64)
0x7776  ret
0x7777  ldarg.1
0x7778  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x777d  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat
0x7782  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7787  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x778c  brfalse.s loc_77A4
0x778e  ldarg.2
0x778f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7794  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7799  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x779e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat::.ctor(float64)
0x77a3  ret
0x77a4  ldarg.1
0x77a5  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x77aa  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney
0x77af  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x77b4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x77b9  brfalse.s loc_77D1
0x77bb  ldarg.2
0x77bc  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x77c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x77c6  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x77cb  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney::.ctor(valuetype [mscorlib]System.Decimal)
0x77d0  ret
0x77d1  ldarg.1
0x77d2  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x77d7  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean
0x77dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x77e1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x77e6  brfalse.s loc_77F9
0x77e8  ldarg.2
0x77e9  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x77ee  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x77f3  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean::.ctor(bool)
0x77f8  ret
0x77f9  ldarg.1
0x77fa  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x77ff  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime
0x7804  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7809  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x780e  brfalse.s loc_7856
0x7810  ldarg.2
0x7811  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7816  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x781b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x7820  stloc.1
0x7821  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x7826  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x782b  ldloc.1
0x782c  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToUniversalTime(valuetype [mscorlib]System.DateTime)
0x7831  stloc.2
0x7832  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7837  ldstr    a0SZ// "{0:s}Z"
0x783c  ldc.i4.1
0x783d  newarr   [mscorlib]System.Object
0x7842  dup
0x7843  ldc.i4.0
0x7844  ldloc.2
0x7845  box      [mscorlib]System.DateTime
0x784a  stelem.ref
0x784b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7850  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::.ctor(string)
0x7855  ret
0x7856  ldarg.1
0x7857  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x785c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x7861  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7866  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x786b  brfalse.s loc_78B9
0x786d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor()
0x7872  ldarg.2
0x7873  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x7878  pop
0x7879  dup
0x787a  ldarg.2
0x787b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7880  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7885  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x788a  ldarg.2
0x788b  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x7890  pop
0x7891  ldarg.2
0x7892  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7897  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x789c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x78a1  stloc.3
0x78a2  dup
0x78a3  ldloc.3
0x78a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78a9  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x78ae  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x78b3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x78b8  ret
0x78b9  ldarg.1
0x78ba  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x78bf  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer
0x78c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x78c9  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x78ce  brfalse.s loc_791E
0x78d0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer::.ctor()
0x78d5  ldarg.2
0x78d6  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x78db  pop
0x78dc  dup
0x78dd  ldarg.2
0x78de  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x78e3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x78e8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x78ed  ldarg.2
0x78ee  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x78f3  pop
0x78f4  ldarg.2
0x78f5  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x78fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78ff  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7904  stloc.s  4
0x7906  dup
0x7907  ldloc.s  4
0x7909  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x790e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7913  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x7918  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x791d  ret
0x791e  ldarg.1
0x791f  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x7924  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner
0x7929  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x792e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7933  brfalse.s loc_7983
0x7935  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner::.ctor()
0x793a  ldarg.2
0x793b  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x7940  pop
0x7941  dup
0x7942  ldarg.2
0x7943  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7948  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x794d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_Value(valuetype [mscorlib]System.Guid)
0x7952  ldarg.2
0x7953  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext()
0x7958  pop
0x7959  ldarg.2
0x795a  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x795f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7964  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7969  stloc.s  5
0x796b  dup
0x796c  ldloc.s  5
0x796e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7973  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7978  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x797d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_type(string)
0x7982  ret
0x7983  ldarg.1
0x7984  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x7989  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status
0x798e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7993  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7998  brfalse  loc_7A23
0x799d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::.ctor()
0x79a2  stloc.s  6
0x79a4  ldloc.s  6
0x79a6  ldarg.2
0x79a7  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x79ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79b1  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x79b6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_Value(int32)
0x79bb  ldarg.1
0x79bc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x79c1  ldc.i4.0
0x79c2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x79c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x79cc  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x79d1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x79d6  ldarg.1
0x79d7  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_AttributeName()
0x79dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x79e1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x79e6  stloc.s  7
0x79e8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x79ed  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x79f2  stloc.s  8
0x79f4  ldloc.s  6
0x79f6  ldloc.s  7
0x79f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x79fd  ldloc.s  6
0x79ff  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::get_Value()
0x7a04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x7a09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x7a0e  ldloc.s  8
0x7a10  ldloc.0
0x7a11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7a16  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7a1b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_name(string)
0x7a20  ldloc.s  6
0x7a22  ret
0x7a23  ldarg.1
0x7a24  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x7a29  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist
0x7a2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7a33  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7a38  brfalse  loc_7AC3
0x7a3d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::.ctor()
0x7a42  stloc.s  9
0x7a44  ldloc.s  9
0x7a46  ldarg.2
0x7a47  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x7a4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7a51  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7a56  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::set_Value(int32)
0x7a5b  ldarg.1
0x7a5c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x7a61  ldc.i4.0
0x7a62  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x7a67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7a6c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7a71  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x7a76  ldarg.1
0x7a77  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_AttributeName()
0x7a7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7a81  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x7a86  stloc.s  0xA
0x7a88  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x7a8d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x7a92  stloc.s  0xB
0x7a94  ldloc.s  9
0x7a96  ldloc.s  0xA
0x7a98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x7a9d  ldloc.s  9
0x7a9f  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::get_Value()
0x7aa4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x7aa9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x7aae  ldloc.s  0xB
0x7ab0  ldloc.0
0x7ab1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ab6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7abb  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::set_name(string)
0x7ac0  ldloc.s  9
0x7ac2  ret
0x7ac3  ldnull
0x7ac4  ret
```
