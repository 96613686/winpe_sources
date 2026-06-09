# Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x26e30`
- end: `0x27abc`
- name: `Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `3212`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x24e40`
- `0x26560`
- `0x26e30`
- `0x42b40`
- `0x42c00`
- `0x42de0`
- `0x42ed0`
- `0x42ff0`
- `0x43310`
- `0x433a0`
- `0x443d0`
- `0x468c0`
- `0x6fd60`
- `0x6fe90`
- `0xa94d0`

## string_xrefs

- `0x26ec5`: `validforupdateapi`
- `0x26ed6`: `validforreadapi`
- `0x26ee7`: `validforcreateapi`
- `0x26f7f`: `isidentity`
- `0x27030`: `canbesecuredforcreate`
- `0x27041`: `canbesecuredforread`
- `0x27052`: `canbesecuredforupdate`
- `0x27085`: `isrenameable`

## pseudocode

```c

```

## disassembly

```asm
0x26e30  ldarg.2
0x26e31  newobj   instance void Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x26e36  stloc.0
0x26e37  ldloc.0
0x26e38  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x26e3d  stloc.1
0x26e3e  ldloc.1
0x26e3f  ldstr    aAttributeid_1// "attributeid"
0x26e44  ldarg.0
0x26e45  box      [mscorlib]System.Guid
0x26e4a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26e4f  ldloc.1
0x26e50  ldstr    aAttributetypei// "attributetypeid"
0x26e55  ldarg.1
0x26e56  box      [mscorlib]System.Guid
0x26e5b  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26e60  call     class Microsoft.Crm.Metadata.AttributeTypeDictionary Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x26e65  ldarg.1
0x26e66  box      [mscorlib]System.Guid
0x26e6b  callvirt instance class Microsoft.Crm.Metadata.AttributeTypeInfo Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object key)
0x26e70  stloc.2
0x26e71  ldloc.2
0x26e72  callvirt instance int32 Microsoft.Crm.Metadata.AttributeTypeInfo::get_Length()
0x26e77  brfalse.s loc_26E91
0x26e79  ldloc.1
0x26e7a  ldstr    aLength_0// "length"
0x26e7f  ldloc.2
0x26e80  callvirt instance int32 Microsoft.Crm.Metadata.AttributeTypeInfo::get_Length()
0x26e85  box      [mscorlib]System.Int32
0x26e8a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26e8f  br.s     loc_26EA2
0x26e91  ldloc.1
0x26e92  ldstr    aLength_0// "length"
0x26e97  ldc.i4.0
0x26e98  box      [mscorlib]System.Int32
0x26e9d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ea2  ldloc.1
0x26ea3  ldstr    aIsnullable_0// "isnullable"
0x26ea8  ldc.i4.1
0x26ea9  box      [mscorlib]System.Boolean
0x26eae  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26eb3  ldloc.1
0x26eb4  ldstr    aColumnnumber_0// "columnnumber"
0x26eb9  ldc.i4.0
0x26eba  box      [mscorlib]System.Int32
0x26ebf  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ec4  ldloc.1
0x26ec5  ldstr    aValidforupdate_1// "validforupdateapi"
0x26eca  ldc.i4.0
0x26ecb  box      [mscorlib]System.Boolean
0x26ed0  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ed5  ldloc.1
0x26ed6  ldstr    aValidforreadap_1// "validforreadapi"
0x26edb  ldc.i4.0
0x26edc  box      [mscorlib]System.Boolean
0x26ee1  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ee6  ldloc.1
0x26ee7  ldstr    aValidforcreate_1// "validforcreateapi"
0x26eec  ldc.i4.0
0x26eed  box      [mscorlib]System.Boolean
0x26ef2  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ef7  ldloc.1
0x26ef8  ldstr    aVisibletoplatf_0// "visibletoplatform"
0x26efd  ldc.i4.1
0x26efe  box      [mscorlib]System.Boolean
0x26f03  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f08  ldloc.1
0x26f09  ldstr    aIspkattribute_0// "ispkattribute"
0x26f0e  ldc.i4.0
0x26f0f  box      [mscorlib]System.Boolean
0x26f14  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f19  ldloc.1
0x26f1a  ldstr    aAutonumberform_0// "autonumberformat"
0x26f1f  ldsfld   string [mscorlib]System.String::Empty
0x26f24  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f29  ldloc.1
0x26f2a  ldstr    aIscustomfield_0// "iscustomfield"
0x26f2f  ldc.i4.0
0x26f30  box      [mscorlib]System.Boolean
0x26f35  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f3a  ldloc.1
0x26f3b  ldstr    aIslogical_0// "islogical"
0x26f40  ldc.i4.0
0x26f41  box      [mscorlib]System.Boolean
0x26f46  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f4b  ldloc.1
0x26f4c  ldstr    aDisplaymask_0// "displaymask"
0x26f51  ldc.i4.0
0x26f52  box      [mscorlib]System.Int32
0x26f57  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f5c  ldloc.1
0x26f5d  ldstr    aReferencedenti_2// "referencedentityobjecttypecode"
0x26f62  ldc.i4.0
0x26f63  box      [mscorlib]System.Int32
0x26f68  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f6d  ldloc.1
0x26f6e  ldstr    aIssortattribut_0// "issortattribute"
0x26f73  ldc.i4.0
0x26f74  box      [mscorlib]System.Boolean
0x26f79  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f7e  ldloc.1
0x26f7f  ldstr    aIsidentity_0// "isidentity"
0x26f84  ldc.i4.0
0x26f85  box      [mscorlib]System.Boolean
0x26f8a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26f8f  ldloc.1
0x26f90  ldstr    aIsreplicated_0// "isreplicated"
0x26f95  ldc.i4.1
0x26f96  box      [mscorlib]System.Boolean
0x26f9b  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26fa0  ldloc.1
0x26fa1  ldstr    aIsauditenabled_0// "isauditenabled"
0x26fa6  ldc.i4.1
0x26fa7  box      [mscorlib]System.Boolean
0x26fac  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26fb1  ldloc.1
0x26fb2  ldstr    aIsrowguidattri_0// "isrowguidattribute"
0x26fb7  ldc.i4.0
0x26fb8  box      [mscorlib]System.Boolean
0x26fbd  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26fc2  ldloc.1
0x26fc3  ldstr    aHasmultiplelab_0// "hasmultiplelabels"
0x26fc8  ldc.i4.0
0x26fc9  box      [mscorlib]System.Boolean
0x26fce  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26fd3  ldloc.1
0x26fd4  ldstr    aAttributeof_0// "attributeof"
0x26fd9  ldnull
0x26fda  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26fdf  ldloc.1
0x26fe0  ldstr    aInheritsfrom_0// "inheritsfrom"
0x26fe5  ldnull
0x26fe6  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26feb  ldloc.1
0x26fec  ldstr    aIsstoredonprim_0// "isstoredonprimarytable"
0x26ff1  ldc.i4.1
0x26ff2  box      [mscorlib]System.Boolean
0x26ff7  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x26ffc  ldloc.1
0x26ffd  ldstr    aIsinheritancet_0// "isinheritancetypeattribute"
0x27002  ldc.i4.0
0x27003  box      [mscorlib]System.Boolean
0x27008  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x2700d  ldloc.1
0x2700e  ldstr    aIsunmanagedatt_0// "isunmanagedattribute"
0x27013  ldc.i4.0
0x27014  box      [mscorlib]System.Boolean
0x27019  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x2701e  ldloc.1
0x2701f  ldstr    aIsonewayboolea_0// "isonewaybooleanattribute"
0x27024  ldc.i4.0
0x27025  box      [mscorlib]System.Boolean
0x2702a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x2702f  ldloc.1
0x27030  ldstr    aCanbesecuredfo_2// "canbesecuredforcreate"
0x27035  ldc.i4.0
0x27036  box      [mscorlib]System.Boolean
0x2703b  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27040  ldloc.1
0x27041  ldstr    aCanbesecuredfo_3// "canbesecuredforread"
0x27046  ldc.i4.0
0x27047  box      [mscorlib]System.Boolean
0x2704c  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27051  ldloc.1
0x27052  ldstr    aCanbesecuredfo_4// "canbesecuredforupdate"
0x27057  ldc.i4.0
0x27058  box      [mscorlib]System.Boolean
0x2705d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27062  ldloc.1
0x27063  ldstr    aIssecured_0// "issecured"
0x27068  ldc.i4.0
0x27069  box      [mscorlib]System.Boolean
0x2706e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27073  ldloc.1
0x27074  ldstr    aIscustomizable_0// "iscustomizable"
0x27079  ldc.i4.1
0x2707a  box      [mscorlib]System.Boolean
0x2707f  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27084  ldloc.1
0x27085  ldstr    aIsrenameable_0// "isrenameable"
0x2708a  ldc.i4.1
0x2708b  box      [mscorlib]System.Boolean
0x27090  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27095  ldloc.1
0x27096  ldstr    aCanmodifysearc_0// "canmodifysearchsettings"
0x2709b  ldc.i4.1
0x2709c  box      [mscorlib]System.Boolean
0x270a1  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270a6  ldloc.1
0x270a7  ldstr    aIsfilterablese// "isfilterablesetbysystem"
0x270ac  ldc.i4.0
0x270ad  box      [mscorlib]System.Boolean
0x270b2  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270b7  ldloc.1
0x270b8  ldstr    aIsretrievables// "isretrievablesetbysystem"
0x270bd  ldc.i4.0
0x270be  box      [mscorlib]System.Boolean
0x270c3  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270c8  ldloc.1
0x270c9  ldstr    aCanmodifyrequi_0// "canmodifyrequirementlevelsettings"
0x270ce  ldc.i4.1
0x270cf  box      [mscorlib]System.Boolean
0x270d4  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270d9  ldloc.1
0x270da  ldstr    aCanmodifyaddit_0// "canmodifyadditionalsettings"
0x270df  ldc.i4.1
0x270e0  box      [mscorlib]System.Boolean
0x270e5  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270ea  ldloc.1
0x270eb  ldstr    aCanmodifyaudit_0// "canmodifyauditsettings"
0x270f0  ldc.i4.1
0x270f1  box      [mscorlib]System.Boolean
0x270f6  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x270fb  ldloc.1
0x270fc  ldstr    aValuesfromrela_1// "valuesfromrelationshipattribute"
0x27101  ldnull
0x27102  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27107  ldloc.1
0x27108  ldstr    aSourcetype_0// "sourcetype"
0x2710d  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x27112  brfalse.s loc_27125
0x27114  ldloc.1
0x27115  ldstr    aSourcetype_0// "sourcetype"
0x2711a  ldc.i4.0
0x2711b  box      [mscorlib]System.Int32
0x27120  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27125  ldloc.1
0x27126  ldstr    aSourcetypemask_0// "sourcetypemask"
0x2712b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x27130  brfalse.s loc_27143
0x27132  ldloc.1
0x27133  ldstr    aSourcetypemask_0// "sourcetypemask"
0x27138  ldc.i4.0
0x27139  box      [mscorlib]System.Int32
0x2713e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27143  ldloc.1
0x27144  ldstr    aIsactive_0// "isactive"
0x27149  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x2714e  brfalse.s loc_27161
0x27150  ldloc.1
0x27151  ldstr    aIsactive_0// "isactive"
0x27156  ldc.i4.1
0x27157  box      [mscorlib]System.Boolean
0x2715c  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27161  ldloc.1
0x27162  ldstr    aIsdatasourcese_0// "isdatasourcesecret"
0x27167  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x2716c  brfalse.s loc_2717F
0x2716e  ldloc.1
0x2716f  ldstr    aIsdatasourcese_0// "isdatasourcesecret"
0x27174  ldc.i4.0
0x27175  box      [mscorlib]System.Boolean
0x2717a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x2717f  ldloc.1
0x27180  ldstr    aIsglobalfilter_0// "isglobalfilterenabled"
0x27185  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x2718a  brfalse.s loc_2719D
0x2718c  ldloc.1
0x2718d  ldstr    aIsglobalfilter_0// "isglobalfilterenabled"
0x27192  ldc.i4.0
0x27193  box      [mscorlib]System.Boolean
0x27198  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x2719d  ldloc.1
0x2719e  ldstr    aIssortableenab_0// "issortableenabled"
0x271a3  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x271a8  brfalse.s loc_271BB
0x271aa  ldloc.1
0x271ab  ldstr    aIssortableenab_0// "issortableenabled"
0x271b0  ldc.i4.0
0x271b1  box      [mscorlib]System.Boolean
0x271b6  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x271bb  ldloc.1
0x271bc  ldstr    aCanmodifygloba_0// "canmodifyglobalfiltersettings"
0x271c1  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x271c6  brfalse.s loc_271D9
0x271c8  ldloc.1
0x271c9  ldstr    aCanmodifygloba_0// "canmodifyglobalfiltersettings"
0x271ce  ldc.i4.1
0x271cf  box      [mscorlib]System.Boolean
0x271d4  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x271d9  ldloc.1
0x271da  ldstr    aCanmodifyissor_0// "canmodifyissortablesettings"
0x271df  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x271e4  brfalse.s loc_271F7
0x271e6  ldloc.1
0x271e7  ldstr    aCanmodifyissor_0// "canmodifyissortablesettings"
0x271ec  ldc.i4.1
0x271ed  box      [mscorlib]System.Boolean
0x271f2  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x271f7  ldloc.1
0x271f8  ldstr    aLocked_0// "locked"
0x271fd  ldc.i4.0
0x271fe  box      [mscorlib]System.Boolean
0x27203  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27208  ldloc.1
0x27209  ldstr    aAttributeimemo_0// "attributeimemodeid"
0x2720e  ldstr    aAuto// "auto"
0x27213  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x27218  ldloc.1
0x27219  ldstr    aAttributerequi_0// "attributerequiredlevelid"
  ... truncated ...
```
