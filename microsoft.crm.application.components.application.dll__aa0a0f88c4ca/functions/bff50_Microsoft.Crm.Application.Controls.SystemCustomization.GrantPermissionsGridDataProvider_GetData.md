# Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::GetData

- ea: `0xbff50`
- end: `0xc0141`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::GetData`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0xbfea0`
- `0xbfec0`
- `0xbfee0`
- `0xbff00`
- `0xbff20`
- `0xbff50`
- `0xc0150`
- `0xc03d0`
- `0xc0420`
- `0xf4210`

## string_xrefs

- `0xbff7f`: `canread`
- `0xbff87`: `canupdate`
- `0xbff97`: `update`

## pseudocode

```c

```

## disassembly

```asm
0xbff50  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbff55  stloc.0
0xbff56  ldarg.1
0xbff57  ldc.i4.8
0xbff58  newarr   [mscorlib]System.String
0xbff5d  dup
0xbff5e  ldc.i4.0
0xbff5f  ldstr    aOid// "oid"
0xbff64  stelem.ref
0xbff65  dup
0xbff66  ldc.i4.1
0xbff67  ldstr    aMoid// "moid"
0xbff6c  stelem.ref
0xbff6d  dup
0xbff6e  ldc.i4.2
0xbff6f  ldstr    aAttributename// "attributename"
0xbff74  stelem.ref
0xbff75  dup
0xbff76  ldc.i4.3
0xbff77  ldstr    aAttributedispl// "attributedisplayname"
0xbff7c  stelem.ref
0xbff7d  dup
0xbff7e  ldc.i4.4
0xbff7f  ldstr    aCanread// "canread"
0xbff84  stelem.ref
0xbff85  dup
0xbff86  ldc.i4.5
0xbff87  ldstr    aCanupdate// "canupdate"
0xbff8c  stelem.ref
0xbff8d  dup
0xbff8e  ldc.i4.6
0xbff8f  ldstr    aRead// "read"
0xbff94  stelem.ref
0xbff95  dup
0xbff96  ldc.i4.7
0xbff97  ldstr    aUpdate_0// "update"
0xbff9c  stelem.ref
0xbff9d  stind.ref
0xbff9e  ldarg.0
0xbff9f  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbffa4  ldstr    aPrincipalid// "principalid"
0xbffa9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbffae  stloc.1
0xbffaf  ldloc.1
0xbffb0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbffb5  brtrue   loc_C0129
0xbffba  ldarg.0
0xbffbb  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbffc0  ldstr    aPrincipaltype// "principaltype"
0xbffc5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbffca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbffcf  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xbffd4  stloc.2
0xbffd5  ldarg.0
0xbffd6  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbffdb  ldstr    aObjectid// "objectid"
0xbffe0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbffe5  stloc.3
0xbffe6  ldarg.0
0xbffe7  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xbffec  ldstr    aObjecttype_0// "objecttype"
0xbfff1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbfff6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbfffb  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xc0000  stloc.s  4
0xc0002  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xc0007  stloc.s  5
0xc0009  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::.ctor()
0xc000e  stloc.s  6
0xc0010  ldarg.0
0xc0011  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::RetrieveOptionSetNames()
0xc0016  ldarg.0
0xc0017  ldloc.1
0xc0018  ldloc.2
0xc0019  ldloc.3
0xc001a  ldloc.s  4
0xc001c  ldloc.s  6
0xc001e  ldloc.s  5
0xc0020  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::RetrieveFieldPermissions(string principalId, int32 principalType, string objectId, int32 objectType, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION> fps, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xc0025  ldloc.s  6
0xc0027  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::GetEnumerator()
0xc002c  stloc.s  7
0xc002e  br       loc_C010D
0xc0033  ldloca.s 7
0xc0035  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Current()
0xc003a  stloc.s  8
0xc003c  ldc.i4.8
0xc003d  newarr   [mscorlib]System.String
0xc0042  dup
0xc0043  ldc.i4.0
0xc0044  ldloca.s 8
0xc0046  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc004b  stloc.s  0xA
0xc004d  ldloca.s 0xA
0xc004f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_attributeId()
0xc0054  stloc.s  0xB
0xc0056  ldloca.s 0xB
0xc0058  ldstr    aB// "B"
0xc005d  call     instance string [mscorlib]System.Guid::ToString(string)
0xc0062  stelem.ref
0xc0063  dup
0xc0064  ldc.i4.1
0xc0065  ldstr    a1201// "1201"
0xc006a  stelem.ref
0xc006b  dup
0xc006c  ldc.i4.2
0xc006d  ldloca.s 8
0xc006f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc0074  stloc.s  0xA
0xc0076  ldloca.s 0xA
0xc0078  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_AttributeName()
0xc007d  stelem.ref
0xc007e  dup
0xc007f  ldc.i4.3
0xc0080  ldloca.s 8
0xc0082  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc0087  stloc.s  0xA
0xc0089  ldloca.s 0xA
0xc008b  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_AttributeDisplayName()
0xc0090  stelem.ref
0xc0091  dup
0xc0092  ldc.i4.4
0xc0093  ldarg.0
0xc0094  ldloca.s 8
0xc0096  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc009b  stloc.s  0xA
0xc009d  ldloca.s 0xA
0xc009f  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_Read()
0xc00a4  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::GetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xc00a9  stelem.ref
0xc00aa  dup
0xc00ab  ldc.i4.5
0xc00ac  ldarg.0
0xc00ad  ldloca.s 8
0xc00af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc00b4  stloc.s  0xA
0xc00b6  ldloca.s 0xA
0xc00b8  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_Update()
0xc00bd  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.GrantPermissionsGridDataProvider::GetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess value)
0xc00c2  stelem.ref
0xc00c3  dup
0xc00c4  ldc.i4.6
0xc00c5  ldloca.s 8
0xc00c7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc00cc  stloc.s  0xA
0xc00ce  ldloca.s 0xA
0xc00d0  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_Read()
0xc00d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc00da  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc00df  stelem.ref
0xc00e0  dup
0xc00e1  ldc.i4.7
0xc00e2  ldloca.s 8
0xc00e4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::get_Value()
0xc00e9  stloc.s  0xA
0xc00eb  ldloca.s 0xA
0xc00ed  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION::get_Update()
0xc00f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc00f7  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc00fc  stelem.ref
0xc00fd  stloc.s  9
0xc00ff  ldloc.0
0xc0100  ldloc.s  9
0xc0102  newobj   instance void Row::.ctor(string[] columns)
0xc0107  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc010c  pop
0xc010d  ldloca.s 7
0xc010f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>::MoveNext()
0xc0114  brtrue   loc_C0033
0xc0119  leave.s  loc_C0129
0xc011b  ldloca.s 7
0xc011d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.PERMISSION>
0xc0123  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc0128  endfinally
0xc0129  ldarg.2
0xc012a  ldloc.0
0xc012b  ldtoken  Row
0xc0130  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc0135  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xc013a  castclass class Row[]
0xc013f  stind.ref
0xc0140  ret
```
