# Microsoft.Crm.Application.Forms.FormDescriptorLoader::LoadCacheData

- ea: `0x31890`
- end: `0x31aef`
- name: `Microsoft.Crm.Application.Forms.FormDescriptorLoader::LoadCacheData`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16b80`
- `0x16b90`
- `0x1bce0`
- `0x1be70`
- `0x1c210`
- `0x317f0`
- `0x31890`
- `0x31af0`
- `0x31cb0`
- `0x31f30`
- `0x31f50`
- `0x320b0`
- `0x32120`
- `0x32140`
- `0x32160`
- `0x32180`
- `0x321a0`
- `0x321c0`
- `0x32200`
- `0x32220`
- `0x32240`
- `0x339d0`
- `0x33a80`
- `0x5be20`
- `0xa3700`

## string_xrefs

- `0x31975`: `formxml`
- `0x31987`: `componentstate`
- `0x31890`: `FormDescrCache`
- `0x31ac5`: `Form XML not found for entity {0} and form type {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x31890  ldstr    aFormdescrcache// "FormDescrCache"
0x31895  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x3189a  stloc.0
0x3189b  ldloc.0
0x3189c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x318a1  ldnull
0x318a2  stloc.1
0x318a3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x318a8  stloc.2
0x318a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x318ae  stloc.3
0x318af  ldsfld   string [mscorlib]System.String::Empty
0x318b4  stloc.s  4
0x318b6  ldc.i4.0
0x318b7  stloc.s  5
0x318b9  ldc.i4.0
0x318ba  stloc.s  6
0x318bc  ldc.i4.m1
0x318bd  stloc.s  7
0x318bf  ldc.i4.0
0x318c0  conv.i8
0x318c1  stloc.s  8
0x318c3  ldc.i4.0
0x318c4  stloc.s  9
0x318c6  ldc.i4.0
0x318c7  stloc.s  0xA
0x318c9  ldnull
0x318ca  stloc.s  0xB
0x318cc  call     class ClientFormDescriptorDefinitionCache ClientFormDescriptorDefinitionCache::Instance()
0x318d1  ldarg.1
0x318d2  ldarg.2
0x318d3  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Application.Forms.FormDescriptorCacheKey, class Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue>::LookupEntry(void, var<u1>)
0x318d8  stloc.s  0xC
0x318da  ldloc.s  0xC
0x318dc  brtrue   loc_31A1D
0x318e1  ldarg.1
0x318e2  ldarg.2
0x318e3  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve(class Microsoft.Crm.Application.Forms.FormDescriptorCacheKey key, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x318e8  stloc.1
0x318e9  ldloc.1
0x318ea  brtrue.s loc_31963
0x318ec  ldarg.1
0x318ed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::get_FormId()
0x318f2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x318f7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x318fc  brfalse.s loc_31963
0x318fe  ldarg.0
0x318ff  ldarg.1
0x31900  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::get_FormId()
0x31905  ldarg.2
0x31906  call     instance class Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormDescriptorLoader::GetDefaultFormDescriptor(valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3190b  stloc.s  0xB
0x3190d  ldloc.s  0xB
0x3190f  callvirt instance string Microsoft.Crm.Application.FormDescriptor::get_ID()
0x31914  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x31919  stloc.2
0x3191a  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x3191f  callvirt instance bool Microsoft.Crm.Application.Utility.ClientContext::get_IsMobileClientWebDialog()
0x31924  brtrue.s loc_3193D
0x31926  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x3192b  ldarg.2
0x3192c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x31931  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x31936  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x3193b  br.s     loc_31952
0x3193d  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x31942  ldarg.2
0x31943  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x31948  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserUICulture()
0x3194d  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x31952  stloc.s  0xD
0x31954  ldloc.2
0x31955  ldloc.s  0xD
0x31957  newobj   instance void Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::.ctor(valuetype [mscorlib]System.Guid formId, int32 baseLanguageId)
0x3195c  ldarg.2
0x3195d  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve(class Microsoft.Crm.Application.Forms.FormDescriptorCacheKey key, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x31962  stloc.1
0x31963  ldloc.1
0x31964  ldstr    aFormid// "formid"
0x31969  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x3196e  unbox.any [mscorlib]System.Guid
0x31973  stloc.2
0x31974  ldloc.1
0x31975  ldstr    aFormxml// "formxml"
0x3197a  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x3197f  castclass [mscorlib]System.String
0x31984  stloc.s  4
0x31986  ldloc.1
0x31987  ldstr    aComponentstate// "componentstate"
0x3198c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31991  unbox.any [mscorlib]System.Int32
0x31996  stloc.s  5
0x31998  ldloc.1
0x31999  ldstr    aSolutionid_0// "solutionid"
0x3199e  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319a3  unbox.any [mscorlib]System.Guid
0x319a8  stloc.3
0x319a9  ldloc.1
0x319aa  ldstr    aObjecttypecode// "objecttypecode"
0x319af  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319b4  brtrue.s loc_319B9
0x319b6  ldc.i4.0
0x319b7  br.s     loc_319C9
0x319b9  ldloc.1
0x319ba  ldstr    aObjecttypecode// "objecttypecode"
0x319bf  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319c4  unbox.any [mscorlib]System.Int32
0x319c9  stloc.s  6
0x319cb  ldloc.1
0x319cc  ldstr    aType// "type"
0x319d1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319d6  unbox.any [mscorlib]System.Int32
0x319db  call     valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::ConvertSdkFormTypeToAppFormType(int32 formType)
0x319e0  stloc.s  7
0x319e2  ldloc.1
0x319e3  ldstr    aVersionnumber// "versionnumber"
0x319e8  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319ed  unbox.any [mscorlib]System.Int64
0x319f2  stloc.s  8
0x319f4  ldloc.1
0x319f5  ldstr    aFormpresentati// "formpresentation"
0x319fa  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x319ff  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode
0x31a04  stloc.s  9
0x31a06  ldloc.1
0x31a07  ldstr    aFormactivation// "formactivationstate"
0x31a0c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31a11  unbox.any [mscorlib]System.Int32
0x31a16  ldc.i4.1
0x31a17  ceq
0x31a19  stloc.s  0xA
0x31a1b  br.s     loc_31A6C
0x31a1d  ldloc.s  0xC
0x31a1f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_FormId()
0x31a24  stloc.2
0x31a25  ldloc.s  0xC
0x31a27  callvirt instance string Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_FormXml()
0x31a2c  stloc.s  4
0x31a2e  ldloc.s  0xC
0x31a30  callvirt instance int32 Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_CompState()
0x31a35  stloc.s  5
0x31a37  ldloc.s  0xC
0x31a39  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_SolutionId()
0x31a3e  stloc.3
0x31a3f  ldloc.s  0xC
0x31a41  callvirt instance int32 Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_Otc()
0x31a46  stloc.s  6
0x31a48  ldloc.s  0xC
0x31a4a  callvirt instance valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_FormType()
0x31a4f  stloc.s  7
0x31a51  ldloc.s  0xC
0x31a53  callvirt instance int64 Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_VersionNumber()
0x31a58  stloc.s  8
0x31a5a  ldloc.s  0xC
0x31a5c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_FormPresentation()
0x31a61  stloc.s  9
0x31a63  ldloc.s  0xC
0x31a65  callvirt instance bool Microsoft.Crm.Application.Forms.FormDescriptorDefinitionValue::get_IsActive()
0x31a6a  stloc.s  0xA
0x31a6c  ldloc.s  4
0x31a6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31a73  brtrue.s loc_31AC0
0x31a75  ldloc.s  7
0x31a77  ldc.i4.7
0x31a78  bne.un.s loc_31A86
0x31a7a  ldarg.0
0x31a7b  ldloc.s  4
0x31a7d  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Forms.FormDescriptorLoader::PreProcessMobileFormXml(string formXml)
0x31a82  stloc.s  0xE
0x31a84  br.s     loc_31A8F
0x31a86  ldloc.s  4
0x31a88  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x31a8d  stloc.s  0xE
0x31a8f  ldloc.s  0xB
0x31a91  brtrue.s loc_31AA9
0x31a93  ldloc.s  6
0x31a95  ldloc.s  0xE
0x31a97  ldloc.2
0x31a98  ldloc.s  7
0x31a9a  ldloc.s  8
0x31a9c  ldloc.s  9
0x31a9e  ldloc.s  0xA
0x31aa0  ldarg.2
0x31aa1  ldc.i4.1
0x31aa2  newobj   instance void Microsoft.Crm.Application.FormDescriptor::.ctor(int32 typeCode, class [System.Xml]System.Xml.XmlNode formXml, valuetype [mscorlib]System.Guid formId, valuetype Microsoft.Crm.Application.FormType formType, int64 versionNumber, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.FormPresentationMode formPresentation, bool isActive, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool insertLabel)
0x31aa7  stloc.s  0xB
0x31aa9  ldloc.s  0xB
0x31aab  ldarg.2
0x31aac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x31ab1  ldloc.s  5
0x31ab3  ldloc.3
0x31ab4  newobj   instance void Microsoft.Crm.Application.Forms.FormDescriptorCacheValue::.ctor(class Microsoft.Crm.Application.FormDescriptor descriptor, valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState componentState, valuetype [mscorlib]System.Guid solutionId)
0x31ab9  ldloc.0
0x31aba  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x31abf  ret
0x31ac0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31ac5  ldstr    aFormXmlNotFoun// "Form XML not found for entity {0} and f"...
0x31aca  ldc.i4.2
0x31acb  newarr   [mscorlib]System.Object
0x31ad0  dup
0x31ad1  ldc.i4.0
0x31ad2  ldloc.s  6
0x31ad4  box      [mscorlib]System.Int32
0x31ad9  stelem.ref
0x31ada  dup
0x31adb  ldc.i4.1
0x31adc  ldloc.s  7
0x31ade  box      Microsoft.Crm.Application.FormType
0x31ae3  stelem.ref
0x31ae4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31ae9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x31aee  throw
```
