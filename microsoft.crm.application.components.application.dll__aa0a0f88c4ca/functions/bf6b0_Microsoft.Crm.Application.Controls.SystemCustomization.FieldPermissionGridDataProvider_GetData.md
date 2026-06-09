# Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetData

- ea: `0xbf6b0`
- end: `0xbf94b`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetData`
- size: `667`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0xbf580`
- `0xbf5a0`
- `0xbf5c0`
- `0xbf5e0`
- `0xbf600`
- `0xbf620`
- `0xbf640`
- `0xbf660`
- `0xbf680`
- `0xbf6b0`
- `0xbf950`
- `0xbfd70`
- `0xbfdc0`
- `0xbfe40`
- `0xf4210`

## string_xrefs

- `0xbf6f0`: `canread`
- `0xbf6f8`: `canupdate`
- `0xbf700`: `cancreate`
- `0xbf712`: `update`
- `0xbf71b`: `create`

## pseudocode

```c

```

## disassembly

```asm
0xbf6b0  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbf6b5  stloc.0
0xbf6b6  ldarg.1
0xbf6b7  ldc.i4.s 0xE
0xbf6b9  newarr   [mscorlib]System.String
0xbf6be  dup
0xbf6bf  ldc.i4.0
0xbf6c0  ldstr    aOid// "oid"
0xbf6c5  stelem.ref
0xbf6c6  dup
0xbf6c7  ldc.i4.1
0xbf6c8  ldstr    aMoid// "moid"
0xbf6cd  stelem.ref
0xbf6ce  dup
0xbf6cf  ldc.i4.2
0xbf6d0  ldstr    aAttributename// "attributename"
0xbf6d5  stelem.ref
0xbf6d6  dup
0xbf6d7  ldc.i4.3
0xbf6d8  ldstr    aAttributedispl// "attributedisplayname"
0xbf6dd  stelem.ref
0xbf6de  dup
0xbf6df  ldc.i4.4
0xbf6e0  ldstr    aType// "type"
0xbf6e5  stelem.ref
0xbf6e6  dup
0xbf6e7  ldc.i4.5
0xbf6e8  ldstr    aEntitydisplayn// "entitydisplayname"
0xbf6ed  stelem.ref
0xbf6ee  dup
0xbf6ef  ldc.i4.6
0xbf6f0  ldstr    aCanread// "canread"
0xbf6f5  stelem.ref
0xbf6f6  dup
0xbf6f7  ldc.i4.7
0xbf6f8  ldstr    aCanupdate// "canupdate"
0xbf6fd  stelem.ref
0xbf6fe  dup
0xbf6ff  ldc.i4.8
0xbf700  ldstr    aCancreate// "cancreate"
0xbf705  stelem.ref
0xbf706  dup
0xbf707  ldc.i4.s 9
0xbf709  ldstr    aRead// "read"
0xbf70e  stelem.ref
0xbf70f  dup
0xbf710  ldc.i4.s 0xA
0xbf712  ldstr    aUpdate_0// "update"
0xbf717  stelem.ref
0xbf718  dup
0xbf719  ldc.i4.s 0xB
0xbf71b  ldstr    aCreate_0// "create"
0xbf720  stelem.ref
0xbf721  dup
0xbf722  ldc.i4.s 0xC
0xbf724  ldstr    aEntity// "entity"
0xbf729  stelem.ref
0xbf72a  dup
0xbf72b  ldc.i4.s 0xD
0xbf72d  ldstr    aAttribute// "attribute"
0xbf732  stelem.ref
0xbf733  stind.ref
0xbf734  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xbf739  stloc.1
0xbf73a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::.ctor()
0xbf73f  stloc.2
0xbf740  ldarg.0
0xbf741  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveOptionSetNames()
0xbf746  ldloca.s 3
0xbf748  ldarg.0
0xbf749  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbf74e  ldstr    aOid// "oid"
0xbf753  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbf758  call     instance void [mscorlib]System.Guid::.ctor(string)
0xbf75d  ldarg.0
0xbf75e  ldloc.3
0xbf75f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SystemFieldSecurityProfileId
0xbf764  ldloc.2
0xbf765  ldloc.1
0xbf766  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissions(valuetype [mscorlib]System.Guid profileId, valuetype [mscorlib]System.Guid sysProfileId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION> fps, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xbf76b  ldloc.2
0xbf76c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::GetEnumerator()
0xbf771  stloc.s  4
0xbf773  br       loc_BF917
0xbf778  ldloca.s 4
0xbf77a  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Current()
0xbf77f  stloc.s  5
0xbf781  ldc.i4.s 0xE
0xbf783  newarr   [mscorlib]System.String
0xbf788  dup
0xbf789  ldc.i4.0
0xbf78a  ldloca.s 5
0xbf78c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf791  stloc.s  7
0xbf793  ldloca.s 7
0xbf795  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_fpId()
0xbf79a  stloc.s  8
0xbf79c  ldloca.s 8
0xbf79e  ldstr    aB// "B"
0xbf7a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf7a8  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0xbf7ad  stelem.ref
0xbf7ae  dup
0xbf7af  ldc.i4.1
0xbf7b0  ldstr    aFieldpermissio// "fieldpermission"
0xbf7b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbf7ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbf7bf  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xbf7c4  stloc.s  9
0xbf7c6  ldloca.s 9
0xbf7c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf7cd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbf7d2  stelem.ref
0xbf7d3  dup
0xbf7d4  ldc.i4.2
0xbf7d5  ldloca.s 5
0xbf7d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf7dc  stloc.s  7
0xbf7de  ldloca.s 7
0xbf7e0  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_AttributeName()
0xbf7e5  stelem.ref
0xbf7e6  dup
0xbf7e7  ldc.i4.3
0xbf7e8  ldloca.s 5
0xbf7ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf7ef  stloc.s  7
0xbf7f1  ldloca.s 7
0xbf7f3  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_AttributeDisplayName()
0xbf7f8  stelem.ref
0xbf7f9  dup
0xbf7fa  ldc.i4.4
0xbf7fb  ldarg.0
0xbf7fc  ldloca.s 5
0xbf7fe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf803  stloc.s  7
0xbf805  ldloca.s 7
0xbf807  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_AttributeType()
0xbf80c  ldloca.s 5
0xbf80e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf813  stloc.s  7
0xbf815  ldloca.s 7
0xbf817  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_AttributeType()
0xbf81c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xbf821  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetTypeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo type, string defaultName)
0xbf826  stelem.ref
0xbf827  dup
0xbf828  ldc.i4.5
0xbf829  ldloca.s 5
0xbf82b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf830  stloc.s  7
0xbf832  ldloca.s 7
0xbf834  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_EntityDisplayName()
0xbf839  stelem.ref
0xbf83a  dup
0xbf83b  ldc.i4.6
0xbf83c  ldarg.0
0xbf83d  ldloca.s 5
0xbf83f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf844  stloc.s  7
0xbf846  ldloca.s 7
0xbf848  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Read()
0xbf84d  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbf852  stelem.ref
0xbf853  dup
0xbf854  ldc.i4.7
0xbf855  ldarg.0
0xbf856  ldloca.s 5
0xbf858  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf85d  stloc.s  7
0xbf85f  ldloca.s 7
0xbf861  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Update()
0xbf866  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbf86b  stelem.ref
0xbf86c  dup
0xbf86d  ldc.i4.8
0xbf86e  ldarg.0
0xbf86f  ldloca.s 5
0xbf871  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf876  stloc.s  7
0xbf878  ldloca.s 7
0xbf87a  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Create()
0xbf87f  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::GetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xbf884  stelem.ref
0xbf885  dup
0xbf886  ldc.i4.s 9
0xbf888  ldloca.s 5
0xbf88a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf88f  stloc.s  7
0xbf891  ldloca.s 7
0xbf893  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Read()
0xbf898  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf89d  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xbf8a2  stelem.ref
0xbf8a3  dup
0xbf8a4  ldc.i4.s 0xA
0xbf8a6  ldloca.s 5
0xbf8a8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf8ad  stloc.s  7
0xbf8af  ldloca.s 7
0xbf8b1  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Update()
0xbf8b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf8bb  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xbf8c0  stelem.ref
0xbf8c1  dup
0xbf8c2  ldc.i4.s 0xB
0xbf8c4  ldloca.s 5
0xbf8c6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf8cb  stloc.s  7
0xbf8cd  ldloca.s 7
0xbf8cf  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_Create()
0xbf8d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf8d9  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xbf8de  stelem.ref
0xbf8df  dup
0xbf8e0  ldc.i4.s 0xC
0xbf8e2  ldloca.s 5
0xbf8e4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf8e9  stloc.s  7
0xbf8eb  ldloca.s 7
0xbf8ed  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_EntityName()
0xbf8f2  stelem.ref
0xbf8f3  dup
0xbf8f4  ldc.i4.s 0xD
0xbf8f6  ldloca.s 5
0xbf8f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::get_Value()
0xbf8fd  stloc.s  7
0xbf8ff  ldloca.s 7
0xbf901  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION::get_AttributeName()
0xbf906  stelem.ref
0xbf907  stloc.s  6
0xbf909  ldloc.0
0xbf90a  ldloc.s  6
0xbf90c  newobj   instance void Row::.ctor(string[] columns)
0xbf911  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbf916  pop
0xbf917  ldloca.s 4
0xbf919  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>::MoveNext()
0xbf91e  brtrue   loc_BF778
0xbf923  leave.s  loc_BF933
0xbf925  ldloca.s 4
0xbf927  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION>
0xbf92d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbf932  endfinally
0xbf933  ldarg.2
0xbf934  ldloc.0
0xbf935  ldtoken  Row
0xbf93a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbf93f  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xbf944  castclass class Row[]
0xbf949  stind.ref
0xbf94a  ret
```
