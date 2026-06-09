# Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::.cctor

- ea: `0x77270`
- end: `0x77324`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::.cctor`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## string_xrefs

- `0x77279`: `Attribute.xml`
- `0x77281`: `AttributeLookupValue.xml`
- `0x77289`: `AttributePicklistValue.xml`
- `0x77291`: `Entity.xml`
- `0x77299`: `EntityKey.xml`
- `0x772a1`: `EntityKeyAttribute.xml`
- `0x772a9`: `EntityRelationship.xml`
- `0x772b1`: `EntityRelationshipRelationships.xml`
- `0x772b9`: `EntityRelationshipRole.xml`
- `0x772c2`: `LocalizedLabel.xml`
- `0x772cb`: `ManagedProperty.xml`
- `0x772d4`: `OptionSet.xml`
- `0x772dd`: `Organization.xml`
- `0x772e6`: `Privilege.xml`
- `0x772ef`: `PrivilegeObjectTypeCode.xml`
- `0x772f8`: `Relationship.xml`
- `0x77301`: `RelationshipExtraCondition.xml`
- `0x7730a`: `RoleTemplatePrivilege.xml`
- `0x77313`: `ViewAttribute.xml`

## pseudocode

```c

```

## disassembly

```asm
0x77270  ldc.i4.s 0x13
0x77272  newarr   [mscorlib]System.String
0x77277  dup
0x77278  ldc.i4.0
0x77279  ldstr    aAttributeXml// "Attribute.xml"
0x7727e  stelem.ref
0x7727f  dup
0x77280  ldc.i4.1
0x77281  ldstr    aAttributelooku_9// "AttributeLookupValue.xml"
0x77286  stelem.ref
0x77287  dup
0x77288  ldc.i4.2
0x77289  ldstr    aAttributepickl_6// "AttributePicklistValue.xml"
0x7728e  stelem.ref
0x7728f  dup
0x77290  ldc.i4.3
0x77291  ldstr    aEntityXml// "Entity.xml"
0x77296  stelem.ref
0x77297  dup
0x77298  ldc.i4.4
0x77299  ldstr    aEntitykeyXml// "EntityKey.xml"
0x7729e  stelem.ref
0x7729f  dup
0x772a0  ldc.i4.5
0x772a1  ldstr    aEntitykeyattri_10// "EntityKeyAttribute.xml"
0x772a6  stelem.ref
0x772a7  dup
0x772a8  ldc.i4.6
0x772a9  ldstr    aEntityrelation_36// "EntityRelationship.xml"
0x772ae  stelem.ref
0x772af  dup
0x772b0  ldc.i4.7
0x772b1  ldstr    aEntityrelation_37// "EntityRelationshipRelationships.xml"
0x772b6  stelem.ref
0x772b7  dup
0x772b8  ldc.i4.8
0x772b9  ldstr    aEntityrelation_38// "EntityRelationshipRole.xml"
0x772be  stelem.ref
0x772bf  dup
0x772c0  ldc.i4.s 9
0x772c2  ldstr    aLocalizedlabel_15// "LocalizedLabel.xml"
0x772c7  stelem.ref
0x772c8  dup
0x772c9  ldc.i4.s 0xA
0x772cb  ldstr    aManagedpropert_26// "ManagedProperty.xml"
0x772d0  stelem.ref
0x772d1  dup
0x772d2  ldc.i4.s 0xB
0x772d4  ldstr    aOptionsetXml// "OptionSet.xml"
0x772d9  stelem.ref
0x772da  dup
0x772db  ldc.i4.s 0xC
0x772dd  ldstr    aOrganizationXm// "Organization.xml"
0x772e2  stelem.ref
0x772e3  dup
0x772e4  ldc.i4.s 0xD
0x772e6  ldstr    aPrivilegeXml// "Privilege.xml"
0x772eb  stelem.ref
0x772ec  dup
0x772ed  ldc.i4.s 0xE
0x772ef  ldstr    aPrivilegeobjec_7// "PrivilegeObjectTypeCode.xml"
0x772f4  stelem.ref
0x772f5  dup
0x772f6  ldc.i4.s 0xF
0x772f8  ldstr    aRelationshipXm_4// "Relationship.xml"
0x772fd  stelem.ref
0x772fe  dup
0x772ff  ldc.i4.s 0x10
0x77301  ldstr    aRelationshipex_11// "RelationshipExtraCondition.xml"
0x77306  stelem.ref
0x77307  dup
0x77308  ldc.i4.s 0x11
0x7730a  ldstr    aRoletemplatepr_10// "RoleTemplatePrivilege.xml"
0x7730f  stelem.ref
0x77310  dup
0x77311  ldc.i4.s 0x12
0x77313  ldstr    aViewattributeX_2// "ViewAttribute.xml"
0x77318  stelem.ref
0x77319  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x7731e  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::MetadataForMetadataXmlFiles
0x77323  ret
```
