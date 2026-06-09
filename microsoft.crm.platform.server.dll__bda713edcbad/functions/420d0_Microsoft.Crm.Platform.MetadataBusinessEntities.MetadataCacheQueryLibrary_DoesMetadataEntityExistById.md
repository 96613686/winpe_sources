# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataCacheQueryLibrary::DoesMetadataEntityExistById

- ea: `0x420d0`
- end: `0x4241e`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataCacheQueryLibrary::DoesMetadataEntityExistById`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x45390`

## callees

- `0x420d0`
- `0x85d00`

## string_xrefs

- `0x422a7`: `Privilege`
- `0x422bc`: `PrivilegeObjectTypeCode`
- `0x422d1`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x420d0  ldarg.0
0x420d1  ldstr    aMetadataentity// "metadataEntityName"
0x420d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x420db  ldarg.0
0x420dc  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x420e1  stloc.0
0x420e2  ldloc.0
0x420e3  ldc.i4   0x62FA988F
0x420e8  bgt.un.s loc_42156
0x420ea  ldloc.0
0x420eb  ldc.i4   0x21E27D10
0x420f0  bgt.un.s loc_42118
0x420f2  ldloc.0
0x420f3  ldc.i4   0x1ACCD85B
0x420f8  beq      loc_4227C
0x420fd  ldloc.0
0x420fe  ldc.i4   0x1D72D1E6
0x42103  beq      loc_422D0
0x42108  ldloc.0
0x42109  ldc.i4   0x21E27D10
0x4210e  beq      loc_42267
0x42113  br       loc_423FF
0x42118  ldloc.0
0x42119  ldc.i4   0x3578225F
0x4211e  bgt.un.s loc_4213B
0x42120  ldloc.0
0x42121  ldc.i4   0x2FB17EF0
0x42126  beq      loc_42291
0x4212b  ldloc.0
0x4212c  ldc.i4   0x3578225F
0x42131  beq      loc_42228
0x42136  br       loc_423FF
0x4213b  ldloc.0
0x4213c  ldc.i4   0x4F6B9560
0x42141  beq      loc_4223D
0x42146  ldloc.0
0x42147  ldc.i4   0x62FA988F
0x4214c  beq      loc_42213
0x42151  br       loc_423FF
0x42156  ldloc.0
0x42157  ldc.i4   0x9F56E047
0x4215c  bgt.un.s loc_4219C
0x4215e  ldloc.0
0x4215f  ldc.i4   0x80D2874B
0x42164  bgt.un.s loc_42181
0x42166  ldloc.0
0x42167  ldc.i4   0x6E61547A
0x4216c  beq      loc_422BB
0x42171  ldloc.0
0x42172  ldc.i4   0x80D2874B
0x42177  beq      loc_421FE
0x4217c  br       loc_423FF
0x42181  ldloc.0
0x42182  ldc.i4   0x946992DC
0x42187  beq      loc_422E5
0x4218c  ldloc.0
0x4218d  ldc.i4   0x9F56E047
0x42192  beq      loc_42252
0x42197  br       loc_423FF
0x4219c  ldloc.0
0x4219d  ldc.i4   0xC0670678
0x421a2  bgt.un.s loc_421BC
0x421a4  ldloc.0
0x421a5  ldc.i4   0xA6468091
0x421aa  beq.s    loc_421E9
0x421ac  ldloc.0
0x421ad  ldc.i4   0xC0670678
0x421b2  beq      loc_422FA
0x421b7  br       loc_423FF
0x421bc  ldloc.0
0x421bd  ldc.i4   0xC09B32FA
0x421c2  beq.s    loc_421D4
0x421c4  ldloc.0
0x421c5  ldc.i4   0xF92D43AC
0x421ca  beq      loc_422A6
0x421cf  br       loc_423FF
0x421d4  ldarg.0
0x421d5  ldstr    aEntity// "Entity"
0x421da  call     bool [mscorlib]System.String::op_Equality(string, string)
0x421df  brtrue   loc_4230F
0x421e4  br       loc_423FF
0x421e9  ldarg.0
0x421ea  ldstr    aEntitykey// "EntityKey"
0x421ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x421f4  brtrue   loc_4231F
0x421f9  br       loc_423FF
0x421fe  ldarg.0
0x421ff  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x42204  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42209  brtrue   loc_4232F
0x4220e  br       loc_423FF
0x42213  ldarg.0
0x42214  ldstr    aAttribute// "Attribute"
0x42219  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4221e  brtrue   loc_4233F
0x42223  br       loc_423FF
0x42228  ldarg.0
0x42229  ldstr    aAttributepickl// "AttributePicklistValue"
0x4222e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42233  brtrue   loc_4234F
0x42238  br       loc_423FF
0x4223d  ldarg.0
0x4223e  ldstr    aEntityrelation// "EntityRelationship"
0x42243  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42248  brtrue   loc_4235F
0x4224d  br       loc_423FF
0x42252  ldarg.0
0x42253  ldstr    aEntityrelation_1// "EntityRelationshipRelationships"
0x42258  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4225d  brtrue   loc_4236F
0x42262  br       loc_423FF
0x42267  ldarg.0
0x42268  ldstr    aEntityrelation_0// "EntityRelationshipRole"
0x4226d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42272  brtrue   loc_4237F
0x42277  br       loc_423FF
0x4227c  ldarg.0
0x4227d  ldstr    aRelationship// "Relationship"
0x42282  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42287  brtrue   loc_4238F
0x4228c  br       loc_423FF
0x42291  ldarg.0
0x42292  ldstr    aRelationshipex// "RelationshipExtraCondition"
0x42297  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4229c  brtrue   loc_4239F
0x422a1  br       loc_423FF
0x422a6  ldarg.0
0x422a7  ldstr    aPrivilege// "Privilege"
0x422ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x422b1  brtrue   loc_423AF
0x422b6  br       loc_423FF
0x422bb  ldarg.0
0x422bc  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x422c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x422c6  brtrue   loc_423BF
0x422cb  br       loc_423FF
0x422d0  ldarg.0
0x422d1  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x422d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x422db  brtrue   loc_423CF
0x422e0  br       loc_423FF
0x422e5  ldarg.0
0x422e6  ldstr    aOptionset// "OptionSet"
0x422eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x422f0  brtrue   loc_423DF
0x422f5  br       loc_423FF
0x422fa  ldarg.0
0x422fb  ldstr    aViewattribute// "ViewAttribute"
0x42300  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42305  brtrue   loc_423EF
0x4230a  br       loc_423FF
0x4230f  ldarg.2
0x42310  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42315  ldarg.1
0x42316  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(valuetype [mscorlib]System.Guid)
0x4231b  ldnull
0x4231c  cgt.un
0x4231e  ret
0x4231f  ldarg.2
0x42320  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42325  ldarg.1
0x42326  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityKey(valuetype [mscorlib]System.Guid)
0x4232b  ldnull
0x4232c  cgt.un
0x4232e  ret
0x4232f  ldarg.2
0x42330  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42335  ldarg.1
0x42336  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityKeyAttribute(valuetype [mscorlib]System.Guid)
0x4233b  ldnull
0x4233c  cgt.un
0x4233e  ret
0x4233f  ldarg.2
0x42340  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42345  ldarg.1
0x42346  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetAttribute(valuetype [mscorlib]System.Guid)
0x4234b  ldnull
0x4234c  cgt.un
0x4234e  ret
0x4234f  ldarg.2
0x42350  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42355  ldarg.1
0x42356  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEnumOption(valuetype [mscorlib]System.Guid)
0x4235b  ldnull
0x4235c  cgt.un
0x4235e  ret
0x4235f  ldarg.2
0x42360  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42365  ldarg.1
0x42366  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityRelationship(valuetype [mscorlib]System.Guid)
0x4236b  ldnull
0x4236c  cgt.un
0x4236e  ret
0x4236f  ldarg.2
0x42370  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42375  ldarg.1
0x42376  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRelationships [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityRelationshipRelationship(valuetype [mscorlib]System.Guid)
0x4237b  ldnull
0x4237c  cgt.un
0x4237e  ret
0x4237f  ldarg.2
0x42380  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42385  ldarg.1
0x42386  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityRelationshipRole(valuetype [mscorlib]System.Guid)
0x4238b  ldnull
0x4238c  cgt.un
0x4238e  ret
0x4238f  ldarg.2
0x42390  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42395  ldarg.1
0x42396  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRelationship(valuetype [mscorlib]System.Guid)
0x4239b  ldnull
0x4239c  cgt.un
0x4239e  ret
0x4239f  ldarg.2
0x423a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423a5  ldarg.1
0x423a6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRelationshipExtraCondition(valuetype [mscorlib]System.Guid)
0x423ab  ldnull
0x423ac  cgt.un
0x423ae  ret
0x423af  ldarg.2
0x423b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423b5  ldarg.1
0x423b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetPrivilege(valuetype [mscorlib]System.Guid)
0x423bb  ldnull
0x423bc  cgt.un
0x423be  ret
0x423bf  ldarg.2
0x423c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423c5  ldarg.1
0x423c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetPrivilegeObjectTypeCode(valuetype [mscorlib]System.Guid)
0x423cb  ldnull
0x423cc  cgt.un
0x423ce  ret
0x423cf  ldarg.2
0x423d0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423d5  ldarg.1
0x423d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RoleTemplatePrivilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRoleTemplatePrivilege(valuetype [mscorlib]System.Guid)
0x423db  ldnull
0x423dc  cgt.un
0x423de  ret
0x423df  ldarg.2
0x423e0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423e5  ldarg.1
0x423e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(valuetype [mscorlib]System.Guid)
0x423eb  ldnull
0x423ec  cgt.un
0x423ee  ret
0x423ef  ldarg.2
0x423f0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x423f5  ldarg.1
0x423f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ViewInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetViewAttribute(valuetype [mscorlib]System.Guid)
0x423fb  ldnull
0x423fc  cgt.un
0x423fe  ret
0x423ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42404  ldstr    aDoesmetadataen// "DoesMetadataEntityExistById for Metadat"...
0x42409  ldc.i4.1
0x4240a  newarr   [mscorlib]System.Object
0x4240f  dup
0x42410  ldc.i4.0
0x42411  ldarg.0
0x42412  stelem.ref
0x42413  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42418  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotImplementedException::.ctor(string)
0x4241d  throw
```
