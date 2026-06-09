# Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::LoadData

- ea: `0x51bf0`
- end: `0x52029`
- name: `Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::LoadData`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x51bf0`
- `0x52030`

## string_xrefs

- `0x51ea7`: `canDelete`
- `0x51edb`: `canDelete`
- `0x51ed4`: `canDelete_Hidden`
- `0x51eec`: `canOverwrite`
- `0x51f18`: `canOverwrite`
- `0x51f11`: `canOverwrite_Hidden`
- `0x51f56`: `isFormReadOnly`
- `0x51f6a`: `isFormReadOnly`
- `0x51fa5`: `isFormReadOnly`
- `0x51f9e`: `isFormReadOnly_Hidden`

## pseudocode

```c

```

## disassembly

```asm
0x51bf0  ldarg.0
0x51bf1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::LoadData()
0x51bf6  ldc.i4.0
0x51bf7  stloc.0
0x51bf8  ldarg.0
0x51bf9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0x51bfe  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0x51c03  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x51c08  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.InternalDataCollectionBase::GetEnumerator()
0x51c0d  stloc.3
0x51c0e  br       loc_52001
0x51c13  ldloc.3
0x51c14  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x51c19  castclass [System.Data]System.Data.DataRow
0x51c1e  stloc.s  4
0x51c20  ldloc.s  4
0x51c22  ldstr    aDatatypeValue// "datatype_Value"
0x51c27  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51c2c  unbox.any [mscorlib]System.Int32
0x51c31  stloc.s  5
0x51c33  ldloc.s  5
0x51c35  switch   loc_51C53, loc_51C8A, loc_51CC1, loc_51D6D, loc_51DA1
0x51c4e  br       loc_51DD3
0x51c53  ldloc.s  4
0x51c55  ldstr    aDefaultattribu// "defaultattributevalue"
0x51c5a  ldloc.s  4
0x51c5c  ldstr    aDefaultvalueop// "defaultvalueoptionset"
0x51c61  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51c66  brtrue.s loc_51C6F
0x51c68  ldsfld   string [mscorlib]System.String::Empty
0x51c6d  br.s     loc_51C80
0x51c6f  ldloc.s  4
0x51c71  ldstr    aDefaultvalueop// "defaultvalueoptionset"
0x51c76  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51c7b  callvirt instance string [mscorlib]System.Object::ToString()
0x51c80  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51c85  br       loc_51DD3
0x51c8a  ldloc.s  4
0x51c8c  ldstr    aDefaultattribu// "defaultattributevalue"
0x51c91  ldloc.s  4
0x51c93  ldstr    aDefaultvaluede// "defaultvaluedecimal"
0x51c98  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51c9d  brtrue.s loc_51CA6
0x51c9f  ldsfld   string [mscorlib]System.String::Empty
0x51ca4  br.s     loc_51CB7
0x51ca6  ldloc.s  4
0x51ca8  ldstr    aDefaultvaluede// "defaultvaluedecimal"
0x51cad  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51cb2  callvirt instance string [mscorlib]System.Object::ToString()
0x51cb7  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51cbc  br       loc_51DD3
0x51cc1  ldsfld   string [mscorlib]System.String::Empty
0x51cc6  stloc.s  6
0x51cc8  ldloc.s  4
0x51cca  ldstr    aDefaultvaluedo// "defaultvaluedouble"
0x51ccf  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51cd4  callvirt instance string [mscorlib]System.Object::ToString()
0x51cd9  dup
0x51cda  stloc.s  6
0x51cdc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51ce1  brtrue.s loc_51D5D
0x51ce3  ldloc.s  4
0x51ce5  ldstr    aPrecision// "precision"
0x51cea  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51cef  callvirt instance string [mscorlib]System.Object::ToString()
0x51cf4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51cf9  brtrue.s loc_51D5D
0x51cfb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x51d00  ldstr    a0N0// "{{0:N{0}}}"
0x51d05  ldc.i4.1
0x51d06  newarr   [mscorlib]System.Object
0x51d0b  dup
0x51d0c  ldc.i4.0
0x51d0d  ldloc.s  4
0x51d0f  ldstr    aPrecision// "precision"
0x51d14  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51d19  callvirt instance string [mscorlib]System.Object::ToString()
0x51d1e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x51d23  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x51d28  box      [mscorlib]System.Int32
0x51d2d  stelem.ref
0x51d2e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x51d33  stloc.s  7
0x51d35  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x51d3a  ldloc.s  7
0x51d3c  ldc.i4.1
0x51d3d  newarr   [mscorlib]System.Object
0x51d42  dup
0x51d43  ldc.i4.0
0x51d44  ldloc.s  6
0x51d46  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x51d4b  call     float64 [mscorlib]System.Convert::ToDouble(string, class [mscorlib]System.IFormatProvider)
0x51d50  box      [mscorlib]System.Double
0x51d55  stelem.ref
0x51d56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x51d5b  stloc.s  6
0x51d5d  ldloc.s  4
0x51d5f  ldstr    aDefaultattribu// "defaultattributevalue"
0x51d64  ldloc.s  6
0x51d66  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51d6b  br.s     loc_51DD3
0x51d6d  ldloc.s  4
0x51d6f  ldstr    aDefaultattribu// "defaultattributevalue"
0x51d74  ldloc.s  4
0x51d76  ldstr    aDefaultvaluest// "defaultvaluestring"
0x51d7b  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51d80  brtrue.s loc_51D89
0x51d82  ldsfld   string [mscorlib]System.String::Empty
0x51d87  br.s     loc_51D9A
0x51d89  ldloc.s  4
0x51d8b  ldstr    aDefaultvaluest// "defaultvaluestring"
0x51d90  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51d95  callvirt instance string [mscorlib]System.Object::ToString()
0x51d9a  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51d9f  br.s     loc_51DD3
0x51da1  ldloc.s  4
0x51da3  ldstr    aDefaultattribu// "defaultattributevalue"
0x51da8  ldloc.s  4
0x51daa  ldstr    aDefaultvaluein// "defaultvalueinteger"
0x51daf  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51db4  brtrue.s loc_51DBD
0x51db6  ldsfld   string [mscorlib]System.String::Empty
0x51dbb  br.s     loc_51DCE
0x51dbd  ldloc.s  4
0x51dbf  ldstr    aDefaultvaluein// "defaultvalueinteger"
0x51dc4  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51dc9  callvirt instance string [mscorlib]System.Object::ToString()
0x51dce  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51dd3  ldarg.0
0x51dd4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51dd9  ldloc.0
0x51dda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51ddf  brfalse  loc_51FFD
0x51de4  ldarg.0
0x51de5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51dea  ldloc.0
0x51deb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51df0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x51df5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DynamicProperties.Constants/Relationships::get_DynamicPropertyAssociation()
0x51dfa  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::Contains(var<u1>)
0x51dff  brfalse  loc_51FFD
0x51e04  ldarg.0
0x51e05  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51e0a  ldloc.0
0x51e0b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51e10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x51e15  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DynamicProperties.Constants/Relationships::get_DynamicPropertyAssociation()
0x51e1a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x51e1f  ldc.i4.0
0x51e20  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51e25  stloc.s  8
0x51e27  ldloc.s  4
0x51e29  ldstr    aInheritancesta// "inheritancestatus"
0x51e2e  ldloc.s  8
0x51e30  ldstr    aInheritancesta_0// "inheritancestate"
0x51e35  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x51e3a  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x51e3f  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x51e44  box      [mscorlib]System.Int32
0x51e49  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51e4e  ldloc.s  4
0x51e50  ldstr    aInheritancesta// "inheritancestatus"
0x51e55  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51e5a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x51e5f  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x51e64  stloc.1
0x51e65  ldloc.s  4
0x51e67  ldstr    aCanoverride// "canOverride"
0x51e6c  ldloc.1
0x51e6d  brtrue.s loc_51E7F
0x51e6f  ldarg.0
0x51e70  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isDraftRegardingObject
0x51e75  brtrue.s loc_51E82
0x51e77  ldarg.0
0x51e78  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isRevisedRegardingObject
0x51e7d  brtrue.s loc_51E82
0x51e7f  ldc.i4.0
0x51e80  br.s     loc_51E83
0x51e82  ldc.i4.1
0x51e83  box      [mscorlib]System.Boolean
0x51e88  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51e8d  ldloc.s  4
0x51e8f  ldstr    aCanoverrideHid// "canOverride_Hidden"
0x51e94  ldloc.s  4
0x51e96  ldstr    aCanoverride// "canOverride"
0x51e9b  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51ea0  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51ea5  ldloc.s  4
0x51ea7  ldstr    aCandelete// "canDelete"
0x51eac  ldloc.1
0x51ead  ldc.i4.2
0x51eae  beq.s    loc_51EB4
0x51eb0  ldloc.1
0x51eb1  ldc.i4.1
0x51eb2  bne.un.s loc_51EC4
0x51eb4  ldarg.0
0x51eb5  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isDraftRegardingObject
0x51eba  brtrue.s loc_51EC7
0x51ebc  ldarg.0
0x51ebd  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isRevisedRegardingObject
0x51ec2  brtrue.s loc_51EC7
0x51ec4  ldc.i4.0
0x51ec5  br.s     loc_51EC8
0x51ec7  ldc.i4.1
0x51ec8  box      [mscorlib]System.Boolean
0x51ecd  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51ed2  ldloc.s  4
0x51ed4  ldstr    aCandeleteHidde// "canDelete_Hidden"
0x51ed9  ldloc.s  4
0x51edb  ldstr    aCandelete// "canDelete"
0x51ee0  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51ee5  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51eea  ldloc.s  4
0x51eec  ldstr    aCanoverwrite// "canOverwrite"
0x51ef1  ldloc.1
0x51ef2  ldc.i4.2
0x51ef3  beq.s    loc_51EF9
0x51ef5  ldloc.1
0x51ef6  ldc.i4.1
0x51ef7  bne.un.s loc_51F01
0x51ef9  ldarg.0
0x51efa  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isRevisedRegardingObject
0x51eff  brtrue.s loc_51F04
0x51f01  ldc.i4.0
0x51f02  br.s     loc_51F05
0x51f04  ldc.i4.1
0x51f05  box      [mscorlib]System.Boolean
0x51f0a  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51f0f  ldloc.s  4
0x51f11  ldstr    aCanoverwriteHi// "canOverwrite_Hidden"
0x51f16  ldloc.s  4
0x51f18  ldstr    aCanoverwrite// "canOverwrite"
0x51f1d  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51f22  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51f27  ldarg.0
0x51f28  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51f2d  ldloc.0
0x51f2e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51f33  ldstr    aStatecode// "statecode"
0x51f38  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x51f3d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x51f42  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x51f47  stloc.2
0x51f48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x51f4d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51f52  brfalse.s loc_51F68
0x51f54  ldloc.s  4
0x51f56  ldstr    aIsformreadonly// "isFormReadOnly"
0x51f5b  ldc.i4.1
0x51f5c  box      [mscorlib]System.Boolean
0x51f61  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51f66  br.s     loc_51F9C
0x51f68  ldloc.s  4
0x51f6a  ldstr    aIsformreadonly// "isFormReadOnly"
0x51f6f  ldloc.1
0x51f70  ldc.i4.2
0x51f71  beq.s    loc_51F77
0x51f73  ldloc.1
0x51f74  ldc.i4.1
0x51f75  bne.un.s loc_51F91
0x51f77  ldloc.2
0x51f78  ldc.i4.1
0x51f79  bne.un.s loc_51F91
0x51f7b  ldarg.0
0x51f7c  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isDraftRegardingObject
0x51f81  brtrue.s loc_51F8E
0x51f83  ldarg.0
0x51f84  ldfld    bool Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::isRevisedRegardingObject
0x51f89  ldc.i4.0
0x51f8a  ceq
0x51f8c  br.s     loc_51F92
0x51f8e  ldc.i4.0
0x51f8f  br.s     loc_51F92
0x51f91  ldc.i4.1
0x51f92  box      [mscorlib]System.Boolean
0x51f97  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51f9c  ldloc.s  4
0x51f9e  ldstr    aIsformreadonly_0// "isFormReadOnly_Hidden"
0x51fa3  ldloc.s  4
0x51fa5  ldstr    aIsformreadonly// "isFormReadOnly"
0x51faa  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x51faf  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x51fb4  ldarg.0
0x51fb5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51fba  ldloc.0
0x51fbb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51fc0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x51fc5  ldstr    aBasedynamicpro// "basedynamicpropertyid"
0x51fca  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x51fcf  brfalse.s loc_51FFD
0x51fd1  ldloc.s  4
0x51fd3  ldstr    aBasedynamicpro// "basedynamicpropertyid"
0x51fd8  ldarg.0
0x51fd9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.DynamicPropertyGridDataProvider::dynamicPropertiesBasedOnPaging
0x51fde  ldloc.0
0x51fdf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x51fe4  ldstr    aBasedynamicpro// "basedynamicpropertyid"
0x51fe9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x51fee  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x51ff3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
  ... truncated ...
```
