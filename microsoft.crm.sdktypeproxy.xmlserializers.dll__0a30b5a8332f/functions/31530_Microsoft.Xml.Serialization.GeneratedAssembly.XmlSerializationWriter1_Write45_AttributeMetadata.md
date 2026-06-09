# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write45_AttributeMetadata

- ea: `0x31530`
- end: `0x318a3`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write45_AttributeMetadata`
- size: `883`
- prototype: ``
- caller_count: `7`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x30290`
- `0x304e0`
- `0x686d0`
- `0x68760`
- `0x697c0`

## callees

- `0x11c0`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x31530`
- `0x318b0`
- `0x319c0`
- `0x31ba0`
- `0x31eb0`
- `0x321e0`
- `0x32540`
- `0x329a0`
- `0x32cc0`
- `0x32f10`
- `0x33160`
- `0x333b0`
- `0x33600`
- `0x33840`

## string_xrefs

- `0x316ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x316ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31717`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3172d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31743`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31759`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31771`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31789`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x317a1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x317b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x317d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x317e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31801`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31819`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31831`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31849`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3185f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31875`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3188b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x317e4`: `ValidForCreate`
- `0x317fc`: `ValidForRead`
- `0x31814`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x31530  ldarg.3
0x31531  brtrue.s loc_31540
0x31533  ldarg.s  4
0x31535  brfalse.s loc_3153F
0x31537  ldarg.0
0x31538  ldarg.1
0x31539  ldarg.2
0x3153a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3153f  ret
0x31540  ldarg.s  5
0x31542  brtrue   loc_316DA
0x31547  ldarg.3
0x31548  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3154d  stloc.0
0x3154e  ldloc.0
0x3154f  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata
0x31554  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31559  beq      loc_316DA
0x3155e  ldloc.0
0x3155f  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateAttributeMetadata
0x31564  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31569  bne.un.s loc_3157D
0x3156b  ldarg.0
0x3156c  ldarg.1
0x3156d  ldarg.2
0x3156e  ldarg.3
0x3156f  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateAttributeMetadata
0x31574  ldarg.s  4
0x31576  ldc.i4.1
0x31577  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write44_StateAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateAttributeMetadata o, bool isNullable, bool needType)
0x3157c  ret
0x3157d  ldloc.0
0x3157e  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.PicklistAttributeMetadata
0x31583  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31588  bne.un.s loc_3159C
0x3158a  ldarg.0
0x3158b  ldarg.1
0x3158c  ldarg.2
0x3158d  ldarg.3
0x3158e  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.PicklistAttributeMetadata
0x31593  ldarg.s  4
0x31595  ldc.i4.1
0x31596  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write42_PicklistAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.PicklistAttributeMetadata o, bool isNullable, bool needType)
0x3159b  ret
0x3159c  ldloc.0
0x3159d  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata
0x315a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x315a7  bne.un.s loc_315BB
0x315a9  ldarg.0
0x315aa  ldarg.1
0x315ab  ldarg.2
0x315ac  ldarg.3
0x315ad  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata
0x315b2  ldarg.s  4
0x315b4  ldc.i4.1
0x315b5  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write41_StringAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata o, bool isNullable, bool needType)
0x315ba  ret
0x315bb  ldloc.0
0x315bc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata
0x315c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x315c6  bne.un.s loc_315DA
0x315c8  ldarg.0
0x315c9  ldarg.1
0x315ca  ldarg.2
0x315cb  ldarg.3
0x315cc  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata
0x315d1  ldarg.s  4
0x315d3  ldc.i4.1
0x315d4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write40_MemoAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata o, bool isNullable, bool needType)
0x315d9  ret
0x315da  ldloc.0
0x315db  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata
0x315e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x315e5  bne.un.s loc_315F9
0x315e7  ldarg.0
0x315e8  ldarg.1
0x315e9  ldarg.2
0x315ea  ldarg.3
0x315eb  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata
0x315f0  ldarg.s  4
0x315f2  ldc.i4.1
0x315f3  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write37_DecimalAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata o, bool isNullable, bool needType)
0x315f8  ret
0x315f9  ldloc.0
0x315fa  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusAttributeMetadata
0x315ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31604  bne.un.s loc_31618
0x31606  ldarg.0
0x31607  ldarg.1
0x31608  ldarg.2
0x31609  ldarg.3
0x3160a  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusAttributeMetadata
0x3160f  ldarg.s  4
0x31611  ldc.i4.1
0x31612  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write36_StatusAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusAttributeMetadata o, bool isNullable, bool needType)
0x31617  ret
0x31618  ldloc.0
0x31619  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata
0x3161e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31623  bne.un.s loc_31637
0x31625  ldarg.0
0x31626  ldarg.1
0x31627  ldarg.2
0x31628  ldarg.3
0x31629  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata
0x3162e  ldarg.s  4
0x31630  ldc.i4.1
0x31631  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write34_LookupAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata o, bool isNullable, bool needType)
0x31636  ret
0x31637  ldloc.0
0x31638  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata
0x3163d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31642  bne.un.s loc_31656
0x31644  ldarg.0
0x31645  ldarg.1
0x31646  ldarg.2
0x31647  ldarg.3
0x31648  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata
0x3164d  ldarg.s  4
0x3164f  ldc.i4.1
0x31650  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write33_DateTimeAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata o, bool isNullable, bool needType)
0x31655  ret
0x31656  ldloc.0
0x31657  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata
0x3165c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31661  bne.un.s loc_31675
0x31663  ldarg.0
0x31664  ldarg.1
0x31665  ldarg.2
0x31666  ldarg.3
0x31667  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata
0x3166c  ldarg.s  4
0x3166e  ldc.i4.1
0x3166f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write30_BooleanAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata o, bool isNullable, bool needType)
0x31674  ret
0x31675  ldloc.0
0x31676  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata
0x3167b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31680  bne.un.s loc_31694
0x31682  ldarg.0
0x31683  ldarg.1
0x31684  ldarg.2
0x31685  ldarg.3
0x31686  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata
0x3168b  ldarg.s  4
0x3168d  ldc.i4.1
0x3168e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write28_IntegerAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata o, bool isNullable, bool needType)
0x31693  ret
0x31694  ldloc.0
0x31695  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata
0x3169a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3169f  bne.un.s loc_316B3
0x316a1  ldarg.0
0x316a2  ldarg.1
0x316a3  ldarg.2
0x316a4  ldarg.3
0x316a5  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata
0x316aa  ldarg.s  4
0x316ac  ldc.i4.1
0x316ad  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write25_MoneyAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata o, bool isNullable, bool needType)
0x316b2  ret
0x316b3  ldloc.0
0x316b4  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata
0x316b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x316be  bne.un.s loc_316D2
0x316c0  ldarg.0
0x316c1  ldarg.1
0x316c2  ldarg.2
0x316c3  ldarg.3
0x316c4  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata
0x316c9  ldarg.s  4
0x316cb  ldc.i4.1
0x316cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write23_FloatAttributeMetadata(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata o, bool isNullable, bool needType)
0x316d1  ret
0x316d2  ldarg.0
0x316d3  ldarg.3
0x316d4  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x316d9  throw
0x316da  ldarg.0
0x316db  ldarg.1
0x316dc  ldarg.2
0x316dd  ldarg.3
0x316de  ldc.i4.0
0x316df  ldnull
0x316e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x316e5  ldarg.s  5
0x316e7  brfalse.s loc_316F9
0x316e9  ldarg.0
0x316ea  ldstr    aAttributemetad// "AttributeMetadata"
0x316ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x316f4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x316f9  ldarg.0
0x316fa  ldstr    aMetadataid// "MetadataId"
0x316ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31704  ldarg.3
0x31705  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x3170a  ldc.i4.0
0x3170b  ldc.i4.0
0x3170c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x31711  ldarg.0
0x31712  ldstr    aSchemaname// "SchemaName"
0x31717  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3171c  ldarg.3
0x3171d  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x31722  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31727  ldarg.0
0x31728  ldstr    aLogicalname// "LogicalName"
0x3172d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31732  ldarg.3
0x31733  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x31738  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3173d  ldarg.0
0x3173e  ldstr    aEntitylogicaln// "EntityLogicalName"
0x31743  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31748  ldarg.3
0x31749  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x3174e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31753  ldarg.0
0x31754  ldstr    aAttributetype// "AttributeType"
0x31759  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3175e  ldarg.3
0x3175f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x31764  ldc.i4.0
0x31765  ldc.i4.0
0x31766  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x3176b  ldarg.0
0x3176c  ldstr    aDisplayname// "DisplayName"
0x31771  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31776  ldarg.3
0x31777  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x3177c  ldc.i4.0
0x3177d  ldc.i4.0
0x3177e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x31783  ldarg.0
0x31784  ldstr    aDescription// "Description"
0x31789  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3178e  ldarg.3
0x3178f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x31794  ldc.i4.0
0x31795  ldc.i4.0
0x31796  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x3179b  ldarg.0
0x3179c  ldstr    aIscustomfield// "IsCustomField"
0x317a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x317a6  ldarg.3
0x317a7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x317ac  ldc.i4.0
0x317ad  ldc.i4.0
0x317ae  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x317b3  ldarg.0
0x317b4  ldstr    aRequiredlevel// "RequiredLevel"
0x317b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x317be  ldarg.3
0x317bf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x317c4  ldc.i4.0
0x317c5  ldc.i4.0
0x317c6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x317cb  ldarg.0
0x317cc  ldstr    aDefaultvalue// "DefaultValue"
0x317d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x317d6  ldarg.3
0x317d7  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x317dc  ldc.i4.0
0x317dd  ldc.i4.0
0x317de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x317e3  ldarg.0
0x317e4  ldstr    aValidforcreate// "ValidForCreate"
0x317e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x317ee  ldarg.3
0x317ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x317f4  ldc.i4.0
0x317f5  ldc.i4.0
0x317f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x317fb  ldarg.0
0x317fc  ldstr    aValidforread// "ValidForRead"
0x31801  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31806  ldarg.3
0x31807  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x3180c  ldc.i4.0
0x3180d  ldc.i4.0
0x3180e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31813  ldarg.0
0x31814  ldstr    aValidforupdate// "ValidForUpdate"
0x31819  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3181e  ldarg.3
0x3181f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x31824  ldc.i4.0
0x31825  ldc.i4.0
0x31826  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x3182b  ldarg.0
0x3182c  ldstr    aDisplaymask// "DisplayMask"
0x31831  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31836  ldarg.3
0x31837  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x3183c  ldc.i4.0
0x3183d  ldc.i4.0
0x3183e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x31843  ldarg.0
0x31844  ldstr    aAggregateof// "AggregateOf"
0x31849  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
  ... truncated ...
```
