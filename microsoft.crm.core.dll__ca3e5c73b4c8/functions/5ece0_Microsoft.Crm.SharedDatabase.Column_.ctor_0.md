# Microsoft.Crm.SharedDatabase.Column::.ctor_0

- ea: `0x5ece0`
- end: `0x5f0ee`
- name: `Microsoft.Crm.SharedDatabase.Column::.ctor_0`
- size: `1038`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5ecd0`
- `0x65010`

## callees

- `0x1a860`
- `0x1a880`
- `0x2d8d0`
- `0x5ece0`
- `0x5f0f0`
- `0x5f170`
- `0x5f180`
- `0x5f1a0`
- `0x5f3e0`
- `0x5f420`
- `0x60aa0`

## string_xrefs

- `0x5eef2`: `IsIdentity`
- `0x5eeff`: `IsIdentity`
- `0x5f0be`: `IsReadable`
- `0x5f0cb`: `IsReadable`

## pseudocode

```c

```

## disassembly

```asm
0x5ece0  ldarg.0
0x5ece1  call     instance void [mscorlib]System.Object::.ctor()
0x5ece6  ldarg.0
0x5ece7  call     instance void Microsoft.Crm.SharedDatabase.Column::Initialize()
0x5ecec  ldarg.1
0x5eced  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5ecf2  stloc.0
0x5ecf3  ldarg.0
0x5ecf4  ldloc.0
0x5ecf5  ldstr    aName// "Name"
0x5ecfa  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5ecff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5ed04  stfld    string Microsoft.Crm.SharedDatabase.Column::_name
0x5ed09  ldarg.1
0x5ed0a  ldstr    aDescription_0// "Description"
0x5ed0f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ed14  brfalse.s loc_5ED28
0x5ed16  ldarg.1
0x5ed17  ldstr    aDescription_0// "Description"
0x5ed1c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ed21  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ed26  br.s     loc_5ED29
0x5ed28  ldnull
0x5ed29  stloc.1
0x5ed2a  ldloc.1
0x5ed2b  brtrue.s loc_5ED3D
0x5ed2d  ldstr    aDescriptionMus// "Description must be specified"
0x5ed32  ldc.i4   0x80044197
0x5ed37  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x5ed3c  throw
0x5ed3d  ldarg.0
0x5ed3e  ldtoken  [System.Data]System.Data.SqlDbType
0x5ed43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ed48  ldarg.1
0x5ed49  ldstr    aType// "Type"
0x5ed4e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ed53  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ed58  ldc.i4.1
0x5ed59  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value, bool ignoreCase)
0x5ed5e  unbox.any [System.Data]System.Data.SqlDbType
0x5ed63  stfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::_sqlType
0x5ed68  ldarg.2
0x5ed69  ldc.i4.m1
0x5ed6a  beq.s    loc_5EDA3
0x5ed6c  ldarg.0
0x5ed6d  ldarg.1
0x5ed6e  ldstr    aSchematype// "SchemaType"
0x5ed73  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ed78  brfalse.s loc_5ED9B
0x5ed7a  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSchemaType
0x5ed7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ed84  ldarg.1
0x5ed85  ldstr    aSchematype// "SchemaType"
0x5ed8a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ed8f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ed94  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x5ed99  br.s     loc_5ED9C
0x5ed9b  ldarg.2
0x5ed9c  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigSchemaType Microsoft.Crm.SharedDatabase.Column::_schemaType
0x5eda1  br.s     loc_5EDC8
0x5eda3  ldarg.0
0x5eda4  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSchemaType
0x5eda9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5edae  ldarg.1
0x5edaf  ldstr    aSchematype// "SchemaType"
0x5edb4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5edb9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5edbe  call     int32 Microsoft.Crm.SharedDatabase.ConvertUtility::EnumFromXmlString(class [mscorlib]System.Type enumType, string mask)
0x5edc3  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigSchemaType Microsoft.Crm.SharedDatabase.Column::_schemaType
0x5edc8  ldarg.0
0x5edc9  ldarg.1
0x5edca  ldstr    aCachingkey// "CachingKey"
0x5edcf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5edd4  brfalse.s loc_5EDED
0x5edd6  ldarg.1
0x5edd7  ldstr    aCachingkey// "CachingKey"
0x5eddc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ede1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ede6  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5edeb  br.s     loc_5EDEE
0x5eded  ldc.i4.0
0x5edee  stfld    bool Microsoft.Crm.SharedDatabase.Column::_cachingKey
0x5edf3  ldarg.0
0x5edf4  ldarg.1
0x5edf5  ldstr    aPrimarykey_0// "PrimaryKey"
0x5edfa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5edff  brfalse.s loc_5EE18
0x5ee01  ldarg.1
0x5ee02  ldstr    aPrimarykey_0// "PrimaryKey"
0x5ee07  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ee0c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ee11  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5ee16  br.s     loc_5EE19
0x5ee18  ldc.i4.0
0x5ee19  stfld    bool Microsoft.Crm.SharedDatabase.Column::_primaryKey
0x5ee1e  ldarg.0
0x5ee1f  ldarg.1
0x5ee20  ldstr    aNonclustered// "Nonclustered"
0x5ee25  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ee2a  brfalse.s loc_5EE43
0x5ee2c  ldarg.1
0x5ee2d  ldstr    aNonclustered// "Nonclustered"
0x5ee32  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ee37  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ee3c  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5ee41  br.s     loc_5EE44
0x5ee43  ldc.i4.0
0x5ee44  call     instance void Microsoft.Crm.SharedDatabase.Column::set_Nonclustered(bool value)
0x5ee49  ldarg.0
0x5ee4a  call     instance bool Microsoft.Crm.SharedDatabase.Column::get_Nonclustered()
0x5ee4f  brfalse.s loc_5EE6F
0x5ee51  ldarg.0
0x5ee52  ldfld    bool Microsoft.Crm.SharedDatabase.Column::_primaryKey
0x5ee57  brtrue.s loc_5EE6F
0x5ee59  ldstr    aNonclusteredOp// "NonClustered option is only valid for t"...
0x5ee5e  ldarg.0
0x5ee5f  ldfld    string Microsoft.Crm.SharedDatabase.Column::_name
0x5ee64  call     string [mscorlib]System.String::Concat(string, string)
0x5ee69  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x5ee6e  throw
0x5ee6f  ldarg.0
0x5ee70  ldarg.1
0x5ee71  ldstr    aCasesensitive// "CaseSensitive"
0x5ee76  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ee7b  brfalse.s loc_5EE94
0x5ee7d  ldarg.1
0x5ee7e  ldstr    aCasesensitive// "CaseSensitive"
0x5ee83  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ee88  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ee8d  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5ee92  br.s     loc_5EE95
0x5ee94  ldc.i4.0
0x5ee95  call     instance void Microsoft.Crm.SharedDatabase.Column::set_CaseSensitive(bool value)
0x5ee9a  ldarg.0
0x5ee9b  ldarg.1
0x5ee9c  ldstr    aNullable// "Nullable"
0x5eea1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eea6  brfalse.s loc_5EEBF
0x5eea8  ldarg.1
0x5eea9  ldstr    aNullable// "Nullable"
0x5eeae  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eeb3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5eeb8  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5eebd  br.s     loc_5EEC0
0x5eebf  ldc.i4.0
0x5eec0  stfld    bool Microsoft.Crm.SharedDatabase.Column::_nullable
0x5eec5  ldarg.0
0x5eec6  ldarg.1
0x5eec7  ldstr    aEncrypted// "Encrypted"
0x5eecc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eed1  brfalse.s loc_5EEEA
0x5eed3  ldarg.1
0x5eed4  ldstr    aEncrypted// "Encrypted"
0x5eed9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eede  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5eee3  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5eee8  br.s     loc_5EEEB
0x5eeea  ldc.i4.0
0x5eeeb  stfld    bool Microsoft.Crm.SharedDatabase.Column::_encrypted
0x5eef0  ldarg.0
0x5eef1  ldarg.1
0x5eef2  ldstr    aIsidentity// "IsIdentity"
0x5eef7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eefc  brfalse.s loc_5EF15
0x5eefe  ldarg.1
0x5eeff  ldstr    aIsidentity// "IsIdentity"
0x5ef04  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ef09  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ef0e  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5ef13  br.s     loc_5EF16
0x5ef15  ldc.i4.0
0x5ef16  stfld    bool Microsoft.Crm.SharedDatabase.Column::_identity
0x5ef1b  ldarg.0
0x5ef1c  ldfld    bool Microsoft.Crm.SharedDatabase.Column::_encrypted
0x5ef21  brfalse.s loc_5EF99
0x5ef23  ldarg.0
0x5ef24  ldarg.1
0x5ef25  ldstr    aEncryptwithkey// "EncryptWithKey"
0x5ef2a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ef2f  brfalse.s loc_5EF58
0x5ef31  ldtoken  Microsoft.Crm.SharedDatabase.CrmEncryptionKey
0x5ef36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ef3b  ldarg.1
0x5ef3c  ldstr    aEncryptwithkey// "EncryptWithKey"
0x5ef41  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ef46  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ef4b  ldc.i4.1
0x5ef4c  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value, bool ignoreCase)
0x5ef51  unbox.any Microsoft.Crm.SharedDatabase.CrmEncryptionKey
0x5ef56  br.s     loc_5EF59
0x5ef58  ldc.i4.0
0x5ef59  stfld    valuetype Microsoft.Crm.SharedDatabase.CrmEncryptionKey Microsoft.Crm.SharedDatabase.Column::_encryptionKey
0x5ef5e  ldarg.0
0x5ef5f  ldarg.1
0x5ef60  ldstr    aForceencryptio// "ForceEncryptionSKU"
0x5ef65  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ef6a  brfalse.s loc_5EF93
0x5ef6c  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSku
0x5ef71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ef76  ldarg.1
0x5ef77  ldstr    aForceencryptio// "ForceEncryptionSKU"
0x5ef7c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5ef81  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5ef86  ldc.i4.1
0x5ef87  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value, bool ignoreCase)
0x5ef8c  unbox.any Microsoft.Crm.SharedDatabase.ConfigSku
0x5ef91  br.s     loc_5EF94
0x5ef93  ldc.i4.0
0x5ef94  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.SharedDatabase.Column::_forceEncryptionSku
0x5ef99  ldarg.0
0x5ef9a  ldarg.1
0x5ef9b  ldstr    aUniqueifier// "Uniqueifier"
0x5efa0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5efa5  brfalse.s loc_5EFBE
0x5efa7  ldarg.1
0x5efa8  ldstr    aUniqueifier// "Uniqueifier"
0x5efad  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5efb2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5efb7  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5efbc  br.s     loc_5EFBF
0x5efbe  ldc.i4.0
0x5efbf  stfld    bool Microsoft.Crm.SharedDatabase.Column::_uniqueifier
0x5efc4  ldarg.0
0x5efc5  ldfld    bool Microsoft.Crm.SharedDatabase.Column::_uniqueifier
0x5efca  brfalse.s loc_5EFE6
0x5efcc  ldc.i4.s 0xE
0x5efce  ldarg.0
0x5efcf  ldfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::_sqlType
0x5efd4  beq.s    loc_5EFE6
0x5efd6  ldstr    aUniqueifierCol// "Uniqueifier column must be of type uniq"...
0x5efdb  ldc.i4   0x80040216
0x5efe0  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x5efe5  throw
0x5efe6  ldarg.1
0x5efe7  ldstr    aLength_0// "Length"
0x5efec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5eff1  brfalse.s loc_5F005
0x5eff3  ldarg.1
0x5eff4  ldstr    aLength_0// "Length"
0x5eff9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5effe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5f003  br.s     loc_5F006
0x5f005  ldnull
0x5f006  stloc.2
0x5f007  ldloc.2
0x5f008  brfalse.s loc_5F02C
0x5f00a  ldloc.2
0x5f00b  ldstr    aMax// "max"
0x5f010  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5f015  brfalse.s loc_5F020
0x5f017  ldarg.0
0x5f018  ldc.i4.m1
0x5f019  stfld    int32 Microsoft.Crm.SharedDatabase.Column::_dataLength
0x5f01e  br.s     loc_5F02C
0x5f020  ldarg.0
0x5f021  ldloc.2
0x5f022  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x5f027  stfld    int32 Microsoft.Crm.SharedDatabase.Column::_dataLength
0x5f02c  ldarg.0
0x5f02d  ldfld    bool Microsoft.Crm.SharedDatabase.Column::_primaryKey
0x5f032  brfalse.s loc_5F04C
0x5f034  ldarg.0
0x5f035  ldfld    bool Microsoft.Crm.SharedDatabase.Column::_nullable
0x5f03a  brfalse.s loc_5F04C
0x5f03c  ldstr    aPrimaryKeyCann// "Primary Key cannot be nullable"
0x5f041  ldc.i4   0x80044196
0x5f046  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x5f04b  throw
0x5f04c  ldarg.0
0x5f04d  ldarg.1
0x5f04e  ldstr    aDefault// "Default"
0x5f053  ldarg.0
0x5f054  ldfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::_sqlType
0x5f059  call     object Microsoft.Crm.SharedDatabase.Column::ValueFromXml(class [System.Xml]System.Xml.XmlNode node, string elementName, valuetype [System.Data]System.Data.SqlDbType sqlType)
0x5f05e  stfld    object Microsoft.Crm.SharedDatabase.Column::_defaultValue
0x5f063  ldarg.0
0x5f064  ldarg.1
0x5f065  ldstr    aMin// "Min"
0x5f06a  ldarg.0
0x5f06b  ldfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::_sqlType
0x5f070  call     object Microsoft.Crm.SharedDatabase.Column::ValueFromXml(class [System.Xml]System.Xml.XmlNode node, string elementName, valuetype [System.Data]System.Data.SqlDbType sqlType)
0x5f075  stfld    object Microsoft.Crm.SharedDatabase.Column::_minValue
0x5f07a  ldarg.0
0x5f07b  ldarg.1
0x5f07c  ldstr    aMax_0// "Max"
0x5f081  ldarg.0
0x5f082  ldfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::_sqlType
0x5f087  call     object Microsoft.Crm.SharedDatabase.Column::ValueFromXml(class [System.Xml]System.Xml.XmlNode node, string elementName, valuetype [System.Data]System.Data.SqlDbType sqlType)
0x5f08c  stfld    object Microsoft.Crm.SharedDatabase.Column::_maxValue
0x5f091  ldarg.0
0x5f092  ldarg.1
0x5f093  ldstr    aIswritable// "IsWritable"
0x5f098  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5f09d  brfalse.s loc_5F0B6
0x5f09f  ldarg.1
0x5f0a0  ldstr    aIswritable// "IsWritable"
0x5f0a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5f0aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5f0af  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x5f0b4  br.s     loc_5F0B7
  ... truncated ...
```
