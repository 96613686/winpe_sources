# Microsoft.Crm.Metadata.AttributeMetadata::.cctor

- ea: `0x12930`
- end: `0x12b13`
- name: `Microsoft.Crm.Metadata.AttributeMetadata::.cctor`
- size: `483`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x43300`
- `0x443e0`
- `0x468c0`

## string_xrefs

- `0x12a21`: `createdon`
- `0x12a5b`: `createdon`
- `0x12a91`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x12930  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x12935  dup
0x12936  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1293b  ldstr    aLookup// "lookup"
0x12940  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x12945  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1294a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1294f  dup
0x12950  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x12955  ldstr    aCustomer// "customer"
0x1295a  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x1295f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x12964  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x12969  dup
0x1296a  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1296f  ldstr    aOwner// "owner"
0x12974  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x12979  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1297e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x12983  stsfld   class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeMetadata::LookupCustomerOwnerAttributeTypeIds
0x12988  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1298d  dup
0x1298e  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x12993  ldstr    aPicklist// "picklist"
0x12998  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x1299d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x129a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x129a7  dup
0x129a8  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x129ad  ldstr    aState// "state"
0x129b2  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x129b7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x129bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x129c1  dup
0x129c2  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x129c7  ldstr    aStatus// "status"
0x129cc  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x129d1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x129d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x129db  stsfld   class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeMetadata::PickListStateStatusAttributeTypeIds
0x129e0  ldc.i4.s 9
0x129e2  newarr   [mscorlib]System.String
0x129e7  dup
0x129e8  ldc.i4.0
0x129e9  ldstr    aOwnerid// "ownerid"
0x129ee  stelem.ref
0x129ef  dup
0x129f0  ldc.i4.1
0x129f1  ldstr    aOwningbusiness// "owningbusinessunit"
0x129f6  stelem.ref
0x129f7  dup
0x129f8  ldc.i4.2
0x129f9  ldstr    aBusinessunitid// "businessunitid"
0x129fe  stelem.ref
0x129ff  dup
0x12a00  ldc.i4.3
0x12a01  ldstr    aVersionnumber// "versionnumber"
0x12a06  stelem.ref
0x12a07  dup
0x12a08  ldc.i4.4
0x12a09  ldstr    aStatecode// "statecode"
0x12a0e  stelem.ref
0x12a0f  dup
0x12a10  ldc.i4.5
0x12a11  ldstr    aStatuscode// "statuscode"
0x12a16  stelem.ref
0x12a17  dup
0x12a18  ldc.i4.6
0x12a19  ldstr    aEntityimageUrl// "entityimage_url"
0x12a1e  stelem.ref
0x12a1f  dup
0x12a20  ldc.i4.7
0x12a21  ldstr    aCreatedon// "createdon"
0x12a26  stelem.ref
0x12a27  dup
0x12a28  ldc.i4.8
0x12a29  ldstr    aModifiedon// "modifiedon"
0x12a2e  stelem.ref
0x12a2f  stsfld   string[] Microsoft.Crm.Metadata.AttributeMetadata::NamedAttributesSharedInSearchIndex
0x12a34  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a39  dup
0x12a3a  ldstr    aOwnerid// "ownerid"
0x12a3f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a44  dup
0x12a45  ldstr    aOwningbusiness// "owningbusinessunit"
0x12a4a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a4f  dup
0x12a50  ldstr    aBusinessunitid// "businessunitid"
0x12a55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a5a  dup
0x12a5b  ldstr    aCreatedon// "createdon"
0x12a60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a65  dup
0x12a66  ldstr    aModifiedon// "modifiedon"
0x12a6b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a70  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.AttributeMetadata::NamedAttributesWhereIsFilterableSetBySystem
0x12a75  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12a7a  dup
0x12a7b  ldstr    aVersionnumber// "versionnumber"
0x12a80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a85  dup
0x12a86  ldstr    aEntityimageUrl// "entityimage_url"
0x12a8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a90  dup
0x12a91  ldstr    aCreatedon// "createdon"
0x12a96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12a9b  dup
0x12a9c  ldstr    aModifiedon// "modifiedon"
0x12aa1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12aa6  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.AttributeMetadata::NamedAttributesWhereIsRetrievableSetBySystem
0x12aab  ldc.i4.4
0x12aac  conv.i8
0x12aad  ldsfld   int64 [Microsoft.Crm.Core]Microsoft.Crm.BasicSizeConstants::Pointer
0x12ab2  mul
0x12ab3  stsfld   int64 Microsoft.Crm.Metadata.AttributeMetadata::initialAttributeSize
0x12ab8  ldstr    a95ae88b3Cc0c45// "95AE88B3-CC0C-45AC-A2DB-655DCEEC238B"
0x12abd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12ac2  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::EmailEntityId
0x12ac7  ldstr    a39245040E28648// "39245040-E286-48FF-9D9D-BEF07835A376"
0x12acc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12ad1  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::EmailSafeDescriptionAttributeId
0x12ad6  ldstr    a95e930c5812a44// "95e930c5-812a-44e8-85c9-154cd5f59465"
0x12adb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12ae0  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::AppointmentEntityId
0x12ae5  ldstr    a0b242a488e9646// "0b242a48-8e96-461b-875c-d2cab1e8e472"
0x12aea  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12aef  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::AppointmentSafeDescriptionAttributeId
0x12af4  ldstr    aE4796c89Bd4744// "e4796c89-bd47-4413-a5ff-92959ac3a3e0"
0x12af9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12afe  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::RecurringAppointmentEntityId
0x12b03  ldstr    aA6ace66f174248// "a6ace66f-1742-4866-93de-41c1ea9d5e4c"
0x12b08  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12b0d  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeMetadata::RecurringAppointmentSafeDescriptionAttributeId
0x12b12  ret
```
